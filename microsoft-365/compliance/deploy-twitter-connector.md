---
title: コネクタを展開して Twitter データをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Twitter データをインポートおよびアーカイブするネイティブ コネクタをセットアップして、ユーザーにMicrosoft 365。 このデータを Microsoft 365 にインポートした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227057"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="1e02a-104">コネクタを展開して Twitter データをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="1e02a-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="1e02a-105">この記事では、Office 365 Import サービスを使用して組織の Twitter アカウントから Microsoft 365 にデータをインポートするコネクタを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="1e02a-106">このプロセスの概要と、Twitter コネクタの展開に必要な前提条件の一覧については、「コネクタをセットアップして Twitter データをアーカイブする」 [を参照してください ](archive-twitter-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="1e02a-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="1e02a-107">手順 1: アプリをアプリで作成Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e02a-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="1e02a-108">グローバル管理者 <https://portal.azure.com> アカウントの資格情報を使用して、アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Azure にサインインする](../media/TCimage01.png)

2. <span data-ttu-id="1e02a-110">左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![[ユーザー] に移動Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="1e02a-112">左側のナビゲーション ウィンドウで、[アプリの登録 ] **(プレビュー) をクリックし** 、[新しい登録] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![新しいアプリ登録を作成する](../media/TCimage03.png)

4. <span data-ttu-id="1e02a-114">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-114">Register the application.</span></span> <span data-ttu-id="1e02a-115">[ **リダイレクト URI (省略可能)]** で、[アプリケーションの種類] ドロップダウン リストで **[Web]** を選択し `https://portal.azure.com` 、URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![リダイレクト https://portal.azure.com URI の種類](../media/TCimage04.png)

5. <span data-ttu-id="1e02a-117">アプリケーション **(クライアント) ID とディレクトリ** **(テナント) ID** をコピーし、テキスト ファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="1e02a-118">これらの ID は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-118">You use these IDs in later steps.</span></span>

    ![アプリケーション ID とディレクトリ ID をコピーして保存する](../media/TCimage05.png)

6. <span data-ttu-id="1e02a-120">[新しい **アプリの証明書&シークレット** ] に移動し、[クライアント シークレット] の下の [新 **しいクライアント** シークレット] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![新しいクライアント シークレットを作成する](../media/TCimage06.png)

7. <span data-ttu-id="1e02a-122">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-122">Create a new secret.</span></span> <span data-ttu-id="1e02a-123">[説明] ボックスにシークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-123">In the description box, type the secret and then choose an expiration period.</span></span>

   ![シークレットを入力し、有効期限を選択する](../media/TCimage08.png)

8. <span data-ttu-id="1e02a-125">シークレットの値をコピーし、テキスト ファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="1e02a-126">これは、後の手順で使用する AAD アプリケーション シークレットです。</span><span class="sxs-lookup"><span data-stu-id="1e02a-126">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットをコピーして保存する](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="1e02a-128">手順 2: コネクタ Web サービスを Azure アカウントGitHubから展開する</span><span class="sxs-lookup"><span data-stu-id="1e02a-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="1e02a-129">このサイトに [移動しGitHub Azure](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) **に展開をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Azure のホーム ページに移動する](../media/FBCimage11.png)

2. <span data-ttu-id="1e02a-131">[Azure に **展開] をクリック** すると、カスタム テンプレート ページを使用して Azure ポータルにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="1e02a-132">[基本] と **[詳細\*\*\*\*設定入力** し、[購入] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

    - <span data-ttu-id="1e02a-134">**サブスクリプション:** Twitter コネクタ Web サービスを展開する Azure サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>

    - <span data-ttu-id="1e02a-135">**リソース グループ:** 新しいリソース グループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="1e02a-136">リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="1e02a-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="1e02a-137">**場所:** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="1e02a-138">**Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="1e02a-139">名前の長さは 3 ~ 18 文字です。</span><span class="sxs-lookup"><span data-stu-id="1e02a-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="1e02a-140">この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば **、twitterconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL が **twitterconnector.azurewebsites.net。**</span><span class="sxs-lookup"><span data-stu-id="1e02a-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>

    - <span data-ttu-id="1e02a-141">**tenantId:** 手順 1 で Azure Active Directory で Facebook コネクタ Microsoft 365作成した後にコピーした組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="1e02a-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>

   - <span data-ttu-id="1e02a-142">**APISecretKey:** 任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="1e02a-143">これは、手順 5 でコネクタ Web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="1e02a-144">展開が成功すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="1e02a-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![[アカウントStorage] をクリックし、[アカウント] Storageクリックします。](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="1e02a-146">手順 3: Twitter アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="1e02a-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="1e02a-147">に移動し、組織の開発者アカウントの資格情報を使用してログインし、[アプリ https://developer.twitter.com ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![に移動 https://developer.twitter.com してログインする](../media/TCimage25-5.png)
2. <span data-ttu-id="1e02a-149">[アプリ **の作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-149">Click **Create an app**.</span></span>

   ![[アプリ] ページに移動してアプリを作成する](../media/TCimage26.png)

3. <span data-ttu-id="1e02a-151">[ **アプリの詳細]** で、アプリケーションに関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-151">Under **App details**, add information about the application.</span></span>

   ![アプリに関する情報を入力する](../media/TCimage27.png)

4. <span data-ttu-id="1e02a-153">Twitter 開発者ダッシュボードで、作成したアプリを選択し、[詳細] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>

   ![アプリ ID をコピーして保存する](../media/TCimage28.png)

5. <span data-ttu-id="1e02a-155">[キー **とトークン]** タブの [コンシューマー API キー] で **、API** キーと API シークレット キーの両方をコピーし、テキスト ファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="1e02a-156">次に、[ **作成]** をクリックしてアクセス トークンとアクセス トークン シークレットを生成し、これらをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>

   ![API シークレット キーにコピーして保存する](../media/TCimage29.png)

   <span data-ttu-id="1e02a-158">次に、[ **作成]** をクリックしてアクセス トークンとアクセス トークン シークレットを生成し、これらをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="1e02a-159">[アクセス許可 **] タブを** クリックし、次のスクリーンショットに示すようにアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![アクセス許可を構成する](../media/TCimage30.png)

7. <span data-ttu-id="1e02a-161">アクセス許可設定を保存したら、[アプリの詳細] タブをクリックし、[詳細の編集] >**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![アプリの詳細を編集する](../media/TCimage31.png)

8. <span data-ttu-id="1e02a-163">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-163">Do the following tasks:</span></span>

   - <span data-ttu-id="1e02a-164">コネクタ アプリが Twitter にサインインするには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>

   - <span data-ttu-id="1e02a-165">次の形式を使用して OAuth リダイレクト Uri を追加します。 **\<connectorserviceuri> /Views/TwitterOAuth** *、connectorserviceuri* の値は、組織の Azure アプリ サービス URL です。たとえば https://twitterconnector.azurewebsites.net/Views/TwitterOAuth 。</span><span class="sxs-lookup"><span data-stu-id="1e02a-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![コネクタ アプリによる Twitter へのサインインと OAuth リダイレクト Uri の追加を許可する](../media/TCimage32.png)

<span data-ttu-id="1e02a-167">これで、Twitter 開発者アプリを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="1e02a-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="1e02a-168">手順 4: コネクタ Web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="1e02a-168">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="1e02a-169">[https:// \<AzureAppResourceName> .azurewebsites.net に移動します **(AzureAppResourceName** は、手順 4 で指定した Azure アプリ リソースの名前です)。</span><span class="sxs-lookup"><span data-stu-id="1e02a-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="1e02a-170">たとえば、名前が **twitterconnector の場合は**、 に移動します https://twitterconnector.azurewebsites.net 。</span><span class="sxs-lookup"><span data-stu-id="1e02a-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="1e02a-171">アプリのホーム ページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="1e02a-171">The home page of the app looks like the following screenshot:</span></span>

   ![[Azure アプリ リソース] ページに移動する](../media/FBCimage41.png)

2. <span data-ttu-id="1e02a-173">[構成 **] を** クリックしてサインイン ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-173">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインイン ページを表示する](../media/FBCimage42.png)

3. <span data-ttu-id="1e02a-175">[テナント ID] ボックスに、テナント ID (手順 2 で取得した) を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="1e02a-176">パスワード ボックスに、APISecretKey (手順 2 で取得した) を入力または貼り付け、[構成の設定] 設定 をクリックして構成の詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![テナント ID と API シークレット キーを使用してサインインする](../media/TCimage35.png)

4. <span data-ttu-id="1e02a-178">次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-178">Enter the following configuration settings</span></span>

   - <span data-ttu-id="1e02a-179">**Twitter Api キー:** 手順 3 で作成した Twitter アプリケーションの API キー。</span><span class="sxs-lookup"><span data-stu-id="1e02a-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="1e02a-180">**Twitter Api シークレット キー:** 手順 3 で作成した Twitter アプリケーションの API シークレット キー。</span><span class="sxs-lookup"><span data-stu-id="1e02a-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="1e02a-181">**Twitter アクセス トークン:** 手順 3 で作成したアクセス トークン。</span><span class="sxs-lookup"><span data-stu-id="1e02a-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>

   - <span data-ttu-id="1e02a-182">**Twitter Access トークン シークレット:** 手順 3 で作成したアクセス トークン シークレット。</span><span class="sxs-lookup"><span data-stu-id="1e02a-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>

   - <span data-ttu-id="1e02a-183">**AAD アプリケーション ID:** 手順 1 で作成Azure Active Directoryアプリのアプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="1e02a-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>

   - <span data-ttu-id="1e02a-184">**AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="1e02a-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="1e02a-185">[保存 **] を** クリックしてコネクタ設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1e02a-186">手順 5: アプリケーションで Twitter コネクタをセットアップMicrosoft 365 コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="1e02a-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="1e02a-187">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、左側の **ナビゲーションで [** データ コネクタ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1e02a-188">[Twitter]**の [データ コネクタ] ページ\*\*\*\*で、[表示**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="1e02a-189">Twitter ページで **、[コネクタの** 追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="1e02a-190">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="1e02a-191">[コネクタ **アプリの資格情報の追加]** ページで、次の情報を入力し、[接続の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![コネクタ アプリの資格情報を入力する](../media/TCimage38.png)

    - <span data-ttu-id="1e02a-193">[名前 **] ボックス** に、Twitter ヘルプ ハンドルなどのコネクタの **名前を入力します**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>

    - <span data-ttu-id="1e02a-194">[コネクタ **の URL] ボックス** に、Azure アプリ サービスの URL を入力または貼り付けます。たとえば `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1e02a-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>

    - <span data-ttu-id="1e02a-195">[パスワード **] ボックス** に、手順 2 で作成した APISecretKey の値を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>

    - <span data-ttu-id="1e02a-196">[Azure **App ID]** ボックスに、手順 1 で取得した Azure Application App ID (クライアント *ID* とも呼ばれる) の値を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="1e02a-197">接続が正常に検証された後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="1e02a-198">[データの **インポートMicrosoft 365承認する**] ページで、APISecretKey を再度入力または貼り付け、[Web アプリのログイン]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="1e02a-199">[Twitter **でログイン] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="1e02a-200">[Twitter サインイン] ページで、組織の Twitter アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1e02a-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Twitter アカウントにサインインする](../media/TCimage42.png)

   <span data-ttu-id="1e02a-202">サインインすると、Twitter ページに「Twitter Connector Job 正常にセットアップされました」というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="1e02a-203">[続行 **] を** クリックして、Twitter コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="1e02a-204">[フィルター **の設定] ページ** で、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="1e02a-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="1e02a-205">年齢を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="1e02a-206">[保存 **場所の選択**] ページで、Twitter アイテムMicrosoft 365するメールボックスの電子メール アドレスを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1e02a-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="1e02a-207">[ **次へ]** をクリックしてコネクタの設定を確認し、[完了] を **クリックして** コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="1e02a-208">コンプライアンス センターで、[データ コネクタ] ページに **移動** し、[コネクタ] タブをクリックしてインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="1e02a-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
