---
title: Använd DKIM för e-post i din anpassade domän i Office 365, 2048-bitars, 1024-bitars, steg, hur den fungerar, SPF, DMARC
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Sammanfattning: i den här artikeln beskrivs hur du använder DomainKeys Identified Mail (DKIM) med Office 365 för att säkerställa att mål-e-postsystemen litar på meddelanden som skickas från din anpassade domän.'
ms.openlocfilehash: d76c31c6a3f0ce1550f0259ee40996189b60cb79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811473"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a>Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365

 **Sammanfattning:** i den här artikeln beskrivs hur du använder DomainKeys Identified Mail (DKIM) med Office 365 för att säkerställa att mål-e-postsystemen litar på utgående meddelanden som skickas från din anpassade domän.

Du bör använda DKIM tillsammans med SPF och DMARC för att förhindra att förfalskare skickar meddelanden som ser ut som att de kommer från din domän. Med DKIM kan du lägga till en digital signatur i utgående e-postmeddelanden i meddelandehuvudet. Det kan vara komplicerat, men det är det faktiskt inte. När du konfigurerar DKIM verifierar du att din domän ska kopplas till ett e-postmeddelande med hjälp av krypterad autentisering. E-postsystem som får e-post från din domän använder denna digitala signatur för att fastställa om inkommande e-post som tas emot är legitim.

I stort sett använder du en privat nyckel för att kryptera huvudet i domänens utgående e-post. Du publicerar en offentlig nyckel i din domäns DNS-poster som tar emot servrar som sedan kan användas för att avkoda signaturen. De använder en offentlig nyckel för att kontrollera att de verkligen kommer från dig och att de inte kommer från någon som *förfalskar* din domän.

I Office 365 konfigureras automatiskt DKIM för dess ursprungliga ”onmicrosoft.com”-domäner. Det innebär att du inte behöver göra något för att konfigurera DKIM för alla inledande domännamn (t. ex. litware.onmicrosoft.com). Mer information om domäner finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

Du kan också välja att inte göra något med DKIM för din anpassade domän. Om du inte konfigurerar DKIM för din anpassade domän skapar Office 365 ett privat och offentligt nyckelpar, aktiverar DKIM-signering och konfigurerar sedan standardprincipen för Office 365 för din anpassade domän. Även om det är tillräcklig täckning för de flesta Office 365-kunder ska du manuellt konfigurera DKIM för din anpassade domän i följande fall:

- Du har fler än en anpassad domän i Office 365

- Du ska även konfigurera DMARC (rekommenderas)

- Du vill ha kontroll över din privata nyckel

- Du vill anpassa dina CNAME-poster

- Du vill konfigurera DKIM-nycklar för e-post som kommer från en domän från tredje part, t. ex. om du använder ett massutskick från tredje part.

I den här artikeln:

