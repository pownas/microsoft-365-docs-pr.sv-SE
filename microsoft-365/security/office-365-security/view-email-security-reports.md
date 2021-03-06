---
title: Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter
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
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Lär dig hur du hittar och använder e-postsäkerhets rapporter för organisationen. Säkerhets rapporter för e-post finns i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e98e59d39744d67427a272f456a03fc123034aa7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659483"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Det finns en mängd olika rapporter i [säkerhets & Compliance Center](https://protection.office.com) som hjälper dig att se hur säkerhetsfunktionerna för e-post, till exempel skydd mot skräp post, mot skadlig program vara och krypterings funktioner i Microsoft 365 som skyddar din organisation. Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till  \> **instrument panelen** för rapporter. Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Rapport om komprometterade användare

> [!NOTE]
> Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor. Den är inte tillgänglig i fristående Exchange Online Protection-organisationer (EOP).

Rapporten **äventyrade användare** visar antalet användar konton som marker ATS som **misstänkta** eller **begränsade** under de senaste 7 dagarna. Konton i något av dessa tillstånd är problematiska eller till och med kompromissade. Med en ofta förekommande användning kan du använda rapporten för att upptäcka mellanliggande och till och med trender i misstänkta eller begränsade konton. Mer information om komprometterade användare finns i [svara på ett komprometterat e-postkonto](responding-to-a-compromised-email-account.md).

![Widgeten användare med sekretess i rapport instrument panelen](../../media/compromised-users-report-widget.png)

I vyn mängd visas data för de senaste 90 dagarna och detaljvyn visar data för de senaste 30 dagarna.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **användare med kompromissade**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=CompromisedUsers> .

Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja ett eller flera av följande värden:

- **Start datum** och **slutdatum**

- **Misstänkt**: användar kontot har skickat misstänkt e-post och riskerar att begränsas från att skicka e-post.

- **Begränsat**: användar kontot har begränsats från att skicka e-post på grund av starkt misstänkta mönster.

![Rapportvyn i rapporten användare med kompromissad](../../media/compromised-users-report-activity-view.png)

Om du klickar på **Visa informations tabell** kan du se följande uppgifter:

- **Skapelse tid**
- **Användar-ID**
- **Åtgärd**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="encryption-report"></a>Krypterings rapport

**Krypterings rapporten** är tillgänglig i EOP (abonnemang med post lådor i Exchange Online eller fristående EOP utan Exchange Online-postlådor). Din organisations säkerhets team kan använda informationen i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden. Till exempel:

