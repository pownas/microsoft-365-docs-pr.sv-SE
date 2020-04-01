---
title: Svara på ett komprometterat e-postkonto i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lär dig hur du känner igen och svarar på ett komprometterat e-postkonto i Office 365
ms.openlocfilehash: b19d48046834e3f1387490774babb40dcbd92acc
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812965"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="49d18-103">Svara på ett komprometterat e-postkonto i Office 365</span><span class="sxs-lookup"><span data-stu-id="49d18-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="49d18-104">**Sammanfattning** Lär dig hur du känner igen och svarar på ett komprometterat e-postkonto i Office 365.</span><span class="sxs-lookup"><span data-stu-id="49d18-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="49d18-105">Vad är ett komprometterat e-postkonto i Office 365?</span><span class="sxs-lookup"><span data-stu-id="49d18-105">What is a Compromised Email Account in Office 365?</span></span>

<span data-ttu-id="49d18-106">Åtkomst till Office 365-postlådor, data och andra tjänster styrs genom användningen av autentiseringsuppgifter, t. ex. ett användarnamn och lösenord eller en PIN-kod.</span><span class="sxs-lookup"><span data-stu-id="49d18-106">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="49d18-107">När någon annan än den avsedda användaren stjäl de här autentiseringsuppgifterna anses de stulna uppgifterna ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="49d18-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="49d18-108">Angriparen kan använda dem för att logga in som den ursprungliga användaren och utföra illegala åtgärder.</span><span class="sxs-lookup"><span data-stu-id="49d18-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="49d18-109">Med hjälp av de stulna autentiseringsuppgifterna kan angriparen komma åt användarens Office 365-postlåda, SharePoint-mappar eller filer i användarens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="49d18-109">Using the stolen credentials, the attacker can access the user's Office 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="49d18-110">En vanligt förekommande åtgärd är att angriparen skickar e-postmeddelanden i den ursprungliga användarens namn till mottagare både inom och utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="49d18-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="49d18-111">När angriparen skickar data via e-post till externa mottagare kallas det för dataexfiltrering.</span><span class="sxs-lookup"><span data-stu-id="49d18-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="49d18-112">Symptom hos ett komprometterat Office 365-e-postkonto</span><span class="sxs-lookup"><span data-stu-id="49d18-112">Symptoms of a Compromised Office 365 Email Account</span></span>

