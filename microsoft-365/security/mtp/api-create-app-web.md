---
title: ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する
description: ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する方法について説明します。
keywords: アプリ、アクセス、api、作成
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
ms.openlocfilehash: be637bab97083cb857e3983dd9b82290590c1302
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650418"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="ab9e5-104">ユーザーなしで Microsoft の脅威保護にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="ab9e5-104">Create an app to access Microsoft Threat Protection without a user</span></span>

<span data-ttu-id="ab9e5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ab9e5-105">**Applies to:**</span></span>
- <span data-ttu-id="ab9e5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ab9e5-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="ab9e5-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ab9e5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ab9e5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ab9e5-109">このページでは、ユーザーなしで Microsoft の脅威保護へのプログラムによるアクセスを可能にするアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="ab9e5-110">ユーザーに代わって Microsoft の脅威保護にプログラムによってアクセスする必要がある場合は、「 [Get access with user context](api-create-app-user-context.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="ab9e5-111">必要なアクセス権がわからない場合は、「 [はじめ](api-access.md)に」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="ab9e5-112">Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="ab9e5-113">これらの Api は、Microsoft の脅威保護機能に基づいて、ワークフローとイノベーションを自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="ab9e5-114">API へのアクセスには、OAuth 2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="ab9e5-115">詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="ab9e5-116">一般に、Api を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="ab9e5-117">Azure Active Directory (Azure AD) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="ab9e5-118">このアプリケーションを使用してアクセストークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-118">Get an access token using this application.</span></span>
- <span data-ttu-id="ab9e5-119">トークンを使用して、Microsoft の脅威保護 API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="ab9e5-120">この記事では、Azure AD アプリケーションを作成し、Microsoft の脅威保護へのアクセストークンを取得し、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="ab9e5-121">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="ab9e5-121">Create an app</span></span>

