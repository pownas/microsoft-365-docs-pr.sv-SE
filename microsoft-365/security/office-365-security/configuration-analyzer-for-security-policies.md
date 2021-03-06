---
title: Konfigurations analys för säkerhets principer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de använder konfigurations analys för att hitta och åtgärda säkerhets principer som är under standard säkerhets principer för förvalda skydd och begränsande skydd.
ms.openlocfilehash: af7cf269151c7e947a0a2f653ce8638d46ccd905
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658667"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Konfigurations analys för skydds principer i EOP och Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> De funktioner som beskrivs i den här artikeln är i förhands granskning, är inte tillgängliga i alla organisationer och kan komma att ändras. Information om versions schema finns i [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).

Med konfigurations analys i säkerhets & Compliance Center får du en central plats för att hitta och åtgärda säkerhets principer där inställningarna är under standard skydds-och strikta skydds profil inställningar i [förvalda säkerhets principer](preset-security-policies.md).

Följande typer av principer analyseras av konfigurations analys:

- **Principer för Exchange Online Protection (EOP)**: det inkluderar Microsoft 365-organisationer med Exchange Online-postlådor och fristående EOP-organisationer utan Exchange Online-postlådor:

  - [Principer för skräp post](configure-your-spam-filter-policies.md).
  - [Principer mot skadlig program vara](configure-anti-malware-policies.md).
  - [EOP anti-nätfiske-principer](set-up-anti-phishing-policies.md#spoof-settings).

- **Microsoft Defender för Office 365-principer**: Detta inkluderar organisationer med Microsoft 365 E5-eller Defender för Office 365-tilläggs prenumerationer:

  - Skydd mot nätfiske i Microsoft Defender för Office 365, som omfattar:

    - Samma [falska inställningar](set-up-anti-phishing-policies.md#spoof-settings) som är tillgängliga i EOP anti-phishing-principer.
    - [Inställningar för personifiering](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Avancerade nät fiske trösklar](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Principer för säkra länkar](set-up-atp-safe-links-policies.md).

  - [Principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md).

De **vanliga** och **strikta** princip inställnings värden som används som bas linjer beskrivs i [rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **konfigurations analys** kan du använda <https://protection.office.com/configurationAnalyzer> .

- Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:
  - För att använda konfigurations analys **och** göra uppdateringar av säkerhets principer måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .
  - Om du vill ha skrivskyddad åtkomst till konfigurations analys måste du vara medlem i rollen **global läsare** eller **säkerhets läsare** .

  Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Använda Configuration Analyzer i Center för säkerhets &

Gå till  \>  \> **konfigurations analys** för Threat Management policy i säkerhets & efterlevnad.

![Widgeten för konfigurations analys på \> sidan Threat Management policy](../../media/configuration-analyzer-widget.png)

Konfigurations analysen har två primära flikar:

- **Inställningar och rekommendationer**: du väljer standard eller Strict och jämför dessa inställningar med dina befintliga säkerhets principer. I resultatet kan du justera värdena för inställningarna så att de får samma nivå som standard eller strikt.

- **Analys och historik för konfigurations avvikelse**: med den här vyn kan du spåra princip förändringar med tiden.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Fliken inställning och rekommendationer i konfigurations analys

Som standard öppnas fliken i jämförelsen med standard skydds profilen. Du kan växla till jämförelsen av den strikta skydds profilen genom att klicka på **Visa strikta rekommendationer**. Om du vill gå tillbaka väljer du **Visa standard rekommendationer**.

![Vyn inställningar och rekommendationer i konfigurations analys](../../media/configuration-analyzer-settings-and-recommendations-view.png)

Som standard innehåller kolumnen **princip grupp/inställnings namn** en dold vy av de olika typerna av säkerhets principer och det antal inställningar som behöver förbättras. Följande typer av principer är:

- **Skydd mot skräp post**
- **Anti-nätfiske**
- **Skadlig program vara**
- **ATP-säkra bifogade filer** (om ditt abonnemang innehåller Microsoft Defender för Office 365)
- **Säkerhet för ATP** (om ditt abonnemang inkluderar Microsoft Defender för Office 365)

I standardvyn är allting dolda. Bredvid varje princip finns en sammanfattning av jämförelse resultat från dina principer (som du kan ändra) och inställningarna i motsvarande principer för standard-eller sträng skydds profilerna (som du inte kan ändra). Följande information om den skydds profil som du jämför med ska visas:

- **Grön**: alla inställningar i alla befintliga principer är åtminstone lika säkra som skydds profilen.
- **Gul**: ett litet antal inställningar i befintliga principer är inte så säkert som skydds profilen.
- **Rött**: ett stort antal inställningar i befintliga principer är inte så säkert som skydds profilen. Det här kan vara några få inställningar i många principer eller många inställningar i en princip.

För fördelaktig jämförelser visas texten: **alla inställningar följer** \<**Standard** or **Strict**\> **rekommendationer**. I annat fall ser du antalet rekommenderade inställningar att ändra.

Om du expanderar **princip grupp/inställnings namn** visas alla principer och associerade inställningar i varje specifik princip som kräver åtgärd. Eller så kan du expandera en viss typ av princip (till exempel **anti-spam**) för att se bara de inställningar som gäller för de principer som kräver din uppmärksamhet.

Om jämförelsen inte har några rekommendationer för förbättring (grön) kan du utöka policyn genom att Visa ingenting. Om det finns några rekommendationer för förbättringar (gul eller röd) visas de inställningar som kräver åtgärd och informationen visas i följande kolumner:

- Namnet på den inställning som kräver din uppmärksamhet. I föregående skärm bild är det till exempel att **tröskelvärdet för Mass** utskick av e-post i en policy för skräp post.

- **Princip**: namnet på den berörda policyn som innehåller inställningen.

- **Tillämpas på**: antalet användare som de berörda principerna tillämpas på.

- **Aktuell konfiguration**: det aktuella värdet för inställningen.

- **Senast ändrad**: det datum då principen senast ändrades.

- **Rekommendationer**: värdet för inställningen i standard-eller sträng skydds profilen. Om du vill ändra värdet för inställningen i principen så att det matchar det rekommenderade värdet i skydds profilen klickar du **på Välj.** Om ändringen lyckas visas meddelandet: **rekommendationerna har antagits**. Klicka på **Uppdatera** om du vill visa det nedsänkta antalet rekommendationer och borttagning av raden specifik inställning/princip från resultaten.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Konfiguration av avvikelser och historik i konfigurations analys

Med den här fliken kan du spåra de ändringar du har gjort i dina anpassade säkerhets principer. Följande information visas som standard:

- **Senast ändrad**
- **Ändrat av**
- **Inställnings namn**
- **Autentiseringsprincip**
- **Typ**

Om du vill filtrera resultaten klickar du på **Filter**. I de utfällbara **filter** som visas kan du välja bland följande filter:

- **Start tid** och **slut tid** (datum)
- **Standard skydd** eller **strikt skydd**

Exportera resultaten till en CSV-fil genom att klicka på **Exportera**.

![Konfiguration av avvikelser och historik i konfigurations analys](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
