---
title: Optimera webb dels prestanda i sidor i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du använder Nätverksdiagnostik för att optimera prestanda för webb delar i SharePoint Online-moderna webbplats sidor.
ms.openlocfilehash: 7dcfcbfe033ef5f4257cc9688b61aca3227ade8b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694608"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="0a520-103">Optimera webb dels prestanda i sidor i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0a520-103">Optimize web part performance in SharePoint Online modern site pages</span></span>

<span data-ttu-id="0a520-104">Moderna webbplats sidor för SharePoint Online innehåller webb delar som kan bidra till den totala sid inläsnings tiden.</span><span class="sxs-lookup"><span data-stu-id="0a520-104">SharePoint Online modern site pages contain web parts that can contribute to overall page load times.</span></span> <span data-ttu-id="0a520-105">Den här artikeln hjälper dig att förstå hur webb delar på sidor påverkar uppskattad svars tid och hur du åtgärdar vanliga problem.</span><span class="sxs-lookup"><span data-stu-id="0a520-105">This article will help you understand how to determine how web parts in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="0a520-106">Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="0a520-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a><span data-ttu-id="0a520-107">Använda verktyget för nätverksdiagnostik för SharePoint för att analysera webb delar</span><span class="sxs-lookup"><span data-stu-id="0a520-107">Use the Page Diagnostics for SharePoint tool to analyze web parts</span></span>

<span data-ttu-id="0a520-108">Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="0a520-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="0a520-109">Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor.</span><span class="sxs-lookup"><span data-stu-id="0a520-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="0a520-110">Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="0a520-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="0a520-111">Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="0a520-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="0a520-112">När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om vilka webb delar som överskrider bas linjen i **webb delarna som påverkar sid inläsnings tiden** i fönstret _diagnostiktest_ .</span><span class="sxs-lookup"><span data-stu-id="0a520-112">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts that exceed the baseline metric in the **Web parts are impacting page load time** result in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="0a520-113">Möjliga resultat:</span><span class="sxs-lookup"><span data-stu-id="0a520-113">Possible results include:</span></span>

- <span data-ttu-id="0a520-114">**Åtgärd krävs** (röd): en _anpassad_ webbdel som visas i visnings området (skärm synlig del av sidan som laddas först) och som tar längre tid än **två** sekunder att läsa in.</span><span class="sxs-lookup"><span data-stu-id="0a520-114">**Attention required** (red): Any _custom_ web part that is visible in the viewport (screen visible portion of the page which is loaded first) that takes longer than **two** seconds to load.</span></span> <span data-ttu-id="0a520-115">_Anpassade_ webb delar utanför det område som tar längre tid än **fyra** sekunder att läsa in.</span><span class="sxs-lookup"><span data-stu-id="0a520-115">Any _custom_ web parts outside of the viewport that take longer than **four** seconds to load.</span></span> <span data-ttu-id="0a520-116">Total inläsnings tid visas i test resultat och är uppdelat per modul laddas, Lazy load, init and rendering.</span><span class="sxs-lookup"><span data-stu-id="0a520-116">Total load time is displayed in test results and is broken down by module load, lazy load, init and render.</span></span>
- <span data-ttu-id="0a520-117">**Förbättrings möjligheter** (gula): objekt som kan påverka sid inläsnings tid visas i det här avsnittet och bör granskas och övervakas.</span><span class="sxs-lookup"><span data-stu-id="0a520-117">**Improvement opportunities** (yellow): Items that may be impacting page load time are shown in this section and should be reviewed and monitored.</span></span> <span data-ttu-id="0a520-118">Det kan innehålla "från lådan" (OOTB) webb delar.</span><span class="sxs-lookup"><span data-stu-id="0a520-118">This may include "out of the box" (OOTB) Microsoft web parts.</span></span> <span data-ttu-id="0a520-119">Resultaten för de Microsoft-webbdelar som visas i det här avsnittet rapporteras automatiskt till Microsoft, så **Ingen åtgärd krävs**.</span><span class="sxs-lookup"><span data-stu-id="0a520-119">Results for any Microsoft web parts shown in this section are automatically reported to Microsoft, so **no action is required**.</span></span> <span data-ttu-id="0a520-120">Du bör bara logga ett support ärende för att få en undersökning om du har mycket långsam prestanda på sidan och **alla Microsoft webb delar** på sidan visas i avsnittet **förbättrings möjligheter** .</span><span class="sxs-lookup"><span data-stu-id="0a520-120">You should only log a support ticket for investigation if you are experiencing very slow performance on the page and **all Microsoft web parts** on the page appear in the results in the **Improvement opportunities** section.</span></span> <span data-ttu-id="0a520-121">Observera att om du uppdaterar en framtida diagnostik för SharePoint-verktyg kommer resultaten att brytas efter den specifika konfigurationen för Microsoft-webbdelen.</span><span class="sxs-lookup"><span data-stu-id="0a520-121">Note that a future Page Diagnostics for SharePoint tool update will further break down the results based on the specific configuration of the Microsoft web part.</span></span>
- <span data-ttu-id="0a520-122">**Ingen åtgärd krävs** (grön): ingen webbdel tar längre tid än **två** sekunder att returnera data.</span><span class="sxs-lookup"><span data-stu-id="0a520-122">**No action required** (green): No web part is taking longer than **two** seconds to return data.</span></span>

