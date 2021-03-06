---
title: Threat Explorer och real tids identifiering
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig hur du använder Utforskaren och identifiering av real tid i säkerhets & kompatibilitetstillstånd för att undersöka och reagera på hot effektivt och effektivt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4328bfc52497f911c57256f8366b3742523b17b0
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615570"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer och real tids identifiering

Om din organisation har [Microsoft Defender för Office 365](office-365-atp.md), och du har [nödvändig behörighet](#required-licenses-and-permissions), har du antingen **Explorer** -eller **real tids identifiering** (tidigare *real tids rapporter* – [se vad som är nytt](#new-features-in-threat-explorer-and-real-time-detections)!). Gå till **Threat Management** i säkerhets & efterlevnad och välj sedan **Utforskaren** _eller_ **identifiering av real tid**.

|Med Microsoft Defender för Office 365 abonnemang 2 ser du:|Med Microsoft Defender för Office 365 abonnemang 1 ser du:|
|---|---|
|![Threat Explorer](../../media/threatmgmt-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

Med Explorer (eller real tids identifieringar) har du en kraftfull rapport som gör det möjligt för säkerhets åtgärds gruppen att undersöka och reagera på hot effektivt och effektivt. Rapporten ser ut ungefär så här:

![Gå till Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Med den här rapporten kan du:

- [Se malware identifieras av Microsoft 365-säkerhetsfunktioner](#see-malware-detected-in-email-by-technology)
- [Visa data om nät fiske adresser och klicka på Verdict](#view-data-about-phishing-urls-and-click-verdict)
- [Starta en automatiserad undersökning och svars process från en vy i Utforskaren](#start-automated-investigation-and-response) (endast för Office 365 abonnemang 2)
- ... [Undersök skadlig e-post och mycket mer](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Upplev förbättringar av Threat Explorer och identifiering i real tid

### <a name="tags-in-threat-explorer"></a>Taggar i Threat Explorer

> [!NOTE]
> Funktionen användar koder är i förhands granskning, inte tillgänglig för alla och kan komma att ändras. Information om versions schema finns i Microsoft 365-översikten.

User-taggar är identifierare för specifika grupper med användare i Microsoft Defender för Office 365. Mer information finns i taggar, licensiering och konfigurering [av taggar.](user-tags.md)

I Threat Explorer kan du se information kring användar koder i följande versioner:

#### <a name="email-grid-view"></a>Vyn e-post

Kolumnerna som visas i e-postrutnätet innehåller alla Taggar som har kopplats till avsändaren eller mottagarna. Som standard visas systemtaggar som prioritets konton först.

> [!div class="mx-imgBorder"]
> ![Filtrera märkord i vyn e-post](../../media/tags-grid.png)

#### <a name="filtering"></a>Paketfilter

Nu har vi taggar som ett filter så att du bara kan upptäcka bara över prioriterade konton eller specifika användar märknings scenarier (och till och med exkludera resultat med vissa taggar som en del av den här versionen). Genom att kombinera dessa med de andra filter som vi tillhandahåller, kan du begränsa omfattningen av undersökningen

[![Filtrera märkord](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Filtrera inte märkord](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Utfällbar e-postinformation
Om du vill visa de enskilda taggarna för avsändare och mottagare klickar du på ämnet. Meddelande detaljerna öppnas. På fliken Sammanfattning visas fälten avsändare och mottagare separat, om de finns för ett e-postmeddelande.
Information om enskilda taggar för avsändare och mottagare kan även utökas till exporterad CSV, där du kan se dessa uppgifter i två separata kolumner.

> [!div class="mx-imgBorder"]
> ![E-postinformation](../../media/tags-flyout.png)

Information om taggar visas också i URL: er. Om du vill gå till URL-adressen klickar du på Phish eller alla e-postvyer och sedan till URL: er eller URL-Klicka på fliken. om du klickar på en enskild URL-utfällare visas mer information om hur du klickar på URL-adressen och om den är kopplad till det klickade.

> [!div class="mx-imgBorder"]
> ![URL-taggar](../../media/tags-urls.png)

## <a name="improvements-to-threat-hunting-experience-upcoming"></a>Förbättringar av hot mot hotet (kommande)

### <a name="updated-threat-information-for-emails"></a>Uppdaterad Hot information för e-post

Vi har fokuserat på förbättringar av plattform och data kvalitet för att öka dataens exakthet och konsekvens för e-post. De här uppdateringarna inkluderar konsolidering av information om för leverans och efter leverans (exempel åtgärd som utförs på ett e-postmeddelande som en del av ZAP-process) till en enda post tillsammans med Richness som skräp post Verdict, hot på enhets nivå (till exempel, vilken URL-adress som är skadlig) och de senaste leverans platserna.

Efter de här uppdateringarna visas en enda post för varje meddelande, oavsett vilka händelser för inlägg som har utförts. Åtgärder kan inkludera ZAP, manuell reparation (vilket betyder administratörs åtgärd), dynamisk leverans o.s.v.

Förutom att Visa skadlig kod och Phish hot kan du nu se skräp post Verdict associerad med ett e-postmeddelande. I e-postmeddelandet kan du se alla hot som är kopplade till e-postmeddelandet tillsammans med motsvarande identifierings teknik. Alla e-postmeddelanden kan ha 0, 1 eller flera hot. De aktuella hoten visas i avsnittet information i den utfällbara e-postadressen. För att få flera hot (t. ex. ett e-postmeddelande med både skadlig kod och Phish) skulle detta ge den Threat-Detection mappningen, vilket innebär vilken identifierings teknik som ledde till identifieringen av hotet.

Uppsättningen av identifierings teknologier har uppdaterats till att omfatta nya identifierings metoder, samt funktioner för skräp identifiering och i alla olika e-postvyer (skadlig program vara, Phish, all e-post).

> [!NOTE]
> Verdict-analys kanske inte nödvändigt vis är knuten till enheter. Som ett exempel kan ett e-postmeddelande klassificeras som Phish eller spam, men det finns inga URL-adresser som har Phish/spam Verdict. Detta beror på att våra filter också utvärdera innehåll och annan information för ett e-postmeddelande innan de tilldelas en Verdict.

#### <a name="threats-in-urls"></a>Hot i URL: er

Med utfällbar e-post-fliken > information kan du nu se det speciella hotet för en URL (hotet för en URL kan vara skadlig, Phish, spam eller ingen alls)

> [!div class="mx-imgBorder"]
> ![URL-hot](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Uppdaterad tidslinjevy (kommande)

> [!div class="mx-imgBorder"]
> ![Uppdaterad vyn tids linje](../../media/Email_Timeline.png)

Förutom att identifiera alla leverans-och efter leverans händelser ger vyn tids linje också information om det hot som identifieras vid den tidpunkten för en delmängd av dessa händelser. Här får du mer information om ytterligare åtgärder (till exempel ZAP, manuell reparation) tillsammans med resultatet av den åtgärden. Vyn tids linje innehåller information om den ursprungliga leveransen och därefter eventuella efter leverans händelser utförda på ett e-postmeddelande.

- Källa: det kan vara administratören/systemet/användaren baserat på vad som var händelsen.
- Händelse: Detta inkluderar händelser på den översta nivån som ursprunglig leverans, manuell justering, ZAP, inlämning och dynamisk leverans.
- Åtgärd: det här gäller för den åtgärd som gjorts antingen som en del av en ZAP-eller administratörs åtgärd (t. ex. mjuk borttagning).
- Hot: omfattar hoten (skadlig program vara, Phish, spam) som identifieras vid den tidpunkten.
- Resultat/Detaljer: Här finns mer information om resultatet av åtgärden, om det utfördes som en del av ZAP/administratörs åtgärd.

### <a name="original-and-latest-delivery-location"></a>Ursprunglig och senaste leverans plats

I dag skickar vi Surface leverans plats i e-postrutnät och utfällbar e-post. Framåt, fältet leverans plats ändras till ursprunglig leverans plats. Dessutom introducerar vi också ett annat fält som heter senaste leverans plats.

Den ursprungliga leverans platsen skulle ge mer information om var e-postmeddelandet levererades. Den senaste leverans platsen innehåller plats där ett e-postmeddelande kan ha landats efter att system åtgärder som ZAP eller administratörs åtgärder som **Flytta till borttagna objekt**. Den senaste leverans platsen är avsedd att informera administratörer om meddelandets senast kända plats efter leverans och alla system-och administratörs åtgärder. Det finns inga åtgärder för slutanvändare på e-postmeddelandet. Till exempel: om en användare tar bort ett meddelande eller flyttar meddelandet till Arkiv/PST uppdateras inte meddelandets leverans plats. Om en system åtgärd har uppdaterat platsen (till exempel en ZAP som resulterade i ett e-postmeddelande som flyttas till karantänen) ser du den senaste leverans platsen som karantän.

> [!div class="mx-imgBorder"]
> ![Uppdaterade leverans platser](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Det finns några fall där leverans plats och leverans åtgärd kan Visa "okänt" som värde:
>
> - Leverans platsen kan visas som levererad och leverans platsen som okänd. Det här inträffar när meddelandet levererades, men en regel för Inkorgen flyttade meddelandet till en standardmapp (utkast, arkiv osv.) i stället för Inkorgen eller mappen skräp post.
>
> - Den senaste leverans platsen kan vara okänd om en administratör/system åtgärd (till exempel, ZAP, administratörs åtgärd) har prövats men meddelandet inte hittas. Vanligt vis utförs åtgärden efter att användaren har flyttat eller tagit bort meddelandet. I sådana fall ska du kontrol lera kolumnen resultat/information i vyn tids linje. Leta efter meddelandet: meddelandet har flyttats eller tagits bort av användaren.

> [!div class="mx-imgBorder"]
> ![Leverans ställen för tids linje](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Ytterligare åtgärder

Ytterligare åtgärder består av de åtgärder som har tillämpats anslå leveransen av e-postmeddelandet, och kan innehålla ZAP, manuell reparation (åtgärd som vidtas av en administratör, till exempel mjuk borttagning), dynamisk leverans och omarbetad (ett e-postmeddelande identifierades retroaktivt).

> [!NOTE]
>
> - Som en del av den här ändringen tas värdet borttaget med ZAP i filtret leverans åtgärd bort. Du kan söka efter all e-post med ZAP-försök via ytterligare åtgärder.
>
> - Det kommer att finnas nya fält och värden för identifierings teknologier och ytterligare åtgärder (särskilt för ZAP-scenarier). Utvärdera dina befintliga sparade frågor och spårade frågor för att kontrol lera att de fungerar med de nya värdena.

> [!div class="mx-imgBorder"]
> ![Ytterligare åtgärder i Utforskaren](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Systemåsidosättningar

Systemåsidosättningar är en metod för att skapa undantag till den avsedda leverans platsen för ett meddelande genom att åsidosätta den leverans plats som tillhandahålls av systemet (baserat på hoten och andra upptäckter som identifieras av vår filtrerings stack). Systemåsidosättningar kan anges via klient organisation eller användar princip för att leverera meddelandet enligt policyn. Åsidosättningar är användbara för att identifiera eventuell oavsiktlig leverans av skadliga meddelanden på grund av konfigurations luckor (till exempel en mycket omfattande policy för säker avsändare som har ställts in av en användare). Dessa värden kan vara:

- Tillåts av en användar princip: det här är när en användare tillåter domäner eller avsändare genom att skapa principer på post lådans nivå.
- Blockerad av en användar princip: det är när en användare spärrar domäner eller avsändare genom att skapa principer på post lådans nivå.
- Tillåtet enligt organisations princip: det här är när organisationens säkerhets team anger principer eller Exchange mail flöde-regler (kallas även transport regler) för att tillåta avsändare och domäner för användare i organisationen. Detta kan vara för en uppsättning användare eller hela organisationen.
- Blockerat av en organisations princip: det här är när organisationens säkerhets team anger principer eller regler för e-postflöde för att blockera avsändare, domäner, meddelande språk eller käll-IP för användare i organisationen. Det kan också vara för en uppsättning användare eller hela organisationen.
- Fil tillägget blockerat av en organisations princip: det här är när ett fil namns tillägg blockeras av en organisations säkerhets team via princip inställningarna mot skadlig program vara. Dessa värden visas nu i e-postinformation för att hjälpa till med undersökningar. Secops Teams kan också filtrera på blockerade fil namns tillägg med hjälp av funktionen för RTF-filtrering.

[![Systemåsidosättningar i Utforskaren](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Systemet åsidosätter rutnät i Utforskaren](../../media/System_Overrides_Grid.png)

### <a name="improvements-around-url-and-clicks-experience"></a>Förbättringar kring URL-och klicknings upplevelser

De förbättringar som prioriteras mot URL och URL klickar på data inkluderar:

- Visar fullständig URL-adress (inklusive frågeparametrar som är en del av URL) i avsnittet klickningar i URL-utfällbar. För närvarande visar vi URL-domänen och sökvägen i namn listen. Vi förlänger den informationen för att visa hela webb adressen.

- Korrigeringar via URL-filter (URL kontra URL-domän kontra URL-domän): vi har gjort uppdateringar för att söka efter meddelanden som innehåller en URL-adress/klicka på Verdict. Som en del av det har vi aktiverat stöd för sökning av protokoll oberoende (vilket betyder att du kan söka efter en URL utan http). Som standard mappas URL-sökning till http, om inget annat anges. Till exempel:

  1. Sök med och utan `http://` prefix i "URL", "URL Domain" och "URL Domain and Path", filter fält. Det här är konsekvent och bör visa samma resultat.

  1. Sök efter `https://` prefixet i "URL". När det inte `http://` anges används prefixet.

  1. `/` i början och slutet av "URL-sökväg", "URL-domän", "URL-domän och sökväg" ignoreras. `/` i slutet av fältet "URL" ignoreras.

### <a name="phish-confidence-level"></a>Phish konfidensnivå

Phish konfidensnivå hjälper dig att identifiera graden av förtroende, med vilken ett e-postmeddelande kategoriserats som Phish. De två möjliga värdena är hög och normal. I de inledande faserna är det här filtret bara tillgängligt i den Phish vyn av Threat Explorer.

[![Phish konfidensnivå i Utforskaren](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>ZAP URL-signal

Används vanligt vis för Phish varnings scenarier där en e-postadress angavs som Phish och togs bort efter leverans. Detta används för att koppla aviseringen med motsvarande resultat i Utforskaren. Det är en av IOCs för aviseringen.

Som en del av att förbättra jakt processen har vi gjort några uppdateringar för Threat Explorer och identifiering av real tid. Det här är en "Experience" förbättringar, med fokus på att göra jakt upplevelsen mer enhetlig. Dessa ändringar beskrivs nedan:

- [Förbättringar av tidszon](#timezone-improvements)
- [Uppdatera i uppdaterings processen](#update-in-the-refresh-process)
- [Diagram specificering att lägga till i filter](#chart-drilldown-to-add-to-filters)
- [Uppdateringar av produkt information](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrera efter användardefinierade Taggar

Du kan nu sortera och filtrera efter antingen system-eller anpassade användar märkningar för att snabbt förstå. Mer information finns i [användar koder](user-tags.md) .

> [!IMPORTANT]
> Filtrering och sortering efter användarmallar är för närvarande i offentlig för hands version.
> Den kan ändras väsentligt innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls.

![Kolumnen Taggar i Utforskaren](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Förbättringar av tidszon

Du kommer att se tids zonen för e-postmeddelandena i portalen samt för exporterade data. Tids zonen visas i upplevelser som e-postrutnät, information utfällbar, e-posttids linje och liknande e-postmeddelanden, så att tids zonen för resultat uppsättningen är klar för användaren.

> [!div class="mx-imgBorder"]
> ![Visa tids zonen i Utforskaren](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Uppdatera i uppdaterings processen

Vi har hört att få feedback kring förvirring med automatisk uppdatering (t. ex. för datum så fort du ändrar datumet kommer sidan att uppdateras) och manuell uppdatering (för andra filter). På samma sätt kan borttagning av filter leda till automatisk uppdatering, vilket gör att situationer där det går att ändra de olika filtren när du ändrar frågan är inkonsekventa Sök upplevelser. För att lösa det här flyttar vi till en manuell filtrerings funktion.

Från en miljö synpunkt kan användaren tillämpa och ta bort det olika intervallet med filter (från filter uppsättning och datum) och klicka på knappen Uppdatera för att filtrera resultaten när de har definierats. Knappen Uppdatera har också uppdaterats så att den visas tydligt på skärmen. Vi har också uppdaterat beskrivningar och dokumentation i produkten kring den här ändringen.

> [!div class="mx-imgBorder"]
> ![Klicka på Uppdatera för att filtrera resultat](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Diagram specificering att lägga till i filter

Du kommer nu att kunna Klicka på diagrammets serie värden för att lägga till det värdet som ett filter. Observera att du fortfarande måste klicka på knappen Uppdatera för att filtrera resultaten som en del av ändringen som beskrivs ovan.

> [!div class="mx-imgBorder"]
> ![Filtrera fram diagram](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Uppdateringar av produkt information

Du bör också läsa mer om produkten. Det totala antalet Sök resultat inom rutnätet (se nedan), samt förbättringar kring etiketter, fel meddelanden och beskrivningar, för att ge mer information kring filter, Sök funktioner och resultat uppsättning.

> [!div class="mx-imgBorder"]
> ![Visa information om produkten](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Utökade funktioner i Threat Explorer

### <a name="top-targeted-users"></a>Vanligaste riktade användare

Idag står det för en lista över de vanligaste riktade användarna i vyn mot skadlig kod för e-postmeddelanden (i den övre delen av familjen med skadlig kod). Vi kommer att utöka den här vyn i Phish och alla e-postvyer, där du kan se de fem vanligaste användarna tillsammans med antalet försök för varje användare för motsvarande vy (till exempel för Phish-vy kan du se antalet Phish-försök).
Du kan också exportera listan med riktade användare till en gräns på 3000 tillsammans med antalet försök för offline-analys för varje e-postvy. Det är bara att välja Nej. av försök (till exempel 13 försök nedan) öppnar en filtrerad vy i Threat Explorer så att du kan titta på mer information i alla e-postmeddelanden och hot för den användaren.

> [!div class="mx-imgBorder"]
> ![Vanligaste riktade användare](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Exchange Transport-regler

Som en del av data berikning bör du även kunna se alla olika transport regler som används för ett meddelande. Den här informationen visas i vyn e-post-rutnät (om du vill visa det väljer du kolumn alternativ i rutnätet och Lägg till Exchange-transportläge från kolumn alternativen i rutnätet) samt information som visas i e-postmeddelandet.
Du kan se både GUID och namnet på de transport regler som har lagts till i meddelandet. Dessutom kan du söka efter meddelanden med hjälp av namnet på transport regeln. Det här är en "innehåller"-sökning vilket innebär att du kan söka i vissa sökningar.

#### <a name="important-note"></a>Viktigt Obs!

Exchange Sök-och namn tillgänglighet beror på vilken roll som har tilldelats dig. Du måste ha någon av följande roller/behörigheter för att kunna visa Exchange namn och sökning.  Om du inte har någon av följande roller kopplade till dig kan du inte se namnen på transport reglerna och söka efter meddelanden med hjälp av Exchange-namnen. Men du kan se Exchange etikett och GUID-information i e-postinformationen. Det går inte att visa poster i e-postrutnät, e-flyouts, filter och export påverkas inte.

- Endast EXO – förhindra data förlust: alla
- Endast EXO-O365SupportViewConfig: alla
- AAD eller EXO-säkerhets administratör: alla
- AAD eller EXO – säkerhets läsare: alla
- Endast EXO – transport regler: alla
- Endast EXO-View-Only konfiguration: alla

I e-postrutnätet, den utfällbara informationen och exporterad CSV-fil visas ETR med ett namn/GUID som visas nedan.

> [!div class="mx-imgBorder"]
> ![Exchange Transport-regler](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Inkommande kopplingar

Kopplingar är en samling instruktioner som anpassar hur din e-post flödar till och från din Microsoft 365-eller Office 365-organisation, med möjligheten att tillämpa säkerhets begränsningar eller kontroller. I Threat Explorer kan du nu Visa kopplingarna som är relaterade till ett e-postmeddelande och söka efter e-postmeddelanden med hjälp av kopplings namnen.
Sök efter anslutningar är "innehåller", vilket innebär att ofullständiga nyckelords sökningar också fungerar.
I vyn huvud rutnät, den utfällbara informationen och den exporterade CSV-filen visas kopplingarna i namn/GUID-formatet enligt nedan:

> [!div class="mx-imgBorder"]
> ![Anslutnings information](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nya funktioner i Threat Explorer och identifiering av real tid

Tre nya funktioner läggs till i Threat Explorer och real tids identifiering:

- [Förhandsgranska e-posthuvud och hämta e-postmeddelande](#preview-email-header-and-download-email-body)
- [E-posttids linje](#email-timeline)
- [Exportera URL Klicka på data](#export-url-click-data)

Dessa nya funktioner beskrivs nedan.

### <a name="preview-email-header-and-download-email-body"></a>Förhandsgranska e-posthuvud och hämta e-postmeddelande

Möjligheten att förhandsgranska ett e-posthuvud och hämta e-postmeddelandet är nya funktioner som är tillgängliga i Threat Explorer. Administratörer kan analysera hämtade meddelandehuvuden/e-postmeddelanden för hot. Eftersom hämtning av e-postmeddelanden kan påverka exponeringen av informationen styrs processen av en rollbaserad åtkomst kontroll (RBAC). En ny roll, för *hands version*, måste läggas till i en annan roll grupp (som säkerhets åtgärder eller säkerhets administratör) för att tillåta möjligheten att hämta e-post och förhandsgranska rubriker i alla e-postmeddelanden.

Men Explorer (och real tids identifieringar) lägger också till nya fält som är utformade för att ge dig en mer fullständig bild av var e-postmeddelandena hamnar. En del av syftet med ändringen är att göra det lättare för säkerhetsledandet att skydda dig, men netto resultatet är att du snabbt kan se var det finns problem med e-postmeddelanden.

Hur gör du det här? Leverans status är nu uppdelad i två kolumner:

- **Leverans åtgärd** – vilken är statusen för det här meddelandet?
- **Leverans plats** – var hette detta e-postmeddelande som ett resultat?

Leverans åtgärden är den åtgärd som utförs via e-post på grund av befintliga principer eller identifieringar. Här är de möjliga åtgärder som ett e-postmeddelande kan ta:

|Levereras|Skräp post|Blockering|Byta|
|---|---|---|---|
|E-postmeddelandet skickades till Inkorgen eller mappen för en användare och användaren kan komma åt den direkt.|E-postmeddelandet skickades till antingen en användares skräppost eller borttagna mapp och användaren har till gång till e-post i dessa mappar.|Alla e-postmeddelanden som har satts i karantän, som misslyckats eller tagits bort. Det här är fullständigt otillgängligt för användaren!|Alla e-postmeddelanden där skadliga bifogade filer ersätts med txt-filer som gör att den bifogade filen har skadligt.|

|Levereras|Skräp post|Blockering|Byta|
|---|---|---|---|
|E-postmeddelandet skickades till användarens inkorg eller till en annan mapp, och användaren kan komma åt den direkt.|E-postmeddelandet skickades antingen till användarens skräppostmappen eller mappen borttagen, och användaren har till gång till e-postmeddelanden i dessa mappar.|Alla e-postmeddelanden som har satts i karantän, som misslyckats eller tagits bort och inte är tillgängliga för användaren.|Alla e-postmeddelanden där skadliga bifogade filer ersattes med txt-filer som anger att de bifogade filerna var skadliga.|
|

Så här ser användaren vad de kan se och vad de inte kan:

|Tillgänglig för slutanvändare|Ej tillgänglig för slutanvändare|
|---|---|
|Levereras|Blockering|
|Skräp post|Byta|

Leverans platsen visar resultaten av principer och upptäckter med efter-leverans. Den är länkad till en leverans åtgärd. Det här fältet lades till för att ge insyn i den åtgärd som utförs när ett problem har uppstått. Här är möjliga värden för leverans plats:

- **Inkorgen eller mapp**: e-postmeddelandet finns i Inkorgen eller i en mapp (enligt dina e-postregler).
- **On-lokala eller external**: post lådan finns inte i molnet, men den är lokal.
- **Skräppostmappen**: e-postmeddelandet finns i skräppostmappen för en användare.
- **Mappen Borttaget**: e-post i mappen Borttaget för en användare.
- **Karantän**: e-postmeddelandet i karantän och finns inte i en användares post låda.
- **Misslyckades**: det gick inte att nå post lådan.
- **Släppt**: e-postmeddelandet tappas bort någonstans i e-postflödet.

### <a name="email-timeline"></a>E-posttids linje

**E-Posttids linjen** är en ny Explorer-funktion som syftar till att förbättra jakt upplevelsen för administratörer. Den minskar med slumpmässigheten eftersom det är mindre tid att kontrol lera olika platser för att försöka förstå händelsen. När flera händelser inträffar till, eller nära till, samma tid i ett e-postmeddelande, visas händelserna i vyn tids linje. Vissa händelser som inträffar efter leverans till din e-post sparas i förhållande till "särskild åtgärd"-kolumnen. Om du kombinerar informationen från tids linjen för det e-postmeddelandet med den speciella åtgärden som utförs på post-leveransen får administratörer inblick i hur deras principer fungerar, där e-postmeddelandet slutligen skickades och, i vissa fall, vad den slutliga utvärderingen var.

Mer information om hur du undersöker illasinnade e-postmeddelanden finns i [undersöka och åtgärda skadlig e-post som har levererats i Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportera URL Klicka på data

Du kan då nu exportera rapporter för URL-musklick till Microsoft Excel för att visa både deras nätverks meddelande-ID och deras Klicka på Verdict, så att du kan förstå var din URL-adress klicka på trafik har blivit enklare. Så här fungerar det. Starta med Threat Management i snabb start för Office 365 genom att klicka igenom den här kedjan:

**Utforskaren** \> **Visa Phish** \> **Klickar på** \> **De översta URL-adresserna eller webb adressen** \> **Klicka på en post för att öppna webb adressen**

När du klickar på en URL-adress i listan visas en ny exportera-knapp på panelen utflygande. Använd den här knappen för att flytta data till ett Excel-kalkylblad för enklare rapportering.

Du kan komma till samma plats i rapporten för rapporter i real tid så här:

**Utforskaren** \> **Real tids identifiering** \> **Visa Phish** \> **URL: er** \> **Översta URL-adresser eller högst upp** \> **Klicka på en post för att öppna webb adressen** \> **Gå till fliken klickningar.**

> [!TIP]
> ID för nätverks meddelanden du klickar på tillbaka till vissa e-postmeddelanden när du söker via Utforskaren eller tillhör ande tredje parts verktyg via nätverks meddelande-ID. Om du söker igenom nätverks meddelande-ID: t får administratörer det specifika e-postmeddelandet som är associerat med ett Klicka Vid export är identifiering av nätverks meddelande-ID för snabbare och effektivare analys.

> [!div class="mx-imgBorder"]
> ![Klickar på fliken i Utforskaren](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Se malware identifierat i e-post efter teknik

Anta att du vill se hur skadlig kod identifieras i e-post, av Microsoft 365-teknologi. För att göra det här använder du [e-postmeddelandet med > skadlig program vara](threat-explorer-views.md#email--malware) för Explorer (eller real tids identifiering).

1. <https://protection.office.com>Välj **Threat Management** \> **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **View** **e-** \> **postmalware** på Visa-menyn.

   > [!div class="mx-imgBorder"]
   > ![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicka på **avsändare** och välj sedan **grundläggande** \> **identifierings teknik**.

   Din identifierings teknik är nu tillgänglig som filter för rapporten.

   > [!div class="mx-imgBorder"]
   > ![Tekniker för identifiering av skadlig program vara](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Välj ett alternativ och klicka sedan på knappen **Uppdatera** för att tillämpa filtret.

   > [!div class="mx-imgBorder"]
   > ![Vald identifierings teknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Rapporten uppdateras för att visa resultatet skadlig program vara som identifieras i e-post, med det teknik alternativ du valt. Härifrån kan du göra ytterligare analyser.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Visa data om nät fiske adresser och klicka på Verdict

Anta att du vill se nät fiske försök via URL: er via e-post, inklusive en lista med URL-adresser som tilläts, blockerades och åsidosatts. Om du vill konfigurera URL-adresser som har klickats kräver [säkra länkar](atp-safe-links.md) . Kontrol lera att du har angett [principer för säkra länkar](set-up-atp-safe-links-policies.md) för att klicka på skydd och loggning av Klicka på Verdicts efter Safe Links.

Om du vill granska Phish URL-adresser i meddelanden och klickar på URL: er i Phish meddelanden använder du [e-post> Phish](threat-explorer-views.md#email--phish) vyn av Utforskaren (eller real tids identifieringar).

1. <https://protection.office.com>Välj **Threat Management** \> **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **e-** Phish på **Visa** -menyn \> **Phish**.

   > [!div class="mx-imgBorder"]
   > ![Menyn Visa för Explorer i nät fiske kontext](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicka på **avsändare** och välj **URL-adresser** \> **på Verdict**.

4. Välj ett eller flera alternativ, till exempel **blockerat** och **blockera**, och klicka sedan på knappen **Uppdatera** på samma rad som de alternativ som används för att tillämpa filtret. (Uppdatera inte webbläsarfönstret.)

   > [!div class="mx-imgBorder"]
   > ![URL: er och klicka på verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Rapporten uppdateras och visar två olika URL-tabeller på fliken URL under rapporten:

   - De **vanligaste URL** -adresserna är de URL-adresser som visas i de meddelanden som du har filtrerat ned till och hur många e-postleveranser som är tillgängliga I Phish e-postvy innehåller listan normalt legitima URL: er. Attackerare inkluderar en blandning av bra och dåliga URL-adresser i sina meddelanden för att försöka komma åt dem, men de tar bort de skadliga länkarna mer intressant för användaren att klicka på. Tabellen med URL-adresser sorteras efter totalt antal e-postmeddelanden (men Observera att den här kolumnen är dold för att förenkla vyn).

   - De **bästa klickningarna** är de inkapslade länkarna som du har klickat på, sorterat efter totalt antal klickningar (den här kolumnen visas inte för att förenkla vyn). Kolumnen totalt antal gånger visar de säkra länkarna Klicka på Verdict antal för varje klickning-URL. I Phish e-postvy är de oftare misstänkta eller illasinnade webb adresser, men kan innehålla URL-adresser som inte är Hot men som är i Phish meddelanden. URL-klickningar på ej figursatta länkar visas inte här.

   I de två URL-tabellerna visas de högsta URL-adresserna i phishing-e-postmeddelanden efter leverans åtgärd och plats, och de visar URL-klickningar som har blockerats (eller som besökts trots en varning) så att du kan förstå vilka potentiella felaktiga länkar som användare har fått och interagerat med av användare. Härifrån kan du göra ytterligare analyser. Under diagrammet kan du till exempel se de högsta URL-adresserna i e-postmeddelanden som har blockerats i organisationens miljö.

   > [!div class="mx-imgBorder"]
   > ![Explorer-URL: er som blockerats](../../media/ExplorerPhishClickVerdictURLs.png)

   Välj en URL för att visa mer detaljerad information.

   > [!NOTE]
   > I dialog rutan URL-utfällbar text tas filtreringen av e-postmeddelanden bort så att du får fullständig vy över URL-vyns exponering i miljön. Med den här funktionen kan du filtrera ned e-postmeddelanden i Utforskaren till dem du är orolig för, hitta specifika URL-adresser som är potentiella hot och sedan utöka din förståelse av URL-exponeringen i din miljö (via dialog rutan URL-information) utan att behöva lägga till URL-filter i själva Utforskarvyn.

### <a name="interpretation-of-different-click-verdicts"></a>Tolkning av olika klick verdicts

I e-postmeddelandet eller URL-flyouts, de viktigaste tryckningarna samt i vår filter upplevelse ser du olika klick värden som en del av din jakt upplevelse. I det här avsnittet kan du välja Verdicts och deras tolkning:

- **Ingen**: det gick inte att skapa Verdict för URL-adressen. Användaren kanske har klickat via webb adressen.
- **Tillåten**: användaren har fått åtkomst till URL-adressen.
- **Blockerat**: användaren hindrades från att navigera till webb adressen.
- **Väntande Verdict**: användaren har presenter ATS med den väntande sidan för Sprängaren.
- **Blockerad åsidosatt**: användaren hindrades från att gå till URL-adressen. användaren overrode dock att gå till URL-adressen.
- **Väntande Verdict förbigåde**: användaren uppvisade sig med sidan detonation; användaren overrode till sidan för att gå till URL-adressen.
- **Fel**: användaren uppvisade fel sidan. Det kan också betyda att det fanns ett fel när du hämtade Verdict.
- **Fel**: ett okänt undantag uppstod när du hämtade Verdict. Användaren kanske har klickat via webb adressen.

## <a name="review-email-messages-reported-by-users"></a>Granska e-postmeddelanden som rapporter ATS av användare

Anta att du vill se e-postmeddelanden som användare i organisationen har rapporterat som skräp post, inte skräp post eller nätfiske med hjälp av [rapport tillägget för Outlook och Outlook på webben](enable-the-report-message-add-in.md). För att göra detta kan du använda [e-post>-](threat-explorer-views.md#email--submissions) vyn i Utforskaren (eller real tids identifieringar).

1. <https://protection.office.com>Välj **Threat Management** \> **Explorer** (eller **real tids identifiering**) i gruppen säkerhets & efterlevnad. (Det här exemplet använder Utforskaren.)

2. Välj **View** **e-** \> **postinlägg** i menyn Visa.

   > [!div class="mx-imgBorder"]
   > ![Menyn Visa för e-post i Utforskaren](../../media/explorer-view-menu-email-user-reported.png)

3. Klicka på **avsändare** och välj sedan **enkel** \> **typ av rapport**.

4. Välj ett alternativ, till exempel **Phish**, och klicka sedan på knappen **Uppdatera** .

   > [!div class="mx-imgBorder"]
   > ![Användardefinierad Phish](../../media/EmailUserReportedReportType.png)

Rapporten uppdateras och visar information om e-postmeddelanden som personer i organisationen har rapporterat som ett nät fiske försök. Du kan använda den här informationen för att utföra ytterligare analyser och, om det behövs, justera dina [skydds principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Starta automatisk undersökning och svar

> [!NOTE]
> Den automatiska undersöknings-och svars funktionerna är tillgängliga i **Microsoft Defender för Office 365 abonnemang 2** och **Office 365 E5**.

(Ny!) Den [automatiska undersökningen och svaret](automated-investigation-response-office.md) kan spara säkerhets arbets gruppen i stort sett tid och ansträngning för att undersöka och begränsa cyberattacks. Förutom att konfigurera aviseringar som kan utlösa en säkerhets Playbook kan du starta en automatiserad undersökning och svars process från en vy i Utforskaren.

För mer information, se [exempel: en säkerhets administratör utlöser en undersökning från Utforskaren](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Fler sätt att använda Explorer (eller real tids identifiering)

Utöver de scenarier som beskrivs i den här artikeln finns det många fler rapporterings alternativ som är tillgängliga med Explorer (eller real tids identifieringar).

- [Hitta och undersöka skadlig e-post som har levererats](investigate-malicious-email-that-was-delivered.md)
- [Visa skadliga filer som identifieras i SharePoint Online, OneDrive och Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Få en översikt över vyerna i Threat Explorer (och identifieringar i real tid)](threat-explorer-views.md)
- [Statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report)
- [Automatisk undersökning och svar i skydd mot Microsoft Threat](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Nödvändiga licenser och behörigheter

Du måste ha [Microsoft Defender för Office 365](office-365-atp.md) för att få Explorer eller real tids identifiering.

- Explorer ingår i Defender för Office 365 abonnemang 2.
- Rapporten om real tids identifiering ingår i Defender för Office 365 abonnemang 1.
- Planera för att tilldela licenser för alla användare som ska skyddas av Defender för Office 365. (Explorer eller real tids identifiering visar identifierings data för licensierade användare.)

Om du vill visa och använda Explorer-eller real tids identifiering måste du ha lämplig behörighet, till exempel en säkerhets administratör eller en säkerhets läsare.

- För säkerhets & Compliance Center måste du ha någon av följande roller tilldelade:

  - Organisationshantering
  - Säkerhets administratör (detta kan tilldelas i Azure Active Directory Admin Center ( <https://aad.portal.azure.com> )
  - Säkerhets läsare

- För Exchange Online måste du ha någon av följande roller tilldelade i antingen Exchange Admin Center ( <https://admin.protection.outlook.com/ecp/> ) eller [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):

  - Organisationshantering
  - View-Only organisations hantering
  - View-Only mottagare
  - Hantering av efterlevnad

Mer information om roller och behörigheter finns i följande resurser:

- [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)
- [Behörigheter för funktioner i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Skillnader mellan Threat Explorer och identifiering av real tid

- Rapporten om **identifiering av real tid** är tillgänglig i Defender för Office 365 abonnemang 1, medan **hot Explorer** är tillgänglig i Defender för Office 365 plan 2.
- Med rapporten **real tids identifiering** kan du Visa identifieringar i real tid. **Threat Explorer** fungerar också, men du kan även visa ytterligare information om en viss attack.
- En **all e-** postvy är tillgänglig i **Threat Explorer** (och är inte med i rapporten om **identifiering i real tid** ).
- Fler filter funktioner och tillgängliga åtgärder ingår i **Threat Explorer**.

Mer information finns i [Microsoft Defender för Office 365 Service Description: funktions tillgänglighet i Defender för office 365-abonnemang](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
