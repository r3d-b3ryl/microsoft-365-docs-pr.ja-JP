---
title: コネクタを展開して Facebook ビジネス ページのデータをアーカイブする
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
description: 管理者は、Microsoft 365 に Facebook Business ページをインポートしてアーカイブするネイティブ コネクタを設定できます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619953"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="406fa-104">コネクタを展開して Facebook ビジネス ページのデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="406fa-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="406fa-105">この記事では、Office 365 インポート サービスを使用して Facebook Business ページから Microsoft 365 にデータをインポートするコネクタを展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="406fa-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="406fa-106">このプロセスの概要と、Facebook コネクタを展開するために必要な前提条件の一覧については、「コネクタをセットアップして Facebook データをアーカイブする」を参照 [してください](archive-facebook-data-with-sample-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="406fa-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="406fa-107">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="406fa-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="406fa-108">グローバル管理者 <https://portal.azure.com> アカウントの資格情報を使用して、アクセスしてサインインします。</span><span class="sxs-lookup"><span data-stu-id="406fa-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![AAD でアプリを作成する](../media/FBCimage1.png)

2. <span data-ttu-id="406fa-110">左側のナビゲーション ウィンドウで **、Azure Active Directory をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![[Azure Active Directory] をクリックします。](../media/FBCimage2.png)

3. <span data-ttu-id="406fa-112">左側のナビゲーション ウィンドウで、アプリの登録 **(プレビュー)** をクリックし、[新しい登録] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. <span data-ttu-id="406fa-114">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="406fa-114">Register the application.</span></span> <span data-ttu-id="406fa-115">[リダイレクト URI] で、アプリケーションの種類のドロップダウン リストで [Web] を選択し、URI のボックス <https://portal.azure.com> に入力します。</span><span class="sxs-lookup"><span data-stu-id="406fa-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![アプリケーションの登録](../media/FBCimage4.png)

5. <span data-ttu-id="406fa-117">アプリケーション **(クライアント) ID と\*\*\*\*ディレクトリ (テナント) ID** をコピーし、テキスト ファイルなどの安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="406fa-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="406fa-118">これらの ID は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="406fa-118">You use these IDs in later steps.</span></span>

   ![アプリケーション ID とディレクトリ ID をコピーして保存する](../media/FBCimage5.png)

6. <span data-ttu-id="406fa-120">新しい **アプリの&証明書とシークレットに移動します。**</span><span class="sxs-lookup"><span data-stu-id="406fa-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![新しいアプリの証明書&シークレットに移動します。](../media/FBCimage6.png)

7. <span data-ttu-id="406fa-122">[新 **しいクライアント シークレット] をクリックする**</span><span class="sxs-lookup"><span data-stu-id="406fa-122">Click **New client secret**</span></span>

   ![[新しいクライアント シークレット] をクリックする](../media/FBCimage7.png)

8. <span data-ttu-id="406fa-124">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="406fa-124">Create a new secret.</span></span> <span data-ttu-id="406fa-125">説明ボックスにシークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="406fa-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![シークレットを入力し、有効期限を選択する](../media/FBCimage8.png)