<span data-ttu-id="0a520-123">Om **webb delarna påverkar tiden för sid inläsnings tid** som visas i avsnittet **Obs!** eller **förbättrings möjligheter** i resultatet klickar du på resultatet för att visa information om vilka webb delar som laddas långsamt.</span><span class="sxs-lookup"><span data-stu-id="0a520-123">If the **Web parts are impacting page load time** result appears in either the **Attention required** or **Improvement opportunities** section of the results, click the result to see details about which web parts are loading slowly.</span></span> <span data-ttu-id="0a520-124">Framtida uppdateringar av diagnostikverktyget för SharePoint kan innehålla uppdateringar av analys regler, så se till att du alltid har den senaste versionen av verktyget.</span><span class="sxs-lookup"><span data-stu-id="0a520-124">Future updates to the Page Diagnostics for SharePoint tool may include updates to analysis rules, so please ensure you always have the latest version of the tool.</span></span>

![Resultat för verktyget Nätverksdiagnostik](../media/modern-portal-optimization/pagediag-web-part.png)

<span data-ttu-id="0a520-126">Informationen i resultatet inkluderar:</span><span class="sxs-lookup"><span data-stu-id="0a520-126">Information available in the results includes:</span></span>

- <span data-ttu-id="0a520-127">**Gjort av** visar om webb delen är anpassad eller Microsoft OOTB</span><span class="sxs-lookup"><span data-stu-id="0a520-127">**Made by** shows whether the web part is custom or Microsoft OOTB</span></span>
- <span data-ttu-id="0a520-128">**Namn och ID** visar identifierande information som kan hjälpa dig att hitta webb delen på sidan</span><span class="sxs-lookup"><span data-stu-id="0a520-128">**Name and ID** shows identifying information that can help you find the web part on the page</span></span>
- <span data-ttu-id="0a520-129">**Totalt** visar den totala tiden för webb delen som ska läsas in</span><span class="sxs-lookup"><span data-stu-id="0a520-129">**Total** shows the total time for the web part to load</span></span>
- <span data-ttu-id="0a520-130">**Modul beläggning** visar hur lång tid det tar att hämta och ladda webb dels komponenter</span><span class="sxs-lookup"><span data-stu-id="0a520-130">**Module Load** shows the time taken to fetch and load the web part components</span></span>
- <span data-ttu-id="0a520-131">**Lazy load** visar tiden för uppskjutning av webb delar som inte visas i huvud avsnittet på sidan</span><span class="sxs-lookup"><span data-stu-id="0a520-131">**Lazy Load** shows the time for deferred loading of web parts not seen in the main section of the page</span></span>
- <span data-ttu-id="0a520-132">**Init** visar den tid det tar för webb dels initiering</span><span class="sxs-lookup"><span data-stu-id="0a520-132">**Init** shows the time taken for web part initialization</span></span>
- <span data-ttu-id="0a520-133">**Rendera** visar den tid det tar för webb delen att hämta och återge resultat</span><span class="sxs-lookup"><span data-stu-id="0a520-133">**Render** shows the time taken for the web part to fetch and render results</span></span>

<span data-ttu-id="0a520-134">Den här informationen tillhandahålls för att utvecklare och utvecklare ska kunna felsöka problem.</span><span class="sxs-lookup"><span data-stu-id="0a520-134">This information is provided to help designers and developers troubleshoot issues.</span></span> <span data-ttu-id="0a520-135">Denna information bör ges till din design-och utvecklings grupp.</span><span class="sxs-lookup"><span data-stu-id="0a520-135">This information should be provided to your design and development team.</span></span>

## <a name="remediate-web-part-performance-issues"></a><span data-ttu-id="0a520-136">Åtgärda problem med webb dels prestanda</span><span class="sxs-lookup"><span data-stu-id="0a520-136">Remediate web part performance issues</span></span>

<span data-ttu-id="0a520-137">Följ anvisningarna i det här avsnittet om du vill identifiera och åtgärda prestanda problem med webb delar som listas i **webb delarna påverkar sid inläsnings tid** .</span><span class="sxs-lookup"><span data-stu-id="0a520-137">Follow the guidance in this section to identify and remediate performance issues with web parts listed in the **Web parts are impacting page load time** results.</span></span>

