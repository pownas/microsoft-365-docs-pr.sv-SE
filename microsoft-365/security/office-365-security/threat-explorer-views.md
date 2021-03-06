---
title: Vyer i Threat Explorer och identifieringar i real tid
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig hur du använder Threat Explorer och rapporten om identifiering av real tids rapporter för att undersöka och reagera på hot i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7300f8c87b100a38117b0cc4bee1bb95c9584c6
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615714"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Vyer i Threat Explorer och identifieringar i real tid

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

[Threat Explorer](threat-explorer.md) (och rapporten om identifiering av real tid) är ett kraftfullt, nära real tids verktyg som hjälper säkerhets åtgärder att undersöka och reagera på hot i säkerhets & Compliance Center. Utforskaren (och rapporten real tids identifiering) visar information om misstänkt skadlig program vara och Phish i e-post och filer i Office 365 samt andra säkerhetshot och risker för din organisation.

- Om du har [Microsoft Defender för Office 365](office-365-atp.md) abonnemang 2 har du Explorer.
- Om du har Microsoft Defender för Office 365 abonnemang 1 har du real tids identifiering.

När du först öppnar Utforskaren (eller rapporten real tids identifiering) visas e-postidentifiering av skadlig program vara under de senaste sju dagarna. Den här rapporten kan även visa Microsoft Defender för Office 365-identifieringar, till exempel skadlig URL-adresser som identifieras av [säkra länkar](atp-safe-links.md)och skadliga filer som identifieras av [säkra bifogade](atp-safe-attachments.md)filer. Den här rapporten kan ändras för att visa data för de senaste 30 dagarna (med ett Microsoft Defender för Office 365 P2-betalat abonnemang). Prov abonnemang kommer endast att omfatta data för de senaste sju dagarna.

****

|Prenumerationsvy|Nytta|Dagar med data|
|---|---|---|
|Utvärderings version av Microsoft Defender för Office 365|Identifiering i realtid|borttagning|
|Microsoft Defender för Office 365|Identifiering i realtid|halvtimme|
|Microsoft Defender för Office 365 P1-test Defender för Office 365 P2-utvärdering|Hotutforskaren|borttagning|
|Microsoft Defender för Office 365 P2-utvärdering|Hotutforskaren|borttagning|
|Microsoft Defender för Office 365 P2-betalat|Hotutforskaren|halvtimme|
|

Använd **Visa** -menyn för att ändra vilken information som visas. Med knapp beskrivningar kan du bestämma vilken vy som ska användas.

![Menyn Threat Explorer](../../media/ThreatExplorerViewMenu.png)

När du har valt en vy kan du använda filter och ställa in frågor för att utföra ytterligare analyser. I följande avsnitt får du en kort översikt över de olika vyer som är tillgängliga i Utforskaren (eller i real tid).

## <a name="email--malware"></a>> skadlig program vara

Om du vill visa rapporten klickar du på **Visa** \> **e-** \> **postskadlig kod** i Utforskaren (eller i real tid). I den här vyn visas information om e-postmeddelanden som identifierats som innehåll ande malware.

![Visa information om e-post som identifieras som skadlig program vara](../../media/ExplorerEmailMalwareMenu.png)

Klicka på **avsändare** för att öppna listan över visnings alternativ. Använd den här listan för att visa data efter avsändare, mottagare, avsändare, ämne, identifierings teknik, skydds status och mer.

Om du till exempel vill se vilka åtgärder som har utförts på identifierade e-postmeddelanden väljer du **skydds status** i listan. Välj ett alternativ och klicka sedan på knappen Uppdatera för att tillämpa filtret på rapporten.

