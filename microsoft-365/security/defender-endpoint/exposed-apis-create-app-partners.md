---
title: ユーザーなしでMicrosoft Defender for Endpointにアクセスするアプリケーションを作成する
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
ms.openlocfilehash: 5f17f29f083df6e567218363027e7677c87ee154
ms.sourcegitcommit: 265a4fb38258e9428a1ecdd162dbf9afe93eb11b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2022
ms.locfileid: "65268874"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API を介したパートナー アクセス

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このページでは、Azure Active Directory (Azure AD) アプリケーションを作成して、顧客に代わってMicrosoft Defender for Endpointにプログラムでアクセスする方法について説明します。

Microsoft Defender for Endpointは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、作業フローを自動化し、Microsoft Defender for Endpoint機能に基づいてイノベーションを行うのに役立ちます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については、「[OAuth 2.0 Authorization Code Flow」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、API を使用するには、次の手順を実行する必要があります。

- **マルチテナント** Azure AD アプリケーションを作成します。
- アプリケーションが必要とする Defender for Endpoint リソースにアクセスするために、顧客管理者から承認(同意)を取得します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して、Microsoft Defender for Endpoint API にアクセスします。

次の手順では、Azure AD アプリケーションを作成し、アクセス トークンを取得してMicrosoft Defender for Endpointし、トークンを検証する方法について説明します。

## <a name="create-the-multi-tenant-app"></a>マルチテナント アプリを作成する

1. **グローバル管理者** ロールを持つユーザーを使用して [Azure テナント](https://portal.azure.com)にサインインします。

2. **Azure Active Directory アプリの登録** \>  \> **新しい登録** に移動します。

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="アプリケーション登録ウィンドウへのナビゲーション" lightbox="images/atp-azure-new-app2.png":::

3. 登録フォームで、次の手順を実行します。

   - アプリケーションの名前を選択します。

   - サポートされているアカウントの種類 - 任意の組織ディレクトリ内のアカウント。

   - リダイレクト URI - 種類: Web、URI: https://portal.azure.com

     :::image type="content" source="images/atp-api-new-app-partner.png" alt-text="Microsoft Azure パートナー アプリケーションの登録ページ" lightbox="images/atp-api-new-app-partner.png":::

4. アプリケーションがMicrosoft Defender for Endpointにアクセスできるようにし、統合を完了するために必要な最小限のアクセス許可セットを使用してアプリケーションに割り当てます。

   - アプリケーション ページで、組織が **WindowsDefenderATP** の種類>使用する **API アクセス許可**\>の **追加アクセス許可** \> **API** を選択し、**WindowsDefenderATP** で選択します。

   - **注**: *WindowsDefenderATP* は元の一覧には表示されません。 テキスト ボックスに名前を書き始めて、表示されます。

     :::image type="content" source="images/add-permission.png" alt-text="[アクセス許可の追加] オプション" lightbox="images/add-permission.png":::

### <a name="request-api-permissions"></a>API のアクセス許可を要求する

必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを確認します。 例:

- [高度なクエリを実行](run-advanced-query-api.md)するには、[詳細クエリの実行] アクセス許可を選択します
- [デバイスを分離](isolate-machine.md)するには、[マシンの分離] アクセス許可を選択します

次の例では、 **"すべてのアラートの読み取り"** アクセス許可を使用します。

1. **[アプリケーションのアクセス許可** \> **のアラート].Read.All** > [**アクセス許可の追加]** を選択します

   :::image type="content" source="images/application-permissions.png" alt-text="アクセス許可の追加を許可するオプション" lightbox="images/application-permissions.png":::

2. **[同意の付与]** を選択する

   - **注**: アクセス許可を追加するたびに、新しいアクセス許可を有効にするには **、[同意の付与** ] を選択する必要があります。

   :::image type="content" source="images/grant-consent.png" alt-text="同意の付与を許可するオプション" lightbox="images/grant-consent.png":::

3. アプリケーションにシークレットを追加します。

   - [ **証明書&シークレット**] を選択し、シークレットに説明を追加して、[ **追加**] を選択します。

    **重要**: [追加] をクリックした後、 **生成されたシークレット値をコピー** します。 退出後は取得できません。

     :::image type="content" source="images/webapp-create-key2.png" alt-text="アプリ キーの作成" lightbox="images/webapp-create-key2.png":::

4. アプリケーション ID を書き留めます。

   - アプリケーション ページで、[ **概要]** に移動し、次の情報をコピーします。

     :::image type="content" source="images/app-id.png" alt-text="アプリケーションの作成 ID" lightbox="images/app-id.png":::

5. アプリケーションを顧客のテナントに追加します。

   アプリケーションを使用する各顧客テナントでアプリケーションを承認する必要があります。 これは、アプリケーションが顧客に代わってMicrosoft Defender for Endpointアプリケーションと対話するためです。

   顧客のテナントから **グローバル管理者** を持つユーザーは、同意リンクを選択し、アプリケーションを承認する必要があります。

   同意リンクは次の形式です。

   ```http
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   00000000-0000-0000-0000-00000000000 をアプリケーション ID に置き換える必要がある場合

   同意リンクをクリックした後、顧客のテナントのグローバル管理者にサインインし、アプリケーションに同意します。

   :::image type="content" source="images/app-consent-partner.png" alt-text="[承諾] ボタン" lightbox="images/app-consent-partner.png":::

   さらに、顧客にテナント ID を要求し、トークンを取得するときに将来使用するために保存する必要があります。

6. **完成です！** アプリケーションが正常に登録されました。 トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token-example"></a>アクセス トークンの例を取得する

**メモ：** 顧客に代わってアクセス トークンを取得するには、次のトークン取得で顧客のテナント ID を使用します。

AAD トークンの詳細については、「[AAD チュートリアル」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)参照してください。

### <a name="using-powershell"></a>PowerShell の使用

```powershell
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a>C の使用#

> 次のコードは、Nuget Microsoft.IdentityModel.Clients.ActiveDirectory でテストされました

> [!IMPORTANT]
> [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) NuGet パッケージとAzure AD Authentication ライブラリ (ADAL) は非推奨になりました。 2020 年 6 月 30 日以降、新機能は追加されていません。   アップグレードすることを強くお勧めします。詳細については、 [移行ガイド](/azure/active-directory/develop/msal-migration) を参照してください。

- 新しいコンソール アプリケーションを作成する
- [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGetインストールする
- 以下を使用して追加する

    ```console
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- アプリケーションに次のコードをコピー/貼り付けます (3 つの変数を更新してください。 `tenantId``appId``appSecret`

    ```console
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

### <a name="using-python"></a>Python の使用

Python を[使用したトークンの取得](run-advanced-query-sample-python.md#get-token)に関する参照

### <a name="using-curl"></a>Curl の使用

> [!NOTE]
> 次の手順では、Windows用の Curl がコンピューターに既にインストールされていると想定されています

- コマンド ウィンドウを開く
- CLIENT_IDを Azure アプリケーション ID に設定する
- CLIENT_SECRETを Azure アプリケーション シークレットに設定する
- アプリケーションを使用してアプリケーションにアクセスする顧客の Azure テナント ID にTENANT_ID Microsoft Defender for Endpoint設定する
- 次のコマンドを実行します。

```curl
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

フォームの回答が表示されます。

```console
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得していることを確認するサニティ チェック:

- 前の手順で取得したトークンを [JWT](https://jwt.ms) にコピー/貼り付けてデコードする
- 必要なアクセス許可を持つ "ロール" 要求を取得したことを検証する
- 次のスクリーンショットでは、Microsoft Defender for Endpointに対する複数のアクセス許可を持つアプリケーションから取得されたデコードされたトークンを確認できます。
- "tid" 要求は、トークンが属するテナント ID です。

:::image type="content" source="images/webapp-decoded-token.png" alt-text="トークン検証ページ" lightbox="images/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>トークンを使用してMicrosoft Defender for Endpoint API にアクセスする

- 使用する API を選択してください。詳細については、「[サポートされているMicrosoft Defender for Endpoint API」を](exposed-apis-list.md)参照してください。
- 送信する Http 要求の Authorization ヘッダーを "Bearer {token}" に設定します (Bearer は承認スキームです)
- トークンの有効期限は 1 時間です (同じトークンを使用して複数の要求を送信できます)

- **C# を使用して** アラートの一覧を取得する要求を送信する例

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