1. <span data-ttu-id="ab9e5-122">**グローバル管理者**の役割を持つユーザーを使用して[Azure](https://portal.azure.com)にログオンします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="ab9e5-123">**Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="ab9e5-125">登録フォームで、アプリケーションの名前を選択し、[ **登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="ab9e5-126">アプリが Microsoft の脅威保護にアクセスできるようにして、it アクセス許可を割り当てるには、アプリケーションページで、[ **API アクセス**許可 api を追加する] [  >  **Add permission**  >  **組織は**> を使用します] を選択し、「 **microsoft threat protection**」と入力して、[ **microsoft threat protection**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab9e5-127">Microsoft の脅威保護は、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="ab9e5-128">テキストボックスに名前を記述して、表示されることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="ab9e5-130">[ **アプリケーションの権限** ] を選択します。たとえば、 **インシデント**に関連するアクセス許可を選択し、[ **アクセス許可の追加**] を選択します。 >。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![API アクセスと API 選択の画像](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="ab9e5-132">シナリオに関連するアクセス許可を選択する必要があります。 **「すべてのインシデントの読み取り」** は例にすぎません。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="ab9e5-133">必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="ab9e5-134">[ **同意を許可**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ab9e5-135">アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意の付与** ] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![許可権限の画像](../../media/grant-consent.PNG)

6. <span data-ttu-id="ab9e5-137">アプリケーションにシークレットを追加するには、[ **証明書 & シークレット**] を選択し、シークレットに説明を追加して、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab9e5-138">[ **追加**] を選択した後、[ **生成されたシークレットの値をコピー**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="ab9e5-139">その後、この値を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-139">You won't be able to retrieve this value after you leave.</span></span>

    ![アプリキーを作成する画像](../../media/webapp-create-key2.png)

7. <span data-ttu-id="ab9e5-141">アプリケーション ID とテナント ID を書き留めます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="ab9e5-142">アプリケーションページで、[ **概要** ] に移動し、次のようにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![作成されたアプリ id の画像](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="ab9e5-144">**Microsoft の脅威保護パートナーの場合のみ**。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="ab9e5-145">[こちらの手順に従って](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)ください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="ab9e5-146">アプリをテナント (同意した後、すべてのテナントで利用可能) に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="ab9e5-147">これは、サードパーティ製のアプリ (たとえば、複数の顧客のテナントで実行するためのアプリを作成する場合など) に **必要** です。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="ab9e5-148">テナントのみで実行するサービスを作成する場合は、この操作は **必要ありません** (たとえば、独自のデータと対話する独自の使用法用のアプリケーションを作成する場合)。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="ab9e5-149">アプリをテナントに設定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="ab9e5-150">[ **認証**] に移動し https://portal.azure.com て、 **リダイレクト URI**としてを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="ab9e5-151">ページの下部にある [ **サポートされるアカウントの種類**] で、マルチテナントアプリの **組織ディレクトリ** アプリケーションの同意にあるアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="ab9e5-152">アプリケーションは、その使用を予定している各テナントで承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="ab9e5-153">これは、アプリケーションがお客様の代わりに Microsoft の脅威保護に作用するからです。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="ab9e5-154">(または、サードパーティ製アプリを作成しているお客様) は、同意リンクを選択してアプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="ab9e5-155">Active Directory の管理者権限を持つユーザーとの同意を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="ab9e5-156">同意リンクの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="ab9e5-157">00000000-0000-0000-0000-000000000000 は、アプリケーション ID に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="ab9e5-158">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="ab9e5-158">**Done!**</span></span> <span data-ttu-id="ab9e5-159">アプリケーションが正常に登録されました。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-159">You have successfully registered an application!</span></span> <span data-ttu-id="ab9e5-160">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="ab9e5-161">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="ab9e5-161">Get an access token</span></span>

<span data-ttu-id="ab9e5-162">Azure AD トークンの詳細については、「 [AZURE ad チュートリアル](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="ab9e5-163">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="ab9e5-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="ab9e5-164">C# を使用します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-164">Use C#:</span></span>

<span data-ttu-id="ab9e5-165">次のコードは、Nuget 3.19.8 を使用してテストされました。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="ab9e5-166">新しいコンソールアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-166">Create a new console application.</span></span>
1. <span data-ttu-id="ab9e5-167">Nuget [クライアント](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="ab9e5-168">以下を追加します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="ab9e5-169">次のコードをコピーして、アプリに貼り付けます (3 つの変数を更新してください ```tenantId, appId, appSecret``` )。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="ab9e5-170">Python の使用</span><span class="sxs-lookup"><span data-stu-id="ab9e5-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="ab9e5-171">Curl の使用</span><span class="sxs-lookup"><span data-stu-id="ab9e5-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="ab9e5-172">次の手順では、Windows 用の Curl がコンピューターに既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="ab9e5-173">コマンドプロンプトを開き、CLIENT_ID を Azure アプリケーション ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="ab9e5-174">Azure アプリケーションシークレットに CLIENT_SECRET を設定します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="ab9e5-175">アプリを使用して Microsoft の脅威保護にアクセスするお客様の Azure テナント ID に TENANT_ID を設定します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="ab9e5-176">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="ab9e5-177">次の形式で答えが得られます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="ab9e5-178">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="ab9e5-178">Validate the token</span></span>

<span data-ttu-id="ab9e5-179">正しいトークンを取得していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="ab9e5-180">前の手順で取得したトークンを、 [JWT](https://jwt.ms) にコピーして貼り付け、デコードします。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="ab9e5-181">必要なアクセス許可を持つ ' roles ' 要求を取得していることを検証する</span><span class="sxs-lookup"><span data-stu-id="ab9e5-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="ab9e5-182">次の画像では、およびアクセス許可を持つアプリから取得した、デコードされたトークンを確認でき ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` ます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![トークン検証のイメージ](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="ab9e5-184">トークンを使用して Microsoft の脅威保護 API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ab9e5-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="ab9e5-185">使用する API を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-185">Choose the API you want to use.</span></span> <span data-ttu-id="ab9e5-186">詳細については、「 [サポートされる Microsoft Threat Protection api](api-supported.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="ab9e5-187">"ベアラー {token}" に送信する http 要求の承認ヘッダーを設定します (ベアラーは認証スキームです)。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="ab9e5-188">トークンの有効期限は1時間です。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="ab9e5-189">同じトークンを使用して、複数の要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="ab9e5-190">次に、 **C# を使用して**、インシデントのリストを取得するための要求を送信する例を示します。</span><span class="sxs-lookup"><span data-stu-id="ab9e5-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="ab9e5-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab9e5-191">Related topics</span></span>
- [<span data-ttu-id="ab9e5-192">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ab9e5-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="ab9e5-193">アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ab9e5-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="ab9e5-194">ユーザーコンテキストを使用して Microsoft の脅威保護にアクセスする</span><span class="sxs-lookup"><span data-stu-id="ab9e5-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
