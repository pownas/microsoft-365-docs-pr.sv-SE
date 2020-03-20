---
title: Hitta din domänregistrator för Office 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Lär dig hur du hittar din domänregistrator och DNS-värdtjänst med InterNIC-sökning.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812342"
---
# <a name="find-your-domain-registrar-for-office-365"></a>Hitta din domänregistrator för Office 365

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter. 
  
## <a name="domain-registrar"></a>Domänregistrator
  
### <a name="find-your-domain-name-registrar"></a>Hitta din domännamnsregistrator

>[!NOTE]
> Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.
  
1. På [söksidan InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän. Till exempel *contoso.com.* 
    
2. Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).
    
3. På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du den organisation som tillhandahåller registreringstjänsten för din domän. 
    
## <a name="dns-hosting-provider"></a>DNS-värdtjänst
  
### <a name="find-your-dns-hosting-provider"></a>Hitta din DNS-värdtjänst

>[!NOTE]
> Bara domäner som slutar med *.COM*, *.NET* och *.EDU* fungerar med det här verktyget.
  
1. På [söksidan InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), i rutan **Whois Search** (Whois-sökning), anger du din domän. Till exempel contoso.com. 
    
2. Välj alternativet **Domain** (Domän) och välj sedan **Submit** (Skicka).
    
3. På sidan **Whois Search Results** (Whois-sökresultat) söker du efter den första **Name Server** (Namnserver)-posten. 
    
4. Kopiera den namnserverinformation som visas efter kolonet (:) och klistra in den i rutan **Search** (Sök) längst upp på sidan. Välj **Nameserver** (Namnserver) och välj sedan **Submit** (Skicka).
    
5. På sidan **Whois Search Results** (Whois-sökresultat) letar du upp rutan **Registrar** (Registrator). Här hittar du namnet på den DNS-tjänstleverantör som äger din domäns namnserver. 
    
---
