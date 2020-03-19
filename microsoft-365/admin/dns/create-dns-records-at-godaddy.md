---
title: Skapa DNS-poster på GoDaddy för Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på GoDaddy för Office 365.
ms.custom: okr_smb
ms.openlocfilehash: e037e989a51a95b16077d1edfcdff4b341ee3b80
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42813003"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>Skapa DNS-poster på GoDaddy för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.

Om GoDaddy är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.

När du har lagt till dessa poster på GoDaddy är din domän konfigurerad för att fungera med Office 365-tjänster.

Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.

> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner**väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **TXT (Text)** i listrutan. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

    |**Record type** |**Host**|**TXT Value**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (Text)|@|MS=ms *XXXXXXXX*<br>**Obs:** Detta är ett exempel. Använd ditt specifika **Mål eller pekar på adress**-värde här, från tabellen i Office 365. [Hur hittar jag detta?](../get-help-with-domains/information-for-dns-records.md)|1 timme  <br>(Välj ett värde i listrutan.)|

      ![GoDaddy-BP-Verifiera-1-0](../../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Välj **Spara**.

6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.

Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.

När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>

    
2. På sidan **Domäner** väljer du den domän som du verifierar. 
    
    
  
3. På **sidan Inställningar** väljer du **Starta installationsprogrammet**.



4. Välj **Verifiera**på **sidan Verifiera domän.**



> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner**väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **MX (Mail Exchanger)** i listrutan.

    ![GoDaddy-BP-Konfigurera-2-0](../../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Host (värd)**|**Points to (pekar på)**|**Priority**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX (Mail Exchanger)  <br/> |@  <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> **Obs:** Hämta din * \<domännyckel\> * från ditt Office 365-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |10  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1 timme  <br/> |

6. Välj **Spara**.

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Lägg till CNAME-posterna som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner**väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Välj **CNAME (Alias)** i listrutan.

    ![GoDaddy-BP-Konfigurera-3-0](../../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Skapa den första CNAME-posten.

    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Host (värd)**|**Points to (pekar på)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 timme  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 timme  <br/> |



6. Upprepa dessa steg om du vill lägga till nästa CNAME-post tills du har skapat alla sex CNAME-posterna.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner**väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **TXT (Text)** i listrutan.

    ![GoDaddy-BP-Konfigurera-4-0](../../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. I rutorna för den nya posten skriver du in eller kopierar och klistrar in följande värden.

    (Välj **TTL-värdet** i listrutan.)

    |**Record type**|**Host**|**TXT Value**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Text)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |1 timme  <br/> |

    ![GoDaddy-BP-Konfigurera-4-1](../../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Välj **Spara**.


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan.

1. Kom igång genom att gå till domänsidan på GoDaddy med [den här länken](https://account.godaddy.com/products/?go_redirect=disabled). Du uppmanas att logga in först.

    ![GoDaddy-BP-Konfigurera-1-1](../../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Under **Domäner**väljer du DNS under den domän som du vill redigera.

    ![GoDaddy-BP-Konfigurera-1-2](../../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Välj **Lägg till**.

    ![GoDaddy-BP-Konfigurera-1-4](../../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Välj **SRV (Service)** (SRV (tjänst)) i listrutan.

    ![GoDaddy-BP-Konfigurera-5-0](../../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Skapa den första SRV-posten.

    I rutorna för den nya posten anger du eller kopierar och klistrar in värdena från den första raden i följande tabell.

    (Välj **posttyp** och **TTL-värden** i listrutan.)

    |**Record type**|**Namn**|**Target (mål)**|**Protocol**|**Tjänst**|**Priority (prioritet)**|**Weight**|**Port**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Service)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 timme  <br/> |
    |SRV (Service)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 timme  <br/> |

    ![GoDaddy-BP-Konfigurera-5-1](../../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Upprepa **steg 5** för att skapa den andra SRV-posten.

7. Välj **Spara**.

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).