---
title: Azure-integrering med Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integrera Microsoft 365 med Azure AD om du vill ha Lösenordssynkronisering eller enkel inloggning med din lokala miljö.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384741"
---
# <a name="azure-integration-with-microsoft-365"></a>Azure-integrering med Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

I Microsoft 365 används Azure Active Directory (Azure AD) för att hantera användar identiteter bakom kulisserna. Ditt Microsoft 365-abonnemang innehåller ett kostnads fritt Azure AD-abonnemang så att du kan integrera dina lokala Active Directory Domain Services (AD DS) för att synkronisera användar konton och lösen ord eller konfigurera en enkel inloggning. Du kan också köpa avancerade funktioner för att hantera dina konton bättre.
  
Azure AD erbjuder även andra funktioner, till exempel att hantera integrerade appar, som du kan använda för att utöka och anpassa dina Microsoft 365-prenumerationer.
  
Du kan använda Azure AD Advisor för användning av en guidad installation och konfiguration i administrations centret för Microsoft 365 (du måste vara inloggad på Microsoft 365):

 - [Azure AD Connect Advisor](https://aka.ms/aadconnectpwsync)
 - [Distributions rådgivare för AD FS](https://aka.ms/adfsguidance)
 - [Konfigurations guide för Azure AD](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a>Azure AD-utgåvor och Microsoft 365 Identity Management

Om du har ett betalt abonnemang på Microsoft 365 har du också ett gratis Azure AD-abonnemang. Du kan använda Azure AD för att skapa och hantera användar-och grupp konton. Om du vill aktivera det här abonnemanget måste du slutföra en enstaka registrering. Därefter kan du få till gång till Azure AD från Microsoft 365 Admin Center. 

Anvisningar för hur du registrerar din gratis Azure AD-prenumeration finns i [använda din gratis Azure AD-prenumeration](../compliance/use-your-free-azure-ad-subscription-in-office-365.md). Gå inte direkt till azure.microsoft.com för att registrera dig, eller så får du ett utvärderings abonnemang till Microsoft Azure som är åtskilt från din gratis Azure AD-prenumeration med Microsoft 365. 
  
Med den kostnads fria prenumerationen kan du synkronisera med lokala kataloger, konfigurera enkel inloggning och synkronisera med många program som tjänst program, till exempel Salesforce, DropBox och många fler.
  
Om du vill använda förbättrade AD DS-funktioner, dubbelriktad synkronisering och andra hanterings funktioner kan du uppgradera ditt kostnads fria abonnemang till ett betalt Premium-abonnemang. Mer information finns i [Azure Active Directory-utgåvor](https://azure.microsoft.com/pricing/details/active-directory/).
  
Mer information om Microsoft 365 och Azure AD finns i [microsoft 365-Identity-modeller](about-microsoft-365-identity.md).
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a>Utöka funktionerna i din Microsoft 365-klient organisation

|**Funktion**|**Beskrivning**|
|:-----|:-----|
|Integrerade appar  <br/> |Du kan ge enskilda appar åtkomst till dina Microsoft 365-data, till exempel e-post, kalendrar, kontakter, användare, grupper, filer och mappar. Du kan också auktorisera dessa appar på global administratörs nivå och göra dem tillgängliga för hela företaget genom att registrera appar i Azure AD. Information om Formore finns i [integrerade program och Azure AD för Microsoft 365-administratörer](integrated-apps-and-azure-ads.md).  <br/> Se även [enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=698604).  <br/> |
|PowerApps  <br/> | Power Apps är prioriterade appar för mobila enheter som kan ansluta till dina befintliga data källor, till exempel SharePoint-listor och andra dataappar. Mer information finns i [skapa en PowerApp för en lista i SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) och [sidan PowerApps](https://powerapps.microsoft.com/) .  <br/> |
   
## <a name="see-also"></a>Se även

[Översikt över Microsoft 365 Enterprise](microsoft-365-overview.md)
