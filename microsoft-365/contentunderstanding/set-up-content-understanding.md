---
title: Konfigurera SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Konfigurera innehållstolkning i Project Cortex
ms.openlocfilehash: 1abcc71200642de3f74a92e83299e079ffffb038
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604274"
---
# <a name="set-up-sharepoint-syntex"></a>Konfigurera SharePoint Syntex

Administratörer kan använda Administrationscenter för Microsoft 365 för att konfigurera [Microsoft SharePoint Syntex](index.md). 

Tänk på följande innan du börjar:

- På vilka SharePoint-webbplatser kommer du aktivera formulärbearbetning? Alla, vissa eller utvalda webbplatser?
- Vad heter ditt standard innehållscenter?

Du kan ändra inställningarna efter den första konfigurationen i Administrationscenter för Microsoft 365.

Innan konfigurationen ser du till att planera för det bästa sättet att ställa in och konfigurera innehållstolkning i din miljö. Till exempel behöver du överväga om följande namn av:

- De SharePoint-webbplatser som du vill aktivera formulärbearbetning för – alla, vissa eller utvalda webbplatser
- Ditt innehållscenter och namnet på den primära webbplatsadministratören

## <a name="requirements"></a>Krav 

> [!NOTE]
> Du måste ha behörighet som global administratör eller SharePoint-administratör för att kunna komma åt Administrationscenter för Microsoft 365 och konfigurera innehållstolkning.

Som administratör kan du också göra ändringar i dina valda inställningar när som helst efter konfigurationen och under inställningarna för hantering av innehållstolkning i Administrationscenter för Microsoft 365.

## <a name="to-set-up-sharepoint-syntex"></a>Att konfigurera SharePoint Syntex

1. I Administrationscenter för Microsoft 365 välj **Konfiguration** och se sedan **Filer och innehåll** sektionen.

2. I **Filer och innehåll** sektionen välj **Automatisera innehållstolkning**.<br/>

3. På sidan **Automatisera innehållstolkning** klickar du på **Komma igång** för att gå igenom konfigurationsprocessen.<br/>

    > [!div class="mx-imgBorder"]
    > ![Starta konfiguration](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. På sidan **Konfigurera formulärbearbetning** kan du välja om du vill tillåta att användare kan skapa modeller för formulärbearbetning i vissa dokumentbibliotek i SharePoint. Ett menyalternativ kommer att vara tillgängligt i menyfliksområdet för dokumentbiblioteket för att **Skapa en modell för formulärbearbetning** i dokumentbibliotek i SharePoint där den är aktiverad.
 
     För **vilka SharePoint-bibliotek som ska visa alternativ för att skapa modell för formulärbearbetning** kan du välja:</br>
      - **Alla SharePoint-bibliotek** för att göra det tillgängligt för alla SharePoint-bibliotek i organisationen.</br>
      - **Bara bibliotek på utvalda webbplatser** och välj sedan de webbplatser där du vill göra det tillgängligt eller ladda upp en lista med upp till 50 webbplatser.</br>
      - **Inga SharePoint-bibliotek** om du inte vill att det ska vara tillgängligt för några webbplatser (du kan ändra det när konfigurationen är slutförd).

   > [!div class="mx-imgBorder"]
   > ![Konfigurera formulärbearbetning](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Att ta bort en webbplats efter att den har inkluderats påverkar inte befintliga modeller som används i biblioteken på webbplatsen eller möjligheten att använda modeller för dokumenttolkning på ett bibliotek. 
    
5. På sidan **Skapa innehållscenter** kan du skapa en SharePoint-webbplats för innehållscenter där dina användare kan skapa och hantera modeller för dokumenttolkning.

    1. För **Webbplatsnamn** skriver du namnet som du vill använda på webbplatsen för innehållscenter.
    
    1. **Webbplatsens adress** kommer att visa URL:en för din webbplats baserat på vad du valde som webbplatsnamn. Om du vill ändra det klickar du på **Redigera**.

       > [!div class="mx-imgBorder"]
       > ![Skapa innehållscenter](../media/content-understanding/admin-cu-create-cc.png)</br>

       Välj **Nästa**.

6. På sidan **Granska och slutför** kan du titta på vald inställning och välja att göra ändringar. Om du är nöjd med dina val väljer du **Aktivera**.

7. På bekräftelsesidan klickar du på **Klar**.

8. Du kommer tillbaka till sidan **Automatisera innehållstolkning**. På den här sidan kan du välja **Hantera** om du vill göra ändringar i dina konfigurationsinställningar. 

## <a name="assign-licenses"></a>Tilldela licenser

När du har konfigurerat en SharePoint Syntex måste du tilldela licenser för de användare som kommer att använda SharePoint Syntex-funktioner.

För att tilldela licenser:

1. I Administrationscenter för Microsoft 365 klickar du på **Användare** > **Aktiva användare**.

2. Välj de användare som du vill licensiera och klicka på **Hantera produktlicenser**.

3. Välj **Tilldela fler**.

4. Välj **SharePoint Syntex**. Under **Appar** kontrollerar du att **Common Data Service for SharePoint Syntex**, **SharePoint Syntex** och **SharePoint Syntex – SPO-typ** är alla markerade.

    > [!div class="mx-imgBorder"]
    > ![SharePoint Syntex-licenser i Administrationscentret för Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. Klicka på **Spara ändringar**.

## <a name="ai-builder-credits"></a>AI Builder-krediter

Om du har 300 eller fler SharePoint Syntex-licenser för SharePoint Syntex i din organisation allokeras en miljon AI Builder-krediter. Om du har färre än 300 licenser måste du köpa AI Builder-krediter för att kunna använda formulärbearbetning.

Du kan beräkna den AI Builder-kapacitet som passar dig bäst med [Kalkylatorn för AI Builder](https://powerapps.microsoft.com/ai-builder-calculator).

Gå till [Administrationscenter för Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) om du vill kontrollera krediterna och användningen.

## <a name="see-also"></a>Se även

[Översikt över modellen för formulärbearbetning](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[Steg för steg: Hur du skapar en modell för dokumenttolkning (video)](https://www.youtube.com/watch?v=DymSHObD-bg)

