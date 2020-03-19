---
title: Planera konfigurationen av Office 365 för företag
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Läs om vad du behöver göra för att konfigurera ditt Office 365 för företag.
ms.openlocfilehash: 3b38f0092b323175c6a12170105e781fab21934d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42813030"
---
# <a name="plan-your-setup-of-office-365-for-business"></a>Planera konfigurationen av Office 365 för företag

Den här artikeln är avsedd för personer som prenumererar på ett abonnemang för Office 365 för företag.
  
Det finns några saker du måste bestämma och information du behöver ha till hands innan du flyttar organisationen till Office 365.
  
## <a name="info-to-have-on-hand-before-you-run-the-office-365-setup-wizard"></a>Information du behöver ha till hands innan du kör Office 365-installationsguiden

När du är redo att köra installationsguiden för Office 365 och flytta din domän till Office 365 behöver du ha följande information till hands:
  
- Lista över användare som du vill lägga till i Office 365. Även om du redan har lagt till dem i Office 365 måste du ange deras namn här om du uppdaterar domäninformationen.

- Hur du meddelar de anställda om deras användar-ID och lösenord för Office 365 så att de kan logga in. Ger du dem informationen över telefon? Eller skickar du den till deras privata e-postadresser? De har ännu inte tillgång till sina e-postadresser för Office 365, så du kan inte använda dessa.

- Om du har ett domännamn för din organisation (till exempel contoso.com) **och** du planerar att använda Office 365-e-post måste du veta var domänen är registrerad och ha inloggningsinformation.

## <a name="what-happens-when-you-run-the-office-365-setup-wizard"></a>Vad händer när du kör Office 365-installationsguiden

Installationsguiden hjälper dig att installera Office 365-apparna på datorn, lägga till och verifiera din domän, lägga till användare och tilldela licenser till dem och ansluta domänen.

> [!NOTE]
> Om du behöver [tilldela administratörsroller i Office 365 för företag](../add-users/assign-admin-roles.md) till de användare som du lägger till i guiden kan du göra det senare på sidan **Användare.** 
  
