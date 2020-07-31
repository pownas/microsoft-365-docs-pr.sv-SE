---
title: Microsoft 365-rapporter i administrationscentret – Användaraktivitet för Microsoft Teams – Förhandsversion
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Läs om hur du hämtar användaraktivitetsrapporten för Microsoft Teams och får insikter om teams-aktiviteten i organisationen.
ms.openlocfilehash: 734a4dfd62160c2f4d29b8faffb3268a1962fe4f
ms.sourcegitcommit: a50260b7c5be7374e8e2bea19cc08406ef51ac47
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2020
ms.locfileid: "45167347"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity--preview"></a>Microsoft 365-rapporter i administrationscentret – Användaraktivitet för Microsoft Teams– Förhandsversion

Instrumentpanelen Microsoft 365 **Reports** visar aktivitetsöversikten för produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md). I användaraktivitetsrapporten för Microsoft Teams får du inblick i Microsoft Teams-aktiviteterna i organisationen.
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter.  
 
## <a name="how-to-get-to-the-preview-microsoft-teams-user-activity-report"></a>Så här kommer du till användaraktivitetsrapporten för förhandsversionen av Microsoft Teams

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.
2. Välj **Microsoft Teams**i listrutan Välj **en rapport** .
  
## <a name="interpret-the-preview-microsoft-teams-user-activity-report"></a>Tolka användaraktivitetsrapporten för förhandsversionen av Microsoft Teams

Du kan visa användaraktiviteten i rapporten Förhandsgranska Teams genom att välja fliken **Användaraktivitet.**
  
|||
|:-----|:-----|
|**Metriska**|**Definition**|
|Användarnamn  <br/> |Användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt.   <br/> |
|Kanalmeddelanden   <br/> |Antalet unika meddelanden som användaren har publicerat i en gruppchatt under den angivna tidsperioden.  <br/> |
|Chattmeddelanden   <br/> |Antalet unika meddelanden som användaren har publicerat i en privat chatt under den angivna tidsperioden.  <br/> |
|Totalt antal möten   <br/> |Antalet onlinemöten som användaren deltog i under den angivna tidsperioden.  <br/> |
|01:1 samtal   <br/> | Antalet 1:1-anrop som användaren deltog i under den angivna tidsperioden.  <br/> |
|Sista aktivitetsdatum (UTC)  <br/> |Det sista datum då användaren deltog i en Microsoft Teams-aktivitet.<br/> |
|Möten deltog adhoc   <br/> | Antalet möten som inte har schemalagts i kalendern som användaren deltog i under den angivna tidsperioden.  <br/> |
|Möten organiserade adhoc <br/> |Antalet möten som inte har schemalagts i kalendern som användaren organiserade under den angivna tidsperioden. <br/>|
|Möten ordnade schemalagda  <br/> |Antalet schemalagda möten som en användare har organiserat under den angivna tidsperioden.  <br/> |
|Är licensierad |Väljs om användaren är licensierad att använda Teams.|
|Övrig aktivitet|Användaren anses vara aktiv men har ett nollvärde för chattmeddelanden, 1:1-samtal, kanalmeddelanden, totalt antal möten och möten. Exempel på åtgärder är när Microsoft Teams-klienten aktiveras till förgrunden, åtgärder vidtogs i området för att skriva meddelande, popup-meddelanden dök upp i Microsoft Teams-klienten, banners visades i Microsoft Teams-klienten osv. |
|||