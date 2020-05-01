---
title: Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du använder regler för e-postflöde (kallas även transportregler) för att ta emot kopior av meddelanden som användarna rapporterar till Microsoft.
ms.openlocfilehash: 2b1e82ece936551c48e5617955f546cf851a8913
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939505"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Använd regler för e-postflöde för att se vad användarna rapporterar till Microsoft

Det finns flera sätt för användare att rapportera meddelanden till Microsoft för analys enligt beskrivningen i [Rapportmeddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

Du kan skapa en regel för e-postflöde (kallas även en transportregel) som söker efter meddelanden som användare rapporterar till Microsoft, och du kan konfigurera Mottagare av hemlig kopia så att de tar emot kopior av dessa rapporterade meddelanden.

Du kan skapa e-postflödesregeln i Administrationscenter för Exchange (EAC) och PowerShell (Exchange Online PowerShell för Microsoft 365-kunder. Exchange Online Protection PowerShell för fristående EOP-kunder).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste tilldelas behörigheter i Exchange Online eller EOP innan du kan göra dessa procedurer. Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard. Mer information finns [i Hantera rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Information om hur du öppnar EAC finns [i Administrationscenter för Exchange Online eller](https://docs.microsoft.com/Exchange/exchange-admin-center) Exchange i Exchange Online [Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Mer information om regler för e-postflöde i Exchange Online och fristående EOP finns i följande avsnitt:

  - [Regler för e-postflöde (transportregler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Villkor och undantag för e-postflödesregel (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda EAC för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

1. Gå till **Regler för** **e-postflöde** \> i EAC .

2. Klicka på](../../media/ITPro-EAC-AddIcon.png) Ikonen Lägg **till** ![och välj sedan Skapa en ny **regel**.

3. Konfigurera följande inställningar på sidan **Ny regel** som öppnas:

   - **Namn**: Ange ett unikt, beskrivande namn för regeln. Till exempel hemlig kopia meddelanden som rapporterats till Microsoft.

   - Klicka på **Fler alternativ**.

   - **Använd den här regeln om:** Välj **Mottagaradressen** \> **innehåller något av dessa ord**: I dialogrutan Ange ord eller **fraser** anger du ett av följande värden, klickar på **Lägg till** ![ikon](../../media/ITPro-EAC-AddIcon.png)och upprepar tills du har angett alla värden.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Om du vill redigera en post](../../media/ITPro-EAC-EditIcon.png)markerar du den och klickar på **Ikonen Redigera** ![redigering . Om du vill ta bort en](../../media/ITPro-EAC-DeleteIcon.png)post markerar du den och klickar på Ikonen Ta bort ta **bort** ![.

     När du är klar klickar du på **OK**.

   - **Gör så här:** Välj **Lägg till mottagare** \> **i rutan Hemlig kopia**. Leta reda på och markera de mottagare som du vill lägga till i dialogrutan som visas. När du är klar klickar du på **OK**.

4. Du kan göra ytterligare val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra inställningar. Vi rekommenderar att du testar regeln innan du tillämpar den.

5. Klicka på **Spara** när du är klar.

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Använda PowerShell för att skapa en regel för e-postflöde för att ta emot kopior av rapporterade meddelanden

I det här exemplet skapas en ny regel för e-postflöde med namnet Hemlig kopia meddelanden som rapporterats till Microsoft och som söker efter e-postmeddelanden som rapporteras till Microsoft med hjälp av de metoder som beskrivs i det här avsnittet och lägger till användarna laura@contoso.com och julia@contoso.com som mottagare av hemlig kopia.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har konfigurerat regler för e-postflöde för att ta emot kopior av rapporterade meddelanden:

- Gå till EAC-regler för att skicka **Edit** ![till](../../media/ITPro-EAC-EditIcon.png) **E-postflödesregler** \> **Rules** \> och markera regeln \> klicka på Redigera redigera ikon och kontrollera inställningarna.

- I PowerShell kör du följande kommando för att verifiera inställningarna:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Skicka ett testmeddelanden till en av de rapporterande e-postadresserna och verifiera resultaten.