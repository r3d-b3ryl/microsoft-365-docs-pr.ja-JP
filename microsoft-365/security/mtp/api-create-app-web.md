---
title: ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する
description: ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する方法について説明します。
keywords: アプリ、アクセス、api、作成
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
ms.openlocfilehash: be637bab97083cb857e3983dd9b82290590c1302
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650418"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a>ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

このページでは、ユーザーなしで Microsoft の脅威保護へのプログラムによるアクセスを可能にするアプリケーションを作成する方法について説明します。 ユーザーに代わって Microsoft の脅威保護にプログラムによってアクセスする必要がある場合は、「 [Get access with user context](api-create-app-user-context.md)」を参照してください。 必要なアクセス権がわからない場合は、「 [はじめ](api-access.md)に」を参照してください。

Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。 これらの Api は、Microsoft の脅威保護機能に基づいて、ワークフローとイノベーションを自動化するのに役立ちます。 API へのアクセスには、OAuth 2.0 認証が必要です。 詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。

一般に、Api を使用するには、次の手順を実行する必要があります。
- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセストークンを取得します。
- トークンを使用して、Microsoft の脅威保護 API にアクセスします。

この記事では、Azure AD アプリケーションを作成し、Microsoft の脅威保護へのアクセストークンを取得し、トークンを検証する方法について説明します。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者**の役割を持つユーザーを使用して[Azure](https://portal.azure.com)にログオンします。

2. **Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. 登録フォームで、アプリケーションの名前を選択し、[ **登録**] を選択します。

4. アプリが Microsoft の脅威保護にアクセスできるようにして、it アクセス許可を割り当てるには、アプリケーションページで、[ **API アクセス**許可 api を追加する] [  >  **Add permission**  >  **組織は**> を使用します] を選択し、「 **microsoft threat protection**」と入力して、[ **microsoft threat protection**] を選択します。

   > [!NOTE]
   > Microsoft の脅威保護は、元のリストには表示されません。 テキストボックスに名前を記述して、表示されることを確認する必要があります。

   ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)

   - [ **アプリケーションの権限** ] を選択します。たとえば、 **インシデント**に関連するアクセス許可を選択し、[ **アクセス許可の追加**] を選択します。 >。

   ![API アクセスと API 選択の画像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >シナリオに関連するアクセス許可を選択する必要があります。 **「すべてのインシデントの読み取り」** は例にすぎません。 必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。

5. [ **同意を許可**する] を選択します。

     > [!NOTE]
     > アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意の付与** ] を選択する必要があります。

    ![許可権限の画像](../../media/grant-consent.PNG)

6. アプリケーションにシークレットを追加するには、[ **証明書 & シークレット**] を選択し、シークレットに説明を追加して、[ **追加**] を選択します。

    > [!NOTE]
    > [ **追加**] を選択した後、[ **生成されたシークレットの値をコピー**する] を選択します。 その後、この値を取得することはできません。

    ![アプリキーを作成する画像](../../media/webapp-create-key2.png)

7. アプリケーション ID とテナント ID を書き留めます。 アプリケーションページで、[ **概要** ] に移動し、次のようにコピーします。

   ![作成されたアプリ id の画像](../../media/app-and-tenant-ids.png)

8. **Microsoft の脅威保護パートナーの場合のみ**。 [こちらの手順に従って](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)ください。 アプリをテナント (同意した後、すべてのテナントで利用可能) に設定します。 これは、サードパーティ製のアプリ (たとえば、複数の顧客のテナントで実行するためのアプリを作成する場合など) に **必要** です。 テナントのみで実行するサービスを作成する場合は、この操作は **必要ありません** (たとえば、独自のデータと対話する独自の使用法用のアプリケーションを作成する場合)。 アプリをテナントに設定するには、次のようにします。

    - [ **認証**] に移動し https://portal.azure.com て、 **リダイレクト URI**としてを追加します。

    - ページの下部にある [ **サポートされるアカウントの種類**] で、マルチテナントアプリの **組織ディレクトリ** アプリケーションの同意にあるアカウントを選択します。

    アプリケーションは、その使用を予定している各テナントで承認される必要があります。 これは、アプリケーションがお客様の代わりに Microsoft の脅威保護に作用するからです。

    (または、サードパーティ製アプリを作成しているお客様) は、同意リンクを選択してアプリを承認する必要があります。 Active Directory の管理者権限を持つユーザーとの同意を行う必要があります。

    同意リンクの形式は次のとおりです。 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    00000000-0000-0000-0000-000000000000 は、アプリケーション ID に置き換えられます。


**完成です！** アプリケーションが正常に登録されました。 トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure AD トークンの詳細については、「 [AZURE ad チュートリアル](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)」を参照してください。

### <a name="use-powershell"></a>PowerShell の使用

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>C# を使用します。

次のコードは、Nuget 3.19.8 を使用してテストされました。

1. 新しいコンソールアプリケーションを作成します。
1. Nuget [クライアント](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)をインストールします。
1. 以下を追加します。

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 次のコードをコピーして、アプリに貼り付けます (3 つの変数を更新してください ```tenantId, appId, appSecret``` )。

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Python の使用 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Curl の使用

> [!NOTE]
> 次の手順では、Windows 用の Curl がコンピューターに既にインストールされていることを前提としています。

1. コマンドプロンプトを開き、CLIENT_ID を Azure アプリケーション ID に設定します。
1. Azure アプリケーションシークレットに CLIENT_SECRET を設定します。
1. アプリを使用して Microsoft の脅威保護にアクセスするお客様の Azure テナント ID に TENANT_ID を設定します。
1. 次のコマンドを実行します。

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

次の形式で答えが得られます。

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得していることを確認します。

1. 前の手順で取得したトークンを、 [JWT](https://jwt.ms) にコピーして貼り付け、デコードします。
1. 必要なアクセス許可を持つ ' roles ' 要求を取得していることを検証する
1. 次の画像では、およびアクセス許可を持つアプリから取得した、デコードされたトークンを確認でき ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` ます。

![トークン検証のイメージ](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>トークンを使用して Microsoft の脅威保護 API にアクセスする

1. 使用する API を選択します。 詳細については、「 [サポートされる Microsoft Threat Protection api](api-supported.md)」を参照してください。

2. "ベアラー {token}" に送信する http 要求の承認ヘッダーを設定します (ベアラーは認証スキームです)。

3. トークンの有効期限は1時間です。 同じトークンを使用して、複数の要求を送信できます。

次に、 **C# を使用して**、インシデントのリストを取得するための要求を送信する例を示します。 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>関連項目
- [Microsoft の脅威保護 Api にアクセスする](api-access.md)
- [アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする](api-create-app-web.md)
- [ユーザーコンテキストを使用して Microsoft の脅威保護にアクセスする](api-create-app-user-context.md)
