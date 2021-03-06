---
title: Skapa och redigera AutoPilot-profiler
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Lär dig att skapa en AutoPilot-profil och tillämpa den på en enhet, samt redigera eller ta bort en profil eller ta bort en profil från en enhet.
ms.openlocfilehash: e58418813ed0b4d23a5fa7e1d23aae33d8850e7f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400983"
---
# <a name="create-and-edit-autopilot-profiles"></a>Skapa och redigera AutoPilot-profiler

## <a name="create-a-profile"></a>Skapa en profil

En profil gäller för en enhet eller en grupp enheter.
  
1. I administrationscentret för Microsoft 365 väljer du **Devices** \> **Autopilot för**enheter .
  
2. På sidan **Autopilot** väljer du fliken **Profiler** \> **Skapa profil**.
    
3. På sidan **Skapa profil** anger du ett namn på profilen som hjälper dig att identifiera den, till exempel Marknadsföring. Aktivera den inställning du vill använda och välj sedan **Spara**. Mer information om profilerinställningar för Autopilot finns i [Om inställningar för autopilotprofil](autopilot-profile-settings.md).
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Använda profil på en enhet

När du har skapat en profil kan du använda den på en enhet eller en grupp enheter. Du kan välja en befintlig profil i [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) och använda den på nya enheter, eller ersätta en befintlig profil för en enhet eller grupp av enheter. 
  
1. På sidan för att **förbereda Windows** väljer du fliken **Enheter**. 
    
2. Markera kryssrutan bredvid ett enhetsnamn **Device** och välj en profil i listrutan **Tilldelad profil** \> **Spara**.
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Redigera eller ta bort en profil

När du har tilldelat en profil till en enhet kan du uppdatera den, även om du redan har gett enheten till en användare. När enheten ansluts till internet laddar den ned den senaste versionen av profilen under installationen. Om användaren återställer enheten till de förvalda inställningarna hämtar enheten på nytt de senaste uppdateringarna av profilen. 
  
### <a name="edit-a-profile"></a>Redigera en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Profiler**. 
    
2. Markera kryssrutan bredvid ett enhetsnamn och uppdatera någon av de tillgängliga inställningarna Spara på **profilpanelen** \> **Save**.
    
    Om du gör detta innan någon användare ansluter enheten till internet används profilen för installationen.
    
### <a name="delete-a-profile"></a>Radera en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Profiler**. 
    
2. Markera kryssrutan bredvid ett enhetsnamn och välj **Ta bort profil** Spara på **profilpanelen** \> **Save**.
    
    När du raderar en profil tas den bort från en enhet eller en grupp av enheter som den var tilldelad till.
    
### <a name="remove-a-profile"></a>Ta bort en profil

1. På sidan för att **förbereda Windows** väljer du fliken **Enheter**. 
    
2. Markera kryssrutan bredvid ett enhetsnamn **Device** och välj **Ingen** i listrutan **Tilldelad profil** \> **Spara**.
    
