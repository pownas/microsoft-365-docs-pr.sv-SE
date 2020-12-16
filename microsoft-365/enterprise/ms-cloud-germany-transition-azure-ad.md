---
title: Ytterligare Azure Active Directory-information för migreringen från Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Sammanfattning: ytterligare Azure Active Directory-information när du flyttar från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster i det nya tyska data centret.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688838"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="17a36-103">Ytterligare Azure Active Directory-information för migreringen från Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="17a36-103">Additional Azure Active Directory information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="17a36-104">För att slutföra flytten från det tyska Azure-molnet till det offentliga Azure Cloud-molnet rekommenderar vi att du uppdaterar slut punkten för autentiseringscookien, Azure Active Directory (Azure AD) och MS Graph slut punkter för dina program uppdateras till de kommersiella molnen när OpenID Connect (OIDC)-slut punkten `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` börjar rapportera kommersiella moln slut punkter.</span><span class="sxs-lookup"><span data-stu-id="17a36-104">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="17a36-105">**När ska jag göra den här ändringen?**</span><span class="sxs-lookup"><span data-stu-id="17a36-105">**When should I make this change?**</span></span>

<span data-ttu-id="17a36-106">Du får ett meddelande i Azure/Office Portal när din klient organisation har migrerat från tyskt moln till det kommersiella molnet.</span><span class="sxs-lookup"><span data-stu-id="17a36-106">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="17a36-107">Det har gått 30 dagar efter att du har fått detta meddelande för att slutföra dessa uppdateringar, så att din app fortsätter att fungera för klient organisationer som migreras från Azure Germany-molnet till det offentliga Azure-molnet.</span><span class="sxs-lookup"><span data-stu-id="17a36-107">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="17a36-108">Det finns tre villkor för att du ska kunna uppdatera inloggnings myndigheten:</span><span class="sxs-lookup"><span data-stu-id="17a36-108">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="17a36-109">OIDC identifierings slut punkt för din klient organisation `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returnerar slut punkter för Azure AD Public-moln.</span><span class="sxs-lookup"><span data-stu-id="17a36-109">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="17a36-110">Om klient organisationen har kon figurer ATS för Federation uppdateras AD FS (Active Directory Federation Services) så att den synkroniseras med Azure AD Public.</span><span class="sxs-lookup"><span data-stu-id="17a36-110">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="17a36-111">Du kan följa anvisningarna för att uppdatera Azure AD Connect-inställningar för den här ändringen.</span><span class="sxs-lookup"><span data-stu-id="17a36-111">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="17a36-112">Resurs program som används av dina program ändras till att acceptera tokens som är signerade av både Azure AD Tyskland och Azure AD Public.</span><span class="sxs-lookup"><span data-stu-id="17a36-112">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="17a36-113">**Vilka program?**</span><span class="sxs-lookup"><span data-stu-id="17a36-113">**What kind of applications?**</span></span>

<span data-ttu-id="17a36-114">Ett program kan vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="17a36-114">An application could be any of the following:</span></span>

- [<span data-ttu-id="17a36-115">En enda sida (SPA)</span><span class="sxs-lookup"><span data-stu-id="17a36-115">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="17a36-116">Webb program som loggar in i användare</span><span class="sxs-lookup"><span data-stu-id="17a36-116">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="17a36-117">Webb program som anropar webb-API</span><span class="sxs-lookup"><span data-stu-id="17a36-117">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="17a36-118">Skyddad webb-API</span><span class="sxs-lookup"><span data-stu-id="17a36-118">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="17a36-119">Webb-API som anropar webb-API</span><span class="sxs-lookup"><span data-stu-id="17a36-119">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="17a36-120">Skriv bords program</span><span class="sxs-lookup"><span data-stu-id="17a36-120">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="17a36-121">Daemon-app</span><span class="sxs-lookup"><span data-stu-id="17a36-121">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="17a36-122">Mobilapp</span><span class="sxs-lookup"><span data-stu-id="17a36-122">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="17a36-123">När ett program växlar till att använda `login.microsoftonline.com` som auktoritet kommer tokens att signeras av den här nya myndigheten.</span><span class="sxs-lookup"><span data-stu-id="17a36-123">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="17a36-124">Om du har ett resurs program som andra appar ringer till måste du tillåta verifiering av lax-token.</span><span class="sxs-lookup"><span data-stu-id="17a36-124">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="17a36-125">Det innebär att din app måste tillåta att tokens som är signerade av både Azure AD Germany och offentliga Azure AD-molnen.</span><span class="sxs-lookup"><span data-stu-id="17a36-125">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="17a36-126">Denna lax krävs tills alla klient program som anropar tjänsten är fullständigt migrerade till det offentliga Azure AD-molnet.</span><span class="sxs-lookup"><span data-stu-id="17a36-126">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="17a36-127">Efter migrering måste resurs programmet bara acceptera tokens som är signerade av Azure AD Public Cloud.</span><span class="sxs-lookup"><span data-stu-id="17a36-127">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="17a36-128">**Vad behöver jag uppdatera?**</span><span class="sxs-lookup"><span data-stu-id="17a36-128">**What do I need to update?**</span></span>

1. <span data-ttu-id="17a36-129">Om du är värd för ett program i Azure Tyskland som används för att autentisera användare av Azure Tyskland eller Office 365 Germany kontrollerar du att `https://login.microsoftonline.com` används som auktoritet i verifierings kontexten.</span><span class="sxs-lookup"><span data-stu-id="17a36-129">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="17a36-130">Se kontext text för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="17a36-130">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="17a36-131">Detta gäller både för att verifiera program varan och för att verifiera alla API: er som ditt program kan anropa (det vill säga Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span><span class="sxs-lookup"><span data-stu-id="17a36-131">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="17a36-132">Uppdatera Azure AD Graph-slutpunkten så att den blir `https://graph.windows.net` .</span><span class="sxs-lookup"><span data-stu-id="17a36-132">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="17a36-133">Uppdatera slut punkten för MS Graph `https://graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="17a36-133">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="17a36-134">Uppdatera eventuella tyska moln slut punkter (till exempel dem för Exchange Online och SharePoint Online) som används av dina program för att vara de som tillhör det offentliga molnet.</span><span class="sxs-lookup"><span data-stu-id="17a36-134">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="17a36-135">Uppdatera miljöparametrar för att vara `AzurePublic` (i stället för `AzureGermany` ) i administrativa verktyg och skript för:</span><span class="sxs-lookup"><span data-stu-id="17a36-135">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="17a36-136">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="17a36-136">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [<span data-ttu-id="17a36-137">Azure AD PowerShell (MSOnline)</span><span class="sxs-lookup"><span data-stu-id="17a36-137">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [<span data-ttu-id="17a36-138">Azure AD PowerShell (AzureAD)</span><span class="sxs-lookup"><span data-stu-id="17a36-138">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [<span data-ttu-id="17a36-139">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="17a36-139">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
<span data-ttu-id="17a36-140">**Vad händer med program som jag publicerar?**</span><span class="sxs-lookup"><span data-stu-id="17a36-140">**What about applications that I publish?**</span></span>

