---
title: Microsoft 365 Defender API を介したパートナー アクセス
description: ユーザーに代わってMicrosoft 365 Defenderにプログラムでアクセスできるようにするアプリを作成する方法について説明します。
keywords: パートナー, access, api, マルチテナント, 同意, アクセス トークン, アプリ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 43bb018abe6a19464d7e52493ed1b4ccd1f15140
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102418"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a>Microsoft 365 Defender API へのパートナー アクセス権を持つアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

このページでは、複数のテナントのユーザーに代わって、Microsoft 365 DefenderにプログラムでアクセスできるAzure Active Directory アプリを作成する方法について説明します。 マルチテナント アプリは、大規模なユーザー グループにサービスを提供する場合に便利です。

1 人のユーザーに代わってMicrosoft 365 Defenderにプログラムでアクセスする必要がある場合は、「[アプリを作成して、ユーザーの代わりにMicrosoft 365 Defender API にアクセスする」を参照してください](api-create-app-user-context.md)。 ユーザーが明示的に定義されていないアクセスが必要な場合 (たとえば、バックグラウンド アプリやデーモンを作成している場合)、[ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md)方法に関するページを参照してください。 必要なアクセスの種類がわからない場合は、[概要](api-access.md)を参照してください。

Microsoft 365 Defenderは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defenderの機能を利用するのに役立ちます。 この API アクセスには、OAuth2.0 認証が必要です。 詳細については、「[OAuth 2.0 Authorization Code Flow」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、これらの API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して、Microsoft 365 Defender API にアクセスします。

このアプリはマルチテナントであるため、ユーザーに代わって各テナントの [管理者の同意](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) も必要になります。

この記事では、次の方法について説明します。

- **マルチテナント** Azure AD アプリケーションを作成する
- アプリケーションに必要なリソースMicrosoft 365 Defenderにアクセスするために、ユーザー管理者から承認された同意を得ます。
- Microsoft 365 Defenderへのアクセス トークンを取得する
- トークンを検証する

Microsoft 365 Defenderは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、作業フローを自動化し、Microsoft 365 Defender機能に基づいてイノベーションを行うのに役立ちます。 API アクセスには、OAuth2.0 認証が必要です。 詳細については、「[OAuth 2.0 Authorization Code Flow」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、API を使用するには、次の手順を実行する必要があります。

- **マルチテナント** Azure AD アプリケーションを作成します。
- アプリケーションが必要なリソースにアクセスするための承認 (同意) をユーザー管理者から取得Microsoft 365 Defender。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して、Microsoft 365 Defender API にアクセスします。

次の手順では、マルチテナント Azure AD アプリケーションを作成し、アクセス トークンを取得してMicrosoft 365 Defenderし、トークンを検証する方法について説明します。

## <a name="create-the-multi-tenant-app"></a>マルチテナント アプリを作成する

1. **グローバル管理者** ロールを持つユーザーとして [Azure](https://portal.azure.com) にサインインします。

2. **Azure Active Directory** > **アプリの登録** > **新しい登録** に移動します。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender ポータルのアプリケーションの登録セクション" lightbox="../../media/atp-azure-new-app2.png":::

3. 登録フォームで、次の手順を実行します。

   - アプリケーションの名前を選択します。
   - **サポートされているアカウントの種類** から、**任意の組織ディレクトリ (任意の Azure AD ディレクトリ) の [アカウント] - [マルチテナント**] を選択します。
   - **[リダイレクト URI]** セクションに入力します。 種類 **Web** を選択し、リダイレクト URI を **https://portal.azure.com**.

   フォームへの入力が完了したら、[登録] を選択 **します**。

   :::image type="content" source="../..//media/atp-api-new-app-partner.png" alt-text="Microsoft 365 Defender ポータルのアプリケーションの登録セクション" lightbox="../..//media/atp-api-new-app-partner.png":::

4. アプリケーション ページで、組織が>**を使用する** **API アクセス許可** > **の追加アクセス許可** >  API を選択し、「**Microsoft Threat Protection」** と入力して、**Microsoft Threat Protection** を選択します。 これで、アプリはMicrosoft 365 Defenderにアクセスできるようになりました。

   > [!TIP]
   > *Microsoft Threat Protection* はMicrosoft 365 Defenderの以前の名前であり、元の一覧には表示されません。 テキスト ボックスに名前を書き込み始めて、その名前が表示されるのを確認する必要があります。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender ポータルの [API の使用状況] セクション" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. [**アプリケーションのアクセス許可**] を選択します。 シナリオに関連するアクセス許可 ( **Incident.Read.All** など) を選択し、[ **アクセス許可の追加**] を選択します。

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender ポータルのアプリケーションのアクセス許可ウィンドウ" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > シナリオに関連するアクセス許可を選択する必要があります。 *すべてのインシデントを読み取* るは、単なる例です。 必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを参照してください。
    >
    > たとえば、 [高度なクエリを実行するには、[高度なクエリ](api-advanced-hunting.md)の実行] アクセス許可を選択します。 [デバイスを分離](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)するには、"マシンの分離" アクセス許可を選択します。

6. [ **管理者の同意を付与する]** を選択します。 アクセス許可を追加するたびに、[ **管理者の同意を付与** する] を選択して有効にする必要があります。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Microsoft 365 Defender ポータルで管理者の同意を付与するセクション" lightbox="../../media/grant-consent.PNG":::

7. アプリケーションにシークレットを追加するには、[ **証明書&シークレット**] を選択し、シークレットに説明を追加してから、[ **追加**] を選択します。

    > [!TIP]
    > **[追加]** を選択した後、**生成されたシークレット値のコピーを** 選択します。 退出後にシークレット値を取得することはできません。

      :::image type="content" source="../../media/webapp-create-key2.png" alt-text="Microsoft 365 Defender ポータルの [シークレットの追加] セクション" lightbox="../../media/webapp-create-key2.png":::

8. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [ **概要]** に一覧表示されます。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender ポータルの [概要] ウィンドウ" lightbox="../../media/app-and-tenant-ids.png":::

9. ユーザーのテナントにアプリケーションを追加します。

   アプリケーションはユーザーに代わってMicrosoft 365 Defenderと対話するため、アプリケーションを使用するすべてのテナントに対して承認する必要があります。

   ユーザーのテナントの **グローバル管理者** は、同意リンクを表示し、アプリケーションを承認する必要があります。

   同意リンクは次の形式です。

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   数字 `00000000-0000-0000-0000-000000000000` はアプリケーション ID に置き換える必要があります。

   同意リンクをクリックした後、ユーザーのテナントのグローバル管理者にサインインし、アプリケーションに同意します。

   :::image type="content" source="../../media/app-consent-partner.png" alt-text="Microsoft 365 Defender ポータルの同意アプリケーション ページ" lightbox="../../media/app-consent-partner.png":::

   また、テナント ID をユーザーに要求する必要もあります。 テナント ID は、アクセス トークンの取得に使用される識別子の 1 つです。

- **完了!** アプリケーションが正常に登録されました。
- トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure AD トークンの詳細については、 [Azure AD のチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

> [!IMPORTANT]
> このセクションの例では、テスト目的でシークレット値を貼り付けすることをお勧めしますが、運用環境で実行されているアプリケーションに **シークレットをハードコーディングしないでください** 。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)を使用すると、アプリのシークレットをセキュリティで保護することができます。 アプリを保護する方法の実用的な例については、「[Azure Key Vaultを使用してサーバー アプリのシークレットを管理する」を参照してください](/learn/modules/manage-secrets-with-azure-key-vault/)。

> [!TIP]
> 次の例では、ユーザーのテナント ID を使用して、スクリプトが動作していることをテストします。

### <a name="get-an-access-token-using-powershell"></a>PowerShell を使用してアクセス トークンを取得する

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

### <a name="get-an-access-token-using-c"></a>C を使用してアクセス トークンを取得する\#

> [!NOTE]
> 次のコードは、Nuget Microsoft.Identity.Client 3.19.8 でテストされました。

> [!IMPORTANT]
> [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) NuGet パッケージとAzure AD Authentication ライブラリ (ADAL) は非推奨になりました。 2020 年 6 月 30 日以降、新機能は追加されていません。   アップグレードすることを強くお勧めします。詳細については、 [移行ガイド](/azure/active-directory/develop/msal-migration) を参照してください。

1. 新しいコンソール アプリケーションを作成します。
1. [Microsoft.Identity.Client](https://www.nuget.org/packages/Microsoft.Identity.Client/) NuGetインストールします。
1. 次の行を追加します。

    ```C#
    using Microsoft.Identity.Client;
    ```

1. 次のコードをコピーしてアプリに貼り付けます (次の 3 つの変数を更新することを忘れないでください。 `tenantId``clientId``appSecret`

    ```C#
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 
    const string authority = https://login.microsoftonline.com;
    const string audience = https://api.securitycenter.microsoft.com;

    IConfidentialClientApplication myApp = ConfidentialClientApplicationBuilder.Create(appId).WithClientSecret(appSecret).WithAuthority($"{authority}/{tenantId}").Build();

    List<string> scopes = new List<string>() { $"{audience}/.default" };

    AuthenticationResult authResult = myApp.AcquireTokenForClient(scopes).ExecuteAsync().GetAwaiter().GetResult();

    string token = authResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a>Python を使用してアクセス トークンを取得する

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a>curl を使用してアクセス トークンを取得する

> [!NOTE]
> Curl は、Windows 10 バージョン 1803 以降にプレインストールされています。 その他のバージョンのWindowsについては、[公式の curl Web サイト](https://curl.haxx.se/windows/)から直接ツールをダウンロードしてインストールします。

1. コマンド プロンプトを開き、CLIENT_IDを Azure アプリケーション ID に設定します。
1. CLIENT_SECRETを Azure アプリケーション シークレットに設定します。
1. アプリを使用してMicrosoft 365 Defenderにアクセスするユーザーの Azure テナント ID にTENANT_IDを設定します。
1. 次のコマンドを実行します。

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

成功した応答は次のようになります。

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>トークンを検証する

1. トークンをコピーし [、JSON Web トークン検証ツール Web サイト JWT](https://jwt.ms) に貼り付けてデコードします。
1. デコードされたトークン内の *ロール* 要求に必要なアクセス許可が含まれていることを確認します。

次の図では、アプリから取得したデコードされたトークンと、アクセス許可、および```AdvancedHunting.Read.All```アクセス許可を```Incidents.Read.All``````Incidents.ReadWrite.All```確認できます。

:::image type="content" source="../../media/webapp-decoded-token.png" alt-text="Microsoft 365 Defender ポータルの [デコードされたトークン] ウィンドウ" lightbox="../../media/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>トークンを使用してMicrosoft 365 Defender API にアクセスする

1. 使用する API (インシデント、または高度な捜索) を選択します。 詳細については、「[サポートされているMicrosoft 365 Defender API」を参照してください](api-supported.md)。
2. 送信しようとしている http 要求で、承認ヘッダー `"Bearer" <token>`を 、承認スキームである *ベアラー* 、検証済み *トークンであるトークン* に設定します。
3. トークンの有効期限は 1 時間以内です。 この間に、同じトークンを使用して複数の要求を送信できます。

次の例は、 **C# を使用して** インシデントの一覧を取得する要求を送信する方法を示しています。

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- ["Hello world" アプリケーションを作成する](api-hello-world.md)
- [ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md)
- [ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [Azure Key Vaultを使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [ユーザー サインインと API アクセスに対する OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
