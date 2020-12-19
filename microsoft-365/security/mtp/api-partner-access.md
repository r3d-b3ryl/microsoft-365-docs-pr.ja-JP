---
title: Microsoft 365 Defender API を介したパートナー アクセス
description: ユーザーに代わって Microsoft 365 Defender にプログラムでアクセスするアプリを作成する方法について説明します。
keywords: パートナー, アクセス, api, マルチ テナント, 同意, アクセス トークン, アプリ
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719442"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="8d0a4-104">パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8d0a4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8d0a4-105">**Applies to:**</span></span>

- <span data-ttu-id="8d0a4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d0a4-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d0a4-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8d0a4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8d0a4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8d0a4-109">このページでは、複数のテナントのユーザーに代わって、Microsoft 365 Defender にプログラムでアクセスできる Azure Active Directory アプリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="8d0a4-110">マルチテナント アプリは、大規模なユーザー グループにサービスを提供する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="8d0a4-111">1 人のユーザーの代わりに Microsoft 365 Defender にプログラムでアクセスする必要がある場合は、「ユーザーの代わりに [Microsoft 365 Defender API](api-create-app-user-context.md)にアクセスするアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="8d0a4-112">ユーザーが明示的に定義されていないアクセスが必要な場合 (たとえば、バックグラウンド アプリやデーモンを作成している場合)、「ユーザーなしで [Microsoft 365 Defender](api-create-app-web.md)にアクセスするアプリを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="8d0a4-113">必要なアクセスの種類が不明な場合は、「開始する」を [参照してください](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="8d0a4-114">Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8d0a4-115">これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能を利用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="8d0a4-116">この API アクセスには OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8d0a4-117">詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8d0a4-118">一般に、これらの API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="8d0a4-119">Azure Active Directory (Azure AD) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8d0a4-120">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-120">Get an access token using this application.</span></span>
- <span data-ttu-id="8d0a4-121">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="8d0a4-122">このアプリはマルチテナントです。ユーザーの代わりに、各[](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant)テナントからの管理者の同意も必要になります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="8d0a4-123">この記事では、次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-123">This article explains how to:</span></span>

- <span data-ttu-id="8d0a4-124">マルチテナント **の** Azure AD アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="8d0a4-125">アプリケーションが必要とする Microsoft 365 Defender にアクセスするために、ユーザー管理者から承認された同意を得る。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="8d0a4-126">Microsoft 365 Defender へのアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="8d0a4-127">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-127">Validate the token</span></span>

<span data-ttu-id="8d0a4-128">Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8d0a4-129">これらの API は、作業フローを自動化し、Microsoft 365 Defender の機能に基づいて革新を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="8d0a4-130">API アクセスには OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8d0a4-131">詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8d0a4-132">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="8d0a4-133">マルチテナント **の** Azure AD作成します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="8d0a4-134">アプリケーションが必要とする Microsoft 365 Defender リソースにアクセスするために、ユーザー管理者によって承認 (同意) されます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="8d0a4-135">このアプリケーションを使用してアクセス トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-135">Get an access token using this application.</span></span>
- <span data-ttu-id="8d0a4-136">トークンを使用して Microsoft 365 Defender API にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="8d0a4-137">次の手順では、マルチテナント Azure AD アプリケーションを作成し、Microsoft 365 Defender へのアクセス トークンを取得し、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="8d0a4-138">マルチテナント アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="8d0a4-139">グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8d0a4-140">Azure **Active Directory アプリの**  >  **登録新規登録**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8d0a4-142">登録フォームで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-142">In the registration form:</span></span>

   - <span data-ttu-id="8d0a4-143">アプリケーションの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="8d0a4-144">[ **サポートされているアカウントの種類] で**、任意の組織のディレクトリ **(任意の Azure AD ディレクトリ) の [マルチテナント] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="8d0a4-145">[リダイレクト **URI] セクションに入力** します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="8d0a4-146">**[Web] と入力し**、リダイレクト URI を次のように指定します **https://portal.azure.com** 。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="8d0a4-147">フォームへの入力が完了したら、[登録] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-147">After you're done filling out the form, select **Register**.</span></span>

   ![[アプリケーションの登録] フォームの画像](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="8d0a4-149">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用し  >    >  **、「Microsoft Threat Protection」と** 入力して **、Microsoft Threat Protection を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="8d0a4-150">これで、アプリは Microsoft 365 Defender にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="8d0a4-151">*Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="8d0a4-152">表示するには、テキスト ボックスに名前を書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="8d0a4-154">アプリケーションの **アクセス許可を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-154">Select **Application permissions**.</span></span> <span data-ttu-id="8d0a4-155">シナリオに関連するアクセス許可 **(Incident.Read.All** など) を選択し、[アクセス許可の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![API アクセスと API の選択の画像](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="8d0a4-157">シナリオに関連するアクセス許可を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="8d0a4-158">*すべてのインシデントの読み取り* は単なる例です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="8d0a4-159">必要なアクセス許可を確認するには、呼び出す API の **[** アクセス許可] セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="8d0a4-160">たとえば、高度な [クエリを実行するには、[](api-advanced-hunting.md)高度なクエリの実行] 権限を選択します。デバイス [を分離するには、[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="8d0a4-161">[管理者 **の同意を付与する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="8d0a4-162">アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![アクセス許可の付与の画像](../../media/grant-consent.PNG)

7. <span data-ttu-id="8d0a4-164">アプリケーションにシークレットを追加するには、[証明書とシークレット&し、シークレットに説明を追加して、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="8d0a4-165">[追加] を **選択した後**、生成 **されたシークレットの値をコピーします**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="8d0a4-166">退出後にシークレット値を取得できない。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![アプリ キーの作成の画像](../../media/webapp-create-key2.png)

8. <span data-ttu-id="8d0a4-168">アプリケーション ID とテナント ID を安全な場所に記録します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="8d0a4-169">アプリケーション ページの [概要] **に一** 覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-169">They're listed under **Overview** on your application page.</span></span>

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="8d0a4-171">ユーザーのテナントにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="8d0a4-172">アプリケーションはユーザーの代わりに Microsoft 365 Defender とやり取りを行うので、そのアプリケーションを使用する予定のすべてのテナントに対して承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="8d0a4-173">ユーザー **のテナント** のグローバル管理者は、同意リンクを表示してアプリケーションを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="8d0a4-174">同意リンクの形式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="8d0a4-175">数字は `00000000-0000-0000-0000-000000000000` アプリケーション ID に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="8d0a4-176">同意リンクをクリックした後、ユーザーのテナントのグローバル管理者でサインインし、アプリケーションに同意します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![同意の画像](../../media/app-consent-partner.png)

   <span data-ttu-id="8d0a4-178">また、テナント ID をユーザーに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="8d0a4-179">テナント ID は、アクセス トークンを取得するために使用される識別子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="8d0a4-180">**完成です！**</span><span class="sxs-lookup"><span data-stu-id="8d0a4-180">**Done!**</span></span> <span data-ttu-id="8d0a4-181">アプリケーションが正常に登録されました。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="8d0a4-182">トークンの取得と検証については、以下の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="8d0a4-183">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-183">Get an access token</span></span>

<span data-ttu-id="8d0a4-184">Azure AD トークンの詳細については [、Azure](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)ADしてください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8d0a4-185">このセクションの例では、テスト目的でシークレット値を貼り付ける方法を推奨しますが、実稼働環境で実行されているアプリケーションにシークレットをハードコードし込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="8d0a4-186">サード パーティは、シークレットを使用してリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="8d0a4-187">[Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)を使用して、アプリのシークレットをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="8d0a4-188">アプリを保護する方法の実用的な例については [、「Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)を使用してサーバー アプリのシークレットを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="8d0a4-189">次の例では、ユーザーのテナント ID を使用して、スクリプトが機能しているのをテストします。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="8d0a4-190">PowerShell を使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="8d0a4-191">C を使用してアクセス トークンを取得する\#</span><span class="sxs-lookup"><span data-stu-id="8d0a4-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="8d0a4-192">次のコードは、Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8 でテストされました。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="8d0a4-193">新しいコンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-193">Create a new console application.</span></span>
1. <span data-ttu-id="8d0a4-194">NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory をインストールします](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="8d0a4-195">次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="8d0a4-196">次のコードをコピーしてアプリに貼り付けます (3 つの変数 ( , , ) を更新することを `tenantId` 忘 `clientId` れないでください `appSecret` 。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="8d0a4-197">Python を使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="8d0a4-198">レジストリを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="8d0a4-199">Windows 10 バージョン 1803 以降には、Windows 10 がプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="8d0a4-200">他のバージョンの Windows では、公式 Web サイトから直接ツールをダウンロード [してインストールします](https://curl.haxx.se/windows/)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="8d0a4-201">コマンド プロンプトを開き、Azure CLIENT_ID ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="8d0a4-202">Azure CLIENT_SECRETシークレットに設定します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="8d0a4-203">アプリTENANT_ID使用して Microsoft 365 Defender にアクセスするユーザーの Azure テナント ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="8d0a4-204">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="8d0a4-205">正常な応答は次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="8d0a4-206">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-206">Validate the token</span></span>

1. <span data-ttu-id="8d0a4-207">トークンをコピーして JSON Web トークン検証 Web サイト [(JWT)](https://jwt.ms) に貼り付け、デコードします。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="8d0a4-208">デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="8d0a4-209">次の図では、アプリから取得したデコードされたトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 確認できます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![トークン検証の画像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="8d0a4-211">トークンを使用して Microsoft 365 Defender API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="8d0a4-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="8d0a4-212">使用する API (インシデントまたは高度な検索) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="8d0a4-213">詳細については、「サポートされている [Microsoft 365 Defender API」を参照してください](api-supported.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="8d0a4-214">送信する http 要求で、承認ヘッダーを 、承認スキームである `"Bearer" <token>` *Bearer、* 検証済みトークンであるトークンに設定します。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="8d0a4-215">トークンは 1 時間以内に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-215">The token will expire within one hour.</span></span> <span data-ttu-id="8d0a4-216">この間、同じトークンを使用して複数の要求を送信できます。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="8d0a4-217">次の例は、C# を使用してインシデントの一覧を取得する要求を送信 **する方法を示しています**。</span><span class="sxs-lookup"><span data-stu-id="8d0a4-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="8d0a4-218">関連記事</span><span class="sxs-lookup"><span data-stu-id="8d0a4-218">Related articles</span></span>

- [<span data-ttu-id="8d0a4-219">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="8d0a4-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="8d0a4-220">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="8d0a4-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8d0a4-221">"Hello world" アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="8d0a4-222">ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8d0a4-223">ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="8d0a4-224">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="8d0a4-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="8d0a4-225">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="8d0a4-226">Azure Key Vault を使用してサーバー アプリのシークレットを管理する</span><span class="sxs-lookup"><span data-stu-id="8d0a4-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="8d0a4-227">ユーザー サインインと API アクセスの OAuth 2.0 承認</span><span class="sxs-lookup"><span data-stu-id="8d0a4-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
