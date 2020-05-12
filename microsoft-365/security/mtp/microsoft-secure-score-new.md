---
title: Microsoft Secure Score ny
description: I artikeln beskrivs Microsoft Secure Score i säkerhetscentret Microsoft 365, hur information beräknas och vilka säkerhetsadministratörer som kan förvänta sig att använda den.
keywords: säkerhet, malware, Microsoft 365, M365, säker poäng, säkerhetscenter, förbättringsåtgärder
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 965b4cf872129dc7bc9b439c1c15025acceb44c6
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173568"
---
# <a name="microsoft-secure-score-new"></a>Microsoft Secure Score (ny)

>[!IMPORTANT]
>Denna nya iteration av Microsoft Secure Score ersätter den tidigare iterationen med nya designelement och funktioner under de närmaste månaderna
>
>Om du INTE ser fliken **Mått & trender bredvid** Historik, är du i föregående iteration. [Gå till Microsoft Secure Score (föregående iteration)](microsoft-secure-score.md)

Microsoft Secure Score är ett mått på en organisations säkerhetsposition, med ett högre antal som anger fler förbättringsåtgärder som vidtas. Den finns på https://security.microsoft.com/securescore i [Microsoft 365 security center](overview-security-center.md).

Om du följer rekommendationerna om säkerhetsresultat kan du skydda din organisation från hot. Från en centraliserad instrumentpanel i Microsoft 365-säkerhetscentret kan organisationer övervaka och arbeta med säkerheten för sina Microsoft 365-identiteter, data, appar, enheter och infrastruktur.

Secure Score hjälper organisationer:  

* Rapport om det aktuella läget för organisationens säkerhetsposition.
* Förbättra deras säkerhetsposition genom att tillhandahålla upptäckbarhet, synlighet, vägledning och kontroll.  
* Jämför med riktmärken och fastställ nyckeltal.

Organisationer får tillgång till robusta visualiseringar av mått och trender, integrering med andra Microsoft-produkter, poängjämlikhet med liknande organisationer och mycket mer. Poängen kan också återspegla när tredjepartslösningar har åtgärdat rekommenderade åtgärder.

