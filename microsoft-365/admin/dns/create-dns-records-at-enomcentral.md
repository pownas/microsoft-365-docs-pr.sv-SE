---
title: Skapa DNS-poster på eNomCentral för Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på eNomCentral för Microsoft.
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658117"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Skapa DNS-poster på eNomCentral för Microsoft

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.

Om eNomCentral är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.

När du har lagt till dessa poster på eNomCentral är din domän konfigurerad för att fungera med Microsoft-tjänster.

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Microsoft, vill vi vara säkra på att det är du som äger den. Att du kan logga in på ditt konto hos domänregistratorn och skapa DNS-posten bevisar för Microsoft att du äger domänen.

> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill.

Följ stegen nedan eller [titta på videon (börja vid 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Under **My Domains** väljer du namnet på den domän som du vill redigera.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. I listrutan **Manage Domain** väljer du **Host Records**.

   ![eNom-BP-verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

   Välj värdet **Record Type** i list rutan.

   |Värdnamn|Record Type|Adress|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. Välj **Spara**.

   ![eNom-BP-verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.

Nu när du har lagt till posten på domänregistratorns webbplats går du tillbaka till Microsoft 365 och begär att Microsoft 365 letar efter posten.

När Microsoft hittar rätt TXT-post är din domän verifierad.

1. I Microsoft-administrationscentret går du till **Inställningar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domäner</a>.

2. På sidan **Domains** väljer du den domän du verifierar.

3. På sidan **Setup** väljer du **Start setup**.

4. På sidan **Verify domain** väljer du **Verify**.

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.
<a name="BKMK_add_MX"> </a>

Följ stegen nedan eller [titta på videon (börja vid 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Under **My Domains** väljer du namnet på den domän som du vill redigera.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. I listrutan **Manage Domain** väljer du **Email Settings**.

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. I listrutan **Service Selection** väljer du **User (MX)**.

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

   |Värdnamn|Adress|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  . mail.protection.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)** <br/> **Obs!** Hämta ditt  *\<domain-key\>*  från ditt Microsoft-konto. [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)|10.3  <br/> Mer information om prioritet finns i [Vad är MX-prioritet?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. Välj **Spara**.

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. Om det finns andra befintliga MX-poster väljer du dem genom att markera kryssrutorna för posterna.

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. Välj **ta bort markerad**.

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Lägga till CNAME-posterna som krävs för Microsoft
<a name="BKMK_add_CNAME"> </a>

Följ stegen nedan eller [titta på videon (börja vid 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Under **My Domains** väljer du namnet på den domän som du vill redigera.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. I listrutan **Manage Domain** väljer du **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Välj **ny rad**.

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. I rutorna för de sex nya posterna skriver du in, eller kopierar och klistrar in, följande värden.

   Välj värdet **Record Type** i list rutan.

   |Värdnamn|Record Type|Adress|
   |---|---|---|
   |autodiscover|CNAME (Alias)|autodiscover.outlook.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|
   |sip|CNAME (Alias)|sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|
   |lyncdiscover|CNAME (Alias)|webdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|
   |enterpriseregistration|CNAME (Alias)|enterpriseregistration.windows.net.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|
   |enterpriseenrollment|CNAME (Alias)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. Välj **Spara**.

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft. I stället kan du lägga till de Microsoft-värden som krävs i den aktuella posten så att du har en  *enda*  SPF-post som innehåller båda uppsättningar med värden.

Följ stegen nedan eller [titta på videon (börja vid 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Under **My Domains** väljer du namnet på den domän som du vill redigera.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. I listrutan **Manage Domain** väljer du **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. I rutorna för den nya posten skriver du in, eller kopierar och klistrar in, värdena från följande tabell.

   Välj värdet **Record Type** i list rutan.

   |Värdnamn|Record Type|Adress|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.    |

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. Välj **Spara**.

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Lägga till de två SRV-posterna som krävs för Microsoft
<a name="BKMK_add_SRV"> </a>

Följ stegen nedan eller [titta på videon (börja vid 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Kom igång genom att gå till domänsidan på eNom Central med [den här länken](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Du uppmanas att logga in först.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Under **My Domains** väljer du namnet på den domän som du vill redigera.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. I listrutan **Manage Domain** väljer du **Host Records**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Till höger om **ny rad** väljer du **Add SRV or SPF record**.

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. I rutorna för de två nya posterna skriver du, eller kopierar och klistrar in, värdena från följande tabell.

   |Tjänst|Protokoll|Ordningen|Väga|Port|Mål (värdnamn)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|9.1|443|sipdir.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|
   |_sipfederationtls|_tcp|100|9.1|5061|sipfed.online.lync.com.  <br/> **Värdet MÅSTE sluta med en punkt (.)**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. Välj **Spara**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md).
