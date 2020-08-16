---
title: Förbereda för Active Directory-synkronisering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Här beskrivs hur du förbereder användare till Microsoft 365 med hjälp av profilsynkronisering och de långsiktiga fördelarna med den här metoden.
ms.openlocfilehash: cf5afc05b8273974c069662c2b887092fdd20b96
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696701"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="72c94-103">Förbereda för Active Directory-synkronisering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72c94-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="72c94-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="72c94-104">*This article applies to both Microsoft 365 Enterprise and Microsoft 365 Enterprise.*</span></span>

<span data-ttu-id="72c94-105">Fördelarna med hybrid identitet och katalog synkronisering i din organisation inkluderar:</span><span class="sxs-lookup"><span data-stu-id="72c94-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>
  
- <span data-ttu-id="72c94-106">Reducera administrativa program i organisationen</span><span class="sxs-lookup"><span data-stu-id="72c94-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="72c94-107">Om du vill aktivera enkel inloggnings scenario</span><span class="sxs-lookup"><span data-stu-id="72c94-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="72c94-108">Automatisera konto ändringar i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="72c94-108">Automating account changes in Microsoft 365</span></span>
    
<span data-ttu-id="72c94-109">Mer information om fördelarna med att använda katalog synkronisering finns i [Översikt över katalog synkronisering]( https://go.microsoft.com/fwlink/p/?LinkId=525398) och [hybrid identitet för Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="72c94-109">For more information about the advantages of using directory synchronization, see [Directory synchronization roadmap]( https://go.microsoft.com/fwlink/p/?LinkId=525398) and [Hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="72c94-110">För att katalog synkroniseringen ska fungera måste planering och förberedelse för att säkerställa att Active Directory Domain Services (AD DS) synkroniseras med Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen med minst fel.</span><span class="sxs-lookup"><span data-stu-id="72c94-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription with a minimum of errors.</span></span> 

<span data-ttu-id="72c94-111">Följ de här stegen för bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="72c94-111">Follow these steps in order for the best results.</span></span>
  
## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="72c94-112">1. katalog rensnings uppgifter</span><span class="sxs-lookup"><span data-stu-id="72c94-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="72c94-113">Innan du synkroniserar AD DS till din Azure AD-klient organisation måste du rensa AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72c94-114">Om du inte utför AD DS-rensning innan du synkroniserar kan distributions processen vara en väsentlig negativ effekt.</span><span class="sxs-lookup"><span data-stu-id="72c94-114">If you don't perform AD DS cleanup before you synchronize, there can be a significant negative effect on the deployment process.</span></span> <span data-ttu-id="72c94-115">Det kan ta några dagar, eller till och med veckor, att gå igenom Active Directory-synkroniseringen, identifiera fel och synkronisera igen.</span><span class="sxs-lookup"><span data-stu-id="72c94-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span> 
  
<span data-ttu-id="72c94-116">I din AD DS utför du följande rensnings aktiviteter för varje användar konto som tilldelas en Microsoft 365-licens:</span><span class="sxs-lookup"><span data-stu-id="72c94-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>
  
1. <span data-ttu-id="72c94-117">Kontrol lera en giltig och unik e-postadress i **proxyAddresses** -attributet.</span><span class="sxs-lookup"><span data-stu-id="72c94-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span> 
  
2. <span data-ttu-id="72c94-118">Ta bort alla dubblettvärden i attributet **proxyAddresses** .</span><span class="sxs-lookup"><span data-stu-id="72c94-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span> 
    
3.  <span data-ttu-id="72c94-119">Kontrol lera om möjligt ett giltigt och unikt värde för attributet **userPrincipalName** i användarens **användar** objekt.</span><span class="sxs-lookup"><span data-stu-id="72c94-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="72c94-120">För att den bästa synkroniseringen ska fungera bör du kontrol lera att AD DS UPN stämmer överens med Azure AD-UPN.</span><span class="sxs-lookup"><span data-stu-id="72c94-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="72c94-121">Om en användare inte har ett värde för **userPrincipalName** -attributet måste **användarobjektet** innehålla ett giltigt och unikt värde för **sAMAccountName** -attributet.</span><span class="sxs-lookup"><span data-stu-id="72c94-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="72c94-122">Ta bort alla dubblettvärden i **userPrincipalName** -attributet.</span><span class="sxs-lookup"><span data-stu-id="72c94-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span> 
    
4. <span data-ttu-id="72c94-123">För optimal användning av den globala adress listan (GAL) kontrollerar du att informationen i följande attribut för AD DS-användarkontot är korrekt:</span><span class="sxs-lookup"><span data-stu-id="72c94-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>
    
  - <span data-ttu-id="72c94-124">givenName</span><span class="sxs-lookup"><span data-stu-id="72c94-124">givenName</span></span>
  - <span data-ttu-id="72c94-125">efter namn</span><span class="sxs-lookup"><span data-stu-id="72c94-125">surname</span></span>
  - <span data-ttu-id="72c94-126">displayName</span><span class="sxs-lookup"><span data-stu-id="72c94-126">displayName</span></span>
  - <span data-ttu-id="72c94-127">Befattning</span><span class="sxs-lookup"><span data-stu-id="72c94-127">Job Title</span></span>
  - <span data-ttu-id="72c94-128">Department</span><span class="sxs-lookup"><span data-stu-id="72c94-128">Department</span></span>
  - <span data-ttu-id="72c94-129">Office</span><span class="sxs-lookup"><span data-stu-id="72c94-129">Office</span></span>
  - <span data-ttu-id="72c94-130">Telefonnr till arbetet</span><span class="sxs-lookup"><span data-stu-id="72c94-130">Office Phone</span></span>
  - <span data-ttu-id="72c94-131">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="72c94-131">Mobile Phone</span></span>
  - <span data-ttu-id="72c94-132">Fax nummer</span><span class="sxs-lookup"><span data-stu-id="72c94-132">Fax Number</span></span>
  - <span data-ttu-id="72c94-133">Gatuadress</span><span class="sxs-lookup"><span data-stu-id="72c94-133">Street Address</span></span>
  - <span data-ttu-id="72c94-134">Ort</span><span class="sxs-lookup"><span data-stu-id="72c94-134">City</span></span>
  - <span data-ttu-id="72c94-135">Region</span><span class="sxs-lookup"><span data-stu-id="72c94-135">State or Province</span></span>
  - <span data-ttu-id="72c94-136">Post nummer</span><span class="sxs-lookup"><span data-stu-id="72c94-136">Zip or Postal Code</span></span>
  - <span data-ttu-id="72c94-137">Land eller region</span><span class="sxs-lookup"><span data-stu-id="72c94-137">Country or Region</span></span>
    
## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="72c94-138">2. katalog objekt och filförberedelse</span><span class="sxs-lookup"><span data-stu-id="72c94-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="72c94-139">Om du har gjort en katalog synkronisering mellan AD DS och Microsoft 365 måste dina AD DS-attribut vara korrekt för beredda.</span><span class="sxs-lookup"><span data-stu-id="72c94-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="72c94-140">Du måste till exempel se till att specifika tecken inte används i vissa attribut som synkroniseras med Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="72c94-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="72c94-141">Oväntade tecken gör inte att Active Directory-synkroniseringen Miss lyckas men en varning kan visas.</span><span class="sxs-lookup"><span data-stu-id="72c94-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="72c94-142">Ogiltiga tecken gör att synkroniseringen Miss lyckas.</span><span class="sxs-lookup"><span data-stu-id="72c94-142">Invalid characters will cause directory synchronization to fail.</span></span>
  
<span data-ttu-id="72c94-143">Katalog synkronisering fungerar också om vissa av dina AD DS-användare har en eller flera dubbletter.</span><span class="sxs-lookup"><span data-stu-id="72c94-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="72c94-144">Varje användare måste ha unika attribut.</span><span class="sxs-lookup"><span data-stu-id="72c94-144">Each user must have unique attributes.</span></span>
  
<span data-ttu-id="72c94-145">De attribut som du måste förbereda finns här:</span><span class="sxs-lookup"><span data-stu-id="72c94-145">The attributes that you need to prepare are listed here:</span></span>
  
- <span data-ttu-id="72c94-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="72c94-146">**displayName**</span></span>
    
  - <span data-ttu-id="72c94-147">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72c94-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="72c94-148">Om det finns ett objekt i användarobjektet måste det vara ett värde för det.</span><span class="sxs-lookup"><span data-stu-id="72c94-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="72c94-149">Attributet får inte vara tomt.</span><span class="sxs-lookup"><span data-stu-id="72c94-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="72c94-150">Maximalt antal tecken: 256</span><span class="sxs-lookup"><span data-stu-id="72c94-150">Maximum number of characters: 256</span></span>
    
- <span data-ttu-id="72c94-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="72c94-151">**givenName**</span></span>
    
  - <span data-ttu-id="72c94-152">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men Microsoft 365 behöver inte eller använda det.</span><span class="sxs-lookup"><span data-stu-id="72c94-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="72c94-153">Maximalt antal tecken: 64</span><span class="sxs-lookup"><span data-stu-id="72c94-153">Maximum number of characters: 64</span></span>
    
- <span data-ttu-id="72c94-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="72c94-154">**mail**</span></span>
    
  - <span data-ttu-id="72c94-155">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-155">The attribute value must be unique within the directory.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="72c94-156">Om det finns dubblettvärden synkroniseras den första användaren med värdet.</span><span class="sxs-lookup"><span data-stu-id="72c94-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="72c94-157">Efterföljande användare visas inte i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72c94-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="72c94-158">Du måste ändra värdet i Microsoft 365 eller ändra båda värdena i AD DS för att båda användarna ska visas i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72c94-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span> 
  
- <span data-ttu-id="72c94-159">**smek namn** (Exchange-alias)</span><span class="sxs-lookup"><span data-stu-id="72c94-159">**mailNickname** (Exchange alias)</span></span> 
    
  - <span data-ttu-id="72c94-160">Attributvärdet får inte börja med en punkt (.).</span><span class="sxs-lookup"><span data-stu-id="72c94-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="72c94-161">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-161">The attribute value must be unique within the directory.</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="72c94-162">Under streck ("_") i det synkroniserade namnet anger att det ursprungliga värdet för det här attributet innehåller ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="72c94-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="72c94-163">Mer information om det här attributet finns i [attribut för Exchange-alias](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="72c94-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps).</span></span>
    >
      
