---
title: IdentityDirectoryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om domän kontrol Lanterna och Active Directory-händelser i tabellen IdentityDirectoryEvents för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityDirectoryEvents, domänkontrollant, Active Directory, Azure ATP, identiteter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 41b429e32122d6cc58a746649c8a0428f0a90b0f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847434"
---
# <a name="identitydirectoryevents"></a>IdentityDirectoryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

`IdentityDirectoryEvents`Tabellen i det [avancerade](advanced-hunting-overview.md) antivirus programmet innehåller händelser som berör en lokal domänkontrollant som kör Active Directory (AD). Den här tabellen innehåller olika identitets relaterade händelser, till exempel lösen ords ändringar, lösen ords giltighet och UPN-ändringar. Den fångar också system händelser på domänkontrollanten, som schemaläggning av uppgifter och PowerShell-aktivitet. Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.

>[!TIP]
> Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.

Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).

| Kolumnnamn | Datatyp | Beskrivning |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum och tid när händelsen registrerades |
| `ActionType` | strängvärdet | Typ av aktivitet som utlöste händelsen. Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) |
| `Application` | strängvärdet | Program som utförde den inspelade åtgärden |
| `TargetAccountUpn` | strängvärdet | Användarens huvud namn (UPN) för det konto som den inspelade åtgärden tillämpades på |
| `TargetAccountDisplayName` | strängvärdet | Visnings namn för det konto som den inspelade åtgärden tillämpades på |
| `TargetDeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten som den inspelade åtgärden tillämpades på |
| `DestinationDeviceName` | strängvärdet | Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationIPAddress` | strängvärdet | IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden |
| `DestinationPort` | strängvärdet | Mål Port för aktiviteten |
| `Protocol` | strängvärdet | Protokoll som används under kommunikationen |
| `AccountName` | strängvärdet | Kontots användar namn |
| `AccountDomain` | strängvärdet | Kontots domän |
| `AccountUpn` | strängvärdet | Kontots huvud namn (UPN) |
| `AccountSid` | strängvärdet | Kontots säkerhets identifierare (SID) |
| `AccountObjectId` | strängvärdet | Unik identifierare för kontot i Azure Active Directory |
| `AccountDisplayName` | strängvärdet | Namnet på kontot som visas i adress boken. Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång. |
| `DeviceName` | strängvärdet | Det fullständigt kvalificerade domän namnet (FQDN) för enheten |
| `IPAddress` | strängvärdet | Den IP-adress som tilldelats enheten under kommunikationen |
| `Port` | strängvärdet | TCP-port som används under kommunikation |
| `Location` | strängvärdet | Ort, land eller annan geografisk plats som är kopplad till evenemanget |
| `ISP` | strängvärdet | Internet leverantör associerad med IP-adressen |
| `ReportId` | tids | Unik identifierare för händelsen |
| `AdditionalFields` | strängvärdet | Ytterligare information om enheten eller händelsen |

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
