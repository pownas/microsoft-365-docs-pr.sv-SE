---
title: Hot undersökning & svars funktioner-Microsoft Defender för Office 365 abonnemang 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Lär dig mer om hot-och svars funktioner i Microsoft Defender för Office 365-abonnemang.
ms.openlocfilehash: cbda50dacd6b892c976ce55632c8fc35813839b7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614780"
---
# <a name="threat-investigation-and-response"></a>Hot utredning och svar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hot-undersökningar och svars funktioner i [Microsoft Defender för Office 365](office-365-atp.md) hjälper säkerhets analyser och administratörer att skydda organisationens Microsoft 365 för företag-användare genom att:

- Gör det enkelt att identifiera, övervaka och förstå cyberattacks
- Att snabbt adressera hot i Exchange Online, SharePoint Online, OneDrive för företag och Microsoft Teams
- Tillhandahålla insikter och kunskaper för att hjälpa säkerhets hanteringen att förhindra cyberattacks mot deras organisation
- Använda [Automatisk undersökning och svar i Office 365](automated-investigation-response-office.md) för viktiga e-postbaserade hot

Hot-och svars funktioner tillhandahåller insikter för hot och relaterade svars åtgärder som är tillgängliga i centret för säkerhets & efterlevnad. Dessa insikter kan hjälpa din organisations säkerhets team att skydda användare från e-post-eller filbaserade attacker. Funktionerna hjälper dig att övervaka signaler och samla in data från flera källor, till exempel användar aktivitet, inloggningsautentisering, e-post, kompromissade datorer och säkerhets händelser. Besluts fattare och säkerhets åtgärder kan använda den här informationen för att förstå och reagera på hot mot din organisation och skyddar din immateriella egendom.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Bekanta dig med Threat-och svars verktyg

Arbets ytan för hot-undersökningar och svars funktioner i området säkerhets & efterlevnad, som en uppsättning verktyg och svars flöden, inklusive följande:

