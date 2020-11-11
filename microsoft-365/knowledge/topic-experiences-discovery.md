---
title: 'Hantera din kunskaps Management Network (för hands version) '
description: Så här konfigurerar du kunskaps hantering.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 265816a8d3d04b8d10b529f1ea1a0b658aa2931d
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989033"
---
# <a name="manage-your-knowledge-management-network-preview"></a><span data-ttu-id="3b6f3-103">Hantera din kunskaps Management Network (för hands version)</span><span class="sxs-lookup"><span data-stu-id="3b6f3-103">Manage your knowledge management network (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="3b6f3-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="3b6f3-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="3b6f3-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="3b6f3-106">När du [har konfigurerat kunskaps hanteringen](set-up-topic-experiences.md)kan du när som helst göra ändringar i konfigurations inställningarna via administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-106">After you [set up knowledge management](set-up-topic-experiences.md), at any time afterwards an admin can make adjustments to your configuration settings through the Microsoft 365 admin center.</span></span>

<span data-ttu-id="3b6f3-107">Du kan till exempel behöva justera dina inställningar för något av följande:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-107">For example, you may need to adjust your settings for any of the following:</span></span>
- <span data-ttu-id="3b6f3-108">Lägga till nya SharePoint-källor i mina avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-108">Add new SharePoint sources to mine topics.</span></span>
- <span data-ttu-id="3b6f3-109">Ändra vilka användare som ska ha åtkomst till ämnen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-109">Change which users will have access to topics.</span></span>
- <span data-ttu-id="3b6f3-110">Ändra vilka användare som har behörighet att utföra uppgifter i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-110">Change which users have permissions to do tasks on the topic center.</span></span>
- <span data-ttu-id="3b6f3-111">Ändra namnet på ämnes Center</span><span class="sxs-lookup"><span data-stu-id="3b6f3-111">Change the name of your topic center</span></span>


## <a name="requirements"></a><span data-ttu-id="3b6f3-112">Krav</span><span class="sxs-lookup"><span data-stu-id="3b6f3-112">Requirements</span></span> 
<span data-ttu-id="3b6f3-113">Du måste ha global administratör eller administratörs behörighet för SharePoint för att kunna komma åt Microsoft 365 Admin Center och hantera organisationens kunskaps uppgifter.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-113">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and manage Organizational knowledge tasks.</span></span>


## <a name="to-access-knowledge-management-settings"></a><span data-ttu-id="3b6f3-114">Så här använder du inställningar för kunskaps hantering:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-114">To access knowledge management settings:</span></span>

