---
title: Flytta grundläggande data till nya Microsoft 365 Data Center-geos
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: Lär dig mer om nya Office 365 Data Center-geos och hur du använder alternativet data de för att begära att dina grundläggande data flyttas till en ny geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c1c838f52627e0ff2eee5b7fdbeef7aee55b137
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694292"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a><span data-ttu-id="681e0-103">Flytta grundläggande data till nya Microsoft 365 Data Center-geos</span><span class="sxs-lookup"><span data-stu-id="681e0-103">Moving core data to new Microsoft 365 datacenter geos</span></span>

<span data-ttu-id="681e0-104">Vi fortsätter att öppna nya data Center-geos för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="681e0-104">We continue to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="681e0-105">De här nya datacenter-geos lägga till kapacitet och beräkna resurser för att stödja vår pågående kund efter frågan och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="681e0-105">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="681e0-106">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="681e0-106">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span> 

<span data-ttu-id="681e0-107">Grundläggande kund data är en term som refererar till en delmängd kunddata, inklusive:</span><span class="sxs-lookup"><span data-stu-id="681e0-107">Core customer data is a term that refers to a subset of customer data including:</span></span> 
- <span data-ttu-id="681e0-108">Innehåll för Exchange Online-postlådan (e-post, kalender poster och innehållet i e-postbilagor)</span><span class="sxs-lookup"><span data-stu-id="681e0-108">Exchange Online mailbox content (email body, calendar entries, and the content of email attachments)</span></span>
- <span data-ttu-id="681e0-109">SharePoint Online-webbinnehåll och filer som lagras på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="681e0-109">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="681e0-110">Filer som laddats upp till OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="681e0-110">Files uploaded to OneDrive for Business</span></span>
- <span data-ttu-id="681e0-111">Teams chatt meddelanden, inklusive privata meddelanden, kanal meddelanden och bilder som används i chattar</span><span class="sxs-lookup"><span data-stu-id="681e0-111">Teams chat messages, including private messages, channel messages, and images used in chats</span></span>
  
<span data-ttu-id="681e0-112">Befintliga kunder som har sina grundläggande kund uppgifter lagrade i ett befintligt Data Center-geo påverkas inte av lanseringen av ett nytt Data Center geo.</span><span class="sxs-lookup"><span data-stu-id="681e0-112">Existing customers that have their core customer data stored in an already existing datacenter geo are not impacted by the launch of a new datacenter geo.</span></span> <span data-ttu-id="681e0-113">Vi presenterar inga unika funktioner, funktioner och certifikat certifiering med det nya data centret geo.</span><span class="sxs-lookup"><span data-stu-id="681e0-113">We introduce no unique capabilities, features or compliance certifications with the new datacenter geo.</span></span> <span data-ttu-id="681e0-114">Som kund i någon av de två geos kommer du att uppleva samma QoS-kvalitet, prestanda och säkerhets kontroller som du gjorde förut.</span><span class="sxs-lookup"><span data-stu-id="681e0-114">As a customer in any of those two geos, you will experience the same quality of service, performance and security controls as you did before.</span></span> <span data-ttu-id="681e0-115">Vi tillhandahåller befintliga kunder i tabellen nedan ett alternativ för att begära tidiga migration av organisationens grundläggande kund uppgifter på ett sätt som vilar mot deras nya data Center.</span><span class="sxs-lookup"><span data-stu-id="681e0-115">We offer existing customers listed in the table below an option to request early migration of their organization's core customer data at rest to their new datacenter geo.</span></span>
  