- Om du ser ett stort antal e-postmeddelanden som har krypterats av användarna kanske du vill lägga till en krypterings princip för att automatisera kryptering för vissa användnings fall. Mer information finns i [definiera regler för e-postflöde för att kryptera e-postmeddelanden i Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Om du har ett antal krypteringsalgoritmer tillgängliga men ingen använder dem kan du undersöka om användarna behöver funktions träning.

Med mängd läget kan du filtrera under de senaste 90 dagarna, medan vyn detaljerad kan filtreras i 10 dagar.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **krypterings rapport**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=EncryptionReport> .

Mer information om kryptering finns i [kryptering med e-post i Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Rapportvy för krypterings rapporten

Du kan använda följande filter i diagrammet:

- **Visa data via: meddelande krypterings rapport** och **bryta ned efter: krypterings metod**: följande krypterings metoder är tillgängliga:

  - **Kryptering efter användare**
  - **Kryptering per princip**

  Om du klickar på **filter** kan du ändra diagrammet med följande filter:

  - **Start datum** och **slutdatum**
  - Krypterings metod.
  - Krypterings mal len.

- **Visa data via: meddelande krypterings rapport** och **bryta ned efter: krypterings mal len**: följande krypterings metoder är tillgängliga:

  - **Vidarekoppla inte**
  - **Endast kryptering**
  - **OME föregående**
  - **Företagsanpassade**

  Om du klickar på **filter** kan du ändra diagrammet med följande filter:

  - **Start datum** och **slutdatum**
  - Krypteringsmetod
  - Krypterings mal len

- **Visa data efter: de fem främsta mottagar domänerna**: i den här vyn visas ett cirkel diagram med antal skickade meddelanden för de fem främsta domänerna.

  Om du klickar på **filter** kan du välja ett **start datum** och ett **slutdatum**.

### <a name="details-table-view-for-the-encryption-report"></a>Vyn detaljerad tabell för krypterings rapporten

Om du klickar på **Visa informations tabell** beror informationen som visas på diagrammet du tittade på:

- **Bryt ner med: krypterings metod** eller **Bryt ner med: krypterings mal len**: följande information visas:

  - **Datum**
  - **Avsändarens adress**
  - **Krypterings mal len**
  - **Krypteringsmetod**
  - **Mottagarens adress**
  - **Ämne**

- **Visa data enligt: de 5 främsta mottagar domänerna**:

  - **Datum**
  - **Mottagar domän**
  - **Antal meddelanden**

Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:

- **Start datum** och **slutdatum**
- Krypteringsmetod
- Krypterings mal len

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="mailflow-status-report"></a>Flödes status rapport

I **rapporten flödes** schema visas information om skadlig program vara, skräp post, nätfiske och Edge-blockerade meddelanden. Mer information finns i [flödes status rapport](view-mail-flow-reports.md#mailflow-status-report).

## <a name="malware-detections-in-email-report"></a>Identifiering av skadlig program vara i e-postrapport

**Identifiering av skadlig program vara i e-** postrapporten visar information om identifiering av skadlig program vara i inkommande och utgående e-postmeddelanden (malware identifieras av Exchange Online Protection eller EOP). Mer information om skydd mot skadlig program vara i EOP finns i [skydda mot skadlig program vara i EOP](anti-malware-protection.md).

 Med filtret mängd filter kan du använda 90 dagar, men det går bara att filtrera tabellen med information i 10 dagar.

Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **identifiering av skadlig kod i e-post**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MalwareDetections> .

![Identifiering av skadlig program vara i e-postwidget på rapport instrument panelen](../../media/malware-detections-widget.png)

Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja:

- **Start datum** och **slutdatum**
- **Inkommande**
- **Gående**

![Rapportvy i rapporten om skadlig program vara i e-postrapporten](../../media/malware-detections-report-view.png)

Om du klickar på **Visa informations tabell** kan du se följande uppgifter:

- **Datum**
- **Avsändarens adress**
- **Mottagarens adress**
- **Meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt. Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).
- **Ämne**
- **Datafil**
- **Namn på skadlig kod**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="mail-latency-report"></a>E-postrapport

I **rapporten e-postsvars tid** finns information om hur du skickar e-post och Spräng Mer information finns i [rapporten om e-postsvar](view-reports-for-atp.md#mail-latency-report).

## <a name="sent-and-received-email-report"></a>Skicka och ta emot e-postrapport

Den **skickade och mottagna e-** postrapporten innehåller information om skadlig kod, skräp post, regler för e-postflöde (kallas även transport regler) och avancerade identifieringar av skadlig kod efter e-post till tjänsten. Mer information finns i [skicka och ta emot e-postrapport](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Rapport om skräp identifiering

I rapporten **skräp identifiering** visas skräp post meddelanden som blockeras av EOP. Meddelanden räknas individuellt, inte per mottagare. Om till exempel samma skräp post skickades till 100 mottagare i din organisation räknas det som ett meddelande.

I den sammanslagna vyn kan du filtrera 90 dagar medan tabellen information tillåter filtrering i tio dagar.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **skräp identifiering**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget för skräp post identifiering i instrument panelen rapporter](../../media/spam-detections-report-widget.png)

Mer information om skydd mot skräp post finns i [skydd mot skräp post i EOP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Rapportvy för rapporten skräp identifiering

Följande diagram är tillgängliga i rapportvyn:

- **Bryt ned genom: åtgärd**: följande händelse typer visas:

  - **Skräp post filtrerat**
  - **Skräp post IP-block**
  - **Skräp post omslag**
  - **Spam DBEB filter**: mappad Edge-blockering (DBEB)

  När du hovrar över en dag (data punkt) i diagrammet kan du se hur många objekt som har blockerats den dagen samt hur objekten kategoriseras.

  ![Aktivitetsvy i rapporten om skräp identifiering](../../media/spam-detections-report-action-view.png)

- **Bryt ned efter: riktning**: följande vägvisningar visas:

  - **Inkommande**
  - **Gående**

  ![Vyn riktning i rapporten skräp identifiering](../../media/spam-detections-report-direction-view.png)

Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:

- **Start datum** och **slutdatum**
- Riktnings värden
- Händelse typ värden

### <a name="details-table-view-for-the-spam-detections-report"></a>Vyn detaljerad tabell för rapporten skräp identifiering

Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:

- **Datum**
- **Avsändarens adress**
- **Mottagarens adress**
- **Händelse typ**
- **Åtgärd**
- **Ämne**

Om du klickar på **filter** i en informations tabell kan du ändra resultatet med följande filter:

- **Start datum** och **slutdatum**
- Riktnings värden
- Händelse typ värden

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="spoof-detections-report"></a>Rapport om falska identifieringar

Rapporten **Spoof identifieringar** visar hur många e-postmeddelanden som har identifierats och vilka som ansågs "goda" (falsk e-post gjorda för legitima affärs skäl). Mer information om förfalskning finns i [skydd mot förfalskning i EOP](anti-spoofing-protection.md).

Med den sammanslagna rapporten kan du använda 90 dagar på filtreringen, men i detaljvyn kan endast tio dagar av filtrering tillåtas.

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **falska identifierings** regler. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widgeten för förfalskningar i rapport instrument panelen](../../media/spoof-detections-widget.png)

När du håller mus pekaren över en dag (data punkt) i diagrammet kan du se hur många e-postmeddelanden som är falska.

Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja ett eller flera av följande värden:

- **Start datum** och **slutdatum**

- **Bra e-post**

- **Fångade som skräp post**

![Rapportvy i rapporten för falska identifieringar](../../media/spoof-detections-report-view.png)

Om du klickar på **Visa informations tabell** kan du se följande uppgifter:

- **Datum**
- **Falsk avsändare**
- **Sant avsändare**
- **Avsändarens IP**
- **Åtgärd**
- **Antal meddelanden**

Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.

## <a name="threat-protection-status-report"></a>Statusrapport för hotskydd

Status rapporten för **hotet Protection** finns i både EOP och Microsoft Defender för Office 365; rapporterna innehåller emellertid olika data. EOP kunder kan till exempel Visa information om skadlig kod som upptäckts i e-post, men inte information om skadliga filer som identifieras av [ATP för SharePoint, OneDrive eller Microsoft Teams](atp-for-spo-odb-and-teams.md).

I rapporten får du räknat antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbplats adresser (URL: er) som blockerades av motorn mot skadlig program vara, en [hel timmes autorensning (Zap)](zero-hour-auto-purge.md)och Defender för Office 365-funktioner som [säkra länkar](atp-safe-links.md), [säkra bifogade filer](atp-safe-attachments.md)och [nätfiske](set-up-anti-phishing-policies.md). Du kan använda den här informationen för att identifiera trender eller för att avgöra om organisations principer behöver justeras.

**Obs!** det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.

Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **skydds status**. Om du vill gå direkt till rapporten öppnar du en av följande webb adresser:

- Microsoft Defender för Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widgeten skydds status i rapport instrument panelen](../../media/threat-protection-status-report-widget.png)

Som standard visar diagrammet data för de senaste sju dagarna. Om du klickar på **filter** kan du välja ett datum intervall för 90 dagar (prov abonnemang kan vara begränsat till 30 dagar). Med vyn detaljerad tabell kan du filtrera i 30 dagar.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportvy för status rapport för hotet skydd

Följande vyer är tillgängliga:

- **Visa data via: översikt**: följande identifierings information visas:

  - **Skadlig program vara**
  - **E-Phish**
  - **Skadlig program vara**

  ![Vyn Översikt i status rapport för hotet skydd](../../media/threat-protection-status-report-overview-view.png)

- **Visa data efter: innehåll \> Malware**<sup>1</sup>: följande information visas för Microsoft Defender för Office 365-organisationer:

  - **Skydd mot skadlig program vara**: illasinnade filer identifieras i SharePoint, OneDrive och Microsoft Teams med [inbyggd virus identifiering i Microsoft 365](virus-detection-in-spo.md).
  - **Fil sprängare**: illasinnade filer identifieras av [ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md).

  ![Vyn skadlig program vara i rapporten skydds status](../../media/threat-protection-status-report-content-malware-view.png)

- **Visa data via: åsidosättning av meddelande**: följande information om att åsidosätta orsaken visas:

  - **Lokal hoppning**
  - **IP-Tillåt**
  - **Regel för e-postflöde**
  - **Tillåt avsändare**
  - **Tillåt domän**
  - **ZAP är inte aktiverat**
  - **Mappen skräp post är inte aktive rad**
  - **Användarens säkra avsändare**
  - **Användarens säkra domän**

  ![Vyn Åsidosätt meddelande i rapporten skydds status](../../media/threat-protection-status-report-message-override-view.png)

- **Bryta ned efter: identifierings teknologi** och **Visa data via: e- \> Phish**: följande information visas:

  - **ATP-genererad URL-rykte**<sup>1</sup>: skadlig URL-rykte skapad från Defender för Office 365-sprängor i andra Microsoft 365-kunder.
  - **Avancerat Phish filter**: phishing-signaler baserade på dator inlärning.
  - **Skydd mot förfalskning – DMARC**: DMARC misslyckades för meddelanden.
  - **Skydd mot förfalskning**: avsändaren försöker skicka falska till mottagar domänen.
  - **Skydd mot förfalskning-extern domän**: avsändaren försöker använda en annan domän.
  - **Varumärkes-personifiering**: personifiering av välkända varumärken baserat på avsändare.
  - **Domän person**<sup>1</sup>: personifiering av domäner som kunden äger eller definierar.
  - **EOP URL rykte**: skadlig URL-rykte.
  - **Allmänt Phish-filter**: nät fiske signaler baserade på analytiker regler.
  - **Gemensamma**
  - **PHISH ZAP**<sup>2</sup>: nollställt Hour Time rensning av nät fiske meddelanden.
  - **URL-sprängare**<sup>1</sup>
  - **User personifieringstoken**<sup>1</sup>: personifiering av användare som definierats av administratören eller lärts via post låda.

  ![Identifierings teknologi vy för nät fiske-e-post i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Bryta ned efter: identifierings teknologi** och **Visa data via: e- \> postskadlig program vara**: följande information visas:

  - **ATP – genererad fil rykte**<sup>1</sup>: alla skadliga fil rykte som genererats av Defender för Office 365-sprängmedel.
  - **Skydd mot skadlig program vara**<sup>: identifiering</sup>från motorer med skadlig program vara.
  - **Fil typs block för principer mot skadlig program vara**: dessa e-postmeddelanden filtreras på grund av den typ av skadlig fil som identifieras i meddelandet.
  - **Fil sprängare**<sup>1</sup>: identifiering av säkra bifogade filer.
  - **Fil rykte**
  - **Malware, ZAP**<sup>2</sup>
  - **Gemensamma**

  ![Identifierings teknologi vy för malware i status rapport för hotet skydd](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Bryt ned med: princip typ** och **Visa data via: e- \> Phish** eller **Visa data via: e-post för \> skadlig kod**: följande information visas:

  - **Skadlig program vara**
  - **Säkra bifogade filer**<sup>1</sup>
  - **Anti-Phish**
  - **Skydd mot skräp post**
  - **Regel för e-postflöde** (kallas även transport regel)
  - **Gemensamma**

  ![Vy för princip typ för nät fiske meddelanden i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Bryt ner med: leverans status** och **Visa data via: e- \> Phish** eller **Visa data via: e-post för \> skadlig kod**: följande information visas:

  - **Leveransen misslyckades**
  - **Avbröts**
  - **Vidarekopplas**
  - **Den värdbaserade post lådan: anpassad mapp**
  - **Den värdbaserade post lådan: borttagna objekt**
  - **Den värdbaserade post lådan: Inkorgen**
  - **Post låda: skräp post**
  - **Lokal server: levereras**
  - **Karantän**

  ![Vyn leverans status för phishing-e-post i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Defender för Office 365

<sup>2</sup> noll-timmars autorensning (Zap) är inte tillgängligt i fristående EOP (den fungerar bara i Exchange Online-postlådor).

Om du klickar på **filter**, beror de tillgängliga filtren på diagrammet du tittade på:

- Om du vill **Visa data via: \> skadligt innehåll** kan du ändra rapporten genom att **Starta datum** och **slutdatum** samt **identifiering** svärdet.

- Om du vill **Visa data via: åsidosättning av meddelande** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - **Åsidosätt orsak**
  - **Tagg**: filtrera resultat efter användare eller grupper som har den angivna användar tag gen installerad (inklusive prioriterade konton). Mer information om användar flaggor finns i [User Tags](user-tags.md).
  - **Domain**

- För alla andra vyer kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - **Proxyidentifiering**
  - **Skyddas av**: **ATP** eller **EOP**
  - **Tagg**: filtrera resultat efter användare eller grupper som har den angivna användar tag gen installerad (inklusive prioriterade konton). Mer information om användar flaggor finns i [User Tags](user-tags.md).
  - **Domain**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Vyn detaljerad tabell för status rapport för hotet skydd

Om du klickar på **Visa informations tabell** beror informationen som visas på diagrammet du tittade på:

- **Visa data efter: översikt**: knappen för **tabell information** är tillgänglig.

- **Visa data efter: innehåll \> Skadlig kod**:

  - **Datum**
  - **Plats**
  - **Omkopplad av**
  - **Namn på skadlig kod**

  Om du klickar på **filter** i den här vyn kan du ändra rapporten genom **start datum** och **slutdatum** samt **identifiering** svärdet.

- **Visa data via: åsidosättning av meddelande**:

  - **Datum**
  - **Ämne**
  - **Avsändare**
  - **Mottagarna**
  - **Identifieras av**
  - **Åsidosätt orsak**
  - **Kompromiss källa**
  - **Taggen**

  Om du klickar på **filter** i den här vyn kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - **Åsidosätt orsak**
  - **Tagg**: filtrera resultat efter användare eller grupper som har den angivna användar tag gen installerad (inklusive prioriterade konton). Mer information om användar flaggor finns i [User Tags](user-tags.md).
  - **Domain**
  - **Mottagare** (Observera att den här filter bara egenskapen är endast tillgänglig i vyn detaljerad tabell)

- Alla andra diagram:

  - **Datum**
  - **Ämne**
  - **Avsändare**
  - **Mottagarna**
  - **Identifieras av**
  - **Leverans status**
  - **Kompromiss källa**
  - **Taggen**

  Om du klickar på **filter** kan du ändra rapporten med följande filter:

  - **Start datum** och **slutdatum**
  - **Proxyidentifiering**
  - **Skyddas av**: **Defender för Office 365** eller **EOP**
  - **Tagg**: filtrera resultat efter användare eller grupper som har den angivna användar tag gen installerad (inklusive prioriterade konton). Mer information om användar flaggor finns i [User Tags](user-tags.md).
  - **Domain**
  - **Mottagare** (Observera att den här filter bara egenskapen är endast tillgänglig i vyn detaljerad tabell)

## <a name="top-malware-report"></a>Top skadlig kod-rapport

Den **översta program varan** rapporterar visar de olika typer av skadlig kod som identifieras av [skydd mot skadlig program vara i EOP](anti-malware-protection.md).

Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **högsta skadliga program vara**. Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopMalware> .

![Widgeten Top skadlig kod på instrument panelen rapporter](../../media/top-malware-report-widget.png)

När du hovrar över en sektor i cirkel diagrammet kan du se namnet på en typ av skadlig kod och hur många meddelanden som har identifierats.

![Övre rapport över skadlig program vara](../../media/top-malware-report-view.png)

Om du klickar på **Visa informations tabell** kan du se följande uppgifter:

- **Övre skadliga program**
- **Öka**

Om du klickar på **filter** i vyn rapport eller detaljerad tabell kan du ange ett datum intervall med **start datum** och **slutdatum**.

## <a name="url-threat-protection-report"></a>Rapport om skydd mot URL-hotet

**Rapporten för skydd mot URL-hotet** är tillgänglig i Microsoft Defender för Office 365. Mer information finns i [rapporten om skydd mot URL-hotet](view-reports-for-atp.md#url-threat-protection-report).

## <a name="user-reported-messages-report"></a>Rapport med rapporterat meddelande

I rapporten **rapporterad meddelanden** visas information om e-postmeddelanden som användare har rapporterat som skräp post, nät fiske försök eller god e-post med hjälp av [rapport tillägget](enable-the-report-message-add-in.md).

Information är tillgänglig för varje meddelande, inklusive leverans orsaken, sådant undantag för skräp post eller regel för e-postflöde som har kon figurer ATS för din organisation. Om du vill visa information väljer du ett objekt i listan med användar rapporter och visar sedan informationen på flikarna **Sammanfattning** och **information** .

![I rapporten User-Reported meddelanden visas de meddelanden som användare märkt som skräp post, inte skräp post eller nätfiske-försök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Om du vill visa den här rapporten gör du något av följande i avsnittet [säkerhet & regelefterlevnad](https://protection.office.com):

- Gå till instrument panel för **Threat Management** \>  \> **-rapporter**.

- Gå till **Threat Management** \> **Granska** \> **användardefinierade meddelanden**.

![Välj Threat Management \> Granska \> användarnas rapporterade meddelanden i säkerhets & efterlevnad](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> För att det rapporterade meddelandet ska fungera korrekt **måste gransknings loggning vara aktiverat** för din Office 365-miljö. Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online. Mer information finns i [Aktivera eller inaktivera Gransknings logg för Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Vilka behörigheter behövs för att visa rapporterna?

För att kunna visa och använda de rapporter som beskrivs i den här artikeln måste du vara medlem i någon av följande roll grupper i säkerhets & Compliance Center:

- **Organisationshantering**
- **Säkerhets administratör**
- **Säkerhets läsare**
- **Global läsare**

Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

**Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="what-if-the-reports-arent-showing-data"></a>Vad händer om rapporterna inte visar data?

Om du inte ser data i rapporterna kontrollerar du att dina principer är korrekt konfigurerade. Mer information finns i [skydda mot hot](protect-against-threats.md).

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot skräp post och skyddet mot skadlig program vara i EOP](anti-spam-and-anti-malware-protection.md)

[Smarta rapporter och insikter i säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md)

[Visa rapporter om e-postflöden i säkerhets & Compliance Center](view-mail-flow-reports.md)

[Visa rapporter för Defender för Office 365](view-reports-for-atp.md)
