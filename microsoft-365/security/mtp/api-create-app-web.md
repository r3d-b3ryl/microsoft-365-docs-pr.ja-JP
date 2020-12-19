---
title: ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する
description: ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する方法について説明します。
keywords: アプリ, アクセス, api, 作成
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719358"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="522e3-104">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="522e3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="522e3-105">**Applies to:**</span></span>

- <span data-ttu-id="522e3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="522e3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="522e3-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="522e3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="522e3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="522e3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="522e3-109">このページでは、定義されたユーザーなしで Microsoft 365 Defender にプログラムでアクセスするアプリケーションを作成する方法について説明します。たとえば、デーモンやバックグラウンド サービスを作成する場合などです。</span><span class="sxs-lookup"><span data-stu-id="522e3-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="522e3-110">1 人または複数のユーザーの代わりに Microsoft 365 Defender にプログラムでアクセスする必要がある場合は、「ユーザーの代わりに [Microsoft 365 Defender](api-create-app-user-context.md) API にアクセスするアプリを作成する」と [「Microsoft 365 Defender](api-partner-access.md)API へのパートナー アクセスを使用してアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522e3-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="522e3-111">必要なアクセスの種類が不明な場合は、「開始する」を [参照してください](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="522e3-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="522e3-112">Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="522e3-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="522e3-113">これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能を利用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="522e3-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="522e3-114">この API アクセスには OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="522e3-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="522e3-115">詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="522e3-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="522e3-116">一般に、これらの API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="522e3-117">Azure Active Directory (Azure AD) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="522e3-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="522e3-118">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="522e3-118">Get an access token using this application.</span></span>
- <span data-ttu-id="522e3-119">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="522e3-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="522e3-120">この記事では、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="522e3-120">This article explains how to:</span></span>

- <span data-ttu-id="522e3-121">Azure AD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-121">Create an Azure AD application</span></span>
- <span data-ttu-id="522e3-122">Microsoft 365 Defender へのアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="522e3-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="522e3-123">トークンを検証します。</span><span class="sxs-lookup"><span data-stu-id="522e3-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="522e3-124">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-124">Create an app</span></span>

