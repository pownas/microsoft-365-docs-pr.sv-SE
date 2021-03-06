---
title: Använda e-postflödes regler i SCL i meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Lär dig hur du skapar e-postflödes regler (transport regler) för att identifiera meddelanden och ange SCL (skräp säkerhets nivå) för meddelanden i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659843"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Använda regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används principer för skräp post (kallas även för principer för skräp post filter eller principer för innehålls filter) för att söka igenom inkommande meddelanden. Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

Om du vill markera specifika meddelanden som skräp post innan de är inaktiverade med skräp post filtrering, eller markera meddelanden så att de hoppar över skräp post filtrering, kan du skapa regler för e-postflöde (kallas även transport regler) för att identifiera meddelandena och ställa in säkerhets nivån för skräp post. Mer information om SCL finns i [säkerhets nivå för skräp post (SCL) i EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i Exchange Online eller Exchange Online Protection innan du kan göra det i den här artikeln. För det specifika måste du ha rollen **Transport regel** , som är tilldelad till **organisations hantering**, **hantering av efterlevnad** (globala administratörer) och roll grupperna **Arkiv handlings hantering** som standard.

  Mer information finns i följande avsnitt:

  - [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Behörigheter i fristående EOP](feature-permissions-in-eop.md)
  - [Använda UK ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöden i Exchange Online och Exchange Online Protection finns i [regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Använd UK för att skapa en regel för e-postflöde som anger SCL för ett meddelande

1. Gå till regler för **e-postflöde** i UK \> .

2. Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.

3. På sidan **ny regel** som öppnas konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln.

   - Klicka på **fler alternativ**.

   - **Använd den här regeln om**: Välj ett eller flera villkor för att identifiera meddelanden. Mer information finns i [villkor och undantag för e-postflödes regler (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**. I dialog rutan **Ange SCL** väljer du något av följande värden:

   - **Kringgå skräp post filtrering**: meddelanden åsidosätter inte skräp post filtrering.

     > [!CAUTION]
     > Var försiktig om att låta meddelanden hoppa över skräp post filtrering. Angripare kan använda detta problem för att skicka nätfiske och andra skadliga meddelanden till din organisation. Reglerna för e-postflöden kräver mer än avsändarens e-postadress eller domän. Mer information finns i [skapa säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md).

   - **0 till 4**: meddelandet skickas via spam för ytterligare bearbetning.

   - **5 eller 6**: meddelandet är markerat som **skräp post**. Den åtgärd som du har konfigurerat för **skräp post** filtrering verdicts i dina meddelanden (standardvärdet **flyttas till mappen skräp post**).

   - **7 till 9**: meddelandet har marker ATS som **skräp post**. Den åtgärd som du har konfigurerat för filtrering av skräp post med **hög exakthet** verdicts i meddelandet (standardvärdet **flyttas till mappen skräp post**).

4. Ange ytterligare egenskaper för regeln. Klicka på **Spara** när du är klar.

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Verifiera att den här proceduren fungerar som den ska genom att skicka ett e-postmeddelande till någon inom organisationen och kontrol lera att åtgärden som utförs på meddelandet är som förväntat. Om du till exempel **ställer in säkerhets nivån för skräp post (SCL)** för att **kringgå skräp post** ska meddelandet skickas till den angivna mottagarens inkorg. Men om du **har angett säkerhets nivån för skräp post (SCL)** till **9** och åtgärden att ta bort **hög säkerhet** för dina tillämpliga skydd mot skräp post är att meddelandet ska flyttas till mappen skräp post.