Dessutom kan du komma åt dina rekommendationer och poäng via [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api). Läs mer om [resurstypen Säker poäng](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Så här fungerar det

Du får poäng för att konfigurera rekommenderade säkerhetsfunktioner, utföra säkerhetsrelaterade uppgifter eller åtgärda förbättringsåtgärden med ett program eller program från tredje part, eller en alternativ begränsning. Vissa förbättringsåtgärder ger bara poäng när de är helt slutförda, och vissa ger partiella poäng om de slutförs för vissa enheter eller användare. Om du inte kan eller inte vill anta någon av förbättringsåtgärderna kan du välja att acceptera risken eller den återstående risken.

Vi visar dig alla möjliga förbättringar, oavsett licens, så att du kan förstå bästa praxis för säkerhet och förbättra dina poäng. Din absoluta säkerhetsposition representeras av Secure Score, som förblir densamma oavsett vilka produktlicenser din organisation äger. Tänk på att säkerheten bör vara balanserad med användbarhet, och inte varje rekommendation kan fungera för din miljö.

Din poäng uppdateras i realtid för att återspegla den information som presenteras i visualiseringar och förbättring åtgärd sidor. Secure Score synkroniserar också dagligen för att ta emot systemdata om dina uppnådda poäng för varje åtgärd.

### <a name="how-improvement-actions-are-scored"></a>Hur förbättringsåtgärder görs

Varje förbättringsåtgärd är värd 10 poäng eller mindre. De flesta görs på ett binärt sätt - om du genomför förbättringsåtgärden, som att skapa en ny princip eller aktivera en viss inställning, får du 100% av poängen. För andra förbättringsåtgärder anges punkter som en procentandel av den totala konfigurationen. Till exempel, om förbättringen åtgärd stater du får 30 poäng genom att skydda alla dina användare med multifaktorautentisering och du bara har 5 av 100 totala användare skyddade, skulle du få en partiell poäng på cirka 2 poäng (5 skyddade / 100 totalt * 30 max poäng = 2 poäng partiell poäng).

### <a name="products-included-in-secure-score"></a>Produkter som ingår i Secure Score

För närvarande finns det rekommendationer för Microsoft 365 (inklusive Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP och Cloud App Security. Rekommendationer för andra säkerhetsprodukter kommer snart. Rekommendationerna kommer inte att omfatta alla angreppsytor som är associerade med varje produkt, men de är en bra baslinje. Du kan också markera förbättringsåtgärderna som omfattas av en tredje part eller alternativ begränsning.

## <a name="required-permissions"></a>Nödvändiga behörigheter

Om du vill ha behörighet att komma åt Microsoft Secure Score måste du tilldelas en av följande roller i Azure Active Directory.

### <a name="read-and-write-roles"></a>Läs- och skrivroller

Med läs- och skrivåtkomst kan du göra ändringar och interagera direkt med Secure Score. Du kan också tilldela skrivskyddad åtkomst till andra användare.

* Global administratör
* Säkerhetsadministratör
* Exchange-administratör
* SharePoint-administratör
* Kontoadministratör

### <a name="read-only-roles"></a>Skrivskyddade roller

Med skrivskyddad åtkomst kan du inte redigera status eller anteckningar för en förbättringsåtgärd, redigera poängzoner eller redigera anpassade jämförelser.

* Helpdesk-administratör
* Användaradministratör
* Tjänstadministratör
* Säkerhetsläsare
* Säkerhetsoperatör
* Global läsare

### <a name="graph-api"></a>Api för diagram

Om du vill komma åt Graph API måste du ha något av följande scope utöver en roll:

* SecurityEvents.Read.All (för skrivskyddade roller)
* SecurityEvents.ReadWrite.All (för läs- och skrivroller)

## <a name="gain-visibility-into-your-security-posture"></a>Få insyn i din säkerhetsposition

För att hjälpa dig den information du behöver snabbare är Microsofts förbättringsåtgärder organiserade i grupper:

* Identitet (Azure AD-konton & roller)
* Data (Microsofts informationsskydd)
* Enhet (Microsoft Defender ATP)
* App (e-post- och molnappar, inklusive Office 365 och Microsoft Cloud App Security)
* Infrastruktur (inga förbättringsåtgärder för tillfället)

På översiktssidan för Microsoft Secure Score kan du se hur poäng delas mellan dessa grupper och vilka punkter som är tillgängliga. Översiktssidan är också platsen för att få en helhetsbild av den totala poängen, historisk trend för din säkra poäng med jämförelsemål och prioriterade förbättringsåtgärder som kan vidtas för att förbättra din poäng.

![Startsida för säkra poäng](../../media/secure-score/secure-score-homepage-new.png)


## <a name="take-action-to-improve-your-score"></a>Vidta åtgärder för att förbättra din poäng

På fliken **Förbättringsåtgärder** visas de säkerhetsrekommendationer som åtgärdar möjliga angreppsytor, tillsammans med deras status (för att ta itu med, planerade, risk accepterade, lösas via tredje part, lösas genom alternativ begränsning och slutförd). Du kan söka, filtrera och gruppera alla förbättringsåtgärder.  

### <a name="ranking"></a>Ranking

Rankningen baseras på antalet återstående poäng kvar att uppnå, implementeringssvårigheter, användarpåverkan och komplexitet. De högst rankade förbättringsåtgärderna har ett stort antal punkter kvar med låg svårighet, användarpåverkan och komplexitet.

### <a name="view-improvement-action-details"></a>Visa information om förbättringsåtgärder

När du väljer en viss förbättringsåtgärd visas ett utfällbart utfällbart helsidesutfällbart resultat.  

![Utfällbart exempel](../../media/secure-score/secure-score-improvement-action-details.png)
på förbättringsåtgärd*Bild 2: Exempel på utfällbara förbättringar*

För att slutföra åtgärden har du några alternativ:

* Välj **Hantera** om du vill gå till konfigurationsskärmen och göra ändringen. Du kommer då att få de punkter som åtgärden är värd, synlig i flyga ut. Poäng tar i allmänhet ca 24 timmar att uppdatera.

* Välj **Dela** om du vill kopiera den direkta länken till förbättringsåtgärden eller välj den plattform som du vill dela länken som e-post, Microsoft Teams, Microsoft Planner eller ServiceNow. Genom att välja ServiceNow kan du skapa en ändringsbiljett som visas i ServiceNow och Microsoft 365 security center home. Mer information finns i [Microsoft 365 Security Center och ServiceNow-integrering](tickets.md).

### <a name="choose-an-improvement-action-status"></a>Välj status för förbättringsåtgärder

Välj alla statusar och spela in anteckningar som är specifika för förbättringsåtgärden. De statyer du kan välja är följande:

* **För att ta itu med** - Du inser att förbättringen åtgärder är nödvändiga och planerar att ta itu med det någon gång i framtiden. Det här tillståndet gäller även åtgärder som identifieras som delvis, men inte helt slutförda.
* **Planerad** – Det finns konkreta planer för att slutföra förbättringsåtgärderna.
* **Risk accepteras** - Säkerhet bör alltid balanseras med användbarhet, och inte varje rekommendation kommer att fungera för din miljö. När så är fallet kan du välja att acceptera risken, eller den återstående risken, och inte anta förbättringsåtgärden. Du kommer inte att få några poäng, men åtgärden kommer inte längre att vara synlig i listan över förbättringsåtgärder. Du kan visa den här åtgärden i historiken eller ångra den när som helst.
* **Matchas via tredje part** och **löst genom alternativ begränsning** – Förbättringsåtgärden har redan åtgärdats av ett program eller program från tredje part, eller ett internt verktyg. Du kommer att få de poäng som åtgärden är värd, så din poäng bättre återspeglar din totala säkerhet hållning. Om en tredje part eller ett internt verktyg inte längre täcker kontrollen kan du välja en annan status. Tänk på att Microsoft inte har någon insyn i implementeringens fullständighet om förbättringsåtgärden markeras som någon av dessa statusar.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Åtgärder för förbättring av hot & sårbarhetshantering

För förbättringsåtgärder i kategorin "Enhet" kan du inte välja status. I stället dirigeras du till den tillhörande [& säkerhetsproblemshantering (TVM) i](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) för att vidta åtgärder. Det undantag du väljer och motiveringen som du skriver kommer att vara specifikt för portalen och kommer inte att finnas i Microsoft Secure Score-portalen.

#### <a name="completed-improvement-actions"></a>Slutförda förbättringsåtgärder

Förbättringsåtgärder har en "slutförd" status när alla möjliga punkter för förbättringsåtgärderna har uppnåtts. Slutförda förbättringsåtgärder bekräftas genom Microsoft-data och du kommer inte att kunna ändra status.

### <a name="assess-information-and-review-user-impact"></a>Utvärdera information och granska användarnas påverkan

I avsnittet **Vid ett ögonkast** visas kategorin, attacker som den kan skydda mot och produkten.

**Användareffekten** visar vad användarna kommer att uppleva om förbättringsåtgärden har antagits och **användare som påverkas** visar vem som kommer att uppleva det.

### <a name="implement-the-improvement-action"></a>Genomföra förbättringsåtgärderna

Avsnittet **Implementering** visar eventuella förutsättningar, steg för steg nästa steg för att slutföra förbättringsåtgärden, den aktuella implementeringsstatusen för förbättringsåtgärden och eventuella fler länkar.

Förutsättningar kommer att vara alla licenser som måste erhållas eller åtgärder som måste slutföras innan förbättringsåtgärden åtgärdas. Se till att du har tillräckligt med platser i din licens för att slutföra förbättringsåtgärden och att dessa licenser tillämpas på nödvändiga användare.  

## <a name="track-your-score-history-and-meet-goals"></a>Spåra din poänghistorik och uppnå mål

Du kan visa ett diagram över organisationens poäng över tid på fliken **Historik.** Under diagrammet finns en lista över alla åtgärder som vidtagits i det valda tidsintervallet och deras attribut, till exempel resulterande poäng och kategori. Du kan anpassa ett datumintervall och filtrera efter kategori.

På fliken **Mått & trender** finns det flera diagram och diagram som ger dig större insyn i trender och sätta upp mål. Du kan ange datumintervallet för hela sidan med visualiseringar. Visualiseringarna inkluderar:

* **Zonen Secure Score** – Anpassad baserat på organisationens mål och definitioner av bra, okej och dåliga resultatintervall.
* **Regressionstrend** – En tidslinje med punkter som har gått tillbaka på grund av konfigurations-, användar- eller enhetsändringar.  
* **Jämförelsetrend** – Hur organisationens säkra resultat kan jämföras med andras över tid. Den här vyn kan innehålla rader som representerar poänggenomsnittet för organisationer med liknande platsantal och en anpassad jämförelsevy som du kan ange.
* **Riskacceptanstrend** – Tidslinje för förbättringsåtgärder markerade som "riskgodtagen".
* **Poängändringar** – Antalet uppnådda poäng, poäng som gått tillbaka, tillsammans med den efterföljande poängändringen, i det angivna datumintervallet.

## <a name="risk-awareness"></a>Riskmedvetenhet

Microsoft Secure Score är en numerisk sammanfattning av din säkerhetsposition baserat på systemkonfigurationer, användarbeteende och andra säkerhetsrelaterade mätningar. Det är inte ett absolut mått på hur sannolikt ditt system eller data kommer att brytas. Snarare är det i vilken utsträckning du har antagit säkerhetskontroller i din Microsoft-miljö som kan bidra till att kompensera risken för att brytas. Ingen onlinetjänst är helt immun mot säkerhetsöverträdelser, och säker poäng bör inte tolkas som en garanti mot säkerhetsöverträdelse på något sätt.

## <a name="whats-new"></a>Vad är nytt? 

För att göra Microsoft Secure Score till en bättre representant för din säkerhetsposition har vi gjort vissa ändringar. Mer information om planerade ändringar finns [i Vad som kommer i Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

- Lade till Azure Active Directory-förbättringsåtgärder
- Lade till Azure Advanced Threat Protection improvement-åtgärder
- Stöd för säkerhetsrekommendationer för Microsoft Defender ATP [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alla utgivna säkerhetsrekommendationer från TVM är nu tillgängliga

### <a name="updated-interface-and-functionality"></a>Uppdaterat gränssnitt och funktionalitet

* Alla nya statistik- och trendersvyer för CISO- och leadnivådiskussioner
* Nya sätt att spåra och jämföra din poäng
* Bättre spårning och förståelse för poängregressioner
* Filtrera, tagga, söka och gruppera förbättringsåtgärder
* Hantera mot dina framtida mål med hjälp av resultatprognoser och planerade åtgärder
* Och mer!

## <a name="we-want-to-hear-from-you"></a>Vi vill höra från dig

Om du har några problem, vänligen meddela oss genom att publicera i [security, privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community. Vi övervakar samhället och kommer att ge hjälp.