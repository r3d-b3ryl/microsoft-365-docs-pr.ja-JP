---
title: ユーザーなしで Microsoft Defender for Endpoint にアクセスするアプリケーションを作成する
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
ms.technology: mde
ms.openlocfilehash: bc58241be69a1d8e1a78abc583b2c87dbef9cfa7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199404"
---
# <a name="partner-access-through-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="05689-104">Microsoft Defender for Endpoint API を介したパートナー アクセス</span><span class="sxs-lookup"><span data-stu-id="05689-104">Partner access through Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="05689-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="05689-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="05689-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="05689-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05689-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="05689-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="05689-108">このページでは、Azure Active Directory (Azure AD) アプリケーションを作成して、お客様に代わって Microsoft Defender for Endpoint へのプログラムによるアクセスを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05689-108">This page describes how to create an Azure Active Directory (Azure AD) application to get programmatic access to Microsoft Defender for Endpoint on behalf of your customers.</span></span>


<span data-ttu-id="05689-109">Microsoft Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="05689-109">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="05689-110">これらの API は、Microsoft Defender for Endpoint の機能に基づいてワークフローを自動化し、革新するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="05689-110">Those APIs will help you automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="05689-111">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="05689-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="05689-112">詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="05689-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="05689-113">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05689-113">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="05689-114">マルチテナント **Azure AD** 作成します。</span><span class="sxs-lookup"><span data-stu-id="05689-114">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="05689-115">アプリケーションが必要とする Defender for Endpoint リソースにアクセスするために、お客様の管理者によって承認 (同意) を受け取る。</span><span class="sxs-lookup"><span data-stu-id="05689-115">Get authorized(consent) by your customer administrator for your application to access Defender for Endpoint resources it needs.</span></span>
- <span data-ttu-id="05689-116">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="05689-116">Get an access token using this application.</span></span>
- <span data-ttu-id="05689-117">トークンを使用して、Microsoft Defender for Endpoint API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="05689-117">Use the token to access Microsoft Defender for Endpoint API.</span></span>

<span data-ttu-id="05689-118">次の手順では、Azure AD アプリケーションを作成し、Microsoft Defender for Endpoint へのアクセス トークンを取得し、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05689-118">The following steps will guide you how to create an Azure AD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="05689-119">マルチテナント アプリの作成</span><span class="sxs-lookup"><span data-stu-id="05689-119">Create the multi-tenant app</span></span>

1. <span data-ttu-id="05689-120">グローバル管理者の役割 [を持つユーザーを](https://portal.azure.com) 使用して Azure **テナントにサインイン** します。</span><span class="sxs-lookup"><span data-stu-id="05689-120">Sign in to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="05689-121">**[Azure Active Directory アプリの**  >  **登録] [新規登録**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="05689-121">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](images/atp-azure-new-app2.png)

3. <span data-ttu-id="05689-123">登録フォームで次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="05689-123">In the registration form:</span></span>

    - <span data-ttu-id="05689-124">アプリケーションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="05689-124">Choose a name for your application.</span></span>

    - <span data-ttu-id="05689-125">サポートされているアカウントの種類 - 任意の組織ディレクトリ内のアカウント。</span><span class="sxs-lookup"><span data-stu-id="05689-125">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="05689-126">リダイレクト URI - タイプ: Web、URI: https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="05689-126">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Microsoft Azure パートナー アプリケーション登録のイメージ](images/atp-api-new-app-partner.png)


4. <span data-ttu-id="05689-128">アプリケーションが Microsoft Defender for Endpoint にアクセスし、統合を完了するために必要な最小限のアクセス許可セットで割り当て許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="05689-128">Allow your Application to access Microsoft Defender for Endpoint and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="05689-129">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択します。組織で  >    >  WindowsDefenderATP >を使用し **、WindowsDefenderATP** で選択します。 </span><span class="sxs-lookup"><span data-stu-id="05689-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="05689-130">**注**: *WindowsDefenderATP* は元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="05689-130">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="05689-131">テキスト ボックスに名前を書き始め、表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="05689-131">Start writing its name in the text box to see it appear.</span></span>

   ![アクセス許可の追加](images/add-permission.png)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="05689-133">API のアクセス許可を要求する</span><span class="sxs-lookup"><span data-stu-id="05689-133">Request API permissions</span></span>

   <span data-ttu-id="05689-134">必要なアクセス許可を確認するには、呼び出す API の [アクセス許可] セクションを確認します。</span><span class="sxs-lookup"><span data-stu-id="05689-134">To determine which permission you need, review the **Permissions** section in the API you are interested to call.</span></span> <span data-ttu-id="05689-135">例えば：</span><span class="sxs-lookup"><span data-stu-id="05689-135">For instance:</span></span>

   - <span data-ttu-id="05689-136">高度 [なクエリを実行するには、[](run-advanced-query-api.md)高度なクエリの実行] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="05689-136">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
   
   - <span data-ttu-id="05689-137">デバイス [を分離するには、[](isolate-machine.md)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="05689-137">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>

   <span data-ttu-id="05689-138">次の例では、[すべてのアラートの読み取 **り] アクセス許可を使用** します。</span><span class="sxs-lookup"><span data-stu-id="05689-138">In the following example we will use **'Read all alerts'** permission:</span></span>

   <span data-ttu-id="05689-139">[**アプリケーションのアクセス許可**  >  **] Alert.Read.All >** アクセス許可 **の追加] で選択します。**</span><span class="sxs-lookup"><span data-stu-id="05689-139">Choose **Application permissions** > **Alert.Read.All** > select on **Add permissions**</span></span>

   ![アプリのアクセス許可](images/application-permissions.png)