|<span data-ttu-id="681e0-116">**Kunder med klient organisationens registrerings land i**</span><span class="sxs-lookup"><span data-stu-id="681e0-116">**Customers with tenant signup country in**</span></span>|<span data-ttu-id="681e0-117">**Föregående Data Center geo**</span><span class="sxs-lookup"><span data-stu-id="681e0-117">**Previous datacenter geo**</span></span>|<span data-ttu-id="681e0-118">**Nytt Data Center geo**</span><span class="sxs-lookup"><span data-stu-id="681e0-118">**New datacenter geo**</span></span>|<span data-ttu-id="681e0-119">**Geo-tillgängligt sedan**</span><span class="sxs-lookup"><span data-stu-id="681e0-119">**Geo available since**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="681e0-120">**Japan**</span><span class="sxs-lookup"><span data-stu-id="681e0-120">**Japan**</span></span>| <span data-ttu-id="681e0-121">Asien/Stilla havet</span><span class="sxs-lookup"><span data-stu-id="681e0-121">Asia/Pacific</span></span> | <span data-ttu-id="681e0-122">Japan</span><span class="sxs-lookup"><span data-stu-id="681e0-122">Japan</span></span> | <span data-ttu-id="681e0-123">December 2014</span><span class="sxs-lookup"><span data-stu-id="681e0-123">December 2014</span></span> |
|<span data-ttu-id="681e0-124">**Australien, Nya Zeeland, Fidji**</span><span class="sxs-lookup"><span data-stu-id="681e0-124">**Australia, New Zealand, Fiji**</span></span>| <span data-ttu-id="681e0-125">Asien/Stilla havet</span><span class="sxs-lookup"><span data-stu-id="681e0-125">Asia/Pacific</span></span> | <span data-ttu-id="681e0-126">Australien</span><span class="sxs-lookup"><span data-stu-id="681e0-126">Australia</span></span> | <span data-ttu-id="681e0-127">Mars 2015</span><span class="sxs-lookup"><span data-stu-id="681e0-127">March 2015</span></span> |
|<span data-ttu-id="681e0-128">**Indien**</span><span class="sxs-lookup"><span data-stu-id="681e0-128">**India**</span></span>| <span data-ttu-id="681e0-129">Asien/Stilla havet</span><span class="sxs-lookup"><span data-stu-id="681e0-129">Asia/Pacific</span></span> | <span data-ttu-id="681e0-130">Indien</span><span class="sxs-lookup"><span data-stu-id="681e0-130">India</span></span> | <span data-ttu-id="681e0-131">Oktober 2015</span><span class="sxs-lookup"><span data-stu-id="681e0-131">October 2015</span></span> |
|<span data-ttu-id="681e0-132">**Kanada**</span><span class="sxs-lookup"><span data-stu-id="681e0-132">**Canada**</span></span>| <span data-ttu-id="681e0-133">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="681e0-133">North America</span></span> | <span data-ttu-id="681e0-134">Kanada</span><span class="sxs-lookup"><span data-stu-id="681e0-134">Canada</span></span> | <span data-ttu-id="681e0-135">Maj 2016</span><span class="sxs-lookup"><span data-stu-id="681e0-135">May 2016</span></span> |
|<span data-ttu-id="681e0-136">**Storbritannien**</span><span class="sxs-lookup"><span data-stu-id="681e0-136">**United Kingdom**</span></span>| <span data-ttu-id="681e0-137">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-137">Europe</span></span> | <span data-ttu-id="681e0-138">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="681e0-138">United Kingdom</span></span> | <span data-ttu-id="681e0-139">September 2016</span><span class="sxs-lookup"><span data-stu-id="681e0-139">September 2016</span></span> |
|<span data-ttu-id="681e0-140">**Sydkorea**</span><span class="sxs-lookup"><span data-stu-id="681e0-140">**South Korea**</span></span>| <span data-ttu-id="681e0-141">Asien/Stilla havet</span><span class="sxs-lookup"><span data-stu-id="681e0-141">Asia/Pacific</span></span> | <span data-ttu-id="681e0-142">Sydkorea</span><span class="sxs-lookup"><span data-stu-id="681e0-142">South Korea</span></span> | <span data-ttu-id="681e0-143">April 2017</span><span class="sxs-lookup"><span data-stu-id="681e0-143">April 2017</span></span> |
|<span data-ttu-id="681e0-144">**Frankrike**</span><span class="sxs-lookup"><span data-stu-id="681e0-144">**France**</span></span>| <span data-ttu-id="681e0-145">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-145">Europe</span></span> | <span data-ttu-id="681e0-146">Frankrike</span><span class="sxs-lookup"><span data-stu-id="681e0-146">France</span></span> | <span data-ttu-id="681e0-147">Mars 2018</span><span class="sxs-lookup"><span data-stu-id="681e0-147">March 2018</span></span> |
|<span data-ttu-id="681e0-148">**Förenade Arabemiraten**</span><span class="sxs-lookup"><span data-stu-id="681e0-148">**United Arab Emirates**</span></span>| <span data-ttu-id="681e0-149">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-149">Europe</span></span> | <span data-ttu-id="681e0-150">Förenade Arabemiraten</span><span class="sxs-lookup"><span data-stu-id="681e0-150">United Arab Emirates</span></span> | <span data-ttu-id="681e0-151">Juni 2019</span><span class="sxs-lookup"><span data-stu-id="681e0-151">June 2019</span></span> |
|<span data-ttu-id="681e0-152">**Sydafrika**</span><span class="sxs-lookup"><span data-stu-id="681e0-152">**South Africa**</span></span>| <span data-ttu-id="681e0-153">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-153">Europe</span></span> | <span data-ttu-id="681e0-154">Sydafrika</span><span class="sxs-lookup"><span data-stu-id="681e0-154">South Africa</span></span> | <span data-ttu-id="681e0-155">Juli 2019</span><span class="sxs-lookup"><span data-stu-id="681e0-155">July 2019</span></span> |
|<span data-ttu-id="681e0-156">**Schweiz, Liechtenstein**</span><span class="sxs-lookup"><span data-stu-id="681e0-156">**Switzerland, Liechtenstein**</span></span>| <span data-ttu-id="681e0-157">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-157">Europe</span></span> | <span data-ttu-id="681e0-158">Schweiz</span><span class="sxs-lookup"><span data-stu-id="681e0-158">Switzerland</span></span> | <span data-ttu-id="681e0-159">December 2019</span><span class="sxs-lookup"><span data-stu-id="681e0-159">December 2019</span></span> |
|<span data-ttu-id="681e0-160">**Tyskland**</span><span class="sxs-lookup"><span data-stu-id="681e0-160">**Germany**</span></span>| <span data-ttu-id="681e0-161">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-161">Europe</span></span> | <span data-ttu-id="681e0-162">Tyskland</span><span class="sxs-lookup"><span data-stu-id="681e0-162">Germany</span></span> | <span data-ttu-id="681e0-163">December 2019</span><span class="sxs-lookup"><span data-stu-id="681e0-163">December 2019</span></span> |
|<span data-ttu-id="681e0-164">**Norge**</span><span class="sxs-lookup"><span data-stu-id="681e0-164">**Norway**</span></span>| <span data-ttu-id="681e0-165">Europa</span><span class="sxs-lookup"><span data-stu-id="681e0-165">Europe</span></span> | <span data-ttu-id="681e0-166">Norge</span><span class="sxs-lookup"><span data-stu-id="681e0-166">Norway</span></span> | <span data-ttu-id="681e0-167">April 2020</span><span class="sxs-lookup"><span data-stu-id="681e0-167">April 2020</span></span> |
  
