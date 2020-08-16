---
title: Microsoft 365 SharePoint Online-data borttagning
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Lär dig hur data borttagning fungerar i SharePoint Online, till exempel var borttagna innehåll lagras och hur länge.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694751"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="1f3a1-103">SharePoint Online-Databorttagning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f3a1-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="1f3a1-104">SharePoint Online lagrar objekt som en upplagrad kod i program databaser.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="1f3a1-105">När en användare laddar upp en fil till SharePoint Online assembleras den och omvandlas till program kod och lagras i flera tabeller i flera databaser.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="1f3a1-106">I SharePoint Online delas allt innehåll som en kund uppladdning till i bitar, krypterat (kan med flera AES 256-bitars nycklar) och distribueras i data centret.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="1f3a1-107">Specifik information om delnings-och krypterings processen finns i [kryptering i Microsofts moln](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="1f3a1-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="1f3a1-108">I SharePoint Online bevaras objekt i 93 dagar från den tid du tar bort dem från den ursprungliga platsen.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="1f3a1-109">De stannar i webbplatsens pappers korg hela tiden, såvida inte någon tar bort dem från där eller tömmer pappers korgen.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="1f3a1-110">I så fall går objekten till pappers korgen för webbplats samlingen, där de kvarstår för resten av 93 dagar.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="1f3a1-111">Information om hur du återställer borttagna objekt finns i [återställa objekt i pappers korgen på en SharePoint-webbplats](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) och [återställa borttagna objekt från webbplats samlingens pappers korg](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span><span class="sxs-lookup"><span data-stu-id="1f3a1-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="1f3a1-112">Bevarande tiden för pappers korgen kan inte konfigureras i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="1f3a1-113">När du tar bort en webbplats samling tar du också bort hierarkin över webbplatser i samlingen och allt innehåll i dem:</span><span class="sxs-lookup"><span data-stu-id="1f3a1-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="1f3a1-114">Dokument och dokument bibliotek</span><span class="sxs-lookup"><span data-stu-id="1f3a1-114">Documents and document libraries</span></span>
- <span data-ttu-id="1f3a1-115">Listor och listdata</span><span class="sxs-lookup"><span data-stu-id="1f3a1-115">Lists and list data</span></span>
- <span data-ttu-id="1f3a1-116">Inställningar för webbplats konfiguration</span><span class="sxs-lookup"><span data-stu-id="1f3a1-116">Site configuration settings</span></span>
- <span data-ttu-id="1f3a1-117">Roll-och säkerhets information som är relaterad till webbplatsen eller dess under webbplatser</span><span class="sxs-lookup"><span data-stu-id="1f3a1-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="1f3a1-118">Under webbplatser till webbplatsen på den översta nivån, deras innehåll och användar information</span><span class="sxs-lookup"><span data-stu-id="1f3a1-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="1f3a1-119">Om du tar bort en webbplats samling av misstag kan den återställas av en global administratör eller en SharePoint-admin med administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="1f3a1-120">Borttagna webbplats samlingar behålls i 93 dagar.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="1f3a1-121">Efter 93 dagar raderas webbplatser och allt innehåll och inställningar permanent, inklusive listor, bibliotek, sidor och eventuella underwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="1f3a1-122">Borttagning av filer sker när en användare tar bort borttagna objekt från webbplats samlingens pappers korg när bevarande-och säkerhets kopierings perioden går ut, eller när en administratör raderar en webbplats samling med hjälp av [cmdleten Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="1f3a1-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="1f3a1-123">När en användare tar bort (permanent tar bort) innehåll från SharePoint Online tas alla krypterings nycklar för de borttagna bitarna bort.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="1f3a1-124">Blocken på de diskar som tidigare sparade de borttagna bitarna markeras som oanvända och tillgängliga för åter användning.</span><span class="sxs-lookup"><span data-stu-id="1f3a1-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>