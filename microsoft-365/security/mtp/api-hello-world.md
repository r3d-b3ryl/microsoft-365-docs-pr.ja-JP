---
title: Microsoft 365 Defender REST API の Hello World
description: アプリを作成し、トークンを使用して Microsoft 365 Defender Api にアクセスする方法について説明します。
keywords: アプリ、トークン、アクセス、aad、アプリ、アプリケーションの登録、powershell、スクリプト、グローバル管理者、アクセス許可
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844046"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Microsoft 365 Defender REST API の Hello World 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>簡単な PowerShell スクリプトを使用してインシデントを取得する

### <a name="how-long-it-takes-to-go-through-this-example"></a>この例では、どのくらいの時間がかかりますか?
次の2つの手順では、5分で完了します。
- アプリケーションの登録
- 使用例: 短い PowerShell スクリプトのコピー/貼り付けのみが必要です

### <a name="do-i-need-a-permission-to-connect"></a>接続するためのアクセス許可が必要ですか。
アプリケーション登録ステージでは、Azure Active Directory (Azure AD) テナントに **グローバル管理者** ロールが必要です。

### <a name="step-1---create-an-app-in-azure-active-directory"></a>手順 1-Azure Active Directory でアプリを作成する

1. **グローバル管理者** ユーザーと共に [Azure](https://portal.azure.com)にログオンします。

2. **Azure Active Directory**  >  **アプリ登録**  >  の **新しい登録** に移動します。 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. 登録フォームで、アプリケーションの名前を選択し、[ **登録** ] を選択します。

4. アプリケーションがエンドポイントの Microsoft Defender にアクセスして、それを **すべてのインシデントの読み取り** アクセス許可に割り当てることを許可します。

   - アプリケーションページで、[ **API Permissions** ] [組織が使用する  >  **アクセス許可**  >  **api** の追加 > **microsoft 365 defender** ] と入力し、[ **microsoft 365 defender** ] を選択します。

   >[!NOTE]
   >Microsoft 365 Defender は、元のリストには表示されません。 テキストボックスに名前を記述して、表示されることを確認する必要があります。

   ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)

   - [ **アプリケーションのアクセス許可** のインシデント] を選択します。  >  **すべて** > [ **アクセス許可の追加** ] を選択します。

   ![API アクセスと API 選択の画像](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >関連するアクセス許可を選択する必要があります。 

     例えば

     - 必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。

5. [ **管理者の同意を付与** する] を選択する

    - >[!NOTE]
      > アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **Grant 同意** ] を選択する必要があります。

    ![許可権限の画像](../../media/grant-consent.PNG)

6. アプリケーションにシークレットを追加します。

    - [ **証明書 & シークレット** ] を選択し、シークレットに説明を追加して、[ **追加** ] を選択します。

    >[!IMPORTANT]
    > [ **追加** ] を選択した後、 **生成されたシークレット値をコピー** します。 退出後に取得することはできません。

    ![アプリキーを作成する画像](../../media/webapp-create-key2.png)

7. アプリケーション ID とテナント ID を書き留めておきます。

   - アプリケーションページで、[ **概要** ] に移動し、次の内容をコピーします。

   ![作成されたアプリ id の画像](../../media/app-and-tenant-ids.png)


完成です！ アプリケーションが正常に登録されました。

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>手順 2-アプリを使用してトークンを取得し、このトークンを使用して API にアクセスします。

-   次のスクリプトを PowerShell ISE またはテキストエディターにコピーし、" **Get-Token.ps1** " として保存します。
-   このスクリプトを実行すると、トークンが生成され、" **Latest-token.txt** " という名前の作業フォルダーに保存されます。

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   正当性チェック:<br>
スクリプトを実行します。<br>
ブラウザーで、次のように移動します。 https://jwt.ms/ <br>
トークン (Latest-token.txt ファイルの内容) をコピーします。<br>
一番上のボックスに貼り付けます。<br>
「役割」セクションを参照してください。 役割を検索 ```Incidents.Read.All``` します。<br>
次の例は ```Incidents.Read.All``` 、 ```Incidents.ReadWrite.All``` およびアクセス許可を持つアプリからのものです ```AdvancedHunting.Read.All``` 。

![Image jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>インシデントを入手できます。

-   次のスクリプトでは **Get-Token.ps1** を使用して API にアクセスし、過去48時間以内に最終更新されたインシデントを取得します。
-   このスクリプトは、前のスクリプト **Get-Token.ps1** を保存したときと同じフォルダーに保存します。 
-   スクリプトと同じフォルダー内のデータを含む json ファイル。

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

すべて完了しました。 正常に完了したのは次のとおりです。
-   作成および登録され、アプリケーション
-   そのアプリケーションに対して通知を読み取るためのアクセス許可が付与されます。
-   API の接続
-   PowerShell スクリプトを使用して過去48時間以内に作成されたインシデントを返す



## <a name="related-topic"></a>関連トピック
- [Microsoft 365 Defender Api にアクセスする](api-access.md)
- [アプリケーションコンテキストを使用して Microsoft 365 Defender にアクセスする](api-create-app-web.md)
- [ユーザーコンテキストを使用して Microsoft 365 Defender にアクセスする](api-create-app-user-context.md)
