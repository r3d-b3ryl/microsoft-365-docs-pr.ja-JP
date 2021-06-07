---
title: ユーザーなしで Microsoft Defender for Endpoint にアクセスするアプリを作成する
ms.reviewer: ''
description: ユーザーなしで Microsoft Defender for Endpoint へのプログラムによるアクセスを取得する Web アプリを設計する方法について説明します。
keywords: apis, graph api, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度なハンティング, クエリ
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 4742a32fd899f41d4e7772c52415891cdd8895bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769523"
---
# <a name="create-an-app-to-access-microsoft-defender-for-endpoint-without-a-user"></a><span data-ttu-id="8fd3e-104">ユーザーなしで Microsoft Defender for Endpoint にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-104">Create an app to access Microsoft Defender for Endpoint without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8fd3e-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8fd3e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8fd3e-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="8fd3e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8fd3e-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="8fd3e-108">このページでは、ユーザーなしで Defender for Endpoint へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-108">This page describes how to create an application to get programmatic access to Defender for Endpoint without a user.</span></span> <span data-ttu-id="8fd3e-109">ユーザーに代わって Defender for Endpoint へのプログラムによるアクセスが必要な場合は、「ユーザー コンテキストでアクセスを取得する」 [を参照してください](exposed-apis-create-app-nativeapp.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-109">If you need programmatic access to Defender for Endpoint on behalf of a user, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span> <span data-ttu-id="8fd3e-110">必要なアクセス権が分からない場合は、「開始する」 [を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-110">If you are not sure which access you need, see [Get started](apis-intro.md).</span></span>

<span data-ttu-id="8fd3e-111">Microsoft Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-111">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8fd3e-112">これらの API は、Defender for Endpoint の機能に基づいてワークフローを自動化し、革新するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-112">Those APIs will help you automate work flows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="8fd3e-113">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-113">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8fd3e-114">詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-114">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8fd3e-115">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-115">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="8fd3e-116">アプリケーション (azure Azure Active Directory) AD作成します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-116">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8fd3e-117">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-117">Get an access token using this application.</span></span>
- <span data-ttu-id="8fd3e-118">トークンを使用して Defender for Endpoint API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-118">Use the token to access Defender for Endpoint API.</span></span>

<span data-ttu-id="8fd3e-119">この記事では、Azure AD アプリケーションを作成し、エンドポイント用 Microsoft Defender へのアクセス トークンを取得し、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-119">This article explains how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="8fd3e-120">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-120">Create an app</span></span>

