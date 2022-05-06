---
title: ユーザーなしでMicrosoft Defender for Endpointにアクセスするアプリを作成する
ms.reviewer: ''
description: ユーザーなしでMicrosoft Defender for Endpointにプログラムでアクセスできるように Web アプリを設計する方法について説明します。
keywords: apis, graph api, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度な捜索, クエリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6b9ad54a881ae5e14767e55da8dfc23b2fb237eb
ms.sourcegitcommit: 292de1a7e5ecc2e9e6187126aebba6d3b9416dff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65243120"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>ユーザーなしでMicrosoft Defender for Endpointにアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このページでは、ユーザーなしで Defender for Endpoint へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。 ユーザーに代わって Defender for Endpoint にプログラムでアクセスする必要がある場合は、「ユーザー [コンテキストを使用したアクセスの取得](exposed-apis-create-app-nativeapp.md)」を参照してください。 必要なアクセスが不明な場合は、[概要](apis-intro.md)を参照してください。

Microsoft Defender for Endpointは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、Defender for Endpoint 機能に基づいて作業フローを自動化し、イノベーションを行うのに役立ちます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については、「[OAuth 2.0 Authorization Code Flow」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、API を使用するには、次の手順を実行する必要があります。
- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して Defender for Endpoint API にアクセスします。

この記事では、Azure AD アプリケーションを作成し、Microsoft Defender for Endpointにアクセス トークンを取得し、トークンを検証する方法について説明します。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者** ロールを持つユーザーを使用して [Azure](https://portal.azure.com) にログオンします。

2. **Azure Active Directory アプリの登録** \>  \> **新しい登録** に移動します。 

    :::image type="content" source="images/atp-azure-new-app2.png" alt-text="アプリケーションの登録ウィンドウ" lightbox="images/atp-azure-new-app2.png":::

3. 登録フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。

4. アプリが Defender for Endpoint にアクセスし、**"すべてのアラートの読み取り"** アクセス許可を割り当てられるようにするには、アプリケーション ページで、**組織** が>使用する **API の [API アクセス許可** \> **の追加**] \> を選択し、「**WindowsDefenderATP**」と入力し、**WindowsDefenderATP** を選択します。

   > [!NOTE]
   > *WindowsDefenderATP* は元の一覧に表示されません。 テキスト ボックスに名前を書き始めて、表示されます。

   :::image type="content" source="images/add-permission.png" alt-text="[API アクセス許可] ウィンドウ" lightbox="images/add-permission.png":::

   [ **アプリケーションのアクセス許可** \> **アラート.Read.All**] を選択し、[ **アクセス許可の追加]** を選択します。

   :::image type="content" source="images/application-permissions.png" alt-text="アプリケーションのアクセス許可情報ウィンドウ" lightbox="images/application-permissions.png":::

     関連するアクセス許可を選択する必要があります。 "すべてのアラートの読み取り" は例にすぎません。 次に、例を示します。

     - [高度なクエリを実行](run-advanced-query-api.md)するには、[高度なクエリの実行] アクセス許可を選択します。
     - [デバイスを分離](isolate-machine.md)するには、[コンピューターの分離] アクセス許可を選択します。
     - 必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを参照してください。

5. [ **同意の付与]** を選択します。

     > [!NOTE]
     > アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意の付与** ] を選択する必要があります。

    :::image type="content" source="images/grant-consent.png" alt-text="[アクセス許可の付与] ページ" lightbox="images/grant-consent.png":::

6. アプリケーションにシークレットを追加するには、[ **証明書&シークレット**] を選択し、シークレットに説明を追加して、[ **追加**] を選択します。

    > [!NOTE]
    > **[追加]** を選択した後、**生成されたシークレット値のコピーを** 選択します。 この値は、退出後は取得できません。

      :::image type="content" source="images/webapp-create-key2.png" alt-text="アプリケーションの作成オプション" lightbox="images/webapp-create-key2.png":::

7. アプリケーション ID とテナント ID を書き留めます。 アプリケーション ページで、[ **概要]** に移動し、次の内容をコピーします。

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="作成されたアプリとテナント ID" lightbox="images/app-and-tenant-ids.png":::

8. **Microsoft Defender for Endpoint パートナーの場合のみ**。 アプリをマルチテナントに設定します (同意後、すべてのテナントで使用できます)。 これは、サード パーティのアプリ (たとえば、複数の顧客のテナントで実行することを目的としたアプリを作成する場合) に **必要** です。 これは、テナントでのみ実行するサービスを作成する場合 (たとえば、独自のデータと対話するだけの独自の用途のアプリケーションを作成する場合) には **必要ありません** 。 アプリをマルチテナントに設定するには:

    - **[認証]** に移動し、**リダイレクト URI** として追加`https://portal.azure.com`します。

    - ページの下部にある [ **サポートされているアカウントの種類**] で、マルチテナント アプリ **の組織ディレクトリ アプリケーションの同意で [アカウント** ] を選択します。

    アプリケーションを使用する各テナントでアプリケーションを承認する必要があります。 これは、アプリケーションが顧客に代わって Defender for Endpoint と対話するためです。

    お客様 (またはサード パーティ製アプリを作成している場合は顧客) は、同意リンクを選択し、アプリを承認する必要があります。 同意は、Active Directory で管理者特権を持つユーザーに対して行う必要があります。

    同意リンクは次のように形成されます。 

    ```https
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    ここで、00000000-0000-0000-0000-00000000000 はアプリケーション ID に置き換えられます。


**完成です！** アプリケーションが正常に登録されました。 トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure AD トークンの詳細については、[Azure ADチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

### <a name="use-powershell"></a>PowerShell を使う

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
$token
```

### <a name="use-c"></a>C# を使用する:

次のコードは、NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 でテストされました。

1. 新しいコンソール アプリケーションを作成します。
1. [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGetインストールします。
1. 次を追加します。

    ```csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. アプリに次のコードをコピーして貼り付けます (3 つの変数 ```tenantId, appId, appSecret```を更新することを忘れないでください)。

    ```csharp
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    console.write(token)
    ```


### <a name="use-python"></a>Python を使用する

[「Python を使用してトークンを取得する](run-advanced-query-sample-python.md#get-token)」を参照してください。

### <a name="use-curl"></a>Curl を使用する

> [!NOTE]
> 次の手順では、curl for Windowsがコンピューターに既にインストールされていることを前提としています。

1. コマンド プロンプトを開き、CLIENT_IDを Azure アプリケーション ID に設定します。
1. CLIENT_SECRETを Azure アプリケーション シークレットに設定します。
1. アプリを使用して Defender for Endpoint にアクセスする顧客の Azure テナント ID にTENANT_IDを設定します。
1. 次のコマンドを実行します。

    ```console
    curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
    ```
    
    次の形式で回答が得られます。
    
    ```console
    {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
    ```
    
## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得したことを確認します。

1. 前の手順で取得したトークンをコピーし、 [JWT](https://jwt.ms) に貼り付けてデコードします。

1. 必要なアクセス許可を持つ "ロール" 要求を取得することを検証します。

   次の図では、Microsoft Defender for Endpointのすべてのロールに対するアクセス許可を持つ、アプリから取得されたデコードされたトークンを確認できます。

   :::image type="content" source="images/webapp-decoded-token.png" alt-text="トークンの詳細部分" lightbox="images/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>トークンを使用してMicrosoft Defender for Endpoint API にアクセスする

1. 使用する API を選択します。 詳細については、「 [サポートされている Defender for Endpoint API」を参照](exposed-apis-list.md)してください。
1. 送信する http 要求の承認ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)。
1. トークンの有効期限は 1 時間です。 同じトークンを使用して複数の要求を送信できます。

**C# を使用して** アラートの一覧を取得する要求を送信する例を次に示します。

```csharp
var httpClient = new HttpClient();

var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

// Do something useful with the response
```

## <a name="see-also"></a>関連項目
- [サポート対象 Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [ユーザーに代わってMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-nativeapp.md)