- [Hot instrument panel](#threat-dashboard)
- [Gick](#threat-explorer)
- [Incidenter](#incidents)
- [Attacksimulator](#attack-simulator)
- [Automatiska undersökningar och svar](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Hot instrument panel

Använd hot instrument panelen (Detta kallas även för [säkerhets instrument panelen](security-dashboard.md)) för att snabbt se vilka hot som har åtgärd ATS, och som ett visuellt sätt att rapportera till besluts fattare för företag hur Microsoft 365-tjänster säkrar verksamheten.

![Hot instrument panel](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

Om du vill visa och använda den här instrument panelen går du till fliken **Threat Management** på \> **instrument panelen** för säkerhet &.

### <a name="threat-explorer"></a>Hotutforskaren

Använd [Threat Explorer (och identifieringar i real tid)](threat-explorer.md) för att analysera hot, se hur mycket du har attacker och analysera data från hot familjer, angripare och andra infrastrukturer. Threat Explorer (kallas även Utforskaren) är start platsen för eventuella säkerhetsanalytikers undersökningar.

![Threat Explorer](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

Om du vill visa och använda den här & rapporten går du till **Threat Management** \> **Explorer**.

### <a name="incidents"></a>Incidenter

Använd listan incidenter (kallas även undersökningar) för att se en lista över flyg säkerhets tillbud. Incidenter används för att spåra hot som misstänkta e-postmeddelanden och för att genomföra ytterligare undersökningar och åtgärder.

![Lista över aktuella hot händelser i Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

Om du vill visa en lista över aktuella incidenter för organisationen går du till fliken säkerhet & regelefterlevnad och går till **Threat Management** \>  \> .

![I fönstret säkerhets & efterlevnad väljer du Threat Management \> recension](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Attacksimulator

Använd angrepps Simulator för att ställa in och köra realistiska cyberattacks i din organisation och identifiera utsatta människor innan en verklig cyberattack påverkar ditt företag. Mer information finns i [angrepps Simulator i Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Automatiska undersökningar och svar

Använd automatiserade undersökningar och svar (AIR)-funktioner för att spara tid och ansträngning som korrelerar innehåll, enheter och personer mot hot från din organisation. LUFT processer kan börja när vissa notifieringar utlöses eller när de startas av din säkerhets åtgärd. Mer information finns i [automatiserad undersökning och svar i Office 365](automated-investigation-response-office.md).

## <a name="threat-intelligence-widgets"></a>Hot Intelligence-widget

Som en del av Microsoft Defender för Office 365 abonnemang 2, kan säkerhets analytiker granska information om ett känt hot. Detta är användbart för att ta reda på om det finns ytterligare förebyggande åtgärder/steg som kan vidtas för att skydda användare.

![Säkerhets trender som visar information om de senaste hoten](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>Hur får de här funktionerna?

Microsoft 365 hot-och svars funktioner ingår i Microsoft Defender för Office 365 abonnemang 2, som ingår i Enterprise, E5 eller som ett tillägg till vissa abonnemang. Mer information finns i [Defender för Office 365 abonnemang 1 och abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Nödvändiga roller och behörigheter

I Microsoft Defender för Office 365 används rollbaserad åtkomst kontroll. Behörigheter tilldelas genom vissa roller i Azure Active Directory, administrations centret för Microsoft 365 eller säkerhets & Compliance Center.

> [!TIP]
> Även om vissa roller, till exempel säkerhets administratör, kan tilldelas i säkerhets & Compliance Center, bör du överväga att använda antingen Microsoft 365 Admin Center eller Azure Active Directory i stället. Information om roller, roll grupper och behörigheter finns i följande resurser:
>
> - [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)
>
> - [Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|Aktivitet|Roller och behörigheter|
|---|---|
|Använda hot instrument panelen (eller den nya [säkerhets instrument panelen](security-dashboard.md)) <p> Visa information om senaste eller aktuella hot|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhets administratör**</li><li>**Säkerhets läsare**</li></ul> <p> Dessa roller kan tilldelas i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Microsoft 365 Admin Center ( <https://admin.microsoft.com> ).|
|Använd [Threat Explorer (och real tids identifieringar)](threat-explorer.md) för att analysera hot|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhets administratör**</li><li>**Säkerhets läsare**</li></ul> <p> Dessa roller kan tilldelas i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Microsoft 365 Admin Center ( <https://admin.microsoft.com> ).|
|Visa incidenter (kallas även undersökningar) <p> Lägga till e-postmeddelanden i en olycka|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhets administratör**</li><li>**Säkerhets läsare**</li></ul> <p> Dessa roller kan tilldelas i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Microsoft 365 Admin Center ( <https://admin.microsoft.com> ).|
|Utlösa e-poståtgärder i en olycka <p> Hitta och ta bort misstänkta e-postmeddelanden|Något av följande: <ul><li>**Global administratör**</li><li>**Säkerhets administratören** plus rollen **Sök och rensa**</li></ul> <p> Rollen som **Global administratör** och **säkerhets administratör** kan tilldelas i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Microsoft 365 Admin Center ( <https://admin.microsoft.com> ). <p> Rollen **sökning och rensning** måste tilldelas i säkerhets & Compliance Center ( <https://protection.office.com> ).|
|Integrera Microsoft Defender för Office 365 abonnemang 2 med Microsoft Defender för slut punkt  <p> Integrera Microsoft Defender för Office 365 abonnemang 2 med en SIEM-Server|Antingen den **globala administratören** eller rollen **säkerhets administratör** tilldelad i antingen Azure Active Directory ( <https://portal.azure.com> ) eller Microsoft 365 Admin Center ( <https://admin.microsoft.com> ). <p> --- **bransch** --- <p> En lämplig roll som har tilldelats till ytterligare program (till exempel [Microsoft Defender säkerhets Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) eller din Siem-Server).|
|

## <a name="next-steps"></a>Nästa steg

- [Lär dig mer om hot-Spårare-nya och intressanta](threat-trackers.md)

- [Hitta och undersöka skadlig e-post som har levererats (Office 365 hot undersökning och svar)](investigate-malicious-email-that-was-delivered.md)

- [Integrera Office 365 hot-undersökningar och-svar med Microsoft Defender för slut punkten](integrate-office-365-ti-with-wdatp.md)

- [Lär dig mer om angrepps Simulator](attack-simulator.md)
