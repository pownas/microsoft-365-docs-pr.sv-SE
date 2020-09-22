---
title: List API för incidenter i Microsoft Threat Protection
description: Lär dig hur du felvisar API för incidenter i Microsoft Threat Protection
keywords: lista, incident, incidenter, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 54f5ba640ecc175e78c7087df8016e9b715f17f7
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775117"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a>List API för incidenter i Microsoft Threat Protection

**Gäller för:**

- Microsoft Hotskydd

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.


## <a name="api-description"></a>API-Beskrivning

Med incident-API kan du sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity-svar. Den exponerar en mängd händelser som har flaggats från enheter, e-postkonton och användare i nätverket, inom det tidsintervall som du angav i miljön. De senaste incidenterna visas högst upp i listan. Varje händelse innehåller en matris med relaterade aviseringar och tillhör deras relaterade enheter.

<br>API: et stöder följande **OData** -operatorer.
<br>```$filter``` för: ```lastUpdateTime``` , ```createdTime``` ```status``` och ```assignedTo``` Egenskaper.
<br>```$top``` med max värdet **100**
<br>```$skip```

## <a name="limitations"></a>Begränsningar

1. Maximal sid storlek är **100-incidenter**.
2. Maximal taxa för förfrågningar är **50 samtal per minut** och **1500 samtal per timme**.

## <a name="permissions"></a>Behörigheter

En av följande behörigheter krävs för att kunna ringa detta API. Om du vill veta mer, inklusive hur du väljer behörigheter, se [åtkomst till Microsoft Threat Protection API: er](api-access.md)

Behörighets typ |   Tillåtelse  |   Visnings namn för behörighet
:---|:---|:---
Program |   Incident. Read. all | "Läs alla händelser"
Program |   Incident. ReadWrite. alla | "Läs och skriv alla händelser"
Delegerat (arbets-eller skol konto) | Incident. Read | "Läsfel"
Delegerat (arbets-eller skol konto) | Incident. ReadWrite | "Läs-och skriv händelser"

> [!Note]
> När du erhåller ett token med användar uppgifter:
> - Användaren måste ha behörigheten Visa för händelser i portalen.
> - Svaret innehåller endast händelser som användaren utsätts för.

## <a name="http-request"></a>HTTP-begäran

```
GET /api/incidents
```

## <a name="request-headers"></a>Begärandehuvuden

Namn | Type (Typ) | Beskrivning
:---|:---|:---
Bemyndigande | Sträng | Bearer {token}. **Obligatoriskt**.


## <a name="request-body"></a>Brödtext
Ingen.

## <a name="response"></a>Interimssvar
Om det lyckas returnerar den här metoden 200 OK och en lista med [incidenter](api-incident.md) i svars texten.

## <a name="schema-mapping"></a>Schema mappning