- [Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning i Office 365](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [Steg du behöver göra för att konfigurera DKIM manuellt i Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [Konfigurera fler än en anpassad domän i Office 365](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [Inaktivera DKIM-signeringsprincipen för en anpassad domän i Office 365](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [Standardbeteende för DKIM och Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [Nästa steg: När du har konfigurerat DKIM för Office 365](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a>Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning i Office 365
<a name="HowDKIMWorks"> </a>

SPF lägger till information i ett meddelandekuvert, men DKIM krypterar faktiskt en signatur i meddelandehuvudet. När du vidarebefordrar ett meddelande kan delar av meddelandets kuvert vara rensade av vidarebefordringsservern. Eftersom den digitala signaturen ligger kvar i e-postmeddelandet eftersom den är en del av e-postmeddelandets huvud fungerar DKIM även när ett meddelande har vidarebefordrats enligt följande exempel.

![Diagram som visar ett vidarebefordrat meddelande som skickar DKIM-autentiseringen där SPF-kontrollen misslyckades](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

Om du bara hade publicerat en SPF TXT-post för domänen i det här exemplet skulle mottagarens e-postserver ha markerat e-postmeddelandet som skräppost och genererat ett falskt positivt resultat. Om du lägger till DKIM i det här scenariot minskas falska positiva skräppostrapporter. Eftersom DKIM använder offentlig nyckelkryptering för att autentisera och inte bara IP-adresser anses DKIM vara en mycket starkare autentiseringsmetod än SPF. Vi rekommenderar att du använder både SPF och DKIM, och även DMARC i din distribution.

Nitty Gritty: DKIM använder en privat nyckel för att infoga en krypterad signatur i meddelandehuvudena. Signeringsdomänen, eller den utgående domänen, infogas som värdet för fältet **d =** i huvudet. Den verifierade domänen, eller mottagarens domän använder sedan fältet **d=** för att leta upp den offentliga nyckeln från DNS och autentisera meddelandet. Om meddelandet har bekräftats godkänns DKIM-kontrollen.

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar
<a name="1024to2048DKIM"> </a>

Eftersom både 1024 och 2048 bitar stöds för DKIM-nycklar visar riktningarna hur du ska uppgradera din 1024-bitarsnyckel till 2048. Stegen nedan gäller för två användningsfall: Välj det som passar bäst för konfigurationen.

1. När du **redan har konfigurerat DKIM** kan du rotera bitar enligt följande:
    1. [Ansluta till Office 365-arbetsbelastningar via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (Cmdleten kommer från Exchange Online.)
    1. Kör sedan följande cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`

1. Eller för en **ny implementation av DKIM**:
    1. [Ansluta till Office 365-arbetsbelastningar via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window). (Det här är en Exchange Online-cmdlet.)
    1. Kör följande cmdlet:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`

Fortsätt att vara ansluten till Office 365 för att *verifiera* konfigurationen.

2. Kör cmdleten:

&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`

> [!TIP]
>Den här nya 2048-bitarsnyckeln träder i kraft på RotateOnDate och skickar e-postmeddelanden med 1024-bitarsnyckeln i interimversionen. Efter fyra dagar kan du testa igen med 2048-bitarsnyckeln (det vill säga när rotationen träder i kraft i den andra väljaren).

Om du vill rotera till den andra väljaren är dina alternativ a) att låta Office 365-tjänsten rotera väljaren och uppgradera till 2048 bitar inom de kommande sex månaderna och b) att efter fyra dagar bekräfta att 2048-bitar används, manuellt rotera den andra väljarknappen med hjälp av lämplig cmdlet.

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a>Steg du behöver göra för att konfigurera DKIM manuellt i Office 365
<a name="SetUpDKIMO365"> </a>

Om du vill konfigurera DKIM gör du så här:

- [Publicera två CNAME-poster för din anpassade domän i DNS](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [Aktivera DKIM-signering för din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>Publicera två CNAME-poster för din anpassade domän i DNS
<a name="Publish2CNAME"> </a>

För varje domän som du vill lägga till en DKIM-signatur för måste du publicera två CNAME-poster.

Kör följande kommandon för att skapa väljarposterna:

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

Skapa CNAME-referenser i Get-DkimSigningConfig-utdata

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

I Office 365 utförs automatisk nyckelrotation med de två poster som du skapar. Om du har etablerade egna domäner förutom den första domänen i Office 365 måste du publicera två CNAME-poster för varje ytterligare domän. Om du har två domäner måste du publicera två ytterligare CNAME-poster och så vidare.

Använd följande format för CNAME-posterna.

> [!IMPORTANT]
> Om du är en av våra GCC High-kunder beräknar vi _domainGuid_ annorlunda! I stället för att leta upp MX-posten för din _initialDomain_ för att beräkna _domainGuid_ beräknar vi det direkt från den anpassade domänen. Om du till exempel har en anpassad domän som ”contoso.com” blir din domainGuid ”contoso-com”. Punkter ersätts med ett streck. Oavsett vilken MX-post som initialDomain pekar på kommer du alltid att använda metoden ovan för att beräkna vilken domainGuid som ska användas i dina CNAME-poster.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

Var:

- För Office 365 är väljarna alltid ”selector1” eller ”selector2”.

- _domainGUID_ är samma som _domainGUID_ i den anpassade MX-posten för din domän som visas före mail.protection.outlook.com. Exempel: i följande MX-post för domänen contoso.com blir din _domainGUID_ contoso-com:

    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- _initialDomain_ är den domän som du använde när du registrerade dig för Office 365. De första domänerna avslutas alltid i onmicrosoft.com. Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

Om du till exempel har en första domän med cohovineyardandwinery.onmicrosoft.com, och två egna domäner cohovineyard.com och cohowinery.co, behöver du skapa två CNAME-poster för varje ytterligare domän för att summera fyra CNAME-poster.

```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> Det är viktigt att skapa den andra posten, men bara en av dem kan vara tillgänglig när du skapar den. I själva verket kan den andra väljarens peka på en adress som inte har skapats än. Vi rekommenderar fortfarande att du skapar den andra CNAME-posten eftersom nyckelroteringen blir smidig och du inte behöver göra några manuella steg själv.

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a>Aktivera DKIM-signering för din anpassade domän i Office 365
<a name="EnableDKIMinO365"> </a>

När du har publicerat CNAME-posterna i DNS är du redo att aktivera DKIM-signering via Office 365. Du kan göra det antingen via administrationscentret för Microsoft 365 eller med hjälp av PowerShell.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>Aktivera DKIM-signering för din anpassade domän via administrationscentret

1. [Logga in på Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt konto för arbetet eller skolan.

2. Välj ikonen för startprogrammet i det övre vänstra hörnet, och välj sedan **Admin**.

3. I den nedre vänstra navigeringen expanderar du **Administratör** och väljer **SharePoint**.

4. Gå till **Skydd** \> **DKIM**.

5. Välj domänen som du vill aktivera DKIM för och sedan går du till **Sign messages for this domain with DKIM signatures** (Signera meddelanden för domänen ed DKIM-signaturer) och väljer **Aktivera**. Upprepa det här steget för varje anpassad domän.

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>För att aktivera DKIM-signering för din anpassade domän med PowerShell

1. [Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Kör följande kommando:

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   Här är _domänen_ namnet på den anpassade domän som du vill aktivera DKIM-signering för.

   Till exempel för domänen contoso.com:

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a>Bekräfta att DKIM-signering är rätt konfigurerad för Office 365

Vänta några minuter innan du följer de här anvisningarna för att kontrollera att du har konfigurerat DKIM. Då får DKIM-informationen om domänen tid att spridas i hela nätverket.

- Skicka ett meddelande från ett konto i din Office 365-DKIM-aktiverade domän till ett annat e-postkonto, till exempel outlook.com eller Hotmail.com.

- Använd inte ett aol.com-konto för testningsändamål. AOL kan hoppa över DKIM för att kontrollera om SPF-kontrollen överförs. Det här annullerar testet.

- Öppna meddelandet och titta på rubriken. Information om hur du visar rubriken för meddelandet beror på vilken meddelandeklient du har. Information om hur du visar meddelanderubriker i Outlook finns i [Visa e-postmeddelandehuvud](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).

  Det DKIM-signerade meddelandet innehåller värdnamnet och domänen som du angav när du publicerade CNAME-posterna. Meddelandet liknar nu följande exempel:

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- Håll utkik efter huvudet Authentication-Results. Även om varje mottagande tjänst använder något annat format för att stämpla inkommande e-post ska resultatet innehålla något som liknar **DKIM=pass** eller **DKIM=OK**.

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a>Konfigurera fler än en anpassad domän i Office 365
<a name="DKIMMultiDomain"> </a>

Om du senare bestämmer dig för att lägga till en egen domän och vill aktivera DKIM för den nya domänen måste du utföra stegen i den här artikeln för varje domän. Slutför först alla steg i [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365) (Vad du behöver göra för att konfigurera DKIM i Office 365).

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a>Inaktivera DKIM-signeringsprincipen för en anpassad domän i Office 365
<a name="DisableDKIMSigningPolicy"> </a>

När du inaktiverar signeringsprincipen inaktiveras inte DKIM fullständigt. Efter en tidsperiod används standardprincipen för Office 365 automatiskt för din domän i Office 365. Mer information finns i [Standardbeteende för DKIM och Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Inaktivera DKIM-signeringsprincipen med Windows PowerShell

1. [Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Kör något av följande kommandon för varje domän som du vill inaktivera DKIM-signering för.

    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Till exempel:

    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   Eller

    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    Där _number_ är indexet för principen. Till exempel:

    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a>Standardbeteende för DKIM och Office 365
<a name="DefaultDKIMbehavior"> </a>

Om du inte aktiverar DKIM skapar Office 365 automatiskt en offentlig 1024-bitars DKIM-nyckel för din standarddomän och den tillhörande privata nyckeln som vi lagrar internt i vårt datacenter. Som standard använder Office 365 en standardkonfiguration för signering för domäner som inte har någon princip. Det innebär att om du inte konfigurerar DKIM själv kommer Office 365 att använda sin standardprincip och de nycklar som skapas för att aktivera DKIM för din domän.

Om du inaktiverar DKIM-signering när du har aktiverat det kommer Office 365 att automatiskt använda standardprincipen för Office 365 för din domän.

I följande exempel antar vi att DKIM för fabrikam.com har aktiverats av Office 365, inte av domänens administratör. Det innebär att de nödvändiga CNAME-posterna inte finns i DNS. DKIM-signaturer för e-post från den här domänen ser ut ungefär så här:

```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

I det här exemplet innehåller värddatornamnet och domänen värdena som CNAME pekar på om DKIM-signering för fabrikam.com har aktiverats av domänadministratören. Slutligen kommer alla meddelanden som skickats från Office 365 att DKIM-signeras. Om du aktiverar DKIM själv blir domänen samma som domänen i Från: adress, i det här fallet fabrikam.com. Om du inte gör det justeras det inte. I stället används din organisations första domän. Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän.
<a name="SetUp3rdPartyspoof"> </a>

Vissa leverantör av e-posttjänster, eller leverantörer av programvara som tjänst, kan konfigurera DKIM-nycklar för e-post som kommer från tjänsten. Det kräver samordning mellan dig och tredje part för att du ska kunna skapa de DNS-poster som krävs. Inga organisationer fungerar på exakt samma sätt. I stället beror processen helt på organisationen.

Ett exempelmeddelande som visar ett korrekt konfigurerat DKIM för contoso.com och bulkemailprovider.com kan se ut så här:

```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

I det här exemplet för att uppnå följande resultat:

1. E-postleverantören för massutskick gav Contoso en offentlig DKIM-nyckel.

2. Contoso offentliggjorde nyckeln DKIM till dess DNS-post.

3. När du skickar e-post signerar e-postleverantören för massutskick nyckeln med motsvarande privata nyckel. Det gör att e-postleverantören för massutskicket bifogar DKIM-signaturen i meddelandehuvudet.

4. Mottagande e-postsystem utför en DKIM-kontroll genom att autentisera värdet i DKIM-signaturen d=\<domän\> mot domänen i meddelandet Från: (5322.From) för meddelandet. I det här exemplet överensstämmer värdena:

    sender@**contoso.com**

    d=**contoso.com**

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a>Nästa steg: När du har konfigurerat DKIM för Office 365
<a name="DKIMNextSteps"> </a>

Även om DKIM har utformats för att förhindra förfalskningar fungerar DKIM bättre med SPF och DMARC. När du har konfigurerat DKIM kan du konfigurera SPF om du inte redan har gjort det. En introduktion till SPF finns i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt. För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md). Därefter läser du [Använd DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md). [Meddelandehuvuden för antiskräppost](anti-spam-message-headers.md) innehåller syntaxen och rubrikerna som används i Office 365 för DKIM-kontroller.