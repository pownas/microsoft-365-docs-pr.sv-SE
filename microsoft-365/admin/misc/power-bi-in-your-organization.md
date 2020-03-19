---
title: Power BI i organisationen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Läs mer om Power BI och hur användare i organisationen kan använda den här företagsanalystjänsten.
ms.openlocfilehash: 4d89594812486d06629d614ab0c59fba09dcdad8
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807245"
---
# <a name="power-bi-in-your-organization"></a>Power BI i organisationen

På den här sidan beskrivs hur användare i organisationen kan använda Power BI, och hur du kan styra hur din organisation tar del av den här tjänsten.
    
## <a name="what-is-power-bi"></a>Vad är Power BI?

Med Microsoft Power BI kan användarna visualisera data, dela upptäckter med varandra och samarbeta på nya och intuitiva sätt. Mer information finns på [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Uppfyller Power BI nationella, regionala och branschspecifika efterlevnadskrav?

Mer information om Power BI-efterlevnad finns i [Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>Hur registrerar sig användarna för Power BI?

Som administratör kan du registrera dig för Power BI via [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/). Du kan också registrera dig via sidan köptjänster i administrationscentret för Microsoft 365. När administratörer registrerar sig för Power BI kan de tilldela prenumerationslicenser till användare som bör ha åtkomst.
  
Dessutom kan enskilda användare i organisationen registrera sig för Power BI via [Power BI-webbplatsen](https://powerbi.microsoft.com/en-us/). När en användare i organisationen registrerar sig för Power BI tilldelas den användaren en Power BI-licens automatiskt.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>Hur registrerar sig enskilda användare inom organisationen?

Det finns tre situationer som kan gälla för användare i organisationen:
  
### <a name="scenario-1-your-organization-already-has-an-existing-office-365-environment-and-the-user-signing-up-for-power-bi-already-has-an-office-365-account"></a>Situation 1: Organisationen har redan en befintlig Office 365-miljö och användaren som registrerar sig för Power BI har redan ett Office 365-konto.

I den här situationen, där användaren redan har ett konto för arbetet eller skolan hos klientorganisationen (t.ex. contoso.com) men ännu inte har Power BI, aktiverar Microsoft helt enkelt abonnemanget för kontot, och användaren får automatiskt ett meddelande om hur man använder Power BI-tjänsten.
  
### <a name="scenario-2-your-organization-has-an-existing-office-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-an-office-365-account"></a>Situation 2: Organisationen har redan en befintlig Office 365-miljö men användaren som registrerar sig för Power BI har inget Office 365-konto.

I den här situationen har användaren en e-postadress i organisationens domän (t.ex. contoso.com), men har ännu inte något Office 365-konto. I det här fallet kan användaren registrera sig för Power BI och automatiskt tilldelas ett konto. Efter det har användaren tillgång till Power BI-tjänsten. Exempel: Om en anställd med namnet Nancy använder sin e-postadress för arbetet (t.ex. Nancy@contoso.com ) för att registrera sig, lägger Microsoft automatiskt till Nancy som användare i Contosos Office 365-miljö och aktiverar Power BI för hennes konto.
  
### <a name="scenario-3-your-organization-does-not-have-an-office-365-environment-connected-to-your-email-domain"></a>Situation 3: Organisationen har ingen Office 365-miljö ansluten till e-postdomänen.

Organisationen behöver inte vidta några administrativa åtgärder för att kunna dra nytta av Power BI.
  
> [!IMPORTANT]
> Om din organisation har flera e-postdomäner och föredrar att alla e-postadresstillägg finns i samma klientorganisation lägger du till alla e-postadressdomäner i klienten innan några användare skapar din primära klient, alla e-postadressdomäner till klienten innan några användare skapar din primära klientorganisation. Det finns ingen automatiserad mekanism för att flytta användare över klienter efter att de har skapats. Mer information om den här processen finns i [Om jag har flera domäner, kan jag styra Office 365-klienten som användare läggs till i senare](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) i den här artikeln och lägga till en domän i Office [365](../setup/add-domain.md) online. 
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hur ändrar det här mitt nuvarande sätt att hantera identiteter för organisationens användare?

Om organisationen redan har en befintlig Office 365-miljö och alla användare i organisationen har Office 365-konton, ändras inte identitetshanteringen.
  
Om organisationen redan har en befintlig Office 365-miljö men inte alla användare i organisationen har Office 365-konton, skapas en användare i klientorganisationen och licenser tilldelas baserat på användarens e-postadress för arbetet eller skolan. Det innebär att antalet användare som du hanterar växer efter hand som användare inom organisationen registrerar sig för tjänsten.
  
Om du hanterar katalogen lokalt och använder AD FS (Active Directory Federation Services), så kommer Microsoft inte att lägga till några användare i klientorganisationen, och användare som försöker gå med i klientorganisationen får ett meddelande om att de ska kontakta organisationens administratör.
  
Om organisationen inte har någon Office 365-miljö kopplad till din e-postdomän så blir det ingen förändring i hur du hanterar identiteter. Användarna läggs till i en ny, molnbaserad användarkatalog, och du har möjlighet att välja att ta över som administratör för klientorganisationen och hantera dem.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Vilken är processen för att hantera en klientorganisation som skapats av Microsoft för mina användare?

Om en klientorganisation har skapats av Microsoft kan du begära och hantera klientorganisationen genom att följa stegen nedan:
  
1. Anslut till klientorganisationen genom att [registrera dig för Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) med en e-postadressdomän som överensstämmer med den klientorganisationsdomän som du vill hantera. Om Microsoft t.ex. skapade klientorganisationen contoso.edu, så måste du ansluta till klientorganisationen med en e-postadress som slutar med @contoso.edu. 
    
2. Begära administratörskontroll genom att verifiera att du äger domänen: du kan ge dig själv administratörsrollen genom att verifiera att du äger domänen. Gör så här:
 
::: moniker range="o365-worldwide"
   
3. Gå till [https://admin.microsoft.com](https://admin.microsoft.com).
 

::: moniker-end

::: moniker range="o365-germany"

3. Gå till [https://portal.office.de](https://portal.office.de).

::: moniker-end

::: moniker range="o365-21vianet"

3. Gå till [https://portal.partner.microsoftonline.cn](https://portal.partner.microsoftonline.cn).

::: moniker-end

    
4. Välj ikonen för startprogrammet i det övre vänstra hörnet, och välj sedan **Admin**.
    
    ![The Office 365 app launcher with the Admin app highlighted](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Läs instruktionerna på **sidan Bli admin** och välj sedan **Ja, jag vill vara admin**.
    
    > [!NOTE]
    >  Om det här alternativet inte visas finns det redan en administratör på plats. 
  
## <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Om jag har flera domäner, kan jag styra vilken Office 365-klientorganisation som användare läggs till i?

Om du inte gör någonting skapas en klientorganisation för varje e-postdomän och e-postunderdomän för användare.
  
Om du vill att alla användare ska finnas i samma klientorganisation, oavsett e-postadresstillägg, gör du följande:
  
- Skapa en målklientorganisation i förväg eller använd en befintlig klientorganisation, och lägg till alla befintliga domäner och underdomäner som du vill samla i den klientorganisationen. Då kommer alla användare med e-postadresser som slutar med de domänerna och underdomänerna automatiskt att gå med i målklientorganisationen när de registrerar sig.
    
> [!IMPORTANT]
> Det finns ingen automatiserad mekanism för att flytta användare mellan klientorganisationer när de har skapats. Mer information om hur du lägger till domäner i en enda Office 365-klientorganisation finns [i Lägga till en domän i Office 365](../setup/add-domain.md). 
  
> [!IMPORTANT]
> Mer information och vägledning om hur du hanterar klienter finns i [Vad är Power BI-administration?](https://docs.microsoft.com/power-bi/service-admin-administering-power-bi-in-your-organization). 
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Hur kan jag förhindra att användare ansluter sig till min befintliga Office 365-klientorganisation?

Det finns åtgärder du kan vidta som administratör för att förhindra att användare ansluter sig till din befintliga Office 365-klientorganisation. Om du blockerar detta misslyckas användarnas försök att logga in och de kommer att uppmanas att kontakta organisationens administratör. Du behöver inte upprepa den här processen om du redan har inaktiverat automatisk licensdistribution tidigare (t.ex.
  
För de här stegen måste du använda Windows PowerShell. Om du vill få hjälp med att komma igång med Windows PowerShell kan du läsa [PowerShell Komma igång](https://go.microsoft.com/fwlink/p/?LinkID=286814).
  
För att utföra följande steg måste du installera den senaste 64-bitarsversionen av [Azure Active Directory-modul för Windows PowerShell](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).
  
När du har valt länken väljer du **Kör** för att köra installationspaketet. 
  
 **Inaktivera automatisk anslutning till klientorganisation**: Använd det här Windows PowerShell-kommandot för att hindra nya användare från att ansluta till en hanterad klientorganisation:
  
Så här inaktiverar du automatisk anslutning till klientorganisation för nya användare:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Så här aktiverar du automatisk anslutning till klientorganisation för nya användare:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Den här blockeringen förhindrar att nya användare i organisationen registrerar sig för Power BI. Användare som registrerar sig för Power BI innan nya registreringar för din organisation inaktiveras behåller fortfarande sina licenser. Se [Hur tar jag bort Power BI för användare som redan har registrerat sig?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) 
  
## <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Hur tillåter jag att användare ansluter till min befintliga Office 365-klientorganisation?

Om du vill tillåta att användarna ansluter till klientorganisationen inverterar du kommandot som anges i frågan ovan:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Hur verifierar jag om jag har blockering aktiverad i klientorganisationen?

Använd följande PowerShell-skript:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Hur kan jag förhindra att min befintliga användare börjar använda Power BI?

 **Inaktivera automatisk licensdistribution:** Använd det här Windows PowerShell-skriptet för att inaktivera automatiska licensdistributioner för befintliga användare. Du behöver inte upprepa den här processen om du redan har inaktiverat automatisk licensdistribution tidigare (t.ex. 
  
Så här inaktiverar du automatisk licensdistribution för befintliga användare:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Så här aktiverar du automatisk licensdistribution för befintliga användare:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> Flaggan *AllowAdHocSubscriptions* används för att styra flera användarfunktioner i organisationen, inklusive möjligheten för användare att registrera sig för Azure Rights Management Service. Om den här flaggan ändras, påverkas alla de här funktionerna. 
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Hur tillåter jag att de befintliga användarna registrerar sig för Power BI?

Om du vill tillåta att användarna registrerar sig för Power BI inverterar du kommandot som anges i frågan ovan:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Hur tar jag bort Power BI för användare som redan registrerat sig?

Om en användare har registrerat sig för Power BI-men du inte längre vill att de ska ha åtkomst till Power BI, kan du ta bort Power BI-licensen för den användaren.

::: moniker range="o365-worldwide"

> [!NOTE]
> Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.
  
1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
    
2. Hitta den användare du vill ta bort licensen för och välj sedan deras namn.
    
3. Avmarkera kryssrutan Microsoft Power **BI** på fliken **Licenser och Appar.**
    
4. Välj **Spara ändringar**.

::: moniker-end

  
::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.

2. Hitta den användare du vill ta bort licensen för och välj sedan deras namn.
    
3. Välj **Redigera**bredvid **Produktlicenser**. 
    
4. Stäng av **alternativet Microsoft Power BI.**
    
5. Välj **Spara**.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.

2. Hitta den användare du vill ta bort licensen för och välj sedan deras namn.
    
3. Välj **Redigera**bredvid **Produktlicenser**. 
    
4. Stäng av **alternativet Microsoft Power BI.**
    
5. Välj **Spara**.

::: moniker-end 


## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Hur vet jag när nya användare har anslutit till min klientorganisation?

Användare som har anslutit till din klientorganisation som en del av det här programmet tilldelas en unik licens som du kan filtrera efter i det aktiva användarfönstret på instrumentpanelen för administratörer.
  
Om du vill skapa den nya vyn följer du stegen i [Skapa en anpassad användarvy](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view)i administrationscentret. Välj **Microsoft Power BI**under **Tilldelad produktlicens**. När den nya vyn har skapats kan du se alla användare i din klientorganisation som har registrerat sig i det här programmet.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Finns det något annat som jag ska vara förberedd på?

Du får eventuellt fler förfrågningar om återställning av lösenord. Mer information om den här processen finns i [Återställa en användares lösenord](../add-users/reset-passwords.md).
  
Du kan ta bort en användare från din klient via standardprocessen i administrationscentret. Men om användaren fortfarande har en aktiv e-postadress från organisationen kan de ansluta igen såvida du inte blockerar alla användare från att ansluta.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-office-365-tenant"></a>Varför dök 1 miljon licenser för Microsoft Power BI upp i min Office 365-klientorganisation?

Eftersom din organisation är kvalificerad, är användare inom organisationen behöriga att använda Microsoft Power BI-tjänsten, och de här licenserna representerar den tillgängliga kapaciteten för nya Power BI-användare inom klientorganisationen. Ingen avgift utgår för de här licenserna. Om du har valt att tillåta användare att registrera sig för Power BI själva tilldelas de en av dessa tillgängliga kostnadsfria licenser när de slutför registreringsprocessen. Du kan också välja att tilldela dessa licenser till användare själv via administrationscentret.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Kostar det någonting? Debiteras jag för licenserna?

Licenserna gäller för den kostnadsfria versionen av Power BI. Om du vill ha fler funktioner kan du ta en titt på Power BI Pro.
  
## <a name="why-1-million-licenses"></a>Varför 1 miljon licenser?

Vi valde ett nummer som var tillräckligt stort för att majoriteten av organisationerna skulle ha gott om licenser för att ge denna förmån utan dröjsmål till sina användare.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>Vad händer om jag behöver mer än 1 miljon licenser?

Kontakta din Microsoft-kontorepresentant för mer information om du behöver skaffa ytterligare licenser.