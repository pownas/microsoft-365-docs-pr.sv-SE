---
title: Uppgradera dina Office 365 för företag-användare till den senaste Office-klienten
f1.keywords:
- NOCSH
ms.author: janellem
author: janellem
manager: eliree
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Läs om hur du uppgraderar användarna till den senaste Office-klienten.
ms.openlocfilehash: 3d9c92a5362889db69926552848ba4c71d7c4c42
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807745"
---
# <a name="upgrade-your-office-365-for-business-users-to-the-latest-office-client"></a>Uppgradera dina Office 365 för företag-användare till den senaste Office-klienten

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 når support

Office 2010 kommer att nå sitt stöd den 13 oktober 2020. När Office 2010 når sitt stöd kommer Microsoft inte längre att tillhandahålla följande:

- Teknisk support för frågor

- Buggfixar för problem som upptäcks

- Säkerhetskorrigeringar för säkerhetsproblem som upptäcks

Mer information finns i [översikten över supporten i Office 2010.](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap)

 **Är detta rätt ämne för dig?**
  
 Om du är administratör som ansvarar för Office 365 för företag-prenumerationen i organisationen är du på rätt plats. Administratörer ansvarar vanligtvis för uppgifter som att hantera användare, återställa lösenord, hantera Office-installationer och lägga till eller ta bort licenser.

 Om du inte är administratör och har en [Office för-hem-produkt](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) läser [jag Hur uppgraderar jag Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) för information om hur du uppgraderar din äldre, hemmaanvändningsversion av Office.

## <a name="getting-ready-to-upgrade"></a>Förbereder uppgradering

Som administratör styr du vilken version av Office-personer i organisationen som kan installera. Vi rekommenderar starkt att du hjälper användare i organisationen att köra äldre versioner av Office, till exempel Office 2010, Office 2013 eller Office 2016 uppgradera till den senaste versionen för att dra nytta av dess säkerhets- och produktivitetsförbättringar.

## <a name="upgrade-steps"></a>Steg för att uppgradera

Stegen nedan vägleder dig genom processen att uppgradera användarna till den senaste Office-skrivbordsklienten. Vi rekommenderar att du läser igenom de här stegen innan du påbörjar uppgraderingen.
  
## <a name="step-1---check-system-requirements"></a>Steg 1 - Kontrollera systemkrav

[Kontrollera att office-enheterna](https://products.office.com/office-system-requirements) är kompatibla med den senaste versionen av Office. Nya versioner av Office kan till exempel inte installeras på datorer som kör Windows XP eller Windows Vista.
  
> [!TIP]
> Om du har användare i organisationen som kör äldre versioner av Windows på sina datorer eller bärbara datorer rekommenderar vi att du uppgraderar till Windows 10. Windows 7 har nått slutet av supporten. Läs [support för Windows 7 slutar i januari 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) för mer information.

Kolla in systemkraven för [Windows 10](https://www.microsoft.com/windows/windows-10-specifications) för att se om du kan uppgradera deras operativsystem.

### <a name="check-application-compatibility"></a>Utvärdera programkompatibilitet

För att säkerställa en lyckad uppgradering rekommenderar vi att du identifierar dina Office-program - inklusive VBA-skript, makron, tillägg från tredje part och komplexa dokument och kalkylblad - och att du utvärderar deras kompatibilitet med den senaste versionen av Office.
  
Om du använder tillägg från tredje part med din aktuella Office-installation kontaktar du tillverkaren för att försäkra dig om att tilläggen är kompatibla med den senaste versionen av Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Steg 2 - Kontrollera ditt befintliga abonnemang

I vissa Office 365-abonnemang ingår inte en komplett skrivbordsversion av Office. Stegen för att uppgradera skiljer sig från abonnemang som innehåller Office.
  
Är du osäker på vilken prenumerationsplan du har? Se [Vad Office 365 för företag-prenumeration har jag?](../admin-overview/what-subscription-do-i-have.md)
  
Om ditt befintliga abonnemang innehåller Office kan du fortsätta till [Steg 3 - Avinstallera Office](#step-3---uninstall-office).
  
Om ditt befintliga abonnemang inte innehåller Office väljer du bland alternativen nedan:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Uppgraderingsalternativ för abonnemang som inte innehåller Office

 **Alternativ 1: Växla Office-prenumerationer**

Byt till en prenumeration som innehåller Office. Läs mer i [Byta till ett annat Office 365 för företag-abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md)

**Alternativ 2: Köp enskilda engångsköp av Office eller köp Office via en volymlicens**

 - Köp ett enskilt engångsköp av Office. Se [Office &amp; Home Business](https://products.office.com/home-and-business) eller Office [Professional](https://products.office.com/professional)

     ELLER

 - Köp flera kopior av Office via en volymlicens. Se [Jämför paket som är tillgängliga för volymlicensiering](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Steg 3 - Avinstallera Office

Innan du installerar den senaste versionen av Office rekommenderar vi att du avinstallerar alla äldre versioner av Office. Om du ändrar dig om hur du uppgraderar Office bör du dock tänka på följande instanser där du inte kan installera om Office när du har avinstallerat det.
  
Om du använder tillägg från tredje part bör du kontakta tillverkaren för att se om det finns en uppdatering som fungerar med den senaste versionen av Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Markera den version av Office du vill avinstallera.

- [Från en dator](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [Från en Mac](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Kända problem vid ominstallation av äldre versioner av Office efter en avinstallation

 **Office via en volymlicens** Om du inte längre har tillgång till installationsfilerna för volymlicensversionen av Office kan du inte göra en ominstallation.

 **Office förinstallerat på din dator** Om du inte längre har en skiva eller produktnyckel (om en sådan bifogades) kan du inte göra en ominstallation.

 **Office 365-prenumerationer som inte stöds** Om ditt exemplar av Office har hämtats genom avvecklade prenumerationer, till exempel Office 365 Small Business Premium eller Office 365 Mid-size Business, kan du inte installera en äldre version av Office om du inte har produktnyckeln som medföljde prenumerationen.

Om du föredrar att ha den äldre versionen av Office installerad sida vid sida med den senaste versionen finns mer information i [Installera och använda flera versioner av Office på samma dator](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx). En sida vid sida-installation kan vara rätt val för dig om du till exempel använder tillägg från tredje part i en äldre version av Office och inte kan bekräfta att tilläggen är kompatibla med den senaste versionen.

## <a name="step-4---assign-office-licenses-to-users"></a>Steg 4 - Tilldela licenser till användare

Om du inte redan har gjort det kan du tilldela licenser till alla användare i organisationen som behöver installera Office, läs mer i [Tilldela användare licenser i Office 365 för företag](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Steg 5 - Installera Office

När du har verifierat de användare som du vill uppgradera alla har licenser är det sista steget att låta dem installera Office, se [Hämta och installera om Office på datorn eller Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).
  
> [!TIP]
> Om du inte vill att användarna själva installerar Office kan du läsa mer i artikeln om att [hantera nedladdningsinställningar för programvara i Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). Du kan använda [distributionsverktyget för Office](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) om du vill ladda ned Office-programvaran till ditt lokala nätverk och sedan distribuera Office med hjälp av den programdistributionsmetod som du normalt använder.