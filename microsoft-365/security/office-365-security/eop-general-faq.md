---
title: Vanliga frågor och svar om EOP:s allmänna
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Här svarar vi på de vanligaste allmänna frågorna om Microsoft Exchange Online Protection (EOP) molnbaserade e-postfiltreringstjänst. Mer information om vanliga frågor och svar finns i följande länkar:'
ms.openlocfilehash: 03fb070b2a40ad1e363138124eb0225e64fd5702
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805863"
---
# <a name="eop-general-faq"></a>Vanliga frågor och svar om EOP:s allmänna

Här svarar vi på de vanligaste allmänna frågorna om Microsoft Exchange Online Protection (EOP) molnbaserade e-postfiltreringstjänst. Mer information om vanliga frågor och svar finns i följande länkar:

- [Vanliga frågor och svar om EOP-köade, uppskjutna och studsade meddelanden](eop-queued-deferred-and-bounced-messages-faq.md)

- [Vanliga frågor och svar om delegerad administration](delegated-administration-faq.md)

- [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md)

- [Säkra avsändare- och blockerade avsändarelistor i Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

- [Vanliga frågor om karantän](quarantine-faq.md)

- [Vanliga frågor om skydd mot skadlig kod](anti-malware-protection-faq-eop.md)

- [Vanliga frågor och svar om meddelandespårning](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**F. Vad är EOP?**

A. EOP är en molnbaserad e-postfiltreringstjänst som är byggd för att skydda kunder från skräppost och skadlig kod och för att implementera anpassade principregler.

**F. Hur registrerar jag mig för en EOP-utvärderingsversion eller köper EOP?**

A. Registrera dig för en EOP-utvärderingsversion eller köp EOP via webben på [Exchange Online Protection hemsida](https://products.office.com/exchange/exchange-email-security-spam-protection). Observera att funktionerna för ett provköp är desamma som för en betald prenumeration, men även de ytterligare funktioner som medföljer [Exchange Enterprise CAL med tjänster](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) prenumerationsplan.

**F. Hur är EOP prissatt?**

A. EOP är licensierat av användaren. Den senaste prisinformationen finns på [startsidan för Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection).

**F. Hur lång tid tar det att sätta EOP i produktion?**

A. När du ändrar MX-posten, enligt stegen i [Konfigurera din EOP-tjänst](set-up-your-eop-service.md)och din e-post flödar via EOP, börjar filtrningen omedelbart. MX-posten kan ta upp till 24-48 timmar att sprida via DNS. Du kan finjustera dina skyddsinställningar i Administrationscenter för Exchange (EAC) när som helst under den här processen.

**F. Måste jag använda alla funktioner i Microsoft Office 365 för att använda EOP? Tänk om jag bara vill ha EOP-skydd och det är allt?**

A. Du kan använda EOP för att skydda dina lokala postlådor utan att använda några andra funktioner i Office 365. Detta kallas en fristående prenumeration. En lista över EOP-funktioner finns i beskrivningen av [Exchange Online Protection Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

**F. Varför behöver jag en Office 365-klientorganisation när jag registrerar mig för e-postfiltrering via EOP?**

A. Office 365 är namnet på en samling produkter och tjänster som kan nås via en Office 365-klientorganisation. Tänk på Office 365-klienten som utgångspunkt som du kan lägga till licenser för e-postfiltrering.

**F. Har EOP en kommunikationsportal där jag kan ta reda på kända problem och förväntade lösningar? Hur är det med nya funktioner?**

A. Microsoft 365 admin center kommer att ha en del av denna information. Om du påverkas av en servicenivåhändelse bör du se en kommunikationsavisering (vanligtvis tillsammans med en klockikon) efter att du har loggat in på Microsoft 365-administrationscentret. Vi rekommenderar att du läser och agerar på alla objekt som är lämpliga.

När det gäller nya EOP-funktioner är [office 365 för företag-färdplanen](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) en bra resurs för att ta reda på information om kommande nya funktioner. Vi kommer också att publicera blogg artiklar om nya funktioner till [Microsoft 365 Bloggar](https://www.microsoft.com/microsoft-365/blog/) webbplats.

**F. Fungerar tjänsten med äldre Exchange-versioner (till exempel Exchange Server 2010) och miljöer som inte är Exchange?**

A. Ja, tjänsten är serveroberoende och kan användas med valfri SMTP-postöverföringsagent.

**F. Vilken storlek organisation kan använda tjänsten?**

A. Vilken storlek som helst. EOP-nätverket har tillräcklig kapacitet för att tillgodose din tillväxt, oavsett hur snabbt din organisation växer.

**Vilka behörigheter behöver jag för att konfigurera EOP?**

För att kunna konfigurera EOP måste du vara en Global Office 365-administratör eller en Exchange Company Administrator (rollgruppen Organisationshantering).

**F. Hur vet jag att mina data och privata uppgifter är säkra?**

A. Om du vill veta mer om de åtgärder vi har vidtagit för att säkerställa säkerheten för dina data och privat information, inklusive information om servicenivåavtal , går du till [Office 365 Trust Center](https://www.microsoft.com/trust-center).

**F. Finns det några gränser som jag bör vara medveten om, till exempel begränsningar för meddelandestorlek?**

A. Ja. Mer information om begränsningar i EOP finns i [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

**F. Stöder EOP PowerShell?**

A. Ja, fullständig EOP-funktionalitet är tillgänglig via PowerShell. Mer information finns i [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).