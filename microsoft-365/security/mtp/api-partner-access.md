---
title: 'Partner åtkomst via Microsoft 365 Defender API: er'
description: Lär dig hur du skapar en app för att få programmatisk åtkomst till Microsoft 365 Defender åt dina användare.
keywords: partner, Access, API, multi-klient, medgivande, åtkomsttoken, app
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719446"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Skapa en app med partner åtkomst till Microsoft 365 Defender API: er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

På den här sidan beskrivs hur du skapar ett Azure Active Directory-program som har programmatisk åtkomst till Microsoft 365 Defender för användare i flera klient organisationer. Flera klient program är användbara för att betjäna stora användar grupper.

Om du behöver programmatisk åtkomst till Microsoft 365 Defender för en enskild användare läser du [skapa en app för att få åtkomst till microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md). Om du behöver åtkomst utan någon användare uttryckligen (om du till exempel skriver en bakgrunds program eller en daemon) läser du [skapa en app för att få åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md). Om du inte är säker på vilken typ av åtkomst du behöver läser du [komma igång](api-access.md).

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er. Dessa API: er hjälper dig att automatisera arbets flöden och utnyttja Microsoft 365 Defender-funktionerna. Denna API-åtkomst kräver autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

I allmänhet måste du göra följande för att använda dessa API:

- Skapa ett Azure Active Directory (Azure AD)-program.
- Skaffa en åtkomsttoken med det här programmet.
- Använd token för att få åtkomst till Microsoft 365 Defender API.

Eftersom den här appen är en multi-klient organisation behöver du också [Administratörs medgivande](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) från varje klient organisation åt sina användare.

I den här artikeln förklarar vi hur du:

- Skapa ett Azure AD-program **med flera innehavare**
- Få ett godkänt medgivande från din användar administratör för din ansökan för att få åtkomst till Microsoft 365 Defender-resurserna som behövs.
- Skaffa en åtkomsttoken till Microsoft 365 Defender
- Validera token

