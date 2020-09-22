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
ms.openlocfilehash: ae9e5ae158c95ae52112f7bc16559559230a20e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203709"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a><span data-ttu-id="32aa9-104">Microsoft の脅威保護 Api によるパートナーアクセス</span><span class="sxs-lookup"><span data-stu-id="32aa9-104">Partner access through Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="32aa9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="32aa9-105">**Applies to:**</span></span>
- <span data-ttu-id="32aa9-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="32aa9-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="32aa9-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="32aa9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="32aa9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="32aa9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="32aa9-109">このページでは、ユーザーの代わりに Microsoft の脅威保護にプログラムによってアクセスする AAD アプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-109">This page describes how to create an AAD application to get programmatic access to Microsoft Threat Protection on behalf of your customers.</span></span>

<span data-ttu-id="32aa9-110">Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-110">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="32aa9-111">これらの Api は、Microsoft の脅威保護機能に基づいて、ワークフローとイノベーションを自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="32aa9-111">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="32aa9-112">API へのアクセスには、OAuth 2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="32aa9-112">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="32aa9-113">詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-113">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="32aa9-114">一般に、Api を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-114">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="32aa9-115">**マルチテナント**AAD アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-115">Create a **multi-tenant** AAD application.</span></span>
- <span data-ttu-id="32aa9-116">お客様のアプリケーションが必要とする Microsoft の脅威保護リソースにアクセスするために、お客様の管理者による承認 (同意) を取得します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-116">Get authorized (consent) by your customer administrator for your application to access Microsoft Threat Protection resources it needs.</span></span>
- <span data-ttu-id="32aa9-117">このアプリケーションを使用してアクセストークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-117">Get an access token using this application.</span></span>
- <span data-ttu-id="32aa9-118">トークンを使用して、Microsoft の脅威保護 API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-118">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="32aa9-119">AAD アプリケーションを作成する方法、Microsoft の脅威保護へのアクセストークンを取得する方法、トークンを検証する方法については、以下の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-119">The following steps with guide you how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="32aa9-120">マルチテナントアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="32aa9-120">Create the multi-tenant app</span></span>

1. <span data-ttu-id="32aa9-121">**グローバル管理者**の役割を持つユーザーを使用して[Azure テナント](https://portal.azure.com)にログオンします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-121">Log on to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="32aa9-122">**Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="32aa9-124">登録形式:</span><span class="sxs-lookup"><span data-stu-id="32aa9-124">In the registration form:</span></span>

    - <span data-ttu-id="32aa9-125">アプリケーションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-125">Choose a name for your application.</span></span>

    - <span data-ttu-id="32aa9-126">サポートされているアカウントの種類-任意の組織ディレクトリ内のアカウント。</span><span class="sxs-lookup"><span data-stu-id="32aa9-126">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="32aa9-127">リダイレクト URI-種類: Web、URI: https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="32aa9-127">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Microsoft Azure パートナーアプリケーション登録の画像](../../media/atp-api-new-app-partner.png)


4. <span data-ttu-id="32aa9-129">アプリケーションに Microsoft の脅威保護へのアクセスを許可し、統合を完了するために必要な最低限のアクセス許可セットを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="32aa9-129">Allow your Application to access Microsoft Threat Protection and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="32aa9-130">アプリケーションページで、[ **API Permissions**] [組織が使用する  >  **アクセス許可**api を追加する] > 入力して、[microsoft threat  >  **APIs my organization uses** **protection** ] をクリックします。 **Microsoft Threat Protection**</span><span class="sxs-lookup"><span data-stu-id="32aa9-130">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft Threat Protection** and click on **Microsoft Threat Protection**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="32aa9-131">Microsoft の脅威保護は、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="32aa9-131">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="32aa9-132">テキストボックスに名前を記述して、表示されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="32aa9-134">API アクセス許可の要求</span><span class="sxs-lookup"><span data-stu-id="32aa9-134">Request API permissions</span></span>

   <span data-ttu-id="32aa9-135">必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-135">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span> 

   <span data-ttu-id="32aa9-136">次の例では、 **「すべてのインシデントを読み取る」** アクセス許可を使用します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-136">In the following example we will use **'Read all incidents'** permission:</span></span>

   <span data-ttu-id="32aa9-137">[**アプリケーションのアクセス許可**のインシデント] を選択します。  >  **すべて**> [**アクセス許可の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-137">Choose **Application permissions** > **Incidents.Read.All** > Click on **Add permissions**</span></span>

   ![API アクセスと API 選択の画像](../../media/request-api-permissions.PNG)


5. <span data-ttu-id="32aa9-139">[**同意を許可**する] をクリックする</span><span class="sxs-lookup"><span data-stu-id="32aa9-139">Click **Grant consent**</span></span>

    >[!NOTE]
    ><span data-ttu-id="32aa9-140">アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意** を得る] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-140">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![許可権限の画像](../../media/grant-consent.PNG)

