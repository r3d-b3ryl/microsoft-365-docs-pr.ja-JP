---
title: コネクタをアーカイブ Twitter データに展開する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Office 365 に Twitter データをインポートしてアーカイブするためのネイティブコネクタをセットアップできます。 このデータを Office 365 にインポートした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織の Twitter データのガバナンスを管理できます。
ms.openlocfilehash: 87faad6546d70b1e3893e2f5737af189ebb5f77b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806150"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="696bb-104">コネクタをアーカイブ Twitter データに展開する</span><span class="sxs-lookup"><span data-stu-id="696bb-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="696bb-105">この記事では、Office 365 インポートサービスを使用して組織の Twitter アカウントから Office 365 にデータをインポートするコネクタを展開するための段階的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="696bb-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="696bb-106">このプロセスの概要と、Twitter コネクタを展開するために必要な前提条件の一覧については、「[サンプルコネクタを使用して Office 365 の Twitter データをアーカイブする (プレビュー)](archive-twitter-data-with-sample-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="696bb-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="696bb-107">手順 1: パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="696bb-107">Step 1: Download the package</span></span>

<span data-ttu-id="696bb-108">の GitHub リポジトリのリリースセクションから、構築済みパッケージをダウンロード[https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)します。</span><span class="sxs-lookup"><span data-stu-id="696bb-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="696bb-109">最新リリースの下で、 **SampleConnector**という名前の zip ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="696bb-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="696bb-110">この zip ファイルを手順4で Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="696bb-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="696bb-111">手順 2: Azure Active Directory でアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="696bb-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="696bb-112">に<https://portal.azure.com>移動し、Office 365 グローバル管理者アカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="696bb-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Azure にサインインする](media/TCimage01.png)

2. <span data-ttu-id="696bb-114">左側のナビゲーションウィンドウで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Azure Active Directory に移動します。](media/TCimage02.png)

