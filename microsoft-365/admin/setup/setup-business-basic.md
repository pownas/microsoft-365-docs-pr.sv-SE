---
title: Konfigurera Microsoft 365 Business Basic
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Lär dig hur du konfigurerar din Microsoft 365 Business Basic-abonnemang.
ms.openlocfilehash: b40b6a633c9c6c25daa4607c9e05178a1f418c51
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350221"
---
# <a name="set-up-microsoft-365-business-basic"></a>Konfigurera Microsoft 365 Business Basic

 Titta på en kort video om hur du konfigurerar Microsoft 365 Business Basic.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Lägga till din domän för att personanpassa inloggning

När du köper Microsoft 365 Business Basic får du möjlighet att använda en domän som du äger eller köpa en under registreringen.

- Om du har köpt en ny domän när du registrerade dig kommer din domän att konfigureras, och du kan gå vidare till [Lägga till användare och tilldela licenser](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Om du använder Office 365 Germany går du till [det här administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041).

::: moniker-end

::: moniker range="o365-21vianet"

1. Om du använder Office 365 som drivs av 21Vianet går du till [det här administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627).

::: moniker-end 

2. Starta guiden genom att välja **Gå till inställningar**.
    
3. Under steget **Lägg till domän** anger du domännamnet du vill använda (t.ex. contoso.com).

    > [!IMPORTANT]
    > Om du har köpt en domän under registreringen ser du inte steget **Lägg till en domän** här. Gå istället till [Lägg till användare](#add-users-and-assign-licenses).

    
4. Följ anvisningarna i guiden för att [Skapa DNS-poster på vilken DNS-värd som helst för Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) som verifierar att du äger domänen. Om du vet vilken din domänvärd är kan du även se [Värdspecifika anvisningar](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Om din värd är GoDaddy eller en annan värd som är aktiverad med [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)är processen enkel och du blir automatiskt ombedd att logga in och låta Microsoft autentisera.

    ![Välj Auktorisera på sidan Bekräfta Åtkomst hos GoDaddy.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Lägga till användare och tilldela licenser

Du kan lägga till användare i guiden eller så kan du [lägga till användare senare](../add-users/add-users.md) i administratörscentret. Om du har en lokal domänkontrollant kan du även lägga till användare med [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Lägg till användare i guiden

Alla användare som du lägger till i guiden får automatiskt en Microsoft 365 Business Basic-licens.

1. Om ditt Microsoft 365 Business Basic-abonnemang har befintliga användare (till exempel om du använde Azure AD Connect), får du möjlighet att tilldela licenser till dem nu. Lägg till licenser till dem också.

2. Efter att ha lagt till användarna får du också möjlighet att dela autentiseringsuppgifter med de nya användarna som du har lagt till. Du kan välja att skriva ut, e-posta eller ladda ned.

## <a name="connect-your-domain"></a>Koppla din domän

> [!NOTE]
> Om du väljer att använda .onmicrosoft-domänen, eller använde Azure AD Connect för att konfigurera användare, kommer du inte att se det här steget.
  
För att få igång tjänsten måste du uppdatera några poster hos din DNS-värd eller domänregistrator.
  
1. Installationsguiden identifierar normalt din domänregistrator och ger dig en länk till stegvisa instruktioner för att uppdatera dina NS-poster på registratorns webbplats. Om det inte gör det, [ ändra namnservrar för att konfigurera Office 365 med valfri domänregistrator](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Om du har befintliga DNS-poster, t. ex. en befintlig webbplats, men din DNS-värd är aktiverad för [Domain Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect)väljer du **Lägga till poster för mig**. På sidan **Välj onlinetjänster** accepterar du alla standardinställningar och väljer **Nästa**och väljer **Auktorisera** på DNS-värdens sida.
    - Om du har befintliga DNS-poster med andra DNS-värdar (inte aktiverad för domänanslutning), ska du hantera dina egna DNS-poster för att se till att de befintliga tjänsterna fortsätter att vara anslutna. Mer information finns i [domängrunder](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics).

2. Följ stegen i guiden så kommer e-postmeddelanden och andra tjänster att konfigureras åt dig.

    När registreringsprocessen är klar dirigeras du till administrationscentret, där du kan lägga till användare och tilldela licenser. När du har slutfört den första konfigurationen kan du använda **konfigurationssidan** i administrationscentret och fortsätta att installera och konfigurera tjänsterna som medföljer prenumerationerna.

    Mer information om installationsguiden för och administrationscentrets **konfigurationssida** finns i [Skillnaden mellan installationsguiden och sidan Konfigurera](o365-setup-wizard-and-setup-page.md).