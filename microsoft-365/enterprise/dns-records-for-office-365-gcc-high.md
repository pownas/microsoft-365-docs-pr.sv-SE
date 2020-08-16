---
title: DNS-poster för Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Sammanfattning: DNS-poster för Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694522"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="23f66-103">DNS-poster för Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="23f66-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="23f66-104">*Den här artikeln gäller Office 365 GCC High och Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="23f66-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="23f66-105">När du hanterar Office 365-GCC hög måste du lägga till dina SMTP-och SIP-domäner i din Online Services-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="23f66-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="23f66-106">Du ska göra detta med den nya-MsolDomain cmdlet i Azure AD PowerShell eller använda [Azure stats Portal](https://portal.azure.us) för att börja lägga till domänen och bevisa ägarskap.</span><span class="sxs-lookup"><span data-stu-id="23f66-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="23f66-107">När du har lagt till dina domäner till klient organisationen och validerat kan du använda följande vägledning för att lägga till lämpliga DNS-poster för tjänsterna nedan.</span><span class="sxs-lookup"><span data-stu-id="23f66-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="23f66-108">Du kan behöva ändra tabellen nedan för att passa organisationens behov med avseende på den inkommande MX-posten (erna) och eventuella befintliga Exchange Autodiscover-poster.</span><span class="sxs-lookup"><span data-stu-id="23f66-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="23f66-109">Vi rekommenderar starkt att koordinera dessa DNS-poster med din meddelande grupp för att undvika avbrott eller problem med att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="23f66-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="23f66-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="23f66-110">Exchange Online</span></span>

| <span data-ttu-id="23f66-111">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="23f66-111">Type</span></span> | <span data-ttu-id="23f66-112">Ordningen</span><span class="sxs-lookup"><span data-stu-id="23f66-112">Priority</span></span> | <span data-ttu-id="23f66-113">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="23f66-113">Host name</span></span> | <span data-ttu-id="23f66-114">Pekar på adress eller värde</span><span class="sxs-lookup"><span data-stu-id="23f66-114">Points to address or value</span></span> | <span data-ttu-id="23f66-115">TTL</span><span class="sxs-lookup"><span data-stu-id="23f66-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="23f66-116">MX</span><span class="sxs-lookup"><span data-stu-id="23f66-116">MX</span></span> | <span data-ttu-id="23f66-117">siffrorna</span><span class="sxs-lookup"><span data-stu-id="23f66-117">0</span></span> | @ | <span data-ttu-id="23f66-118">*klient organisation*. mail.Protection.Office365.us (se nedan för mer information)</span><span class="sxs-lookup"><span data-stu-id="23f66-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="23f66-119">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-119">1 Hour</span></span> |
| <span data-ttu-id="23f66-120">TXT</span><span class="sxs-lookup"><span data-stu-id="23f66-120">TXT</span></span> | - | @ | <span data-ttu-id="23f66-121">v = spf1 inkluderar include SPF. Protection. Office365. USA-alla</span><span class="sxs-lookup"><span data-stu-id="23f66-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="23f66-122">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-122">1 Hour</span></span> |
| <span data-ttu-id="23f66-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="23f66-123">CNAME</span></span> | - | <span data-ttu-id="23f66-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="23f66-124">autodiscover</span></span> | <span data-ttu-id="23f66-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="23f66-125">autodiscover.office365.us</span></span> | <span data-ttu-id="23f66-126">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="23f66-127">Autodiscover-post för Exchange</span><span class="sxs-lookup"><span data-stu-id="23f66-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="23f66-128">Om du har en lokal Exchange-Server rekommenderar vi att du lämnar din befintliga post på plats medan du migrerar till Exchange Online och uppdaterar den posten när du har slutfört migreringen.</span><span class="sxs-lookup"><span data-stu-id="23f66-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="23f66-129">Exchange Online MX-post</span><span class="sxs-lookup"><span data-stu-id="23f66-129">Exchange Online MX Record</span></span>

<span data-ttu-id="23f66-130">MX-postens värde för godkända domäner följer ett standardformat enligt ovan: *klient organisation*. mail.Protection.Office365.us, vilket ersätter *klient organisationen* med den första delen av ditt standard klient namn.</span><span class="sxs-lookup"><span data-stu-id="23f66-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="23f66-131">Om klient namnet till exempel är contoso.onmicrosoft.us använder du **contoso.mail.Protection.Office365.us** som värde för MX-posten.</span><span class="sxs-lookup"><span data-stu-id="23f66-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="23f66-132">Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="23f66-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="23f66-133">CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="23f66-133">CNAME records</span></span>

| <span data-ttu-id="23f66-134">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="23f66-134">Type</span></span> | <span data-ttu-id="23f66-135">Värdnamn</span><span class="sxs-lookup"><span data-stu-id="23f66-135">Host name</span></span> | <span data-ttu-id="23f66-136">Pekar på adress eller värde</span><span class="sxs-lookup"><span data-stu-id="23f66-136">Points to address or value</span></span> | <span data-ttu-id="23f66-137">TTL</span><span class="sxs-lookup"><span data-stu-id="23f66-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="23f66-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="23f66-138">CNAME</span></span> | <span data-ttu-id="23f66-139">sip</span><span class="sxs-lookup"><span data-stu-id="23f66-139">sip</span></span> | <span data-ttu-id="23f66-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="23f66-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="23f66-141">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-141">1 Hour</span></span> |
| <span data-ttu-id="23f66-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="23f66-142">CNAME</span></span> | <span data-ttu-id="23f66-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="23f66-143">lyncdiscover</span></span> | <span data-ttu-id="23f66-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="23f66-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="23f66-145">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="23f66-146">SRV-poster</span><span class="sxs-lookup"><span data-stu-id="23f66-146">SRV records</span></span>

| <span data-ttu-id="23f66-147">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="23f66-147">Type</span></span> | <span data-ttu-id="23f66-148">Tjänst</span><span class="sxs-lookup"><span data-stu-id="23f66-148">Service</span></span> | <span data-ttu-id="23f66-149">Protokoll</span><span class="sxs-lookup"><span data-stu-id="23f66-149">Protocol</span></span> | <span data-ttu-id="23f66-150">Port</span><span class="sxs-lookup"><span data-stu-id="23f66-150">Port</span></span> | <span data-ttu-id="23f66-151">Väga</span><span class="sxs-lookup"><span data-stu-id="23f66-151">Weight</span></span> | <span data-ttu-id="23f66-152">Ordningen</span><span class="sxs-lookup"><span data-stu-id="23f66-152">Priority</span></span> | <span data-ttu-id="23f66-153">Namn</span><span class="sxs-lookup"><span data-stu-id="23f66-153">Name</span></span> | <span data-ttu-id="23f66-154">Mål</span><span class="sxs-lookup"><span data-stu-id="23f66-154">Target</span></span> | <span data-ttu-id="23f66-155">TTL</span><span class="sxs-lookup"><span data-stu-id="23f66-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="23f66-156">SRV</span><span class="sxs-lookup"><span data-stu-id="23f66-156">SRV</span></span> | <span data-ttu-id="23f66-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="23f66-157">\_sip</span></span> | <span data-ttu-id="23f66-158">\_Transmission</span><span class="sxs-lookup"><span data-stu-id="23f66-158">\_tls</span></span> | <span data-ttu-id="23f66-159">443</span><span class="sxs-lookup"><span data-stu-id="23f66-159">443</span></span> | <span data-ttu-id="23f66-160">9.1</span><span class="sxs-lookup"><span data-stu-id="23f66-160">1</span></span> | <span data-ttu-id="23f66-161">100</span><span class="sxs-lookup"><span data-stu-id="23f66-161">100</span></span> | @ | <span data-ttu-id="23f66-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="23f66-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="23f66-163">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-163">1 Hour</span></span> |
| <span data-ttu-id="23f66-164">SRV</span><span class="sxs-lookup"><span data-stu-id="23f66-164">SRV</span></span> | <span data-ttu-id="23f66-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="23f66-165">\_sipfederationtls</span></span> | <span data-ttu-id="23f66-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="23f66-166">\_tcp</span></span> | <span data-ttu-id="23f66-167">5061</span><span class="sxs-lookup"><span data-stu-id="23f66-167">5061</span></span> | <span data-ttu-id="23f66-168">9.1</span><span class="sxs-lookup"><span data-stu-id="23f66-168">1</span></span> | <span data-ttu-id="23f66-169">100</span><span class="sxs-lookup"><span data-stu-id="23f66-169">100</span></span> | @ | <span data-ttu-id="23f66-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="23f66-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="23f66-171">1 timme</span><span class="sxs-lookup"><span data-stu-id="23f66-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="23f66-172">Ytterligare DNS-poster</span><span class="sxs-lookup"><span data-stu-id="23f66-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23f66-173">Om du har en befintlig *msoid* CNAME-post i DNS-zonen måste du **ta bort** posten från DNS för närvarande.</span><span class="sxs-lookup"><span data-stu-id="23f66-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="23f66-174">Msoid-posten är inkompatibel med Microsoft 365 Enterprise *-appar (tidigare Office 365 ProPlus)* och hindrar aktiveringen från att lyckas.</span><span class="sxs-lookup"><span data-stu-id="23f66-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>