<span data-ttu-id="17a36-141">Om du publicerar ett program som är tillgängligt för användare utanför din klient organisation kan du behöva ändra registreringen för att säkerställa kontinuitet.</span><span class="sxs-lookup"><span data-stu-id="17a36-141">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="17a36-142">Andra klient organisationer som använder programmet kan flyttas vid en annan tidpunkt än din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="17a36-142">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="17a36-143">Om du inte vill att de ska förlora åtkomsten till ditt program måste du godkänna att ditt program synkroniseras från Azure Tyskland till Azure Public.</span><span class="sxs-lookup"><span data-stu-id="17a36-143">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="17a36-144">Ytterligare överväganden</span><span class="sxs-lookup"><span data-stu-id="17a36-144">Additional considerations</span></span>

<span data-ttu-id="17a36-145">Här är några ytterligare saker du bör tänka på för Azure AD:</span><span class="sxs-lookup"><span data-stu-id="17a36-145">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="17a36-146">För federerad inloggningsautentisering:</span><span class="sxs-lookup"><span data-stu-id="17a36-146">For federated authentication:</span></span>

  - <span data-ttu-id="17a36-147">Du får inte skapa, befordra eller degradera en federerad domän när över gången till klient organisationen pågår.</span><span class="sxs-lookup"><span data-stu-id="17a36-147">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="17a36-148">När migreringen till Azure AD-tjänsten är slutförd (klient organisationen är fullständigt fullständig) kan du återuppta hanteringen av federerade domäner.</span><span class="sxs-lookup"><span data-stu-id="17a36-148">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="17a36-149">Om du använder federerad trafik med AD FS (Active Directory Federation Services) bör du inte göra ändringar i de certifikat utfärdare som används för all identifiering med din lokala Active Directory Domain Services (AD DS) under migreringen.</span><span class="sxs-lookup"><span data-stu-id="17a36-149">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="17a36-150">Ändring av utfärdares-URI: er leder till autentiserings fel för användare i domänen.</span><span class="sxs-lookup"><span data-stu-id="17a36-150">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="17a36-151">Utfärdares-URI: er kan ändras direkt i AD FS eller när en domän konverteras från hanterad till federerad och vice versa.</span><span class="sxs-lookup"><span data-stu-id="17a36-151">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="17a36-152">Microsoft rekommenderar att kunderna inte lägger till, tar bort eller konverterar en federerad domän i den Azure AD-klient som migreras.</span><span class="sxs-lookup"><span data-stu-id="17a36-152">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="17a36-153">Utfärdares-URI: er kan ändras när migreringen är fullständigt fullständig.</span><span class="sxs-lookup"><span data-stu-id="17a36-153">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="17a36-154">För nätverk:</span><span class="sxs-lookup"><span data-stu-id="17a36-154">For networking:</span></span>

  - <span data-ttu-id="17a36-155">Det går inte att skapa IPv6-namngivna nätverk i Azure-portalen `http://portal.microsoftazure.de/` .</span><span class="sxs-lookup"><span data-stu-id="17a36-155">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="17a36-156">Använd Azure-portalen för `https://portal.azure.com` att skapa nätverk med IPv6-namn.</span><span class="sxs-lookup"><span data-stu-id="17a36-156">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="17a36-157">Du kan inte skapa betrodda IP-adressintervall för tjänste inställningar för Azure Multi-Factorion (MFA) från Microsoft Cloud Deutschland-portalen.</span><span class="sxs-lookup"><span data-stu-id="17a36-157">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="17a36-158">Använd Azure AD-portalen för Office 365-tjänster för att skapa betrodda IP-adressintervall för Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="17a36-158">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="17a36-159">För villkorlig åtkomst:</span><span class="sxs-lookup"><span data-stu-id="17a36-159">For Conditional Access:</span></span> 

  - <span data-ttu-id="17a36-160">Principer för villkorsstyrd åtkomst med följande anslag-kontroller stöds inte förrän migreringen till Office 365-tjänster är slutförd (efter den [slutförda Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration-fasen):</span><span class="sxs-lookup"><span data-stu-id="17a36-160">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="17a36-161">Kräv kompatibel enhet</span><span class="sxs-lookup"><span data-stu-id="17a36-161">Require Compliant Device</span></span>
    - <span data-ttu-id="17a36-162">Kräv godkänt program</span><span class="sxs-lookup"><span data-stu-id="17a36-162">Require Approved App</span></span>
    - <span data-ttu-id="17a36-163">Kräv program skydds policy</span><span class="sxs-lookup"><span data-stu-id="17a36-163">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="17a36-164">Princip gränssnittet för villkorsstyrd åtkomst ger en falsk varning om säkerhets standarden aktive ras för klient organisationen även om den är inaktive rad och principer för villkorsstyrd åtkomst redan finns för klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="17a36-164">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="17a36-165">Du bör ignorera varningen eller använda Office 365-tjänst portalen för att hantera principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="17a36-165">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="17a36-166">Det går endast att använda Intune-slutpunkter för slut punkter efter att klient migreringen har slutförts, inklusive alla migreringar av kontors belastning.</span><span class="sxs-lookup"><span data-stu-id="17a36-166">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="17a36-167">Microsoft Cloud Deutschland användare som använder appen för mobilapp för MFA-begäranden se användarens ObjectId (ett GUID) i stället för användarens huvud namn (UPN) i Microsoft Authenticator-appen.</span><span class="sxs-lookup"><span data-stu-id="17a36-167">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="17a36-168">När migreringen av Azure AD-innehavaren är färdig och finns i Office 365-tjänsterna visas användarens UPN-värden.</span><span class="sxs-lookup"><span data-stu-id="17a36-168">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="17a36-169">Befintliga Microsoft Authenticator-konton kommer att fortsätta att Visa användaren ObjectId, men de fortsätter att arbeta med aviseringar om mobila appar.</span><span class="sxs-lookup"><span data-stu-id="17a36-169">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="17a36-170">För klient organisationer som skapas efter 22 oktober 2019 kan säkerhets standarden aktive ras automatiskt för klient organisationen när den migreras till Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="17a36-170">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="17a36-171">Klient organisationens administratörer kan välja att lämna säkerhets standarder aktiverat och registrera sig för MFA, eller så kan de inaktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="17a36-171">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="17a36-172">Mer information finns i [inaktivera säkerhets inställningar](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="17a36-172">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="17a36-173">Organisationer som inte är automatiskt aktiverade under migreringen kan ändå vara automatiskt uppdelade när funktionen för att aktivera säkerhets standarder är uppkopplad i Office 365-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="17a36-173">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="17a36-174">Administratörer som uttryckligen väljer att inaktivera eller aktivera säkerhets standarder kan göra det genom att uppdatera funktionen under **Azure Active Directory >-egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="17a36-174">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="17a36-175">När funktionen är aktive rad av administratören aktive ras den inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="17a36-175">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="17a36-176">Det visas ett varnings meddelande om versionen av Azure AD Connect på Office 365 Germany-portalen samt på Office 365-portalen när klient organisationen migreras.</span><span class="sxs-lookup"><span data-stu-id="17a36-176">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="17a36-177">Det här kan ignoreras om varningen inte längre visas när migreringen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="17a36-177">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="17a36-178">Om det finns en varning, antingen före eller efter migreringen, måste du uppdatera Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="17a36-178">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="17a36-179">Varnings meddelandet visar att du använder ett föråldrat katalog-Sync-verktyg.</span><span class="sxs-lookup"><span data-stu-id="17a36-179">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="17a36-180">Vi rekommenderar att du går till Microsoft Download Center och skaffar den senaste versionen av Azure AD Connect. "</span><span class="sxs-lookup"><span data-stu-id="17a36-180">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="more-information"></a><span data-ttu-id="17a36-181">Mer information</span><span class="sxs-lookup"><span data-stu-id="17a36-181">More information</span></span>

<span data-ttu-id="17a36-182">Komma igång:</span><span class="sxs-lookup"><span data-stu-id="17a36-182">Getting started:</span></span>

- [<span data-ttu-id="17a36-183">Migrering från Microsoft Cloud Deutschland till Office 365-tjänster i de nya tyska Data Center-regionerna</span><span class="sxs-lookup"><span data-stu-id="17a36-183">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="17a36-184">Hjälp för Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="17a36-184">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="17a36-185">Så här väljer du för migrering</span><span class="sxs-lookup"><span data-stu-id="17a36-185">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="17a36-186">Kund upplevelse under migreringen</span><span class="sxs-lookup"><span data-stu-id="17a36-186">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="17a36-187">Flytta genom över gången:</span><span class="sxs-lookup"><span data-stu-id="17a36-187">Moving through the transition:</span></span>

- [<span data-ttu-id="17a36-188">Åtgärder och påverkan i migreringsfaser</span><span class="sxs-lookup"><span data-stu-id="17a36-188">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="17a36-189">Övrig för hands arbete</span><span class="sxs-lookup"><span data-stu-id="17a36-189">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="17a36-190">Ytterligare information för [Azure AD](ms-cloud-germany-transition-azure-ad.md), [enheter](ms-cloud-germany-transition-add-devices.md), [upplevelser](ms-cloud-germany-transition-add-experience.md)och [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="17a36-190">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="17a36-191">Molnappar:</span><span class="sxs-lookup"><span data-stu-id="17a36-191">Cloud apps:</span></span>

- [<span data-ttu-id="17a36-192">Information om programmet för Dynamics 365 migration</span><span class="sxs-lookup"><span data-stu-id="17a36-192">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="17a36-193">Information om datamigreringshanteraren för Power BI</span><span class="sxs-lookup"><span data-stu-id="17a36-193">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="17a36-194">Komma igång med din uppgradering av Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17a36-194">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)