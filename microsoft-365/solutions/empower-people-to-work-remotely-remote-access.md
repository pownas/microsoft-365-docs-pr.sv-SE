---
title: Steg 2. Tillhandahålla fjärråtkomst till lokala appar och tjänster
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Kontrollera att dina distansarbetare kan komma åt lokala resurser samtidigt som du optimerar åtkomst till Microsoft 365-molntjänster.
ms.openlocfilehash: 1fbb1cb6ad9817f0e167ae95f9fc113ecdee4221
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681426"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a>Steg 2. Tillhandahålla fjärråtkomst till lokala appar och tjänster

Användarna använda VPN-anslutningarna för fjärråtkomst för att komma åt lokala appar och servrar om din organisation använder en VPN-lösning för fjärråtkomst, oftast med VPN-servrar på kanten av ditt nätverk och VPN-klienter som är installerade på användarnas enheter. Men du kan behöva optimera trafik för molnbaserade Microsoft 365-tjänster.

Om dina användare inte använder en VPN-lösning kan du med hjälp av Azure Active Directory (Azure AD) Application Proxy och Azure Point-to-Site (P2S) VPN för att ge åtkomst, beroende på om alla dina appar är webbaserade.

Här beskrivs de primära konfigurationerna för fjärråtkomst:

- Du använder redan en VPN-lösning för fjärråtkomst.
- Du använder inte en VPN-lösning för fjärråtkomst och du vill att dina distansarbetare ska använda sina egna datorer.
- Du använder inte en VPN-lösning för fjärråtkomst, men du har en hybrididentitet och du behöver endast fjärråtkomst till lokala webbaserade appar.
- Du använder inte en VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, varav några inte är webbaserade.

Se det här flödesschemat för konfigurationsalternativen för fjärråtkomst som beskrivs i den här artikeln.

