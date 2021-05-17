---
title: エンドポイント API で Microsoft Defender を使用する
ms.reviewer: ''
description: ユーザーなしで Microsoft Defender for Endpoint にプログラムWindowsアクセスを取得するネイティブ アプリを設計する方法について説明します。
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
ms.openlocfilehash: 5e59ff75a7933cf52af857f1a41b0925aa7bb47a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198921"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="2a09c-104">エンドポイント API で Microsoft Defender を使用する</span><span class="sxs-lookup"><span data-stu-id="2a09c-104">Use Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2a09c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2a09c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a09c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a09c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="2a09c-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="2a09c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2a09c-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="2a09c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2a09c-109">このページでは、ユーザーに代わって Defender for Endpoint へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-109">This page describes how to create an application to get programmatic access to Defender for Endpoint on behalf of a user.</span></span>

<span data-ttu-id="2a09c-110">ユーザーなしで Microsoft Defender for Endpoint にプログラムでアクセスする必要がある場合は、「Access Microsoft Defender for Endpoint with application [context」を参照してください](exposed-apis-create-app-webapp.md)。</span><span class="sxs-lookup"><span data-stu-id="2a09c-110">If you need programmatic access Microsoft Defender for Endpoint without a user, refer to [Access Microsoft Defender for Endpoint with application context](exposed-apis-create-app-webapp.md).</span></span>

