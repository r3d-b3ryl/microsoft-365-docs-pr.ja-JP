---
title: Hello World for Microsoft Defender for Endpoint API
ms.reviewer: ''
description: Microsoft Defender for Endpoint (Microsoft Defender ATP) API に対するプラクティス 'Hello world' スタイルの API 呼び出しを作成します。
keywords: apis、サポートされている API、高度な検索、クエリ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3b076d0fa6e01be2a810e8fa810cc3e32955388e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199654"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="ca529-104">エンドポイント API 用 Microsoft Defender - Hello World</span><span class="sxs-lookup"><span data-stu-id="ca529-104">Microsoft Defender for Endpoint API - Hello World</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ca529-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ca529-105">**Applies to:**</span></span> 
- [<span data-ttu-id="ca529-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca529-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="ca529-107">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ca529-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca529-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ca529-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="ca529-109">簡単な PowerShell スクリプトを使用してアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="ca529-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="ca529-110">この例ではどのくらいの時間が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ca529-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="ca529-111">2 つの手順で 5 分しかかからな</span><span class="sxs-lookup"><span data-stu-id="ca529-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="ca529-112">アプリケーションの登録</span><span class="sxs-lookup"><span data-stu-id="ca529-112">Application registration</span></span>
- <span data-ttu-id="ca529-113">使用例: 短い PowerShell スクリプトのコピー/貼り付けだけが必要</span><span class="sxs-lookup"><span data-stu-id="ca529-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="ca529-114">接続するアクセス許可が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="ca529-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="ca529-115">アプリケーション登録ステージでは、Azure Active Directory  (Azure Active Directory) テナントにグローバル管理者AD必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca529-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="ca529-116">手順 1 - Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="ca529-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="ca529-117">グローバル管理者ユーザー [を使用](https://portal.azure.com) して Azure **にログオン** します。</span><span class="sxs-lookup"><span data-stu-id="ca529-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="ca529-118">**[Azure Active Directory アプリの**  >  **登録] [新規登録**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca529-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](images/atp-azure-new-app2.png)

3. <span data-ttu-id="ca529-120">登録フォームで、アプリケーションの名前を選択し、[登録] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca529-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="ca529-121">アプリケーションが Defender for Endpoint にアクセスし、"すべてのアラートの読み取り" アクセス許可 **を割り当てるのを許可** します。</span><span class="sxs-lookup"><span data-stu-id="ca529-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="ca529-122">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API をクリックします。組織で  >    >  WindowsDefenderATP >を使用し **、[WindowsDefenderATP] をクリックします**。 </span><span class="sxs-lookup"><span data-stu-id="ca529-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="ca529-123">**注**: WindowsDefenderATP は元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ca529-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="ca529-124">テキスト ボックスに名前を書き込み始め、表示を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca529-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセスと API 選択のイメージ1](images/add-permission.png)

   - <span data-ttu-id="ca529-126">[**アプリケーションのアクセス許可**  >  **] Alert.Read.All >** [アクセス許可の追加 **] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="ca529-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![API アクセスと API 選択のイメージ2](images/application-permissions.png)

   <span data-ttu-id="ca529-128">**重要な注意**: 関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca529-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="ca529-129">'すべてのアラートの読み取り' は、一例にすら限定されます。</span><span class="sxs-lookup"><span data-stu-id="ca529-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="ca529-130">例えば</span><span class="sxs-lookup"><span data-stu-id="ca529-130">For instance,</span></span>

     - <span data-ttu-id="ca529-131">高度 [なクエリを実行するには、[](run-advanced-query-api.md)高度なクエリの実行] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca529-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="ca529-132">コンピューター [を分離するには、[](isolate-machine.md)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca529-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="ca529-133">必要なアクセス許可を決定するには、呼び出す API の **[** アクセス許可] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca529-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="ca529-134">[同意 **の付与] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="ca529-134">Click **Grant consent**</span></span>

    - <span data-ttu-id="ca529-135">**注**: アクセス許可を追加する度に、[新しい **アクセス許可を** 有効にするための同意の付与] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca529-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![アクセス許可の付与のイメージ](images/grant-consent.png)

6. <span data-ttu-id="ca529-137">アプリケーションにシークレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca529-137">Add a secret to the application.</span></span>

    - <span data-ttu-id="ca529-138">[ **証明書とシークレット&クリックし、** シークレットに説明を追加し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca529-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="ca529-139">**重要**: [追加] をクリックした後 **、生成されたシークレット値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="ca529-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="ca529-140">退出後に取得できない!</span><span class="sxs-lookup"><span data-stu-id="ca529-140">You won't be able to retrieve after you leave!</span></span>

    ![アプリ キーの作成のイメージ](images/webapp-create-key2.png)

7. <span data-ttu-id="ca529-142">アプリケーション ID とテナント ID を書き出します。</span><span class="sxs-lookup"><span data-stu-id="ca529-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="ca529-143">アプリケーション ページで、[概要] に移動 **し** 、次をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ca529-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![作成されたアプリ ID のイメージ](images/app-and-tenant-ids.png)


<span data-ttu-id="ca529-145">完成です！</span><span class="sxs-lookup"><span data-stu-id="ca529-145">Done!</span></span> <span data-ttu-id="ca529-146">アプリケーションの登録に成功しました!</span><span class="sxs-lookup"><span data-stu-id="ca529-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="ca529-147">手順 2 - アプリを使用してトークンを取得し、このトークンを使用して API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ca529-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="ca529-148">以下のスクリプトを PowerShell ISE またはテキスト エディターにコピーし、"Get-Token.ps1"**として保存** します。</span><span class="sxs-lookup"><span data-stu-id="ca529-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="ca529-149">このスクリプトを実行すると、トークンが生成され、作業フォルダーに ""Latest-token.txt"**という名前で保存** されます。</span><span class="sxs-lookup"><span data-stu-id="ca529-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
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

-   <span data-ttu-id="ca529-150">サニティ チェック:</span><span class="sxs-lookup"><span data-stu-id="ca529-150">Sanity Check:</span></span><br>
<span data-ttu-id="ca529-151">スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca529-151">Run the script.</span></span><br>
<span data-ttu-id="ca529-152">ブラウザーで次の場所に移動します。 https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="ca529-152">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="ca529-153">トークン (ファイルのコンテンツ) をLatest-token.txtします。</span><span class="sxs-lookup"><span data-stu-id="ca529-153">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="ca529-154">上部ボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ca529-154">Paste in the top box.</span></span><br>
<span data-ttu-id="ca529-155">[役割] セクションを探します。</span><span class="sxs-lookup"><span data-stu-id="ca529-155">Look for the "roles" section.</span></span> <span data-ttu-id="ca529-156">Alert.Read.All ロールを検索します。</span><span class="sxs-lookup"><span data-stu-id="ca529-156">Find the Alert.Read.All role.</span></span>

![イメージ jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="ca529-158">アラートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="ca529-158">Lets get the Alerts!</span></span>

-   <span data-ttu-id="ca529-159">以下のスクリプトでは、API **Get-Token.ps1** を使用して、過去 48 時間のアラートを取得します。</span><span class="sxs-lookup"><span data-stu-id="ca529-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
-   <span data-ttu-id="ca529-160">前のスクリプトを保存したのと同じフォルダーにこのスクリプト **を保存** Get-Token.ps1。</span><span class="sxs-lookup"><span data-stu-id="ca529-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="ca529-161">スクリプトは、スクリプトと同じフォルダー内のデータを含む 2 つのファイル (json と csv) を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca529-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

```
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

<span data-ttu-id="ca529-162">完了です!</span><span class="sxs-lookup"><span data-stu-id="ca529-162">You’re all done!</span></span> <span data-ttu-id="ca529-163">成功したのは次の場合です。</span><span class="sxs-lookup"><span data-stu-id="ca529-163">You have just successfully:</span></span>
-   <span data-ttu-id="ca529-164">作成および登録およびアプリケーション</span><span class="sxs-lookup"><span data-stu-id="ca529-164">Created and registered and application</span></span>
-   <span data-ttu-id="ca529-165">そのアプリケーションに通知を読み取るアクセス許可が付与されている</span><span class="sxs-lookup"><span data-stu-id="ca529-165">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="ca529-166">API の接続</span><span class="sxs-lookup"><span data-stu-id="ca529-166">Connected the API</span></span>
-   <span data-ttu-id="ca529-167">PowerShell スクリプトを使用して、過去 48 時間に作成されたアラートを返す</span><span class="sxs-lookup"><span data-stu-id="ca529-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="ca529-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ca529-168">Related topic</span></span>
- [<span data-ttu-id="ca529-169">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ca529-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="ca529-170">アプリケーション コンテキストを使用して Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ca529-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="ca529-171">ユーザー コンテキストを使用して Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ca529-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
