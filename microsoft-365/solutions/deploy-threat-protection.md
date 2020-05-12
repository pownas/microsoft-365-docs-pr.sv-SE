---
title: Distribuera hotskyddsfunktioner i Microsoft 365
description: Lär dig hur du distribuerar tjänster och funktioner för hotskydd på Microsoft 365 E5.
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 92a2cc7603a1a49be5ee72fc7b6d132ce46e38d7
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160876"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Distribuera hotskyddsfunktioner i Microsoft 365

[Skadlig kod](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)och sofistikerade cyberattacker, till exempel [fillösa hot,](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)är vanligt förekommande. Företagen måste skydda sig själva och sina kunder. Sådana attacker kan orsaka stora problem för din organisation, allt från en förlust av förtroende till ekonomiska elände, affärshotande driftstopp och mycket mer. Det är viktigt att skydda mot hot, men det kan vara svårt att avgöra var organisationen ska fokusera tid, ansträngning och resurser. 

Microsofts säkerhetslösningar är inbyggda i våra produkter och tjänster. Automatiserings- och maskininlärningsfunktioner minskar belastningen på dina säkerhetsteam för att se till att rätt objekt åtgärdas. Och styrkan i Microsofts säkerhetslösningar bygger på biljoner signaler som vi bearbetar varje dag i vår [Intelligent Security Graph](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph). Microsoft 365 säkerhetslösningar inkluderar [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), en lösning som samlar signaler över din e-post, data, enheter och identiteter för att måla en bild av avancerade hot mot din organisation.

Titta på det här videoklippet om du vill ha en översikt över distributionsprocessen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Använd den här artikeln som en guide för att implementera din hotskyddslösning.

## <a name="threat-protection-in-microsoft-365-e5"></a>Hotskydd i Microsoft 365 E5

[Med Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) kan du skydda din organisation med anpassad och inbyggd intelligens. Med hotskyddsfunktionerna i Microsoft 365 E5 kan du identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga åtgärder i dina lokala miljöer och molnmiljöer.

I Microsoft 365 E5 är hotskyddsfunktionerna integrerade som standard. Signaler från varje förmåga ger styrka till den övergripande förmågan att upptäcka och reagera på hot. Den kombinerade uppsättningen funktioner ger det bästa skyddet för organisationer, särskilt multinationella organisationer, jämfört med att köra produkter som inte kommer från Microsoft. Följande bild visar de tjänster och funktioner för hotskydd i Microsoft 365 E5 som beskrivs i den här artikeln.

