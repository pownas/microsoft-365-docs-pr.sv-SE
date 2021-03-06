---
title: Microsoft 365 Rapporter i administrationscentret - Aktivitetsrapport för Yammer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.assetid: c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a
description: Hämta Yammer Activity-rapporten och veta mer om hur många användare som använder Yammer för att publicera, gilla eller läsa ett meddelande.
ms.openlocfilehash: 2bf02c0599f999b0eebb52d119096567bb09508b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387471"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Microsoft 365 Rapporter i administrationscentret - Aktivitetsrapport för Yammer

Som Microsoft 365-administratör visar instrumentpanelen **Rapporter** data om användningen av produkterna inom organisationen. Kolla in [aktivitetsrapporter i administrationscentret](activity-reports.md). Med **Yammer-aktivitetsrapporten** får du förståelse för användningen av Yammer i organisationen genom att titta på antalet unika användare som använder Yammer för att publicera, gilla eller läsa ett meddelande och graden av aktivitet som skapas i organisationen. 
  
> [!NOTE]
> Du måste vara global administratör, global läsare eller rapportläsare i Microsoft 365 eller exchange-, SharePoint-, Teams-tjänst, Teams Communications eller Skype för företag-administratör för att kunna se rapporter. 
 
## <a name="how-to-get-to-the-yammer-activity-report"></a>Komma åt Yammer-aktivitetsrapporten

1. I administrationscentret går du till sidan **Rapporter** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Användning</a>.

    
2. Välj **Yammer-aktivitet** i listrutan **Välj en rapport** \> **Activity**.
  
## <a name="interpret-the-yammer-activity-report"></a>Tolka Yammer-aktivitetsrapporten

Du kan få inblick i användarnas Yammer-aktivitet genom att titta på diagrammen Aktivitet och Användare.
  
![Yammer-aktivitetsrapport](../../media/92e8b2c6-166a-4154-9824-3fb6bbedf0db.JPG)
  
Aktivitetsrapporten innehåller följande information.
  
- Använd dagflikarna för att visa **Yammer-aktivitetstrenderna** under de senaste 7, 30, 90 eller 180 dagarna. Om du väljer en viss dag i rapporten visas data i upp till 28 dagar från det aktuella datumet (inte det datum då rapporten genererades). 
    
- Varje rapport har ett datum för när rapporten skapades. Rapporterna visar normalt 24 till 48 timmars fördröjning från aktivitetstiden.
    
- Du kan visa diagrammet **Aktivitet** för att bättre förstå trenden med hur mycket Yammer-aktivitet som pågår i organisationen. Du förstår fördelningen av meddelanden som publiceras, läses eller gillas. 
    
    ![Aktivitetsvy i yammeraktivitetsrapporten](../../media/76983516-2c5f-43a1-a5e3-c414e9f17638.JPG)
  
  - I diagrammet **Aktivitet** visar Y-axeln antalet aktiviteter av publicerade, lästa eller gillade meddelanden. 
    
- Du kan visa diagrammet **Användare** för att bättre förstå trenden med mängden unika användare som skapar Yammer-aktiviteter. Du kan titta på trenden av användare som publicerar, läser eller gillar Yammer-meddelanden. 
    
    ![Användarvyn i yammeraktivitetsrapporten](../../media/b1098162-7b79-430f-bfe4-9d3957d56885.JPG)
  
  - I diagrammet **Användare** visar Y-axeln användare som publicerat, läst eller gillat Yammer-meddelanden. 
    
  - X-axeln i båda diagrammen är det valda datumintervallet för den här specifika rapporten.
    
- Du kan filtrera serien som visas i diagrammet genom att markera ett objekt i förklaringen. I **aktivitetsdiagrammet** väljer du till exempel **Bokförd,** **Läst**eller **Om du** bara vill se den information som är relaterad till var och en. 
    
    ![Inlagda, lästa och gillade alternativ](../../media/8b832afc-415c-409b-816f-cb02b7a71e69.png)
  
    När du ändrar det här valet ändras inte informationen i rutnätstabellen.
    
- Tabellen under diagrammet visar en uppdelning av Yammer-aktiviteter per användare.
    
    Du kan använda menyn till att filtrera och sortera data.
    
    ![Menyalternativ för Yammer-rapporter](../../media/9d32240c-f1ff-400b-9c4e-a21b48651530.JPG)
  
    Du kan också lägga till och ta bort kolumner. De tillgängliga kolumnerna är:
    
  - **Användarnamn** är användarens e-postadress. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. 
    
    Det här rutnätet visar användare som har loggat in på Yammer med Microsoft 365-kontot eller som loggat in på nätverket med enkel inloggning.
    
  - **Visningsnamn** är användarens fullständiga namn. Du kan visa den faktiska e-postadressen eller göra fältet anonymt. 
    
  - **Användartillstånd** är ett av tre värden: Aktiverad, Borttagen eller Inaktiverad. 
    
    De här rapporterna visar data för aktiva, inaktiverade och borttagna användare. De avspeglar inte väntande användare eftersom väntande användare inte kan publicera, läsa eller gilla ett meddelande.
    
  - **Datum för statusändring (UTC)** är datumet då användarens status ändrades i Yammer. 
    
  - **Datum för senaste aktivitet (UTC)** anger det senaste datumet då användaren publicerade, läste eller gillade ett meddelande. 
    
  - **Publicerat** är antalet meddelanden som användaren publicerat under den angivna tidsperioden. 
    
  - **Läst** är antalet konversationer som användaren läst under den angivna tidsperioden. 
    
  - **Gillat** är antalet meddelanden som användaren gillat under den angivna tidsperioden. 
    
  - **Produkt som tilldelats** är de produkter som har tilldelats den här användaren. 
    
    Om organisationens principer förhindrar dig att visa rapporter där användarinformationen är identifierbar kan du ändra sekretessinställningen för alla de här rapporterna. Kolla in avsnittet **Hur döljer jag information på användarnivå?** [Activity reports in the Microsoft 365 admin center](activity-reports.md)
    
- Du kan också exportera rapportdata till en CSV-fil i Excel genom att välja länken **Exportera.** Då exporteras data för alla användare och du kan göra enkel sortering och filtrering för vidare analys. Om du har mindre än 2 000 användare kan du sortera och filtrera i tabellen i själva rapporten. Om du har fler än 2 000 användare måste du exportera data för att kunna filtrera och sortera. 
    
## <a name="what-data-is-in-these-reports"></a>Vilka data ingår i de här rapporterna?

- **Alla klienter** De här rapporterna samlar data för alla klienter, t.ex. användning av Yammer i en webbläsare eller i en iOS- eller Android-app. 
    
- **Inga externa nätverksdata** Externa nätverksdata tas inte med i rapporterna. 
    
- **Aktiverade nätverk** Dessa rapporter visar data för Yammer-nätverket som ingår i din Microsoft 365-prenumeration. Diagrammet sammanställer användningen av alla användare som loggat in i Yammer-nätverket, oavsett om de använde Microsoft 365 eller Yammer för att logga in. 
    

