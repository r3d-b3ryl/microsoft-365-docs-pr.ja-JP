---
title: SharePoint の同期 Tex をセットアップする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: コンテンツの理解をプロジェクト Cortex で設定する
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294867"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="9c9b1-103">SharePoint の同期 Tex をセットアップする</span><span class="sxs-lookup"><span data-stu-id="9c9b1-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="9c9b1-104">管理者は、Microsoft 365 管理センターを使用して、Microsoft SharePoint の同期 Tex をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="9c9b1-105">開始する前に、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-105">Consider the following before you start:</span></span>

- <span data-ttu-id="9c9b1-106">どの SharePoint サイトでフォーム処理を有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="9c9b1-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="9c9b1-107">すべてのサイト、一部、またはサイトの選択</span><span class="sxs-lookup"><span data-stu-id="9c9b1-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="9c9b1-108">コンテンツセンターの名前と、プライマリサイト管理者を指定してください。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="9c9b1-109">Microsoft 365 管理センターの初期セットアップ後に設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="9c9b1-110">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="9c9b1-111">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="9c9b1-112">セットアップの前に、環境内のコンテンツの理解を設定して構成するための最善の方法を計画してください。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="9c9b1-113">たとえば、次のような名前を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="9c9b1-114">フォーム処理を有効にする必要がある SharePoint サイト (すべてのサイト、一部、または選択したサイト)</span><span class="sxs-lookup"><span data-stu-id="9c9b1-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="9c9b1-115">コンテンツセンターと、プライマリサイト管理者の名前</span><span class="sxs-lookup"><span data-stu-id="9c9b1-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="9c9b1-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="9c9b1-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="9c9b1-117">Microsoft 365 管理センターにアクセスし、コンテンツの理解を設定するには、グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="9c9b1-118">管理者であれば、セットアップ後に選択した設定を変更することもできます。また、コンテンツ全体で、Microsoft 365 管理センターの管理設定について理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="9c9b1-119">SharePoint の同期 Tex をセットアップするには</span><span class="sxs-lookup"><span data-stu-id="9c9b1-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="9c9b1-120">Microsoft 365 管理センターで、[ **セットアップ**] を選択し、[ **組織ナレッジ** ] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="9c9b1-121">[ **組織ナレッジ** ] セクションで、[ **コンテンツの理解を自動化**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![組織ナレッジの設定ページ](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="9c9b1-123">[ **SharePoint の同期の自動化** ] ページで、[ **開始** ] をクリックして、セットアッププロセスの手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![セットアップの開始](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="9c9b1-125">[画像のタグ付けの有効化] ページで、画像への [タグ付け](image-tagging.md)を許可するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![画像へのタグ付けのオプションのスクリーンショット](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="9c9b1-127">[ **フォーム処理の構成** ] ページで、ユーザーが AI ビルダーを使用して、特定の SharePoint ドキュメントライブラリのフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="9c9b1-128">[ドキュメントライブラリ] リボンでメニューオプションを使用して、フォーム処理モデルが有効になっている SharePoint ドキュメントライブラリに **フォーム処理モデルを作成** できます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="9c9b1-129">**フォーム処理モデルを作成するためのオプションをどの SharePoint ライブラリに表示するかを指定**するには、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="9c9b1-130">組織内のすべての SharePoint ライブラリで利用できるようにするための**すべての sharepoint ライブラリ**。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="9c9b1-131">[**選択したサイトのライブラリのみ**] を選択し、使用できるようにするサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![フォーム処理を構成する](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="9c9b1-133">SharePoint ドキュメントライブラリでこの設定を有効にしても、ライブラリに適用されている既存のモデル、またはドキュメントを認識するモデルをライブラリに適用する機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="9c9b1-134">[ **コンテンツセンターの作成** ] ページで、ユーザーがドキュメントを作成および管理できる SharePoint コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="9c9b1-135">a. </span><span class="sxs-lookup"><span data-stu-id="9c9b1-135">a.</span></span> <span data-ttu-id="9c9b1-136">[ **サイト名**] に、コンテンツセンターサイトに付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="9c9b1-137">b. </span><span class="sxs-lookup"><span data-stu-id="9c9b1-137">b.</span></span> <span data-ttu-id="9c9b1-138">サイト **アドレス** には、サイト名に対して選択した内容に基づいてサイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="9c9b1-139">変更する場合は、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-139">If you want to change it, click **Edit**.</span></span></br>

      ![コンテンツセンターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="9c9b1-141">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-141">Select **Next**.</span></span>

7. <span data-ttu-id="9c9b1-142">[ **確認と完了** ] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="9c9b1-143">選択内容に問題がなければ、[ **アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="9c9b1-144">[確認] ページで、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="9c9b1-145">**コンテンツの自動理解**ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="9c9b1-146">このページでは、[ **管理** ] を選択して構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="9c9b1-147">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9c9b1-147">Assign licenses</span></span>

<span data-ttu-id="9c9b1-148">SharePoint の同期 Tex を構成した後、フォーム処理を使用するユーザーにライセンスを割り当てる必要があります。また、ドキュメントを理解するには、その機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="9c9b1-149">ライセンスを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="9c9b1-149">To assign licenses:</span></span>

1. <span data-ttu-id="9c9b1-150">Microsoft 365 管理センターで、[ **ユーザー**] の下の [ **アクティブなユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="9c9b1-151">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="9c9b1-152">[ **詳細の割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="9c9b1-153">[ **インテリジェントコンテンツサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="9c9b1-154">[**アプリ**] の下で、[インテリジェントコンテンツサービス] と [**インテリジェントコンテンツ**サービス**用の共通データサービス] の**両方が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 管理センターの SharePoint 同期 Tex ライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="9c9b1-156">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="9c9b1-157">AI ビルダークレジット</span><span class="sxs-lookup"><span data-stu-id="9c9b1-157">AI Builder credits</span></span>

<span data-ttu-id="9c9b1-158">組織に300以上の sharepoint の同期 tex ライセンスがある場合は、100万 AI ビルダークレジットが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="9c9b1-159">ライセンス数が300未満の場合は、フォーム処理を使用するために、AI ビルダークレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="9c9b1-160">[Ai ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)で、適切な ai ビルダーの容量を見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

1. <span data-ttu-id="9c9b1-161">[電源プラットフォーム管理センター](https://admin.powerplatform.microsoft.com/resources/capacity)に移動して、クレジットと使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c9b1-162">SharePoint ドキュメントライブラリでこの設定を有効にしても、ライブラリに適用されている既存のモデル、またはドキュメントを認識するモデルをライブラリに適用する機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-162">Enable this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
2. <span data-ttu-id="9c9b1-163">[ **コンテンツセンターの作成** ] ページで、ユーザーがドキュメントを作成および管理できる SharePoint コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-163">From the **Create Content Center** page, you can create a SharePoint content center site for which users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="9c9b1-164">a. </span><span class="sxs-lookup"><span data-stu-id="9c9b1-164">a.</span></span> <span data-ttu-id="9c9b1-165">[ **サイト名**] に、コンテンツセンターサイトに付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-165">For **Site name**, type the name you want for the content center site.</span></span></br>
    <span data-ttu-id="9c9b1-166">b. </span><span class="sxs-lookup"><span data-stu-id="9c9b1-166">b.</span></span> <span data-ttu-id="9c9b1-167">サイト **アドレス** には、サイト名に基づいてサイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-167">The **Site address** shows the URL for your site, based on the site name.</span></span></br>

    > [!NOTE] 
    > <span data-ttu-id="9c9b1-168">サポートされている言語を選択することはできますが、モデルを理解しているのは英語の場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-168">While you can select any supported language, content understanding models can only be created for English.</span></span></br>

      ![コンテンツセンターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

3. <span data-ttu-id="9c9b1-170">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-170">Select **Next**.</span></span>

4. <span data-ttu-id="9c9b1-171">[ **完了と確認** ] ページで、選択した設定を確認し、変更を行うように選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-171">On the **Finish and review** page, look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="9c9b1-172">選択内容に問題がなければ、[ **アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-172">If you are satisfied with your selections, select **Activate**.</span></span>

5. <span data-ttu-id="9c9b1-173">**コンテンツはアクティブ化**されたページを理解しており、システムがフォーム処理の設定を追加し、コンテンツセンターサイトを作成したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-173">The **Content understanding activated** page displays, confirming the system added your form processing preferences and created the Content Center site.</span></span> <span data-ttu-id="9c9b1-174">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-174">Select **Done**.</span></span>

6. <span data-ttu-id="9c9b1-175">**コンテンツの自動理解**ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-175">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="9c9b1-176">このページでは、[ **管理** ] を選択して構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="9c9b1-176">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9c9b1-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c9b1-177">See also</span></span>

[<span data-ttu-id="9c9b1-178">フォーム処理モデルの概要</span><span class="sxs-lookup"><span data-stu-id="9c9b1-178">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="9c9b1-179">ステップバイステップ: ドキュメントを構築する方法モデルについて (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="9c9b1-179">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