1. <span data-ttu-id="522e3-125">グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。</span><span class="sxs-lookup"><span data-stu-id="522e3-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="522e3-126">Azure **Active Directory アプリの**  >  **登録の新規登録**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="522e3-128">フォームで、アプリケーションの名前を選択し、[登録] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="522e3-129">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用し  >    >  **、「Microsoft Threat Protection」と** 入力して **、Microsoft Threat Protection を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="522e3-130">これで、アプリは Microsoft 365 Defender にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="522e3-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="522e3-131">*Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="522e3-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="522e3-132">テキスト ボックスが表示されるのを確認するには、テキスト ボックスに名前の書き込みを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="522e3-134">アプリケーションの **アクセス許可を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-134">Select **Application permissions**.</span></span> <span data-ttu-id="522e3-135">シナリオに関連するアクセス許可 **(Incident.Read.All** など) を選択し、[アクセス許可の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API アクセスと API の選択の画像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="522e3-137">シナリオに関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="522e3-138">*すべてのインシデントの読み取り* は単なる例です。</span><span class="sxs-lookup"><span data-stu-id="522e3-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="522e3-139">必要なアクセス許可を確認するには、呼び出す API の **[** アクセス許可] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="522e3-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="522e3-140">たとえば、高度な [クエリを実行するには、[](api-advanced-hunting.md)高度なクエリの実行] 権限を選択します。デバイス [を分離するには、[コンピューターの](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="522e3-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="522e3-141">[管理者 **の同意を付与する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="522e3-142">アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![アクセス許可の付与の画像](../../media/grant-consent.PNG)

7. <span data-ttu-id="522e3-144">アプリケーションにシークレットを追加するには、[証明書とシークレット&し、シークレットに説明を追加して、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="522e3-145">[追加] を **選択した後**、生成 **されたシークレットの値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="522e3-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="522e3-146">退出後にシークレット値を取得できない。</span><span class="sxs-lookup"><span data-stu-id="522e3-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![アプリ キーの作成の画像](../../media/webapp-create-key2.png)

8. <span data-ttu-id="522e3-148">アプリケーション ID とテナント ID を安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="522e3-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="522e3-149">アプリケーション ページの [概要] **に** 一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="522e3-149">They're listed under **Overview** on your application page.</span></span>

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="522e3-151">**Microsoft 365 Defender パートナー** の場合 [のみ:](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) Microsoft 365 Defender API を介したパートナー アクセスについては、次の手順に従い、アプリをマルチテナントに設定して、管理者の同意を受け取った後、すべてのテナントで利用できます。</span><span class="sxs-lookup"><span data-stu-id="522e3-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="522e3-152">パートナー アクセスは **、サード** パーティ製アプリ (たとえば、複数の顧客のテナントで実行するアプリを作成する場合) に必要です。</span><span class="sxs-lookup"><span data-stu-id="522e3-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="522e3-153">テナント **でのみ** 実行するサービス (独自のデータのみを操作する独自の利用状況用のアプリケーションなど) を作成する場合は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="522e3-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="522e3-154">アプリをマルチテナントに設定するには:</span><span class="sxs-lookup"><span data-stu-id="522e3-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="522e3-155">[認証 **] に** 移動し、リダイレクト https://portal.azure.com URI **として追加します**。</span><span class="sxs-lookup"><span data-stu-id="522e3-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="522e3-156">ページの下部にある [サポートされているアカウントの種類] で、マルチテナント アプリの組織ディレクトリ アプリケーションの同意にある [アカウント] を選択します。</span><span class="sxs-lookup"><span data-stu-id="522e3-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="522e3-157">アプリケーションはユーザーの代わりに Microsoft 365 Defender とやり取りを行うので、そのアプリケーションを使用する予定のすべてのテナントに対して承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="522e3-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="522e3-158">各テナントの Active Directory グローバル管理者は、同意リンクを選択してアプリを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="522e3-159">同意リンクの構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="522e3-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="522e3-160">数字は `00000000-0000-0000-0000-000000000000` アプリケーション ID に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="522e3-161">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="522e3-161">**Done!**</span></span> <span data-ttu-id="522e3-162">アプリケーションが正常に登録されました。</span><span class="sxs-lookup"><span data-stu-id="522e3-162">You've successfully registered an application!</span></span> <span data-ttu-id="522e3-163">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522e3-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="522e3-164">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="522e3-164">Get an access token</span></span>

<span data-ttu-id="522e3-165">Azure Active Directory トークンについて詳しくは、Azure Active Directory のチュートリアル [AD覧ください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="522e3-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="522e3-166">このセクションの例では、テスト目的でシークレット値を貼り付ける方法を推奨しますが、実稼働環境で実行されているアプリケーションにシークレットをハードコードし込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="522e3-167">サード パーティは、シークレットを使用してリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="522e3-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="522e3-168">[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)を使用して、アプリのシークレットをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="522e3-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="522e3-169">アプリを保護する方法の実用的な例については、「Azure Key Vault を使用してサーバー アプリのシークレットを管理する」 [を参照してください](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)。</span><span class="sxs-lookup"><span data-stu-id="522e3-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="522e3-170">PowerShell を使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="522e3-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="522e3-171">C を使用してアクセス トークンを取得する\#</span><span class="sxs-lookup"><span data-stu-id="522e3-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="522e3-172">次のコードは、Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 でテストされました。</span><span class="sxs-lookup"><span data-stu-id="522e3-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="522e3-173">新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="522e3-173">Create a new console application.</span></span>

1. <span data-ttu-id="522e3-174">NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory をインストールします](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="522e3-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="522e3-175">次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="522e3-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="522e3-176">次のコードをコピーしてアプリに貼り付けます (3 つの変数を忘れずに更新してください: `tenantId` `clientId` , , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="522e3-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="522e3-177">Python を使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="522e3-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="522e3-178">レジストリを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="522e3-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="522e3-179">Windows 10 バージョン 1803 以降には、あらかじめインストールされています。</span><span class="sxs-lookup"><span data-stu-id="522e3-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="522e3-180">他のバージョンの Windows では、公式 Web サイトから直接ツールをダウンロード [してインストールします](https://curl.haxx.se/windows/)。</span><span class="sxs-lookup"><span data-stu-id="522e3-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="522e3-181">コマンド プロンプトを開き、Azure CLIENT_ID ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="522e3-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="522e3-182">Azure CLIENT_SECRET シークレットに設定します。</span><span class="sxs-lookup"><span data-stu-id="522e3-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="522e3-183">アプリTENANT_ID使用して Microsoft 365 Defender にアクセスする顧客の Azure テナント ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="522e3-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="522e3-184">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="522e3-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="522e3-185">正常な応答は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="522e3-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="522e3-186">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="522e3-186">Validate the token</span></span>

1. <span data-ttu-id="522e3-187">トークンをコピーして JSON Web トークン検証 Web サイト [(JWT)](https://jwt.ms) に貼り付け、デコードします。</span><span class="sxs-lookup"><span data-stu-id="522e3-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="522e3-188">デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="522e3-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="522e3-189">次の図では、アプリから取得したデコードされたトークンと、アクセス許可 `Incidents.Read.All` `Incidents.ReadWrite.All` を `AdvancedHunting.Read.All` 確認できます。</span><span class="sxs-lookup"><span data-stu-id="522e3-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![トークン検証の画像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="522e3-191">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="522e3-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="522e3-192">使用する API (インシデントまたは高度な検索) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522e3-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="522e3-193">詳細については、「サポートされている [Microsoft 365 Defender API」を参照してください](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="522e3-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="522e3-194">送信する http 要求で、承認ヘッダーを 、承認スキームであるベアラー、検証済みトークンであるトークンに `"Bearer" <token>` 設定します。  </span><span class="sxs-lookup"><span data-stu-id="522e3-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="522e3-195">トークンは 1 時間以内に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="522e3-195">The token will expire within one hour.</span></span> <span data-ttu-id="522e3-196">この間は、同じトークンを使用して複数の要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="522e3-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="522e3-197">次の例は、C# を使用してインシデントの一覧を取得する要求を送信 **する方法を示しています**。</span><span class="sxs-lookup"><span data-stu-id="522e3-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="522e3-198">関連記事</span><span class="sxs-lookup"><span data-stu-id="522e3-198">Related articles</span></span>

- [<span data-ttu-id="522e3-199">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="522e3-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="522e3-200">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="522e3-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="522e3-201">"Hello world" アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="522e3-202">ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="522e3-203">マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="522e3-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="522e3-204">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="522e3-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="522e3-205">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="522e3-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="522e3-206">Azure Key Vault を使用してサーバー アプリのシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="522e3-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="522e3-207">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="522e3-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
