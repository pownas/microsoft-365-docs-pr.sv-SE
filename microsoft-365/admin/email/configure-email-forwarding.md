---
title: Konfigurera vidarebefordran av e-post
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Konfigurera vidarebefordran av e-post till ett eller flera e-postkonton med Office365.
ms.openlocfilehash: 5bbb7d4fa122051725418153e43f40aec370de61
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580621"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Konfigurera vidarebefordran av e-post i Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Som administratör för en organisation kan du ha företags krav för att konfigurera e-postvidarekoppling för en användares post låda. Med vidarebefordran av e-post kan du vidarebefordra e-postmeddelanden som skickas till en användares brevlåda till en annan användares brevlåda i eller utanför organisationen.

> [!IMPORTANT]
> Du kan använda filter principer för utgående e-post för att styra automatisk vidarebefordran till externa mottagare. Mer information finns i [styra automatisk extern e-postvidarebefordran i Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Konfigurera vidarebefordran av e-post

Observera följande innan du konfigurerar e-postvidarebefordran:

- När du har konfigurerat e-postvidarekoppling vidarekopplas bara **nya** e-postmeddelanden som skickas till  *från*  -post lådan.

- För e-postvidarekoppling krävs det att  *from*  -kontot har en licens. Om du konfigurerar vidarebefordran av e-post eftersom användaren har lämnat organisationen är ett annat alternativ att [göra om postlådan till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md). På det sättet kan flera personer komma åt den. En delad postlåda kan dock inte vara större än 50 GB.

Du måste vara Exchange-administratör eller global administratör i Microsoft 365 för att utföra de här stegen. Mer information finns i avsnittet [om administratörs roller](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. Gå till sidan **användare** \> **[aktiva användare](https://go.microsoft.com/fwlink/p/?linkid=834822)** i administrations centret.

2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.

3. Välj **Hantera e-postvidarebefordran** på fliken **e-post** .

4. På sidan e-postchatt väljer du **vidarebefordra alla e-postmeddelanden som skickas till den här post lådan**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara ändringar**.

    **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.

5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **användare** \> **[aktiva användare](https://go.microsoft.com/fwlink/p/?linkid=847686)** i administrations centret.

2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.

3. Expandera **e-postinställningar** och välj sedan **Redigera** i avsnittet **e-postvidarebefordran** .

4. På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.

   **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.

5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **användare** \> **[aktiva användare](https://go.microsoft.com/fwlink/p/?linkid=850628)** i administrations centret.

2. Välj namnet på den användare vars e-postadress du vill vidarebefordra för att öppna egenskaps sidan.

3. Expandera **e-postinställningar** och välj sedan **Redigera** i avsnittet **e-postvidarebefordran** .

4. På sidan e-postvidarekoppling ställer du in på **på**, anger adressen för vidarebefordran och väljer om du vill behålla en kopia av vidarebefordrade e-postmeddelanden. Se till att en licens tilldelas till användarkontot om du inte ser det här alternativet. Välj **Spara**.

   **Om du vill vidarebefordra till flera e-postadresser** kan du be användaren att konfigurera en regel i Outlook så att den vidarebefordras till adresserna. Mer information finns i [använda regler för att automatiskt vidarebefordra meddelanden](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Du kan också [skapa en distributions grupp](../setup/create-distribution-lists.md)i administrations centret, [lägga till adresser i den](add-user-or-contact-to-distribution-list.md)och ställa in vidarebefordran så att den pekar på dl enligt instruktionerna i den här artikeln.

5. Ta inte bort kontot för den användare som skickar e-post som du vidarebefordrar eller tar bort sin licens!  Om du gör det stoppas e-postvidarekoppling.

::: moniker-end
