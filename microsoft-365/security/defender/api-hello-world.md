---
title: Microsoft 365 Defender REST API のHello World
description: アプリを作成し、トークンを使用してMicrosoft 365 Defender API にアクセスする方法について説明します
keywords: アプリ, トークン, アクセス, aad, アプリ, アプリケーション登録, powershell, スクリプト, グローバル管理者, アクセス許可, Microsoft 365 Defender
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
ms.openlocfilehash: ca56847bf484714aaa7155ce756417b5263a746b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482452"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API のHello World

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="get-incidents-using-a-simple-powershell-script"></a>単純な PowerShell スクリプトを使用してインシデントを取得する

このプロジェクトを完了するには、5 分から 10 分かかります。 今回の見積もりには、アプリケーションの登録と、PowerShell サンプル スクリプトからのコードの適用が含まれます。

### <a name="register-an-app-in-azure-active-directory"></a>Azure Active Directory にアプリを登録する

1. **グローバル管理者** ロールを持つユーザーとして [Azure](https://portal.azure.com) にサインインします。

2. **Azure Active Directory** >  **に移動アプリの登録** > **新しい登録**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Microsoft 365 Defender ポータルの [新しい登録] セクション" lightbox="../../media/atp-azure-new-app2.png":::

3. 登録フォームで、アプリケーションの名前を選択し、[ **登録**] を選択します。 リダイレクト URI の選択は省略可能です。 この例を完了する必要はありません。

4. アプリケーション ページで、組織が>**を使用する** **API アクセス許可** > **の追加アクセス許可** >  API を選択し、「**Microsoft Threat Protection」** と入力して、**Microsoft Threat Protection** を選択します。 これで、アプリはMicrosoft 365 Defenderにアクセスできるようになりました。

   > [!TIP]
   > *Microsoft Threat Protection* はMicrosoft 365 Defenderの以前の名前であり、元の一覧には表示されません。 テキスト ボックスに名前を書き込み始めて、その名前が表示されるのを確認する必要があります。
   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender ポータルでの API の使用状況のセクション" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - [ **アプリケーションのアクセス許可** > **インシデント.Read.All** ] を選択し、[ **アクセス許可の追加]** を選択します。

     :::image type="content" source="../../media/request-api-permissions.PNG" alt-text="Microsoft 365 Defender ポータルのアプリケーションのアクセス許可ウィンドウ" lightbox="../../media/request-api-permissions.PNG":::

5. [ **管理者の同意を付与する]** を選択します。 アクセス許可を追加するたびに、[ **管理者の同意を付与** する] を選択して有効にする必要があります。

    :::image type="content" source="../../media/grant-consent.PNG" alt-text="Microsoft 365 Defender ポータルの [管理者の同意の付与] セクション" lightbox="../../media/grant-consent.PNG":::

6. アプリケーションにシークレットを追加します。 [ **証明書&シークレット**] を選択し、シークレットに説明を追加して、[ **追加**] を選択します。

    > [!TIP]
    > **[追加]** を選択した後、**生成されたシークレット値のコピーを** 選択します。 退出後にシークレット値を取得することはできません。

    :::image type="content" source="../../media/webapp-create-key2.png" alt-text="Microsoft 365 Defender ポータルの [シークレットの追加] セクション" lightbox="../../media/webapp-create-key2.png":::
    

7. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [ **概要]** に一覧表示されます。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender ポータルの [概要] セクション" lightbox="../../media/app-and-tenant-ids.png":::

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>アプリを使用してトークンを取得し、そのトークンを使用して API にアクセスする

Azure Active Directory トークンの詳細については、 [Azure AD のチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

> [!IMPORTANT]
> このデモ アプリの例では、テスト目的でシークレット値を貼り付けすることをお勧めしますが、運用環境で実行されているアプリケーションに **シークレットをハードコーディングしないでください** 。 サード パーティは、シークレットを使用してリソースにアクセスできます。 [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates)を使用すると、アプリのシークレットをセキュリティで保護することができます。 アプリを保護する方法の実用的な例については、「[Azure Key Vaultを使用してサーバー アプリのシークレットを管理する」を参照してください](/learn/modules/manage-secrets-with-azure-key-vault/)。

1. 下のスクリプトをコピーし、お気に入りのテキスト エディターに貼り付けます。 **Get-Token.ps1** として保存します。 PowerShell ISE でコードをそのまま実行することもできますが、次のセクションでインシデントフェッチ スクリプトを使用する場合は再度実行する必要があるため、コードを保存する必要があります。

    このスクリプトはトークンを生成 *し、Latest-token.txt* という名前の作業フォルダーに保存します。

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

1. 受け取ったトークンを [JWT](https://jwt.ms) にコピーして貼り付けてデコードします。
1. *JWT* は *JSON Web トークン* を表します。 デコードされたトークンには、JSON 形式のアイテムまたは要求の数が含まれます。 デコードされたトークン内の *ロール* 要求に必要なアクセス許可が含まれていることを確認します。

    次の図では、アプリから取得したデコードされたトークンと、アクセス許可、および```AdvancedHunting.Read.All```アクセス許可を```Incidents.Read.All``````Incidents.ReadWrite.All```確認できます。

    :::image type="content" source="../../media/api-jwt-ms.png" alt-text="Microsoft 365 Defender ポータルの [デコードされたトークン] セクション" lightbox="../../media/api-jwt-ms.png":::

### <a name="get-a-list-of-recent-incidents"></a>最近のインシデントの一覧を取得する

次のスクリプトでは、 **Get-Token.ps1** を使用して API にアクセスします。 その後、過去 48 時間以内に最後に更新されたインシデントの一覧を取得し、リストを JSON ファイルとして保存します。

> [!IMPORTANT]
> このスクリプトは、Get-Token.ps1保存したのと同じフォルダー **に** 保存します。

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

これで完了です。 これで次の操作が正常に完了しました。

- アプリケーションを作成して登録しました。
- アラートを読み取るためのそのアプリケーションに対するアクセス許可を付与しました。
- API に接続されています。
- PowerShell スクリプトを使用して、過去 48 時間に更新されたインシデントを返しました。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md)
- [ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する](api-create-app-user-context.md)
- [Microsoft 365 Defender API へのマルチテナント パートナー アクセス権を持つアプリを作成する](api-partner-access.md)
- [Azure Key Vaultを使用してサーバー アプリのシークレットを管理する](/learn/modules/manage-secrets-with-azure-key-vault/)
- [OAuth 2.0 ユーザー サインインと API アクセスの承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)