![Översikt över Microsofts hotskydd](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Så fort du distribuerar någon av de avancerade hotskyddsfunktionerna kan du aktivera Microsoft Threat Protection, som samlar signaler och data på ett ställe. 

![Konceptuell illustration av instrumentpanelen för Microsoft Threat Protection](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

Följande bild visar en rekommenderad sökväg för distribution av dessa enskilda funktioner. 

![M365 hotskyddssignaler](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Lösning/funktioner  |Beskrivning  |
|---------|---------|
|Multifaktorautentisering och villkorsstyrd åtkomst     |Skydda mot komprometterade identiteter och enheter. Börja med detta skydd eftersom det är grundläggande. Konfigurationen som rekommenderas i den här vägledningen innehåller Azure AD Identity Protection som en förutsättning.     |
|Azure Advanced Threat Protection     |  En molnbaserad säkerhetslösning som utnyttjar dina lokala Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga insideråtgärder som riktas mot din organisation. Fokusera på detta nästa eftersom det skyddar din on-prem och din molninfrastruktur, har inga beroenden eller förutsättningar och kan ge omedelbar nytta.       | 
|Office 365 Avancerat skydd     | Skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (webbadresser) och samarbetsverktyg. Skydd för skadlig kod, nätfiske, förfalskning och andra angreppstyper. Detta rekommenderas härnäst eftersom ändringskontroll, migrerande inställningar från det etablerade systemet och andra överväganden kan ta längre tid att distribuera. <br><br>Se till att du även konfigurerar hotskyddsfunktionerna som ingår i alla Office 365-prenumerationer (Exchange Online Protection).       |
|Microsoft Defender Avancerat skydd    | En slutpunktsskyddsplattform som hjälper till att förebygga, upptäcka, undersöka och svara på avancerade hot. Detta tar längre tid att distribuera, men kan göras parallellt med de andra funktionerna om andra administratörer är ansvariga.   |
|Microsoft Cloud App Security     |   En molnåtkomstsäkerhetsmäklare för identifiering, undersökning och styrning. Du kan aktivera detta tidigt för att börja samla in data och insikter. Implementering av information och annat riktat skydd i dina SaaS-appar innebär planering och kan ta längre tid.       | 

> [!TIP]
> Organisationer med flera säkerhetsteam kan implementera dessa funktioner parallellt.

## <a name="deploy-your-threat-protection-solution"></a>Distribuera din hotskyddslösning

Om du vill vara säker på att din organisation har bästa möjliga skydd konfigurerar och distribuerar du säkerhetslösningen så att den innehåller följande steg:

1. [Ställ in principer för multifaktorautentisering och villkorlig åtkomst](#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Konfigurera Avancerat hotskydd för Azure](#step-2-configure-azure-advanced-threat-protection)
3. [Aktivera Microsoft Hotskydd](#step-3-turn-on-microsoft-threat-protection)
4. [Konfigurera avancerat hotskydd för Office 365](#step-4-configure-office-365-advanced-threat-protection)
5. [Konfigurera avancerat hotskydd för Microsoft Defender](#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Konfigurera Säkerhet för Microsoft Cloud-appar](#step-6-configure-microsoft-cloud-app-security)
7. [Övervaka status och vidta åtgärder](#step-7-monitor-status-and-take-actions)
8. [Utbilda användare](#step-8-train-users)

Dina hotskyddsfunktioner kan konfigureras parallellt, så om du har flera säkerhetsteam som ansvarar för olika tjänster kan de konfigurera organisationens skyddsfunktioner samtidigt. Följande diagram illustrerar högnivåprocessen för distribution av hotskyddsfunktioner. 

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Steg 1: Konfigurera principer för multifaktorautentisering och villkorlig åtkomst

[MFA (Multifaktor authentication)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) kräver att användarna verifierar sin identitet med en app för telefonsamtal eller autentiserare. [Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definierar vissa krav som måste uppfyllas för att användare ska komma åt appar och data i Microsoft 365. MFA och principer för villkorlig åtkomst fungerar tillsammans för att skydda din organisation. Om någon till exempel försöker logga in från en mobil enhet med ett konto som inte är aktiverat för MFA och en princip för villkorlig åtkomst kräver att MFA gäller, hindras användaren från att logga in.  

Microsoft har testat och rekommenderar en specifik uppsättning principer för villkorlig åtkomst och relaterade principer för att skydda åtkomsten till alla Dina SaaS-program, särskilt Microsoft 365. Principer rekommenderas för grundläggande, känsligt och starkt reglerat skydd. Börja med att implementera principerna för baslinjeskydd. 


[![Vanliga principer för att konfigurera identitets- och enhetsåtkomst](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)
[Se en större version av den här avbildningen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Så här implementerar du baslinjeskydd för Microsoft 365

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Konfigurera förutsättningar, inklusive Azure Identity Protection](../enterprise/identity-access-prerequisites.md).
2. Konfigurera vanliga principer för [identitets- och enhetsåtkomst](../enterprise/identity-access-policies.md) för baslinjeskydd.
3. Konfigurera principer för [gästanvändare](../enterprise/identity-access-policies-guest-access.md), [Microsoft Teams,](../enterprise/teams-access-policies.md) [Exchange Online](../enterprise/secure-email-recommended-policies.md)och [SharePoint Online och OneDrive](../enterprise/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Mer information om hur du skyddar identiteter

- [Konfigurationer av identiteter och enhetsåtkomst](../enterprise/microsoft-365-policies-configurations.md)
- [Säkerhetsvägledning för Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-azure-advanced-threat-protection"></a>Steg 2: Konfigurera Avancerat hotskydd i Azure

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) är en molnbaserad säkerhetslösning som fungerar med dina lokala [Azure Active Directory-signaler](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga insideråtgärder som riktas mot din organisation.

Azure ATP möjliggör säkerhetsåtgärder (SecOps) analytiker och säkerhetspersonal som kämpar för att upptäcka avancerade attacker i hybridmiljöer för att:
- Övervaka användare, entitetsbeteende och aktiviteter med utbildningsbaserad analys.
- Skydda användaridentiteter och inloggningsuppgifter som lagras i Active Directory.
- Identifiera och undersök misstänkta användaraktiviteter och avancerade attacker under alla attackfaserna.
- Ge tydlig information om incidenten på en enkel tidslinje för snabb prioritering.

### <a name="to-set-up-azure-atp"></a>Så här konfigurerar du Azure ATP

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Konfigurera Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) för att skydda dina primära miljöer.
2. Skydda alla [domänkontrollanter](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) och [skogar.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integrera [Azure ATP-aviseringar](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) i ditt arbetsflöde för säkerhetsåtgärder (SecOps).

### <a name="more-information-about-azure-atp"></a>Mer information om Azure ATP

- [Vad är Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Introduktion till Azure ATP](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Azure ATP-distribution](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-threat-protection"></a>Steg 3: Aktivera Microsoft Threat Protection

[Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) kombinerar signaler och orkestrerar funktioner till en enda lösning. Med den integrerade Microsoft Threat Protection-lösningen kan säkerhetspersonal sy ihop de hotsignaler som var och en av dessa produkter tar emot och avgöra hotets fulla omfattning och inverkan. hur den kom in i miljön, vad den påverkas och hur den för närvarande påverkar organisationen. Microsoft Threat Protection vidtar automatiska åtgärder för att förhindra eller stoppa angrepp och självläker affected postlådor, slutpunkter och användaridentiteter.

Microsoft Threat Protection förenar aviseringar, incidenter, automatisk undersökning och svar och avancerad jakt över arbetsbelastningar (Azure ATP, Office 365 ATP, Microsoft Defender ATP och Microsoft Cloud App Security) till en enda glasruta. När du har konfigurerat en eller flera av dina avancerade hotskyddstjänster aktiverar du Microsoft Threat Protection. Nya funktioner läggs till kontinuerligt i Microsoft Threat Protection. överväga att anmäla sig för att ta emot förhandsgranskningsfunktioner.

### <a name="to-set-up-microsoft-threat-protection"></a>Så här konfigurerar du Microsoft Threat Protection

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Granska förutsättningarna](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Aktivera Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. [Anmäl dig för förhandsgranskningsfunktioner](https://docs.microsoft.com/microsoft-365/security/mtp/preview).

### <a name="more-information-about-microsoft-threat-protection"></a>Mer information om Microsofts hotskydd

- [Vad är Microsoft Hotskydd?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Nyheter i Microsoft Hotskydd](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-office-365-advanced-threat-protection"></a>Steg 4: Konfigurera avancerat hotskydd för Office 365

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) skyddar din organisation mot skadliga hot i e-postmeddelanden (bifogade filer och webbadresser), Office-dokument och samarbetsverktyg. I följande tabell visas funktioner och funktioner för Office 365 ATP som ingår i Microsoft 365 E5:

|||
|---|---|
|Konfigurations-, skydds- och identifieringsfunktioner|Automatisering, utredning, sanering och utbildningskapacitet|
|[Säkra bifogade filer](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Säkra dokument](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[ATP-skydd mot nätfiske](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Hotspårare](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Hotutforskaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Automatiska undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Attacksimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Med Office 365 ATP kan personer i hela organisationen kommunicera och samarbeta säkrare, med hotskydd för sitt e-postinnehåll och Office-dokument.

### <a name="to-set-up-office-365-atp"></a>Så här konfigurerar du Office 365 ATP

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Konfigurera Office 365 ATP-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
2. [Visa och använda dina Office 365 ATP-rapporter](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Använd hotutrednings- och svarsfunktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-office-365-atp"></a>Mer information om Office 365 ATP

- [Översikt över Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Nyheter i Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-advanced-threat-protection"></a>Steg 5: Konfigurera avancerat hotskydd för Microsoft Defender

[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP) skyddar dina organisationers enheter (även kallade slutpunkter) från cyberhot, avancerade attacker och dataintrång. Säkerhetsteam kan vara mer effektiva när det gäller att hantera säkerheten för sina slutpunkter. Robusta verktyg hjälper organisationer att hålla jämna steg med opatrullerade system med hjälp av sårbarhetsidentifiering med [hot- och sårbarhetshantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Automatiserade identifierings- och reparationsfunktioner, till exempel [minskning av angreppsytor,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction) [nästa generations skydd,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)identifiering och svar för [slutpunkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)och [automatisk undersökning och reparation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) hjälper till att skydda dina enheter från skadlig kod. Utöver dessa funktioner kan kunder få proaktiva meddelanden och rådgöra med Microsoft Threat Experts on demand, som en del av opt-in-hanterade jakttjänsten. 


### <a name="set-up-microsoft-defender-atp"></a>Konfigurera Microsoft Defender ATP

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Förbered din Microsoft Defender ATP-distribution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Konfigurera microsoft defender ATP-distributionen](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Ombord på Microsoft Defender ATP-tjänsten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Slutför de högsta administrativa säkerhetsuppgifterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation).

### <a name="more-information-about-microsoft-defender-atp"></a>Mer information om Microsoft Defender ATP

- [Läs mer om Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection).
- [Prova Microsoft Defender ATP-utvärderingslabbet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Steg 6: Konfigurera Säkerhet för Microsoft Cloud-appar

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) är en Cloud Access Security Broker som stöder logginsamling, API-kopplingar och omvänd proxy. Microsoft Cloud App Security ger omfattande synlighet, kontroll över dataresor och sofistikerade analyser för att identifiera och bekämpa cyberhot i alla dina molntjänster. Med Microsoft Cloud App Security kan din säkerhetsoperation skydda organisationens känsliga information, skydda mot cyberhot och avvikelser, upptäcka och övervaka appar som kommer åt organisationens data och se till att organisationens molnappar uppfyller efterlevnadskraven.

### <a name="set-up-microsoft-cloud-app-security"></a>Konfigurera Security för Microsoft Cloud App

![Process för distribution av hotskyddsfunktioner](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Ställ in portalen och andra grundläggande krav](https://docs.microsoft.com/cloud-app-security/general-setup).
2. [Konfigurera molnidentifiering](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) och [ansluta appar](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Distribuera appkontroll för villkorlig åtkomst för utvalda appar](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Använd undersökningsverktygen och instrumentpanelerna](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mer information om Microsoft Cloud App Security

- [Granska nya funktioner och funktioner](https://docs.microsoft.com/cloud-app-security/release-notes).
- [Läs mer om Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Steg 7: Övervaka status och vidta åtgärder

När du har konfigurerat och distribuerat dina tjänster och funktioner för hotskydd är nästa steg att övervaka hotidentifieringar och vidta lämpliga åtgärder. Den bästa utgångspunkten är Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)), där du kan övervaka och hantera säkerhet över dina Microsoft-identiteter, data, enheter, appar och infrastruktur. 

:::image type="content" source="../media/solutions-architecture-center/m365-security-center.png" alt-text="Microsoft 365 Säkerhetscenter":::

Microsoft 365-säkerhetscentret är särskilt avsett för säkerhetsadministratörer och säkerhetsoperationsteam. I säkerhetscentret Microsoft 365 kan du:
- Visa organisationens övergripande säkerhetshälsa med [Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Övervaka och visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) om status för dina identiteter, data, enheter, appar och infrastruktur.
- Anslut punkterna på aviseringar via [incidenter](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Använd [automatisk undersökning och reparation](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) för att hantera hot.
- [Proaktivt jakt efter hot](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview), till exempel intrångsförsök eller intrångsaktivitet som påverkar din e-post, data, enheter och identiteter.
- [Förstå de senaste attackkampanjerna](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) och teknikerna med hotanalys.
- ... och mycket mer!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mer information om säkerhetscentret microsoft 365

- [Kom igång med säkerhetscentret microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Övervaka och visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Se säkerhetsportalerna i Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Steg 8: Utbilda användare

Utbildningsanvändare kan spara användarna och säkerhetsoperationsteamet mycket tid och frustration. Kunniga användare är mindre benägna att öppna bilagor eller klicka på länkar i tvivelaktiga e-postmeddelanden, och de är mer benägna att undvika misstänkta webbplatser. 

Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ger utmärkt vägledning om hur du skapar en stark kultur av säkerhetsmedvetenhet inom din organisation, inklusive utbildning användare att identifiera phishing-attacker. 

Microsoft 365 innehåller följande resurser för att informera användare i organisationen:

|Koncept  |Resurser  |
|---------|---------|
|Microsoft 365     |[Anpassningsbara utbildningsvägar](https://docs.microsoft.com/office365/customlearning/) <p>Dessa resurser kan hjälpa dig att sätta ihop utbildning för slutanvändare i din organisation        |
|Microsoft 365 Säkerhet |[Utbildningsmodul: Skydda din organisation med inbyggd, intelligent säkerhet från Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Med den här modulen kan du beskriva hur Microsoft 365-säkerhetsfunktioner fungerar tillsammans och formulera fördelarna med dessa säkerhetsfunktioner. |
|Multifaktorautentisering     | [Tvåstegsverifiering: Vad är den ytterligare verifieringssidan?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i din organisation.    |

Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar de åtgärder som beskrivs i den här artikeln: [Skydda ditt konto och dina enheter från hackare och skadlig kod](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Dessa åtgärder omfattar:
- Använda starka lösenord
- Skydda enheter 
- Aktivera säkerhetsfunktioner på Windows 10- och Mac-datorer (för ohanterade enheter)
    
Microsoft rekommenderar också att användarna skyddar sina personliga e-postkonton genom att vidta de åtgärder som rekommenderas i följande artiklar:
- [Skydda ditt Outlook.com e-postkonto](https://support.microsoft.com/en-us/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)