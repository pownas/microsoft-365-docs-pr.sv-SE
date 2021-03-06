---
title: Felsöka problem med Microsoft 365 Defender-tjänsten
description: Hitta lösningar och Undvik kända problem med Microsoft 365 Defender
keywords: felsöka Microsoft Threat Protection, felsöka, Azure ATP, problem, tillägg, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844674"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Felsöka problem med Microsoft 365 Defender-tjänsten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

I det här avsnittet åtgärdas problem som kan uppstå när du använder Microsoft 365 Defender-tjänsten.


## <a name="i-dont-see-microsoft-365-defender-content"></a>Jag ser inte Microsoft 365 Defender-innehåll
Om du inte ser funktionerna i navigerings fönstret, till exempel händelser, åtgärds Center eller jakt på din portal, måste du verifiera att klient organisationen har rätt licenser. 

För mer information, se [förutsättningar](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender för identitets varningar visas inte i Microsoft 365 Defender-incidenterna
Om du har Microsoft Defender för en identitet distribuerad i din miljö men inte ser Defender för identitets aviseringar som en del av Microsoft 365 Defender-incidenter måste du kontrol lera att Microsoft Cloud App Security och Defender för identitets integrering är aktiverat. 

Mer information finns i [Microsoft Defender för identitets integrering](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Var är inställnings sidan för att aktivera tjänsten?
Om du vill aktivera Microsoft 365 Defender öppnar du **Inställningar** från navigerings fönstret i Microsoft 365 säkerhets Center. Det här navigerings objektet visas bara om du har [behörighet och licenser för nödvändig](mtp-enable.md#check-license-eligibility-and-required-permissions)installation.
 

