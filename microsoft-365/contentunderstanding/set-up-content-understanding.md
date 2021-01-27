---
title: SharePoint Syntex の設定
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Project Cortex のコンテンツ理解をセットアップする
ms.openlocfilehash: a9713f1d28cf863ab827d2975e84042026105b3f
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976388"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="27bb1-103">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="27bb1-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="27bb1-104">管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](index.md)をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="27bb1-105">事前に、次のことを考慮します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-105">Consider the following before you start:</span></span>

- <span data-ttu-id="27bb1-106">どの SharePoint サイトでフォームの処理を有効にできますか?</span><span class="sxs-lookup"><span data-stu-id="27bb1-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="27bb1-107">これらのすべて、それともサイトのいくつかを選択しますか?</span><span class="sxs-lookup"><span data-stu-id="27bb1-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="27bb1-108">既定のコンテンツ センターの名前を何にしますか?</span><span class="sxs-lookup"><span data-stu-id="27bb1-108">What will you name your default content center?</span></span>

<span data-ttu-id="27bb1-109">Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="27bb1-110">設定する前に、使用している環境のコンテンツ解釈をセットアップして構成する最適な方法を計画してください。</span><span class="sxs-lookup"><span data-stu-id="27bb1-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="27bb1-111">たとえば、以下について決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="27bb1-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="27bb1-112">フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)</span><span class="sxs-lookup"><span data-stu-id="27bb1-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="27bb1-113">名前と管理者またはコンテンツ センター</span><span class="sxs-lookup"><span data-stu-id="27bb1-113">The name and admins or your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="27bb1-114">要件</span><span class="sxs-lookup"><span data-stu-id="27bb1-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="27bb1-115">Microsoft 365 管理センターにアクセスし、コンテンツ認識できるようにするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="27bb1-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="27bb1-116">管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="27bb1-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="27bb1-117">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="27bb1-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="27bb1-118">Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="27bb1-119">**[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="27bb1-120">[ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27bb1-121">![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="27bb1-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="27bb1-122">[ **フォーム処理の構成**] ページで、特定の SharePoint ドキュメントライブラリにユーザーがフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="27bb1-123">ドキュメントライブラリのリボンには、メニューオプションが用意されています。これを有効にしている SharePoint ドキュメントライブラリで  **フォーム処理モデルを作成** します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="27bb1-124">**どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="27bb1-125">**すべての SharePoint サイトのライブラリ** は、組織内のすべての SharePoint ライブラリで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-125">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="27bb1-126">**選択した SharePoint サイトのライブラリ** は、使用可能にするサイトを選択するか、最大 50 件のサイトのリストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-126">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="27bb1-127">**SharePointライブラリはなし** どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。</span><span class="sxs-lookup"><span data-stu-id="27bb1-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="27bb1-128">![フォームの処理を構成する](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="27bb1-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="27bb1-129">含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。</span><span class="sxs-lookup"><span data-stu-id="27bb1-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="27bb1-130">**コンテンツセンターの作成** ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="27bb1-131">[**サイト名**] に、コンテンツ センター サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="27bb1-132">[ **サイトアドレス** には、サイト名に選択した内容に基づいて、サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-132">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="27bb1-133">変更する場合は、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-133">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="27bb1-134">![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="27bb1-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="27bb1-135">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-135">Select **Next**.</span></span>

6. <span data-ttu-id="27bb1-136">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-136">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="27bb1-137">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="27bb1-137">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="27bb1-138">[確認]ページで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="27bb1-139">**コンテンツ理解の自動作成** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="27bb1-139">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="27bb1-140">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-140">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="27bb1-141">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="27bb1-141">Assign licenses</span></span>

<span data-ttu-id="27bb1-142">SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="27bb1-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="27bb1-143">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="27bb1-143">To assign licenses:</span></span>

1. <span data-ttu-id="27bb1-144">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="27bb1-145">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="27bb1-146">[**もっと割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="27bb1-147">**[SharePoint Syntex]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-147">Select **SharePoint Syntex**.</span></span> <span data-ttu-id="27bb1-148">**[アプリ]** で、**Common Data Service for SharePoint Syntex**、**SharePoint Syntex**、**SharePoint Syntex - SPO type** がすべて選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-148">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27bb1-149">![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="27bb1-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="27bb1-150">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27bb1-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="27bb1-151">AI ビルダークレジット</span><span class="sxs-lookup"><span data-stu-id="27bb1-151">AI Builder credits</span></span>

<span data-ttu-id="27bb1-152">組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-152">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="27bb1-153">ライセンス数が300未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27bb1-153">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="27bb1-154">Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="27bb1-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="27bb1-155">[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity) に移動して、クレジットと使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="27bb1-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="27bb1-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="27bb1-156">See also</span></span>

[<span data-ttu-id="27bb1-157">フォーム処理モデルの概要</span><span class="sxs-lookup"><span data-stu-id="27bb1-157">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="27bb1-158">ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="27bb1-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
