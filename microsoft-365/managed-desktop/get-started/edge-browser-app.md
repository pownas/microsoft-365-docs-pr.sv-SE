---
title: Ny Microsoft Edge
description: ''
keywords: webbläsare, Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: d11fd8f29e3232472f9457ba1fc288a5084429e9
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936143"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="2d8ed-103">Ny Microsoft Edge-app</span><span class="sxs-lookup"><span data-stu-id="2d8ed-103">New Microsoft Edge app</span></span>

<span data-ttu-id="2d8ed-104">Den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/edge) ger prestanda i världsklass med mer sekretess, mer produktivitet och mer värde medan du surfar.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="2d8ed-105">Microsoft Managed Desktop erbjuder en offentlig förhandsversion av distributionen av den nya Edge-webbläsaren i din miljö.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="2d8ed-106">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="2d8ed-106">Initial deployment</span></span>

<span data-ttu-id="2d8ed-107">Om du vill migrera dina Microsoft Managed Desktop-enheter till den nya webbläsaren Microsoft Edge filar du en IT-supportbiljett via Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="2d8ed-108">Vi distribuerar Edge Stable-kanalen till testgruppen när du arkiverar biljetten och distribuerar den sedan i varje efterföljande distributionsgrupp var 24:e timme.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="2d8ed-109">Om du vill pausa distributionen sparar du en annan biljett där du ber operationerna att spärra.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="2d8ed-110">Uppdateringar av Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2d8ed-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="2d8ed-111">Microsoft Managed Desktop distribuerar den [stabila kanalen](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) för Microsoft Edge som uppdateras automatiskt ungefär var sjätte vecka.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="2d8ed-112">Uppdateringar på den stabila kanalen lanseras [successivt](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) av Microsoft Edge-produktgruppen för att säkerställa bästa möjliga upplevelse för kunderna.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="2d8ed-113">Microsoft Edge Beta-kanalen är inte tillgänglig för närvarande.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="2d8ed-114">Ändra inte Microsoft [Edge-uppdateringsprinciperna](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)för att säkerställa att Microsoft Edge uppdateras korrekt.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="2d8ed-115">Inställningar som hanteras av Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2d8ed-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="2d8ed-116">Microsoft Managed Desktop har skapat en standarduppsättning principer för Microsoft Edge för att skydda webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="2d8ed-117">Standardinställningarna för webbläsaren är följande:</span><span class="sxs-lookup"><span data-stu-id="2d8ed-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="2d8ed-118">Microsoft Edge-tillägg</span><span class="sxs-lookup"><span data-stu-id="2d8ed-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="2d8ed-119">Säkerhetsbaslinjen för Microsoft Edge på Microsoft Managed Desktop-enheter anger två principer för att inaktivera alla Chrome-tillägg och säkra slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="2d8ed-120">Information om hur du aktiverar och distribuerar tillägg i din miljö finns i Inställningar som du hanterar.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="2d8ed-121">Blockeringslista för tilläggsinstallation</span><span class="sxs-lookup"><span data-stu-id="2d8ed-121">Extension installation blocklist</span></span>
<span data-ttu-id="2d8ed-122">**Standardvärde:** Alla</span><span class="sxs-lookup"><span data-stu-id="2d8ed-122">**Default value:** All</span></span>

<span data-ttu-id="2d8ed-123">Microsoft Managed Desktop anger den här principen för att förhindra att Chrome-tillägg installeras på hanterade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="2d8ed-124">Det finns kända risker i kopplingen till modellen för kromtillägg, inklusive dataskydd, sekretess och andra risker som kan äventyra enheter.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-124">There are known risksassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="2d8ed-125">Tillåt inbyggda meddelandevärdar på användarnivå (installeras utan administratörsbehörighet)</span><span class="sxs-lookup"><span data-stu-id="2d8ed-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="2d8ed-126">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="2d8ed-126">**Default value:** Disabled</span></span>

