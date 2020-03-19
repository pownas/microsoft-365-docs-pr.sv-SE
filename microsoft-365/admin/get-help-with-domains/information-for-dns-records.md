---
title: Samla den information du behöver för att skapa DNS-poster i Office 365
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
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Lär dig att hitta de värden/den information du behöver för att skapa DNS-poster för Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: 7b995aedc21305367e4a6621781e138d0d60efd1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808198"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a>Samla den information du behöver för att skapa DNS-poster i Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Steg 1: Hitta TXT-postvärdet och verifiera

1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret</a> för Microsoft 365.
    
    Om du använder Office 365 Tyskland går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domänsidan.</a> 
    
    Om du använder Office 365 som drivs av 21Vianet går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domänsidan.</a>
    
2. Välj domänen på sidan **Domäner** och välj sedan **Starta installationsprogrammet**. Du går tillbaka till domäninstallationsguiden för att se det specifika värde som du måste lägga till.
    
3. På **sidan Verifiera domän** väljer du **Lägg till en TXT-post i stället**och väljer sedan **Nästa**.
    
4. Kopiera **TXT-värdet** som visas. Det ser ut så här: **MS = msXXXXXXXX**. 
    
5. Gå till [Skapa DNS-poster hos valfri DNS-värd](create-dns-records-at-any-dns-hosting-provider.md)och välj din DNS-värd från listan över registratorer för att se steg-för-steg-instruktioner.
    
6. Följ stegen för att skapa TXT-posten (eller MX-posten) hos din DNS-värd och verifiera sedan domänen i Office 365.

7. Ta bort TXT-posten (eller MX-posten) från DNS-värden när domänen har verifierats i Office 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Steg 2: Hitta MX-postvärdet för e-post med mera

1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret</a> för Microsoft 365.
    
    Om du använder Office 365 Tyskland går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domänsidan.</a> 
    
    Om du använder Office 365 som drivs av 21Vianet går du till den här <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domänsidan.</a>
    
2. Välj en domän på sidan **Domäner**. 
    
3. Under **Obligatoriska DNS-inställningar** visas DNS-posterna som ska läggas till.
    
    Du behöver ha den här informationen tillgänglig när du gör ändringar hos din DNS-värd, så att du kan kopiera och klistra in värdena.
    
    Grupperna av DNS-poster som visas på sidan är beroende av dina val som visas under **Domänsyfte**.
    
4. Gå till [Skapa DNS-poster hos valfri DNS-värd och](create-dns-records-at-any-dns-hosting-provider.md)välj sedan din DNS-värd från listan över registratorer för att se steg-för-steg-instruktioner för att lägga till poster på DNS-värdens webbplats.
    
5. Följ stegen för att skapa posterna hos din DNS-värd.