1. <span data-ttu-id="3b6f3-115">I administrations centret för Microsoft 365 väljer du **Konfigurera** och sedan avsnittet **organisations** information.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-115">In the Microsoft 365 admin center, select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="3b6f3-116">I avsnittet **organisationsinformation** klickar du på **Anslut personer till kunskap**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-116">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![Koppla personer till kunskap](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="3b6f3-118">På sidan **Anslut personer till kunskap** väljer du **Hantera** för att öppna fönstret **kunskaps nätverks inställningar** .</span><span class="sxs-lookup"><span data-stu-id="3b6f3-118">On the **Connect people to knowledge** page, select **Manage** to open the **Knowledge network settings** pane.</span></span><br/>

    ![kunskap – nätverks inställningar](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a><span data-ttu-id="3b6f3-120">Ändra hur kunskaps nätverket hittar ämnen</span><span class="sxs-lookup"><span data-stu-id="3b6f3-120">Change how the knowledge network can find topics</span></span>

<span data-ttu-id="3b6f3-121">Välj fliken **identifiering** om du vill uppdatera dina val för avsnitts källor i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-121">Select the **Topic discovery** tab if you want to update your choices for  for SharePoint topic sources.</span></span> <span data-ttu-id="3b6f3-122">Med den här inställningen kan du välja vilka SharePoint-webbplatser i din klient organisation som ska crawlas och mined för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-122">This setting let you select the SharePoint sites in your tenant that will be crawled and mined for topics.</span></span>

1. <span data-ttu-id="3b6f3-123">På fliken **identifiering** , under **Välj SharePoint-ämnes källor** , väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-123">On the **Topic discovery** tab, under **Select SharePoint topic sources** , select **Edit**.</span></span>
2. <span data-ttu-id="3b6f3-124">På sidan **Select SharePoint topic sources** väljer du vilka SharePoint-webbplatser som ska crawlas som källor för dina ämnen under identifiering.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-124">On the **Select SharePoint topic sources** page, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="3b6f3-125">Detta inkluderar:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-125">This includes:</span></span></br>
    <span data-ttu-id="3b6f3-126">a.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-126">a.</span></span> <span data-ttu-id="3b6f3-127">**Alla webbplatser** : alla SharePoint-webbplatser i din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-127">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="3b6f3-128">Här fångar du aktuella och framtida webbplatser.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-128">This captures current and future sites.</span></span></br>
    <span data-ttu-id="3b6f3-129">b.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-129">b.</span></span> <span data-ttu-id="3b6f3-130">**Alla, förutom markerade webbplatser** : Skriv namnen på de webbplatser du vill undanta.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-130">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="3b6f3-131">Du kan också ladda upp en lista med webbplatser som du inte vill ska ingå i sökningen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-131">You can also upload a list of sites you want to opt out from discovery.</span></span> <span data-ttu-id="3b6f3-132">Webbplatser som skapats i framtiden kommer att inkluderas som källor för avsnitts identifiering.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-132">Sites created in the future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="3b6f3-133">c.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-133">c.</span></span> <span data-ttu-id="3b6f3-134">**Endast valda webbplatser** : Skriv in namnen på de webbplatser du vill ta med.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-134">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="3b6f3-135">Du kan också ladda upp en lista med webbplatser.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-135">You can also upload a list of sites.</span></span> <span data-ttu-id="3b6f3-136">Webbplatser som skapats i framtiden kommer inte att ingå som källor för identifiering av ämnen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-136">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![Välj hur du vill hitta ämnen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    <span data-ttu-id="3b6f3-138">Om du har ett antal webbplatser som du vill undanta (om du markerar **alla, förutom markerade webbplatser** ) eller inkludera (om du valde **endast markerade webbplatser** ) kan du välja att överföra en CSV-fil med webbplats namn och URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-138">If you have a number of sites that you want to exclude (if you select **All, except selected sites** ) or include (if you selected **Only selected sites** ), you can choose to upload a CSV file with the site names and URLs.</span></span> <span data-ttu-id="3b6f3-139">Du kan välja **Hämta webbplatsmall. csv** om du vill använda CSV-mallfilen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-139">You can select **Download site template .csv** if you want to use the CSV template file.</span></span>

3. <span data-ttu-id="3b6f3-140">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-140">Select **Save**.</span></span>

##  <a name="change-who-can-see-topics-in-your-organization"></a><span data-ttu-id="3b6f3-141">Ändra vem som kan se ämnen i din organisation</span><span class="sxs-lookup"><span data-stu-id="3b6f3-141">Change who can see topics in your organization</span></span>

<span data-ttu-id="3b6f3-142">Välj fliken **identifiering** om du vill uppdatera vem i organisationen kan se upptäckta avsnitt i Sök Resultat och när ämnen markeras i innehåll som SharePoint-sidor.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-142">Select the **Topic discovery** tab if you want to update who in your organization can see discovered topics in search results and when topics are highlighted in content like SharePoint pages.</span></span>

1. <span data-ttu-id="3b6f3-143">På fliken **identifiering** , under **vem kan se ämnen i kunskaps nätverket** , väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-143">On the **Topic discovery** tab, under **Who can see topics in the knowledge network** , select **Edit**.</span></span>
2. <span data-ttu-id="3b6f3-144">På sidan **vem kan se ämnen i kunskaps nätverk** väljer du vilka som kommer att ha till gång till ämnen, till exempel markerade ämnen, ämnes kort, ämnes svar i sökningar och avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-144">On the **Who can see topics in the knowledge network** page, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="3b6f3-145">Du kan välja:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-145">You can select:</span></span></br>
    <span data-ttu-id="3b6f3-146">a.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-146">a.</span></span> <span data-ttu-id="3b6f3-147">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-147">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="3b6f3-148">b.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-148">b.</span></span> <span data-ttu-id="3b6f3-149">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-149">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="3b6f3-150">c.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-150">c.</span></span> <span data-ttu-id="3b6f3-151">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-151">**No one**</span></span></br>

    ![Vilka som kan se ämnen](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. <span data-ttu-id="3b6f3-153">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-153">Select **Save**.</span></span>  
 
> [!Note] 
> <span data-ttu-id="3b6f3-154">Med den här inställningen kan du välja en användare i organisationen, men endast användare som har kunskaps hanterings licenser tilldelade till dem kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-154">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span>

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a><span data-ttu-id="3b6f3-155">Ändra vem som har behörighet att utföra uppgifter i ämnes centret</span><span class="sxs-lookup"><span data-stu-id="3b6f3-155">Change who has permissions to do tasks on the topic center</span></span>

<span data-ttu-id="3b6f3-156">Välj fliken **behörigheter för ämne** om du vill uppdatera vilka som har behörighet att göra följande på sidan avsnitts Center:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-156">Select the **Topic permissions** tab if you want to update who has permissions to do the following in the topic center page:</span></span>

- <span data-ttu-id="3b6f3-157">Vilka användare som kan skapa och redigera ämnen: skapa nya avsnitt som inte hittades under identifiering eller redigera befintliga avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-157">Which users can create and edit topics: Create new topics that were not found during discovery or edit existing topic page details.</span></span>
- <span data-ttu-id="3b6f3-158">Vilka användare som kan hantera ämnen: bekräfta eller avvisa upptäckta ämnen.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-158">Which users can manage topics: Confirm or reject discovered topics.</span></span>

<span data-ttu-id="3b6f3-159">Så här uppdaterar du vilka som har behörighet att skapa och redigera ämnen:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-159">To update who has permissions to create and edit topics:</span></span>

1. <span data-ttu-id="3b6f3-160">På fliken **behörigheter** under **vem kan skapa och redigera ämnen** väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-160">On the **Topic permissions** tab, under **Who can create and edit topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="3b6f3-161">På sidan **vem som kan skapa och redigera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-161">On the **Who can create and edit topics** page, you can select:</span></span></br>
    <span data-ttu-id="3b6f3-162">a.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-162">a.</span></span> <span data-ttu-id="3b6f3-163">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-163">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="3b6f3-164">b.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-164">b.</span></span> <span data-ttu-id="3b6f3-165">**Endast valda personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-165">**Only selected people or security groups**</span></span></br>

    ![Skapa och redigera ämnen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. <span data-ttu-id="3b6f3-167">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-167">Select **Save**.</span></span></br>

<span data-ttu-id="3b6f3-168">Så här uppdaterar du vilka som har behörighet att hantera ämnen:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-168">To update who has permissions to manage topics:</span></span>

1. <span data-ttu-id="3b6f3-169">Välj **Redigera** under **vilka kan hantera ämnen** på fliken **behörigheter** .</span><span class="sxs-lookup"><span data-stu-id="3b6f3-169">On the **Topic permissions** tab, under **Who can manage topics** , select **Edit**.</span></span></br>
2. <span data-ttu-id="3b6f3-170">På sidan **vem kan hantera ämnen** kan du välja:</span><span class="sxs-lookup"><span data-stu-id="3b6f3-170">On the **Who can manage topics** page, you can select:</span></span></br>
    <span data-ttu-id="3b6f3-171">a.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-171">a.</span></span> <span data-ttu-id="3b6f3-172">**Alla i organisationen**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="3b6f3-173">b.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-173">b.</span></span> <span data-ttu-id="3b6f3-174">**Markerade personer eller säkerhets grupper**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-174">**Selected people or security groups**</span></span></br>

    ![Hantera ämnen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. <span data-ttu-id="3b6f3-176">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-176">Select **Save**.</span></span></br>


##  <a name="update-your-topic-center-name"></a><span data-ttu-id="3b6f3-177">Uppdatera namnet på ämnes Center</span><span class="sxs-lookup"><span data-stu-id="3b6f3-177">Update your topic center name</span></span>

<span data-ttu-id="3b6f3-178">Välj fliken för **avsnitts Center** om du vill uppdatera namnet på ditt ämnes Center.</span><span class="sxs-lookup"><span data-stu-id="3b6f3-178">Select the **Topic center** tab if you want to update the name of your topic center.</span></span> 

1. <span data-ttu-id="3b6f3-179">Välj **Redigera** under **ämnes Center namn** på fliken **ämnes Center** .</span><span class="sxs-lookup"><span data-stu-id="3b6f3-179">On the **Topic center** tab, under **Topic center name** , select **Edit**.</span></span>
2. <span data-ttu-id="3b6f3-180">Skriv det nya namnet på ämnes centret i rutan **namn** på sidan **Redigera ämnes Center namn** .</span><span class="sxs-lookup"><span data-stu-id="3b6f3-180">On the **Edit topic center name** page, in the **Topic center name** box, type the new name for your topic center.</span></span>
3. <span data-ttu-id="3b6f3-181">Välj **Spara**</span><span class="sxs-lookup"><span data-stu-id="3b6f3-181">Select **Save**</span></span>

    ![Redigera namn på ämnes Center](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a><span data-ttu-id="3b6f3-183">Se även</span><span class="sxs-lookup"><span data-stu-id="3b6f3-183">See also</span></span>



  