9. <span data-ttu-id="406fa-127">シークレットの値をコピーし、テキスト ファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="406fa-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="406fa-128">これは、後の手順で使用する AAD アプリケーション シークレットです。</span><span class="sxs-lookup"><span data-stu-id="406fa-128">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットの値をコピーして保存する](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="406fa-130">手順 2: GitHub から Azure アカウントにコネクタ Web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="406fa-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="406fa-131">この [GitHub サイトに移動し、[Azure](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) に展開 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![[Azure への展開] をクリックします。](../media/FBCGithubApp.png)

2. <span data-ttu-id="406fa-133">[Azure に **展開] を** クリックすると、カスタム テンプレート ページを使用して Azure Portal にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="406fa-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="406fa-134">[基本と **設定] の詳細** を **入力し、[** 購入] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="406fa-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="406fa-135">**サブスクリプション:** Facebook Business ページ コネクタ Web サービスを展開する Azure サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="406fa-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="406fa-136">**リソース グループ:** 新しいリソース グループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="406fa-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="406fa-137">リソース グループは、Azure ソリューションの関連リソースを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="406fa-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="406fa-138">**場所:** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="406fa-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="406fa-139">**Web アプリ名:** コネクタ Web アプリの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="406fa-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="406fa-140">名前の長さは 3 ~ 18 文字です。</span><span class="sxs-lookup"><span data-stu-id="406fa-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="406fa-141">この名前は、Azure アプリ サービスの URL を作成するために使用されます。たとえば **、fbconnector** の Web アプリ名を指定すると、Azure アプリ サービスの URL が **fbconnector.azurewebsites.net。**</span><span class="sxs-lookup"><span data-stu-id="406fa-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="406fa-142">**tenantId:** 手順 1 で Azure Active Directory で Facebook コネクタ アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="406fa-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="406fa-143">**APISecretKey:** 任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="406fa-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="406fa-144">これは、手順 5 でコネクタ Web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="406fa-144">This is used to access the connector web app in Step 5.</span></span>

     ![[リソースの作成] をクリックし、ストレージ アカウントを入力します。](../media/FBCimage12.png)

3. <span data-ttu-id="406fa-146">展開が成功すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="406fa-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![[ストレージ] をクリックし、[ストレージ アカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="406fa-148">手順 3: Facebook アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="406fa-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="406fa-149">に移動し、組織の Facebook Business ページのアカウントの資格情報を使用してログインし、[新しいアプリの追加] を <https://developers.facebook.com> **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Facebook ビジネス ページ用の新しいアプリを追加する](../media/FBCimage25.png)

2. <span data-ttu-id="406fa-151">新しいアプリ ID を作成します。</span><span class="sxs-lookup"><span data-stu-id="406fa-151">Create a new app ID.</span></span>

   ![新しいアプリ ID を作成する](../media/FBCimage26.png)

3. <span data-ttu-id="406fa-153">左側のナビゲーション ウィンドウで、[製品の追加]をクリックし、[Facebook ログイン] タイルの [**セットアップ] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="406fa-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![[製品の追加] をクリックします。](../media/FBCimage27.png)

4. <span data-ttu-id="406fa-155">[Facebook ログインの統合] ページで **、[Web] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![[Facebook ログインの統合] ページで [Web] をクリックする](../media/FBCimage28.png)

5. <span data-ttu-id="406fa-157">Azure アプリ サービスの URL を追加します。次に例を示します `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="406fa-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Azure アプリ サービスの URL を追加する](../media/FBCimage29.png)

6. <span data-ttu-id="406fa-159">Facebook ログインのセットアップのクイック スタート セクションに入力します。</span><span class="sxs-lookup"><span data-stu-id="406fa-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![クイック スタート セクションを完了する](../media/FBCimage30.png)

7. <span data-ttu-id="406fa-161">左側のナビゲーション ウィンドウの **Facebook** ログインで、[設定] をクリックし、[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI **を追加** します。</span><span class="sxs-lookup"><span data-stu-id="406fa-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="406fa-162">**\<connectorserviceuri> 形式 /Views/FacebookOAuth** を使用します。connectorserviceuri の値は、組織の Azure アプリ サービスの URL です。たとえば `https://fbconnector.azurewebsites.net` 、 .</span><span class="sxs-lookup"><span data-stu-id="406fa-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![[有効な OAuth リダイレクト URI] ボックスに OAuth リダイレクト URI を追加する](../media/FBCimage31.png)

8. <span data-ttu-id="406fa-164">左側のナビゲーション ウィンドウで、[製品の追加]**をクリックし\*\*\*\*、[Webhook] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="406fa-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="406fa-165">[ページ **] の** プル ダウン メニューで、[ページ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![[製品の追加] をクリックし、[\*\*Webhooks] をクリックします。](../media/FBCimage32.png)

9. <span data-ttu-id="406fa-167">Webhook コールバック URL を追加し、確認トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="406fa-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="406fa-168">コールバック URL の形式は **<connectorserviceuri> 、/api/FbPageWebhook** という形式を使用します。ここで、connectorserviceuri の値は組織の Azure アプリ サービス URL です。たとえば `https://fbconnector.azurewebsites.net` 、 .</span><span class="sxs-lookup"><span data-stu-id="406fa-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="406fa-169">検証トークンは強力なパスワードに似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="406fa-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="406fa-170">検証トークンをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="406fa-170">Copy the verify token to a text file or other storage location.</span></span>

   ![確認トークンを追加する](../media/FBCimage33.png)

10. <span data-ttu-id="406fa-172">フィード用にエンドポイントをテストしてサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="406fa-172">Test and subscribe to the endpoint for feed.</span></span>

    ![エンドポイントのテストとサブスクライブ](../media/FBCimage34.png)

11. <span data-ttu-id="406fa-174">プライバシー URL、アプリ アイコン、およびビジネスでの使用を追加します。</span><span class="sxs-lookup"><span data-stu-id="406fa-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="406fa-175">また、アプリ ID とアプリ シークレットをテキスト ファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="406fa-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![プライバシー URL、アプリ アイコン、およびビジネスでの使用を追加する](../media/FBCimage35.png)

12. <span data-ttu-id="406fa-177">アプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="406fa-177">Make the app public.</span></span>

    ![アプリを公開する](../media/FBCimage36.png)

13. <span data-ttu-id="406fa-179">管理者ロールまたはテスター ロールにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="406fa-179">Add user to the admin or tester role.</span></span>

    ![管理者またはテスターロールにユーザーを追加する](../media/FBCimage37.png)

14. <span data-ttu-id="406fa-181">ページ パブリック **コンテンツ アクセスのアクセス許可を追加** します。</span><span class="sxs-lookup"><span data-stu-id="406fa-181">Add the **Page Public Content Access** permission.</span></span>

    ![ページ パブリック コンテンツ アクセスのアクセス許可を dd](../media/FBCimage38.png)

15. <span data-ttu-id="406fa-183">ページの管理権限を追加します。</span><span class="sxs-lookup"><span data-stu-id="406fa-183">Add Manage Pages permission.</span></span>

    ![ページの管理権限を追加する](../media/FBCimage39.png)

16. <span data-ttu-id="406fa-185">Facebook によってレビューされたアプリケーションを取得します。</span><span class="sxs-lookup"><span data-stu-id="406fa-185">Get the application reviewed by Facebook.</span></span>

    ![Facebook によってレビューされたアプリケーションを取得する](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="406fa-187">手順 4: コネクタ Web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="406fa-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="406fa-188">(AzureAppResourceName は手順 4 で指定した Azure アプリ リソースの名前です) に `https://<AzureAppResourceName>.azurewebsites.net` 移動します。</span><span class="sxs-lookup"><span data-stu-id="406fa-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="406fa-189">たとえば、名前が **fbconnector の場合は**、移動します `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="406fa-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="406fa-190">アプリのホーム ページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="406fa-190">The home page of the app will look like the following screenshot:</span></span>

   ![Go to you connector web app](../media/FBCimage41.png)

2. <span data-ttu-id="406fa-192">[ **構成] を** クリックしてサインイン ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="406fa-192">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインイン ページを表示する](../media/FBCimage42.png)

3. <span data-ttu-id="406fa-194">[テナント ID] ボックスに、テナント ID (手順 2 で取得した ID) を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="406fa-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="406fa-195">パスワード ボックスに、APISecretKey (手順 2 で取得したキー) を入力するか貼り付け、[構成設定の設定] をクリックして構成の詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="406fa-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![テナント ID とパスワードを使用してサインインし、構成の詳細ページに移動する](../media/FBCimage43.png)

4. <span data-ttu-id="406fa-197">次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="406fa-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="406fa-198">**Facebook アプリケーション ID:** 手順 3 で取得した Facebook アプリケーションのアプリ ID。</span><span class="sxs-lookup"><span data-stu-id="406fa-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="406fa-199">**Facebook アプリケーション シークレット:** 手順 3 で取得した Facebook アプリケーションのアプリ シークレット。</span><span class="sxs-lookup"><span data-stu-id="406fa-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="406fa-200">**Facebook webhooks はトークンを確認します。** 手順 3 で作成した検証トークン。</span><span class="sxs-lookup"><span data-stu-id="406fa-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="406fa-201">**AAD アプリケーション ID:** 手順 1 で作成した Azure Active Directory アプリのアプリケーション ID。</span><span class="sxs-lookup"><span data-stu-id="406fa-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="406fa-202">**AAD アプリケーション シークレット:** 手順 1 で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="406fa-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="406fa-203">[ **保存] を** クリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="406fa-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="406fa-204">手順 5: Microsoft 365 コンプライアンス センターで Facebook コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="406fa-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="406fa-205">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの [ **データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="406fa-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="406fa-206">[データ **コネクタ] ページの** Facebook ビジネス ページ **で、[表示**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="406fa-207">Facebook の **ビジネス ページで、[コネクタの** 追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="406fa-208">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="406fa-209">[コネクタ **アプリの資格情報の追加** ] ページで、次の情報を入力し、[接続の検証] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![コネクタ アプリの資格情報を入力する](../media/TCimage38.png)

   - <span data-ttu-id="406fa-211">[名前 **] ボックス** に、コネクタの名前 (Facebook のニュース ページなど) **を入力します**。</span><span class="sxs-lookup"><span data-stu-id="406fa-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="406fa-212">[接続 **URL] ボックス** に、Azure アプリ サービスの URL を入力するか貼り付けます。次に例を示します `https://fbconnector.azurewebsites.net` 。</span><span class="sxs-lookup"><span data-stu-id="406fa-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="406fa-213">[パスワード **] ボックス** に、手順 2 で追加した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="406fa-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="406fa-214">**[Azure アプリ ID]** ボックスに、手順 1 で作成した AAD アプリケーション ID とも呼ばれるアプリケーション (クライアント) ID の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="406fa-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="406fa-215">接続が正常に検証された後、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="406fa-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="406fa-216">[ **データのインポートを承認する Microsoft 365]** ページで、APISecretKey を再び入力または貼り付け、[ **ログイン] Web アプリをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="406fa-217">[Facebook **コネクタ アプリ** の構成] ページで **、[Facebook** でログイン] をクリックし、組織の Facebook Business ページのアカウントの資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="406fa-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="406fa-218">ログインした Facebook アカウントに、組織の Facebook Business ページの管理者ロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="406fa-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Facebook でログインする](../media/FBCimage50.png)

9. <span data-ttu-id="406fa-220">ログインした Facebook アカウントによって管理されているビジネス ページのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="406fa-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="406fa-221">アーカイブするページを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-221">Select the page to archive and then click **Next**.</span></span>

   ![アーカイブする組織のビジネス ページを選択する](../media/FBCimage52.png)

10. <span data-ttu-id="406fa-223">[ **続行]** をクリックして、コネクタ サービス アプリのセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="406fa-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="406fa-224">[フィルター **の設定]** ページでは、フィルターを適用して、特定の年齢のアイテムを最初にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="406fa-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="406fa-225">年齢を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="406fa-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="406fa-226">[保存 **場所の** 選択] ページで、Facebook アイテムのインポート先の Microsoft 365 メールボックスのメール アドレスを入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="406fa-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="406fa-227">[ **次へ]** をクリックしてコネクタの設定を確認し、[完了] **をクリックして** コネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="406fa-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="406fa-228">コンプライアンス センターで、[データ コネクタ] ページに移動し、[コネクタ] タブをクリックしてインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="406fa-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
