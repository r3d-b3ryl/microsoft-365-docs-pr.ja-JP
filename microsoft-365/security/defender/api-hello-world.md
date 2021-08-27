---
title: Hello World for Microsoft 365 Defender REST API
description: アプリを作成し、トークンを使用してアプリ API にアクセスするMicrosoft 365 Defenderする
keywords: アプリ、トークン、アクセス、aad、アプリ、アプリケーション登録、powershell、スクリプト、グローバル管理者、アクセス許可、microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1aa843bb1e9ca57d6264f34cbfc7c593f9590c2a
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573897"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World for Microsoft 365 Defender REST API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="get-incidents-using-a-simple-powershell-script"></a>簡単な PowerShell スクリプトを使用してインシデントを取得する

このプロジェクトを完了するには、5 ~ 10 分かかります。 この時間の見積もりには、アプリケーションの登録と PowerShell サンプル スクリプトからのコードの適用が含まれます。

### <a name="register-an-app-in-azure-active-directory"></a>アプリをアプリに登録Azure Active Directory

1. グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。

2. [アプリの **登録Azure Active Directory**  >  **新しい登録]**  >  **に移動します**。

   ![アプリケーションの登録Microsoft Azureナビゲーションのイメージ。](../../media/atp-azure-new-app2.png)

3. 登録フォームで、アプリケーションの名前を選択し、[登録] を **選択します**。 リダイレクト URI の選択はオプションです。 この例を完了するために必要な情報は不要です。

4. アプリケーション ページで **、[API アクセス** 許可] [アクセス許可の追加] を選択し、組織で使用するアクセス許可 API > Microsoft Threat Protection と入力し  >    >  **、[Microsoft** Threat **Protection] を選択します**。 これで、アプリはアプリにアクセスMicrosoft 365 Defender。

   > [!TIP]
   > *Microsoft Threat Protection* は、元のMicrosoft 365 Defenderの名前であり、元のリストには表示されません。 テキスト ボックスに名前を書き込み始め、表示を確認する必要があります。
   ![API アクセス許可の選択のイメージ。](../../media/apis-in-my-org-tab.PNG)

   - [**アプリケーションのアクセス許可**  >  **インシデント.Read.All] を選択し、[** アクセス許可 **の追加] を選択します**。

   ![API アクセスと API の選択のイメージ。](../../media/request-api-permissions.PNG)

5. [管理者 **の同意を付与する] を選択します**。 アクセス許可を追加する度に、[管理者の同意 **を付与** する] を選択して有効に設定する必要があります。

    ![アクセス許可の付与のイメージ。](../../media/grant-consent.PNG)

6. アプリケーションにシークレットを追加します。 [ **証明書とシークレット&選択** し、シークレットに説明を追加し、[追加] を **選択します**。

    > [!TIP]
    > [追加] を **選択した後**、生成 **されたシークレット値をコピーします**。 退出後にシークレット値を取得できない。

    ![アプリ キーの作成のイメージ。](../../media/webapp-create-key2.png)

7. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [概要] **に** 一覧表示されます。

   ![作成されたアプリ ID のイメージ。](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>アプリを使用してトークンを取得し、トークンを使用して API にアクセスする

トークンの詳細については、「Azure Azure Active Directoryチュートリアル」[をADしてください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

> [!IMPORTANT]
> このデモ アプリの例では、テスト目的でシークレット値を貼り付けるのを推奨しますが、実稼働環境で実行されているアプリケーションにシークレットをハードコードする必要があります。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)を使用すると、アプリのシークレットをセキュリティで保護できます。 アプリを保護する方法の実用的な例については、「Azure Key Vault を使用してサーバー アプリのシークレットを管理する」 [を参照してください](/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 下のスクリプトをコピーして、お気に入りのテキスト エディターに貼り付けます。 名前を付 **けてGet-Token.ps1。** また、PowerShell ISE でコードを as-is で実行することもできますが、次のセクションでインシデント フェッチ スクリプトを使用するときにもう一度実行する必要がある場合は、保存する必要があります。

    このスクリプトはトークンを生成し、作業フォルダーの名前の下に保存 *Latest-token.txt。*

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

1. 受信したトークンを [JWT](https://jwt.ms) にコピーして貼り付け、デコードします。
1. *JWT は* *JSON Web トークンを表します*。 デコードされたトークンには、多数の JSON 形式のアイテムまたはクレームが含まれます。 デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれているか確認します。

    次の図では、アプリから取得したデコードトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 表示できます。

    ![イメージ jwt.ms。](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>最近のインシデントの一覧を取得する

以下のスクリプトでは、API **Get-Token.ps1** を使用します。 次に、過去 48 時間以内に最後に更新されたインシデントの一覧を取得し、そのリストを JSON ファイルとして保存します。

> [!IMPORTANT]
> このスクリプトは、保存したフォルダーと同じフォルダーに **Get-Token.ps1。**

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

完了です! 正常に完了しました。

- アプリケーションを作成して登録しました。
- そのアプリケーションに通知を読み取るアクセス許可を付与しました。
- API に接続されています。
- PowerShell スクリプトを使用して、過去 48 時間に更新されたインシデントを返しました。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 DefenderAPI の概要](api-overview.md)
- [API にMicrosoft 365 Defenderする](api-access.md)
- [ユーザーなしでアプリを作成してMicrosoft 365 Defenderにアクセスする](api-create-app-web.md)
- [ユーザーに代わって API にMicrosoft 365 Defenderするアプリを作成する](api-create-app-user-context.md)
- [複数テナントパートナーによる API へのアクセス権を持つアプリをMicrosoft 365 Defenderする](api-partner-access.md)
- [Azure Key Vault を使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 ユーザー サインインと API アクセスの承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)