5. <span data-ttu-id="05689-141">[同意 **の付与] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="05689-141">Select **Grant consent**</span></span>

    - <span data-ttu-id="05689-142">**注**: アクセス許可を追加する度に、新しいアクセス許可を有効にするための同意の付与で選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05689-142">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![アクセス許可の付与のイメージ](images/grant-consent.png)

6. <span data-ttu-id="05689-144">アプリケーションにシークレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="05689-144">Add a secret to the application.</span></span>

    - <span data-ttu-id="05689-145">[ **証明書とシークレット&選択し、** シークレットに説明を追加し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="05689-145">Select **Certificates & secrets**, add description to the secret and select **Add**.</span></span>

    <span data-ttu-id="05689-146">**重要**: [追加] をクリックした後 **、生成されたシークレット値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="05689-146">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="05689-147">退出後に取得できない!</span><span class="sxs-lookup"><span data-stu-id="05689-147">You won't be able to retrieve after you leave!</span></span>

    ![アプリ キーの作成のイメージ](images/webapp-create-key2.png)

7. <span data-ttu-id="05689-149">アプリケーション ID を書き下ろします。</span><span class="sxs-lookup"><span data-stu-id="05689-149">Write down your application ID:</span></span>

   - <span data-ttu-id="05689-150">アプリケーション ページで、[概要] に移動 **し** 、次の情報をコピーします。</span><span class="sxs-lookup"><span data-stu-id="05689-150">On your application page, go to **Overview** and copy the following information:</span></span>

   ![作成されたアプリ ID のイメージ](images/app-id.png)

8. <span data-ttu-id="05689-152">アプリケーションを顧客のテナントに追加します。</span><span class="sxs-lookup"><span data-stu-id="05689-152">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="05689-153">アプリケーションを使用する予定の各顧客テナントでアプリケーションを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05689-153">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="05689-154">これは、お客様の代わりにアプリケーションが Microsoft Defender for Endpoint アプリケーションとやり取りする場合です。</span><span class="sxs-lookup"><span data-stu-id="05689-154">This is because your application interacts with Microsoft Defender for Endpoint application on behalf of your customer.</span></span>

    <span data-ttu-id="05689-155">顧客のテナント **からグローバル管理者** を持つユーザーは、同意リンクを選択してアプリケーションを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05689-155">A user with **Global Administrator** from your customer's tenant need to select the consent link and approve your application.</span></span>

    <span data-ttu-id="05689-156">同意リンクは次の形式です。</span><span class="sxs-lookup"><span data-stu-id="05689-156">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="05689-157">00000000-00000-0000-0000-00000000000 をアプリケーション ID に置き換える必要がある場合</span><span class="sxs-lookup"><span data-stu-id="05689-157">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="05689-158">同意リンクをクリックした後、お客様のテナントのグローバル管理者にサインインし、アプリケーションに同意します。</span><span class="sxs-lookup"><span data-stu-id="05689-158">After clicking on the consent link, sign in with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![同意のイメージ](images/app-consent-partner.png)

    <span data-ttu-id="05689-160">さらに、トークンを取得する際には、顧客にテナント ID を要求し、将来使用するために保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05689-160">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="05689-161">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="05689-161">**Done!**</span></span> <span data-ttu-id="05689-162">アプリケーションの登録に成功しました!</span><span class="sxs-lookup"><span data-stu-id="05689-162">You have successfully registered an application!</span></span> 
- <span data-ttu-id="05689-163">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05689-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-example"></a><span data-ttu-id="05689-164">アクセス トークンの例を取得します。</span><span class="sxs-lookup"><span data-stu-id="05689-164">Get an access token example:</span></span>

<span data-ttu-id="05689-165">**注:** 顧客に代わってアクセス トークンを取得するには、次のトークン取得で顧客のテナント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="05689-165">**Note:** To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="05689-166">AAD トークンの詳細については [、「AAD チュートリアル」を参照してください。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="05689-166">For more information on AAD token, see [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="05689-167">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="05689-167">Using PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

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
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a><span data-ttu-id="05689-168">次のC#使用します。</span><span class="sxs-lookup"><span data-stu-id="05689-168">Using C#:</span></span>

><span data-ttu-id="05689-169">以下のコードは、Nuget Microsoft.IdentityModel.Clients.ActiveDirectory でテストされました</span><span class="sxs-lookup"><span data-stu-id="05689-169">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="05689-170">新しいコンソール アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="05689-170">Create a new Console Application</span></span>
- <span data-ttu-id="05689-171">NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory のインストール](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="05689-171">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="05689-172">以下を使用して追加する</span><span class="sxs-lookup"><span data-stu-id="05689-172">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="05689-173">以下のコードをアプリケーションにコピー/貼り付けます (3 つの変数を更新することを忘 ```tenantId, appId, appSecret``` れないでください。</span><span class="sxs-lookup"><span data-stu-id="05689-173">Copy/Paste the below code in your application (do not forget to update the three variables: ```tenantId, appId, appSecret```)</span></span>

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


### <a name="using-python"></a><span data-ttu-id="05689-174">Python の使用</span><span class="sxs-lookup"><span data-stu-id="05689-174">Using Python</span></span>

<span data-ttu-id="05689-175">「Python を [使用してトークンを取得する」を参照してください。](run-advanced-query-sample-python.md#get-token)</span><span class="sxs-lookup"><span data-stu-id="05689-175">Refer to [Get token using Python](run-advanced-query-sample-python.md#get-token)</span></span>

### <a name="using-curl"></a><span data-ttu-id="05689-176">Curl の使用</span><span class="sxs-lookup"><span data-stu-id="05689-176">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="05689-177">以下の手順は、Windows 用の Curl が既にコンピューターにインストールされていることを想定しています</span><span class="sxs-lookup"><span data-stu-id="05689-177">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="05689-178">コマンド ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="05689-178">Open a command window</span></span>
- <span data-ttu-id="05689-179">Azure CLIENT_ID ID に設定する</span><span class="sxs-lookup"><span data-stu-id="05689-179">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="05689-180">Azure CLIENT_SECRETシークレットに設定する</span><span class="sxs-lookup"><span data-stu-id="05689-180">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="05689-181">アプリケーションTENANT_IDを使用して Microsoft Defender for Endpoint アプリケーションにアクセスする顧客の Azure テナント ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="05689-181">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Defender for Endpoint application</span></span>
- <span data-ttu-id="05689-182">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="05689-182">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="05689-183">フォームの回答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05689-183">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="05689-184">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="05689-184">Validate the token</span></span>

<span data-ttu-id="05689-185">正気チェックを実行して、正しいトークンを取得していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05689-185">Sanity check to make sure you got a correct token:</span></span>
- <span data-ttu-id="05689-186">前の手順で [取得した](https://jwt.ms) トークンを JWT にコピー/貼り付けしてデコードする</span><span class="sxs-lookup"><span data-stu-id="05689-186">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="05689-187">必要なアクセス許可を持つ 'roles' クレームを取得する検証</span><span class="sxs-lookup"><span data-stu-id="05689-187">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="05689-188">次のスクリーンショットでは、Microsoft Defender for Endpoint への複数のアクセス許可を持つアプリケーションから取得したデコードされたトークンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="05689-188">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to  Microsoft Defender for Endpoint:</span></span>
- <span data-ttu-id="05689-189">"tid" クレームは、トークンが属するテナント ID です。</span><span class="sxs-lookup"><span data-stu-id="05689-189">The "tid" claim is the tenant ID the token belongs to.</span></span>

![トークン検証のイメージ](images/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="05689-191">トークンを使用して Microsoft Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="05689-191">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="05689-192">使用する API の選択、詳細については、「サポートされている[Microsoft Defender for Endpoint API」を参照してください](exposed-apis-list.md)。</span><span class="sxs-lookup"><span data-stu-id="05689-192">Choose the API you want to use, for more information, see [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="05689-193">送信する Http 要求の Authorization ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)</span><span class="sxs-lookup"><span data-stu-id="05689-193">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="05689-194">トークンの有効期限は 1 時間です (同じトークンで複数の要求を送信できます)</span><span class="sxs-lookup"><span data-stu-id="05689-194">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="05689-195">メッセージを使用してアラートの一覧を取得する要求を送信 **するC#**</span><span class="sxs-lookup"><span data-stu-id="05689-195">Example of sending a request to get a list of alerts **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="05689-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="05689-196">See also</span></span>
- [<span data-ttu-id="05689-197">サポートされている Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="05689-197">Supported Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="05689-198">ユーザーに代わって Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="05689-198">Access Microsoft Defender for Endpoint on behalf of a user</span></span>](exposed-apis-create-app-nativeapp.md)
