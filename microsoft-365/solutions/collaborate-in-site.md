---
title: Samarbeta med gäster på en webbplats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords: NOCSH
description: Läs om hur du samarbetar med gäster på en SharePoint-webbplats.
ms.openlocfilehash: 3a7c14cc4cd31961b0d4c1054f88b5ed276b3b1a
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42808777"
---
# <a name="collaborate-with-guests-in-a-site"></a>Samarbeta med gäster på en webbplats

Om du behöver samarbeta med gäster över dokument, data och listor kan du använda en SharePoint-webbplats. Moderna SharePoint-webbplatser är anslutna till Office 365-grupper som kan hantera webbplatsmedlemskapet och tillhandahålla ytterligare samarbetsverktyg som en delad postlåda och kalender.

I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera en SharePoint-webbplats för samarbete med gäster.

## <a name="video-demonstration"></a>Videodemonstration

I det här videoklippet visas de konfigurationssteg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a>Inställningar för Azure-organisationsrelationer

Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory. Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan Inställningar för Azure Active Directory-organisationsrelationer](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för organisationsrelationer

1. Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .
2. Klicka på Azure **Active Directory**i den vänstra navigeringen .
3. Klicka på **Organisationsrelationer**i **fönstret Översikt.**
4. Klicka på **Inställningar**i fönstret **Organisationsrelationer** .
5. Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Samarbetsbegränsningar.** Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

## <a name="office-365-groups-guest-settings"></a>Gästinställningar för Office 365-grupper

Moderna SharePoint-webbplatser använder Office 365-grupper för att styra webbplatsåtkomsten. Gästinställningarna för Office 365-grupper måste vara aktiverade för att gäståtkomsten i SharePoint-webbplatser ska fungera.

![Skärmbild av gästinställningar för Office 365 Grupper i microsoft 365-administrationscentret](../media/office-365-groups-guest-settings.png)

Så här anger du gästinställningar för Office 365-grupper

1. Expandera **Inställningar**i det vänstra navigeringsfältet i Microsoft 365 i det vänstra navigeringscentret .
2. Klicka på **Tjänster & tillägg**.
3. Klicka på **Office 365 Grupper**i listan .
4. Kontrollera att kryssrutorna **Låt gruppmedlemmar utanför organisationen får åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper** är markerade.
5. Om du har gjort ändringar klickar du på **Spara ändringar**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Delningsinställningar för SharePoint-organisationsnivå

För att gästerna ska få tillgång till SharePoint-webbplatser måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.

Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser. Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.

Om du vill tillåta oautentiserade fil- och mappdelning väljer du **Alla**. Om du vill vara säkra på att alla personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster**. Välj den mest tillåtande inställningen som behövs av en webbplats i organisationen.

![Skärmbild av delningsinställningar på SharePoint-organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delningsinställningar för SharePoint-organisationsnivå

1. Klicka på **SharePoint**under **Administrationscenter i administrationscentret**för Microsoft 365, i den vänstra navigeringen.
2. Klicka på **Dela**i administrationscentret för SharePoint i det vänstra navigeringscentret.
3. Kontrollera att extern delning för SharePoint är inställt **på Alla** eller Nya och **befintliga gäster**.
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-site"></a>Skapa en webbplats

Nästa steg är att skapa den webbplats som du planerar att använda för att samarbeta med gäster.

Så här skapar du en webbplats
1. Klicka på **Aktiva webbplatser**under **Webbplatser**i Administrationscentret för SharePoint.
2. Klicka på **Skapa**.
3. Klicka på **Gruppwebbplats**.
4. Skriv ett webbplatsnamn och ange ett namn för gruppägaren (webbplatsägaren).
5. Under **Avancerade inställningar**väljer du om du vill att det ska vara en offentlig eller privat webbplats.
6. Klicka på **Nästa**.
7. Klicka på **Slutför**.

Vi bjuder in användare senare. Därefter är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för den här webbplatsen.

## <a name="sharepoint-site-level-sharing-settings"></a>Delningsinställningar för SharePoint-webbplatsnivå

Kontrollera delningsinställningarna på webbplatsnivå för att se till att de tillåter den typ av åtkomst som du vill ha för den här webbplatsen. Om du till exempel anger inställningarna på organisationsnivå till **Alla**, men vill att alla gäster ska autentisera för den här webbplatsen, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på **Nya och befintliga gäster**.

Observera att webbplatsen inte kan delas med oautentiserade personer (**Någon** inställning), men enskilda filer och mappar kan.

![Skärmbild av externa delningsinställningar för SharePoint-webbplatsen](../media/sharepoint-site-external-sharing-settings.png)

Så här anger du delningsinställningar på webbplatsnivå
1. Expandera **Platser** i det vänstra navigeringscentret i administrationscentret för SharePoint och klicka på **Aktiva webbplatser.**
2. Välj den webbplats som du just skapade.
3. Klicka på **Dela**i menyfliksområdet .
4. Se till att delning är inställt **på Vem som helst** eller Nya och befintliga **gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjud in användare

Gästdelningsinställningarna är nu konfigurerade, så att du kan börja lägga till interna användare och gäster på webbplatsen. Webbplatsåtkomsten styrs via den associerade Office 365-gruppen, så vi lägger till användare där.

Så här bjuder du in interna användare till en grupp
1. Navigera till den webbplats där du vill lägga till användare.
2. Klicka på **Medlemmar** längst upp till höger.
3. Klicka på **Lägg till medlemmar**.
4. Skriv namnen eller e-postadresserna till de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.

Gästanvändare kan inte läggas till från webbplatsen. Du måste lägga till dem med Outlook på webben.

Så här bjuder du in gäster till en grupp
1. Klicka på den grupp där du vill lägga till medlemmar under **Grupper**i Outlook på webben.
2. Öppna gruppkontaktkortet och klicka sedan på Lägg **till medlemmar**under **Fler alternativ** (...).
3. Skriv e-postadresserna till de gäster som du vill bjuda in och klicka sedan på **Lägg till**.
4. Klicka på **Stäng**.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när du delar med gäster](share-limit-accidental-exposure.md)

[Skapa en säker gästdelningsmiljö](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
