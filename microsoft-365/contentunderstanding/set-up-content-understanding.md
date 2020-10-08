---
title: SharePoint Syntex の設定
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Project Cortex のコンテンツ理解をセットアップする
ms.openlocfilehash: 0d66076c93eb46ca11977cea12417c0816e0d11b
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367933"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="2c89c-103">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="2c89c-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="2c89c-104">管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](document-understanding-overview.md)をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="2c89c-105">事前に、次のことを考慮します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-105">Consider the following before you start:</span></span>

- <span data-ttu-id="2c89c-106">フォームの処理を有効にする SharePoint サイトはどれですか?</span><span class="sxs-lookup"><span data-stu-id="2c89c-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="2c89c-107">これらのすべて、それともサイトのいくつかを選択しますか?</span><span class="sxs-lookup"><span data-stu-id="2c89c-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="2c89c-108">既定のコンテンツセンターの名前を何にしますか?</span><span class="sxs-lookup"><span data-stu-id="2c89c-108">What will you name of your default content center?</span></span>

<span data-ttu-id="2c89c-109">Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="2c89c-110">この記事の内容は、Project Cortex プライべーとビューに関するものです。</span><span class="sxs-lookup"><span data-stu-id="2c89c-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="2c89c-111">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="2c89c-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="2c89c-112">設定する前に、使用している環境のコンテンツ解釈をセットアップして構成する最適な方法を計画してください。</span><span class="sxs-lookup"><span data-stu-id="2c89c-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="2c89c-113">たとえば、次の名前について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c89c-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="2c89c-114">フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)</span><span class="sxs-lookup"><span data-stu-id="2c89c-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="2c89c-115">コンテンツセンターと、プライマリサイト管理者の名前</span><span class="sxs-lookup"><span data-stu-id="2c89c-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="2c89c-116">要件</span><span class="sxs-lookup"><span data-stu-id="2c89c-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="2c89c-117">Microsoft 365 管理センターにアクセスし、コンテンツ認識できるようにするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c89c-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="2c89c-118">管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c89c-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="2c89c-119">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="2c89c-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="2c89c-120">Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="2c89c-121">**[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-121">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="2c89c-122">[ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-122">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="2c89c-124">[イメージタグの設定] ページで、 [画像のタグ付け](image-tagging.md)を許可するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-124">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![画像のタグ付けオプションのスクリーンショット](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="2c89c-126">[ **フォーム処理の構成**] ページで、特定の SharePoint ドキュメントライブラリにユーザーがフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-126">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="2c89c-127">ドキュメントライブラリのリボンには、メニューオプションが用意されています。これを有効にしている SharePoint ドキュメントライブラリで  **フォーム処理モデルを作成**します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-127">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="2c89c-128">**どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-128">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="2c89c-129">**すべての SharePoint ライブラリ**は、組織内のすべての SharePoint ライブラリで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-129">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="2c89c-130">**[選択したサイトのライブラリのみ]**、使用可能にするサイトを選択するか、最大50サイトのリストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-130">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="2c89c-131">**SharePointライブラリはなし**どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。</span><span class="sxs-lookup"><span data-stu-id="2c89c-131">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![フォームの処理を構成する](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="2c89c-133">含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。</span><span class="sxs-lookup"><span data-stu-id="2c89c-133">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="2c89c-p105">\*\*コンテンツセンターの作成 \*\* ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。 </span><span class="sxs-lookup"><span data-stu-id="2c89c-p105">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="2c89c-135">a.</span><span class="sxs-lookup"><span data-stu-id="2c89c-135">a.</span></span> <span data-ttu-id="2c89c-136">[ **サイト名**に、コンテンツセンターサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="2c89c-137">b.</span><span class="sxs-lookup"><span data-stu-id="2c89c-137">b.</span></span> <span data-ttu-id="2c89c-138">[ **サイトアドレス** には、サイト名に選択した内容に基づいて、サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="2c89c-139">変更する場合は、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-139">If you want to change it, click **Edit**.</span></span></br>

      ![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="2c89c-141">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-141">Select **Next**.</span></span>

7. <span data-ttu-id="2c89c-142">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="2c89c-143">選択内容に問題がない場合は、[\*\*ライセンス認証 \*\*]を行います。</span><span class="sxs-lookup"><span data-stu-id="2c89c-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="2c89c-144">[確認]ページで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="2c89c-145">**コンテンツ理解の自動作成** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2c89c-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="2c89c-146">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="2c89c-147">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c89c-147">Assign licenses</span></span>

<span data-ttu-id="2c89c-148">SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c89c-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="2c89c-149">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c89c-149">To assign licenses:</span></span>

1. <span data-ttu-id="2c89c-150">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="2c89c-151">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="2c89c-152">[**もっと割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="2c89c-153">[ **インテリジェントコンテンツサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="2c89c-154">[**アプリ**] の下で、**インテリジェントコンテンツサービスのためのコモンコンテンツサービス** と **インテリジェントコンテンツサービス**の両方が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 管理センターのSharePoint Syntexライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="2c89c-156">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c89c-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="2c89c-157">AI ビルダークレジット</span><span class="sxs-lookup"><span data-stu-id="2c89c-157">AI Builder credits</span></span>

<span data-ttu-id="2c89c-158">組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="2c89c-159">ライセンス数が300未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c89c-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="2c89c-160">Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="2c89c-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="2c89c-161">[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity) に移動して、クレジットと使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="2c89c-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c89c-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c89c-162">See also</span></span>

[<span data-ttu-id="2c89c-163">フォーム処理モデルの概要</span><span class="sxs-lookup"><span data-stu-id="2c89c-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="2c89c-164">ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="2c89c-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

