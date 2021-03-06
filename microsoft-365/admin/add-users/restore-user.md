---
title: Återställa en användare
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
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Lär dig hur du återställer borttagna användar konton och alla associerade data.
ms.openlocfilehash: 7d7269ec338aafb9be317c2ee10a57d23c775c0a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551850"
---
# <a name="restore-a-user"></a>Återställa en användare

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
   
Om du återställer ett användarkonto inom 30 dagar från det att det togs bort, återställs kontot och alla associerade data. Användaren kan logga in med samma arbets- eller skolkonto. Postlådan återställs i sin helhet. Om du vill ta reda på hur mycket tid som återstår innan ett visst användarkonto inte längre kan återställas [kontaktar du oss](../contact-support-for-business-products.md).
  
Här är några tips:
  
- Kontrol lera att det finns licenser som kan kopplas till kontot.
    
- Om ditt företag använder Active Directory, se [Felsökning av borttagna konton i Office 365](https://support.microsoft.com/kb/2619308) för instruktioner om återställning av användarkonton. 
    
## <a name="restore-one-or-more-user-accounts"></a>Återställa ett eller flera användarkonton

Du måste vara 365 en global administratör eller administratör för användar hantering för att utföra de här stegen. 
  
 
::: moniker range="o365-worldwide"

1. Gå till sidan **användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna</a> användare i administrations centret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj **användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj **användare** \> **borttagna användare**.

::: moniker-end

2. På sidan **borttagna användare** väljer du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
 
3. Följ anvisningarna för att ange lösen ordet och välj sedan **Återställ**.
    
4. Om användaren återställs klickar du på **skicka e-post och Stäng**. Om det uppstår en namnkonflikt eller en proxyadresskonflikt kan du läsa instruktionerna nedan om återställning av dessa konton.
    
När du har återställt en användare ska du se till att deras lösen ord ändras och att du följer upp det.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Återställa en användare som har en användarnamnskonflikt
<a name="RestoreUserNameConflict"> </a>

En användarnamnskonflikt inträffar när du tar bort ett användarkonto, skapar ett nytt användarkonto med samma användarnamn (antingen för samma användare eller för en annan användare med ett liknande namn) och sedan försöker återställa det borttagna kontot.
  
Om du vill lösa detta ersätter du det aktiva användarkontot med det konto som du återställer. Eller tilldela det konto som du återställer ett annat användarnamn, så att inte båda kontona har samma användarnamn. Följ nedanstående anvisningar.
  

::: moniker range="o365-worldwide"

1. Gå till sidan **användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna</a> användare i administrations centret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj **användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj **användare** \> **borttagna användare**.

::: moniker-end

  
2. På sidan **borttagna användare** väljer du namnen på de användare som du vill återställa och väljer sedan **Återställ**.
    
    > [!NOTE]
    > Om återställandet av två eller fler användare misslyckas visas ett felmeddelande som informerar dig om att återställningsåtgärden misslyckades för vissa användare. Ta fram loggen och kontrollera vilka användare som inte återställdes. Dessa konton måste du återställa ett åt gången. 
  
3. Följ anvisningarna för att ange lösen ordet och välj **Återställ**.
    
4. Ett meddelande dyker upp där det står att det inte gick att återställa kontot. Gör något av följande:
    
  - Avbryt återställningen och byt namn på den aktiva användaren. Försök sedan återställa igen.
    
  - ELLER Skriv en ny primär e-postadress för användaren och välj **Återställ**.
    
5. Granska resultaten och välj sedan **Stäng**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Återställa en användare som har en proxyadresskonflikt

En proxyadresskonflikt inträffar när du tar bort ett användarkonto som innehåller en proxyadress, tilldelar ett annat konto samma proxyadress och sedan försöker återställa det borttagna kontot. Så här löser du problemet:
  
Du måste ha [Administratörs behörigheter](about-admin-roles.md) i Microsoft 365 för att göra detta. 
  

::: moniker range="o365-worldwide"

1. Gå till sidan **användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">borttagna</a> användare i administrations centret.

::: moniker-end

::: moniker range="o365-germany"

Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=848041)och välj **användare** \> **borttagna användare**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till [administrations centret](https://go.microsoft.com/fwlink/p/?linkid=850627)och välj **användare** \> **borttagna användare**.

::: moniker-end

2. Markera användaren som ska återställas på sidan **Borttagna användare** och välj sedan **Återställ**. 
    
3. Följ instruktionerna på sidan **Återställ** för att ange lösen ordet och välj **Återställ**. Proxyadresser med konflikter tas automatiskt bort från användaren som du återställer.
    
4. Granska resultaten och välj sedan **Stäng**.

## <a name="related-articles"></a>Relaterade artiklar

[Ta bort en användare](delete-a-user.md)
  
