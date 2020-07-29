---
title: コネクタを展開して Facebook ビジネスページデータをアーカイブする
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
description: 管理者は、Facebook のビジネスページをインポートおよびアーカイブするためのネイティブコネクタを Microsoft 365 にセットアップできます。 このデータを Microsoft 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Facebook データのガバナンスを管理できます。
ms.openlocfilehash: 240ce3a90cf46a05ab5d6030b9318d42d23904d8
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434238"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="5e187-104">コネクタを展開して Facebook ビジネスページデータをアーカイブする</span><span class="sxs-lookup"><span data-stu-id="5e187-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="5e187-105">この記事では、Office 365 インポートサービスを使用して、Facebook のビジネスページから Microsoft 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e187-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="5e187-106">このプロセスの概要と、Facebook コネクタを展開するために必要な前提条件の一覧については、「 [facebook データをアーカイブするためのコネクタの設定](archive-facebook-data-with-sample-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e187-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="5e187-107">手順 1: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="5e187-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="5e187-108">に移動 <https://portal.azure.com> し、グローバル管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="5e187-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![AAD でアプリを作成する](../media/FBCimage1.png)

2. <span data-ttu-id="5e187-110">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![[Azure Active Directory] をクリックします。](../media/FBCimage2.png)

3. <span data-ttu-id="5e187-112">左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![[\* \* アプリの登録 (プレビュー)] をクリックし、[\* \* 新しい登録] \* \* をクリックします。](../media/FBCimage3.png)

4. <span data-ttu-id="5e187-114">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="5e187-114">Register the application.</span></span> <span data-ttu-id="5e187-115">[リダイレクト URI] で、[アプリケーションの種類] ドロップダウンリストから [Web] を選択し、 <https://portal.azure.com> URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="5e187-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![アプリケーションの登録](../media/FBCimage4.png)

5. <span data-ttu-id="5e187-117">**アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="5e187-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="5e187-118">これらの Id は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="5e187-118">You use these IDs in later steps.</span></span>

   ![アプリケーション ID とディレクトリ ID をコピーして保存します。](../media/FBCimage5.png)

6. <span data-ttu-id="5e187-120">[証明書] に移動して **、新しいアプリのシークレット & します。**</span><span class="sxs-lookup"><span data-stu-id="5e187-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![新しいアプリの証明書 & シークレットに移動します。](../media/FBCimage6.png)

7. <span data-ttu-id="5e187-122">[**新しいクライアントシークレット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-122">Click **New client secret**</span></span>

   ![[新しいクライアントシークレット] をクリックします。](../media/FBCimage7.png)

8. <span data-ttu-id="5e187-124">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e187-124">Create a new secret.</span></span> <span data-ttu-id="5e187-125">[説明] ボックスに、シークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e187-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![シークレットを入力して、有効期限を選択する](../media/FBCimage8.png)

9. <span data-ttu-id="5e187-127">シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="5e187-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="5e187-128">これは、後の手順で使用する AAD アプリケーションシークレットです。</span><span class="sxs-lookup"><span data-stu-id="5e187-128">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットの値をコピーして保存する](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="5e187-130">手順 2: GitHub から Azure アカウントにコネクタ web サービスを展開する</span><span class="sxs-lookup"><span data-stu-id="5e187-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="5e187-131">[この GitHub サイト](https://github.com/microsoft/m365-sample-connector-csharp-aspnet)に移動し、[ **Azure への展開] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![[Azure への展開] をクリックします。](../media/FBCGithubApp.png)

2. <span data-ttu-id="5e187-133">[ **Azure への展開**] をクリックすると、カスタムテンプレートページを使用して azure portal にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="5e187-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="5e187-134">[**基本**と**設定**] の詳細を入力し、[**購入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="5e187-135">**サブスクリプション:** Facebook Business pages connector web サービスを展開する Azure サブスクリプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e187-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="5e187-136">**リソースグループ:** 新しいリソースグループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="5e187-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="5e187-137">リソースグループは、Azure ソリューションの関連リソースを保持するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="5e187-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="5e187-138">**場所:** 場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e187-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="5e187-139">**Web アプリ名:** コネクタ web アプリの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e187-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="5e187-140">名前の長さは 3 ~ 18 文字でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5e187-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="5e187-141">この名前は、Azure app service の URL を作成するために使用されます。たとえば、 **fbconnector**の Web アプリ名を指定すると、Azure app SERVICE の URL は**fbconnector.azurewebsites.net**になります。</span><span class="sxs-lookup"><span data-stu-id="5e187-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="5e187-142">**tenantId:** 手順1で Azure Active Directory に Facebook connector アプリを作成した後にコピーした、Microsoft 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="5e187-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="5e187-143">**APISecretKey:** 任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="5e187-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="5e187-144">これは、手順5でコネクタ web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e187-144">This is used to access the connector web app in Step 5.</span></span>

     ![[リソースを作成し、ストレージアカウントを入力してください] をクリックします。](../media/FBCimage12.png)

3. <span data-ttu-id="5e187-146">展開に成功すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="5e187-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![[記憶域] をクリックし、[ストレージアカウント] をクリックします。](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="5e187-148">手順 3: Facebook アプリを登録する</span><span class="sxs-lookup"><span data-stu-id="5e187-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="5e187-149">に移動し <https://developers.facebook.com> て、組織の Facebook ビジネスページのアカウントの資格情報を使用してログインし、[**新しいアプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![[Facebook ビジネス用の新しいアプリの追加] ページ](../media/FBCimage25.png)

2. <span data-ttu-id="5e187-151">新しいアプリ ID を作成します。</span><span class="sxs-lookup"><span data-stu-id="5e187-151">Create a new app ID.</span></span>

   ![新しいアプリ ID を作成する](../media/FBCimage26.png)

3. <span data-ttu-id="5e187-153">左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、 **Facebook ログイン**タイルで [**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![[製品の追加] をクリックします。](../media/FBCimage27.png)

4. <span data-ttu-id="5e187-155">[Facebook ログインの統合] ページで、[ **Web**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![[Facebook ログインの統合] ページで、[Web] をクリックします。](../media/FBCimage28.png)

5. <span data-ttu-id="5e187-157">Azure app service の URL を追加します。例を示し `https://fbconnector.azurewebsites.net` ます。</span><span class="sxs-lookup"><span data-stu-id="5e187-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Azure app service の URL を追加する](../media/FBCimage29.png)

6. <span data-ttu-id="5e187-159">Facebook ログインセットアップのクイックスタートセクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="5e187-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![クイックスタートセクションを完了する](../media/FBCimage30.png)

7. <span data-ttu-id="5e187-161">[ **Facebook ログイン**] の左側のナビゲーションウィンドウで、[**設定**] をクリックし、[**有効な oauth リダイレクト**URI] ボックスに oauth リダイレクト uri を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="5e187-162">\*\* \<connectorserviceuri> /Views/FacebookOAuth\*\*の形式を使用します。ここで、[コネクタ] の値は、組織の Azure APP service の URL です。たとえば、のように `https://fbconnector.azurewebsites.net` なります。</span><span class="sxs-lookup"><span data-stu-id="5e187-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![OAuth リダイレクト URI を [有効な OAuth リダイレクト uri] ボックスに追加する](../media/FBCimage31.png)

8. <span data-ttu-id="5e187-164">左側のナビゲーションウィンドウで、[**製品の追加**] をクリックし、[webhooks] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="5e187-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="5e187-165">**ページ**のプルダウンメニューで、[**ページ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![[製品の追加] をクリックし、[\* \* Webhooks] をクリックします。](../media/FBCimage32.png)

9. <span data-ttu-id="5e187-167">Webhooks コールバック URL を追加し、検証トークンを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="5e187-168">コールバック URL の形式。 \*\* <connectorserviceuri> /Api/fbpagewebhook\*\*の形式を使用します。ここで、[コネクタ] の値は、組織の AZURE app service URL です。たとえば、「」のように `https://fbconnector.azurewebsites.net` なります。</span><span class="sxs-lookup"><span data-stu-id="5e187-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="5e187-169">Verify トークンは、強力なパスワードと類似している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e187-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="5e187-170">検証トークンをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5e187-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Verify トークンを追加する](../media/FBCimage33.png)

10. <span data-ttu-id="5e187-172">フィードのエンドポイントをテストし、サブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="5e187-172">Test and subscribe to the endpoint for feed.</span></span>

    ![エンドポイントをテストおよびサブスクライブする](../media/FBCimage34.png)

11. <span data-ttu-id="5e187-174">プライバシー URL、アプリアイコン、およびビジネス用途を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="5e187-175">また、アプリケーション ID とアプリシークレットをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5e187-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![プライバシー URL、アプリアイコン、およびビジネス用途を追加する](../media/FBCimage35.png)

12. <span data-ttu-id="5e187-177">アプリを公開します。</span><span class="sxs-lookup"><span data-stu-id="5e187-177">Make the app public.</span></span>

    ![アプリを公開する](../media/FBCimage36.png)

13. <span data-ttu-id="5e187-179">管理者またはテスト担当者の役割にユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-179">Add user to the admin or tester role.</span></span>

    ![管理者またはテスト担当者の役割にユーザーを追加する](../media/FBCimage37.png)

14. <span data-ttu-id="5e187-181">ページの**パブリックコンテンツのアクセス**許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd ページのパブリックコンテンツアクセス許可](../media/FBCimage38.png)

15. <span data-ttu-id="5e187-183">[ページの管理] アクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e187-183">Add Manage Pages permission.</span></span>

    ![ページの管理アクセス許可を追加する](../media/FBCimage39.png)

16. <span data-ttu-id="5e187-185">Facebook によって確認されたアプリケーションを取得します。</span><span class="sxs-lookup"><span data-stu-id="5e187-185">Get the application reviewed by Facebook.</span></span>

    ![Facebook によって確認されたアプリケーションを取得する](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="5e187-187">手順 4: コネクタ web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="5e187-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="5e187-188">に移動 `https://<AzureAppResourceName>.azurewebsites.net` します (ここで、AzureAppResourceName は、手順4で名前を付けた Azure app リソースの名前です)。</span><span class="sxs-lookup"><span data-stu-id="5e187-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="5e187-189">たとえば、名前が**fbconnector**の場合は、に移動 `https://fbconnector.azurewebsites.net` します。</span><span class="sxs-lookup"><span data-stu-id="5e187-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="5e187-190">アプリのホームページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="5e187-190">The home page of the app will look like the following screenshot:</span></span>

   ![「Go connector web app」に移動します。](../media/FBCimage41.png)

2. <span data-ttu-id="5e187-192">[**構成**] をクリックして、サインインページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e187-192">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインインページを表示する](../media/FBCimage42.png)

3. <span data-ttu-id="5e187-194">[テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。</span><span class="sxs-lookup"><span data-stu-id="5e187-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="5e187-195">[パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして構成の詳細ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e187-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![テナント Id とパスワードを使用してサインインし、[構成の詳細] ページに移動します。](../media/FBCimage43.png)

4. <span data-ttu-id="5e187-197">次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e187-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="5e187-198">**Facebook アプリケーション ID:** 手順3で取得した Facebook アプリケーションのアプリ ID。</span><span class="sxs-lookup"><span data-stu-id="5e187-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="5e187-199">**Facebook アプリケーションシークレット:** 手順3で取得した Facebook アプリケーションのアプリシークレット。</span><span class="sxs-lookup"><span data-stu-id="5e187-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="5e187-200">**Facebook webhook がトークンを確認します。** 手順3で作成した検証トークン。</span><span class="sxs-lookup"><span data-stu-id="5e187-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="5e187-201">**AAD アプリケーション ID:** 手順1で作成した Azure Active Directory アプリのアプリケーション ID。</span><span class="sxs-lookup"><span data-stu-id="5e187-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="5e187-202">**AAD アプリケーションシークレット:** 手順1で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="5e187-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="5e187-203">[**保存**] をクリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="5e187-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="5e187-204">手順 5: Microsoft 365 コンプライアンスセンターで Facebook コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="5e187-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="5e187-205">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com) 、左側のナビゲーションで [**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="5e187-206">[**データコネクタ] (プレビュー)** ページの [ **Facebook ビジネスページ**] で、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-206">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="5e187-207">[ **Facebook のビジネスページ**] ページで、[**コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="5e187-208">[**サービス利用規約**] ページで、[**同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="5e187-209">[**コネクタアプリの資格情報の追加**] ページで、次の情報を入力し、[**接続の検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Connector アプリの資格情報を入力する](../media/TCimage38.png)

   - <span data-ttu-id="5e187-211">[**名前**] ボックスに、 **Facebook news ページ**などのコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e187-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="5e187-212">[**接続 URL** ] ボックスに、Azure app SERVICE の url を入力するか貼り付けます。例を示し `https://fbconnector.azurewebsites.net` ます。</span><span class="sxs-lookup"><span data-stu-id="5e187-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="5e187-213">[**パスワード**] ボックスに、手順2で追加した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5e187-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="5e187-214">[ **Azure APP id** ] ボックスに、手順1で作成した AAD application id とも呼ばれるアプリケーション (クライアント) id の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5e187-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="5e187-215">接続が正常に検証されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="5e187-216">[ **Microsoft 365 にデータをインポートするための承認**] ページで、APISecretKey をもう一度入力するか貼り付けて、[ **Login web app**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="5e187-217">[ **Facebook connector アプリの構成**] ページで、[ **facebook でログイン**] をクリックし、組織の facebook ビジネスページのアカウントの資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="5e187-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="5e187-218">ログインに使用した Facebook アカウントに、組織の Facebook ビジネスページの管理者の役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e187-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Facebook でログインする](../media/FBCimage50.png)

9. <span data-ttu-id="5e187-220">ログインした Facebook アカウントによって管理されるビジネスページの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e187-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="5e187-221">アーカイブするページを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-221">Select the page to archive and then click **Next**.</span></span>

   ![アーカイブする組織のビジネスページを選択します。](../media/FBCimage52.png)

10. <span data-ttu-id="5e187-223">[**続行**] をクリックして、connector service アプリのセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="5e187-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="5e187-224">[**フィルターの設定**] ページでは、特定の年齢のアイテムを最初にインポートするためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="5e187-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="5e187-225">年齢を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="5e187-226">[**ストレージの場所の選択**] ページで、Facebook アイテムがインポートされる Microsoft 365 メールボックスの電子メールアドレスを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e187-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="5e187-227">[**管理者に同意**する] で、[**同意を提供**する] をクリックし、手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5e187-227">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="5e187-228">組織内のデータにアクセスするために Office 365 Import service への同意を提供するには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e187-228">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="5e187-229">[**次**へ] をクリックしてコネクタの設定を確認し、[**完了**] をクリックしてコネクタのセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="5e187-229">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="5e187-230">コンプライアンスセンターで**データコネクタ**ページに移動し、[**コネクタ**] タブをクリックしてインポートプロセスの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="5e187-230">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
