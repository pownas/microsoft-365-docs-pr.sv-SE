---
title: Översikt över instrumentpanelen för säkerhet
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Använd den nya säkerhetsinstrumentpanelen för att granska Status för skydd mot hotskydd i Office 365 och visa och agera på säkerhetsaviseringar.
ms.openlocfilehash: 85c616c717a85f9a6a47e63a48621a8703b487aa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807644"
---
# <a name="security-dashboard"></a>Instrumentpanel för säkerhet

## <a name="overview"></a>Översikt

[Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) gör det möjligt för din organisation att hantera dataskydd och efterlevnad. Förutsatt att du har de behörigheter som krävs kan du med säkerhetsinstrumentpanelen granska din hotskyddsstatus samt visa och agera på säkerhetsaviseringar. 
  
Titta på videon för att få en översikt och läs sedan den här artikeln om du vill veta mer.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
Beroende på vad organisationens Office 365-prenumeration innehåller innehåller säkerhetsinstrumentpanelen flera widgetar, till exempel Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware med mera, enligt beskrivningen i följande avsnitt.
  
Om du vill visa säkerhetsinstrumentpanelen går du till **instrumentpanelen** **för hothantering** \> i [Office 365 Security &amp; Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).
  
> [!NOTE]
> Du måste vara en global Office 365-administratör, en säkerhetsadministratör eller en säkerhetsläsare för att kunna visa säkerhetsinstrumentpanelen. Vissa widgetar kräver ytterligare behörigheter för att kunna visa. Mer information finns [i Behörigheter i Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Sammanfattning av hothantering

Widgeten Sammanfattning av hot ger dig en överblick över hur din organisation har skyddats från hot under de senaste sju (7) dagarna.

![Säkerhetsinstrumentpanel – sammanfattningswidget för hothantering](../../media/SecDash-ThreatMgmtSummary.png)

Vilken information du ser i sammanfattningen av hothantering beror på vad du prenumererar på. I följande tabell beskrivs vilken information som ingår för Office 365 E3 och Office 365 E5.


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|Blockerade meddelanden om skadlig kod<br/>Nätfiskemeddelanden blockerade<br>Meddelanden som rapporterats av användare<br><br><br><br> |Blockerade meddelanden om skadlig kod<br>Nätfiskemeddelanden blockerade<br>Meddelanden som rapporterats av användare<br>Zero-day malware blockerad<br>Avancerade nätfiskemeddelanden har upptäckts<br>Blockerade skadliga webbadresser |

Om du vill visa eller komma åt widgeten Sammanfattning av hothantering måste du ha behörighet för att kunna visa rapporter om avancerat skydd mot hot. Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Status för skydd mot hot

Widgeten Hot Protection Status visar hotskyddseffektivitet med en trendig och detaljerad vy över phish och skadlig kod. 

![Widget för status för hotskydd](../../media/tpswidget.png)

Informationen beror på om din Office 365-prenumeration innehåller [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) med eller utan Office [365 Advanced Threat Protection](office-365-atp.md) (ATP).


|Om din prenumeration innehåller... |Du ser dessa detaljer |
|---------|---------|
|EOP men inte Office 365 ATP     |Skadlig e-post som upptäcktes och blockerades av EOP<br> Se [rapporten Status för hotskydd (EOP).](view-email-security-reports.md#threat-protection-status-report)| 
|Office 365 ATP |Skadligt innehåll och skadlig e-post som upptäckts och blockerats av EOP och Office 365 ATP<br>Aggregerat antal unika e-postmeddelanden med skadligt innehåll som blockerats av anti-malware-motorn, [nolltimmars automatisk rensning](zero-hour-auto-purge.md)och ATP-funktioner (inklusive [säkra länkar,](atp-safe-links.md) [säkra bilagor](atp-safe-attachments.md)och [ATP-anti-phishing).](atp-anti-phishing.md)<br>Se [rapporten Status för hotskydd (ATP).](view-reports-for-atp.md#threat-protection-status-report) | 

Om du vill visa eller komma åt widgeten Status för hotskydd måste du ha behörighet att visa rapporter om avancerat skydd mot hot. Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Globala hotidentifieringar varje vecka
 
Widgeten Global Weekly Threat Detections visar hur många hot som upptäckts i e-postmeddelanden under de senaste sju (7) dagarna.

![Widgeten Globala veckovisa hotidentifieringar](../../media/globalweeklythreatdetections.png)

Måtten beräknas enligt beskrivningen i följande tabell:

|Metriska  |Hur det beräknas  |
|---------|---------|
|Skannade meddelanden |Antal skannade e-postmeddelanden multiplicerat med antalet mottagare |
|Hot stoppas  |Antal e-postmeddelanden som identifierats som innehållande skadlig kod multiplicerat med antalet mottagare |
|Blockerad av [ATP](office-365-atp.md) |Antal e-postmeddelanden som blockerats av ATP multiplicerat med antalet mottagare |
|Tas bort efter leverans |Antal meddelanden som tagits bort med [automatisk rensning](zero-hour-auto-purge.md) noll timmar multiplicerat med antalet mottagare |

## <a name="malware"></a>Malware

Malware widgets visar information om malware trender och malware familjetyper under de senaste sju (7) dagarna.

![Malware trender och familjetyper](../../media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Insikter

Insikter inte bara yta viktiga frågor som du bör granska, de innehåller också rekommendationer och åtgärder att överväga. 

![Smarta insikter](../../media/smartinsights.png)

Du kan till exempel se att nätfiskemeddelanden levereras eftersom vissa användare har inaktiverat sina skräppostalternativ. Mer information om hur insikter fungerar finns [i Rapporter och insikter &amp; i Office 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-investigation-and-response"></a>Hotutredning och hothantering

Om organisationens prenumeration innehåller [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)har säkerhetsinstrumentpanelen ett avsnitt som innehåller avancerade verktyg för utredning och svar av hot. Organisationens säkerhetsteam kan använda informationen i det här avsnittet för att förstå nya kampanjer, undersöka hot och hantera incidenter. 
  
![Hotinformation hjälper dig att förstå attacker riktade mot din organisation](../../media/threatintelwidget.png)
  
  
## <a name="trends"></a>Trender

Längst ned på säkerhetsinstrumentpanelen finns ett **avsnittet Trender** som sammanfattar trender för e-postflödet för din organisation. Rapporter innehåller information om e-post som kategoriseras som skräppost, skadlig kod, nätfiskeförsök och bra e-post. Klicka på en panel om du vill visa mer detaljerad information i rapporten. 
  
![Avsnittet Trender sammanfattar trender för e-postflödet för organisationen](../../media/trends.png)
  
Och om organisationens Office 365-prenumeration innehåller [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)har du också en rapport om aviseringar om **hothantering nyligen** i det här avsnittet som gör det möjligt för säkerhetsteamet att visa och vidta åtgärder för säkerhetsaviseringar med hög prioritet. 

Om du vill visa eller komma åt widgeten Skickat och mottaget e-post måste du ha behörighet för att kunna visa rapporter om avancerat skydd mot hot. Mer information finns i [Vilka behörigheter som behövs för att visa ATP-rapporterna?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Om du vill visa eller komma åt widgeten Senaste hothanteringsaviseringar måste du ha behörighet att visa aviseringar. Mer information finns i [RBAC-behörigheter som krävs för att visa aviseringar](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Relaterade ämnen

[Visa säkerhetsrapporter för &amp; e-post i Säkerhetsefterlevnadscenter](view-email-security-reports.md)
  
[Visa rapporter för avancerat hotskydd för Office 365](view-reports-for-atp.md)
  
[Avancerat hotskydd i Office 365](office-365-atp.md)
  
[Office 365 Hotutredning och hothantering](office-365-ti.md)
  