<span data-ttu-id="681e0-168">Nya kunder eller Office 365-klient organisationer som har skapats efter tillgänglighet av den nya data Center geo kommer att ha grundläggande kund uppgifter lagrade på nya data Center-geo automatiskt.</span><span class="sxs-lookup"><span data-stu-id="681e0-168">New customers or Office 365 tenants created after the availability of the new datacenter geo will have their core customer data stored at rest in the new datacenter geo automatically.</span></span>


>[!Note]
><span data-ttu-id="681e0-169">Vi startade Tyskland Data Center i december 2019.</span><span class="sxs-lookup"><span data-stu-id="681e0-169">We launched the Germany datacenter region in December 2019.</span></span> <span data-ttu-id="681e0-170">Nya Microsoft 365-kunder med en tysk signup-adress som är kopplad till deras klient organisation kommer att ha sina grundläggande kund uppgifter lagrade i andra Tyskland.</span><span class="sxs-lookup"><span data-stu-id="681e0-170">New Microsoft 365 customers with a German signup address associated with their tenant will have their core customer data stored at rest in Germany.</span></span> <span data-ttu-id="681e0-171">Vi planerar att bjuda in från Europa till Tyskland för tyska kunder i framtiden.</span><span class="sxs-lookup"><span data-stu-id="681e0-171">We plan to offer migration from Europe to Germany for German customers in the future.</span></span> <span data-ttu-id="681e0-172">Idag kan Microsoft Cloud Germany/Deutschland kunder begära migrering till Office 365-tjänster i de nya tyska Data Center-regionerna.</span><span class="sxs-lookup"><span data-stu-id="681e0-172">Today, Microsoft Cloud Germany/Deutschland customers can request migration to Office 365 services in the new German datacenter regions.</span></span> <span data-ttu-id="681e0-173">Mer information finns i [så här väljer du för migrering från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster](https://aka.ms/office365germanymoveoptin) .</span><span class="sxs-lookup"><span data-stu-id="681e0-173">Please see [How to opt-in for migration from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter regions](https://aka.ms/office365germanymoveoptin) for more information.</span></span>
>
  
<span data-ttu-id="681e0-174">En fullständig lista över alla data Center geos, data Center och plats för kunddata på rest är tillgängliga som en del av de [interaktiva Data Center-kartorna](https://office.com/datamaps).</span><span class="sxs-lookup"><span data-stu-id="681e0-174">A complete list of all datacenter geos, datacenters, and the location of customer data at rest is available as part of the [interactive datacenter maps](https://office.com/datamaps).</span></span> 
  
## <a name="data-residency-option"></a><span data-ttu-id="681e0-175">Alternativet de</span><span class="sxs-lookup"><span data-stu-id="681e0-175">Data residency option</span></span>

<span data-ttu-id="681e0-176">Vi tillhandahåller ett data de alternativ till befintliga Microsoft 365-kunder som omfattas av data Center geos som visas i tabellen ovan.</span><span class="sxs-lookup"><span data-stu-id="681e0-176">We provide a data residency option to existing Microsoft 365 customers who are covered by the datacenter geos listed in the table above.</span></span> <span data-ttu-id="681e0-177">Med det här alternativet kan kunder med data de-krav begära tidiga migration av organisationens viktigaste kund uppgifter till det nya data centret geo.</span><span class="sxs-lookup"><span data-stu-id="681e0-177">With this option, customers with data residency requirements can request early migration of their organization's core customer data at rest to their new datacenter geo.</span></span>  <span data-ttu-id="681e0-178">Microsoft kommer att erbjuda en tids gräns för alla berättigade kunder som kräver tidiga migration under registrerings fönstret.</span><span class="sxs-lookup"><span data-stu-id="681e0-178">Microsoft will offer a committed deadline to all eligible customers who request early migration during the enrollment window.</span></span>  <span data-ttu-id="681e0-179">Läs om [hur du kan begära en informations flyttnings](request-your-data-move.md) sida om du vill ha mer information om fönstret för din Geo och hur du kan registrera dig i programmet.</span><span class="sxs-lookup"><span data-stu-id="681e0-179">Review the [How to request your data move](request-your-data-move.md) page for more details about the enrollment window for your geo and the steps to enroll into the program.</span></span>  <span data-ttu-id="681e0-180">Data flyttningar kan ta upp till 24 månader efter en begäran om att slutföras.</span><span class="sxs-lookup"><span data-stu-id="681e0-180">Data moves can take up to 24 months after the request period to complete.</span></span>

<span data-ttu-id="681e0-181">Vi presenterar inga unika funktioner, funktioner och certifikat certifiering med det nya data centret geo.</span><span class="sxs-lookup"><span data-stu-id="681e0-181">We introduce no unique capabilities, features or compliance certifications with the new datacenter geo.</span></span>
    
<span data-ttu-id="681e0-182">Komplexiteten, precisionen och skalan där vi måste utföra data flyttningar inom en globalt styrd och automatiserad miljö hindrar oss från att dela när data flyttas för din klient organisation eller annan klient organisation.</span><span class="sxs-lookup"><span data-stu-id="681e0-182">The complexity, precision and scale at which we need to perform data moves within a globally operated and automated environment prohibit us from sharing when a data move is expected to complete for your tenant or any other single tenant.</span></span> <span data-ttu-id="681e0-183">Kunderna får en bekräftelse i meddelande Center per deltagande tjänst när dess data flyttas.</span><span class="sxs-lookup"><span data-stu-id="681e0-183">Customers will receive one confirmation in Message Center per participating service when its data move has completed.</span></span> 
    
<span data-ttu-id="681e0-184">Data flyttas är en backend-åtgärd som påverkar slutanvändaren minimalt.</span><span class="sxs-lookup"><span data-stu-id="681e0-184">Data moves are a back-end service operation with minimal impact to end-users.</span></span> <span data-ttu-id="681e0-185">Vilka funktioner som kan påverkas visas på [under och efter data flyttnings](during-and-after-your-data-move.md) sidan.</span><span class="sxs-lookup"><span data-stu-id="681e0-185">Features that can be impacted are listed on the [During and after your data move](during-and-after-your-data-move.md) page.</span></span> <span data-ttu-id="681e0-186">Vi följer [service nivå avtalet för Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så det finns inget som kunderna behöver för att förbereda för eller för att övervaka under flytten.</span><span class="sxs-lookup"><span data-stu-id="681e0-186">We adhere to the [Microsoft Online Services Service Level Agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) for availability so there is nothing that customers need to prepare for or to monitor during the move.</span></span> <span data-ttu-id="681e0-187">Meddelande om underhåll av tjänster görs vid behov.</span><span class="sxs-lookup"><span data-stu-id="681e0-187">Notification of any service maintenance is done if needed.</span></span> 

<span data-ttu-id="681e0-188">Data flyttas till den nya data Center geoen utan kostnad till kunden.</span><span class="sxs-lookup"><span data-stu-id="681e0-188">Data moves to the new datacenter geo are completed at no additional cost to the customer.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="681e0-189">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="681e0-189">Related topics</span></span> 
 
[<span data-ttu-id="681e0-190">Så här efterfrågar du data flytten</span><span class="sxs-lookup"><span data-stu-id="681e0-190">How to request your data move</span></span>](request-your-data-move.md)
    
[<span data-ttu-id="681e0-191">Vanliga frågor om data förflyttning</span><span class="sxs-lookup"><span data-stu-id="681e0-191">Data move general FAQ</span></span>](data-move-faq.md)
  
[<span data-ttu-id="681e0-192">Ny datacenter-geos för Microsoft Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="681e0-192">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[<span data-ttu-id="681e0-193">Azure-tjänster efter region</span><span class="sxs-lookup"><span data-stu-id="681e0-193">Azure services by region</span></span>](https://azure.microsoft.com/regions/)