---
title: 'Fas 1: nätverksinfrastruktur för Microsoft 365 Enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Steg för att distribuera nätverksinfrastrukturen för Microsoft 365 Enterprise.
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812568"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a><span data-ttu-id="4b26b-103">Fas 1: nätverksinfrastruktur för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b26b-103">Phase 1: Networking infrastructure for Microsoft 365 Enterprise</span></span>

![Fas 1: Nätverk](../media/deploy-foundation-infrastructure/networking_icon.png)

<span data-ttu-id="4b26b-105">Microsoft 365 Enterprise innehåller Office 365, Microsoft Intune och många identitets- och säkerhetstjänster i Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="4b26b-105">Microsoft 365 Enterprise includes Office 365, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="4b26b-106">Alla dessa molnbaserade tjänster kräver säkerhet, prestanda och tillförlitlighet för anslutningar från klientenheter via Internet eller dedikerade kretsar.</span><span class="sxs-lookup"><span data-stu-id="4b26b-106">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="4b26b-107">Om du vill ha de här tjänsterna och göra dem tillgängliga för kunder över hela världen har Microsoft utformat en nätverksinfrastruktur som betonar prestanda och integrering.</span><span class="sxs-lookup"><span data-stu-id="4b26b-107">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="4b26b-108">I det här steget ska du gå igenom de viktigaste aspekterna när du skapar en omfattande anslutning till molntjänsterna för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4b26b-108">In this phase, you step through the key considerations for creating a performant connection to the cloud services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="4b26b-109">En översikt finns i [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694) (Nätverksprinciper för Office 365).</span><span class="sxs-lookup"><span data-stu-id="4b26b-109">For an overview, see [Office 365 networking principles](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).</span></span>

>[!Note]
><span data-ttu-id="4b26b-110">Om du redan har distribuerat en nätverksinfrastruktur går du till [avslutsvillkoren](networking-exit-criteria.md) i den här fasen för att kontrollera att det uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4b26b-110">If you already have a networking infrastructure deployed, please see the [exit criteria](networking-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a><span data-ttu-id="4b26b-111">Planera och distribuera din nätverksinfrastruktur för Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b26b-111">Plan and deploy your Microsoft 365 Enterprise networking infrastructure</span></span> 

<span data-ttu-id="4b26b-112">Använd följande steg för att bygga ut nätverksinfrastrukturen för krav och funktioner i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4b26b-112">Use the following steps to build out your networking infrastructure for the requirements and capabilities of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="4b26b-114">Förbereda nätverket för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b26b-114">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
|![Steg 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="4b26b-116">Konfigurera lokala internetanslutningar för Office</span><span class="sxs-lookup"><span data-stu-id="4b26b-116">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|
|![Steg 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="4b26b-118">Undvika nätverkshairpins</span><span class="sxs-lookup"><span data-stu-id="4b26b-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
|![Steg 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="4b26b-120">Konfigurera förbikoppling av trafik</span><span class="sxs-lookup"><span data-stu-id="4b26b-120">Configure traffic bypass</span></span>](networking-configure-proxies-firewalls.md)|
|![Steg 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="4b26b-122">Optimera prestanda för klienten och Office 365-tjänsten</span><span class="sxs-lookup"><span data-stu-id="4b26b-122">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|


<span data-ttu-id="4b26b-123">När du har utfört de här stegen går du till [avslutsvillkoret](networking-exit-criteria.md) i den här fasen för att säkerställa att du uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4b26b-123">When you've completed these steps, go to the [exit criteria](networking-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="4b26b-124">Hur Microsoft gör Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b26b-124">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4b26b-125">Granska Microsoft och lär dig hur företaget [optimerade Microsoft-nätverket för molntjänster](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span><span class="sxs-lookup"><span data-stu-id="4b26b-125">Peek inside Microsoft and learn how the company [optimized the Microsoft network for cloud services](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="4b26b-126">Hur Contoso skapade Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4b26b-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4b26b-127">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [optimerade sina nätverksenheter och Internet-anslutningar](contoso-networking.md) för Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="4b26b-127">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4b26b-129">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4b26b-129">Next step</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="4b26b-131">Förbereda nätverket för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b26b-131">Prepare your network for Microsoft 365</span></span>](networking-provide-bandwidth-cloud-services.md)|