<span data-ttu-id="49d18-113">Användarna kan lägga märka till och rapportera ovanliga aktiviteter i sina Office 365-postlådor.</span><span class="sxs-lookup"><span data-stu-id="49d18-113">Users might notice and report unusual activity in their Office 365 mailboxes.</span></span> <span data-ttu-id="49d18-114">Här är några vanliga tecken:</span><span class="sxs-lookup"><span data-stu-id="49d18-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="49d18-115">Misstänkt aktivitet, t.ex. saknade eller borttagna e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="49d18-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="49d18-116">Andra användare kan få e-postmeddelanden från det skadade kontot utan att motsvarande e-postmeddelanden finns i mappen **Skickat** hos avsändaren.</span><span class="sxs-lookup"><span data-stu-id="49d18-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="49d18-117">Förekomsten av inkorgsregler som inte har skapats av den avsedda användaren eller administratören.</span><span class="sxs-lookup"><span data-stu-id="49d18-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="49d18-118">Reglerna kan automatiskt vidarebefordra e-postmeddelanden till okända adresser eller flytta dem till någon av mapparna **Anteckningar**, **Skräppost** eller **RSS-prenumerationer**.</span><span class="sxs-lookup"><span data-stu-id="49d18-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="49d18-119">Användarens visningsnamn kan ändras i den globala adresslistan.</span><span class="sxs-lookup"><span data-stu-id="49d18-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="49d18-120">Användarens postlåda hindras från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="49d18-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="49d18-121">Mapparna Skickat och Borttaget i Microsoft Outlook eller Outlook på webben (tidigare Outlook Web App) innehåller vanliga meddelanden för hackade konton, t. ex. ”Jag är fast i London, skicka pengar”.</span><span class="sxs-lookup"><span data-stu-id="49d18-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="49d18-122">Ovanliga profiländringar av t.ex. namn eller telefonnummer, eller uppdatering av postnumret.</span><span class="sxs-lookup"><span data-stu-id="49d18-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="49d18-123">Ovanliga ändringar av autentiseringsuppgifter, till exempel flera ändringar av lösenordet krävs.</span><span class="sxs-lookup"><span data-stu-id="49d18-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="49d18-124">Vidarebefordring av e-post har lagts till nyligen.</span><span class="sxs-lookup"><span data-stu-id="49d18-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="49d18-125">En ovanlig signatur har nyligen lagts till, t.ex. en förfalskad banksignatur eller en signatur för ett receptbelagt läkemedel.</span><span class="sxs-lookup"><span data-stu-id="49d18-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="49d18-126">Om en användare rapporterar något av ovanstående symptom bör du utföra ytterligare utredningar.</span><span class="sxs-lookup"><span data-stu-id="49d18-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="49d18-127">Säkerhets- och efterlevnadscenter för Microsoft 365 och Azure-portalen tillhandahåller verktyg som hjälper dig att undersöka aktiviteter hos ett användarkonto som du misstänker kan ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="49d18-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="49d18-128">**Enhetliga granskningsloggar i Säkerhets- och efterlevnadscenter i Office 365**: Granska alla aktiviteter för det misstänkta kontot genom att filtrera resultaten för datumintervallet från före den misstänkta aktiviteten till dagens datum.</span><span class="sxs-lookup"><span data-stu-id="49d18-128">**Office 365 Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="49d18-129">Filtrera inte på aktiviteterna under sökningen.</span><span class="sxs-lookup"><span data-stu-id="49d18-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="49d18-130">**Office 365-granskningsloggar för administratörer i EAC**: I Exchange Online kan du använda administrationscentret för Exchange (EAC) för att söka efter och visa poster i granskningsloggen för administratörer.</span><span class="sxs-lookup"><span data-stu-id="49d18-130">**Office 365 Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="49d18-131">I granskningsloggen för administratörer registreras vissa åtgärder baserat på Exchange Online PowerShell-cmdletar, utförda av administratörer och användare som har tilldelats administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="49d18-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="49d18-132">Poster i granskningsloggen för administratörer innehåller information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.</span><span class="sxs-lookup"><span data-stu-id="49d18-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="49d18-133">**Inloggningsloggar för Azure AD och andra riskrapporter på Azure AD-portalen**: Granska värdena i följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="49d18-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="49d18-134">Granska IP-adress</span><span class="sxs-lookup"><span data-stu-id="49d18-134">Review IP address</span></span>

  - <span data-ttu-id="49d18-135">inloggningsplatser</span><span class="sxs-lookup"><span data-stu-id="49d18-135">sign-in locations</span></span>

  - <span data-ttu-id="49d18-136">inloggningstider</span><span class="sxs-lookup"><span data-stu-id="49d18-136">sign-in times</span></span>

  - <span data-ttu-id="49d18-137">lyckad eller misslyckad inloggning</span><span class="sxs-lookup"><span data-stu-id="49d18-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="49d18-138">Så kan du skydda och återställa e-postfunktionen till ett konto eller en postlåda i Office 365 som misstänks ha komprometterats</span><span class="sxs-lookup"><span data-stu-id="49d18-138">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="49d18-139">Även efter att du har återskapat åtkomsten till ditt konto kan angriparen ha lagt till bakdörrsposter som gör det möjligt för angripare att återta kontrollen av kontot.</span><span class="sxs-lookup"><span data-stu-id="49d18-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="49d18-140">Du måste utföra alla följande steg för att återta åtkomsten till ditt konto så snabbt som möjligt, för att se till att kaparen inte återtar kontrollen av ditt konto.</span><span class="sxs-lookup"><span data-stu-id="49d18-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="49d18-141">De här åtgärderna hjälper dig att ta bort alla eventuella bakdörrsposter som kaparen kan ha lagt till på ditt konto.</span><span class="sxs-lookup"><span data-stu-id="49d18-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="49d18-142">När du har utfört de här stegen rekommenderar vi att du kör en viruskontroll för att se till att datorn inte är komprometterad.</span><span class="sxs-lookup"><span data-stu-id="49d18-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="49d18-143">Steg 1 Återställ användarens lösenord</span><span class="sxs-lookup"><span data-stu-id="49d18-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="49d18-144">Skicka inte det nya lösen ordet till den avsedda användaren via e-post, eftersom angriparen fortfarande har tillgång till postlådan.</span><span class="sxs-lookup"><span data-stu-id="49d18-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="49d18-145">Följ rutinerna i Återställa ett Office 365 Business-lösenord för någon annan i [Återställa Office 365 Business-lösenord](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="49d18-145">Follow the Reset an Office 365 business password for someone else procedures in [Reset Office 365 business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="49d18-146">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="49d18-146">**Notes**:</span></span>