| Fält namn                                | Beskrivning                                                                                                                                                                                                                                                                                                                                                                                | Exempel värde                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Metadata för incident**                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| incidentId                                | Unik identifierare som representerar incidenten.                                                                                                                                                                                                                                                                                                                                                | 924565                                                                                                                                                                                                                                            |
| redirectIncidentId                        | Endast i händelse av att en olycka grupperas tillsammans med en annan incident, som en del av bearbetnings logiken för olyckor.                                                                                                                                                                                                                                                           | 924569                                                                                                                                                                                                                                            |
| incidentName                              | Ett sträng värde är tillgängligt för alla händelser.                                                                                                                                                                                                                                                                                                                                                  | Utpressnings tro aktivitet                                                                                                                                                                                                                               |
| createdTime                               | Tidpunkt då incidenten först skapades.                                                                                                                                                                                                                                                                                                                                                      | 2020 – 09-06T14:46:57.0733333 Z                                                                                                                                                                                                                      |
| lastUpdateTime                            | Tidpunkt då incidenten senast uppdaterades på Server delen.<br> Det här fältet kan användas när du ställer in parametern request för det tidsintervall som incidenter hämtas.                                                                                                                                                                                                                      | 2020 – 09-06T14:46:57.29 Z                                                                                                                                                                                                                           |
| Tilldelat                                | Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.                                                                                                                                                                                                                                                                                                                         | secop2@contoso.com                                                                                                                                                                                                |
| nomenklatur                            | Specifikation för incidenten. Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive*                                                                                                                                                                                                                                                                           | Okänd                                                                                                                                                                                                                                           |
| bedömning                             | Anger hur incidenten ska visas. Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *övrigt*                                                                                                                                                                                                                | NotAvailable                                                                                                                                                                                                                                      |
| status                                    | Kategorisera incidenter (som *aktiva*eller *löst*). Det hjälper dig att organisera och hantera ditt svar på tillbud.                                                                                                                                                                                                                                                                  | Aktiva                                                                                                                                                                                                                                            |
| allvarlighets grad                                  | Anger möjlig påverkan på till gångar. Ju högre allvarlighets grad desto större effekt. Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.<br>Något av följande värden: *information*, *Low*, * medium och *High*.                                                                                                                                | Risk                                                                                                                                                                                                                                            |
| taggen                                      | Matris med anpassade taggar som är kopplade till en olycka, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| larm                                    | Lista över alla aviseringar som är relaterade till incidenten och annan information, till exempel allvarlighets grad, enheter som ingick i aviseringen, källan till aviseringarna.                                                                                                                                                                                                                     | \[\] (se informationen om aviserings fälten nedan)                                                                                                                                                                                                          |
| **Metadata för aviseringar**                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| alertId                                   | Unik identifierare som representerar aviseringen                                                                                                                                                                                                                                                                                                                                                   | caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC                                                                                                                                                                                                            |
| incidentId                                | Unik identifierare som representerar den incident som aviseringen är associerad med                                                                                                                                                                                                                                                                                                                  | 924565                                                                                                                                                                                                                                            |
| serviceSource                             | Tjänsten som aviseringen kommer från, till exempel Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP eller Office 365 ATP.                                                                                                                                                                                                                                                                     | MicrosoftCloudAppSecurity                                                                                                                                                                                                                         |
| creationTime                              | Tid då aviseringen först skapades.                                                                                                                                                                                                                                                                                                                                                         | 2020 – 09-06T14:46:55.7182276 Z                                                                                                                                                                                                                      |
| lastUpdatedTime                           | Tid när aviseringen senast uppdaterades på Server delen.                                                                                                                                                                                                                                                                                                                                           | 2020 – 09-06T14:46:57.2433333 Z                                                                                                                                                                                                                      |
| resolvedTime                              | Tid då aviseringen löstes.                                                                                                                                                                                                                                                                                                                                                              | 2020 – 09-10T05:22:59Z                                                                                                                                                                                                                              |
| firstActivity                             | Tid när aviseringen först rapporterades om att aktiviteten uppdaterades på Server delen.                                                                                                                                                                                                                                                                                                                             | 2020 – 09-04T05:22:59Z                                                                                                                                                                                                                              |
| titelfält                                     | Ett kort värde som är tillgängligt för varje varning.                                                                                                                                                                                                                                                                                                                                                     | Utpressnings tro aktivitet                                                                                                                                                                                                                               |
| beskrivning                               | Sträng värde som beskriver varje varning.                                                                                                                                                                                                                                                                                                                                                        | User test user2 (testUser2@contoso.com) manipulerar 99-filer med flera tillägg som slutar med det ovanliga tillägget *Herunterladen*. Det här är ett ovanligt antal fil ändringar och är ett exempel på en potentiell utpressnings tro Jan attack. |
| typ                                  | Visuell och numerisk vy av hur långt angreppet har gått under Kill-kedjan. Justerad till [MITREn att&CK™ Framework](https://attack.mitre.org/).                                                                                                                                                                                                                           | Påverkan                                                                                                                                                                                                                                            |
| status                                    | Kategorisera aviseringar (som *nya*, *aktiva*eller *stängda*). Det hjälper dig att organisera och hantera dina svar på aviseringar.                                                                                                                                                                                                                                                                   | Nya                                                                                                                                                                                                                                               |
| allvarlighets grad                                  | Anger möjlig påverkan på till gångar. Ju högre allvarlighets grad desto större effekt. Vanligt vis kräver objekt med högre allvarlighets grad den omedelbara uppmärksamheten.<br>Något av följande värden: *information*, *Low*, * medium och *High*.                                                                                                                                   | Risk                                                                                                                                                                                                                                            |
| investigationId                           | Det automatiska undersöknings-ID: t som utlöste den här varningen.                                                                                                                                                                                                                                                                                                                                | 1234                                                                                                                                                                                                                                              |
| investigationState                        | Information om utredningens aktuella status. Något av följande: *Okänt*, *avslutat*, *SuccessfullyRemediated*, *ofarligt*, *misslyckat*, *PartiallyRemediated*, *pågående*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *köade*, *InnerFailure*, *PreexistingAlert*, *,* *UnsupportedAlertType*, *SuppressedAlert*. | UnsupportedAlertType                                                                                                                                                                                                                              |
| nomenklatur                            | Specifikation för incidenten. Egenskaps värden är: *okänd*, *FalsePositive*, *TruePositive* eller *Null*                                                                                                                                                                                                                                                                   | Okänd                                                                                                                                                                                                                                           |
| bedömning                             | Anger hur incidenten ska visas. Egenskaps värden är: *NotAvailable*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *other* eller  *Null*                                                                                                                                                                                                     | Apt                                                                                                                                                                                                                                               |
| Tilldelat                                | Ägaren till incidenten eller *Null* om ingen ägare är tilldelad.                                                                                                                                                                                                                                                                                                                            | secop2@contoso.com                                                                                                                                                                                                 |
| actorName                                 | Aktivitets gruppen, om den är kopplad till den här aviseringen.                                                                                                                                                                                                                                                                                                                                        | UTTRYCKT                                                                                                                                                                                                                                             |
| threatFamilyName                          | Hot familj som är associerad med den här aviseringen.                                                                                                                                                                                                                                                                                                                                                   | kan                                                                                                                                                                                                                                              |
| mitreTechniques                           | Angrepps metoderna, som är justerade med [MITREn att&CK](https://attack.mitre.org/)™ Framework.                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| anordningar                                   | Alla enheter där aviseringar relaterade till händelsen skickades.                                                                                                                                                                                                                                                                                                     | \[\] (se informationen om entitetsfält nedan)                                                                                                                                                                                                         |
| **Enhets format**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| DeviceId                                  | Enhets-ID enligt Microsoft Defender ATP.                                                                                                                                                                                                                                                                                                                                                       | 24c222b0b60fe148eeece49ac83910cc6a7ef491                                                                                                                                                                                                          |
| aadDeviceId                               |  Enhets-ID enligt [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD). Endast tillgängligt för domänanslutna enheter.                                                                                                                                                                                                                                                                                                                              | kan                                                                                                                                                                                                                                              |
| deviceDnsName                             | Det fullt kvalificerade domän namnet för enheten.                                                                                                                                                                                                                                                                                                                                                                        | user5cx.middleeast.corp.contoso.com                                                                                                                                                                                                    |
| osPlatform                                | Den OS-plattform enheten körs på.                                                                                                                                                                                                                                                                                                                                                                     | WindowsServer2016                                                                                                                                                                                                                                 |
| osBuild                                   | Versions versionen för det OS-enheten.                                                                                                                                                                                                                                                                                                                                                                | 14393                                                                                                                                                                                                                                             |
| rbacGroupName                             | Den [rollbaserad åtkomst kontroll](https://docs.microsoft.com/azure/role-based-access-control/overview) gruppen som är associerad med enheten.                                                                                                                                                                                                                                                                                                                             | WDATP-Ring0                                                                                                                                                                                                                                       |
| firstSeen                                 | Tid då enheten först visades.                                                                                                                                                                                                                                                                                                                                                           | 2020 – 02-06T14:16:01.9330135 Z                                                                                                                                                                                                                      |
| healthStatus                              | Enhetens hälso status.                                                                                                                                                                                                                                                                                                                                                                        | Aktiva                                                                                                                                                                                                                                            |
| riskScore                                 | Risk poängen för enheten.                                                                                                                                                                                                                                                                                                                                                                       | Högsta                                                                                                                                                                                                                                              |
| posterna                                  | Alla enheter som har identifierats som en del av eller är relaterade till en viss avisering.                                                                                                                                                                                                                                                                                | \[\] (se informationen om entitetsfält nedan)                                                                                                                                                                                                         |
| **Enhets format**                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| Angiven                                | Enheter som har identifierats som en del av eller är relaterade till en viss avisering.<br>Egenskaps värden är: *användare*, *IP*, *URL*, *fil*, *process*, *post låda, e*- *postmeddelande*, *kluster*, *register*                                                                                                                                                                                                     | Användare                                                                                                                                                                                                                                              |
| SHA1                                      | Tillgängligt om entityType är *File*.<br>Fil-hash för aviseringar som är kopplade till en fil eller process.                                                                                                                                                                                                                                                                                    | 5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd                                                                                                                                                                                                          |
| sha256                                    | Tillgängligt om entityType är *File*.<br>Fil-hash för aviseringar som är kopplade till en fil eller process.                                                                                                                                                                                                                                                                                    | 28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043                                                                                                                                                                                  |
| Datafil                                  | Tillgängligt om entityType är *File*.<br>Fil namnet för aviseringar som är kopplade till en fil eller process                                                                                                                                                                                                                                                                                    | Detector.UnitTests.dll                                                                                                                                                                                                                            |
| Skript                                  | Tillgängligt om entityType är *File*.<br>Fil Sök vägen för aviseringar som är kopplade till en fil eller process                                                                                                                                                                                                                                                                                    | C: \\ \\ agenten \\ \\ \_ fungerar \\ \\ \_ Temp \\ \\ distribuera \_ system 2020-09-06 12 \_ 14 \_ 54 \\ \\ ut                                                                                                                                                                    |
| processId                                 | Tillgängligt om entityType är *process*.                                                                                                                                                                                                                                                                                                                                                     | 24348                                                                                                                                                                                                                                             |
| processCommandLine                        | Tillgängligt om entityType är *process*.                                                                                                                                                                                                                                                                                                                                                     | " \\ " Filen är klar för nedladdning \_1911150169.exe\\ ""                                                                                                                                                                                           |
| processCreationTime                       | Tillgängligt om entityType är *process*.                                                                                                                                                                                                                                                                                                                                                     | 2020 – 07-18T03:25:38.5269993 Z                                                                                                                                                                                                                      |
| parentProcessId                           | Tillgängligt om entityType är *process*.                                                                                                                                                                                                                                                                                                                                                   | 16840                                                                                                                                                                                                                                             |
| parentProcessCreationTime                 | Tillgängligt om entityType är *process*.                                                                                                                                                                                                                                                                                                                                                     | 2020 – 07-18T02:12:32.8616797 Z                                                                                                                                                                                                                      |
| IP                                 | Tillgängligt om entityType är *IP*. <br>IP-adress för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till ett skadligt nätverk*.                                                                                                                                                                                                                                   | 62.216.203.204                                                                                                                                                                                                                                    |
| :                                       | Tillgängligt om entityType är *URL*. <br>URL för aviseringar som är kopplade till nätverks händelser, till exempel *kommunikation till en illvillig nätverks destination*.                                                                                                                                                                                                                                  | down.esales360.cn                                                                                                                                                                                                                                 |
| Konto                               | Tillgänglig om entityType är *User*.                                                                                                                                                                                                                                                                                                                                                         | testUser2                                                                                                                                                                                                                                         |
| domainName                                | Tillgänglig om entityType är *User*.                                                                                                                                                                                                                                                                                                                                                        | Europa. Corp. contoso                                                                                                                                                                                                                              |
| userSid                                   | Tillgänglig om entityType är *User*.                                                                                                                                                                                                                                                                                                                                                        | S-1-5-21-1721254763-462695806-1538882281-4156657                                                                                                                                                                                                  |
| aadUserId                                 | Tillgänglig om entityType är *User*.                                                                                                                                                                                                                                                                                                                                                        | fc8f7484-f813-4db2-afab-bc1507913fb6                                                                                                                                                                                                              |
| userPrincipalName                         | Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| mailboxDisplayName                        | Tillgänglig om entityType är *post låda*.                                                                                                                                                                                                                                                                                                                                                     | testa user2                                                                                                                                                                                                                                        |
| mailboxAddress                            | Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                      |
| clusterBy                                 | Tillgängligt om entityType är ett  *multicluster*.                                                                                                                                                                                                                                                                                                                                                 | Satt P2SenderDomain; Innehålls                                                                                                                                                                                                                |
| avsändare                                    | Tillgänglig om EntityType är *User* / *e*- / *postmeddelandet*med användar post låda.                                                                                                                                                                                                                                                                                                                                  | user.abc@mail.contoso.co.in                                                                                                                                                                 |
| Recipient                                 | Tillgängligt om entityType är ett *meddelande*.                                                                                                                                                                                                                                                                                                                                                | testUser2@contoso.com                                                                                                                                                                                       |
| satt                                   | Tillgängligt om entityType är ett *meddelande*.                                                                                                                                                                                                                                                                                                                                                 | \[EXTERN \] uppmärksamhet                                                                                                                                                                                                                            |
| deliveryAction                            | Tillgängligt om entityType är ett *meddelande*.                                                                                                                                                                                                                                                                                                                                                 | Levereras                                                                                                                                                                                                                                         |
| securityGroupId                           | Tillgänglig om entityType är  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | 301c47c8-e15f-4059-AB09-e2ba9ffd372b                                                                                                                                                                                                              |
| securityGroupName                         | Tillgänglig om entityType är  *SecurityGroup*.                                                                                                                                                                                                                                                                                                                                               | Operatörer för nätverks konfiguration                                                                                                                                                                                                                   |
| registryHive                              | Tillgängligt om entityType är  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | lokala HKEY- \_ \_ datorer                                                                                                                                                                                                                              |
| registryKey                               | Tillgängligt om entityType är  *Registry*.                                                                                                                                                                                                                                                                                                                                                     | PROGRAM vara \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon                                                                                                                                                                                 |
| registryValueType                         | Tillgängligt om entityType är  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | Sträng                                                                                                                                                                                                                                            |
| registryValue                             | Tillgängligt om entityType är  *Registry*.                                                                                                                                                                                                                                                                                                                                                    | 31-00-00-00                                                                                                                                                                                                                                       |
| deviceId                                  | ID, om sådant finns, för enheten som är relaterad till enheten.                                                                                                                                                                                                                                                                                                                                           | 986e5df8b73dacd43c8917d17e523e76b13c75cd                                                                                                                                                                                                          |



## <a name="example"></a>Exempel

**Ställning**

```
GET https://api.security.microsoft.com/api/incidents
```

**Interimssvar**
```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-topic"></a>Närliggande ämne
- [API för incidenter](api-incident.md)
- [Uppdatera incident](api-update-incidents.md)