- <span data-ttu-id="72c94-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="72c94-164">**proxyAddresses**</span></span>
    
  - <span data-ttu-id="72c94-165">Attribut med flera värden</span><span class="sxs-lookup"><span data-stu-id="72c94-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="72c94-166">Maximalt antal tecken per värde: 256</span><span class="sxs-lookup"><span data-stu-id="72c94-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="72c94-167">Attributvärdet får inte innehålla blank steg.</span><span class="sxs-lookup"><span data-stu-id="72c94-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="72c94-168">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="72c94-169">Ogiltiga tecken: \< \> ();, [] "'</span><span class="sxs-lookup"><span data-stu-id="72c94-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>
    
    <span data-ttu-id="72c94-170">Observera att ogiltiga tecken gäller de tecken som följer efter typ avgränsaren och ":", till exempel att SMTP:User@contso.com är tillåtet, men SMTP:user:M@contoso.com inte är det.</span><span class="sxs-lookup"><span data-stu-id="72c94-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="72c94-171">Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="72c94-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="72c94-172">Om det finns dubbletter eller oönskade adresser, se hjälp avsnittet [ta bort dubbletter och oönskade proxyadresser i Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span><span class="sxs-lookup"><span data-stu-id="72c94-172">If duplicate or unwanted addresses exist, see the Help topic [Removing duplicate and unwanted proxy addresses in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span></span> 
  
- <span data-ttu-id="72c94-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="72c94-173">**sAMAccountName**</span></span>
    
  - <span data-ttu-id="72c94-174">Maximalt antal tecken: 20</span><span class="sxs-lookup"><span data-stu-id="72c94-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="72c94-175">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="72c94-176">Ogiltiga tecken: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="72c94-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="72c94-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="72c94-177">\* ']</span></span>
  - <span data-ttu-id="72c94-178">Om en användare har ett ogiltigt **sAMAccountName** -attribut men har ett giltigt **userPrincipalName** -attribut skapas användar kontot i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="72c94-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span> 
  - <span data-ttu-id="72c94-179">Om både **sAMAccountName** och **userPrincipalName** är ogiltiga måste du uppdatera AD DS **userPrincipalName** -attributet.</span><span class="sxs-lookup"><span data-stu-id="72c94-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span> 
    
- <span data-ttu-id="72c94-180">**SN** (efter namn)</span><span class="sxs-lookup"><span data-stu-id="72c94-180">**sn** (surname)</span></span> 
    
  - <span data-ttu-id="72c94-181">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men Microsoft 365 behöver inte eller använda det.</span><span class="sxs-lookup"><span data-stu-id="72c94-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
    
- <span data-ttu-id="72c94-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="72c94-182">**targetAddress**</span></span>
    
    <span data-ttu-id="72c94-183">Det krävs att attributet **targetAddress** (till exempel SMTP:Tom@contoso.com) som är ifyllt för användaren måste finnas med i Microsoft 365 gal.</span><span class="sxs-lookup"><span data-stu-id="72c94-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="72c94-184">I scenarier med överföring av meddelanden från tredje part måste detta kräva Microsoft 365-schema för AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="72c94-185">Med schema tillägget Microsoft 365 kan du också lägga till andra användbara attribut för att hantera Microsoft 365-objekt som är ifyllda med ett verktyg för katalogbläddring från AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="72c94-186">**MsExchHideFromAddressLists** -attributet för att hantera dolda post lådor eller distributions grupper läggs till exempel till.</span><span class="sxs-lookup"><span data-stu-id="72c94-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span> 
   
  - <span data-ttu-id="72c94-187">Maximalt antal tecken: 256</span><span class="sxs-lookup"><span data-stu-id="72c94-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="72c94-188">Attributvärdet får inte innehålla blank steg.</span><span class="sxs-lookup"><span data-stu-id="72c94-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="72c94-189">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="72c94-190">Ogiltiga tecken: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="72c94-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="72c94-191">Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="72c94-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
    
- <span data-ttu-id="72c94-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="72c94-192">**userPrincipalName**</span></span>
    
  - <span data-ttu-id="72c94-193">**UserPrincipalName** -attributet måste finnas i Internet-stilens inloggnings format där användar namnet följs av snabel-a (@) och ett domän namn: till exempel user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="72c94-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="72c94-194">Alla SMTP-adresser (Simple Mail Transport Protocol) ska överensstämma med e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="72c94-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="72c94-195">Det maximala antalet tecken för **userPrincipalName** -attributet är 113.</span><span class="sxs-lookup"><span data-stu-id="72c94-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="72c94-196">Ett visst antal tecken tillåts före och efter snabel-a (@) enligt följande:</span><span class="sxs-lookup"><span data-stu-id="72c94-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span> 
  - <span data-ttu-id="72c94-197">Maximalt antal tecken för det användar namn som ligger före at-tecknet (@): 64</span><span class="sxs-lookup"><span data-stu-id="72c94-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="72c94-198">Maximalt antal tecken för domän namnet efter snabel-a (@): 48</span><span class="sxs-lookup"><span data-stu-id="72c94-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="72c94-199">Ogiltiga tecken: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="72c94-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="72c94-200">{ } | \< \> ( ) ; : , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="72c94-200">{ } | \< \> ( ) ; : , [ ] " '</span></span>
  - <span data-ttu-id="72c94-201">En omljud är också ett ogiltigt tecken.</span><span class="sxs-lookup"><span data-stu-id="72c94-201">An umlaut is also an invalid character.</span></span>
  - <span data-ttu-id="72c94-202">Tecknet @ är obligatoriskt i varje **userPrincipalName** -värde.</span><span class="sxs-lookup"><span data-stu-id="72c94-202">The @ character is required in each **userPrincipalName** value.</span></span> 
  - <span data-ttu-id="72c94-203">Tecknet @ får inte vara det första tecknet i varje **userPrincipalName** -värde.</span><span class="sxs-lookup"><span data-stu-id="72c94-203">The @ character cannot be the first character in each **userPrincipalName** value.</span></span> 
  - <span data-ttu-id="72c94-204">Användar namnet får inte avslutas med en punkt (.), ett et-tecken ( &amp; ), ett blank steg eller ett snabel-a (@).</span><span class="sxs-lookup"><span data-stu-id="72c94-204">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="72c94-205">Användar namnet får inte innehålla blank steg.</span><span class="sxs-lookup"><span data-stu-id="72c94-205">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="72c94-206">Dirigerade domäner måste användas; lokala eller interna domäner kan till exempel inte användas.</span><span class="sxs-lookup"><span data-stu-id="72c94-206">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="72c94-207">Unicode omvandlas till understryknings tecken.</span><span class="sxs-lookup"><span data-stu-id="72c94-207">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="72c94-208">**userPrincipalName** får inte innehålla dubblettvärden i katalogen.</span><span class="sxs-lookup"><span data-stu-id="72c94-208">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span> 
    
## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="72c94-209">3. förbereda attributet userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="72c94-209">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="72c94-210">Active Directory är utformat för att tillåta slutanvändarna i din organisation att logga in på katalogen med antingen **sAMAccountName** eller **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="72c94-210">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="72c94-211">På liknande sätt kan slutanvändare logga in på Microsoft 365 med hjälp av användarens huvud namn (UPN) på sitt arbets-eller skol konto.</span><span class="sxs-lookup"><span data-stu-id="72c94-211">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="72c94-212">Med katalog-synkronisering görs ett försök att skapa nya användare i Azure Active Directory med samma UPN som finns i AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-212">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="72c94-213">UPN-filen är formaterad som en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="72c94-213">The UPN is formatted like an email address.</span></span> 

<span data-ttu-id="72c94-214">I Microsoft 365 är UPN det standardattribut som används för att skapa e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="72c94-214">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="72c94-215">Det är enkelt att få **userPrincipalName** (i AD DS och Azure AD) och den primära e-postadressen i **proxyAddresses** ange olika värden.</span><span class="sxs-lookup"><span data-stu-id="72c94-215">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="72c94-216">Om de har olika värden kan de vara förvirrande för administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="72c94-216">When they are set to different values, there can be confusion for administrators and end users.</span></span> 
  
<span data-ttu-id="72c94-217">Det bästa är att justera dessa attribut för att minska förvirring.</span><span class="sxs-lookup"><span data-stu-id="72c94-217">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="72c94-218">För att uppfylla kraven för enkel inloggning med AD FS (Active Directory Federation Services) 2,0 måste du se till att UPN i Azure Active Directory och AD DS matchar och använder ett giltigt domän namn område.</span><span class="sxs-lookup"><span data-stu-id="72c94-218">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>
  
## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="72c94-219">4. Lägg till ett alternativt UPN-suffix i AD DS</span><span class="sxs-lookup"><span data-stu-id="72c94-219">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="72c94-220">Du kan behöva lägga till ett alternativt UPN-suffix för att koppla användarens företags referenser till Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="72c94-220">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="72c94-221">Ett UPN-suffix är en del av ett UPN till höger om @-tecknet.</span><span class="sxs-lookup"><span data-stu-id="72c94-221">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="72c94-222">UPN-värden som används för enkel inloggning kan innehålla bokstäver, siffror, punkter, streck och under streck, men inga andra typer av tecken.</span><span class="sxs-lookup"><span data-stu-id="72c94-222">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>
  
<span data-ttu-id="72c94-223">Mer information om hur du lägger till ett alternativt UPN-suffix i Active Directory finns i [förbereda för]( https://go.microsoft.com/fwlink/p/?LinkId=525430)Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="72c94-223">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>
  
## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="72c94-224">5. matcha AD DS-UPN med Microsoft 365-UPN</span><span class="sxs-lookup"><span data-stu-id="72c94-224">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="72c94-225">Om du redan har konfigurerat profilsynkronisering kanske användarens UPN för Microsoft 365 inte stämmer överens med användarens AD DS-UPN som har definierats i din AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-225">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="72c94-226">Det här kan inträffa när en användare tilldelas en licens innan domänen verifierades.</span><span class="sxs-lookup"><span data-stu-id="72c94-226">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="72c94-227">Det här kan du lösa genom att använda [PowerShell för att korrigera dubblett-UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) för att uppdatera användarens UPN så att Microsoft 365 UPN matchar företagets användar namn och domän.</span><span class="sxs-lookup"><span data-stu-id="72c94-227">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="72c94-228">Om du uppdaterar UPN i AD DS och vill att det ska synkroniseras med Azure Active Directory-identiteten, måste du ta bort användarens licens i Microsoft 365 innan du utför ändringarna i AD DS.</span><span class="sxs-lookup"><span data-stu-id="72c94-228">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span> 
  
<span data-ttu-id="72c94-229">Se även [hur du förbereder en icke-dirigerbart domän (till exempel. lokal domän) för Active Directory-synkronisering](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="72c94-229">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="72c94-230">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="72c94-230">Next steps</span></span>

<span data-ttu-id="72c94-231">Om du har gjort steg 1 till 5 ovan läser du [Konfigurera katalog synkronisering](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="72c94-231">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>