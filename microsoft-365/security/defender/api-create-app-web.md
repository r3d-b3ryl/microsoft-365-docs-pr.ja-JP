---
title: ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する
description: ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する方法について説明します。
keywords: アプリ、アクセス、API、作成
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: fbcf081bda20dd470837614c985de77d037673a3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67471392"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

このページでは、デーモンやバックグラウンド サービスを作成する場合など、定義されたユーザーなしでMicrosoft 365 Defenderにプログラムでアクセスするアプリケーションを作成する方法について説明します。

1 人以上のユーザーに代わってMicrosoft 365 Defenderにプログラムでアクセスする必要がある場合は、「[ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成](api-create-app-user-context.md)する」および「[Microsoft 365 Defender API へのパートナー アクセスを持つアプリを作成する」を](api-partner-access.md)参照してください。 必要なアクセスの種類がわからない場合は、「 [作業の開始](api-access.md)」を参照してください。

Microsoft 365 Defenderは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defenderの機能を利用するのに役立ちます。 この API アクセスには、OAuth2.0 認証が必要です。 詳細については、「 [OAuth 2.0 承認コード フロー」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、これらの API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して、Microsoft 365 Defender API にアクセスします。

この記事では、次の方法について説明します。

- Azure AD アプリケーションを作成する
- Microsoft 365 Defenderへのアクセス トークンを取得する
- トークンを検証します。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者** ロールを持つユーザーとして [Azure](https://portal.azure.com) にサインインします。

2. **Azure Active Directory** >  **に移動アプリの登録** > **新しい登録**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender ポータルの [新しい登録] タブ" lightbox="../../media/atp-azure-new-app2.png":::

3. フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。

4. アプリケーション ページで、組織が>**を使用する** **API アクセス許可** > **の追加アクセス許可** >  API を選択し、「**Microsoft Threat Protection」** と入力して、**Microsoft Threat Protection** を選択します。 これで、アプリはMicrosoft 365 Defenderにアクセスできるようになりました。

   > [!TIP]
   > *Microsoft Threat Protection* はMicrosoft 365 Defenderの以前の名前であり、元の一覧には表示されません。 テキスト ボックスに名前を書き込み始めて、その名前が表示されるのを確認する必要があります。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender ポータルの組織の API 使用状況タブ" lightbox="../../media/apis-in-my-org-tab.PNG":::

5. [**アプリケーションのアクセス許可**] を選択します。 シナリオに関連するアクセス許可 ( **Incident.Read.All** など) を選択し、[ **アクセス許可の追加**] を選択します。

   :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender ポータルの [アプリケーションのアクセス許可] ウィンドウ" lightbox="../../media/request-api-permissions.PNG":::

    > [!NOTE]
    > シナリオに関連するアクセス許可を選択する必要があります。 *すべてのインシデントを読み取* るは、単なる例です。 必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを参照してください。
    >
    > たとえば、 [高度なクエリを実行するには、[高度なクエリ](api-advanced-hunting.md)の実行] アクセス許可を選択します。 [デバイスを分離](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)するには、"マシンの分離" アクセス許可を選択します。

6. [ **管理者の同意を付与する]** を選択します。 アクセス許可を追加するたびに、[ **管理者の同意を付与** する] を選択して有効にする必要があります。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Microsoft 365 Defender ポータルの同意付与関連ウィンドウ" lightbox="../../media/grant-consent.PNG":::

7. アプリケーションにシークレットを追加するには、[ **証明書&シークレット**] を選択し、シークレットに説明を追加してから、[ **追加**] を選択します。

    > [!TIP]
    > **[追加]** を選択した後、**生成されたシークレット値のコピーを** 選択します。 退出後にシークレット値を取得することはできません。

    :::image type="content" source="../../media/defender-endpoint/webapp-create-key2.png" alt-text="Microsoft 365 Defender ポータルの [アプリの作成] ウィンドウ" lightbox="../../media/defender-endpoint/webapp-create-key2.png":::

8. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [ **概要]** に一覧表示されます。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender ポータルの [概要] ウィンドウ" lightbox="../../media/app-and-tenant-ids.png":::

9. **Microsoft 365 Defender パートナーの場合のみ**: Microsoft 365 Defender API を介したパートナー アクセスの [手順に従って](./api-partner-access.md)、アプリをマルチテナントに設定し、管理者の同意を受けたらすべてのテナントで利用できるようにします。 パートナー アクセスは、サード パーティのアプリに **必要** です。たとえば、複数の顧客のテナントで実行することを目的としたアプリを作成する場合などです。 テナントでのみ実行するサービスを作成する場合は **必要ありません** 。たとえば、独自のデータとのみ対話する独自の使用のためのアプリケーションなどです。 アプリをマルチテナントに設定するには:

    - **[認証]** に移動し、**リダイレクト URI** として追加https://portal.azure.comします。

    - ページの下部にある [ **サポートされているアカウントの種類**] で、マルチテナント アプリ **の組織ディレクトリ アプリケーションの同意で [アカウント** ] を選択します。

    アプリケーションはユーザーに代わってMicrosoft 365 Defenderと対話するため、アプリケーションを使用するすべてのテナントに対して承認する必要があります。

    各テナントの Active Directory グローバル管理者は、同意リンクを選択し、アプリを承認する必要があります。

    同意リンクの構造は次のとおりです。

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    数字 `00000000-0000-0000-0000-000000000000` はアプリケーション ID に置き換える必要があります。  

**完了!** アプリケーションが正常に登録されました。 トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure Active Directory トークンの詳細については、 [Azure AD のチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

> [!IMPORTANT]
> このセクションの例では、テスト目的でシークレット値を貼り付けすることをお勧めしますが、運用環境で実行されているアプリケーションに **シークレットをハードコーディングしないでください** 。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)を使用すると、アプリのシークレットをセキュリティで保護することができます。 アプリを保護する方法の実用的な例については、「[Azure Key Vaultを使用してサーバー アプリのシークレットを管理する」を参照してください](/learn/modules/manage-secrets-with-azure-key-vault/)。

### <a name="get-an-access-token-using-powershell"></a>PowerShell を使用してアクセス トークンを取得する

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

1. NuGet [Microsoft.Identity.Client をインストールします](https://www.nuget.org/packages/Microsoft.Identity.Client/)。

1. 次の行を追加します。

    ```C#
    using Microsoft.Identity.Client;
    ```

1. 次のコードをコピーしてアプリに貼り付けます (次の 3 つの変数を更新することを忘れないでください。 `tenantId``clientId``appSecret`

    ```C#
    csharp
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
> Curl は、Windows 10 バージョン 1803 以降にプレインストールされています。 他のバージョンの Windows の場合は、 [公式の curl Web サイト](https://curl.haxx.se/windows/)から直接ツールをダウンロードしてインストールします。

1. コマンド プロンプトを開き、CLIENT_IDを Azure アプリケーション ID に設定します。

1. CLIENT_SECRETを Azure アプリケーション シークレットに設定します。

1. アプリを使用してMicrosoft 365 Defenderにアクセスする顧客の Azure テナント ID にTENANT_IDを設定します。

1. 次のコマンドを実行します。

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   成功した応答は次のようになります。

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>トークンを検証する

1. トークンをコピーし [、JSON Web トークン検証ツール Web サイト JWT](https://jwt.ms) に貼り付けてデコードします。

1. デコードされたトークン内の *ロール* 要求に必要なアクセス許可が含まれていることを確認します。

   次の図では、アプリから取得したデコードされたトークンと、アクセス許可、および`AdvancedHunting.Read.All`アクセス許可を`Incidents.Read.All``Incidents.ReadWrite.All`確認できます。

   :::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="Microsoft 365 Defender ポータルの [デコードされたトークン] ウィンドウ" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>トークンを使用してMicrosoft 365 Defender API にアクセスする

1. 使用する API (インシデント、または高度な捜索) を選択します。 詳細については、「[サポートされているMicrosoft 365 Defender API」を参照してください](api-supported.md)。

2. 送信しようとしている http 要求で、承認ヘッダー `"Bearer" <token>`を 、承認スキームである *ベアラー* 、検証済みの *トークンをトークン* に設定します。

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
- [ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md)
- [Microsoft 365 Defender API へのマルチテナント パートナー アクセス権を持つアプリを作成する](api-partner-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [Azure Key Vaultを使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [ユーザー サインインと API アクセスに対する OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
