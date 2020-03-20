---
title: Minska spam-meddelanden i Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Lär dig de vanligaste sätten att minska spam- och skräppost-meddelanden i Office 365.
ms.openlocfilehash: 132c56d3faa0876cc6f7e7d42a433ae0a3a6a5d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809356"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a><span data-ttu-id="05e0d-103">Minska spam-meddelanden i Office 365</span><span class="sxs-lookup"><span data-stu-id="05e0d-103">How to reduce spam email in Office 365</span></span>

 <span data-ttu-id="05e0d-104">**Får du för mycket spam-meddelanden i Office 365? Gör så här.**</span><span class="sxs-lookup"><span data-stu-id="05e0d-104">**Are you getting too much spam in Office 365? Do this.**</span></span>

<span data-ttu-id="05e0d-105">Vi rekommenderar starkt att du rapporterar falskt negativa meddelanden genom [att använda tillägget Rapportera meddelanden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) för att förbättra våra filter.</span><span class="sxs-lookup"><span data-stu-id="05e0d-105">We strongly recommend that you report False Negative messages by [using the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters.</span></span> <span data-ttu-id="05e0d-106">Du kan också skicka meddelandet med hjälp av [Inlämningsutforskaren](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="05e0d-106">Additionally, you can submit the message using [Submissions Explorer](admin-submission.md).</span></span>

> [!TIP]
> <span data-ttu-id="05e0d-107">Om du tror att meddelandet är skräppost och det finns i mappen skräppost ska du inte vara något problem.</span><span class="sxs-lookup"><span data-stu-id="05e0d-107">If you think the message is junk and it is in the Junk Email folder, that should not be a problem.</span></span> <span data-ttu-id="05e0d-108">Om du inte vill att den ska visas alls i postlådan ska du ändra antispam-principen för att placera meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="05e0d-108">If you don't want to see it at all in the mailbox, you should change the antispam policy to quarantine the message.</span></span> <span data-ttu-id="05e0d-109">Mer information om att placera ett meddelande i karantän finns i [Placera e-postmeddelanden i karantän med Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="05e0d-109">More information on quarantining a message can be found in [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

## <a name="fixing-allowed-spam"></a><span data-ttu-id="05e0d-110">Åtgärda tillåten spam</span><span class="sxs-lookup"><span data-stu-id="05e0d-110">Fixing allowed spam</span></span>

<span data-ttu-id="05e0d-111">Vanligtvis ser vi att kunder får skräppost i sin inkorg på grund av felaktiga konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="05e0d-111">We often see that customers get junk mail into their inbox because of incorrect configurations.</span></span> <span data-ttu-id="05e0d-112">Den vanligaste är att konfigurera dina domäner i en regel för e-postflöde (kallas även för en transportregel) för att kringgå filter eller för att visa en lista över dina domäner i listan över tillåtna/säkra avsändare.</span><span class="sxs-lookup"><span data-stu-id="05e0d-112">The most common of which is configuring your domains in a mail flow rule (also known as a transport rule) to bypass filters or listing your domain(s) in the allowed/safe-senders list.</span></span> <span data-ttu-id="05e0d-113">Det är inte bra eftersom de här meddelandena hoppar över spam-filtrering och kunde ha fångats, så att skapa [betrodda avsändarlistor](create-safe-sender-lists-in-office-365.md) måste anses som en tillfällig lösning.</span><span class="sxs-lookup"><span data-stu-id="05e0d-113">This is not good because these messages skip spam filtering and could have otherwise been caught, so creation of [safe sender lists](create-safe-sender-lists-in-office-365.md) must be considered as a temporary solution.</span></span>

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a><span data-ttu-id="05e0d-114">Lösningar till andra vanliga orsaker till att få alltför mycket spam-meddelanden</span><span class="sxs-lookup"><span data-stu-id="05e0d-114">Solutions to other common causes of getting too much spam</span></span>

<span data-ttu-id="05e0d-115">För att skydda dig från att få för mycket spam-meddelanden kräver Exchange Online Protection (EOP) att administratörer slutför några uppgifter.</span><span class="sxs-lookup"><span data-stu-id="05e0d-115">In order to protect you from getting too much spam, Exchange Online Protection (EOP) requires that administrators complete a few tasks.</span></span> <span data-ttu-id="05e0d-116">Om du inte är administratör för din Office 365-klientorganisation och får för mycket spam-meddelanden kanske du vill arbeta tillsammans med din administratör på de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="05e0d-116">If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks.</span></span> <span data-ttu-id="05e0d-117">Annars kan du gå vidare till avsnittet användare.</span><span class="sxs-lookup"><span data-stu-id="05e0d-117">Otherwise, you can skip to the user section.</span></span>

### <a name="for-admins"></a><span data-ttu-id="05e0d-118">För administratörer</span><span class="sxs-lookup"><span data-stu-id="05e0d-118">For admins</span></span>

- <span data-ttu-id="05e0d-119">**Ange Office 365 för dina DNS-poster**: för att EOP ska tillhandahålla bästa skydd måste bytaren för e-post (MX) DNS-poster för alla domäner pekas på Office 365 och bara för Office 365.</span><span class="sxs-lookup"><span data-stu-id="05e0d-119">**Point your DNS records to Office 365**: In order for EOP to provide the best protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365.</span></span> <span data-ttu-id="05e0d-120">Se [Skapa DNS-poster för Office 365 när du hanterar dina DNS-poster](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span><span class="sxs-lookup"><span data-stu-id="05e0d-120">See [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>

- <span data-ttu-id="05e0d-121">**Aktivera skräppostregeln för alla postlådor**. Som standard är alternativet för spam-filtrering inställt på **flytta meddelandet till mappen skräppost**.</span><span class="sxs-lookup"><span data-stu-id="05e0d-121">**Enable the junk mail rule on all mailboxes** By default, the spam filtering action is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="05e0d-122">Om det här är den föredragna och aktuella principen för spam måste varje postlåda [också ha en regel för skräppost aktiverat](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span><span class="sxs-lookup"><span data-stu-id="05e0d-122">If this is the preferred and current spam policy action, then each mailbox [must also have the junk mail rule enabled](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span> <span data-ttu-id="05e0d-123">Om du vill kontrollera det kan du köra cmdleten **get-MailboxJunkEmailConfiguration** på en eller flera postlådor.</span><span class="sxs-lookup"><span data-stu-id="05e0d-123">To check, you can run the **Get-MailboxJunkEmailConfiguration** cmdlet on one or more mailboxes.</span></span> <span data-ttu-id="05e0d-124">Du kan till exempel kontrollera alla postlådor genom att köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="05e0d-124">For example, you might check all mailboxes by running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

  ```powershell
  Get-MailboxJunkEmailConfiguration -Identity * | Where {$_.Enabled -eq $false}
  ```

  <span data-ttu-id="05e0d-125">När du tittar på resultatet ska egenskapens värde för **Aktiverat** vara `True`.</span><span class="sxs-lookup"><span data-stu-id="05e0d-125">When viewing the output, the **Enabled** property value should be `True`.</span></span> <span data-ttu-id="05e0d-126">Om den är `False` kan du köra följande kommando för att ändra det:</span><span class="sxs-lookup"><span data-stu-id="05e0d-126">If it's `False`, you can run the following command to change it:</span></span>

  ```powershell
  Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true
  ```

- <span data-ttu-id="05e0d-127">**Skapa regler för e-postflöde i lokal Exchange Server**: om du använder Exchange Online Protection, men dina postlådor finns i den lokala Exchange-servern, måste du skapa ett par regler för e-postflöde i den lokala Exchange-servern.</span><span class="sxs-lookup"><span data-stu-id="05e0d-127">**Create mail flow rules in on-premises Exchange Server**: If you are using Exchange Online Protection, but your mailboxes are located in on-premises Exchange Server, then you will need to create a couple of mail flow rules in on-premises Exchange Server.</span></span> <span data-ttu-id="05e0d-128">Se [Anvisningarna för endast EOP](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).</span><span class="sxs-lookup"><span data-stu-id="05e0d-128">See the [instructions for EOP-only](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).</span></span>

- <span data-ttu-id="05e0d-129">**Markera massutskick-meddelanden som spam**: Massutskick-meddelanden är e-postmeddelanden som användare kan ha registrerat sig för, men som fortfarande kan vara oönskade.</span><span class="sxs-lookup"><span data-stu-id="05e0d-129">**Mark bulk email as spam**: Bulk email is email which users may have signed up for, but may still be undesirable.</span></span> <span data-ttu-id="05e0d-130">I meddelandehuvudet hittar du egenskapen BCL (Bulk Confidence Level) i rubriken X-Microsoft-Antispam.</span><span class="sxs-lookup"><span data-stu-id="05e0d-130">In the message header, find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header.</span></span> <span data-ttu-id="05e0d-131">Om värdet för BCL är mindre än tröskelvärdet som anges i spam-filtret vill du kanske justera tröskelvärdet så att den här typen av massutskicks-meddelanden markeras som spam-meddelanden i stället.</span><span class="sxs-lookup"><span data-stu-id="05e0d-131">If the BCL value is less than the threshold set in the spam filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam.</span></span> <span data-ttu-id="05e0d-132">Olika användare har olika toleranser och inställningar för [hur massutskick-meddelanden](https://docs.microsoft.com/office365/SecurityCompliance/bulk-complaint-level-values) hanteras.</span><span class="sxs-lookup"><span data-stu-id="05e0d-132">Different users have different tolerances and preferences for [how bulk email](https://docs.microsoft.com/office365/SecurityCompliance/bulk-complaint-level-values) is handled.</span></span> <span data-ttu-id="05e0d-133">Du kan skapa olika principer och regler för olika användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="05e0d-133">You can create different policies or rules for different user preferences.</span></span>

- <span data-ttu-id="05e0d-134">**Blockera omedelbart en avsändare**: i de fall där du vill blockera en avsändare direkt, kan du blockera med e-postadress, domän eller IP-adress.</span><span class="sxs-lookup"><span data-stu-id="05e0d-134">**Immediately block a sender**: In the case where you need to immediately block a sender, you can block by email address, domain, or IP address.</span></span> <span data-ttu-id="05e0d-135">Mer information finns i [Skapa listor för blockerade avsändare i Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="05e0d-135">See [Create block sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span> <span data-ttu-id="05e0d-136">En anmärkning i en lista tillåtna användare hos en slutanvändare kan åsidosätta ett blockering som anges av administratören.</span><span class="sxs-lookup"><span data-stu-id="05e0d-136">An entry in an end-user allow list can override a block set by the administrator.</span></span>

- <span data-ttu-id="05e0d-137">**Aktivera tillägget rapportera meddelande för användare**: Vi rekommenderar starkt att du [aktiverar tillägget rapportera meddelande för användare](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="05e0d-137">**Turn on the report message add-in for users**: We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md).</span></span>

- <span data-ttu-id="05e0d-138">**Använd [Inlämningsutforskare](admin-submission.md)**: administratörer kan nu skicka e-postmeddelanden med hjälp av fil- eller nätverksmeddelande-ID, URL:er och filer för genomsökning av Microsoft i Office 365.</span><span class="sxs-lookup"><span data-stu-id="05e0d-138">**Use [Submissions Explorer](admin-submission.md)**: Admins can now send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="05e0d-139">Som administratör kan du också visa feedback som dina användare skickar och använda alla mönster för att ändra inställningar som kan orsaka problem.</span><span class="sxs-lookup"><span data-stu-id="05e0d-139">As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>

- <span data-ttu-id="05e0d-140">**Aktivera [DKIM](use-dkim-to-validate-outbound-email.md)**: om du vill signera alla utgående meddelanden för att öka säkerheten i din domän och klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="05e0d-140">**Enable [DKIM](use-dkim-to-validate-outbound-email.md)**: to sign all your outbound messages to increase the security in your domain and tenant.</span></span>

  > [!TIP]
  > <span data-ttu-id="05e0d-141">När du har aktiverat DKIM måste du aktivera [DMARC](use-dkim-to-validate-outbound-email.md) eftersom den här posten kommer att verifiera om DKIM och SPF fungerar som de ska. Vanligtvis har falska e-postmeddelanden inte signaturen eftersom O365 hanterar din privata och offentliga symmetriska nyckel.</span><span class="sxs-lookup"><span data-stu-id="05e0d-141">After you enable DKIM you must enable [DMARC](use-dkim-to-validate-outbound-email.md) since this record will validate if DKIM and SPF are working correctly and, generally, spoofing emails don't have the signature, since O365 manages your private and public symmetric key.</span></span>

### <a name="for-users"></a><span data-ttu-id="05e0d-142">För användare</span><span class="sxs-lookup"><span data-stu-id="05e0d-142">For users</span></span>

- <span data-ttu-id="05e0d-143">**Aktivera regeln för skräppost och kontrollera listan Tillåt**. Kontrollera av att åtgärdsregeln för skräppost är aktiverad och att avsändaren eller avsändarens domän inte ställts in på att kringgås i din personliga lista över tillåtna.</span><span class="sxs-lookup"><span data-stu-id="05e0d-143">**Enable the junk mail rule and check your allow list** Check that the junk mail action rule is enabled and that the sender or sender's domain is not set to bypass in your personal allow list.</span></span> <span data-ttu-id="05e0d-144">Det bästa sättet att komma åt de här inställningarna är från [Blockera eller tillåt (inställningar för skräppost-meddelande)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46).</span><span class="sxs-lookup"><span data-stu-id="05e0d-144">The best way to access these settings is from [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46).</span></span> <span data-ttu-id="05e0d-145">Medan du är där kan du också välja att blockera avsändarens e-postadress eller domän.</span><span class="sxs-lookup"><span data-stu-id="05e0d-145">While you are there, you may also choose to block the sender's email address or domain.</span></span>

- <span data-ttu-id="05e0d-146">**Rapportera spam till Microsoft** anmäl spam-meddelanden till Microsoft genom att använda [använd tillägget Rapportera meddelanden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="05e0d-146">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

- <span data-ttu-id="05e0d-147">**Avbryta prenumerationen på massutskick-meddelande**. Om meddelandet är något som du har registrerat dig för (nyhetsbrev, produktmeddelanden osv.) och innehåller en länk för att avbryta prenumerationen från en tillförlitlig källa kan det vara bra att avbryta prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="05e0d-147">**Unsubscribe from bulk email** If the message was something that you signed up for (newsletters, product announcements, etc.) and contains an unsubscribe link from a reputable source, you may want to simply unsubscribe.</span></span> <span data-ttu-id="05e0d-148">Office 365 behandlar vanligtvis inte dessa meddelanden som spam.</span><span class="sxs-lookup"><span data-stu-id="05e0d-148">Office 365 does not typically treat these messages as spam.</span></span> <span data-ttu-id="05e0d-149">Du kan också välja att spärra avsändaren eller be administratören att göra en ändring som gör att alla massutskick-meddelanden behandlas som spam.</span><span class="sxs-lookup"><span data-stu-id="05e0d-149">You can also choose to block the sender, or ask your administrator to make a change that will cause all bulk mail to be treated as spam.</span></span>