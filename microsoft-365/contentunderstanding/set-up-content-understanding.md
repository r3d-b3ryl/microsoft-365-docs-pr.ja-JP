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
ms.openlocfilehash: 410dd9550974ec7b5c1c5b4ae151bc92bf376544
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446325"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="5fdb3-103">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="5fdb3-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="5fdb3-104">管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](index.md)をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="5fdb3-105">事前に、次のことを考慮します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-105">Consider the following before you start:</span></span>

- <span data-ttu-id="5fdb3-106">フォームの処理を有効にする SharePoint サイトはどれですか?</span><span class="sxs-lookup"><span data-stu-id="5fdb3-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="5fdb3-107">これらのすべて、それともサイトのいくつかを選択しますか?</span><span class="sxs-lookup"><span data-stu-id="5fdb3-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="5fdb3-108">既定のコンテンツセンターの名前を何にしますか?</span><span class="sxs-lookup"><span data-stu-id="5fdb3-108">What will you name of your default content center?</span></span>

<span data-ttu-id="5fdb3-109">Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="5fdb3-110">設定する前に、使用している環境のコンテンツ解釈をセットアップして構成する最適な方法を計画してください。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="5fdb3-111">たとえば、次の名前について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-111">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="5fdb3-112">フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)</span><span class="sxs-lookup"><span data-stu-id="5fdb3-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="5fdb3-113">コンテンツセンターと、プライマリサイト管理者の名前</span><span class="sxs-lookup"><span data-stu-id="5fdb3-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="5fdb3-114">要件</span><span class="sxs-lookup"><span data-stu-id="5fdb3-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="5fdb3-115">Microsoft 365 管理センターにアクセスし、コンテンツ認識できるようにするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="5fdb3-116">管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="5fdb3-117">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="5fdb3-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="5fdb3-118">Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="5fdb3-119">**[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="5fdb3-120">[ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="5fdb3-122">[ **フォーム処理の構成**] ページで、特定の SharePoint ドキュメントライブラリにユーザーがフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="5fdb3-123">ドキュメントライブラリのリボンには、メニューオプションが用意されています。これを有効にしている SharePoint ドキュメントライブラリで  **フォーム処理モデルを作成**します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="5fdb3-124">**どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="5fdb3-125">**すべての SharePoint ライブラリ**は、組織内のすべての SharePoint ライブラリで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="5fdb3-126">**[選択したサイトのライブラリのみ]**、使用可能にするサイトを選択するか、最大50サイトのリストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="5fdb3-127">**SharePointライブラリはなし**どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![フォームの処理を構成する](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="5fdb3-129">含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="5fdb3-p104">\*\*コンテンツセンターの作成 \*\* ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。 </span><span class="sxs-lookup"><span data-stu-id="5fdb3-p104">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="5fdb3-131">a.</span><span class="sxs-lookup"><span data-stu-id="5fdb3-131">a.</span></span> <span data-ttu-id="5fdb3-132">[ **サイト名**に、コンテンツセンターサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-132">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="5fdb3-133">b.</span><span class="sxs-lookup"><span data-stu-id="5fdb3-133">b.</span></span> <span data-ttu-id="5fdb3-134">[ **サイトアドレス** には、サイト名に選択した内容に基づいて、サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-134">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="5fdb3-135">変更する場合は、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-135">If you want to change it, click **Edit**.</span></span></br>

      ![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="5fdb3-137">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-137">Select **Next**.</span></span>

6. <span data-ttu-id="5fdb3-138">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-138">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="5fdb3-139">選択内容に問題がない場合は、[\*\*ライセンス認証 \*\*]を行います。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-139">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="5fdb3-140">[確認]ページで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-140">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="5fdb3-141">**コンテンツ理解の自動作成** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="5fdb3-142">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="5fdb3-143">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fdb3-143">Assign licenses</span></span>

<span data-ttu-id="5fdb3-144">SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-144">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="5fdb3-145">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5fdb3-145">To assign licenses:</span></span>

1. <span data-ttu-id="5fdb3-146">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-146">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="5fdb3-147">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-147">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="5fdb3-148">[**もっと割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-148">Select **Assign more**.</span></span>

4. <span data-ttu-id="5fdb3-149">[ **インテリジェントコンテンツサービス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-149">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="5fdb3-150">[**アプリ**] の下で、**インテリジェントコンテンツサービスのためのコモンコンテンツサービス** と **インテリジェントコンテンツサービス**の両方が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-150">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Microsoft 365 管理センターのSharePoint Syntexライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="5fdb3-152">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-152">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="5fdb3-153">AI ビルダークレジット</span><span class="sxs-lookup"><span data-stu-id="5fdb3-153">AI Builder credits</span></span>

<span data-ttu-id="5fdb3-154">組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-154">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="5fdb3-155">ライセンス数が300未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-155">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="5fdb3-156">Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-156">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="5fdb3-157">[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity) に移動して、クレジットと使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fdb3-157">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fdb3-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fdb3-158">See also</span></span>

[<span data-ttu-id="5fdb3-159">フォーム処理モデルの概要</span><span class="sxs-lookup"><span data-stu-id="5fdb3-159">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="5fdb3-160">ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="5fdb3-160">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

