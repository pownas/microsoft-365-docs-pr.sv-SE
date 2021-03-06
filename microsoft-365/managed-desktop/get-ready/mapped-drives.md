---
title: Förbereda mappade enheter för Microsoft Hanterat skrivbord
description: Viktiga steg för att kontrol lera
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104600"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Förbereda mappade enheter för Microsoft Hanterat skrivbord

Många företags miljöer har äldre krav för anslutna enheter så att användare och team kan dela och lagra filer eller för lokala program. Microsoft rekommenderar inte användning av mappade enheter med Microsoft Managed Desktop. Vi rekommenderar att du modernisera fil åtkomst lösningarna så här:
  
- Migrera anslutna enheter som används av enskilda användare till OneDrive för företag. 
- Migrera mappade enheter som används av Teams för att dela filer till SharePoint Online. 
- Modernisera eller Ersätt alla program som använder lokala fil resurser för att ta bort det kravet.
  
Om de här tjänsterna bevaras kommer de att få bästa möjliga användar upplevelse med Microsoft hanterat skriv bord. Microsoft FastTrack-tjänsterna hjälper dig att göra din miljö med Microsofts moln tjänster. Du kan kontrol lera om du är berättigad till FastTrack tjänster för [kvalificerade tjänster och abonnemang](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) och sedan kontakta dem direkt för att förbereda dig för Microsoft Managed Desktop. Om du vill ha information om FastTrack OneDrive för företag eller SharePoint Online-migrering läser du [datamigrering](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Anslutna enheter på Microsoft Managed Desktop
 
Om du inte kan ta bort eller ersätta anslutna enheter för vissa användnings fall ska du skicka en supportbegäran på Microsoft Managed Desktop admin-portalen för att distribueras till Microsoft Managed Desktop-användare.
    
För en sådan begäran måste du uppge följande information i supportbegäran: 

- Alla UNC-sökvägar till fil resurser som måste mappas för Microsoft-hanterade Station ära enheter 
- Användar grupper som kräver åtkomst till dessa fil resurser 
- Eventuell specifik enhets bokstav som måste tilldelas (om det behövs)

Till exempel:

| Enhets beteckning | UNC-sökväg | Användar grupp |
|--------------|----------|------------|
| Kryss  | \\\server\share\Marketing | ContosoMarketing |

Det är helt ditt ansvar att säkerställa att användare och grupper har och upprätthåller rätt behörigheter för åtkomst till fil resurser och att den lokala fil tjänsten är tillgänglig. Dessutom bör du ta bort dina krav för sådana fildelningar så snart som möjligt.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Om du vill att mappade enheter distribueras på Microsoft Managed Desktop
 
Kontrol lera att anslutna enheter inte kan undvikas och att du noggrant har granskat kraven innan du skickar en tjänst förfrågan. Gör sedan följande:

1. Gå till [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och välj "fel sökning + support" och leta efter "tjänst begär Anden" under avsnittet Microsoft Managed Deskop.  
2. Skicka in en supportbegäran med rubriken "anslutna enheter distribution" och ge alla nödvändiga fil uppgifter.  
3. Microsoft-hanterad stationär dator IT-operationer bör använda uppdateringar för support förfrågningar när begäran har slutförts. Först distribueras den här konfigurationen till enheter i test distributions gruppen.  
4. Du måste testa och bekräfta om konfigurationen som distribueras av Microsoft Managed Desktop fungerar som förväntat. Svara med hjälp av fliken diskussion i informationen om samma supportbegäran för att meddela Microsoft Managed Desktop IT-operationer när du har gjort testen.  
5. Gruppen Microsoft Managed Desktop IT Operations distribuerar sedan konfigurationen till de andra distributions grupperna. 
