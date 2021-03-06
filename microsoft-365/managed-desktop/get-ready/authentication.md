---
title: Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord
description: Viktiga steg för att se till att en Azure AD kan kommunicera med lokal annons för att tillhandahålla
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7181e81a2db94ce26fb8601f8b9156c65084c439
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289585"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Förbereda lokala resurser till gång för Microsoft Hanterat skrivbord

På Microsoft Managed Desktop är enheter automatiskt anslutna till Azure Active Directory (Azure AD). Det innebär att om du använder en lokal Active Directory måste du kontrol lera vissa saker för att säkerställa att enheter som är anslutna till Azure AD kan kommunicera med din lokala Active Directory. 

> [!NOTE]  
> *Hybrid* Azure AD Join stöds inte av Microsoft Managed Desktop.

Med Azure Active Directory kan användarna dra nytta av enkel inloggning (SSO), vilket innebär att de vanligt vis inte måste ange autentiseringsuppgifter varje gång de använder resurser.

Information om hur du ansluter till Azure Active Directory finns i så här gör du för att [Planera din implementering av Azure AD Join](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Bakgrunds information om enkel inloggning (SSO) på enheter som är anslutna till Azure AD finns i [hur SSO till lokala resurser fungerar på Azure AD-anslutna enheter](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


I det här avsnittet förklaras de saker du måste kontrol lera för att se till att appar och andra resurser som är beroende av lokala Active Directory-anslutningar fungerar smidigt med Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Enkel inloggning för lokala resurser

Enkel inloggning (SSO) med UPN och lösen ord är aktiverat som standard på Microsoft Managed Station ära enheter. Men användarna kan även använda Windows Hello för företag, vilket kräver ytterligare konfigurations steg. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Enkel inloggning med UPN och lösen ord

I de flesta organisationer kan användarna använda SSO för att autentisera sig via UPN och lösen ord på Microsoft Managed Station ära enheter. För att det ska fungera bör du kontrol lera följande:

- Kontrol lera att Azure AD Connect är installerat och använder en lokal Active Directory-server med Windows Server 2008 R2 eller senare.
- Kontrol lera att Azure AD Connect kör en version som stöds och är inställd på att synkronisera dessa tre attribut med Azure AD: 
    - DNS-domännamn för den lokala Active Directory (där användarna finns)
    - NetBIOS för din lokala Active Directory (där användarna finns)
    - Användarens SAM-konto namn


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Enkel inloggning med Windows Hello för företag

Microsoft Managed Station ära datorer ger också användarna en snabb, lösenordsskyddad upplevelse genom att använda Windows Hello för företag. För att se till att Windows Hello för företag fungerar utan att användarna måste tillhandahålla respektive UPN och lösen ord, kan du gå till [Konfigurera Azure AD-anslutna enheter för lokal inloggning med Windows Hello för företag](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) för att kontrol lera kraven och sedan följa anvisningarna där.


## <a name="apps-and-resources-that-use-authentication"></a>Appar och resurser som använder inloggningsautentisering

Information om hur du använder [program och resurser](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) i Azure-innehålls uppsättning för fullständig vägledning om hur du konfigurerar appar så att de fungerar med Azure Active Directory. Sammanfattning:


- Om du använder **molnbaserade program**, till exempel de som lagts till i Azure AD App-galleriet, behöver du inte längre förbereda dig för att arbeta med Microsoft Managed Desktop. Men alla Win32-appar som inte använder WAM (Web Account Manager) kan fortfarande uppmana användare att verifiera.

- Om du har en **lokal värd**för appar kan du lägga till dem i listan över tillförlitliga platser i webbläsaren. Detta gör att Windows-autentisering fungerar smidigt utan att användare uppmanas att ange autentiseringsuppgifter. För att göra det, se [tillförlitliga platser](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) i [referens för konfigurerbara inställningar](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Om du använder Active Directory-federerade tjänster kontrollerar du att SSO är aktiverat med hjälp av stegen i [Verifiera och hantera enkel inloggning med AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- För program som är **lokala och använder äldre protokoll**behövs ingen extra installation, så länge enheter har åtkomst till en lokal domänkontrollant för autentisering. För att tillhandahålla säker åtkomst för dessa program bör du Distribuera Azure AD Application Proxy. Mer information finns i [fjärråtkomst till lokala program via Azure Active Directorys programproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Appar som körs **lokalt och som använder datorautentisering** stöds inte, så du bör överväga att ersätta dessa med nyare versioner.

### <a name="network-shares-that-use-authentication"></a>Nätverks resurser som använder inloggningsautentisering

Det krävs inga extra inställningar för att användare ska få åtkomst till nätverks resurser, förutsatt att enheterna har åtkomst till en lokal domänkontrollant genom att använda en UNC-sökväg.

### <a name="printers"></a>3100cn

Microsoft Managed Station ära datorer kan inte ansluta till skrivare som publiceras i din lokala Active Directory om du inte har konfigurerat [hybrid moln utskrift](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

När skrivare inte kan identifieras automatiskt i en miljö med endast moln kan användarna använda lokala skrivare genom att använda skrivar Sök vägen eller utskrifts kön, förutsatt att enheterna har åtkomst till en lokal domänkontrollant.

<!--add fuller material on printers when available-->
