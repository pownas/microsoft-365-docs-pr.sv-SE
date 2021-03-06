---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403419"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Felsöka AutoPilot-enhetsfel

## <a name="device-file-error-messages"></a>Felmeddelanden för enhetsfil

Här finns information om några av de fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium. 
  
|**Felkod**|**Åtgärdat för att försöka**|
|:-----|:-----|
|Ogiltig begärandetext  <br/> |Det här felet bör inträffa sällan, om du ser det här felet, försök åtgärden igen.  <br/> |
|Maskinvaruhhh-värdet för en enhet är inte korrekt.  <br/> |Om det här felet visas betyder det att värdet som du angav i CSV-filen för maskinvaruhhen för en enhet inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande händer, fråga maskinvaruleverantören om hjälp.  <br/> |
|Enhet som tilldelats en annan klient  <br/> |Om du ser det här felet betyder det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande händer, fråga maskinvaruleverantören om hjälp.  <br/> |
|CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel  <br/> |Om du ser det här felet betyder det att enheten du försöker registrera redan är registrerad av en annan organisation. Lös det här felet genom att be maskinvaruleverantören om hjälp.  <br/> |
|Den här enheten stöds inte för installation med autopilot  <br/> | Det här felet innebär att enheten inte uppfyller distributionskraven för Autopilot. Enheter måste uppfylla följande krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte har varit via Windows out-of-box-upplevelse.  <br/> |
|Enheten hittades inte  <br/> |Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation. Du kan åtgärda detta genom att be maskinvaruleverantören om hjälp.  <br/> |
