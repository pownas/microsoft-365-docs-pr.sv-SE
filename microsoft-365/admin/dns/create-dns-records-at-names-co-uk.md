---
title: Skapa DNS-poster på Names.co.uk för Office 365
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Lär dig att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag – Online och andra tjänster på Names.co.uk för Office 365.
ms.openlocfilehash: d27cd22b0047cf58def01533a486c7641f50148e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42809431"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a>Skapa DNS-poster på Names.co.uk för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Om Names.co.uk är din DNS-värd följer du stegen i den här artikeln för att verifiera din domän och konfigurera DNS-poster för e-post, Skype för företag - Online och så vidare.
    
När du har lagt till dessa poster på Names.co.uk är din domän konfigurerad för att fungera med Office 365-tjänster.
  
Mer information om webbvärdverktyg och DNS för webbplatser med Office 365 finns i [Använda en offentlig webbplats med Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Lägga till en TXT-post för verifiering
<a name="BKMK_verify"> </a>

Innan du använder din domän med Office 365 vill vi vara säkra på att det är du som äger den. Att du kan logga in på kontot hos domänregistratorn och skapa en DNS-post bevisar för Office 365 att du äger domänen.
  
> [!NOTE]
> Den här posten används endast för att verifiera att du äger domänen. Den påverkar ingenting annat. Du kan ta bort den senare om du vill. 
  
1. Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
        
    |**Värdnamn**|**Typ**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Obs!** Det här är ett exempel. Använd det specifika värdet för **Mål eller pekar på-adress** här, från tabellen i Office 365.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verifiera-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Verifiera-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. Vänta några minuter innan du fortsätter, så att den post som du nyss skapade kan uppdateras på Internet.
    
Nu när du har lagt till posten på domänregistratorns webbplats kan du gå tillbaka till Office 365 och begära att Office 365 letar efter posten.
  
När Office 365 hittar rätt TXT-post är din domän verifierad.
  
1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>
    
2. På sidan **Domäner** väljer du den domän som du verifierar. 
    
    
  
3. Välj **Starta inställningar**på sidan **Inställningar** .
    
    
  
4. På sidan **Verifiera domän** väljer du **Verifiera**.
    
    
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Lägga till en MX-post så att e-post för din domän kommer till Office 365
<a name="BKMK_add_MX"> </a>

1. Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. I avsnittet **Mail exchange records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    |**Värdnamn**|**Priority**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |1  <br/> [Mer information om prioritet finns i ](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)Vad är MX-prioritet? <br/> | *\<domännyckel\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> Hämta * \<domännyckeln\> * från ditt Office 365-konto.           [Hur hittar jag det?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Konfigurera-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. Om det finns andra MX-poster i avsnittet **Mail exchange records** tar du bort var och en av dem genom att markera den och sedan trycka på **Delete**-tangenten. 
    
    ![NamesUK-BP-Konfigurera-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Lägg till de sex CNAME-posterna som krävs för Office 365
<a name="BKMK_add_CNAME"> </a>

1. Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in följande värden i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
    
    |**Host Name**|**Type**|**Result**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![NamesUK-BP-Konfigurera-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. Välj **Spara**.
    
    ![NamesUK-BP-Konfigurera-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Du kan inte ha fler än en TXT-post för SPF för en domän. Om din domän har fler än en SPF-post får du e-postfel och problem med leveranser och skräppostklassificering. Om du redan har en SPF-post för domänen ska du inte skapa en ny för Office 365. Lägg istället till de obligatoriska Office 365-värdena i den aktuella posten, så att du har en  *enda*  SPF-post som innehåller båda uppsättningarna med värden.
  
1. Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Välj namnet på den domän som du uppdaterar i kolumnen **Domännamn** på sidan **DNS-zoner på kontot.** 
    
    ![NamesUK-BP-Konfigurera-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. Under **A, CNAME, AAAA, TXT and NS records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Välj värdet för **Type** i listrutan.) 
    
    (Om du behöver lägga till en rad väljer du **LÄGG TILL A/CNAME-POSTER (+)**.)
    
    (Du kan behöva rulla nedåt.)
    
    |**Värdnamn**|**Typ**|**Resultat**|
    |:-----|:-----|:-----|
    |(Lämna det här fältet tomt.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Obs!** Vi rekommenderar att du kopierar och klistrar in den här posten så att alla avstånd förblir korrekta.               |
       
    ![NamesUK-BP-Konfigurera-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Lägga till de två SRV-posterna som krävs för Office 365
<a name="BKMK_add_SRV"> </a>

1. Kom igång genom att gå till domänsidan på Names.co.uk genom att klicka på [den här länken](https://account.names.co.uk/dashboard#/). Du uppmanas att logga in först.
    
    ![NamesUK-BP-Konfigurera-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. På **Dashboard**-sidan hittar du namnet på domänen du uppdaterar. Välj sedan **DNS Settings** i listrutan. 
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Under **Service records** på sidan **Add/Modify DNS Zone** skriver du in eller kopierar och klistrar in värdena från följande tabell i rutorna för den nya posten. 
    
    (Du kan behöva rulla nedåt.)
    
    |**Name**|**Priority**|**Weight**|**Port**|**Result**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![NamesUK-BP-Konfigurera-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. Välj **Spara**.
    
    (Du kan behöva rulla nedåt.)
    
    ![NamesUK-BP-Konfigurera-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  