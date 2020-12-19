---
title: Microsoft 365 Defender REST API の Hello World
description: アプリを作成し、トークンを使用して Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: アプリ, トークン, アクセス, aad, アプリ, アプリケーションの登録, powershell, スクリプト, グローバル管理者, アクセス許可, Microsoft 365 Defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719312"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="cf45d-104">Microsoft 365 Defender REST API の Hello World</span><span class="sxs-lookup"><span data-stu-id="cf45d-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cf45d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cf45d-105">**Applies to:**</span></span>

- <span data-ttu-id="cf45d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf45d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf45d-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="cf45d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cf45d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="cf45d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="cf45d-109">単純な PowerShell スクリプトを使用してインシデントを取得する</span><span class="sxs-lookup"><span data-stu-id="cf45d-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="cf45d-110">このプロジェクトを完了するには、5 ~ 10 分かかります。</span><span class="sxs-lookup"><span data-stu-id="cf45d-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="cf45d-111">この時間の見積もりには、アプリケーションの登録と、PowerShell サンプル スクリプトからのコードの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="cf45d-112">Azure Active Directory にアプリを登録する</span><span class="sxs-lookup"><span data-stu-id="cf45d-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="cf45d-113">グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="cf45d-114">Azure **Active Directory アプリの**  >  **登録の新規登録**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="cf45d-116">登録フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="cf45d-117">リダイレクト URI の選択はオプションです。</span><span class="sxs-lookup"><span data-stu-id="cf45d-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="cf45d-118">この例を完了するために必要な手順は不要です。</span><span class="sxs-lookup"><span data-stu-id="cf45d-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="cf45d-119">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用し  >    >  **、「Microsoft Threat Protection」と** 入力して **、Microsoft Threat Protection を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="cf45d-120">これで、アプリは Microsoft 365 Defender にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="cf45d-121">*Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="cf45d-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="cf45d-122">テキスト ボックスが表示されるのを確認するには、テキスト ボックスに名前の書き込みを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf45d-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="cf45d-123">![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="cf45d-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="cf45d-124">アプリケーションの **アクセス許可**  >  **Incident.Read.All を** 選択し、[アクセス許可 **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![API アクセスと API の選択の画像](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="cf45d-126">[管理者 **の同意を付与する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="cf45d-127">アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf45d-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![アクセス許可の付与の画像](../../media/grant-consent.PNG)

6. <span data-ttu-id="cf45d-129">アプリケーションにシークレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-129">Add a secret to the application.</span></span> <span data-ttu-id="cf45d-130">Select **Certificates & secrets,** add a description to the secret, then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="cf45d-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="cf45d-131">[追加] を **選択した後**、生成 **されたシークレットの値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="cf45d-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="cf45d-132">退出後にシークレット値を取得できない。</span><span class="sxs-lookup"><span data-stu-id="cf45d-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![アプリ キーの作成の画像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="cf45d-134">アプリケーション ID とテナント ID を安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="cf45d-135">アプリケーション ページの [概要] **に** 一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-135">They're listed under **Overview** on your application page.</span></span>

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="cf45d-137">アプリを使用してトークンを取得し、そのトークンを使用して API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="cf45d-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="cf45d-138">Azure Active Directory トークンについて詳しくは、Azure Active Directory のチュートリアル [AD覧ください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="cf45d-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf45d-139">このデモ アプリの例では、テストの目的で秘密の値を貼り付ける必要があります。ただし、実稼働環境で実行されているアプリケーションにシークレットをハードコードし込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf45d-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="cf45d-140">サード パーティは、シークレットを使用してリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="cf45d-141">[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)を使用して、アプリのシークレットをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-141">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="cf45d-142">アプリを保護する方法の実用的な例については、「Azure Key Vault を使用してサーバー アプリのシークレットを管理する」 [を参照してください](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="cf45d-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="cf45d-143">以下のスクリプトをコピーし、お気に入りのテキスト エディターに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="cf45d-144">名前を付 **けてGet-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="cf45d-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="cf45d-145">PowerShell ISE でコードを一緒に実行することもできますが、保存する必要があります。これは、次のセクションでインシデント フェッチ スクリプトを使用するときに再度実行する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="cf45d-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="cf45d-146">このスクリプトはトークンを生成し、そのトークンを作業フォルダーの名前の下に保存 *Latest-token.txt。*</span><span class="sxs-lookup"><span data-stu-id="cf45d-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

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

#### <a name="validate-the-token"></a><span data-ttu-id="cf45d-147">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="cf45d-147">Validate the token</span></span>

1. <span data-ttu-id="cf45d-148">受け取ったトークンをコピーして JWT に貼 [り付](https://jwt.ms) け、デコードします。</span><span class="sxs-lookup"><span data-stu-id="cf45d-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="cf45d-149">*JWT は* *JSON Web トークンを表します*。</span><span class="sxs-lookup"><span data-stu-id="cf45d-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="cf45d-150">デコードされたトークンには、JSON 形式のアイテムまたはクレームが多数含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="cf45d-151">デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf45d-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="cf45d-152">次の図では、アプリから取得したデコードされたトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 確認できます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![画像jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="cf45d-154">最近のインシデントの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="cf45d-154">Get a list of recent incidents</span></span>

<span data-ttu-id="cf45d-155">以下のスクリプトでは、API **へのアクセスGet-Token.ps1** を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="cf45d-156">次に、過去 48 時間以内に最後に更新されたインシデントの一覧を取得し、そのリストを JSON ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf45d-157">このスクリプトを保存したフォルダーと同じフォルダーに保存 **Get-Token.ps1。**</span><span class="sxs-lookup"><span data-stu-id="cf45d-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

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

<span data-ttu-id="cf45d-158">完了です。</span><span class="sxs-lookup"><span data-stu-id="cf45d-158">You're all done!</span></span> <span data-ttu-id="cf45d-159">正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="cf45d-159">You've successfully:</span></span>

- <span data-ttu-id="cf45d-160">アプリケーションを作成して登録します。</span><span class="sxs-lookup"><span data-stu-id="cf45d-160">Created and registered an application.</span></span>
- <span data-ttu-id="cf45d-161">そのアプリケーションに通知を読み取るアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="cf45d-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="cf45d-162">API に接続されています。</span><span class="sxs-lookup"><span data-stu-id="cf45d-162">Connected to the API.</span></span>
- <span data-ttu-id="cf45d-163">PowerShell スクリプトを使用して、過去 48 時間以内に更新されたインシデントを返しました。</span><span class="sxs-lookup"><span data-stu-id="cf45d-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cf45d-164">関連記事</span><span class="sxs-lookup"><span data-stu-id="cf45d-164">Related articles</span></span>

- [<span data-ttu-id="cf45d-165">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="cf45d-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cf45d-166">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="cf45d-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cf45d-167">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cf45d-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="cf45d-168">ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cf45d-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="cf45d-169">マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cf45d-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="cf45d-170">Azure Key Vault を使用してサーバー アプリのシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="cf45d-170">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="cf45d-171">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="cf45d-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