<span data-ttu-id="2d8ed-127">Genom att inaktivera den här principen använder Microsoft Edge endast inbyggda meddelandevärdar som är installerade på systemnivå.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="2d8ed-128">Inbyggda meddelandevärdar är en del av Chrome-tillägg som gör det möjligt för webbläsaren att interagera med andra delar av användarens slutpunkt, vilket skapar en mängd olika säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="2d8ed-129">Ssl (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="2d8ed-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="2d8ed-130">Minsta SSL-version</span><span class="sxs-lookup"><span data-stu-id="2d8ed-130">Minimum SSL version</span></span>

<span data-ttu-id="2d8ed-131">**Standardvärde:** Minst TLS 1.2 stöds</span><span class="sxs-lookup"><span data-stu-id="2d8ed-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="2d8ed-132">Om du vill använda den mindre säkra TLS 1.1 kan du begära detta.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="2d8ed-133">Tillåter användare att gå vidare från SSL-varningssidan</span><span class="sxs-lookup"><span data-stu-id="2d8ed-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="2d8ed-134">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="2d8ed-134">**Default value:** Disabled</span></span>

<span data-ttu-id="2d8ed-135">Vi rekommenderar inte att du aktiverar den här inställningen eftersom den tillåter användare att besöka webbplatser med SSL-fel.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="2d8ed-136">Microsoft Defender Smart Skärm</span><span class="sxs-lookup"><span data-stu-id="2d8ed-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="2d8ed-137">Konfigurera Smartskärm för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d8ed-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="2d8ed-138">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="2d8ed-138">**Default value:** Enabled</span></span>

<span data-ttu-id="2d8ed-139">Aktiverad som standard för att skydda slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="2d8ed-140">Microsoft Defender SmartScreen uppmanas för webbplatser</span><span class="sxs-lookup"><span data-stu-id="2d8ed-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="2d8ed-141">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="2d8ed-141">**Default value:** Enabled</span></span>

<span data-ttu-id="2d8ed-142">Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det skulle göra det möjligt för användare att ignorera varningar och fortsätta till potentiellt skadliga webbplatser.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="2d8ed-143">Förhindra förbikoppling av Microsoft Defender SmartScreen-varningar om nedladdningar</span><span class="sxs-lookup"><span data-stu-id="2d8ed-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="2d8ed-144">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="2d8ed-144">**Default value:** Enabled</span></span>

<span data-ttu-id="2d8ed-145">Vi rekommenderar inte att du inaktiverar den här inställningen eftersom det skulle göra det möjligt för användare att ignorera varningar och slutföra overifierade nedladdningar.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="2d8ed-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="2d8ed-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="2d8ed-147">Standardinställning för Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="2d8ed-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="2d8ed-148">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="2d8ed-148">**Default value:** Disabled</span></span>

<span data-ttu-id="2d8ed-149">Vi rekommenderar inte att du använder Flash på grund av tillhörande säkerhetsrisker.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="2d8ed-150">Om du fortfarande har processer som är beroende av Flash, ställa in **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** politik för att aktivera Flash för webbplatser som behöver det.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="2d8ed-151">Om det inte går att underhålla en tillåten lista över webbplatser som ska användas i Flash lämnar du in en ändringsbegäran för att ändra värdet till **Klicka för att spela**, vilket gör att användarna kan välja när det är lämpligt att köra Flash.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-151">If can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="2d8ed-152">Lösenordshanterare</span><span class="sxs-lookup"><span data-stu-id="2d8ed-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="2d8ed-153">Aktivera spara lösenord till lösenordshanteraren</span><span class="sxs-lookup"><span data-stu-id="2d8ed-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="2d8ed-154">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="2d8ed-154">**Default value:** Disabled</span></span>

<span data-ttu-id="2d8ed-155">Vi rekommenderar inte att låta slutanvändare spara lösenord på sin enhet.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="2d8ed-156">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="2d8ed-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="2d8ed-157">Aktivera webbplatsisolering för varje plats</span><span class="sxs-lookup"><span data-stu-id="2d8ed-157">Enable site isolation for every site</span></span>

<span data-ttu-id="2d8ed-158">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="2d8ed-158">**Default value:** Enabled</span></span>

<span data-ttu-id="2d8ed-159">När den här principen är aktiverad kan användarna inte välja bort standardbeteendet där varje plats körs i sin egen process.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="2d8ed-160">Autentiseringsscheman som stöds</span><span class="sxs-lookup"><span data-stu-id="2d8ed-160">Supported authentication schemes</span></span>

<span data-ttu-id="2d8ed-161">**Standardvärde:** NTLM, Förhandla</span><span class="sxs-lookup"><span data-stu-id="2d8ed-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="2d8ed-162">Microsoft Managed Desktop stöder inte grundläggande autentiserings- eller sammanfattande autentiseringsscheman.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="2d8ed-163">Importera en annan webbläsares data och inställningar automatiskt vid första körningen</span><span class="sxs-lookup"><span data-stu-id="2d8ed-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="2d8ed-164">**Standardvärde:** Importera alla datatyper och inställningar som stöds automatiskt från standardwebbläsaren</span><span class="sxs-lookup"><span data-stu-id="2d8ed-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="2d8ed-165">När den här principen tillämpas hoppar första körningen över importavsnittet, vilket minimerar användarinteraktionen.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="2d8ed-166">Webbläsardata från äldre versioner av Microsoft Edge migreras alltid tyst vid den första körningen, oavsett den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="2d8ed-167">Inställningar som du hanterar</span><span class="sxs-lookup"><span data-stu-id="2d8ed-167">Settings you manage</span></span>

<span data-ttu-id="2d8ed-168">Du kan distribuera alla Microsft Edge-inställningar som inte tidigare beskrivits med hjälp av profilen Administrativa mallar i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-168">You can deploy any Microsft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="2d8ed-169">Mer information finns i [Konfigurera principinställningar för Microsoft Edge med Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="2d8ed-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="2d8ed-170">Om du vill utvärdera en princip som för närvarande inte ingår i Microsoft Edge Administrativa mallar i Intune kan du använda anpassade inställningar för Windows 10-enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="2d8ed-171">Aktivera specifika Chrome-tillägg</span><span class="sxs-lookup"><span data-stu-id="2d8ed-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="2d8ed-172">Den administrativa mallen erbjuder en inställning för att distribuera vissa Chrome-tillägg med Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="2d8ed-173">Du hittar den i **datorkonfiguration > Microsoft Edge >-tillägg > tillåt att specifika tillägg installeras**.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="2d8ed-174">Installera tillägg tyst</span><span class="sxs-lookup"><span data-stu-id="2d8ed-174">Install extensions silently</span></span>

<span data-ttu-id="2d8ed-175">Du kan också använda den administrativa mallen för att ange Microsoft Edge för att installera tillägg utan att varna användaren.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="2d8ed-176">Du hittar den i **datorkonfiguration > Microsoft Edge >-tillägg > Kontrollerar vilka tillägg som installeras tyst**.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="2d8ed-177">Andra gemensamma företagspolitiker</span><span class="sxs-lookup"><span data-stu-id="2d8ed-177">Other common enterprise policies</span></span>

<span data-ttu-id="2d8ed-178">Microsoft Edge erbjuder många ytterligare policyer.</span><span class="sxs-lookup"><span data-stu-id="2d8ed-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="2d8ed-179">Dessa är några av de vanligaste:</span><span class="sxs-lookup"><span data-stu-id="2d8ed-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="2d8ed-180">Konfigurera platser i företagswebbplatslistan och IE-läget</span><span class="sxs-lookup"><span data-stu-id="2d8ed-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="2d8ed-181">Konfigurera inställningar för start, startsida och ny fliksida</span><span class="sxs-lookup"><span data-stu-id="2d8ed-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="2d8ed-182">Konfigurera inställningen Surf spel</span><span class="sxs-lookup"><span data-stu-id="2d8ed-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="2d8ed-183">Konfigurera proxyserverinställningar</span><span class="sxs-lookup"><span data-stu-id="2d8ed-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)