6. <span data-ttu-id="32aa9-142">アプリケーションにシークレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-142">Add a secret to the application.</span></span>

    - <span data-ttu-id="32aa9-143">[ **証明書 & シークレット**] をクリックし、シークレットに説明を追加して、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-143">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="32aa9-144">[ **追加**] を選択した後、 **生成されたシークレット値をコピー**します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-144">After selecting **Add**, **copy the generated secret value**.</span></span> <span data-ttu-id="32aa9-145">退出後に取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="32aa9-145">You won't be able to retrieve after you leave!</span></span>

    ![アプリキーを作成する画像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="32aa9-147">アプリケーション ID を書き留めておきます。</span><span class="sxs-lookup"><span data-stu-id="32aa9-147">Write down your application ID:</span></span>

   - <span data-ttu-id="32aa9-148">アプリケーションページで、[ **概要** ] に移動し、次の内容をコピーします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-148">On your application page, go to **Overview** and copy the following:</span></span>

   ![作成されたアプリ id の画像](../../media/app-id.png)

8. <span data-ttu-id="32aa9-150">お客様のテナントにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-150">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="32aa9-151">アプリケーションは、使用する予定の各顧客テナントで承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-151">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="32aa9-152">これは、アプリケーションがお客様の代わりに Microsoft の脅威保護アプリケーションと対話するためです。</span><span class="sxs-lookup"><span data-stu-id="32aa9-152">This is because your application interacts with Microsoft Threat Protection application on behalf of your customer.</span></span>

    <span data-ttu-id="32aa9-153">お客様のテナントの **グローバル管理者** を持つユーザーは、同意リンクをクリックして、アプリケーションを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-153">A user with **Global Administrator** from your customer's tenant need to click the consent link and approve your application.</span></span>

    <span data-ttu-id="32aa9-154">同意リンクの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32aa9-154">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="32aa9-155">00000000-0000-0000-0000-000000000000 は、アプリケーション ID に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-155">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="32aa9-156">同意リンクをクリックした後、お客様のテナントの全体管理者にログインして、アプリケーションに同意します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-156">After clicking on the consent link, login with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![同意の画像](../../media/app-consent-partner.png)

    <span data-ttu-id="32aa9-158">また、お客様にテナント ID を要求して、トークンを取得するときに使用するために保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32aa9-158">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="32aa9-159">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="32aa9-159">**Done!**</span></span> <span data-ttu-id="32aa9-160">アプリケーションが正常に登録されました。</span><span class="sxs-lookup"><span data-stu-id="32aa9-160">You have successfully registered an application!</span></span> 
- <span data-ttu-id="32aa9-161">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-161">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-examples"></a><span data-ttu-id="32aa9-162">アクセストークンの例を取得します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-162">Get an access token examples:</span></span>

>[!NOTE]
> <span data-ttu-id="32aa9-163">お客様の代わりにアクセストークンを取得するには、次のトークンの取得でお客様のテナント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-163">To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="32aa9-164">AAD トークンの詳細については、「 [aad チュートリアル](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-164">For more details on AAD token, refer to [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="32aa9-165">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="32aa9-165">Using PowerShell</span></span>

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

### <a name="using-c"></a><span data-ttu-id="32aa9-166">C# を使用する場合:</span><span class="sxs-lookup"><span data-stu-id="32aa9-166">Using C#:</span></span>

><span data-ttu-id="32aa9-167">次のコードは、Nuget の Microsoft という id を使用してテストされています。 ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="32aa9-167">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="32aa9-168">新しいコンソールアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="32aa9-168">Create a new Console Application</span></span>
- <span data-ttu-id="32aa9-169">Nuget[クライアント](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-169">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="32aa9-170">を使用して以下を追加します</span><span class="sxs-lookup"><span data-stu-id="32aa9-170">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="32aa9-171">以下のコードをアプリケーションにコピーまたは貼り付けます (3 つの変数を更新してください ```tenantId, appId, appSecret``` )。</span><span class="sxs-lookup"><span data-stu-id="32aa9-171">Copy/Paste the below code in your application (do not forget to update the 3 variables: ```tenantId, appId, appSecret```)</span></span>

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



### <a name="using-curl"></a><span data-ttu-id="32aa9-172">Curl の使用</span><span class="sxs-lookup"><span data-stu-id="32aa9-172">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="32aa9-173">次の手順では、Windows の Curl がコンピューターに既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="32aa9-173">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="32aa9-174">コマンドウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="32aa9-174">Open a command window</span></span>
- <span data-ttu-id="32aa9-175">Azure アプリケーション ID に CLIENT_ID を設定する</span><span class="sxs-lookup"><span data-stu-id="32aa9-175">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="32aa9-176">Azure アプリケーションシークレットに CLIENT_SECRET を設定する</span><span class="sxs-lookup"><span data-stu-id="32aa9-176">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="32aa9-177">アプリケーションを使用して Microsoft の脅威保護アプリケーションにアクセスするお客様の Azure テナント ID に TENANT_ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-177">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Threat Protection application</span></span>
- <span data-ttu-id="32aa9-178">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="32aa9-178">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="32aa9-179">次の形式の応答が得られます。</span><span class="sxs-lookup"><span data-stu-id="32aa9-179">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="32aa9-180">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="32aa9-180">Validate the token</span></span>

<span data-ttu-id="32aa9-181">正しいトークンを取得していることを確認するために、正当性チェックを行います。</span><span class="sxs-lookup"><span data-stu-id="32aa9-181">Sanity check to make sure you got a correct token:</span></span>

- <span data-ttu-id="32aa9-182">前の手順で取得したトークンにコピー/貼り [付けして](https://jwt.ms) 、デコードします。</span><span class="sxs-lookup"><span data-stu-id="32aa9-182">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="32aa9-183">必要なアクセス許可を持つ ' roles ' クレームを取得することを確認する</span><span class="sxs-lookup"><span data-stu-id="32aa9-183">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="32aa9-184">次のスクリーンショットでは、Microsoft の脅威保護に対する複数のアクセス許可を持つアプリケーションから取得したデコードされたトークンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="32aa9-184">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to Microsoft Threat Protection:</span></span>
- <span data-ttu-id="32aa9-185">"Tid" クレームは、トークンが属するテナント ID です。</span><span class="sxs-lookup"><span data-stu-id="32aa9-185">The "tid" claim is the tenant ID the token belongs to.</span></span>

![トークン検証のイメージ](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="32aa9-187">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="32aa9-187">Use the token to access Microsoft Threat Protection API</span></span>

- <span data-ttu-id="32aa9-188">使用する API を選択します。詳細については、「[サポートされる Microsoft Threat Protection api](api-supported.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32aa9-188">Choose the API you want to use, for more information, see [Supported Microsoft Threat Protection APIs](api-supported.md)</span></span>
- <span data-ttu-id="32aa9-189">"ベアラー {token}" に送信する Http 要求で承認ヘッダーを設定する (ベアラーが認証スキームである)</span><span class="sxs-lookup"><span data-stu-id="32aa9-189">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="32aa9-190">トークンの有効期限は1時間です (同じトークンを使用して、さらに1つの要求を送信できます)。</span><span class="sxs-lookup"><span data-stu-id="32aa9-190">The Expiration time of the token is 1 hour (you can send more then one request with the same token)</span></span>

- <span data-ttu-id="32aa9-191">**C# を使用して**、インシデントのリストを取得するための要求を送信する例</span><span class="sxs-lookup"><span data-stu-id="32aa9-191">Example of sending a request to get a list of incidents **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a><span data-ttu-id="32aa9-192">関連項目</span><span class="sxs-lookup"><span data-stu-id="32aa9-192">Related topics</span></span> 

- [<span data-ttu-id="32aa9-193">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="32aa9-193">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="32aa9-194">アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="32aa9-194">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="32aa9-195">ユーザーコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="32aa9-195">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
