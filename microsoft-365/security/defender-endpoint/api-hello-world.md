---
title: Microsoft Defender for Endpoint API のHello World
ms.reviewer: ''
description: Microsoft Defender for Endpoint API に対する練習 'Hello world' スタイルの API 呼び出しを作成します。
keywords: apis, サポートされている API, 高度な捜索, クエリ, microsoft defender atp, エンドポイント用 Microsoft Defender
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 2805736c3d612716f3b99ba0f97fc74a0070bc68
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328038"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>Microsoft Defender for Endpoint API - Hello World

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>単純な PowerShell スクリプトを使用してアラートを取得する

### <a name="how-long-it-takes-to-go-through-this-example"></a>この例を実行するのにどのくらいの時間がかかりますか?

次の 2 つの手順で 5 分しか実行されません。

- アプリケーションの登録
- 使用例: 短い PowerShell スクリプトのコピー/貼り付けのみが必要です

### <a name="do-i-need-a-permission-to-connect"></a>接続にアクセス許可が必要ですか?

アプリケーション登録ステージでは、Azure Active Directory (Azure AD) テナントに **グローバル管理者** ロールが必要です。

### <a name="step-1---create-an-app-in-azure-active-directory"></a>手順 1 - Azure Active Directory でアプリを作成する

1. **グローバル管理者** ユーザーを使用して [Azure](https://portal.azure.com) にログオンします。

2. **Azure Active Directory** \> **アプリの登録** \> **新しい登録** に移動します。

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Azure Active Directory ポータルの [管理] ウィンドウの下にある [アプリの登録] オプション"  lightbox="images/atp-azure-new-app2.png":::

3. 登録フォームで、アプリケーションの名前を選択し、[ **登録**] をクリックします。

4. アプリケーションが Defender for Endpoint にアクセスし、 **"すべてのアラートの読み取り"** アクセス許可を割り当てることを許可します。

   - アプリケーション ページで、組織が **WindowsDefenderATP** の種類>使用する **API アクセス許可** \> \>の **追加** **API** をクリックし、**WindowsDefenderATP** をクリックします。

     > [!NOTE]
     > WindowsDefenderATP は元の一覧に表示されません。 テキスト ボックスに名前を書き込み始めて、その名前が表示されるのを確認する必要があります。

     :::image type="content" source="images/add-permission.png" alt-text="Azure Active Directory ポータルの [管理] ウィンドウの [API アクセス許可] オプション" lightbox="images/add-permission.png":::

   - [ **アプリケーションのアクセス許可** \> **のアラート].Read.All** > [ **アクセス許可の追加**] をクリックします。

     :::image type="content" source="images/application-permissions.png" alt-text="[要求 API のアクセス許可] ページの [アクセス許可の種類と設定] ウィンドウ" lightbox="images/application-permissions.png":::

     > [!IMPORTANT]
     > 関連するアクセス許可を選択する必要があります。 "すべてのアラートの読み取り" は例に過ぎません。

     例:

     - [高度なクエリを実行](run-advanced-query-api.md)するには、[高度なクエリの実行] アクセス許可を選択します。
     - [コンピューターを分離するには、[コンピューターの](isolate-machine.md)分離] アクセス許可を選択します。
     - 必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを参照してください。

5. [ **同意の付与]** をクリックします。

   > [!NOTE]
   > アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意の付与** ] をクリックする必要があります。

   :::image type="content" source="images/grant-consent.png" alt-text="Azure Active Directory ポータルのアクセス許可の同意オプション" lightbox="images/grant-consent.png":::

6. アプリケーションにシークレットを追加します。

    [ **証明書&シークレット**] をクリックし、シークレットに説明を追加して、[ **追加**] をクリックします。

    > [!IMPORTANT]
    > [追加] をクリックした後、 **生成されたシークレット値をコピーします**。 退出後は取得できません。

    :::image type="content" source="images/webapp-create-key2.png" alt-text="Azure Active Directory ポータルの [管理] ウィンドウの [証明書&シークレット] メニュー項目" lightbox="images/webapp-create-key2.png":::

7. アプリケーション ID とテナント ID を書き留めます。

   アプリケーション ページで、[ **概要]** に移動し、次の内容をコピーします。

   :::image type="content" source="images/app-and-tenant-ids.png" alt-text="Azure Active Directory ポータルの [概要] メニュー項目の下にあるアプリケーションの詳細ウィンドウ" lightbox="images/app-and-tenant-ids.png":::

完了! アプリケーションが正常に登録されました。

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>手順 2 - アプリを使用してトークンを取得し、このトークンを使用して API にアクセスします。

- 次のスクリプトを PowerShell ISE またはテキスト エディターにコピーし、 **Get-Token.ps1** として保存します。
- このスクリプトを実行すると、トークンが生成され、 **Latest-token.txt** という名前で作業フォルダーに保存されます。

   ```powershell
   # That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
   # Paste below your Tenant ID, App ID and App Secret (App key).

   $tenantId = '' ### Paste your tenant ID here
   $appId = '' ### Paste your Application ID here
   $appSecret = '' ### Paste your Application secret here

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

- サニティ チェック:
  - スクリプトを実行します。
  - ブラウザーで次 <https://jwt.ms/>の手順に進みます。
  - トークン (Latest-token.txt ファイルの内容) をコピーします。
  - 上部のボックスに貼り付けます。
  - [ロール] セクションを探します。 _Alert.Read.All_ ロールを見つけます。

  :::image type="content" source="images/api-jwt-ms.png" alt-text="jwt.ms の [デコードされたトークン] ウィンドウ" lightbox="images/api-jwt-ms.png":::

### <a name="lets-get-the-alerts"></a>アラートを取得しましょう。

- 次のスクリプトでは、 **Get-Token.ps1** を使用して API にアクセスし、過去 48 時間のアラートを取得します。
- このスクリプトは、前のスクリプト **Get-Token.ps1** を保存したのと同じフォルダーに保存します。
- スクリプトは、スクリプトと同じフォルダーにデータを含む 2 つのファイル (json と csv) を作成します。

  ```powershell
  # Returns Alerts created in the past 48 hours.

  $token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

  # Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
  $dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

  # The URL contains the type of query and the time filter we create above
  # Read more about other query options and filters at   Https://TBD- add the documentation link
  $url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

  # Set the WebRequest headers
  $headers = @{
      'Content-Type' = 'application/json'
      Accept = 'application/json'
      Authorization = "Bearer $token"
  }

  # Send the webrequest and get the results.
  $response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

  # Extract the alerts from the results.
  $alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

  # Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
  $dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

  # Save the result as json and as csv
  $outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"
  $outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

  Out-File -FilePath $outputJsonPath -InputObject $alerts
  ($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation
  ```

これで完了です。 次の操作に成功しました。

- 作成と登録とアプリケーション
- そのアプリケーションにアラートを読み取るためのアクセス許可を付与しました
- API を接続しました
- PowerShell スクリプトを使用して、過去 48 時間に作成されたアラートを返しました

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [アプリケーション コンテキストを使用してMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-webapp.md)
- [ユーザー コンテキストを使用してMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-nativeapp.md)
