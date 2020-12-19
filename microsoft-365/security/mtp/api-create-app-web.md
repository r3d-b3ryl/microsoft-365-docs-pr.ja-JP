---
title: ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する
description: ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する方法について説明します。
keywords: アプリ, アクセス, api, 作成
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719358"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

このページでは、定義されたユーザーなしで Microsoft 365 Defender にプログラムでアクセスするアプリケーションを作成する方法について説明します。たとえば、デーモンやバックグラウンド サービスを作成する場合などです。

1 人または複数のユーザーの代わりに Microsoft 365 Defender にプログラムでアクセスする必要がある場合は、「ユーザーの代わりに [Microsoft 365 Defender](api-create-app-user-context.md) API にアクセスするアプリを作成する」と [「Microsoft 365 Defender](api-partner-access.md)API へのパートナー アクセスを使用してアプリを作成する」を参照してください。 必要なアクセスの種類が不明な場合は、「開始する」を [参照してください](api-access.md)。

Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能を利用するのに役立ちます。 この API アクセスには OAuth2.0 認証が必要です。 詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般に、これらの API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して Microsoft 365 Defender API にアクセスします。

この記事では、次の方法について説明します。

- Azure AD アプリケーションを作成する
- Microsoft 365 Defender へのアクセス トークンを取得する
- トークンを検証します。

## <a name="create-an-app"></a>アプリを作成する

1. グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。

2. Azure **Active Directory アプリの**  >  **登録の新規登録**  >  **に移動します**。

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。

4. アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用し  >    >  **、「Microsoft Threat Protection」と** 入力して **、Microsoft Threat Protection を選択します**。 これで、アプリは Microsoft 365 Defender にアクセスできます。

   > [!TIP]
   > *Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。 テキスト ボックスが表示されるのを確認するには、テキスト ボックスに名前の書き込みを開始する必要があります。

   ![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)

5. アプリケーションの **アクセス許可を選択します**。 シナリオに関連するアクセス許可 **(Incident.Read.All** など) を選択し、[アクセス許可の追加 **] を選択します**。

   ![API アクセスと API の選択の画像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > シナリオに関連するアクセス許可を選択する必要があります。 *すべてのインシデントの読み取り* は単なる例です。 必要なアクセス許可を確認するには、呼び出す API の **[** アクセス許可] セクションを参照してください。
    >
    > たとえば、高度な [クエリを実行するには、[](api-advanced-hunting.md)高度なクエリの実行] 権限を選択します。デバイス [を分離するには、[コンピューターの](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)分離] アクセス許可を選択します。

6. [管理者 **の同意を付与する] を選択します**。 アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。

    ![アクセス許可の付与の画像](../../media/grant-consent.PNG)

7. アプリケーションにシークレットを追加するには、[証明書とシークレット&し、シークレットに説明を追加して、[追加] を選択 **します**。

    > [!TIP]
    > [追加] を **選択した後**、生成 **されたシークレットの値をコピーします**。 退出後にシークレット値を取得できない。

    ![アプリ キーの作成の画像](../../media/webapp-create-key2.png)

8. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [概要] **に** 一覧表示されます。

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

9. **Microsoft 365 Defender パートナー** の場合 [のみ:](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) Microsoft 365 Defender API を介したパートナー アクセスについては、次の手順に従い、アプリをマルチテナントに設定して、管理者の同意を受け取った後、すべてのテナントで利用できます。 パートナー アクセスは **、サード** パーティ製アプリ (たとえば、複数の顧客のテナントで実行するアプリを作成する場合) に必要です。 テナント **でのみ** 実行するサービス (独自のデータのみを操作する独自の利用状況用のアプリケーションなど) を作成する場合は必要ありません。 アプリをマルチテナントに設定するには:

    - [認証 **] に** 移動し、リダイレクト https://portal.azure.com URI **として追加します**。

    - ページの下部にある [サポートされているアカウントの種類] で、マルチテナント アプリの組織ディレクトリ アプリケーションの同意にある [アカウント] を選択します。

    アプリケーションはユーザーの代わりに Microsoft 365 Defender とやり取りを行うので、そのアプリケーションを使用する予定のすべてのテナントに対して承認が必要です。

    各テナントの Active Directory グローバル管理者は、同意リンクを選択してアプリを承認する必要があります。

    同意リンクの構造は次のとおりです。

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    数字は `00000000-0000-0000-0000-000000000000` アプリケーション ID に置き換える必要があります。  

**完成です！** アプリケーションが正常に登録されました。 トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure Active Directory トークンについて詳しくは、Azure Active Directory のチュートリアル [AD覧ください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> このセクションの例では、テスト目的でシークレット値を貼り付ける方法を推奨しますが、実稼働環境で実行されているアプリケーションにシークレットをハードコードし込む必要があります。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)を使用して、アプリのシークレットをセキュリティで保護することができます。 アプリを保護する方法の実用的な例については、「Azure Key Vault を使用してサーバー アプリのシークレットを管理する」 [を参照してください](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。

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
> 次のコードは、Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 でテストされました。

1. 新しいコンソール アプリケーションを作成します。

1. NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory をインストールします](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。

1. 次の行を追加します。

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. 次のコードをコピーしてアプリに貼り付けます (3 つの変数を忘れずに更新してください: `tenantId` `clientId` , , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Python を使用してアクセス トークンを取得する

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

### <a name="get-an-access-token-using-curl"></a>レジストリを使用してアクセス トークンを取得する

> [!NOTE]
> Windows 10 バージョン 1803 以降には、あらかじめインストールされています。 他のバージョンの Windows では、公式 Web サイトから直接ツールをダウンロード [してインストールします](https://curl.haxx.se/windows/)。

1. コマンド プロンプトを開き、Azure CLIENT_ID ID に設定します。

1. Azure CLIENT_SECRET シークレットに設定します。

1. アプリTENANT_ID使用して Microsoft 365 Defender にアクセスする顧客の Azure テナント ID に設定します。

1. 次のコマンドを実行します。

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   正常な応答は次のように表示されます。

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>トークンを検証する

1. トークンをコピーして JSON Web トークン検証 Web サイト [(JWT)](https://jwt.ms) に貼り付け、デコードします。

1. デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。

   次の図では、アプリから取得したデコードされたトークンと、アクセス許可 `Incidents.Read.All` `Incidents.ReadWrite.All` を `AdvancedHunting.Read.All` 確認できます。

   ![トークン検証の画像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>トークンを使用して Microsoft 365 Defender API にアクセスする

1. 使用する API (インシデントまたは高度な検索) を選択します。 詳細については、「サポートされている [Microsoft 365 Defender API」を参照してください](api-supported.md)。

2. 送信する http 要求で、承認ヘッダーを 、承認スキームであるベアラー、検証済みトークンであるトークンに `"Bearer" <token>` 設定します。  

3. トークンは 1 時間以内に期限切れになります。 この間は、同じトークンを使用して複数の要求を送信できます。

次の例は、C# を使用してインシデントの一覧を取得する要求を送信 **する方法を示しています**。

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)
- ["Hello world" アプリケーションを作成する](api-hello-world.md)
- [ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md)
- [マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する](api-partner-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードを理解する](api-error-codes.md)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
