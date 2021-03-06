---
title: Anvisningar för att konfigurera hot Protection-funktioner i Microsoft 365
description: Lär dig hur du distribuerar hot Protection Services och funktioner i Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: f3fa5c82efad0a51adf5e798bd89860e78256e15
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845318"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Konfigurera hot Protection-funktioner i Microsoft 365

Följ de här stegen för att konfigurera hotets skydd i Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Steg 1: konfigurera principer för multifaktorautentisering och villkorsstyrd åtkomst

[Multi-Factor autentisering](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) kräver att användare verifierar sin identitet med ett telefonsamtal eller en autentiseringsserver. [Principer för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) definierar vissa krav som måste uppfyllas för att användarna ska kunna komma åt appar och data i Microsoft 365. Principer för MFA och villkorsstyrd åtkomst samarbetar för att skydda din organisation. Om någon försöker att logga in från en mobil enhet med ett konto som inte är aktiverat för MFA och en princip för villkorsstyrd åtkomst kräver MFA för att det ska fungera, kommer användaren att förhindras från att logga in.  

Microsoft har testat och rekommenderar en specifik uppsättning villkors åtkomst och relaterade principer för att skydda åtkomst till alla dina SaaS-program, särskilt Microsoft 365. Principer rekommenderas för baseline, känsligheten och starkt reglerat skydd. Börja med att implementera principer för baseline-skyddet. 


