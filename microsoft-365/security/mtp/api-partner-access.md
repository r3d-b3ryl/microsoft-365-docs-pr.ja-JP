---
title: Microsoft の脅威保護 Api によるパートナーアクセス
description: ユーザーに代わって Microsoft 脅威保護へのプログラムによるアクセスを取得する AAD アプリケーションを作成する方法について説明します。
keywords: パートナー、アクセス、api、マルチテナント、同意、アクセストークン、アプリ
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
ms.openlocfilehash: d78996c0cd37a6b82edde52367b04647560d5cf7
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650399"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a>Microsoft の脅威保護 Api によるパートナーアクセス

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


このページでは、ユーザーの代わりに Microsoft の脅威保護にプログラムによってアクセスする AAD アプリケーションを作成する方法について説明します。

Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。 これらの Api は、Microsoft の脅威保護機能に基づいて、ワークフローとイノベーションを自動化するのに役立ちます。 API へのアクセスには、OAuth 2.0 認証が必要です。 詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。

一般に、Api を使用するには、次の手順を実行する必要があります。
- **マルチテナント**AAD アプリケーションを作成します。
- お客様のアプリケーションが必要とする Microsoft の脅威保護リソースにアクセスするために、お客様の管理者による承認 (同意) を取得します。
- このアプリケーションを使用してアクセストークンを取得します。
- トークンを使用して、Microsoft の脅威保護 API にアクセスします。

AAD アプリケーションを作成する方法、Microsoft の脅威保護へのアクセストークンを取得する方法、トークンを検証する方法については、以下の手順に従ってください。

## <a name="create-the-multi-tenant-app"></a>マルチテナントアプリを作成する

1. **グローバル管理者**の役割を持つユーザーを使用して[Azure テナント](https://portal.azure.com)にログオンします。

2. **Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. 登録形式:

    - アプリケーションの名前を選択します。

    - サポートされているアカウントの種類-任意の組織ディレクトリ内のアカウント。

    - リダイレクト URI-種類: Web、URI: https://portal.azure.com

    ![Microsoft Azure パートナーアプリケーション登録の画像](../../media/atp-api-new-app-partner.png)


4. アプリケーションに Microsoft の脅威保護へのアクセスを許可し、統合を完了するために必要な最低限のアクセス許可セットを割り当てます。

   - アプリケーションページで、[ **API Permissions**] [組織が使用する  >  **アクセス許可**api を追加する] > 入力して、[microsoft threat  >  **APIs my organization uses** **protection** ] をクリックします。 **Microsoft Threat Protection**

   >[!NOTE]
   >Microsoft の脅威保護は、元のリストには表示されません。 テキストボックスに名前を記述して、表示されることを確認する必要があります。

   ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a>API アクセス許可の要求

   必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。 

   次の例では、 **「すべてのインシデントを読み取る」** アクセス許可を使用します。

   [**アプリケーションのアクセス許可**のインシデント] を選択します。  >  **すべて**> [**アクセス許可の追加**] をクリックします。

   ![API アクセスと API 選択の画像](../../media/request-api-permissions.PNG)


5. [**同意を許可**する] をクリックする

    >[!NOTE]
    >アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意** を得る] をクリックする必要があります。

    ![許可権限の画像](../../media/grant-consent.PNG)

6. アプリケーションにシークレットを追加します。

    - [ **証明書 & シークレット**] をクリックし、シークレットに説明を追加して、[ **追加**] をクリックします。

    >[!IMPORTANT]
    > [ **追加**] を選択した後、 **生成されたシークレット値をコピー**します。 退出後に取得することはできません。

    ![アプリキーを作成する画像](../../media/webapp-create-key2.png)

7. アプリケーション ID を書き留めておきます。

   - アプリケーションページで、[ **概要** ] に移動し、次の内容をコピーします。

   ![作成されたアプリ id の画像](../../media/app-id.png)

8. お客様のテナントにアプリケーションを追加します。

    アプリケーションは、使用する予定の各顧客テナントで承認される必要があります。 これは、アプリケーションがお客様の代わりに Microsoft の脅威保護アプリケーションと対話するためです。

    お客様のテナントの **グローバル管理者** を持つユーザーは、同意リンクをクリックして、アプリケーションを承認する必要があります。

    同意リンクの形式は次のとおりです。

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    00000000-0000-0000-0000-000000000000 は、アプリケーション ID に置き換える必要があります。

    同意リンクをクリックした後、お客様のテナントの全体管理者にログインして、アプリケーションに同意します。

    ![同意の画像](../../media/app-consent-partner.png)

    また、お客様にテナント ID を要求して、トークンを取得するときに使用するために保存する必要があります。

- **完成です！** アプリケーションが正常に登録されました。 
- トークンの取得と検証については、以下の例を参照してください。

## <a name="get-an-access-token-examples"></a>アクセストークンの例を取得します。

>[!NOTE]
> お客様の代わりにアクセストークンを取得するには、次のトークンの取得でお客様のテナント ID を使用します。

<br>AAD トークンの詳細については、「 [aad チュートリアル](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

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

### <a name="using-c"></a>C# を使用する場合:

>次のコードは、Nuget の Microsoft という id を使用してテストされています。 ActiveDirectory

- 新しいコンソールアプリケーションを作成する
- Nuget[クライアント](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)をインストールします。
- を使用して以下を追加します

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- 以下のコードをアプリケーションにコピーまたは貼り付けます (3 つの変数を更新してください ```tenantId, appId, appSecret``` )。

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a>Curl の使用

> [!NOTE]
> 次の手順では、Windows の Curl がコンピューターに既にインストールされています。

- コマンドウィンドウを開く
- Azure アプリケーション ID に CLIENT_ID を設定する
- Azure アプリケーションシークレットに CLIENT_SECRET を設定する
- アプリケーションを使用して Microsoft の脅威保護アプリケーションにアクセスするお客様の Azure テナント ID に TENANT_ID を設定します。
- 次のコマンドを実行します。

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

次の形式の応答が得られます。

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得していることを確認するために、正当性チェックを行います。

- 前の手順で取得したトークンにコピー/貼り [付けして](https://jwt.ms) 、デコードします。
- 必要なアクセス許可を持つ ' roles ' クレームを取得することを確認する
- 次のスクリーンショットでは、Microsoft の脅威保護に対する複数のアクセス許可を持つアプリケーションから取得したデコードされたトークンを確認できます。
- "Tid" クレームは、トークンが属するテナント ID です。

![トークン検証のイメージ](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a>トークンを使用して Microsoft の脅威保護 API にアクセスする

- 使用する API を選択します。詳細については、「[サポートされる Microsoft Threat Protection api](api-supported.md) 」を参照してください。
- "ベアラー {token}" に送信する Http 要求で承認ヘッダーを設定する (ベアラーが認証スキームである)
- トークンの有効期限は1時間です (同じトークンを使用して、さらに1つの要求を送信できます)。

- **C# を使用して**、インシデントのリストを取得するための要求を送信する例 
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
