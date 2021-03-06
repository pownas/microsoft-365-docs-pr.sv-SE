---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag så att de är redo för anställda.
ms.openlocfilehash: efcb5442b34d2d42275cedc30e71ac98c7ea1266
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401103"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler

Du kan använda Windows AutoPilot för att konfigurera **nya** Windows 10-enheter för ditt företag så att de är redo att användas när du ger dem till dina anställda.
  
## <a name="device-requirements"></a>Enhetskrav

Produkterna måste uppfylla dessa krav:
  
- Windows 10, version 1703 eller senare
    
- Nya enheter som inte har gått via Windows-direktupplevelse
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Använda installationsguiden för att skapa enheter och profiler

[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Om du inte har skapat enhetsgrupper eller profiler ännu är det bästa sättet att komma igång att komma igång med hjälp av steg-för-steg-guiden. Du kan också [lägga till enheter](create-and-edit-autopilot-devices.md) och tilldela [profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden. 
  
1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Välj **Autopilot för enheter** i det vänstra navigeringsfönstret \> **AutoPilot**.

    ![Välj enheter och sedan Autopilot i administrationscentret.](../media/AutoPilot.png)
  
2. Klicka eller tryck på **Startguide**på sidan **Autopilot** .
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Bläddra till en plats där du har förberett den förberedda på **sidan Ladda upp CSV med en lista över enheter.** CSV-fil och sedan **öppna** \> **nästa**. Filen måste ha tre rubriker:
    
    - Kolumn A: Enhetsserienummer
    
    - Kolumn B: Produkt-ID för Windows
    
    - Kolumn C: Maskinvaruhash
    
    Du kan hämta den här informationen från maskinvaruleverantören eller använda [Get-WindowsAutoPilotInfo PowerShell-skriptet](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil. 
    
    Mer information finns i [CSV-filen med enhetslistan](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**. 
    
4. På sidan **Tilldela en profil** kan du antingen välja en befintlig profil eller skapa en ny. Om du inte har en ännu uppmanas du att skapa en. 
    
    En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.
    
    Standardfunktionerna krävs och ställs in automatiskt. Standardfunktionerna är följande:
    
    - Hoppa över Cortana-, OneDrive- och OEM-registrering.
    
    - Skapa inloggning med företagets varumärke.
    
    - Anslut dina enheter till Azure Active Directory-konton och registrera dem automatiskt så att de kan hanteras av Microsoft 365 Business Premium.
    
    Mer information finns i [Om inställningar för profil för Autopilot](autopilot-profile-settings.md). 
    
5. Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard. 
    
    Välj **Nästa**.
    
6. **Du är klar** anger att profilen du skapade (eller valde) kommer att tillämpas på den enhetsgrupp som du skapade genom att ladda upp listan över enheter. Inställningarna gäller när enhetsanvändarna loggar in nästa gång. Välj **Stäng**.
    