[ ![ Vanliga principer för att konfigurera åtkomst till identiteter och enheter](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [se en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Så här implementerar du baseline Protection för Microsoft 365

![Process för distribution av original plan för skydd](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Konfigurera förutsättningar, inklusive Azure Identity Protection](../security/office-365-security/identity-access-prerequisites.md).
2. [Konfigurera vanliga principer för identitets-och enhets åtkomst](../security/office-365-security/identity-access-policies.md) för baseline-skyddet.
3. Konfigurera principer för [gäst användare](../security/office-365-security/identity-access-policies-guest-access.md), [Microsoft Teams](../security/office-365-security/teams-access-policies.md), [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)och [SharePoint Online och OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Mer information om hur du skyddar identiteter

- [Konfigurationer för identitets- och enhetsåtkomst](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Säkerhets vägledning för Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Steg 2: Konfigurera Microsoft Defender för identitet

[Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) är en molnbaserad säkerhets lösning som fungerar med dina lokala [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) -signaler för att identifiera, upptäcka och undersöka avancerade hot, kompromissade identiteter och skadliga Insider-åtgärder som riktas till din organisation.

Med Microsoft Defender för identitet kan du använda säkerhets åtgärder (SecOps)-analytiker och säkerhets experter för att upptäcka avancerade attacker i hybrid miljöer för att:
- Övervaka användare, enheter och aktiviteter med Learning-baserad analys.
- Skydda användaridentiteter och inloggningsuppgifter som lagras i Active Directory.
- Identifiera och undersök misstänkta användaraktiviteter och avancerade attacker under alla attackfaserna.
- Ge tydlig information om incidenten på en enkel tidslinje för snabb prioritering.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Konfigurera Microsoft Defender för identitet

![Process för distribution av Microsoft Defender för identitet](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Konfigurera Microsoft Defender för identitet](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) för att skydda dina primära miljöer.
2. Skydda alla [domänkontrollanter](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) och [skogar](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest).
3. Integrera [Microsoft Defender för identitets varningar](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) i arbets flödet för säkerhets åtgärder (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Mer information om Microsoft Defender för identitets

- [Vad är Microsoft Defender för identitet?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Video: Introduktion till Microsoft Defender för identitet](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender för identitets distribution](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Steg 3: aktivera Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) kombinerar signaler och dirigerar funktioner till en enda lösning. Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperterna häfta ihop hotet så att dessa produkter får och fastställer den fulla omfattningen och påverkan av hotet; hur den har kommit till miljön, vad den påverkar och hur den för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv läka berörda post lådor, slut punkter och användar identiteter.

Microsoft 365 Defender interagerar med aviseringar, händelser, automatiserade undersökningar och svar samt avancerad jakt på arbets belastning (Microsoft Defender för identitets-, Microsoft Defender för Office 365, Microsoft Defender för slut punkt och Microsoft Cloud App Security) i en enda fönster ruta med glas upplevelsen. När du har konfigurerat en eller flera av dina Defender för Office 365-tjänster aktiverar du Microsoft 365 Defender. Nya funktioner läggs till hela tiden till Microsoft 365 Defender; Tänk på vanligt om du vill ha funktioner för förhands granskning.

### <a name="to-set-up-microsoft-365-defender"></a>Konfigurera Microsoft 365 Defender

![Process för distribution av Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Granska kraven](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).
2. [Aktivera Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).
3. [Anmäl dig för förhands gransknings funktioner](https://docs.microsoft.com/microsoft-365/security/mtp/preview).

### <a name="more-information-about-microsoft-365-defender"></a>Mer information om Microsoft 365 Defender

- [Vad är Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Nyheter i Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Steg 4: Konfigurera Microsoft Defender för Office 365

[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) skyddar din organisation mot skadliga hot i e-postmeddelanden (bilagor och URL: er), Office-dokument och samarbets verktyg. Följande tabell innehåller funktioner och funktioner i Microsoft Defender för Office 365 som ingår i Microsoft 365 E5:

|Konfiguration, skydd och identifiering|Automatisering, undersökning, reparation och utbildning|
|---|---|
|[Säkra bifogade filer](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Säkra länkar](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Säkra dokument](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Anti-nätfiske i Defender för Office 365-skydd](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Hotspårare](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Hotutforskaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Automatiska undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Attacksimulator](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Med Microsoft Defender för Office 365 kan folk i hela organisationen kommunicera och samar beta säkrare, med hot skydd mot deras e-postinnehåll och Office-dokument.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Konfigurera Microsoft Defender för Office 365

![Distribuera Microsoft Defender för Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. Konfigurera [och konfigurera Microsoft Defender för Office 365-principer](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).
2. [Visa och Använd Microsoft Defender för Office 365-rapporter](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).
3. [Använd hot-undersökningar och svars funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Mer information om Microsoft Defender för Office 365

- [Översikt över Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Nyheter i Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Steg 5: Konfigurera Microsoft Defender för slut punkten

[Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection) skyddar dina organisationers enheter (kallas även slut punkter) från Cyberthreats, avancerade attacker och data brott. Säkerhets team kan vara mer effektivt när det gäller att hantera deras slut punkter. Robusta verktyg hjälper organisationer att hålla kontakten med hjälp av sårbarhets avkänning med [hot-och sårbarhets hantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Automatiska identifierings-och reparations funktioner, till exempel [reducering av attack yta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction), [nästa generationens skydd](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10), [slut punkts avkänning och svar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)samt [Automatisk undersökning och reparations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) hjälp skyddar dina enheter från skadlig program vara. Med de här funktionerna kan kunderna få proaktiva meddelanden och råd fråga Microsoft Threat-experter på begäran, som en del av den bevarade tjänsten för att hanterade tjänster. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Konfigurera Microsoft Defender för slut punkt

![Process för distribution av Microsoft Defender för slut punkt](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Förbereda en distribution av Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases).
2. [Konfigurera Microsoft Defender för slut punkts distribution](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Inbyggd till Microsoft Defender för slut punkts tjänst](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding).
4. [Utför de viktigaste administrativa aktiviteterna](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation).

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Mer information om Microsoft Defender för slut punkten

- [Läs mer om Microsoft Defender för slut punkter](https://docs.microsoft.com/windows/security/threat-protection).
- [Testa utvärderings versionen av Microsoft Defender för slut punkten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Steg 6: Konfigurera säkerhet för Microsoft Cloud App

[Säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security) är en säkerhets koordinator för moln åtkomst som stöder loggnings insamling, API-kopplingar och omvänd proxy. Säkerhet för Microsoft Cloud app ger stor insyn, kontroll över data resor och avancerad analys för att identifiera och bekämpa Cyberthreats i alla dina moln tjänster. Med säkerhet för Microsoft Cloud App kan säkerhets åtgärderna skydda din organisations känsliga information, skydda dig mot Cyberthreats och avvikelser, upptäcka och övervaka appar som har till gång till organisationens data och se till att organisationens moln program uppfyller kraven.

### <a name="set-up-microsoft-cloud-app-security"></a>Konfigurera säkerhet för Microsoft Cloud App

![Process för distribution av säkerhets funktioner för Microsoft Cloud App](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Ställ in portalen och andra grundläggande krav](https://docs.microsoft.com/cloud-app-security/general-setup).
2. [Konfigurera identifiering av moln](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) och [ansluta appar](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Distribuera program kontroll för villkorsstyrd åtkomst för aktuella program](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).
4. [Använd undersöknings verktyg och instrument paneler](https://docs.microsoft.com/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Mer information om Microsoft Cloud App Security

- [Granska nya funktioner och möjligheter](https://docs.microsoft.com/cloud-app-security/release-notes).
- [Läs mer om säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Steg 7: övervaka status och utföra åtgärder

När du har konfigurerat och distribuerat skydds tjänster och-kapacitet, är nästa steg att övervaka hotets identifieringar och vidta lämpliga åtgärder. Din bästa start punkt är Microsoft 365 säkerhets Center ( [https://security.microsoft.com](https://security.microsoft.com) ), där du kan övervaka och hantera säkerhet för dina Microsoft-identiteter, data, enheter, appar och infrastruktur. 

![Microsoft 365 Säkerhetscenter](../media/solutions-architecture-center/m365-security-center.png)

Säkerhets Center för säkerhets administratörer och säkerhets åtgärder i Microsoft 365. I Microsoft 365 säkerhets Center kan du:
- Se hela din organisations säkerhets tillstånd med [säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).
- [Övervaka och Visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) om status för dina identiteter, data, enheter, appar och infrastruktur.
- Koppla punkterna på aviseringar via [händelser](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue).
- Använd [Automatisk undersökning och](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) åtgärda för att adressera hot.
- Har varit [inaktive rad för att](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)skydda din e-post, dina data, enheter och identiteter.
- [Förstå de senaste angrepps kampanjerna](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) och teknikerna med Threat Analytics.
- ... och mer!

### <a name="more-information-about-the-microsoft-365-security-center"></a>Mer information om Microsoft 365 säkerhets Center

- [Komma igång med Microsoft 365 säkerhets Center](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).
- [Övervaka och Visa rapporter](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting).
- [Visa säkerhets portaler i Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals).

## <a name="step-8-train-users"></a>Steg 8: utbilda användare

Utbildnings användare kan spara dina användare och säkerhets arbets gruppen på ett och samma gång. Smarta användare är mindre troligt att öppna bifogade filer eller klicka på länkar i tveksamma e-postmeddelanden och det är mer sannolikt att misstänkta webbplatser undviks. 

Det här är en utmärkt vägledning i Harvard Kennedy School [Cybersecurity-kampanjen](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) med att skapa en starkt kultur av säkerhets medvetenhet inom din organisation, inklusive utbildnings användare för att identifiera nätfiske-attacker. 

Microsoft 365 tillhandahåller följande resurser för att hjälpa användare i organisationen:

|Symboliserar konceptet  |Resurser  |
|---------|---------|
|Microsoft 365     |[Anpassningsbara Learning-vägar](https://docs.microsoft.com/office365/customlearning/) <p>De här resurserna hjälper dig att hålla ihop utbildning för slutanvändare i din organisation        |
|Microsoft 365 Säkerhetscenter |[Kodmodul: skydda din organisation med inbyggd, intelligent säkerhet från Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Med den här modulen kan du beskriva hur säkerhetsfunktionerna i Microsoft 365 fungerar tillsammans och för att Articulate fördelarna med de här säkerhetsfunktionerna. |
|Multifaktorautentisering     | [Tvåstegsverifiering: Vad är sidan för ytterligare verifiering?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Den här artikeln hjälper slutanvändarna att förstå vad multifaktorautentisering är och varför den används i din organisation.    |

Utöver den här vägledningen rekommenderar Microsoft att användarna vidtar åtgärderna som beskrivs i den här artikeln: [skydda ditt konto och dina enheter från hackare och skadlig program vara](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Dessa åtgärder inkluderar:
- Använda starka lösen ord
- Skydda enheter 
- Aktivera säkerhetsfunktioner på Windows 10-och Mac-datorer (för ohanterade enheter)
    
Microsoft rekommenderar också att användare skyddar sina privata e-postkonton genom att vidta åtgärder som rekommenderas i följande artiklar:
- [Skydda ditt Outlook.com-e-postkonto](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Skydda ditt Gmail-konto med tvåstegsverifiering](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
