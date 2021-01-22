---
title: Microsoft 365 Defender REST API の Hello World
description: アプリを作成し、トークンを使用して Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: アプリ, トークン, アクセス, aad, アプリ, アプリケーションの登録, powershell, スクリプト, グローバル管理者, アクセス許可, Microsoft 365 Defender
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
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928380"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API の Hello World

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>単純な PowerShell スクリプトを使用してインシデントを取得する

このプロジェクトを完了するには、5 ~ 10 分かかります。 この時間の見積もりには、アプリケーションの登録と、PowerShell サンプル スクリプトからのコードの適用が含まれます。

### <a name="register-an-app-in-azure-active-directory"></a>Azure Active Directory にアプリを登録する

1. グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。

2. Azure **Active Directory アプリの**  >  **登録新規登録**  >  **に移動します**。

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. 登録フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。 リダイレクト URI の選択はオプションです。 この例を完了するために必要な手順は不要です。

4. アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用して  >    >  **、「Microsoft Threat Protection」** と入力し **、[Microsoft Threat Protection] を選択します**。 これで、アプリは Microsoft 365 Defender にアクセスできます。

   > [!TIP]
   > *Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。 テキスト ボックスが表示されるのを確認するには、テキスト ボックスに名前の書き込みを開始する必要があります。
   ![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)

   - アプリケーションの **アクセス許可**  >  **Incident.Read.All を** 選択し、[アクセス許可 **の追加] を選択します**。

   ![API アクセスと API の選択の画像](../../media/request-api-permissions.PNG)

5. [管理者 **の同意を付与する] を選択します**。 アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。

    ![アクセス許可の付与の画像](../../media/grant-consent.PNG)

6. アプリケーションにシークレットを追加します。 Select **Certificates & secrets,** add a description to the secret, then select **Add**.

    > [!TIP]
    > [追加] を **選択した後**、生成 **されたシークレットの値をコピーします**。 退出後にシークレット値を取得できない。

    ![アプリ キーの作成の画像](../../media/webapp-create-key2.png)

7. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [概要] **に** 一覧表示されます。

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>アプリを使用してトークンを取得し、そのトークンを使用して API にアクセスする

Azure Active Directory トークンについて詳しくは、Azure Active Directory のチュートリアル [AD覧ください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> このデモ アプリの例では、テストの目的で秘密の値を貼り付ける必要があります。ただし、実稼働環境で実行されているアプリケーションにシークレットをハードコードし込む必要があります。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)を使用して、アプリのシークレットをセキュリティで保護することができます。 アプリを保護する方法の実用的な例については、「Azure Key Vault を使用してサーバー アプリのシークレットを管理する」 [を参照してください](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 以下のスクリプトをコピーし、お気に入りのテキスト エディターに貼り付けます。 名前を付 **けてGet-Token.ps1。** PowerShell ISE でコードを実行することもできますが、保存する必要があります。これは、次のセクションでインシデント フェッチ スクリプトを使用するときに再度実行する必要があるためです。

    このスクリプトはトークンを生成し、そのトークンを作業フォルダーの名前の下に保存 *Latest-token.txt。*

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>トークンを検証する

1. 受け取ったトークンをコピーして JWT に貼 [り付](https://jwt.ms) け、デコードします。
1. *JWT は* *JSON Web トークンを表します*。 デコードされたトークンには、JSON 形式のアイテムまたはクレームが多数含まれます。 デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。

    次の図では、アプリから取得したデコードされたトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 確認できます。

    ![画像jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>最近のインシデントの一覧を取得する

以下のスクリプトでは、API **へのアクセスGet-Token.ps1** を使用します。 次に、過去 48 時間以内に最後に更新されたインシデントの一覧を取得し、そのリストを JSON ファイルとして保存します。

> [!IMPORTANT]
> このスクリプトを保存したフォルダーと同じフォルダーに保存 **Get-Token.ps1。**

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

完了です。 正常に実行されました。

- アプリケーションを作成して登録します。
- そのアプリケーションに通知を読み取るアクセス許可が付与されます。
- API に接続されています。
- PowerShell スクリプトを使用して、過去 48 時間以内に更新されたインシデントを返しました。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)
- [ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する](api-create-app-web.md)
- [ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md)
- [マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する](api-partner-access.md)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