3. <span data-ttu-id="696bb-116">左側のナビゲーションウィンドウで、[**アプリの登録 (プレビュー)** ] をクリックし、[**新しい登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![新しいアプリの登録を作成する](media/TCimage03.png)

4. <span data-ttu-id="696bb-118">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="696bb-118">Register the application.</span></span> <span data-ttu-id="696bb-119">[**リダイレクト URI (オプション)**] で\*\*\*\* 、[アプリケーションの種類] ドロップダウンリストから`https://portal.azure.com` [WEB] を選択し、URI のボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="696bb-120">リダイレクトhttps://portal.azure.com URI の種類</span><span class="sxs-lookup"><span data-stu-id="696bb-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="696bb-121">**アプリケーション (クライアント) id**と**ディレクトリ (テナント) id**をコピーし、それをテキストファイルまたは他の安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="696bb-122">これらの Id は、後の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="696bb-122">You use these IDs in later steps.</span></span>

    ![アプリケーション Id とディレクトリ Id をコピーして保存する](media/TCimage05.png)

6. <span data-ttu-id="696bb-124">[**証明書 & 新しいアプリのシークレット**] および [**クライアントシークレット**] の下で、[**新しいクライアントシークレット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![新しいクライアントシークレットを作成する](media/TCimage06.png)

7. <span data-ttu-id="696bb-126">新しいシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="696bb-126">Create a new secret.</span></span> <span data-ttu-id="696bb-127">[説明] ボックスに、シークレットを入力し、有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="696bb-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![シークレットを入力して、[有効期限の期間] を選択する](media/TCimage08.png)

8. <span data-ttu-id="696bb-129">シークレットの値をコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="696bb-130">これは、後の手順で使用する AAD アプリケーションシークレットです。</span><span class="sxs-lookup"><span data-stu-id="696bb-130">This is the AAD application secret that you use in later steps.</span></span>

   ![シークレットをコピーして保存する](media/TCimage09.png)

9. <span data-ttu-id="696bb-132">**マニフェスト**に移動し、次のスクリーンショットで強調表示されているように、identifieruris (AAD アプリケーション Uri とも呼ばれる) をコピーします。</span><span class="sxs-lookup"><span data-stu-id="696bb-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="696bb-133">AAD アプリケーション Uri をテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="696bb-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="696bb-134">手順6で使用します。</span><span class="sxs-lookup"><span data-stu-id="696bb-134">You use it in Step 6.</span></span>

    ![AAD アプリケーション Uri をコピーして保存する](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="696bb-136">手順 3: Azure storage アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="696bb-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="696bb-137">組織の Azure ホームページに移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-137">Go to the Azure home page for your organization.</span></span>

    ![Gi to Azure ホームページ](media/TCimage11.png)

2. <span data-ttu-id="696bb-139">[**リソースの作成**] をクリックし、検索ボックスに「**ストレージアカウント**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![ストレージアカウントリソースを作成する](media/TCimage12.png)

3. <span data-ttu-id="696bb-141">[**記憶域**] をクリックし、[**ストレージアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![[記憶域] をクリックし、[ストレージアカウント] をクリックします。](media/TCimage13.png)

4. <span data-ttu-id="696bb-143">[**ストレージアカウントの作成**] ページの [サブスクリプション] ボックスで、使用している Azure サブスクリプションの種類に応じて、[**購入時に支払う**] または [**無料試用版**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="696bb-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![ストレージアカウントの種類を選択する](media/TCimage14.png)

5. <span data-ttu-id="696bb-145">リソースグループを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="696bb-145">Select or create a resource group.</span></span>

   ![リソースグループを選択または作成する](media/TCimage15.png)

6. <span data-ttu-id="696bb-147">ストレージアカウントの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-147">Type a name for the storage account.</span></span>

   ![ストレージアカウントの名前](media/TCimage16.png)

7. <span data-ttu-id="696bb-149">確認してから [**作成**] をクリックして、ストレージアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="696bb-149">Review and then click **Create** to create the storage account.</span></span>

   ![設定を確認し、ストレージアカウントを作成する](media/TCimage17.png)

8. <span data-ttu-id="696bb-151">しばらくしてから、[**更新**] をクリックし、[**リソースに移動**] をクリックして、ストレージアカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![作成したストレージアカウントに移動します。](media/TCimage18.png)

9. <span data-ttu-id="696bb-153">左側のナビゲーションウィンドウで [**アクセスキー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-153">Click **Access keys** in the left navigation pane.</span></span>

   ![[アクセスキー] をクリックします。](media/TCimage19.png)

10. <span data-ttu-id="696bb-155">**接続文字列**をコピーし、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="696bb-156">この操作は、手順4で web app リソースを作成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="696bb-156">You use this when creating a web app resource in Step 4.</span></span>

    ![接続文字列をコピーする](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="696bb-158">手順 4: Azure で新しい web app リソースを作成する</span><span class="sxs-lookup"><span data-stu-id="696bb-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="696bb-159">Azure portal の**ホーム**ページで、[**リソース\>すべて\>の Web アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="696bb-160">[ **Web アプリ**] ページで、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-160">On the **Web app** page, click **Create**.</span></span>

   ![Azure で web app リソースを作成する](media/TCimage21.png)

2. <span data-ttu-id="696bb-162">詳細を入力し (次の図を参照)、Web アプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="696bb-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="696bb-163">[**アプリケーション名**] ボックスに入力した名前は、Azure app SERVICE の URL を作成するために使用されます。たとえば、twitterconnector.azurewebsites.net のようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="696bb-164">Web app リソースの種類の名前。例 twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="696bb-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="696bb-165">新しく作成した web app リソースに移動し、左側のナビゲーションウィンドウで [**アプリケーションの設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="696bb-166">[**アプリケーションの設定**] で、[**新しい設定の追加**] をクリックし、次の3つの設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="696bb-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="696bb-167">前の手順で入力したテキストファイルにコピーした値を使用します。</span><span class="sxs-lookup"><span data-stu-id="696bb-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="696bb-168">**APISecretKey** –任意の値をシークレットとして入力できます。</span><span class="sxs-lookup"><span data-stu-id="696bb-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="696bb-169">これは、手順7でコネクタ web アプリにアクセスするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="696bb-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="696bb-170">**Storageaccountconnectionstring** –手順3で Azure storage アカウントを作成した後にコピーした接続文字列 Uri。</span><span class="sxs-lookup"><span data-stu-id="696bb-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="696bb-171">**tenantId** –手順2で、Azure Active Directory で Twitter connector アプリを作成した後にコピーした Office 365 組織のテナント ID。</span><span class="sxs-lookup"><span data-stu-id="696bb-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![アプリ設定の追加](media/TCimage23.png)

4. <span data-ttu-id="696bb-173">[**全般設定**] で、[**常にオン**] の横にある [**オン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="696bb-174">ページの上部にある [**保存**] をクリックして、アプリケーションの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Web app リソースを有効にして保存する](media/TCimage24.png)

5. <span data-ttu-id="696bb-176">最後の手順では、手順1でダウンロードしたコネクタアプリソースコードを Azure にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="696bb-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="696bb-177">Web ブラウザーで、https://<AzureAppResourceName>に移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="696bb-178">たとえば、このセクションの手順2で指定した Azure app リソースの名前が**twitterconnector**の場合は、にhttps://twitterconnector.scm.azurewebsites.net/ZipDeployUi移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="696bb-179">手順1でダウンロードした SampleConnector をドラッグアンドドロップして、このページに移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="696bb-180">ファイルがアップロードされ、展開が正常に完了すると、ページは次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![SampleConnector ファイルをこのページにドラッグアンドドロップします。](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="696bb-182">手順 5: Twitter アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="696bb-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="696bb-183">にhttps://developer.twitter.com移動して、組織の開発者アカウントの資格情報を使用してログインし、[**アプリ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![にhttps://developer.twitter.com移動し、ログインします。](media/TCimage25-5.png)
2. <span data-ttu-id="696bb-185">[**アプリの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-185">Click **Create an app**.</span></span>
   
   ![アプリページに移動してアプリを作成する](media/TCimage26.png)

3. <span data-ttu-id="696bb-187">[**アプリの詳細**] で、アプリケーションに関する情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="696bb-187">Under **App details**, add information about the application.</span></span>

   ![アプリに関する情報を入力する](media/TCimage27.png)

4. <span data-ttu-id="696bb-189">Twitter 開発者ダッシュボードで、作成したばかりのアプリを選択し、表示されたアプリ ID をコピーして、テキストファイルまたはその他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="696bb-190">[**詳細**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-190">Then click **Details**.</span></span>
   
   ![アプリ Id をコピーして保存する](media/TCimage28.png)

5. <span data-ttu-id="696bb-192">[**キーとトークン**] タブの [**コンシューマー api キー** ] で、api シークレットキーをコピーして、テキストファイルまたは他の保存場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="696bb-193">次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="696bb-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![API シークレットキーにコピーして保存する](media/TCimage29.png)

   <span data-ttu-id="696bb-195">次に、[**作成**] をクリックしてアクセストークンとアクセストークンシークレットを生成し、それをテキストファイルまたは他の保存場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="696bb-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="696bb-196">[**アクセス許可**] タブをクリックし、次のスクリーンショットに示されているようにアクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="696bb-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![アクセス許可を構成する](media/TCimage30.png)

7. <span data-ttu-id="696bb-198">アクセス許可の設定を保存した後、[**アプリの詳細**] タブをクリックし、[編集] をクリックして [**詳細の編集 >** します。</span><span class="sxs-lookup"><span data-stu-id="696bb-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![アプリの詳細を編集する](media/TCimage31.png)

8. <span data-ttu-id="696bb-200">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="696bb-200">Do the following tasks:</span></span>

   - <span data-ttu-id="696bb-201">チェックボックスをオンにして、コネクタアプリが Twitter にサインインできるようにします。</span><span class="sxs-lookup"><span data-stu-id="696bb-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="696bb-202">次の形式を使用して OAuth リダイレクト Uri を追加します: \*\* \<コネクタ>/views/twitteroauth\**。この場合、*コネクタサービス uri\*の値は組織の Azure app service URL になります。たとえば、 https://twitterconnector.azurewebsites.net/Views/TwitterOAuthのようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![コネクタアプリが Twitter にサインインして OAuth リダイレクト Uri を追加できるようにする](media/TCimage32.png)

<span data-ttu-id="696bb-204">Twitter 開発者アプリを使用する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="696bb-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="696bb-205">手順 6: コネクタ web アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="696bb-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="696bb-206">Https://\<AzureAppResourceName> に移動します (ここで、 **AzureAppResourceName**は、手順4で名前を付けた Azure app リソースの名前です)。</span><span class="sxs-lookup"><span data-stu-id="696bb-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="696bb-207">たとえば、名前が**twitterconnector**の場合は、にhttps://twitterconnector.azurewebsites.net移動します。</span><span class="sxs-lookup"><span data-stu-id="696bb-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="696bb-208">アプリのホームページは、次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-208">The home page of the app looks like the following screenshot:</span></span>

   ![Azure app リソースページに移動します。](media/FBCimage41.png)

2. <span data-ttu-id="696bb-210">[**構成**] をクリックして、サインインページを表示します。</span><span class="sxs-lookup"><span data-stu-id="696bb-210">Click **Configure** to display a sign in page.</span></span>

   ![[構成] をクリックしてサインインページを表示する](media/FBCimage42.png)

3. <span data-ttu-id="696bb-212">[テナント Id] ボックスに、テナント Id を入力するか貼り付けます (手順2で取得したもの)。</span><span class="sxs-lookup"><span data-stu-id="696bb-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="696bb-213">[パスワード] ボックスに、APISecretKey (手順2で取得した) を入力するか貼り付け、[**構成設定の設定**] をクリックして**構成の詳細**ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="696bb-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![テナント Id と API シークレットキーを使用してサインインする](media/TCimage35.png)

4. <span data-ttu-id="696bb-215">[**構成の詳細**] で、次の構成設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="696bb-216">**Twitter Api キー** –手順5で作成した twitter アプリケーションのアプリ ID。</span><span class="sxs-lookup"><span data-stu-id="696bb-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="696bb-217">**Twitter Api の秘密キー** –手順5で作成した twitter アプリケーションの api シークレットキー。</span><span class="sxs-lookup"><span data-stu-id="696bb-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="696bb-218">**Twitter アクセストークン**–手順5で作成したアクセストークン。</span><span class="sxs-lookup"><span data-stu-id="696bb-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="696bb-219">**Twitter アクセストークンシークレット**–手順5で作成したアクセストークンシークレット。</span><span class="sxs-lookup"><span data-stu-id="696bb-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="696bb-220">**AAD アプリケーション id** –手順2で作成した Azure Active Directory アプリのアプリケーション id</span><span class="sxs-lookup"><span data-stu-id="696bb-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="696bb-221">**AAD アプリケーションシークレット**–手順4で作成した APISecretKey シークレットの値。</span><span class="sxs-lookup"><span data-stu-id="696bb-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="696bb-222">**Aad アプリケーション uri** –手順2で取得した Aad アプリケーション uri。たとえば、 `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`のようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="696bb-223">**App Insights インストルメンテーションキー** –このボックスは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="696bb-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="696bb-224">[**保存**] をクリックしてコネクタの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="696bb-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="696bb-225">手順 7: セキュリティ/コンプライアンスセンターでカスタムコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="696bb-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="696bb-226">に移動<https://protection.office.com>して、[**情報\>ガバナンス\> ] [サードパーティデータのアーカイブをインポート**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![セキュリティ/コンプライアンスセンターの [アーカイブサードパーティのデータ] ページに移動します。](media/TCimage36.png)

2. <span data-ttu-id="696bb-228">[**コネクタの追加**] をクリックし、[ **Twitter**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![[コネクタの追加] をクリックして Twitter コネクタを追加します。](media/TCimage37.png)

3. <span data-ttu-id="696bb-230">[**コネクタアプリの追加**] ページで、次の情報を入力し、[**コネクタの検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="696bb-231">最初のボックスに、 **Twitter**などのコネクタの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="696bb-232">2番目のボックスに、手順4で追加した APISecretKey の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="696bb-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="696bb-233">3番目のボックスに、Azure app service の URL を入力するか、貼り付けます。たとえば、 **https://twitterconnector.azurewebsites.net**のようになります。</span><span class="sxs-lookup"><span data-stu-id="696bb-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="696bb-234">コネクタの検証が正常に完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-234">After the connector is successfully validated, click **Next**.</span></span>

   ![コネクタのアプリ設定の入力](media/TCimage38.png)

4. <span data-ttu-id="696bb-236">[**コネクタアプリを使用してログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-236">Click **Login with Connector App**.</span></span>

   ![ログインコネクタアプリ](media/TCimage39.png)

5. <span data-ttu-id="696bb-238">APISecretKey をもう一度入力するか貼り付け、[**コネクタサービスにログイン] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![「API 秘密キーを入力してコネクタサービスにログインする」](media/TCimage40.png)

6. <span data-ttu-id="696bb-240">[ **Twitter で続行] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="696bb-241">[Twitter サインイン] ページで、組織の Twitter アカウントのアカウントの資格情報を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="696bb-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Twitter アカウントにサインインする](media/TCimage42.png)

   <span data-ttu-id="696bb-243">サインインした後、Twitter ページに次のメッセージが表示されます。 "Twitter Connector ジョブは正常にセットアップされました。"</span><span class="sxs-lookup"><span data-stu-id="696bb-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="696bb-244">[**完了**] をクリックして、Twitter connector の設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="696bb-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="696bb-245">[**フィルターの設定**] ページでは、特定の年齢のアイテムをインポート (およびアーカイブ) するためのフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="696bb-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="696bb-246">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="696bb-246">Click **Next**.</span></span>

   ![特定の期間のアイテムをインポートするようにフィルターを構成する](media/TCimage44.png)

10. <span data-ttu-id="696bb-248">[**ストレージアカウントの設定**] ページで、Twitter アイテムがインポートされる Office 365 メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="696bb-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![Twitter アイテムをインポートする Office 365 メールボックスを指定する](media/TCimage45.png)

11. <span data-ttu-id="696bb-250">設定を確認し、[**完了**] をクリックして、セキュリティ & コンプライアンスセンターでコネクタの設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="696bb-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![設定を確認し、[完了] をクリックします。](media/TCimage46.png)

    ![コネクタの設定が完了したことを示す画面](media/TCimage47.png)

12. <span data-ttu-id="696bb-253">[**サードパーティのデータをアーカイブ**する] ページに移動して、インポートプロセスの進行状況を表示します。</span><span class="sxs-lookup"><span data-stu-id="696bb-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![セキュリティ/コンプライアンスセンターに表示される新しいコネクタ](media/TCimage48.png)