<span data-ttu-id="0a520-138">Det finns tre möjliga orsaker till dåligt webb dels prestanda.</span><span class="sxs-lookup"><span data-stu-id="0a520-138">There are three categories of possible causes for poor web part performance.</span></span> <span data-ttu-id="0a520-139">Använd informationen nedan för att avgöra vilka problem som gäller för ditt scenario och åtgärda dem.</span><span class="sxs-lookup"><span data-stu-id="0a520-139">Use the information below to determine which issues apply to your scenario and remediate them.</span></span>

- <span data-ttu-id="0a520-140">Skript storlek och samband för webb delar</span><span class="sxs-lookup"><span data-stu-id="0a520-140">Web part script size and dependencies</span></span>
  - <span data-ttu-id="0a520-141">Optimera det första skriptet som visar Mainline-scenariot för _endast visnings läge_.</span><span class="sxs-lookup"><span data-stu-id="0a520-141">Optimize the initial script that renders the mainline scenario for _view mode only_.</span></span>
  - <span data-ttu-id="0a520-142">Flytta de mindre vanliga scenarierna och redigerings läges koden (som egenskaps fönstret) till olika segment med hjälp av _import ()_ -instruktionen.</span><span class="sxs-lookup"><span data-stu-id="0a520-142">Move the less frequent scenarios and edit mode code (like the property pane) to separate chunks using the _import()_ statement.</span></span>
  - <span data-ttu-id="0a520-143">Ta bort alla döda koder fullständigt genom att granska sambanden för _package.js_ .</span><span class="sxs-lookup"><span data-stu-id="0a520-143">Review dependencies of the _package.json_ file to remove any dead code completely.</span></span> <span data-ttu-id="0a520-144">Flytta alla test/skapa bara samband till devDependencies.</span><span class="sxs-lookup"><span data-stu-id="0a520-144">Move any test/build only dependencies to devDependencies.</span></span>
  - <span data-ttu-id="0a520-145">Användning av Office 365 CDN krävs för optimal statisk resurs nedladdning.</span><span class="sxs-lookup"><span data-stu-id="0a520-145">Use of the Office 365 CDN is required for optimal static resource download.</span></span> <span data-ttu-id="0a520-146">Offentliga CDN-ursprung är lämpligt för _JS/CSS-_ filer.</span><span class="sxs-lookup"><span data-stu-id="0a520-146">Public CDN origins are preferable for _js/css_ files.</span></span> <span data-ttu-id="0a520-147">Mer information om hur du använder Office 365 CDN finns i [använda office 365-leverans Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="0a520-147">For more information about using the Office 365 CDN, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="0a520-148">Åter användnings bara ramverk som _reagerar_ och _Fabric-import_ som ingår i SharePoint Framework (SPFx).</span><span class="sxs-lookup"><span data-stu-id="0a520-148">Reuse frameworks like _React_ and _Fabric imports_ that come as part of the SharePoint Framework (SPFx).</span></span> <span data-ttu-id="0a520-149">Mer information finns i [Översikt över SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span><span class="sxs-lookup"><span data-stu-id="0a520-149">For more information, see [Overview of the SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).</span></span>
  - <span data-ttu-id="0a520-150">Kontrol lera att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="0a520-150">Ensure that you are using the latest version of the SharePoint Framework, and upgrade to new versions as they become available.</span></span>
- <span data-ttu-id="0a520-151">Data hämtning/cachning</span><span class="sxs-lookup"><span data-stu-id="0a520-151">Data fetching/caching</span></span>
  - <span data-ttu-id="0a520-152">Om webb delen är beroende av extra Server samtal för att hämta data för visning kontrollerar du att dessa Server-API: er snabbt och/eller implementerar cachelagring på klient sidan (till exempel genom att använda _localStorage_ eller _IndexDB_ för större uppsättningar).</span><span class="sxs-lookup"><span data-stu-id="0a520-152">If the web part relies on extra server calls to fetch data for display, ensure those server APIs are fast and/or implement client side caching (such as using _localStorage_ or _IndexDB_ for larger sets).</span></span>
  - <span data-ttu-id="0a520-153">Om det krävs flera samtal för att återge viktiga data bör du överväga att använda en server eller någon annan metod för att konsolidera förfrågningar till ett enda samtal.</span><span class="sxs-lookup"><span data-stu-id="0a520-153">If multiple calls are required to render critical data, consider batching on the server or other methods of consolidating requests to a single call.</span></span>
  - <span data-ttu-id="0a520-154">Om vissa delar av data kräver ett långsammare API men inte är kritiska för inledande rendering kan du koppla ihop dessa med ett separat samtal som körs efter att kritiska data har Render ATS.</span><span class="sxs-lookup"><span data-stu-id="0a520-154">Alternatively, if some elements of data require a slower API, but are not critical to initial rendering, decouple these to a separate call that is executed after critical data is rendered.</span></span>
  - <span data-ttu-id="0a520-155">Om flera delar använder samma data kan du använda ett vanligt data lager för att undvika dubbletter.</span><span class="sxs-lookup"><span data-stu-id="0a520-155">If multiple parts use the same data, utilize a common data layer to avoid duplicate calls.</span></span>
- <span data-ttu-id="0a520-156">Åter givnings tid</span><span class="sxs-lookup"><span data-stu-id="0a520-156">Rendering time</span></span>
  - <span data-ttu-id="0a520-157">Alla medie källor som bilder och videor bör begränsas till gränserna för behållaren, enheten och/eller nätverket för att undvika onödigt stora till gångar.</span><span class="sxs-lookup"><span data-stu-id="0a520-157">Any media sources like images and videos should be sized to the limits of the container, device and/or network to avoid downloading unnecessary large assets.</span></span> <span data-ttu-id="0a520-158">Mer information om innehålls beroenden finns i [använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="0a520-158">For more information about content dependencies, see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>
  - <span data-ttu-id="0a520-159">Undvik API-samtal som orsakar omflöde, komplexa CSS-regler eller komplexa animeringar.</span><span class="sxs-lookup"><span data-stu-id="0a520-159">Avoid API calls that cause re-flow, complex CSS rules or complicated animations.</span></span> <span data-ttu-id="0a520-160">Mer information finns i [minimera bakströmningen](https://developers.google.com/speed/docs/insights/browser-reflow).</span><span class="sxs-lookup"><span data-stu-id="0a520-160">For more information, see [Minimizing browser reflow](https://developers.google.com/speed/docs/insights/browser-reflow).</span></span>
  - <span data-ttu-id="0a520-161">Undvik att använda inaktiva långa aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="0a520-161">Avoid use of chained long running tasks.</span></span> <span data-ttu-id="0a520-162">I stället kan du dela tids krävande uppgifter i olika köer.</span><span class="sxs-lookup"><span data-stu-id="0a520-162">Instead, break long running tasks apart into separate queues.</span></span> <span data-ttu-id="0a520-163">Mer information finns i [optimera JavaScript-körning](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span><span class="sxs-lookup"><span data-stu-id="0a520-163">For more information, see [Optimize JavaScript Execution](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).</span></span>
  - <span data-ttu-id="0a520-164">Reservera motsvarande utrymme för asynkron åter givning av media eller visuella element för att undvika överhoppade ramar och hackigt (kallas även _Jank_).</span><span class="sxs-lookup"><span data-stu-id="0a520-164">Reserve corresponding space for asynchronously rendering media or visual elements to avoid skipped frames and stuttering (also known as _jank_).</span></span>
  - <span data-ttu-id="0a520-165">Om en viss webbläsare inte har stöd för en funktion som används i rendering kan du antingen använda en polyfyllning eller utesluta en beroende kod.</span><span class="sxs-lookup"><span data-stu-id="0a520-165">If a certain browser doesn't support a feature used in rendering, either load a polyfill or exclude running dependent code.</span></span> <span data-ttu-id="0a520-166">Om funktionen inte är kritisk kan du ta bort resurser som händelse hanterare för att undvika minnes läckor.</span><span class="sxs-lookup"><span data-stu-id="0a520-166">If the feature is not critical, dispose resources such as event handlers to avoid memory leaks.</span></span>

<span data-ttu-id="0a520-167">Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten.</span><span class="sxs-lookup"><span data-stu-id="0a520-167">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="0a520-168">Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.</span><span class="sxs-lookup"><span data-stu-id="0a520-168">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="0a520-170">Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden.</span><span class="sxs-lookup"><span data-stu-id="0a520-170">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="0a520-171">Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.</span><span class="sxs-lookup"><span data-stu-id="0a520-171">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a520-172">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0a520-172">Related topics</span></span>

[<span data-ttu-id="0a520-173">Justera SharePoint Online-prestanda</span><span class="sxs-lookup"><span data-stu-id="0a520-173">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="0a520-174">Justera Office 365-prestanda</span><span class="sxs-lookup"><span data-stu-id="0a520-174">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="0a520-175">Prestanda i den moderna SharePoint-upplevelsen</span><span class="sxs-lookup"><span data-stu-id="0a520-175">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="0a520-176">Nätverk för innehålls leverans</span><span class="sxs-lookup"><span data-stu-id="0a520-176">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="0a520-177">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0a520-177">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)