<span data-ttu-id="2a09c-111">必要なアクセスが分からない場合は、[概要] ページをお [読みください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="2a09c-111">If you are not sure which access you need, read the [Introduction page](apis-intro.md).</span></span>

<span data-ttu-id="2a09c-112">Microsoft Defender for Endpoint は、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-112">Microsoft Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="2a09c-113">これらの API を使用すると、Microsoft Defender for Endpoint の機能に基づいてワークフローを自動化し、革新することができます。</span><span class="sxs-lookup"><span data-stu-id="2a09c-113">Those APIs will enable you to automate work flows and innovate based on Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="2a09c-114">API アクセスには、OAuth2.0 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a09c-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="2a09c-115">詳細については[、「OAuth 2.0 Authorization Code Flow」 を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。</span><span class="sxs-lookup"><span data-stu-id="2a09c-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="2a09c-116">一般に、API を使用するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a09c-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="2a09c-117">AAD アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="2a09c-117">Create an AAD application</span></span>
- <span data-ttu-id="2a09c-118">このアプリケーションを使用してアクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="2a09c-118">Get an access token using this application</span></span>
- <span data-ttu-id="2a09c-119">トークンを使用して Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2a09c-119">Use the token to access Defender for Endpoint API</span></span>

<span data-ttu-id="2a09c-120">このページでは、AAD アプリケーションを作成し、Microsoft Defender for Endpoint へのアクセス トークンを取得し、トークンを検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-120">This page explains how to create an AAD application, get an access token to Microsoft Defender for Endpoint and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="2a09c-121">ユーザーに代わって Microsoft Defender for Endpoint API にアクセスする場合は、適切なアプリケーションアクセス許可とユーザーアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2a09c-121">When accessing Microsoft Defender for Endpoint API on behalf of a user, you will need the correct Application permission and user permission.</span></span>
> <span data-ttu-id="2a09c-122">Microsoft Defender for Endpoint のユーザーアクセス許可に精通していない場合は、「役割ベースのアクセス制御を使用してポータル アクセスを管理する」 [を参照してください](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="2a09c-122">If you are not familiar with user permissions on Microsoft Defender for Endpoint, see [Manage portal access using role-based access control](rbac.md).</span></span>

>[!TIP]
> <span data-ttu-id="2a09c-123">ポータルでアクションを実行するアクセス許可がある場合は、API でアクションを実行するアクセス許可を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a09c-123">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="2a09c-124">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="2a09c-124">Create an app</span></span>

1. <span data-ttu-id="2a09c-125">グローバル管理者の [役割を](https://portal.azure.com) 持つユーザー アカウントを使用して **Azure にログオン** します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-125">Log on to [Azure](https://portal.azure.com) with a user account that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="2a09c-126">[アプリの **登録Azure Active Directory**  >  **新しい登録]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="2a09c-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![アプリケーション登録Microsoft Azureナビゲーションのイメージ](images/atp-azure-new-app2.png)

3. <span data-ttu-id="2a09c-128">[**アプリケーションの登録**] ページが表示されたら、以下のアプリケーションの登録情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-128">When the **Register an application** page appears, enter your application's registration information:</span></span>

   - <span data-ttu-id="2a09c-129">**名前** - アプリのユーザーに表示されるわかりやすいアプリケーション名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-129">**Name** - Enter a meaningful application name that will be displayed to users of the app.</span></span>
   - <span data-ttu-id="2a09c-130">**サポートされているアカウントの種類** - アプリケーションでサポートするアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-130">**Supported account types** - Select which accounts you would like your application to support.</span></span>

       | <span data-ttu-id="2a09c-131">サポートされているアカウントの種類</span><span class="sxs-lookup"><span data-stu-id="2a09c-131">Supported account types</span></span> | <span data-ttu-id="2a09c-132">説明</span><span class="sxs-lookup"><span data-stu-id="2a09c-132">Description</span></span> |
       |-------------------------|-------------|
       | <span data-ttu-id="2a09c-133">**この組織のディレクトリ内のアカウントのみ**</span><span class="sxs-lookup"><span data-stu-id="2a09c-133">**Accounts in this organizational directory only**</span></span> | <span data-ttu-id="2a09c-134">基幹業務 (LOB) アプリケーションを作成している場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-134">Select this option if you're building a line-of-business (LOB) application.</span></span> <span data-ttu-id="2a09c-135">アプリケーションをディレクトリに登録していない場合、このオプションは選択できません。</span><span class="sxs-lookup"><span data-stu-id="2a09c-135">This option is not available if you're not registering the application in a directory.</span></span><br><br><span data-ttu-id="2a09c-136">このオプションは、Azure AD のシングルテナントにのみマッピングします。</span><span class="sxs-lookup"><span data-stu-id="2a09c-136">This option maps to Azure AD only single-tenant.</span></span><br><br><span data-ttu-id="2a09c-137">これは、ディレクトリの外部にアプリを登録している場合を除き、既定のオプションです。</span><span class="sxs-lookup"><span data-stu-id="2a09c-137">This is the default option unless you're registering the app outside of a directory.</span></span> <span data-ttu-id="2a09c-138">アプリがディレクトリの外部に登録されている場合、既定のオプションは Azure AD マルチテナントと個人の Microsoft アカウントです。</span><span class="sxs-lookup"><span data-stu-id="2a09c-138">In cases where the app is registered outside of a directory, the default is Azure AD multi-tenant and personal Microsoft accounts.</span></span> |
       | <span data-ttu-id="2a09c-139">**組織のディレクトリ内のアカウント**</span><span class="sxs-lookup"><span data-stu-id="2a09c-139">**Accounts in any organizational directory**</span></span> | <span data-ttu-id="2a09c-140">企業および教育機関のすべてのユーザーを対象とする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-140">Select this option if you would like to target all business and educational customers.</span></span><br><br><span data-ttu-id="2a09c-141">このオプションは、Azure AD のマルチテナントにのみマッピングします。</span><span class="sxs-lookup"><span data-stu-id="2a09c-141">This option maps to an Azure AD only multi-tenant.</span></span><br><br><span data-ttu-id="2a09c-142">アプリを Azure AD のシングルテナントとしてのみ登録した場合は、[**認証**] ブレードを使用して、Azure AD マルチテナントに更新し、シングルテナントに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2a09c-142">If you registered the app as Azure AD only single-tenant, you can update it to be Azure AD multi-tenant and back to single-tenant through the **Authentication** blade.</span></span> |
       | <span data-ttu-id="2a09c-143">**組織のディレクトリ内のアカウントと個人用 Microsoft アカウント**</span><span class="sxs-lookup"><span data-stu-id="2a09c-143">**Accounts in any organizational directory and personal Microsoft accounts**</span></span> | <span data-ttu-id="2a09c-144">最も広い範囲の顧客を対象とする場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-144">Select this option to target the widest set of customers.</span></span><br><br><span data-ttu-id="2a09c-145">このオプションは、Azure AD マルチテナントと個人用 Microsoft アカウントにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="2a09c-145">This option maps to Azure AD multi-tenant and personal Microsoft accounts.</span></span><br><br><span data-ttu-id="2a09c-146">アプリを Azure AD マルチテナントと個人用 Microsoft アカウントとして登録した場合は、UI でこれを変更できません。</span><span class="sxs-lookup"><span data-stu-id="2a09c-146">If you registered the app as Azure AD multi-tenant and personal Microsoft accounts, you cannot change this in the UI.</span></span> <span data-ttu-id="2a09c-147">代わりに、アプリケーション マニフェスト エディターを使用して、サポートされているアカウントの種類を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a09c-147">Instead, you must use the application manifest editor to change the supported account types.</span></span> |

   - <span data-ttu-id="2a09c-148">**リダイレクト URI (オプション)** - 構築しているアプリの種類として **Web** または **パブリック クライアント (モバイルとデスクトップ)** を選択し、アプリケーションのリダイレクト URI (または応答 URL) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-148">**Redirect URI (optional)** - Select the type of app you're building, **Web** or **Public client (mobile & desktop)**, and then enter the redirect URI (or reply URL) for your application.</span></span>
       - <span data-ttu-id="2a09c-149">Web アプリケーションの場合は、アプリのベース URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-149">For web applications, provide the base URL of your app.</span></span> <span data-ttu-id="2a09c-150">たとえば、`http://localhost:31544` はローカル マシンで実行されている Web アプリの URL になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a09c-150">For example, `http://localhost:31544` might be the URL for a web app running on your local machine.</span></span> <span data-ttu-id="2a09c-151">ユーザーはこの URL を使用して、Web クライアント アプリケーションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2a09c-151">Users would use this URL to sign in to a web client application.</span></span>
       - <span data-ttu-id="2a09c-152">パブリック クライアント アプリケーションの場合は、トークンの応答を返す際に Azure AD が使用する URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-152">For public client applications, provide the URI used by Azure AD to return token responses.</span></span> <span data-ttu-id="2a09c-153">`myapp://auth` などのアプリケーションに固有の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-153">Enter a value specific to your application, such as `myapp://auth`.</span></span>

     <span data-ttu-id="2a09c-154">Web アプリケーションまたはネイティブ アプリケーションの具体的な例を見るには、「[クイック スタート](/azure/active-directory/develop/#quickstarts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a09c-154">To see specific examples for web applications or native applications, check out our [quickstarts](/azure/active-directory/develop/#quickstarts).</span></span>

     <span data-ttu-id="2a09c-155">終了したら、[**登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-155">When finished, select **Register**.</span></span>

4. <span data-ttu-id="2a09c-156">アプリケーションが Microsoft Defender for Endpoint にアクセスし、"アラートの読み取り" アクセス許可を割り当てるのを許可します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-156">Allow your Application to access Microsoft Defender for Endpoint and assign it 'Read alerts' permission:</span></span>

    - <span data-ttu-id="2a09c-157">アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択します。組織で  >    >  WindowsDefenderATP >を使用し **、WindowsDefenderATP** で選択します。 </span><span class="sxs-lookup"><span data-stu-id="2a09c-157">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and select on **WindowsDefenderATP**.</span></span>

    - <span data-ttu-id="2a09c-158">**注**: *WindowsDefenderATP* は元のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="2a09c-158">**Note**: *WindowsDefenderATP* does not appear in the original list.</span></span> <span data-ttu-id="2a09c-159">テキスト ボックスに名前を書き始め、表示を確認します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-159">Start writing its name in the text box to see it appear.</span></span>

      ![アクセス許可の追加](images/add-permission.png)

    - <span data-ttu-id="2a09c-161">[**委任されたアクセス許可の**  >  **アラート] を選択し、[アクセス**>を **追加する] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="2a09c-161">Choose **Delegated permissions** > **Alert.Read** > select **Add permissions**</span></span>

      ![アプリケーションのアクセス許可](images/application-permissions-public-client.png)

    - <span data-ttu-id="2a09c-163">**重要な注意**: 関連するアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-163">**Important note**: Select the relevant permissions.</span></span> <span data-ttu-id="2a09c-164">アラートの読み取りは、一例にすのみです。</span><span class="sxs-lookup"><span data-stu-id="2a09c-164">Read alerts is only an example.</span></span>

      <span data-ttu-id="2a09c-165">例えば</span><span class="sxs-lookup"><span data-stu-id="2a09c-165">For instance,</span></span>

      - <span data-ttu-id="2a09c-166">高度 [なクエリを実行するには、[](run-advanced-query-api.md)高度なクエリの実行] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-166">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
      - <span data-ttu-id="2a09c-167">デバイス [を分離するには、[](isolate-machine.md)コンピューターの分離] アクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-167">To [isolate a device](isolate-machine.md), select 'Isolate machine' permission</span></span>
      - <span data-ttu-id="2a09c-168">必要なアクセス許可を確認するには、呼 **び** 出す API の [アクセス許可] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-168">To determine which permission you need, view the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="2a09c-169">[同意 **の付与] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="2a09c-169">Select **Grant consent**</span></span>

      <span data-ttu-id="2a09c-170">**注**: アクセス許可を追加する度に、新しいアクセス許可を有効にするための同意の付与で選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a09c-170">**Note**: Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

      ![アクセス許可の付与のイメージ](images/grant-consent.png)

6. <span data-ttu-id="2a09c-172">アプリケーション ID とテナント ID を書き出します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-172">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="2a09c-173">アプリケーション ページで、[概要] に移動 **し** 、次の情報をコピーします。</span><span class="sxs-lookup"><span data-stu-id="2a09c-173">On your application page, go to **Overview** and copy the following information:</span></span>

   ![作成されたアプリ ID のイメージ](images/app-and-tenant-ids.png)


## <a name="get-an-access-token"></a><span data-ttu-id="2a09c-175">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="2a09c-175">Get an access token</span></span>

<span data-ttu-id="2a09c-176">AAD トークンの詳細については [、「Azure AD」を参照してください。](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="2a09c-176">For more information on AAD tokens, see [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-c"></a><span data-ttu-id="2a09c-177">C の使用#</span><span class="sxs-lookup"><span data-stu-id="2a09c-177">Using C#</span></span>

- <span data-ttu-id="2a09c-178">以下のクラスをアプリケーションにコピー/貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="2a09c-178">Copy/Paste the below class in your application.</span></span>
- <span data-ttu-id="2a09c-179">トークンを取得するには、アプリケーション ID、テナント ID、ユーザー名、およびパスワードで **AcquireUserTokenAsync** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-179">Use **AcquireUserTokenAsync** method with your application ID, tenant ID, user name, and password to acquire a token.</span></span>

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a><span data-ttu-id="2a09c-180">トークンを検証する</span><span class="sxs-lookup"><span data-stu-id="2a09c-180">Validate the token</span></span>

<span data-ttu-id="2a09c-181">正しいトークンを取得していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a09c-181">Verify to make sure you got a correct token:</span></span>
- <span data-ttu-id="2a09c-182">前の手順で取得したトークンを [JWT](https://jwt.ms) にコピー/貼り付けしてデコードする</span><span class="sxs-lookup"><span data-stu-id="2a09c-182">Copy/paste into [JWT](https://jwt.ms) the token you got in the previous step in order to decode it</span></span>
- <span data-ttu-id="2a09c-183">目的のアプリのアクセス許可を持つ 'scp' クレームを取得する検証</span><span class="sxs-lookup"><span data-stu-id="2a09c-183">Validate you get a 'scp' claim with the desired app permissions</span></span>
- <span data-ttu-id="2a09c-184">以下のスクリーンショットでは、チュートリアルでアプリから取得したデコードされたトークンを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2a09c-184">In the screenshot below you can see a decoded token acquired from the app in the tutorial:</span></span>

![トークン検証のイメージ](images/nativeapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a><span data-ttu-id="2a09c-186">トークンを使用して Microsoft Defender for Endpoint API にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2a09c-186">Use the token to access Microsoft Defender for Endpoint API</span></span>

- <span data-ttu-id="2a09c-187">使用する API を選択する - [サポートされている Microsoft Defender for Endpoint API](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="2a09c-187">Choose the API you want to use - [Supported Microsoft Defender for Endpoint APIs](exposed-apis-list.md)</span></span>
- <span data-ttu-id="2a09c-188">送信する HTTP 要求の承認ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)</span><span class="sxs-lookup"><span data-stu-id="2a09c-188">Set the Authorization header in the HTTP request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="2a09c-189">トークンの有効期限は 1 時間です (同じトークンで複数の要求を送信できます)</span><span class="sxs-lookup"><span data-stu-id="2a09c-189">The Expiration time of the token is 1 hour (you can send more than one request with the same token)</span></span>

- <span data-ttu-id="2a09c-190">メッセージを使用してアラートの一覧を取得する要求を送信 **するC#**</span><span class="sxs-lookup"><span data-stu-id="2a09c-190">Example of sending a request to get a list of alerts **using C#**</span></span> 

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a><span data-ttu-id="2a09c-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a09c-191">See also</span></span>
- [<span data-ttu-id="2a09c-192">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2a09c-192">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="2a09c-193">アプリケーション コンテキストを使用して Microsoft Defender for Endpoint にアクセスする</span><span class="sxs-lookup"><span data-stu-id="2a09c-193">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