![Status alternativ för hotets skydd för Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

Visa mer information om specifika meddelanden under diagrammet. När du markerar ett objekt i listan öppnas ett alternativ för att få mer information om det markerade objektet.

![Threat Explorer med utfällbar öppning](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-> Phish

Om du vill visa rapporten går du till Explorer (eller real tids identifiering) och väljer **Visa** \> **e-** \> **Phish**. I den här vyn visas e-postmeddelanden som identifieras som nätfiske-försök.

![Visa information om e-post som identifieras som nätfiske-försök](../../media/ThreatExplorerEmailPhish.png)

Klicka på **avsändare** för att öppna listan över visnings alternativ. Använd den här listan för att visa data efter avsändare, mottagare, avsändarens domän, avsändarens IP, URL-domän, klicka på Verdict och mycket mer.

Om du till exempel vill se vilka åtgärder som vidtogs när personer klickade på URL-adresser som har identifierats som nätfiske-försök väljer du **Klicka på Verdict** i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.

![Klicka på Verdict alternativ för rapporten Phish](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Under diagrammet kan du Visa mer information om specifika meddelanden, URL-musklick, URL: er och e-postursprung.

![URL-adresser identifieras som Phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

När du markerar ett objekt i listan, till exempel en webb adress som upptäckts, öppnas en dialog ruta för att ta reda på mer om det markerade objektet.

![Information om en upptäckd URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>Skicka e-post >

Om du vill visa den här rapporten går du till Explorer (eller real tids identifieringar) och väljer **Visa** \> **e-** \> **postinlägg**. I den här vyn visas e-post som användare har rapporterat som skräp post, inte skräp post eller nätfiske.

![E-postmeddelanden som rapporter ATS av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klicka på **avsändare** för att öppna listan över visnings alternativ. Använd den här listan för att visa information efter avsändare, mottagare, rapport typ (användarens kontroll att e-postmeddelandet var skräp, inte skräp post eller Phish) och mycket mer.

Om du till exempel vill visa information om e-postmeddelanden som rapporter ATS som nätfiske-försök klickar du på **avsändarens** \> **typ**, väljer **Phish** och klickar sedan på knappen Uppdatera.

![Phish markerad för rapport typ filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Under diagrammet visas mer information om specifika e-postmeddelanden, till exempel ämnes raden, avsändarens IP-adress, användaren som rapporterade meddelandet som skräp post, inte skräp post eller Phish.

![Meddelanden som rapporter ATS som nätfiske-försök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Välj ett objekt i listan för att visa ytterligare information.

## <a name="email--all-email"></a>E-posta > all e-post

Om du vill visa rapporten klickar du på **Visa** \> **e-** post i Utforskaren \> . I den här vyn visas en uppkopplings aktivitet med e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig program vara (vanlig e-post, spam och Mass utskick).

> [!NOTE]
> Om du får ett fel meddelande som läser upp **för mycket data** kan du lägga till ett filter och, om det behövs, begränsa det datum intervall du visar.

Om du vill använda ett filter väljer du **avsändare**, markerar ett objekt i listan och klickar sedan på knappen Uppdatera. I vårt exempel använde vi **identifierings teknologi** som ett filter (det finns flera tillgängliga alternativ). Visa information efter avsändare, avsändarens domän, mottagare, ämne, bifogade filer och skadlig program vara, skydds status (åtgärder som vidtas av funktioner och principer för hotets skydd i Office 365), identifierings teknologi (hur skadlig program vara upptäcktes) och mycket mer.

![Visa data om identifierad e-post efter identifierings teknologi](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Under diagrammet kan du Visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.

## <a name="content--malware"></a>Innehålls > skadlig program vara

Om du vill visa rapporten i Utforskaren (eller i real tid) väljer du **Visa** \>  \> **skadlig program vara**. I den här vyn visas filer som identifieras som skadliga av [Microsoft Defender för Office 365 i SharePoint Online, OneDrive för företag och Microsoft Teams](atp-for-spo-odb-and-teams.md).

Visa information från skadlig program vara, identifierings teknologi (hur skadlig kod har identifierats) och arbets belastning (OneDrive, SharePoint eller teams).

![Visa information om identifierad skadlig kod](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Under diagrammet kan du Visa mer information om specifika filer, till exempel fil namn, arbets belastning, fil storlek, som senast ändrade filen och mycket mer.

## <a name="click-to-filter-capabilities"></a>Klicka-och-filtrera-funktioner

Med Explorer (och real tids identifieringar) kan du använda ett filter i ett klick. Klicka på ett objekt i förklaringen så blir objektet ett filter för rapporten. Anta till exempel att vi tittar på vyn mot skadlig program vara i Utforskaren:

![Gå till Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Om du klickar på **ATP-sprängor** i det här diagrammet visas en vy som här:

![Explorer filtrerat för att visa endast Defender för 365-sprängning](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

I den här vyn visar vi nu data för filer som har sprängts med [säkra bifogade](atp-safe-attachments.md)filer. Under diagrammet kan vi se information om specifika e-postmeddelanden med bifogade filer som upptäcktes av säkra bifogade filer.

![Specifik information om e-postmeddelanden med identifierade bilagor](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Om du markerar ett eller flera objekt aktive ras **Åtgärds** menyn, som innehåller flera alternativ som du kan välja för.

![När du markerar ett objekt aktive ras menyn åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

Möjligheten att filtrera i ett klick och navigera till specifika uppgifter gör att du kan spara pengar.

## <a name="queries-and-filters"></a>Frågor och filter

Utforskaren (samt rapporter i real tid) innehåller flera kraftfulla filter och fråge funktioner som gör att du kan visa detaljer, till exempel Top riktade användare, de viktigaste, identifierings teknologin och mer. I alla typer av rapporter finns det flera olika sätt att visa och utforska data.

> [!IMPORTANT]
> Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i fråge fältet för Explorer (eller real tids identifiering). När du söker i **ämnes fältet** för e-postmeddelanden kommer Explorer (eller real tids identifiering) att utföra delvis matchande och ge resultat som liknar en sökning med jokertecken.