- <span data-ttu-id="49d18-147">Kontrollera att lösenordet är starkt och att det innehåller gemener, versaler, minst en siffra och minst ett specialtecken.</span><span class="sxs-lookup"><span data-stu-id="49d18-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="49d18-148">Återanvänd aldrig något av ditt senaste fem lösenord.</span><span class="sxs-lookup"><span data-stu-id="49d18-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="49d18-149">Även om kravet för lösenordshistorik gör att du kan återanvända ett lösenord du använt nyligen bör du välja något som angriparen inte kan gissa.</span><span class="sxs-lookup"><span data-stu-id="49d18-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="49d18-150">Om din lokala identitet är federerad med Office 365 måste du ändra ditt lösenord lokalt, och därefter informera administratören om skadan.</span><span class="sxs-lookup"><span data-stu-id="49d18-150">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="49d18-151">Vi rekommenderar att du aktiverar multifaktorautentisering (MFA) för att förhindra kompromettering, i synnerhet för konton med administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="49d18-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="49d18-152">Du kan läsa mer om MFA [här](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="49d18-152">You can learn more about MFA [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="49d18-153">Steg 2 Ta bort misstänkta adresser för vidarebefordran av e-post</span><span class="sxs-lookup"><span data-stu-id="49d18-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="49d18-154">Öppna **administrationscentret för Microsoft 365 > Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="49d18-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="49d18-155">Leta reda på användarkontot i fråga och visa **E-postinställningar**.</span><span class="sxs-lookup"><span data-stu-id="49d18-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="49d18-156">Under **Vidarebefordran av e-post** klickar du på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="49d18-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="49d18-157">Ta bort eventuella misstänkta vidarebefordringsadresser.</span><span class="sxs-lookup"><span data-stu-id="49d18-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="49d18-158">Steg 3 Inaktivera alla misstänkta inkorgsregler</span><span class="sxs-lookup"><span data-stu-id="49d18-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="49d18-159">Logga in i användarens postlåda med hjälp av Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="49d18-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="49d18-160">Klicka på kugghjulsikonen och klicka på **E-post**.</span><span class="sxs-lookup"><span data-stu-id="49d18-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="49d18-161">Klicka på **Regler för inkorgen och rensning** och granska reglerna.</span><span class="sxs-lookup"><span data-stu-id="49d18-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="49d18-162">Inaktivera eller ta bort misstänkta regler.</span><span class="sxs-lookup"><span data-stu-id="49d18-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="49d18-163">Steg 4 Tillåt att användaren skickar e-post</span><span class="sxs-lookup"><span data-stu-id="49d18-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="49d18-164">Om den misstänkt komprometterade postlådan har använts på ett otillåtet sätt för att skicka skräppost, är det sannolikt att postlådan har hindrats från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="49d18-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="49d18-165">Om du vill tillåta att en postlåda skickar e-post igen följer du procedurerna i [Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="49d18-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="49d18-166">Steg 5 valfritt: Blockera inloggning på användarkontot</span><span class="sxs-lookup"><span data-stu-id="49d18-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49d18-167">Du kan blockera inloggning på det misstänkt komprometterade kontot tills du anser att det är säkert att aktivera åtkomst igen.</span><span class="sxs-lookup"><span data-stu-id="49d18-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="49d18-168">Gå till administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49d18-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="49d18-169">I administrationscentret för Microsoft 365 väljer du **Användare**.</span><span class="sxs-lookup"><span data-stu-id="49d18-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="49d18-170">Markera den anställda du vill blockera och välj sedan **Redigera** bredvid **Inloggningsstatus** i användarfönstret.</span><span class="sxs-lookup"><span data-stu-id="49d18-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="49d18-171">I fönstret **Inloggningsstatus** väljer du **Inloggning blockerad** och sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="49d18-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="49d18-172">I det nedre vänstra navigeringsfönstret i administrationscentret expanderar du **Administratörscentra** och väljer **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="49d18-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="49d18-173">I administrationscentret för Exchange går du till **Mottagare > Postlådor**.</span><span class="sxs-lookup"><span data-stu-id="49d18-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="49d18-174">Markera användaren och under **Mobila enheter** på sidan med användaregenskaper klickar du på **Inaktivera Exchange ActiveSync** och **Inaktivera OWA för enheter** och svarar **Ja** på båda.</span><span class="sxs-lookup"><span data-stu-id="49d18-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="49d18-175">Under **E-postanslutning** väljer du **Inaktivera** och svarar **Ja**.</span><span class="sxs-lookup"><span data-stu-id="49d18-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="49d18-176">Steg 6 valfritt: Ta bort det misstänkt komprometterade kontot från alla administrativa rollgrupper</span><span class="sxs-lookup"><span data-stu-id="49d18-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="49d18-177">Medlemskap i administratörsgruppen kan återställas när kontot har skyddats.</span><span class="sxs-lookup"><span data-stu-id="49d18-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="49d18-178">Logga in på administrationscentret för Microsoft 365 med ett globalt administratörskonto och öppna **Aktiva användare**.</span><span class="sxs-lookup"><span data-stu-id="49d18-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="49d18-179">Leta reda på det misstänkt komprometterade kontot och kontrollera manuellt om det finns några administrativa roller som tilldelats kontot.</span><span class="sxs-lookup"><span data-stu-id="49d18-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="49d18-180">Öppna **Säkerhets- och efterlevnadscenter**.</span><span class="sxs-lookup"><span data-stu-id="49d18-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="49d18-181">Klicka på **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="49d18-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="49d18-182">Granska rollgrupperna manuellt för att se om det misstänkt komprometterade kontot är medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="49d18-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="49d18-183">Om så är fallet:</span><span class="sxs-lookup"><span data-stu-id="49d18-183">If it is:</span></span>

   <span data-ttu-id="49d18-184">a.</span><span class="sxs-lookup"><span data-stu-id="49d18-184">a.</span></span> <span data-ttu-id="49d18-185">Klicka på rollgruppen och klicka på **Redigera rollgrupp**.</span><span class="sxs-lookup"><span data-stu-id="49d18-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="49d18-186">b.</span><span class="sxs-lookup"><span data-stu-id="49d18-186">b.</span></span> <span data-ttu-id="49d18-187">Klicka på **Välj medlemmar** och **Redigera** för att ta bort användaren från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="49d18-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="49d18-188">Öppna **administrationscentret för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="49d18-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="49d18-189">Klicka på **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="49d18-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="49d18-190">Granska rollgrupperna manuellt för att se om det misstänkt komprometterade kontot är medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="49d18-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="49d18-191">Om så är fallet:</span><span class="sxs-lookup"><span data-stu-id="49d18-191">If it is:</span></span>

   <span data-ttu-id="49d18-192">a.</span><span class="sxs-lookup"><span data-stu-id="49d18-192">a.</span></span> <span data-ttu-id="49d18-193">Klicka på rollgruppen och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="49d18-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="49d18-194">b.</span><span class="sxs-lookup"><span data-stu-id="49d18-194">b.</span></span> <span data-ttu-id="49d18-195">Klicka på avsnittet **Medlemmar** för att ta bort användaren från rollgruppen.</span><span class="sxs-lookup"><span data-stu-id="49d18-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="49d18-196">Steg 7 Valfritt: Ytterligare försiktighetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="49d18-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="49d18-197">Var noga med att verifiera dina skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="49d18-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="49d18-198">Du kanske måste meddela personer i din kontaktlista att ditt konto har komprometterats.</span><span class="sxs-lookup"><span data-stu-id="49d18-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="49d18-199">Angriparen kan ha bett om att få pengar genom så kallad förfalskning, t.ex. att du var fast i ett annat land och behövde pengar, eller så kan angriparen ha skickat ett virus för att kapa deras datorer.</span><span class="sxs-lookup"><span data-stu-id="49d18-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="49d18-200">Andra tjänster som har använt Exchange-kontot som ett alternativt e-postkonto kan ha komprometterats.</span><span class="sxs-lookup"><span data-stu-id="49d18-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="49d18-201">Utför först de här stegen för din Office 365-prenumeration och därefter för dina övriga konton.</span><span class="sxs-lookup"><span data-stu-id="49d18-201">First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="49d18-202">Kontrollera att din kontaktinformation, t. ex. telefonnummer och adresser, är korrekt.</span><span class="sxs-lookup"><span data-stu-id="49d18-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="49d18-203">Skydda Office 365 som en expert på cybersäkerhet</span><span class="sxs-lookup"><span data-stu-id="49d18-203">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="49d18-204">Din Office 365-prenumeration innehåller en kraftfull uppsättning säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.</span><span class="sxs-lookup"><span data-stu-id="49d18-204">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="49d18-205">Använd [Säkerhetsöversikt för Office 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Office 365-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="49d18-205">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="49d18-206">Uppgifter som ska utföras under de första 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="49d18-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="49d18-207">De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.</span><span class="sxs-lookup"><span data-stu-id="49d18-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="49d18-208">Uppgifter som ska utföras inom 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="49d18-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="49d18-209">De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.</span><span class="sxs-lookup"><span data-stu-id="49d18-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="49d18-210">Efter 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="49d18-210">Beyond 90 days.</span></span> <span data-ttu-id="49d18-211">De här förbättringarna uppnås under de första 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="49d18-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="49d18-212">Se även</span><span class="sxs-lookup"><span data-stu-id="49d18-212">See also</span></span>

- [<span data-ttu-id="49d18-213">Identifiera och reparera Outlook-regler och inmatningsattacker i anpassade formulär i Office 365</span><span class="sxs-lookup"><span data-stu-id="49d18-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="49d18-214">Klagomålscenter för brottslighet på Internet</span><span class="sxs-lookup"><span data-stu-id="49d18-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="49d18-215">Tillsynsmyndigheten för värdepapper – Bedrägerier genom nätfiske</span><span class="sxs-lookup"><span data-stu-id="49d18-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="49d18-216">Om du vill rapportera skräppost direkt till Microsoft och din administratör [använder du tillägget Rapportera meddelande](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="49d18-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>