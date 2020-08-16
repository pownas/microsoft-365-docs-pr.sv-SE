---
title: Kapacitetsplanering och belastningstestning av SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan att genomföra traditionella inläsnings test eftersom det inte är tillåtet.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694764"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="863b8-103">Kapacitetsplanering och belastningstestning av SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="863b8-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="863b8-104">I den här artikeln beskrivs hur du kan distribuera till SharePoint Online utan traditionella inläsnings test, eftersom det inte är tillåtet att läsa in testning för SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="863b8-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="863b8-105">SharePoint Online är en moln tjänst och lastens kapacitet, hälsa och total saldo för tjänsten hanteras av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="863b8-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="863b8-106">Den bästa metoden för att säkerställa att webbplatsen startas är att följa grundläggande principer, praxis och rekommendationer som är markerade i det abonnemang som [din portal](planportallaunchroll-out.md)börjar på.</span><span class="sxs-lookup"><span data-stu-id="863b8-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="863b8-107">Översikt över hur SharePoint Online utför kapacitets planering</span><span class="sxs-lookup"><span data-stu-id="863b8-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="863b8-108">En av de viktigaste fördelarna med att använda SharePoint Online via en lokal distribution är att molnet är elastiskt samt optimeringar för användare i distribuerade regioner.</span><span class="sxs-lookup"><span data-stu-id="863b8-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="863b8-109">Vår storskalig miljö är inställd på att betjäna miljon tals användare dagligen, så det är viktigt att vi hanterar kapaciteten effektivt genom att balansera och expandera Server grupper.</span><span class="sxs-lookup"><span data-stu-id="863b8-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="863b8-110">Även om tillväxten är ofta oförutsägbart för en enda klient organisation i en Server grupp, är det förutsägbart att en mängd begär Anden är tidsödande över tiden.</span><span class="sxs-lookup"><span data-stu-id="863b8-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="863b8-111">Genom att identifiera tillväxt trenderna i SharePoint Online kan vi planera för framtida utbyggnad.</span><span class="sxs-lookup"><span data-stu-id="863b8-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="863b8-112">För att effektivt utnyttja kapaciteten och hantera oväntad tillväxt i alla Server grupper har vi automatiserat att spåra och övervaka olika delar av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="863b8-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="863b8-113">Flera mått används, med ett av de viktigaste som är CPU-belastning, som används som en signal för att bygga upp front servrar.</span><span class="sxs-lookup"><span data-stu-id="863b8-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="863b8-114">Dessutom rekommenderar vi att du använder en [Stegad/Wave-inställning](planportallaunchroll-out.md), eftersom SQL-miljöerna skal för änd ras i takt med att det går att distribuera och utvecklas.</span><span class="sxs-lookup"><span data-stu-id="863b8-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="863b8-115">Kapaciteten är mer än att bara lägga till mer maskin vara på en gång, men det finns också att hantera och kontrol lera den kapaciteten för att säkerställa att den hanterar giltiga inläsnings begär Anden.</span><span class="sxs-lookup"><span data-stu-id="863b8-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="863b8-116">Vi rekommenderar att kunderna följer den rekommenderade vägledningen för att säkerställa att de har den bästa upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="863b8-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="863b8-117">Det innebär också att vi har begränsat mönster och kontroller för att säkerställa att vi inte tillåter "grova" beteende i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="863b8-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="863b8-118">Men inte alla "dåligt" beteende är avsiktligt måste vi se till att vi begränsar effekten av detta beteende.</span><span class="sxs-lookup"><span data-stu-id="863b8-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="863b8-119">Mer information om hur du begränsar och hur du undviker det finns i artikeln om att [undvika begränsning av vägledning](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) .</span><span class="sxs-lookup"><span data-stu-id="863b8-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="863b8-120">Varför du inte kan läsa in testa SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="863b8-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="863b8-121">Med lokala miljöer används inläsnings testning för att bekräfta skalnings antagande och slutligen för att hitta den avbrotts punkten i en grupp. genom att saturating den med load.</span><span class="sxs-lookup"><span data-stu-id="863b8-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="863b8-122">Med SharePoint Online måste vi göra saker på ett annat sätt eftersom skalan är relativt Fluid och justerar, begränsning och kontroll belastning, baserat på vissa heuristik.</span><span class="sxs-lookup"><span data-stu-id="863b8-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="863b8-123">Eftersom det är en sådan storskalig miljö för flera innehavare måste vi skydda alla klient organisationer i samma server grupp, så vi kommer automatiskt att reglera eventuella laddnings test.</span><span class="sxs-lookup"><span data-stu-id="863b8-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="863b8-124">Om du ändå försöker att läsa in test, utöver begränsning, får du inte blev och potentiellt missvisande resultat eftersom Server gruppen du testade i dag sannolikt hade haft ändringar under test fönstret eller inom några timmar efter testningen, allteftersom skalnings-och Server grupp balansering utförts.</span><span class="sxs-lookup"><span data-stu-id="863b8-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="863b8-125">I stället för att försöka läsa in testa SharePoint som en tjänst kan du i stället fokusera på att följa rekommendationerna och följa anvisningarna för att [skapa, starta och hantera en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838) vägledning.</span><span class="sxs-lookup"><span data-stu-id="863b8-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838) guidance.</span></span>