Microsoft 365 Defender visar mycket av dess data och åtgärder via en uppsättning API: er. Dessa API: er hjälper dig att automatisera arbets flöden och förnyas baserat på Microsoft 365 Defender-funktioner. För API-åtkomst krävs autentisering med OAuth 2.0. Mer information finns i [verifierings kod flödet för OAuth-2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

I allmänhet måste du utföra följande steg för att använda API:

- Skapa ett Azure AD-program **med flera innehavare** .
- Få godkännande (godkänt) av din användar administratör för ditt program för att få åtkomst till Microsoft 365 Defender-resurser som behövs.
- Skaffa en åtkomsttoken med det här programmet.
- Använd token för att få åtkomst till Microsoft 365 Defender API.

Följ de här anvisningarna för att skapa ett Azure AD-program med flera innehavare, skaffa en åtkomsttoken till Microsoft 365 Defender och validera token.

## <a name="create-the-multi-tenant-app"></a>Skapa appen för flera innehavare

1. Logga in på [Azure](https://portal.azure.com) som en användare med rollen **Global administratör** .

2. Navigera till **Azure Active Directory**-  >  **programregistreringar**  >  **ny registrering**.

   ![Bild av Microsoft Azure och navigering till program registrering](../../media/atp-azure-new-app2.png)

3. I registrerings formuläret:

   - Välj ett namn för programmet.
   - Från **konto typer som stöds** väljer du **konton i valfri organisations katalog (vilken Azure AD-katalog)-multiinnehavare**.
   - Fyll i avsnittet **OMDIRIGERA URI** . Välj Skriv **webbplats** och ge omdirigerings-URI som **https://portal.azure.com** .

   När du har fyllt i formuläret väljer du **Registrera**.

   ![Bild av registret registrera ett ansöknings formulär](../..//media/atp-api-new-app-partner.png)

4. På din program sida väljer du **API-behörigheter**  >  **Add permission**  >  **API min organisation använder** >, Skriv **Microsoft Threat Protection** och välj **Microsoft Threat Protection**. Ditt program kan nu komma åt Microsoft 365 Defender.

   > [!TIP]
   > *Microsoft Threat Protection* är ett tidigare namn för Microsoft 365 Defender och kommer inte att synas i den ursprungliga listan. Du måste börja skriva dess namn i text rutan för att se det.

   ![Bild av API-behörighet](../../media/apis-in-my-org-tab.PNG)

5. Välj **program behörigheter**. Välj relevanta behörigheter för ditt scenario (till exempel **incident. Read. all**) och välj sedan **Add Permissions**.

   ![Bild av API-åtkomst och API-val](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Du måste välja relevanta behörigheter för scenariot. *Läs alla händelser* är bara ett exempel. Ta reda på vilken behörighet du behöver genom att titta i avsnittet **behörigheter** i det API som du vill ringa.
    >
    > Om du till exempel vill [köra avancerade frågor](api-advanced-hunting.md)väljer du "kör avancerade frågor". Om du vill [isolera en enhet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)väljer du "isolera datorns tillstånd".

6. Välj **ge administratörs medgivande**. Varje gång du lägger till en behörighet måste du välja **bevilja administratörs medgivande** för att det ska börja gälla.

    ![Bild av beviljande behörigheter](../../media/grant-consent.PNG)

7. Om du vill lägga till en hemlighet i programmet väljer du **certifikat & hemligheter**, lägger till en beskrivning till hemligheten och väljer sedan **Lägg till**.

    > [!TIP]
    > När du har valt **Lägg till** väljer **du kopiera det genererade hemliga värdet**. Du kommer inte att kunna hämta det hemliga värdet efter att du har lämnat.

    ![Bild av Create app-tangenten](../../media/webapp-create-key2.png)

8. Spela in ditt program-ID och klient-ID något säkert. De visas under **Översikt** på din program sida.

   ![Bild av ID för skapat program](../../media/app-and-tenant-ids.png)

9. Lägg till programmet i användarens innehavare.

   Eftersom ditt program interagerar med Microsoft 365 Defender åt användarna måste det godkännas för varje klient organisation som ska använda det.

   En **Global administratör** från användarens innehavare måste visa medgivande länken och godkänna ditt program.

   Godkännande länken är av formen:

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   Siffrorna `00000000-0000-0000-0000-000000000000` bör ersättas med ditt program-ID.

   När du har klickat på länken för godkännande loggar du in med den globala administratören för användarens klient organisation och godkänner programmet.

   ![Bild av godkännande](../../media/app-consent-partner.png)

   Du måste också be din användare om sitt klient-ID. Klient-ID är en av de identifierare som används för att hämta åtkomst-token.

- **Åstadkomma!** Du har registrerat ett program!
- Se exemplen nedan för hämtning av token och verifiering.

## <a name="get-an-access-token"></a>Skaffa en åtkomsttoken

Mer information om Azure AD-token finns i [Azure AD själv studie kurs](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Även om exemplen i det här avsnittet uppmanar dig att klistra in hemliga värden i test syfte bör du **aldrig hardcode hemligheter** i ett program som körs i produktion. En tredje part kan använda din hemlighet för att komma åt resurser. Du kan hålla dina programs hemligheter säkra genom att använda [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Ett praktiskt exempel på hur du kan skydda din app finns i [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

> [!TIP]
> I följande exempel använder du en användares klient-ID för att testa att skriptet fungerar.

### <a name="get-an-access-token-using-powershell"></a>Skaffa en åtkomsttoken med PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a>Skaffa en åtkomsttoken med C\#

> [!NOTE]
> Följande kod har testats med NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Skapa ett nytt konsol program.
1. Installera NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Lägg till följande rad:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Kopiera och klistra in följande kod i appen (Glöm inte att uppdatera de tre variablerna: `tenantId` , `clientId` , `appSecret` ):

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Skaffa en åtkomsttoken med python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a>Skaffa en åtkomsttoken med hjälp av sväng

> [!NOTE]
> Sväng är förinstallerat på Windows 10, version 1803 och senare. För andra versioner av Windows laddar du ned och installerar verktyget direkt från den [officiella platsen](https://curl.haxx.se/windows/).

1. Öppna en kommando tolk och ange CLIENT_ID till ditt Azure-program-ID.
1. Ange CLIENT_SECRET till din Azure Application Secret.
1. Ange TENANT_ID till Azure TENANT ID för den användare som vill använda din app för att komma åt Microsoft 365 Defender.
1. Kör följande kommando:

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Ett lyckat svar ser ut så här:

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validera token

1. Kopiera och klistra in din token i [JSON Web token validator-webbplatsen, JWT,](https://jwt.ms) för att avkoda den.
1. Kontrol lera att de *roller* som är med i det kodade token innehåller de önskade behörigheterna.

I följande bild kan du se ett avkodat token från en app, med ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` och ```AdvancedHunting.Read.All``` behörigheter:

![Bild av verifiering av token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Använda token för att komma åt Microsoft 365 Defender API

1. Välj det API du vill använda (incidenter eller avancerad jakt). Mer information finns i [Microsoft 365 Defender API: n](api-supported.md).
2. I den http-begäran som du ska skicka kan du ange tillstånds huvudet till `"Bearer" <token>` , *innehavaren* är ett godkännande och *token* som verifierad token.
3. Token upphör att gälla inom en timme. Du kan skicka fler än en begäran under tiden med samma token.

I följande exempel visas hur du skickar en begäran om att få en lista över incidenter **med C#**.

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Gå till API för Microsoft 365 Defender](api-access.md)
- [Skapa ett ' Hej världen '-program](api-hello-world.md)
- [Skapa en app för åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md)
- [Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md)
- [Läs mer om API-begränsningar och licensiering](api-terms.md)
- [Förstå felkoder](api-error-codes.md)
- [Hantera hemligheter i dina serverprogram med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2,0-auktorisering för användare inloggning och API-åtkomst](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
