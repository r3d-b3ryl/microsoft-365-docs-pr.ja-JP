---
title: コネクタをアーカイブ Twitter データに展開する
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
description: 管理者は、Twitter データをインポートおよびアーカイブするためのネイティブコネクタを Microsoft 365 にセットアップできます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 01c4901544e47cd1c361a132e144440f00bd8504
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200830"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="f904c-104">コネクタをアーカイブ Twitter データに展開する</span><span class="sxs-lookup"><span data-stu-id="f904c-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="f904c-105">この記事では、Office 365 インポートサービスを使用して組織の Twitter アカウントから Microsoft 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f904c-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="f904c-106">このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「 [Set up a connector to Archive Twitter data ](archive-twitter-data-with-sample-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f904c-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="f904c-107">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f904c-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="f904c-108">に移動 <https://portal.azure.com> し、グローバル管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f904c-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Azure にサインインする](../media/TCimage01.png)

2. <span data-ttu-id="f904c-110">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Azure Active Directory に移動します。](../media/TCimage02.png)

3. <span data-ttu-id="f904c-112">左側のナビゲーションウィンドウで、[ **アプリの登録 (プレビュー)** ] をクリックし、[ **新しい登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![新しいアプリの登録を作成する](../media/TCimage03.png)

4. <span data-ttu-id="f904c-114">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="f904c-114">Register the application.</span></span> <span data-ttu-id="f904c-115">[ **リダイレクト URI (オプション)**] で、[アプリケーションの種類] ドロップダウンリストから [ **Web** ] を選択し、 `https://portal.azure.com` URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="f904c-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="f904c-116">https://portal.azure.comリダイレクト URI の種類</span><span class="sxs-lookup"><span data-stu-id="f904c-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="f904c-117">**アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="f904c-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="f904c-118">これらの Id は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="f904c-118">You use these IDs in later steps.</span></span>

    ![アプリケーション Id とディレクトリ Id をコピーして保存する](../media/TCimage05.png)

6. <span data-ttu-id="f904c-120">[ **証明書 & 新しいアプリのシークレット** ] および [ **クライアントシークレット** ] の下で、[ **新しいクライアントシークレット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![新しいクライアントシークレットを作成する](../media/TCimage06.png)

7. <span data-ttu-id="f904c-122">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="f904c-122">Create a new secret.</span></span> <span data-ttu-id="f904c-123">[説明] ボックスに、シークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="f904c-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![シークレットを入力して、[有効期限の期間] を選択する](../media/TCimage08.png)

8. <span data-ttu-id="f904c-125">シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="f904c-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="f904c-126">これは、後の手順で使用する AAD アプリケーションシークレットです。</span><span class="sxs-lookup"><span data-stu-id="f904c-126">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットをコピーして保存する](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="f904c-128">手順 2: GitHub から Azure アカウントにコネクタ web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="f904c-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="f904c-129">[この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)に移動し、[ **Azure への展開] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Azure ホームページに移動する](../media/FBCimage11.png)

2. <span data-ttu-id="f904c-131">[ **Azure への展開**] をクリックすると、カスタムテンプレートページを使用して azure portal にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f904c-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="f904c-132">[ **基本** と **設定** ] の詳細を入力し、[ **購入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![[リソースを作成し、ストレージアカウントを入力してください] をクリックします。](../media/FBCimage12.png)

    - <span data-ttu-id="f904c-134">**サブスクリプション:** Twitter connector web サービスを展開する Azure サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f904c-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="f904c-135">**リソースグループ:** 新しいリソースグループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="f904c-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="f904c-136">リソースグループは、Azure ソリューションの関連リソースを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="f904c-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="f904c-137">**場所:** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="f904c-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="f904c-138">**Web アプリ名:** コネクタ web アプリの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f904c-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="f904c-139">名前の長さは 3 ~ 18 文字でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f904c-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="f904c-140">この名前は、Azure app service の URL を作成するために使用されます。たとえば、 **twitterconnector** の Web アプリ名を指定すると、Azure app SERVICE の URL は **twitterconnector.azurewebsites.net**になります。</span><span class="sxs-lookup"><span data-stu-id="f904c-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="f904c-141">**tenantId:** 手順1で Azure Active Directory に Facebook connector アプリを作成した後にコピーした、Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="f904c-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="f904c-142">**APISecretKey:** 任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="f904c-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="f904c-143">これは、手順5でコネクタ web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f904c-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="f904c-144">展開に成功すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="f904c-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![[記憶域] をクリックし、[ストレージアカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="f904c-146">手順 3: Twitter アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f904c-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="f904c-147">に移動し https://developer.twitter.com て、組織の開発者アカウントの資格情報を使用してログインし、[ **アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![に移動 https://developer.twitter.com し、ログインします。](../media/TCimage25-5.png)
2. <span data-ttu-id="f904c-149">[ **アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-149">Click **Create an app**.</span></span>
   
   ![アプリページに移動してアプリを作成する](../media/TCimage26.png)

3. <span data-ttu-id="f904c-151">[ **アプリの詳細**] で、アプリケーションに関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="f904c-151">Under **App details**, add information about the application.</span></span>

   ![アプリに関する情報を入力する](../media/TCimage27.png)

4. <span data-ttu-id="f904c-153">Twitter 開発者ダッシュボードで、作成したばかりのアプリを選択し、[ **詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>
   
   ![アプリ Id をコピーして保存する](../media/TCimage28.png)

5. <span data-ttu-id="f904c-155">[ **キーとトークン** ] タブの [ **コンシューマー api キー** ] で、api キーと api シークレットキーの両方をコピーし、テキストファイルまたはその他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="f904c-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="f904c-156">次に、[ **作成** ] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f904c-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>
   
   ![API シークレットキーにコピーして保存する](../media/TCimage29.png)

   <span data-ttu-id="f904c-158">次に、[ **作成** ] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f904c-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="f904c-159">[ **アクセス許可** ] タブをクリックし、次のスクリーンショットに示されているようにアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="f904c-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![アクセス許可を構成する](../media/TCimage30.png)

7. <span data-ttu-id="f904c-161">アクセス許可の設定を保存した後、[ **アプリの詳細** ] タブをクリックし、[編集] をクリックして [ **詳細の編集 >** します。</span><span class="sxs-lookup"><span data-stu-id="f904c-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![アプリの詳細を編集する](../media/TCimage31.png)

8. <span data-ttu-id="f904c-163">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="f904c-163">Do the following tasks:</span></span>

   - <span data-ttu-id="f904c-164">チェックボックスをオンにして、コネクタアプリが Twitter にサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="f904c-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="f904c-165">次の形式を使用して OAuth リダイレクト Uri を追加します: \*\* \<connectorserviceuri> /Views/TwitterOAuth\**。ここで、*コネクタ\*の値は、組織の Azure app service URL です。たとえば、のように https://twitterconnector.azurewebsites.net/Views/TwitterOAuth なります。</span><span class="sxs-lookup"><span data-stu-id="f904c-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![コネクタアプリが Twitter にサインインして OAuth リダイレクト Uri を追加できるようにする](../media/TCimage32.png)

<span data-ttu-id="f904c-167">Twitter 開発者アプリを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="f904c-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="f904c-168">手順 4: コネクタ web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="f904c-168">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="f904c-169">Https://に移動 \<AzureAppResourceName> します (ここで、 **AzureAppResourceName** は、手順4で名前を付けた Azure app リソースの名前です)。</span><span class="sxs-lookup"><span data-stu-id="f904c-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="f904c-170">たとえば、名前が **twitterconnector**の場合は、に移動 https://twitterconnector.azurewebsites.net します。</span><span class="sxs-lookup"><span data-stu-id="f904c-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="f904c-171">アプリのホームページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="f904c-171">The home page of the app looks like the following screenshot:</span></span>

   ![Azure app リソースページに移動します。](../media/FBCimage41.png)

2. <span data-ttu-id="f904c-173">[ **構成** ] をクリックして、サインインページを表示します。</span><span class="sxs-lookup"><span data-stu-id="f904c-173">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインインページを表示する](../media/FBCimage42.png)

3. <span data-ttu-id="f904c-175">[テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。</span><span class="sxs-lookup"><span data-stu-id="f904c-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="f904c-176">[パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[ **構成設定の設定** ] をクリックして構成の詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="f904c-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![テナント Id と API シークレットキーを使用してサインインする](../media/TCimage35.png)

4. <span data-ttu-id="f904c-178">次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="f904c-178">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="f904c-179">**Twitter Api キー:** 手順3で作成した Twitter アプリケーションの API キー。</span><span class="sxs-lookup"><span data-stu-id="f904c-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f904c-180">**Twitter Api の秘密キー:** 手順3で作成した Twitter アプリケーションの API シークレットキー。</span><span class="sxs-lookup"><span data-stu-id="f904c-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f904c-181">**Twitter アクセストークン:** 手順3で作成したアクセストークン。</span><span class="sxs-lookup"><span data-stu-id="f904c-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f904c-182">**Twitter アクセストークンシークレット:** 手順3で作成したアクセストークンシークレット。</span><span class="sxs-lookup"><span data-stu-id="f904c-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="f904c-183">**AAD アプリケーション ID:** 手順1で作成した Azure Active Directory アプリのアプリケーション ID</span><span class="sxs-lookup"><span data-stu-id="f904c-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="f904c-184">**AAD アプリケーションシークレット:** 手順1で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="f904c-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="f904c-185">[ **保存** ] をクリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="f904c-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="f904c-186">手順 5: Microsoft 365 コンプライアンスセンターで Twitter connector をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f904c-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="f904c-187">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com) 、左側のナビゲーションで [ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="f904c-188">[ **データコネクタ** ] ページの [ **Twitter**] で、[ **表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="f904c-189">**Twitter**ページで、[**コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="f904c-190">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="f904c-191">[ **コネクタアプリの資格情報の追加** ] ページで、次の情報を入力し、[ **接続の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Connector アプリの資格情報を入力する](../media/TCimage38.png)

    - <span data-ttu-id="f904c-193">[ **名前** ] ボックスに、 **Twitter ヘルプハンドル**などのコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f904c-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="f904c-194">[ **コネクタの url** ] ボックスに、Azure app SERVICE の url を入力するか貼り付けます。例を示し `https://twitterconnector.azurewebsites.net` ます。</span><span class="sxs-lookup"><span data-stu-id="f904c-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="f904c-195">[ **パスワード** ] ボックスに、手順2で作成した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f904c-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="f904c-196">[ **Azure APP id** ] ボックスに、手順1で取得した Azure アプリケーションアプリ id ( *クライアント ID*とも呼ばれる) の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f904c-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="f904c-197">接続が正常に検証されたら、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="f904c-198">[ **Microsoft 365 にデータをインポートするための承認** ] ページで、APISecretKey をもう一度入力するか貼り付けて、[  **Login web app**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="f904c-199">[ **Twitter でログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="f904c-200">[Twitter サインイン] ページで、組織の Twitter アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="f904c-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Twitter アカウントにサインインする](../media/TCimage42.png)

   <span data-ttu-id="f904c-202">サインインした後、Twitter ページに次のメッセージが表示されます。 "Twitter Connector ジョブは正常にセットアップされました。"</span><span class="sxs-lookup"><span data-stu-id="f904c-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="f904c-203">[ **続行** ] をクリックして、Twitter connector の設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="f904c-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="f904c-204">[ **フィルターの設定** ] ページでは、特定の年齢のアイテムを最初にインポートするためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f904c-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="f904c-205">年齢を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="f904c-206">[ **ストレージの場所の選択** ] ページで、Twitter アイテムがインポートされる Microsoft 365 メールボックスの電子メールアドレスを入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f904c-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="f904c-207">[ **管理者に同意**する] で、[ **同意を提供** する] をクリックし、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f904c-207">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="f904c-208">組織内のデータにアクセスするために Office 365 Import service への同意を提供するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f904c-208">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="f904c-209">[ **次** へ] をクリックしてコネクタの設定を確認し、[ **完了** ] をクリックしてコネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="f904c-209">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="f904c-210">コンプライアンスセンターで **データコネクタ** ページに移動し、[ **コネクタ** ] タブをクリックしてインポートプロセスの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="f904c-210">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