![Flödesdiagram över konfigurationen för fjärråtkomst](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

Med fjärråtkomstanslutningar kan du även använda [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) för att ansluta dina användare till en lokal dator. Distansarbetare kan till exempel använda Remote Desktop för att ansluta till sina datorer på kontoret från sina Windows-, iOS- eller Android-enheter. När de har fjärranslutit kan de använda den som om de satt framför den.

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a>Optimera prestanda för VPN-klienter för fjärråtkomst till Microsoft 365-molntjänster

Om din distansarbetare använder en traditionell VPN-klient för att få fjärråtkomst till organisationens nätverk ska du kontrollera att VPN-klienten har stöd för delad tunnel.

Utan delad tunnel skickas all din fjärrtrafik över VPN-anslutningen, där den måste vidarebefordras till organisationens gränsenheter, bli processad och sedan skickas via Internet.

![Nätverkstrafik från VPN-klienter utan tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

Microsoft 365-trafik måste ta en indirekt väg via din organisation, som kan vara vidarebefordrad till en Microsoft Network startpunkt långt bort från VPN-klientens fysiska plats. Denna indirekta väg lägger till en fördröjning för nätverkstrafiken och minskar prestandan. 

Med delad tunnel kan du konfigurera VPN-klienten så att den exkluderar vissa typer av trafik som inte skickas via VPN-anslutningen till organisationens nätverk.

Om du vill optimera åtkomst till Microsoft 365 molnresurser konfigurerar du VPN-klienter för uppdelad tunnel för att undanta trafik till **optimera** kategori Microsoft 365-slutpunkter över VPN-anslutningen. Mer information finns i [Office 365-slutpunktskategorier](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories). Se listan över Optimera kategorislutpunkter [här](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).

Här är det resulterande trafikflödet, där den mesta trafiken till Microsoft 365-molnappar kringgår VPN-anslutningen.

![Nätverkstrafik från VPN-klienter med tunnel](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

Detta gör att VPN-klienten kan skicka och ta emot viktig trafik i Microsoft 365 molntjänster direkt via Internet och till närmaste startpunkt i Microsoft-nätverket.

Detaljerad information finn i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel??).

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a>Distribuera fjärråtkomst när alla dina appar är webbprogram och du har en hybrididentitet

Om dina distansarbetare inte använder en traditionell VPN-klient och dina lokala användarkonton och -grupper är synkroniserade med Azure AD, kan du använda Azure AD Application Proxy för att tillhandahålla säker fjärråtkomst för webbaserade program som finns på lokala servrar. Webbaserade program är SharePoint Server-webbplatser, Outlook Web Access-servrar eller andra webbaserade affärsprogram. 

Här är komponenterna i Azure Active Directory Application Proxy.

![Komponenter i Azure Active Directory Application Proxy](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

Mer information finns i den här [översikt över Azure Active Directory Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

>[!Note]
>Azure Active Directory Application Proxy ingår inte i en Microsoft 365-prenumeration. Du måste betala för användning med en separat Azure-prenumeration.
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a>Distribuera fjärråtkomst när alla appar inte är webbprogram

Om dina distansarbetare inte använder en traditionell VPN-klient och några av dina appar inte är webbaserade kan du använda en Azure Point-to-Site (P2S) VPN.

En P2S VPN-anslutning skapar en säker anslutning från en distansarbetares enhet till organisationens nätverk via ett virtuellt Azure-nätverk. 

![Komponenter i Azure P2S VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

Mer information finns i denna [översikt över P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).

>[!Note]
>Azure P2S VPN ingår inte i en Microsoft 365-prenumeration. Du måste betala för användning med en separat Azure-prenumeration.
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a>Distribuera Windows Virtual Desktop för att tillhandahålla fjärråtkomst för distansarbetare som använder personliga enheter 

Om du vill stödja distansarbetare som endast kan använda sina personliga och ohanterade enheter kan du använda Windows Virtual Desktop i Azure och skapa och allokera virtuella skrivbord för användarna att använda hemifrån. Virtualiserade datorer kan agera precis som datorer som är anslutna till din organisations nätverk.

![Komponenter i Azure Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

Mer information finns i [den här översikten över Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview). 

>[!Note]
>Windows Virtual Desktop ingår inte i en Microsoft 365-prenumeration. Du måste betala för användning med en separat Azure-prenumeration.
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a>Skydda dina anslutningar för fjärrskrivbordstjänster med gateway för fjärrskrivbordstjänster

Om du använder fjärrskrivbordstjänster (RDS) för att låta dina medarbetare ansluta till Windows-datorer i det lokala nätverket bör du använda en Microsoft Fjärrskrivbordtjänster-gateway i Edge-nätverket. Gatewayen använder SSL (Secure Sockets Layer) för att kryptera kommunikation och förhindra att den lokala datorn som är värd för fjärrskrivbordstjänster exponeras direkt mot Internet.

![Anslutningar för fjärrskrivbordstjänster med gateway för fjärrskrivbordstjänster](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

Mer information finns i [den här artikeln](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/).

## <a name="admin-technical-resources-for-remote-access"></a>Tekniska administrationsresurser för fjärråtkomst

- [Så här kan du snabbt optimera Office 365-trafik för fjärransluten personal och minska belastningen på infrastrukturen](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [Optimera Office 365-anslutningen för fjärranvändare med uppdelad VPN-tunnel](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?)

## <a name="results-of-step-2"></a>Resultat av steg 2

Efter distribution av en lösning för fjärråtkomst för dina distansarbetare:

| Konfigurationen för fjärråtkomst | Resultat |
|:-------|:-----|
| En VPN-lösning för fjärråtkomst finns på plats | Du har konfigurerat VPN-klienten för fjärråtkomst för uppdelad tunnel och för optimeringskategori för Microsoft 365-slutpunkter. |
| Ingen VPN-lösning för fjärråtkomst och du behöver endast fjärråtkomst till lokala webbaserade appar | Du har konfigurerat Azure Application Proxy. |
| Ingen VPN-lösning för fjärråtkomst och du behöver åtkomst till lokala appar, vissa som inte är webbaserade | Du har konfigurerat Azure P2S VPN. |
| Distansarbetare använder sina personliga enheter från hemmet | Du har konfigurerat Windows Virtual Desktop. |
| Distansmedarbetare använder RDS-anslutningar i lokala system | Du har distribuerat en gateway för fjärrskrivbordstjänster i Edge-nätverket. |
|||

## <a name="next-step"></a>Nästa steg

[![Steg 3: Distribuera säkerhets- och efterlevnadstjänster med Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)

Fortsätt med [Steg 3](empower-people-to-work-remotely-security-compliance.md) om du vill distribuera Microsoft 365 säkerhets och efterlevnadstjänster för att skydda appar, data och enheter.

