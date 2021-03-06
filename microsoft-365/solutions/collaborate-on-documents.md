---
title: Samar beta med gäster i ett dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663517"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samar beta med gäster i ett dokument

Om du behöver samar beta med personer utanför organisationen för dokument i SharePoint eller OneDrive kan du skicka dem en delning – länka till dokumentet. I den här artikeln går vi igenom konfigurations stegen för Microsoft 365 som behövs för att konfigurera delning – Länkar för SharePoint och OneDrive för organisationen.

## <a name="video-demonstration"></a>Videodemonstration

I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Inställningar för extern samarbete i Azure

Delning i Microsoft 365 regleras på högsta nivå av [B2B-inställningen för externt samarbete i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.

Kontrol lera inställningarna för externt samarbete för B2B för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för extern samarbete

1. Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.
3. Klicka på **externa identiteter**.
4. Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .
5. Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **samarbets begränsningar** . Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data. Detta hindrar dem från att se vem som är gäst i katalogen. För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.

## <a name="sharepoint-organization-level-sharing-settings"></a>Delnings inställningar för SharePoint på organisations nivå

För att personer utanför din organisation ska ha till gång till ett dokument i SharePoint eller OneDrive måste delnings inställningarna för SharePoint och OneDrive tillåta delning med personer utanför organisationen.

Inställningarna på organisations nivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser. Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå. Inställningen på organisations nivå för OneDrive bestämmer vilken nivå av delning som ska vara tillgänglig i användarnas OneDrive-bibliotek.

Om du vill tillåta icke verifierade fil-och mappdelning för SharePoint och OneDrive väljer du **vem som helst**. Om du vill vara säker på att personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**. *Alla* länkar är det enklaste sättet att dela: personer utanför din organisation kan öppna länken utan att det är möjligt att överföra den till andra.

För SharePoint väljer du den mest krävda inställning som behövs av någon webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delnings inställningar för SharePoint på organisations nivå

1. Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.
2. Klicka på **delning** **i det** vänstra navigerings fältet i administrations centret för SharePoint.
3. Kontrol lera att extern delning för SharePoint eller OneDrive är inställt på **vem som helst** eller **nya och befintliga gäster**. (Observera att OneDrive-inställningen inte kan bli mer tillåtna än SharePoint-inställningen.)
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Inställningar för SharePoint-standardinställningar på organisations nivå

Standardinställningen för fil-och mappikonen styr det länk alternativ som visas för användarna som standard när de delar en fil eller mapp. Användare kan ändra länktyp till något av de andra alternativen innan de delas, om så önskas.

Tänk på att den här inställningen påverkar SharePoint-webbplatser i din organisation samt OneDrive.

Välj en länk från någon av följande typer som sedan är markerad som standard när användare delar filer och mappar:

- **Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra mängder av overifierade fil-och mappdelning. Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard. Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.
- **Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.
- **Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna. Den här typen av länk fungerar med gäster och kräver att de autentiseras.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du inställningar för SharePoint-och OneDrive-standardinställningar på organisations nivå

1. Gå till sidan delning i administrations centret för SharePoint.
2. Under **fil-och mappaktiviteter** väljer du den standard delnings länk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

Om du vill ange behörighet för delnings länken under **Välj den behörighet som är markerad som standard för delning av länkar.**

1. Välj **Visa** om du inte vill att oautentiserade användare ska kunna ändra filerna och mapparna.
2. Välj **Redigera** om du vill tillåta att overifierade användare gör ändringar i filerna och mapparna.

Observera att ovanstående två försändnings alternativ kan tillämpas inte enbart för gäster och externa användare utan även för interna användare. Det behörighets alternativ du väljer avgörs av själv.

Så här anger du behörigheter för länkar som tillåter delning med vem som helst

1. Under de **här länkarna kan du ge behörigheterna:** under fönster rutan 
    1. Från List rutan **filer** 
        - Välj **Visa och redigera** om du vill tillåta att overifierade användare gör ändringar i filerna.
        - Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i filerna.
    2. Från List rutan **mappar**
        - Välj **Visa, redigera och ladda upp** om du vill tillåta att overifierade användare gör ändringar i mapparna.
        - Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i mapparna.

## <a name="sharepoint-site-level-sharing-settings"></a>Delnings inställningar på SharePoint-webbplats nivå

Om du delar filer och mappar på en SharePoint-webbplats måste du också kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Ange delnings inställningar på webbplats nivå

1. I administrations centret för SharePoint, i det vänstra navigerings fönstret, expanderar du **webbplatser** och klickar på **aktiva webbplatser**.
2. Välj den webbplats där du vill dela filer och mappar med gäster.
3. Bläddra till höger på raden (där den valda webbplatsen finns) och klicka någonstans i kolumnen **extern delning** .
4. Klicka på fliken **principer** på sidan som visas.
5. Klicka på **Redigera** under fönstret **extern delning** .
6. Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.
7. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjuda in användare

Inställningar för gäst delning är nu konfigurerade; användare kan nu dela filer och mappar med personer utanför organisationen. Mer information finns i [dela OneDrive-filer och-mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[SharePoint och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