Om du inte slutför installationsguiden kan du slutföra installationsuppgifterna när som helst från**installationsprogrammet**för [administrationscenter](https://go.microsoft.com/fwlink/p/?linkid=2024339) > . Härifrån kan du migrera e-post och kontakter från en annan e-posttjänst, ändra domänen för ditt administratörskonto, hantera din faktureringsinformation, lägga till eller ta bort användare, återställa lösenord och göra andra affärsfunktioner. Mer information om skillnaderna mellan inställningsguiden och **installationssidan** finns i [Skillnader mellan installationsguiden för Office 365 och installationssidan](o365-setup-wizard-and-setup-page.md).

Kontakta oss om du kör fast. [Vi hjälper gärna till!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>När du inte ska använda installationsguiden: Active Directory-synkronisering och hybridmiljöer

Det finns ett par scenarier som inkluderar att migrera data eller användare från lokala miljöer eller konfigurera ett hybridsystem som innehåller katalogsynkronisering. Om du är i någon av kategorierna följer du instruktionerna i följande artiklar:
  
- Om du vill konfigurera katalogsynkronisering med ditt lokala Active Directory läser du [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization), och om du vill förstå de olika identitetsmodellerna i Office 365 läser du [Understanding Office 365 identity and Azure Active Directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity).

- Här finns fullständiga instruktioner som hjälper dig igenom alla olika sätt att konfigurera en Exchange-hybrid (inklusive hur du konfigurerar DNS-poster): [Exchange Server Deployment Assistant](https://aka.ms/exdeploy)

- Om du vill konfigurera en SharePoint-hybrid, och då främst sök- och webbplatsfunktioner, går du till [Hybridsökning i SharePoint](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-office-365-all-at-once-or-in-stages"></a>Flytta till Office 365 på en gång eller i etapper

- **Vill du flytta din organisation till Office 365 på en gång?** Om så är fallet planerar du att flytta domänen till Office 365 direkt. Börja med att köra installationsguiden för Office 365. Det kommer att uppmana dig att ställa in din domän.

- **Vill du flytta till Office 365 gradvis?** Om du vill flytta till Office 365 stegvis hoppar du över Office 365-installationsguiden och överväg att införa Office 365-funktioner i följande ordning:

    1. [Lägga till de anställda i Office 365](../add-users/add-users.md) så att de kan ladda ned och installera Office-programmen.

    2. [Ladda ned och installera Office-programmen](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) för att kunna använda Word, Excel och PowerPoint på datorer och enheter.

    3. [Konfigurera Microsoft Teams](#plan-for-teams) som du kan använda för dina möten.

    4. [Flytta ditt innehåll till Office 365-molnlagring](set-up-file-storage-and-sharing.md) (OneDrive- eller SharePoint-gruppwebbplatser).

    5. När du är klar väljer du **Installationsprogram** i det vänstra navigeringsfönstret i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=2024339)och använder **installationssidan** för att [flytta domänen och e-postmeddelandet](add-domain.md).

## <a name="check-that-your-devices-meet-system-requirements"></a>Kontrollera att enheterna uppfyller systemkraven

Varje person i organisationen kan installera Office 2016-paketet med appar (Word, Excel, PowerPoint och så vidare) på upp till fem datorer och Mac-datorer. Se operativsystem- och datorkraven för installation av [Office 2016-paket](https://go.microsoft.com/fwlink/?LinkId=534827) för företag.
  
Mobilappar kan installeras på iOS-, Android- och Windows-enheter. Du hittar mer information om stöd för mobila enheter och webbläsare i [Systemkrav för Office](https://go.microsoft.com/fwlink/?LinkId=534827).
  
## <a name="plan-for-email"></a>Planera för e-post

Om du planerar att flytta från en befintlig e-posttjänst till Office 365 tar det vanligtvis två dagar att byta.
  
### <a name="plan-for-email-downtime"></a>Planera för driftsavbrott för e-post
  
Om du kommer att använda Office 365 för e-post:
  
- Om du vill flytta företagets e-postadress (till exempel *rob@contoso.com)* från en annan e-posttjänst till Office 365 måste du dirigera din e-post för att levereras till din nya Office 365-postlåda. Du gör detta genom att välja **Migrera användarnas data** på **installationssidan,** där vi guidar dig genom de uppdateringar du behöver göra hos din domänvärd, steg för steg.

- När du har uppdaterat värden för domänen börjar ändringarna vanligtvis att gälla efter bara en timme eller två. Men var medveten om att det ibland kan ta upp till 72 timmar för ändringar att uppdatera över internet.

- Eftersom det kan uppstå driftsavbrott för e-post rekommenderar vi att du planerar att byta till e-post hos Office 365 under en kväll eller helg när du får färre e-postmeddelanden.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Planera att flytta dina befintliga e-postmeddelanden, kontakter och kalendrar
  
Om du kommer att använda Office 365 för ditt e-postkonto kan du ta med dig befintliga e-postmeddelanden, kontakter och kalendrar. **På sidan Inställningar** kan du flytta din befintliga e-post och dina kontakter för de flesta scenarier. Det finns även stegvisa instruktioner för att flytta en eller flera postlådor.
  
|**Hur många postlådor?**|**Rekommendation**|
|:-----|:-----|
|Några få  <br/> |Om du inte vill använda **installationssidan** för att migrera postlådorna kan du låta postlådeägare migrera sina egna e-postmeddelanden och kontakter. Se [Migrera e-post och kontakter till Office 365 för företag](migrate-email-and-contacts-admin.md).  <br/> |
|Flera  <br/> |Om du migrerar från Gmail läser du [Migrera G Suite-postlådor till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes).  <br/> Om du migrerar från en annan e-postleverantör, inklusive Exchange, läser du [Sätt att migrera flera e-postkonton till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Planera för lagring och migrering av filer

Office 365 tillhandahåller molnlagring för enskilda personer, små organisationer och företag. Information om vad du lagrar var finns i [Var du kan lagra dokument i Office 365](https://support.office.com/article/c7c20284-bc94-47f4-9728-d28e9daf0790.aspx).
  
- **Du kan flytta hundratals filer** till [OneDrive](https://support.office.com/article/45114744-6D42-45CD-8975-F9617819BDEB.aspx) eller till en [SharePoint-gruppwebbplats](https://support.office.com/article/da549fb1-1fcb-4167-87d0-4693e93cb7a0.aspx#__toc384119242). Du kan ladda upp 100 filer åt gången. Undvik att ladda upp filer som är större än 2 GB, eftersom det är den största tillåtna filstorleken som standard.
  
- **Om du vill flytta flera tusen filer** till Office 365-lagring bör du läsa [Begränsningar för SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113). Vi rekommenderar att du använder ett migreringsverktyg och överväger att anlita en [partner](https://go.microsoft.com/fwlink/?linkid=391089) som kan hjälpa dig med migreringen. Mer information om hur du migrerar ett stort antal filer finns i [Användarhandbok om SharePoint Online- och OneDrive-migrering](https://go.microsoft.com/fwlink/?LinkId=723574).
  
## <a name="plan-for-teams"></a>Planera för team

Du kan använda Microsoft Teams för att ringa samtal till andra personer i organisationen som använder din prenumeration. Om din organisation till exempel har 10 personer kan du ringa och lägga märke till varandra med teams utan någon särskild konfiguration. Mer information finns i [Komma igång med Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start).

För större organisationer eller om du startar från Skype för företag, lokala eller hybriddistributioner läser du [Så här distribuerar du Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams).
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Planera för integrering med Active Directory eller annan programvara

- **Vill du integrera med din lokala Active Directory?** Du kan integrera din lokala Active Directory med Office 365 med hjälp av Azure Active Directory Connect. Instruktioner finns i [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).
  
- **Vill du integrera Office 365 med annan programvara?** Om du behöver integrera Office 365 med annan programvara i organisationen rekommenderar vi att du [kan anlita en partner](https://go.microsoft.com/fwlink/?linkid=391089) för att hjälpa dig med distributionen.
  
## <a name="do-you-want-someone-to-help-you-set-up-office-365"></a>Vill du ha hjälp med att konfigurera Office 365?

- **Om du har färre än 50 anställda:**

  - **Be om hjälp så ringer vi dig**. När du har köpt Office 365 kan du komma åt administrationscentret (du behöver inte köra installationsprogrammet för att komma åt det). Välj Behöver du **hjälp** längst ned i administrationscentret? Beskriv problemet så ringer vi upp dig. 
  - **Ring [Office 365 för företag-support](../contact-support-for-business-products.md) med dina frågor**. Vi hjälper gärna till! 
  - **Du kan även anlita en [Microsoft-partner](https://go.microsoft.com/fwlink/?linkid=391089)**. Om du har ont om tid eller har avancerade krav (till exempel att flytta tusentals filer till Office 365-molnlagring eller att integrera med andra program) kan en erfaren partner vara till stor hjälp. 

- **Om du har fler än 50 anställda** kan [FastTrack-introduktionscentret](https://go.microsoft.com/fwlink/?LinkId=517115) hjälpa dig med distributionen. 