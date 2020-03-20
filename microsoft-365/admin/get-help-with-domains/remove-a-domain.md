---
title: Ta bort en domän från Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Lär dig hur du tar bort en gammal domän från Office 365 och flyttar användare och grupper till en annan domän.
ms.openlocfilehash: efbd49daa28b5d15989e1531929cb2d9355aeb8f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857433"
---
# <a name="remove-a-domain-from-office-365"></a>Ta bort en domän från Office 365

Deltagare: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)
  
 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
Tar du bort en domän på grund av att du vill lägga till den i ett annat Office 365-abonnemang? Eller vill du avbryta din prenumeration? Du kan [ändra ditt abonnemang eller din prenumeration](../../commerce/subscriptions/switch-to-a-different-plan.md) eller [avbryta prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Steg 1: Flytta användare till en annan domän

#### <a name="move-users"></a>Flytta användare

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a>.

2. Välj **Aktiva användare** > **Active users**.

3. Markera rutorna bredvid namnen på alla användare som du vill flytta.

4. Välj **Fler alternativ** (**...**), högst upp på sidan och välj sedan Ändra **domäner**.

5. Välj en annan domän i fönstret **Ändra domäner.**

Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a>.  

2. Välj **Aktiva användare** > **Active users**.

3. Markera rutorna bredvid namnen på alla användare som du vill flytta.

4. Högst upp på sidan väljer du **Fler** > **redigera domäner**.

5. Välj en annan domän i fönstret **Redigera domäner.**
  
Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.  

2. Välj **Aktiva användare** > **Active users**.

3. Markera rutorna bredvid namnen på alla användare som du vill flytta.

4. Högst upp på sidan väljer du **Fler** > **redigera domäner**.

5. Välj en annan domän i fönstret **Redigera domäner.**
  
Du måste även göra detta för dig själv om du använder den domän som du vill ta bort. När du redigerar domänen för ditt konto måste du logga ut och logga in igen med den nya domänen du har valt.

::: moniker-end

#### <a name="move-yourself"></a>Flytta dig själv

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a>.

2. Gå till **Aktiva användare**för **användare** \> och välj ditt konto i listan.

3. På fliken **Konto** väljer du **Hantera användarnamn**och väljer sedan en annan domän.
  
4. Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.

5. Logga in med den nya domänen och samma lösenord.

Du kan också använda PowerShell för att flytta användare till en annan domän. Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information. Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-germany"

1. Gå till **Aktiva användare**för **användare** \> och välj ditt namn i listan.

2. Välj **Redigera i**avsnittet **Användarnamn/E-post** och välj sedan en annan domän.

3. Välj **Ange som primär** > **spara** > **stänga**.
  
4. Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.

5. Logga in med den nya domänen och samma lösenord.

Du kan också använda PowerShell för att flytta användare till en annan domän. Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information. Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till **Aktiva användare**för **användare** \> och välj ditt namn i listan.

2. Välj **Redigera i**avsnittet **Användarnamn/E-post** och välj sedan en annan domän.

3. Välj **Ange som primär** > **spara** > **stänga**.
  
4. Högst upp väljer du ditt kontonamn och väljer sedan **Logga ut**.

5. Logga in med den nya domänen och samma lösenord.

Du kan också använda PowerShell för att flytta användare till en annan domän. Se [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) för mer information. Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Steg 2: Flytta användare till en annan domän

::: moniker range="o365-worldwide"

1. Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupper</a> i administrationscentret.
  
2. Markera gruppnamnet och välj sedan **Redigera på**fliken **Allmänt** under **E-postadress.**

3. Använd listrutan för att välja en annan domän.

4. Välj **Spara**och **stäng**sedan . Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Grupper** > **grupper** i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a>

2. Markera gruppnamnet och välj sedan **Redigera bredvid** **Namn**.

3. Använd listrutan för att välja en annan domän.

4. Välj **Spara**och **stäng**sedan . Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Grupper** > **grupper** i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a>

2. Markera gruppnamnet och välj sedan **Redigera bredvid** **Namn**.

3. Använd listrutan för att välja en annan domän.

4. Välj **Spara**och **stäng**sedan . Upprepa proceduren för alla grupper eller distributionslistor som är kopplade till den domän som du försöker ta bort.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Steg 3: Ta bort den gamla domänen

::: moniker range="o365-worldwide"

1. Gå till sidan **Inställningar** \> domäner i <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">administrationscentret.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">administrationscentret.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sidan **Installationsdomäner** \> i <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">administrationscentret.</a>

::: moniker-end
  
2. På sidan **Domäner** väljer du den domän som du vill ta bort.

3. Välj **Ta bort**i den högra rutan.

4. Följ eventuella ytterligare uppmaningar och välj sedan **Stäng**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Hur länge dröjer det innan en domän tas bort?

Det kan ta så lite som 5 minuter för Office 365 att ta bort en domän om den inte refereras till på många ställen, till exempel säkerhetsgrupper, distributionslistor, användare och Office 365-grupper. Om det finns många referenser till domänen kan det ta flera timmar (ett dygn) innan domänen tas bort.
  
Om du har hundratals eller tusentals användare använder du PowerShell och letar upp alla användare och flyttar dem till en annan domän. Annars kan det hända att några användare missas i gränssnittet och när du sedan försöker ta bort domänen så går det inte och du kommer inte att veta varför. Mer information finns i [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Om du vill ange standarddomänen använder du [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Vill du ha mer hjälp?

::: moniker range="o365-worldwide"

> [!NOTE]
> Du kan inte ta bort domänen [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) från ditt konto.
  
Fungerar det fortfarande inte? Domänen kan behöva tas bort manuellt. [Ring oss](../contact-support-for-business-products.md) så kan vi hjälpa dig med det!
  
::: moniker-end

## <a name="related-articles"></a>Relaterade artiklar

[Vanliga frågor och svar om domäner](../setup/domains-faq.md)

[Få hjälp med Office 365-domäner](get-help-with-domains.yml)

[Byta till ett annat Office 365 för företag-abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Avbryt prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md)