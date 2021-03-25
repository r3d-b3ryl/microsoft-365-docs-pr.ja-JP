---
title: ユーザーに代わって Microsoft 365 Defender API にアクセスするアプリを作成する
description: ユーザーに代わって Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: access, 代理ユーザー, api, application, user, access token, token,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bffe38ff5dc4c11ed25519c86081e24ff1191e94
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068667"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="cc2de-104">ユーザーに代わって Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cc2de-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cc2de-105">**Applies to:**</span></span>

- <span data-ttu-id="cc2de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc2de-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc2de-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="cc2de-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cc2de-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="cc2de-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cc2de-109">このページでは、1 人のユーザーに代わって Microsoft 365 Defender へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="cc2de-110">定義済みのユーザーなしで Microsoft 365 Defender にプログラムでアクセスする必要がある場合 (たとえば、バックグラウンド アプリやデーモンを作成する場合)、「ユーザーなしで [Microsoft 365 Defender](api-create-app-web.md)にアクセスするアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2de-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="cc2de-111">大規模な組織や顧客グループにサービスを提供する場合など、複数のテナントにアクセス権を提供する必要がある場合は [、「Microsoft 365 Defender API](api-partner-access.md)へのパートナー アクセスを持つアプリを作成する」を参照してください。必要なアクセスの種類が不明な場合は、「開始する」 [を参照してください](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="cc2de-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="cc2de-112">Microsoft 365 Defender は、一連のプログラム API を使用して、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="cc2de-113">これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能を利用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cc2de-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="cc2de-114">この API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc2de-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="cc2de-115">詳細については [、「OAuth 2.0 Authorization Code Flow」を参照してください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="cc2de-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="cc2de-116">一般に、これらの API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="cc2de-117">Azure Active Directory (Azure Active Directory AD) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="cc2de-118">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-118">Get an access token using this application.</span></span>
- <span data-ttu-id="cc2de-119">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cc2de-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="cc2de-120">この記事では、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-120">This article explains how to:</span></span>

- <span data-ttu-id="cc2de-121">Azure AD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-121">Create an Azure AD application</span></span>
- <span data-ttu-id="cc2de-122">Microsoft 365 Defender へのアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="cc2de-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="cc2de-123">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="cc2de-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="cc2de-124">ユーザーの代わりに Microsoft 365 Defender API にアクセスする場合は、適切なアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="cc2de-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="cc2de-125">ポータルでアクションを実行するアクセス許可がある場合は、API でアクションを実行するアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="cc2de-126">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-126">Create an app</span></span>

1. <span data-ttu-id="cc2de-127">グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="cc2de-128">**[Azure Active Directory アプリの**  >  **登録] [新規登録**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="cc2de-130">フォームで、アプリケーションの名前を選択し、リダイレクト URI の次の情報を入力し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![[アプリケーションの作成] ウィンドウのイメージ](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="cc2de-132">**アプリケーションの種類:** パブリック クライアント</span><span class="sxs-lookup"><span data-stu-id="cc2de-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="cc2de-133">**リダイレクト URI:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="cc2de-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="cc2de-134">アプリケーション ページで **、[API アクセス** 許可] [アクセス許可の追加] を選択し、組織で使用するアクセス許可 API > Microsoft Threat Protection と入力し  >    >  **、[Microsoft** Threat **Protection] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="cc2de-135">これで、アプリは Microsoft 365 Defender にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cc2de-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="cc2de-136">*Microsoft Threat Protection* は、Microsoft 365 Defender の以前の名前であり、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="cc2de-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="cc2de-137">テキスト ボックスに名前を書き込み始め、表示を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセス許可の選択のイメージ](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="cc2de-139">[ **委任されたアクセス許可] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="cc2de-140">シナリオに関連するアクセス許可 (インシデント **.読** み取りなど) を選択し、[アクセス許可の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![API アクセスと API の選択のイメージ](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="cc2de-142">シナリオに関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="cc2de-143">*すべてのインシデントの読み取り* は、単なる例です。</span><span class="sxs-lookup"><span data-stu-id="cc2de-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="cc2de-144">必要なアクセス許可を決定するには、呼び出す API の **[** アクセス許可] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc2de-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="cc2de-145">たとえば、高度な [クエリを実行するには、[](api-advanced-hunting.md)高度なクエリの実行] アクセス許可を選択します。デバイス [を分離するには、[](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="cc2de-146">[管理者 **の同意を付与する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cc2de-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="cc2de-147">アクセス許可を追加する度に、[管理者の同意 **を付与** する] を選択して有効に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![アクセス許可の付与のイメージ](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="cc2de-149">アプリケーション ID とテナント ID を安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="cc2de-150">アプリケーション ページの [概要] **に** 一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc2de-150">They're listed under **Overview** on your application page.</span></span>

   ![作成されたアプリ ID のイメージ](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="cc2de-152">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="cc2de-152">Get an access token</span></span>

<span data-ttu-id="cc2de-153">Azure Active Directory トークンの詳細については、「Azure Active Directory トークン」のチュートリアル [ADしてください](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。</span><span class="sxs-lookup"><span data-stu-id="cc2de-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="cc2de-154">PowerShell を使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="cc2de-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="cc2de-155">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="cc2de-155">Validate the token</span></span>

1. <span data-ttu-id="cc2de-156">トークンをコピーして JWT に貼 [り付け、](https://jwt.ms) デコードします。</span><span class="sxs-lookup"><span data-stu-id="cc2de-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="cc2de-157">デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="cc2de-158">次の図では、アプリから取得したデコードトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 表示できます。</span><span class="sxs-lookup"><span data-stu-id="cc2de-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![トークン検証のイメージ](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="cc2de-160">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="cc2de-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="cc2de-161">使用する API (インシデント、高度な検索) を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2de-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="cc2de-162">詳細については、「サポートされている [Microsoft 365 Defender API」を参照してください](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="cc2de-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="cc2de-163">送信する http 要求で、認証ヘッダーを 、承認スキームであるベアラー、検証済みトークンである `"Bearer" <token>` トークンに設定します。 </span><span class="sxs-lookup"><span data-stu-id="cc2de-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="cc2de-164">トークンは 1 時間以内に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="cc2de-164">The token will expire within one hour.</span></span> <span data-ttu-id="cc2de-165">同じトークンを使用して、この期間中に複数の要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="cc2de-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="cc2de-166">次の例は、要求を送信して、イベントを使用してインシデントの一覧を取得する **C#。**</span><span class="sxs-lookup"><span data-stu-id="cc2de-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="cc2de-167">関連記事</span><span class="sxs-lookup"><span data-stu-id="cc2de-167">Related articles</span></span>

- [<span data-ttu-id="cc2de-168">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="cc2de-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="cc2de-169">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="cc2de-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="cc2de-170">'Hello world' アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="cc2de-171">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="cc2de-172">Microsoft 365 Defender API へのマルチテナント パートナー アクセスでアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="cc2de-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="cc2de-173">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="cc2de-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="cc2de-174">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="cc2de-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="cc2de-175">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="cc2de-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)