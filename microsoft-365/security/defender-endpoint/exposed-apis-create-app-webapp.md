---
title: ユーザーなしで Microsoft Defender for Endpoint にアクセスするアプリを作成する
ms.reviewer: ''
description: ユーザーなしで Microsoft Defender for Endpoint へのプログラムによるアクセスを取得する Web アプリを設計する方法について説明します。
keywords: apis, graph api, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度なハンティング, クエリ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8d68a7fc815227f267f79245c7861da8f8afde4d
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58569515"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a>ユーザーなしで Microsoft Defender for Endpoint にアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このページでは、ユーザーなしで Defender for Endpoint へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。 ユーザーに代わって Defender for Endpoint へのプログラムによるアクセスが必要な場合は、「ユーザー コンテキストでアクセスを取得する」 [を参照してください](exposed-apis-create-app-nativeapp.md)。 必要なアクセス権が分からない場合は、「開始する」 [を参照してください](apis-intro.md)。

Microsoft Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新するのに役立ちます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般に、API を使用するには、次の手順を実行する必要があります。
- アプリケーション (azure Azure Active Directory) AD作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して Defender for Endpoint API にアクセスします。

この記事では、Azure AD アプリケーションを作成し、エンドポイント用 Microsoft Defender へのアクセス トークンを取得し、トークンを検証する方法について説明します。

## <a name="create-an-app"></a>アプリを作成する

1. グローバル管理者の [役割を](https://portal.azure.com) 持つユーザーを使用して **Azure にログオン** します。

2. [アプリの **登録Azure Active Directory**  >  **新しい登録]**  >  **に移動します**。 

   ![アプリケーションの登録Microsoft Azureナビゲーションのイメージ。](images/atp-azure-new-app2.png)

3. 登録フォームで、アプリケーションの名前を選択し、[登録] を **選択します**。

4. アプリが Defender for Endpoint にアクセスし、[すべてのアラートの読み取り **]** アクセス許可を割り当てるには、アプリケーション ページで **、[API** アクセス許可の追加] アクセス許可 API を選択して、組織で > を使用し  >    >  **、「WindowsDefenderATP」と入力し、[WindowsDefenderATP]** を選択します。

   > [!NOTE]
   > *WindowsDefenderATP* は元のリストには表示されません。 テキスト ボックスに名前を書き始め、表示を確認します。

   ![アクセス許可を追加します。](images/add-permission.png)

   - [**アプリケーションのアクセス許可**  >  **Alert.Read.All] を選択** し、[アクセス許可の **追加] を選択します**。

   ![アプリのアクセス許可。](images/application-permissions.png)

     関連するアクセス許可を選択する必要があります。 'すべてのアラートの読み取り' は、一例にすすみです。 例:

     - 高度 [なクエリを実行するには、[](run-advanced-query-api.md)高度なクエリの実行] アクセス許可を選択します。
     - デバイス [を分離するには、[](isolate-machine.md)コンピューターの分離] アクセス許可を選択します。
     - 必要なアクセス許可を確認するには、呼び出す API の [アクセス許可] セクションを参照してください。

5. [同意 **の付与] を選択します**。

     > [!NOTE]
     > アクセス許可を追加する度に、[新しいアクセス許可 **を** 有効にするための同意の付与] を選択する必要があります。

    ![アクセス許可を付与する。](images/grant-consent.png)

6. アプリケーションにシークレットを追加するには、[証明書] &シークレットに説明を追加し、[追加] を選択 **します**。

    > [!NOTE]
    > [追加] を **選択した後**、生成 **されたシークレット値をコピーします**。 この値は、退出後に取得できない場合があります。

    ![アプリ キーの作成のイメージ。](images/webapp-create-key2.png)

7. アプリケーション ID とテナント ID を書き出します。 アプリケーション ページで、[概要] に移動 **し** 、次をコピーします。

   ![作成されたアプリ ID のイメージ。](images/app-and-tenant-ids.png)

8. **エンドポイント パートナー向け Microsoft Defender の場合のみ**。 アプリをマルチテナントに設定します (同意後、すべてのテナントで利用できます)。 これは、 **サード パーティ** 製アプリ (たとえば、複数の顧客のテナントで実行することを意図したアプリを作成する場合) に必要です。 これは、 **テナント** でのみ実行するサービスを作成する場合は必須ではありません (たとえば、独自のデータのみを操作する独自の用途用のアプリケーションを作成する場合など)。 アプリをマルチテナントに設定するには、次の方法を実行します。

    - [認証] **に移動** し、リダイレクト `https://portal.azure.com` URI **として追加します**。

    - ページの下部にある [サポートされているアカウントの種類] で、マルチテナント アプリの組織ディレクトリ アプリケーションの同意にある [アカウント] を選択します。

    アプリケーションを使用する各テナントでアプリケーションを承認する必要があります。 これは、アプリケーションが顧客に代わって Defender for Endpoint をやり取りする理由です。

    ユーザー (またはサードパーティ アプリを作成している場合は顧客) は、同意リンクを選択してアプリを承認する必要があります。 同意は、Active Directory で管理者権限を持つユーザーに対して行う必要があります。

    同意リンクは次のように形成されます。 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    00000000-00000-00000-00000-000000000000 がアプリケーション ID に置き換えられる場合。


**完成です！** アプリケーションの登録に成功しました! トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure AD トークンの詳細については [、「Azure AD」を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

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
```

### <a name="use-c"></a>次のC#使用します。

次のコードは、Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 NuGetでテストされました。

1. 新しいコンソール アプリケーションを作成します。
1. [Microsoft.IdentityModel.clients.ActiveDirectory をインストールNuGet Microsoft.IdentityModel.Clients.ActiveDirectory をインストールします](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。
1. 次の項目を追加します。

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 次のコードをアプリにコピーして貼り付けます (3 つの変数を更新することを忘れないでください ```tenantId, appId, appSecret``` )。

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Python を使用する

「Python [を使用してトークンを取得する」を参照してください](run-advanced-query-sample-python.md#get-token)。

### <a name="use-curl"></a>Curl を使用する

> [!NOTE]
> 次の手順では、コンピューターにWindowsの Curl が既にインストールされていることを前提とします。

1. コマンド プロンプトを開き、Azure CLIENT_ID ID に設定します。
1. Azure CLIENT_SECRETシークレットに設定します。
1. アプリTENANT_ID Defender for Endpoint にアクセスする顧客の Azure テナント ID に設定します。
1. 次のコマンドを実行します。

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

次の形式で回答が表示されます。

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得していることを確認します。

1. 前の手順で取得したトークンを [JWT](https://jwt.ms) にコピーして貼り付け、デコードします。
1. 目的のアクセス許可を持つ 'roles' クレームを取得する方法を検証する
1. 次の図では、エンドポイントのすべての Microsoft Defender の役割に対するアクセス許可を持つ、アプリから取得されたデコードされたトークンを確認できます。

![トークン検証のイメージ。](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>トークンを使用して Microsoft Defender for Endpoint API にアクセスする

1. 使用する API を選択します。 詳細については [、「Supported Defender for Endpoint API」を参照してください](exposed-apis-list.md)。
1. 送信する http 要求の承認ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)。
1. トークンの有効期限は 1 時間です。 同じトークンで複数の要求を送信できます。

次に、要求を送信してアラートの一覧を取得する例を次に **示** C#。 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a>関連項目
- [サポート対象 Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [ユーザーに代わって Microsoft Defender for Endpoint にアクセスする](exposed-apis-create-app-nativeapp.md)
