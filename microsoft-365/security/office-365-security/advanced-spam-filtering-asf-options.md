---
title: ASF-inställningar i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om de avancerade inställningarna för skräp post filter (ASF) som är tillgängliga i principer för skräp post överföring i Exchange Online Protection (EOP).
ms.openlocfilehash: 92d5e58937b539bf2be8d6d2c541f985562b7007
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659624"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Avancerade inställningar för skräp post filter (ASF) i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> ASF-inställningar som för närvarande är tillgängliga i principer för skräp post är i föråldrade. Vi rekommenderar att du inte använder dessa inställningar i principer för skräp post. Funktionerna i dessa ASF-inställningar läggs in i andra delar av filtrerings stacken. Mer information finns i [EOP princip inställningar för skräp post](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

I alla Microsoft 365-organisationer är det avancerade skräp post filtret (ASF) för principer för skräp post i EOP att administratörer kan markera meddelanden som skräp post baserat på specifika meddelande egenskaper. ASF specifikt riktar sig på dessa egenskaper eftersom de ofta finns i spam. Beroende på egenskapen kan ASF-identifieringar antingen markera meddelandet som **skräp post** eller **snabb skräp post**.

> [!NOTE]
> Att aktivera en eller flera av ASF-inställningarna är en aggressiv metod för filtrering av skräp post. Du kan inte rapportera meddelanden som filtrerats efter ASF som falska positiva positiv. Du kan identifiera meddelanden som filtrerats efter ASF av:
>
> - Regelbunden skräp avisering om slutanvändare.
>
> - Det finns filtrerade meddelanden i karantänen.
>
> - Specifika `X-CustomSpam:` X-huvudfält som läggs till i meddelanden enligt beskrivningen i den här artikeln.

I följande avsnitt beskrivs de ASF-inställningar och-alternativ som är tillgängliga i principer för skydd mot skräp post i säkerhets & Compliance Center och i Exchange Online PowerShell eller fristående EOP PowerShell ([ny-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) och [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)). Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivera, inaktivera eller testa ASF-inställningar

För varje ASF-inställning är följande alternativ tillgängliga i principer för skräp post:

