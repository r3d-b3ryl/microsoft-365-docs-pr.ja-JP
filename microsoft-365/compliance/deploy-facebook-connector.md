---
title: コネクタを展開して Facebook Business ページのデータをアーカイブする
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
description: 管理者は、Facebook Business ページをインポートおよびアーカイブするネイティブ コネクタを設定して、そのページMicrosoft 365。 このデータを Microsoft 365 にインポートした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619953"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="5a3b0-104">コネクタを展開して Facebook Business ページのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="5a3b0-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="5a3b0-105">この記事では、Office 365 Import サービスを使用して Facebook Business ページからデータをインポートするコネクタを展開する手順Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="5a3b0-106">このプロセスの概要と、Facebook コネクタの展開に必要な前提条件の一覧については、「コネクタをセットアップして Facebook データをアーカイブする」 [を参照してください](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="5a3b0-107">手順 1: アプリをアプリで作成Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5a3b0-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="5a3b0-108">グローバル管理者 <https://portal.azure.com> アカウントの資格情報を使用して、アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![AAD でアプリを作成する](../media/FBCimage1.png)

2. <span data-ttu-id="5a3b0-110">左側のナビゲーション ウィンドウで **[Azure Active Directory]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![[次Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="5a3b0-112">左側のナビゲーション ウィンドウで、[アプリの登録 ] **(プレビュー) をクリックし** 、[新しい登録] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![[**アプリの登録 (プレビュー)**] をクリックし、[**新しい登録** ] をクリックします。](../media/FBCimage3.png)

4. <span data-ttu-id="5a3b0-114">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-114">Register the application.</span></span> <span data-ttu-id="5a3b0-115">[リダイレクト URI] で、[アプリケーションの種類] ドロップダウン リストで [Web] を選択し <https://portal.azure.com> 、URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![アプリケーションの登録](../media/FBCimage4.png)

5. <span data-ttu-id="5a3b0-117">アプリケーション **(クライアント) ID とディレクトリ** **(テナント) ID** をコピーし、テキスト ファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="5a3b0-118">これらの ID は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-118">You use these IDs in later steps.</span></span>

   ![アプリケーション ID とディレクトリ ID をコピーして保存する](../media/FBCimage5.png)

6. <span data-ttu-id="5a3b0-120">新しい **アプリの&に移動します。**</span><span class="sxs-lookup"><span data-stu-id="5a3b0-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![新しいアプリの証明書&シークレットに移動します。](../media/FBCimage6.png)

7. <span data-ttu-id="5a3b0-122">[新 **しいクライアント シークレット] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="5a3b0-122">Click **New client secret**</span></span>

   ![[新しいクライアント シークレット] をクリックします。](../media/FBCimage7.png)

8. <span data-ttu-id="5a3b0-124">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-124">Create a new secret.</span></span> <span data-ttu-id="5a3b0-125">[説明] ボックスにシークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![シークレットを入力し、有効期限を選択する](../media/FBCimage8.png)

9. <span data-ttu-id="5a3b0-127">シークレットの値をコピーし、テキスト ファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="5a3b0-128">これは、後の手順で使用する AAD アプリケーション シークレットです。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-128">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットの値をコピーして保存する](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="5a3b0-130">手順 2: コネクタ Web サービスを Azure アカウントGitHubから展開する</span><span class="sxs-lookup"><span data-stu-id="5a3b0-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="5a3b0-131">このサイトに [移動しGitHub Azure](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) **に展開をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![[Azure に展開する] をクリックします。](../media/FBCGithubApp.png)

2. <span data-ttu-id="5a3b0-133">[Azure に **展開] をクリック** すると、カスタム テンプレート ページを使用して Azure ポータルにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="5a3b0-134">[基本] と **[詳細\*\*\*\*設定入力** し、[購入] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="5a3b0-135">**サブスクリプション:** Facebook Business ページ コネクタ Web サービスを展開する Azure サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="5a3b0-136">**リソース グループ:** 新しいリソース グループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="5a3b0-137">リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="5a3b0-138">**場所:** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="5a3b0-139">**Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="5a3b0-140">名前の長さは 3 ~ 18 文字です。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="5a3b0-141">この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば **、fbconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL が **fbconnector.azurewebsites.net。**</span><span class="sxs-lookup"><span data-stu-id="5a3b0-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="5a3b0-142">**tenantId:** 手順 1 で Facebook コネクタ Microsoft 365作成した後にコピーした組織のテナント ID Azure Active Directory ID です。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="5a3b0-143">**APISecretKey:** 任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="5a3b0-144">これは、手順 5 でコネクタ Web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-144">This is used to access the connector web app in Step 5.</span></span>

     ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

3. <span data-ttu-id="5a3b0-146">展開が成功すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![[アカウントStorage] をクリックし、[アカウント] Storageクリックします。](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="5a3b0-148">手順 3: Facebook アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="5a3b0-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="5a3b0-149">に移動し、組織の Facebook Business ページのアカウントの資格情報を使用してログインし、[新しいアプリの追加 <https://developers.facebook.com> ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Facebook ビジネス ページ用の新しいアプリを追加する](../media/FBCimage25.png)

2. <span data-ttu-id="5a3b0-151">新しいアプリ ID を作成します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-151">Create a new app ID.</span></span>

   ![新しいアプリ ID を作成する](../media/FBCimage26.png)

3. <span data-ttu-id="5a3b0-153">左側のナビゲーション ウィンドウで、[製品の追加] **を** クリックし、[Facebook **ログイン** ] タイルの [セットアップ] **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![[製品の追加] をクリックします。](../media/FBCimage27.png)

4. <span data-ttu-id="5a3b0-155">[Facebook ログインの統合] ページで、[Web] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![[Facebook ログインの統合] ページで [Web] をクリックします。](../media/FBCimage28.png)

5. <span data-ttu-id="5a3b0-157">Azure アプリ サービスの URL を追加します。たとえば `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="5a3b0-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Azure アプリ サービスの URL を追加する](../media/FBCimage29.png)

6. <span data-ttu-id="5a3b0-159">Facebook ログインのセットアップの [クイック スタート] セクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![[クイック スタート] セクションを完了する](../media/FBCimage30.png)

7. <span data-ttu-id="5a3b0-161">[Facebook ログイン]の下の左側のナビゲーション ウィンドウで、[設定]**をクリック** し、[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト **URI を追加** します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="5a3b0-162">**\<connectorserviceuri> /Views/FacebookOAuth** という形式を使用します。connectorserviceuri の値は組織の Azure アプリ サービス URL です。たとえば `https://fbconnector.azurewebsites.net` 、 。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI を追加する](../media/FBCimage31.png)

8. <span data-ttu-id="5a3b0-164">左側のナビゲーション ウィンドウで、[製品の追加]**をクリックし\*\*\*\*、[Webhooks] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="5a3b0-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="5a3b0-165">[ページ **] プルダウン メニュー** で、[ページ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![[製品の追加] をクリックし、[\*\*Webhooks] をクリックします。](../media/FBCimage32.png)

9. <span data-ttu-id="5a3b0-167">Webhooks コールバック URL を追加し、確認トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="5a3b0-168">コールバック URL の形式は **<connectorserviceuri> 、/api/FbPageWebhook** という形式を使用します。connectorserviceuri の値は、組織の Azure アプリ サービス URL です。たとえば、 を指定します `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="5a3b0-169">確認トークンは強力なパスワードと似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="5a3b0-170">確認トークンをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-170">Copy the verify token to a text file or other storage location.</span></span>

   ![検証トークンの追加](../media/FBCimage33.png)

10. <span data-ttu-id="5a3b0-172">フィードのエンドポイントをテストしてサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-172">Test and subscribe to the endpoint for feed.</span></span>

    ![エンドポイントのテストとサブスクライブ](../media/FBCimage34.png)

11. <span data-ttu-id="5a3b0-174">プライバシー URL、アプリ アイコン、およびビジネス使用を追加します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="5a3b0-175">また、アプリ ID とアプリ シークレットをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![プライバシー URL、アプリ アイコン、およびビジネスの使用を追加する](../media/FBCimage35.png)

12. <span data-ttu-id="5a3b0-177">アプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-177">Make the app public.</span></span>

    ![アプリを公開する](../media/FBCimage36.png)

13. <span data-ttu-id="5a3b0-179">管理者またはテスターの役割にユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-179">Add user to the admin or tester role.</span></span>

    ![管理者またはテスターの役割にユーザーを追加する](../media/FBCimage37.png)

14. <span data-ttu-id="5a3b0-181">[ページパブリック **コンテンツ アクセス] アクセス許可を追加** します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd the Page Public Content Access permission](../media/FBCimage38.png)

15. <span data-ttu-id="5a3b0-183">[ページの管理] アクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-183">Add Manage Pages permission.</span></span>

    ![[ページの管理] アクセス許可の追加](../media/FBCimage39.png)

16. <span data-ttu-id="5a3b0-185">Facebook によってレビューされたアプリケーションを取得します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-185">Get the application reviewed by Facebook.</span></span>

    ![Facebook でレビューされたアプリケーションを取得する](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="5a3b0-187">手順 4: コネクタ Web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="5a3b0-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="5a3b0-188">に移動 `https://<AzureAppResourceName>.azurewebsites.net` します (AzureAppResourceName は、手順 4 で指定した Azure アプリ リソースの名前です)。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="5a3b0-189">たとえば、名前が **fbconnector** の場合は、 に移動します `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="5a3b0-190">アプリのホーム ページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-190">The home page of the app will look like the following screenshot:</span></span>

   ![コネクタ Web アプリに移動する](../media/FBCimage41.png)

2. <span data-ttu-id="5a3b0-192">[構成 **] を** クリックしてサインイン ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-192">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインイン ページを表示する](../media/FBCimage42.png)

3. <span data-ttu-id="5a3b0-194">[テナント ID] ボックスに、テナント ID (手順 2 で取得した) を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="5a3b0-195">パスワード ボックスに、APISecretKey (手順 2 で取得した) を入力または貼り付け、[構成の設定] 設定 をクリックして構成の詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![テナント ID とパスワードを使用してサインインし、[構成の詳細] ページに移動します。](../media/FBCimage43.png)

4. <span data-ttu-id="5a3b0-197">次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="5a3b0-198">**Facebook アプリケーション ID:** 手順 3 で取得した Facebook アプリケーションのアプリ ID。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="5a3b0-199">**Facebook アプリケーション シークレット:** 手順 3 で取得した Facebook アプリケーションのアプリ シークレット。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="5a3b0-200">**Facebook Webhooks はトークンを確認します。** 手順 3 で作成した検証トークン。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="5a3b0-201">**AAD アプリケーション ID:** 手順 1 で作成した Azure Active Directory アプリのアプリケーション ID。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="5a3b0-202">**AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="5a3b0-203">[保存 **] を** クリックしてコネクタ設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="5a3b0-204">手順 5: Microsoft 365 コンプライアンス センターで Facebook コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5a3b0-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="5a3b0-205">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com) し、左側の **ナビゲーションで [** データ コネクタ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="5a3b0-206">[データ コネクタ **] ページの [Facebook** Business ページ] で **、[** 表示] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="5a3b0-207">[Facebook のビジネス **ページ] ページで** 、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="5a3b0-208">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="5a3b0-209">[コネクタ **アプリの資格情報の追加]** ページで、次の情報を入力し、[接続の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![コネクタ アプリの資格情報を入力する](../media/TCimage38.png)

   - <span data-ttu-id="5a3b0-211">[名前 **] ボックス** に、Facebook ニュース ページなどのコネクタの **名前を入力します**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="5a3b0-212">[接続 **URL] ボックス** に、Azure アプリ サービスの URL を入力または貼り付けます。たとえば `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="5a3b0-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="5a3b0-213">[パスワード **] ボックス** に、手順 2 で追加した APISecretKey の値を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="5a3b0-214">[Azure **App ID]** ボックスに、手順 1 で作成した AAD アプリケーション ID とも呼ばれるアプリケーション (クライアント) ID の値を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="5a3b0-215">接続が正常に検証された後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="5a3b0-216">[ **データのインポートを Microsoft 365** に承認する] ページで、APISecretKey を再度入力または貼り付け、[Web アプリのログイン] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="5a3b0-217">[Facebook **コネクタ アプリの構成** ] ページで **、[Facebook** でログイン] をクリックし、組織の Facebook Business ページのアカウントの資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="5a3b0-218">ログインした Facebook アカウントに、組織の Facebook Business ページの管理者ロールが割り当てられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Facebook でログインする](../media/FBCimage50.png)

9. <span data-ttu-id="5a3b0-220">ログインした Facebook アカウントによって管理されているビジネス ページの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="5a3b0-221">アーカイブするページを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-221">Select the page to archive and then click **Next**.</span></span>

   ![アーカイブする組織のビジネス ページを選択する](../media/FBCimage52.png)

10. <span data-ttu-id="5a3b0-223">[ **続行] を** クリックして、コネクタ サービス アプリのセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="5a3b0-224">[フィルター **の設定] ページ** で、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="5a3b0-225">年齢を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="5a3b0-226">[保存 **場所の選択** ] ページで、Facebook アイテムをインポートする Microsoft 365 メールボックスの電子メール アドレスを入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="5a3b0-227">[ **次へ]** をクリックしてコネクタの設定を確認し、[完了] を **クリックして** コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="5a3b0-228">コンプライアンス センターで、[データ コネクタ] ページに **移動** し、[コネクタ] タブをクリックしてインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a3b0-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