1. <span data-ttu-id="8fd3e-121">グローバル管理者の [役割を](https://portal.azure.com) 持つユーザーを使用して **Azure にログオン** します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-121">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8fd3e-122">[アプリの **登録Azure Active Directory**  >  **新しい登録]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![アプリケーション登録Microsoft Azureナビゲーションのイメージ](images/atp-azure-new-app2.png)

3. <span data-ttu-id="8fd3e-124">登録フォームで、アプリケーションの名前を選択し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-124">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="8fd3e-125">アプリが Defender for Endpoint にアクセスし、[すべてのアラートの読み取り **]** アクセス許可を割り当てるには、アプリケーション ページで **、[API** アクセス許可の追加] アクセス許可 API を選択して、組織で > を使用し  >    >  **、「WindowsDefenderATP」と入力し、[WindowsDefenderATP]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-125">To enable your app to access Defender for Endpoint and assign it **'Read all alerts'** permission, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **WindowsDefenderATP**, and then select **WindowsDefenderATP**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8fd3e-126">*WindowsDefenderATP* は元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-126">*WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="8fd3e-127">テキスト ボックスに名前を書き始め、表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-127">Start writing its name in the text box to see it appear.</span></span>

   ![アクセス許可の追加](images/add-permission.png)

   - <span data-ttu-id="8fd3e-129">[**アプリケーションのアクセス許可**  >  **Alert.Read.All] を選択** し、[アクセス許可の **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-129">Select **Application permissions** > **Alert.Read.All**, and then select **Add permissions**.</span></span>

   ![アプリのアクセス許可](images/application-permissions.png)

     <span data-ttu-id="8fd3e-131">関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-131">You need to select the relevant permissions.</span></span> <span data-ttu-id="8fd3e-132">'すべてのアラートの読み取り' は、一例にすすみです。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-132">'Read All Alerts' is only an example.</span></span> <span data-ttu-id="8fd3e-133">例えば：</span><span class="sxs-lookup"><span data-stu-id="8fd3e-133">For instance:</span></span>

     - <span data-ttu-id="8fd3e-134">高度 [なクエリを実行するには、[](run-advanced-query-api.md)高度なクエリの実行] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-134">To [run advanced queries](run-advanced-query-api.md), select the 'Run advanced queries' permission.</span></span>
     - <span data-ttu-id="8fd3e-135">デバイス [を分離するには、[](isolate-machine.md)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-135">To [isolate a device](isolate-machine.md), select the 'Isolate machine' permission.</span></span>
     - <span data-ttu-id="8fd3e-136">必要なアクセス許可を確認するには、呼び出す API の [アクセス許可] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-136">To determine which permission you need, look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="8fd3e-137">[同意 **の付与] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-137">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8fd3e-138">アクセス許可を追加する度に、[新しいアクセス許可 **を** 有効にするための同意の付与] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-138">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![アクセス許可を付与する](images/grant-consent.png)

6. <span data-ttu-id="8fd3e-140">アプリケーションにシークレットを追加するには、[証明書] &シークレットに説明を追加し、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-140">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8fd3e-141">[追加] を **選択した後**、生成 **されたシークレット値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-141">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="8fd3e-142">この値は、退出後に取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-142">You won't be able to retrieve this value after you leave.</span></span>

    ![アプリ キーの作成のイメージ](images/webapp-create-key2.png)

7. <span data-ttu-id="8fd3e-144">アプリケーション ID とテナント ID を書き出します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-144">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="8fd3e-145">アプリケーション ページで、[概要] に移動 **し** 、次をコピーします。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-145">On your application page, go to **Overview** and copy the following.</span></span>

   ![作成されたアプリ ID のイメージ](images/app-and-tenant-ids.png)

8. <span data-ttu-id="8fd3e-147">**エンドポイント パートナー向け Microsoft Defender の場合のみ**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-147">**For Microsoft Defender for Endpoint Partners only**.</span></span> <span data-ttu-id="8fd3e-148">アプリをマルチテナントに設定します (同意後、すべてのテナントで利用できます)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-148">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="8fd3e-149">これは、 **サード パーティ** 製アプリ (たとえば、複数の顧客のテナントで実行することを意図したアプリを作成する場合) に必要です。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-149">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="8fd3e-150">これは、 **テナント** でのみ実行するサービスを作成する場合は必須ではありません (たとえば、独自のデータのみを操作する独自の用途用のアプリケーションを作成する場合など)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-150">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="8fd3e-151">アプリをマルチテナントに設定するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-151">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="8fd3e-152">[認証] **に移動** し、リダイレクト `https://portal.azure.com` URI **として追加します**。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-152">Go to **Authentication**, and add `https://portal.azure.com` as the **Redirect URI**.</span></span>

    - <span data-ttu-id="8fd3e-153">ページの下部にある [サポートされているアカウントの種類] で、マルチテナント アプリの組織ディレクトリ アプリケーションの同意にある [アカウント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-153">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="8fd3e-154">アプリケーションを使用する各テナントでアプリケーションを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-154">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="8fd3e-155">これは、アプリケーションが顧客に代わって Defender for Endpoint をやり取りする理由です。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-155">This is because your application interacts Defender for Endpoint on behalf of your customer.</span></span>

    <span data-ttu-id="8fd3e-156">ユーザー (またはサードパーティ アプリを作成している場合は顧客) は、同意リンクを選択してアプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-156">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="8fd3e-157">同意は、Active Directory で管理者権限を持つユーザーに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-157">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="8fd3e-158">同意リンクは次のように形成されます。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-158">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="8fd3e-159">00000000-00000-00000-00000-000000000000 がアプリケーション ID に置き換えられる場合。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-159">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="8fd3e-160">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="8fd3e-160">**Done!**</span></span> <span data-ttu-id="8fd3e-161">アプリケーションの登録に成功しました!</span><span class="sxs-lookup"><span data-stu-id="8fd3e-161">You have successfully registered an application!</span></span> <span data-ttu-id="8fd3e-162">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-162">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="8fd3e-163">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-163">Get an access token</span></span>

<span data-ttu-id="8fd3e-164">Azure AD トークンの詳細については [、「Azure AD」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-164">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="8fd3e-165">PowerShell を使う</span><span class="sxs-lookup"><span data-stu-id="8fd3e-165">Use PowerShell</span></span>

```powershell
# This script acquires the App Context Token and stores it in the variable $token for later use in the script.
# Paste your Tenant ID, App ID, and App Secret (App key) into the indicated quotes below.

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

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
```

### <a name="use-c"></a><span data-ttu-id="8fd3e-166">次のC#使用します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-166">Use C#:</span></span>

<span data-ttu-id="8fd3e-167">次のコードは、Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 NuGetでテストされました。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-167">The following code was tested with NuGet Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="8fd3e-168">新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-168">Create a new console application.</span></span>
1. <span data-ttu-id="8fd3e-169">[Microsoft.IdentityModel.clients.ActiveDirectory をインストールNuGet Microsoft.IdentityModel.Clients.ActiveDirectory をインストールします](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-169">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="8fd3e-170">次の項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-170">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="8fd3e-171">次のコードをアプリにコピーして貼り付けます (3 つの変数を更新することを忘れないでください ```tenantId, appId, appSecret``` )。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-171">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.microsoftonline.com";
    const string wdatpResourceId = "https://api.securitycenter.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="8fd3e-172">Python を使用する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-172">Use Python</span></span>

<span data-ttu-id="8fd3e-173">「Python [を使用してトークンを取得する」を参照してください](run-advanced-query-sample-python.md#get-token)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-173">See [Get token using Python](run-advanced-query-sample-python.md#get-token).</span></span>

### <a name="use-curl"></a><span data-ttu-id="8fd3e-174">Curl を使用する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-174">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="8fd3e-175">次の手順では、コンピューターにWindowsの Curl が既にインストールされていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-175">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="8fd3e-176">コマンド プロンプトを開き、Azure CLIENT_ID ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-176">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="8fd3e-177">Azure CLIENT_SECRETシークレットに設定します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-177">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="8fd3e-178">アプリTENANT_ID Defender for Endpoint にアクセスする顧客の Azure テナント ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-178">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Defender for Endpoint.</span></span>
1. <span data-ttu-id="8fd3e-179">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-179">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="8fd3e-180">次の形式で回答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-180">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="8fd3e-181">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-181">Validate the token</span></span>

<span data-ttu-id="8fd3e-182">正しいトークンを取得していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-182">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="8fd3e-183">前の手順で取得したトークンを [JWT](https://jwt.ms) にコピーして貼り付け、デコードします。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-183">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="8fd3e-184">目的のアクセス許可を持つ 'roles' クレームを取得する方法を検証する</span><span class="sxs-lookup"><span data-stu-id="8fd3e-184">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="8fd3e-185">次の図では、エンドポイントのすべての Microsoft Defender の役割に対するアクセス許可を持つ、アプリから取得されたデコードされたトークンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-185">In the following image, you can see a decoded token acquired from an app with permissions to all of  Microsoft Defender for Endpoint's roles:</span></span>

![トークン検証のイメージ](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="8fd3e-187">トークンを使用して Microsoft Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="8fd3e-187">Use the token to access Microsoft Defender for Endpoint API</span></span>

1. <span data-ttu-id="8fd3e-188">使用する API を選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-188">Choose the API you want to use.</span></span> <span data-ttu-id="8fd3e-189">詳細については [、「Supported Defender for Endpoint API」を参照してください](exposed-apis-list.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-189">For more information, see [Supported Defender for Endpoint APIs](exposed-apis-list.md).</span></span>
1. <span data-ttu-id="8fd3e-190">送信する http 要求の承認ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-190">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>
1. <span data-ttu-id="8fd3e-191">トークンの有効期限は 1 時間です。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-191">The expiration time of the token is one hour.</span></span> <span data-ttu-id="8fd3e-192">同じトークンで複数の要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-192">You can send more than one request with the same token.</span></span>

<span data-ttu-id="8fd3e-193">次に、要求を送信してアラートの一覧を取得する例を次に **示** C#。</span><span class="sxs-lookup"><span data-stu-id="8fd3e-193">The following is an example of sending a request to get a list of alerts **using C#**:</span></span> 
```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="see-also"></a><span data-ttu-id="8fd3e-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fd3e-194">See also</span></span>
- [<span data-ttu-id="8fd3e-195">サポート対象 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="8fd3e-195">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="8fd3e-196">ユーザーに代わって Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="8fd3e-196">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