- **On**: ASF lägger till motsvarande X-huvud-fält i meddelandet och antingen markerar meddelandet som **skräp post** (SCL 5 eller 6 för att [öka inställningarna för skräp post](#increase-spam-score-settings)) eller **hög exakthet för skräp** post (SCL 9 för [markering som skräp post inställningar](#mark-as-spam-settings)).

- **Av**: inställningen för ASF är inaktive rad. Det här är standardvärdet och vi rekommenderar att du inte ändrar det.

- **Test**: ASF lägger till motsvarande X-huvud-fält i meddelandet. Vad som händer med meddelandet beror på alternativ för **testläge** (*TestModeAction*):

  - **Ingen**: meddelande leverans påverkas inte av ASF-identifieringen. Meddelandet gäller fortfarande andra typer av filtrering och regler i EOP.

  - **Lägg till standard text för x-rubrik (*AddXHeader*)**: värdet x-Head `X-CustomSpam: This message was filtered by the custom spam filter option` läggs till i meddelandet. Du kan använda det här värdet i regler för Inkorgen eller regler för e-postflöde (kallas även transport regler) för att påverka leveransen av meddelandet.

  - **Skicka hemlig kopia (*BccMessage*)**: de angivna e-postadresserna ( *TestModeBccToRecipients* -parametervärdet i PowerShell) läggs till i fältet Hemlig kopia i meddelandet och meddelandet skickas till övriga mottagare. I säkerhets & Compliance Center avgränsar du flera e-postadresser med semikolon (;). I PowerShell avgränsar du flera e-postadresser med kommatecken.

  **Anmärkningar**:

  - Test läget är inte tillgängligt för följande ASF-inställningar:

    - **ID för villkorsstyrd avsändare: hårda fel** (*MarkAsSpamFromAddressAuthFail*)
    - *AutoMarkAsSpamNdrBackscatter*( **NDR**)
    - **SPF-post: hårda fel** (*MarkAsSpamSpfRecordHardFail*)

  - Samma åtgärd för test läge tillämpas på *alla* ASF-inställningar som är inställda på att **testa**. Du kan inte konfigurera olika test läges åtgärder för olika ASF-inställningar.

## <a name="increase-spam-score-settings"></a>Öka inställningarna för skräp post

Följande ASF-inställningar anger SCL (skräp Utjämnings grad) för identifierade meddelanden till 5 eller 6, som motsvarar **skräp post** filtret Verdict och motsvarande åtgärd i principer för borttagning av skräp post.

****

|Princip inställning för skräp post|Beskrivning|X-rubrik tillagd|
|---|---|---|
|**Bild länkar till fjärranslutna webbplatser** <p> *IncreaseScoreWithImageLinks*|Meddelanden som innehåller `<Img>` HTML-taggar till fjärranslutna webbplatser (till exempel http) markeras som skräp post.|`X-CustomSpam: Image links to remote sites`|
|**URL-omdirigering till annan port** <p> *IncreaseScoreWithRedirectToOtherPort*|Meddelande som innehåller hyperlänkar som omdirigeras till andra TCP-portar än 80 (HTTP), 8080 (alternativ HTTP) eller 443 (HTTPS) markeras som skräp post.|`X-CustomSpam: URL redirect to other port`|
|**Numerisk IP-adress i URL** <p> *IncreaseScoreWithNumericIps*|Meddelanden som innehåller numeriska adresser (vanligt vis IP-adresser) markeras som skräp post.|`X-CustomSpam: Numeric IP in URL`|
|**URL till. B2B argumentssida eller. info webbplatser** <p> *IncreaseScoreWithBizOrInfoUrls*|Meddelanden som innehåller `.biz` eller `.info` länkar i meddelande texten markeras som skräp post.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markera som skräp post inställningar

Följande ASF-inställningar anger SCL för identifierade meddelanden till 9, som motsvarar **skräp post filtret för hög exakthet** och den motsvarande åtgärden i principer för skräp post.

****

|Princip inställning för skräp post|Beskrivning|X-rubrik tillagd|
|---|---|---|
|**Tomma meddelanden** <p> *MarkAsSpamEmptyMessages*|Meddelanden som inte har något ämne, inget innehåll i meddelandets brödtext och inga bifogade filer markeras som skräp post.|`X-CustomSpam: Empty Message`|
|**Java Script eller VBScript i HTML** <p> *MarkAsSpamJavaScriptInHtml*|Meddelanden som använder Java Script eller Visual Basic script Edition i HTML markeras som skräp post som är säkrare. <p> Dessa skript språk används i e-postmeddelanden för att göra att specifika åtgärder utförs automatiskt.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Ram-eller IFrame-Taggar i HTML** <p> *MarkAsSpamFramesInHtml*|Meddelanden som innehåller `<frame>` eller `<iframe>` HTML-taggar markeras som skräp post. <p> Dessa taggar används i e-postmeddelanden för att formatera sidan för att visa text eller bilder.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Objekt-Taggar i HTML** <p> *MarkAsSpamObjectTagsInHtml*|Meddelanden som innehåller `<object>` HTML-taggar markeras som skräp post. <p> Den här taggen gör att plugin-program eller program kan köras i ett HTML-fönster.|`X-CustomSpam: Object tag in html`|
|**Bädda in Taggar i HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Meddelande som innehåller `<embed>` HTML-taggar är markerade som skräp post med hög exakthet. <p> Med den här taggen kan du bädda in olika typer av dokument i ett HTML-dokument (till exempel ljud, video eller bilder).|`X-CustomSpam: Embed tag in html`|
|**Formulär-Taggar i HTML** <p> *MarkAsSpamFormTagsInHtml*|Meddelanden som innehåller `<form>` HTML-taggar markeras som skräp post. <p> Den här taggen används för att skapa webbplats formulär. E-postannonser inkluderar ofta denna märkning för att skicka information från mottagaren.|`X-CustomSpam: Form tag in html`|
|**Webb program fel i HTML** <p> *MarkAsSpamWebBugsInHtml*|Ett *webb program fel* (kallas även för en *Web beacon*) är ett grafik element (ofta i en bild punkt) som används i e-postmeddelanden för att avgöra om meddelandet lästes av mottagaren. <p> Meddelanden som innehåller webb fel är markerade som skräp post med hög exakthet. <p> Legitima nyhets brev kan använda webb program, även om många anser det här en webb integritet. |`X-CustomSpam: Web bug`|
|**Använda känslig ord lista** <p> *MarkAsSpamSensitiveWordList*|Microsoft hanterar en dynamisk men inte redigerbar lista över ord som är kopplade till potentiellt stötande meddelanden. <p> Meddelanden som innehåller ord från den känsliga ord listan i ämnet eller meddelande texten markeras som skräp post.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-post: hårda fel** <p> *MarkAsSpamSpfRecordHardFail*|Meddelanden som skickas från en IP-adress som inte anges i SPF-posten (SPF avsändaren Policy Framework) i DNS för källan e-postdomänen markeras som skräp post som är säkrare. <p> Test läget är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF Record Fail`|
|**ID för villkorsstyrd avsändare: hårda fel** <p> *MarkAsSpamFromAddressAuthFail*|Meddelanden som inte fungerar på ett annat sätt är markerade som skräp post. <p> Den här inställningen kombinerar en SPF-kontroll med avsändarens ID-kontroll för att skydda mot meddelande rubriker som innehåller förfalskade avsändare. <p> Test läget är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF From Record Fail`|
|**Autoleverans punkt för NDR** <p> *MarkAsSpamNdrBackscatter*|*Bakgrunds program kan inte använda* icke-leverans rapporter (kallas även NDR eller studsande meddelanden) orsakade av förfalskade avsändare i e-postmeddelanden. Mer information finns i [bakpunkts meddelanden och EOP](backscatter-messages-and-eop.md). <p> Du behöver inte konfigurera den här inställningen i följande miljöer, eftersom legitima NDR levereras och bakgrunds funktionen markeras som skräp post: <ul><li>Microsoft 365-organisationer med Exchange Online-postlådor.</li><li>Lokala e-postorganisationer där du dirigerar *utgående* e-post via EOP.</li></ul> <p> I fristående EOP miljöer som skyddar inkommande e-post till lokala post lådor är det bara att aktivera eller inaktivera den här inställningen: <ul><li> **På**: legitima NDR levereras och bakgrunds markering är markerat som skräp post.</li><li>**Av**: legitimt NDR och-och-filter. De mest legitima NDR skickas till den ursprungliga avsändaren. Vissa, men inte alla, bakgrunder markeras som skräp post. Efter definition kan det bara levereras till den falska avsändaren, inte till den ursprungliga avsändaren.</li></ul> <p> Test läget är inte tillgängligt för den här inställningen.|`X-CustomSpam: Backscatter NDR`|
|
