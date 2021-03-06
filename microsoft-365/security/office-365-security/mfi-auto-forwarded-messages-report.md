---
title: Auto-vidarebefordrade meddelanden insikt
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Administratörer kan lära sig mer om rapporten för automatiskt vidarebefordrade meddelanden i instrument panelen för e-postflöde i säkerhets & efterlevnad.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920602"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a>Automatiskt vidarebefordrade meddelanden är inblick i säkerhets & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


De **automatiskt avvidarekopplade meddelandena** är inblick i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) visar information om meddelanden som automatiskt vidarebefordras från din organisation till mottagare i externa domäner.

![Widget för automatiskt vidarebefordrade meddelanden i säkerhets & efterlevnad](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a>Information om automatiskt vidarebefordrade meddelanden

När du klickar på antalet meddelanden i widgeten visas en utfällbar ruta som visar mer information om de automatiskt vidarebefordrade meddelandena:

- **Automatiskt vidarebefordrade meddelanden genom metoder för vidarebefordran** :

  - **Regler för e-postflöde**
  - **Regler för Inkorgen**
  - **Genom SMTP-vidarebefordran** : den här metoden indikerar automatisk vidarebefordran som administratörer kan konfigurera på en post låda enligt beskrivningen i [Konfigurera e-postvidarekoppling för en post låda](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).
  - En länk till [vidarekoppling](view-mail-flow-reports.md#forwarding-report) för mer information.

- **Automatiskt vidarebefordrade meddelanden per domän och användare** :

  - **De fem främsta domänerna vidarekopplas till**
  - **Nya domäner (förra veckan)**
  - **De 5 vanligaste användarna**
  - **Nya användare (förra veckan)**
  - En länk till [rapporten för ändring av ändringar](mfi-new-users-forwarding-email.md#forwarding-modifications-report) för att få mer information.

![Den utfällbara informationen för rapporten för automatiskt vidarebefordrade meddelanden i säkerhets & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a>Insikter

Två insikter genereras utifrån rapportens data:

- [Nya e-postmeddelanden](mfi-new-users-forwarding-email.md)
- [Nya domäner vidarebefordras via e-post](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
