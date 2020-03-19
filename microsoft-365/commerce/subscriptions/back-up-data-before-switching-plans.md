---
title: Säkerhetskopiera data innan du byter Office 365 för affärsabonnemang
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Säkerhetskopiering av Outlook-, OneDrive-, Yammer- och SharePoint-innehåll innan du byter Office 365-prenumerationer eller om en användare lämnar organisationen.
ms.openlocfilehash: 16fb6972869c3caf010c25cbe043dbf79f458531
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808172"
---
# <a name="back-up-data-before-switching-office-365-for-business-plans"></a>Säkerhetskopiera data innan du byter Office 365 för affärsabonnemang

Om en användare byter till en annan prenumeration som har färre datarelaterade tjänster eller lämnar organisationen går det att ladda ned en kopia av användardata som lagras i Office 365 innan de byter till den nya prenumerationen.
  
## <a name="save-a-copy-of-outlook-information"></a>Spara en kopia av Outlook-information

Om användarna har Outlook kan de [exportera eller säkerhetskopiera e-post, kontakter och kalender till en Pst-fil](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) i Outlook innan planen ändras. 
  
När övergången till det nya abonnemanget är klar kan användarna [importera e-post, kontakter och kalender från en Pst-fil i Outlook .](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Spara filer som lagras i OneDrive för företag

Innan de byter till en annan prenumeration kan användarna [hämta filer och mappar från OneDrive eller SharePoint](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05) till en annan plats, till exempel en mapp på datorns hårddisk eller en filresurs i organisationens nätverk. 
  
## <a name="save-yammer-information"></a>Spara Yammer-information

Administratörer kan exportera alla meddelanden, anteckningar, filer, ämnen, användare och grupper till en .zip-fil. Mer information finns i [Exportera data från Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Utvecklare kan använda [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) för att göra detta också. 
  
## <a name="how-to-save-sharepoint-information"></a>Spara SharePoint-information

Om en användare byter från en prenumeration som har SharePoint Online till en som inte har den visas inte längre **SharePoint-panelen** på sin Office 365-meny. 
  
Så länge den nya prenumerationen är inom samma organisation som de har bytt från kan användaren fortfarande se SharePoint-gruppwebbplatsen. De kan visa och uppdatera anteckningsböcker, dokument, uppgifter och kalendrar med hjälp av direktlänkarna på gruppwebbplatsen.
  
> [!TIP]
> Vi rekommenderar att sådana användare går till gruppwebbplatsen innan prenumerationen byts ut och sparar webbadressen som en favorit eller ett bokmärke i webbläsaren. 
  
Som standard har webbadressen till gruppwebbplatser följande format:
  
```
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

där _ \<orgDomain\> _ är organisationens WEBBADRESS. 
  
Om domänen för organisationen till exempel är contoso.onmicrosoft.com så skulle direktadressen till gruppwebbplatsen vara https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Användare kan förstås också ladda ned SharePoint Online-dokument från SharePoint-gruppwebbplatsen till en lokal dator eller annan plats när som helst.