---
title: Meddelanden om avanmälan till slutanvändare i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig om skräp post meddelanden för meddelanden i karantän i Exchange Online Protection (EOP).
ms.openlocfilehash: 0440056e8e31d24e659f9d0ff6662f86f31a6189
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600303"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Använda skräp post meddelanden för att frigöra och rapportera översatta meddelanden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden. Mer information finns i [karantän meddelanden i EOP](quarantine-email-messages.md).

Som standard är skräp post meddelanden avaktiverade i principer för skräp post. När en administratör [aktiverar skräp post meddelanden för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), får mottagarna (inklusive delade post lådor med Automappning aktiverat) regelbundna meddelanden om sina meddelanden som sattes i karantän som skräp post, Mass utskick eller (från april 2020) nätfiske.

För delade post lådor stöds inte skräp post meddelanden för användare som har tilldelats behörigheten Full Access-behörighet till den delade post lådan. Mer information finns i [använda UK för att redigera delegerade post lådor](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

Det går inte att skicka skräp post till slutanvändaren för grupper.

> [!NOTE]
> Meddelanden som satts i karantän som nätfiske, skadlig program vara eller enligt regler för e-postflöde (kallas även transport regler) är endast tillgängliga för administratörer. Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).

Ett skräp post meddelande för slutanvändare innehåller följande information för varje meddelande i karantän:

- **Avsändare**: skicka namn och e-postadress till det uppsatta meddelandet.

- **Ämne**: ämnes raden i det mellanliggande meddelandet.

- **Datum**: det datum och den tid (i UTC) som meddelandet satts i karantän.

- **Spärra avsändare**: Klicka på den här länken för att lägga till avsändaren i listan med spärrade avsändare. Mer information finns i [blockera en e-avsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Version**: för skräp post meddelanden (inte nätfiske) kan du släppa meddelandet här utan att gå till karantänen säkerhets & Compliance Center.

- **Granska**: Klicka på den här länken om du vill gå till karantän i säkerhets & Compliance Center, där du kan (beroende på varför meddelandet satts i karantän), släpp, ta bort eller rapportera dina meddelanden i karantän. Mer information finns i [hitta och släppa meddelanden i karantän som en användare i EOP](find-and-release-quarantined-messages-as-a-user.md).

![Exempel på påminnelse om slutanvändare](../../media/end-user-spam-notification.png)

> [!NOTE]
> En blockerad avsändare kan fortfarande skicka e-post. Alla meddelanden från denna avsändare som gör det till post lådan flyttas omedelbart till mappen skräp post. Framtida meddelanden från den här avsändaren skickas till mappen skräp post eller till slutanvändarnas karantän. Om du vill ta bort dessa meddelanden när de anländer i stället för quarantining kan du använda [e-postflödes regler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) för att ta bort meddelanden när de anländer.
