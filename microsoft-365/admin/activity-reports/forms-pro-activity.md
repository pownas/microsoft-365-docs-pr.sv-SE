---
title: Microsoft 365-rapporter i administrations centret – Dynamics 365 kund röst aktivitet
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Lär dig hur du skaffar en Microsoft Dynamics 365 Customer Voice Activity-rapport med hjälp av instrument panelen för Microsoft 365-rapporter i Microsoft 365 Admin Center.
ms.openlocfilehash: de03067197c80634f02318b35a79eb84e33c4b86
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988558"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-rapporter i administrations centret – Dynamics 365 kund röst aktivitet

Instrument panelen för Microsoft 365- **rapporter** visar en översikt över produkterna i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt. Ta en titt på [översiktsavsnittet för Rapporter](activity-reports.md).
  
Du kan till exempel förstå aktiviteten hos alla användare som har licens att använda Microsoft Dynamics 365 Customer Voice genom att titta på deras interaktioner med Dynamics 365 Customer Voice. Det hjälper dig också att förstå samarbetets möjligheter genom att titta på antalet Pro-undersökningar som skapats och Pro-undersökningar som användarna svarade på. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapport läsare i Microsoft 365 eller en Exchange-, SharePoint-, teams-tjänst, grupp kommunikation eller Skype för företag-administratör för att se rapporter. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Så här kommer du till rapporten formulär Pro-aktivitet

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. I list rutan **Välj en rapport** väljer du **Dynamics 365 kund röst** \> **aktivitet**.

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Tolka rapporten Dynamics 365 Customer Voice Activity

Du kan få en vy i användarens Dynamics 365 kund röst aktivitet genom att titta på diagrammen **aktivitet** och **användare** . 

![Formulär aktivitets rapport](../../media/formsproactivity.png)

|Objekt|Beskrivning|
|:-----|:-----|
|1.  <br/> |I rapporten **Dynamics 365 Customer Voice** Activity kan du se trender under de senaste 7, 30, 90 eller 180 dagar. Om du väljer en viss dag i rapporten visar tabellen (7) data för upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades).   <br/> |
|2.  <br/> |Informationen i varje rapport är normalt sett den senaste 48 timmar.  <br/> |
|3.  <br/> |Med vyn **användare** kan du förstå trenden i antalet aktiva Dynamics 365 Customer Voice-användare. En användare anses vara aktiv om de har kört en aktivitet i en Pro-undersökning (skapa, redigera, vy osv.) under den angivna tids perioden.  <br/> |
|4.  <br/> |Med vyn **aktivitet** kan du förstå trenden för antalet aktiva användare. En användare anses vara aktiv om han eller hon har genomfört en filaktivitet (spara, synkronisera, ändra eller dela) eller besökt en sida inom den angivna tidsperioden.<br/> Obs! en aktivitet kan förekomma flera gånger i en enkät, men räknas bara som en aktiv undersökning. Du kan till exempel skapa en Pro-undersökning och fortsätta att redigera samma undersökning flera gånger under en viss tids period, men räknas bara som en enda undersökning. <br>|
|5.<br/>|I diagrammet **användare** är Y-axeln antalet unika användare. X-axeln är det datum då de unika användarna är aktiva på. Följande förklaringar är:<br/><br/>**Designers** innebär att användaren har skapat eller redigerat en Dynamics 365 Customer Voice-undersökning.<br><br>I diagrammet **aktivitet** är Y-axeln antalet Dynamics 365 kund röst svar per undersökning. X-axeln är det datum då undersökningen eller svars aktiviteten ägde rum. Följande förklaringar är:<br/><br/>**Undersökningar som skapas** är antalet unika Dynamics 365 kund röst kontroller som användarna har skapat<br>**Svar** är antalet anonyma eller icke-anonyma svar som användarna som tog emot undersökningen har skickat in. |
|18.6.<br/>|Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I diagrammet användare väljer du till exempel designer, svarare eller totalt antal användare om du bara vill se informationen som hör till var och en. Om du ändrar den här markeringen ändras inte informationen i rutnäts tabellen nedanför den.|
|borttagning.<br/>|Tabellen visar en uppdelning av aktiviteterna på per-användare-nivå. Följande förklaringar är:<br/><br/>**Username** är e-postadressen för den användare som utförde aktiviteten på Microsoft Forms.<br/>**Datum för senaste aktivitet (UTC)** är det senaste datum då en formulär aktivitet utfördes av användaren för det valda datum intervallet. Om du vill se aktivitet som inträffat på ett visst datum markerar du datumet direkt i diagrammet.<br/>Då filtreras tabellen för att endast Visa fil aktiviteter för användare som utförde aktiviteten på den aktuella dagen.<br/><br/>**Antal undersökningar som skapas** är antalet undersökningar som användaren har skapat.<br/> **Antal undersöknings svar** är antalet svar från svarare som undersökningen distribuerades till.|
|8.2.<br/>|Välj ikonen **Hantera kolumner** för att lägga till eller ta bort kolumner i rapporten.|
|9.<br/>|Du kan också exportera rapport data till en Excel. csv-fil genom att välja **Exportera** -länken. Detta exporterar data för alla användare och gör att du kan utföra enkel sammanställning, sortering och filtrering för ytterligare analyser. Om du har färre än 100 användare kan du sortera och filtrera i tabellen i rapporten. Om du har fler än 100 användare måste du exportera data för att kunna filtrera och sortera.|