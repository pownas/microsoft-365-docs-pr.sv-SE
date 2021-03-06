---
title: Skapa DNS-poster när din domän hanteras av Google (eNom)
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
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Lär dig hur du kommer åt eNom och skapar DNS via sidan Google domains.
ms.openlocfilehash: 3294be667653c568fbbd1a911bcfab9b6ea7788b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656861"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Skapa DNS-poster när din domän hanteras av Google (eNom)

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter. 
  
För att migrera dina e-postkonton till Microsoft måste du skapa en DNS-post hos din domän registrator.
  
Om du har köpt din domän via Google när du registrerade dina **Google Apps för arbets** konton hanteras dina DNS-poster av Google men vara registrerad hos eNom. 
  
Du kan komma åt eNom och skapa DNS via sidan Google **Domains** . Följ bara anvisningarna i den här artikeln. 
  
## <a name="create-the-dns-record"></a>Skapa DNS-posten

1. I [Google Admin Console](https://www.google.com/work/apps/business)väljer du **Logga** in.
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Ange ditt domän namn och välj sedan **Sök**.
    
    ![Google Apps - Konfigurera-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. Välj **fler kontroller** längst ned på sidan.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Välj **Domäner**.
    
    ![Google Apps - Konfigurera-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. På sidan **domäner** väljer du **Lägg till/ta bort domäner**.
    
    ![Google Apps - Konfigurera-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. Välj **Advanced DNS Settings** på sidan **Domains** .
    
    > [!NOTE]
    > Om du inte köpte ett domännamn via Google när du registrerade ditt **Google Apps for Work** -konto visas inte **Advanced DNS settings** på sidan **Domains**. Då måste du i stället gå direkt till domänvärdens webbplats för att komma åt DNS-inställningarna och följa de här anvisningarna. Se [komma åt dina domän inställningar för G Suite](https://support.google.com/a/answer/54693?hl=en) för mer information. 
  
    ![Google-Apps – eNom-Configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. På sidan **Advanced DNS Settings** väljer **du logga in på DNS Console**. Skriv ned **inloggningsnamnet** och **lösenord** sinformationen. Du behöver det i nästa steg. 
    
    ![Google-Apps – eNom-Configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Logga in på Google **Domain Manager** med **inloggningsnamnet** och **lösenordet** fån sidan **Advanced DNS settings**. 
    
    ![Google-Apps – eNom-Configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. På sidan **_domain_name_*_, i avsnittet _* Host Records** väljer du **Edit**.
    
    ![Google-Apps – eNom-Configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. Välj **Add New** i avsnittet **Host Records** .
    
    ![Google-Apps – eNom-Configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. I den nya postens rutor skriver du in, eller kopierar och klistrar in, värdena från följande tabell.
    
    |**HOST (värd)**|**TXT VALUE**|**POSTTYP**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > Det här är ett exempel. Använd ditt specifika **Mål eller pekar på adress** värde här, från tabellen. 
  
    [Hur hittar jag det här?](../get-help-with-domains/information-for-dns-records.md)
  
12. Välj **Spara**.
    
    ![Google-Apps – eNom-Configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Välj **Spara ändringar**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Det brukar ta ungefär 15 minuter för DNS-ändringarna att gå igenom. Ibland kan det dock ta längre tid att uppdatera DNS-systemet på Internet för en ändring som du har gjort. Om du stöter på problem med e-postflödet eller får andra problem när du har lagt till DNS-posterna, går du till [Felsöka problem när du har ändrat domännamn eller DNS-poster](../get-help-with-domains/find-and-fix-issues.md). 
  
