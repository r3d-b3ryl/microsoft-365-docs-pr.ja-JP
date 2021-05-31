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
ms.openlocfilehash: 7589003505aafb480872b14a09c383cfbe0dff40
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683555"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="dbf43-103">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="dbf43-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="dbf43-104">管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](index.md)をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="dbf43-105">事前に、次のことを考慮します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-105">Consider the following before you start:</span></span>

- <span data-ttu-id="dbf43-106">どの SharePoint サイトでフォームの処理を有効にできますか?</span><span class="sxs-lookup"><span data-stu-id="dbf43-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="dbf43-107">これらのすべて、それともサイトのいくつかを選択しますか?</span><span class="sxs-lookup"><span data-stu-id="dbf43-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="dbf43-108">既定のコンテンツ センターの名前を何にしますか?</span><span class="sxs-lookup"><span data-stu-id="dbf43-108">What will you name your default content center?</span></span>

<span data-ttu-id="dbf43-109">Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="dbf43-p102">設定する前に、使用している環境のコンテンツ解釈をセットアップして構成する最適な方法を計画してください。たとえば、以下について決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-p102">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="dbf43-112">フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)</span><span class="sxs-lookup"><span data-stu-id="dbf43-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="dbf43-113">コンテンツ センターの名前と管理者</span><span class="sxs-lookup"><span data-stu-id="dbf43-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="dbf43-114">要件</span><span class="sxs-lookup"><span data-stu-id="dbf43-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="dbf43-115">Microsoft 365 管理センターにアクセスし、SharePoint Syntex をセットアップするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="dbf43-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="dbf43-116">管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

<span data-ttu-id="dbf43-117">カスタム Power Platform 環境を使用する場合は、フォーム処理モデルを作成する前に、[この環境で *プロジェクト Cortex の AI ビルダー* アプリをインストールし、](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view)そのアプリに [AI ビルダー クレジットを割り当てる](/power-platform/admin/capacity-add-on)必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-117">If you plan to use a custom Power Platform environment, you must [install the *AI Builder for Project Cortex* app in this environment](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) and [allocate AI Builder credits](/power-platform/admin/capacity-add-on) to it before you can create form processing models.</span></span>

### <a name="licensing"></a><span data-ttu-id="dbf43-118">ライセンス</span><span class="sxs-lookup"><span data-stu-id="dbf43-118">Licensing</span></span>

<span data-ttu-id="dbf43-119">SharePoint Syntex を使用するには、組織に SharePoint Syntex のサブスクリプションが必要であり、各ユーザーに次のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-119">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="dbf43-120">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="dbf43-120">SharePoint Syntex</span></span>
- <span data-ttu-id="dbf43-121">SharePoint Syntex - SPO の種類</span><span class="sxs-lookup"><span data-stu-id="dbf43-121">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="dbf43-122">SharePoint Syntex の共通データ サービス</span><span class="sxs-lookup"><span data-stu-id="dbf43-122">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="dbf43-123">将来 SharePoint Syntex サブスクリプションを解約すると (または試用期間が終了すると)、ユーザーはドキュメントの理解またはフォーム処理モデルを作成または実行できなくなり、コンテンツ センター テンプレートは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-123">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="dbf43-124">さらに、用語ストア レポート、SKOS 分類インポート、およびコンテンツの種類のプッシュは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-124">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="dbf43-125">コンテンツが削除されたり、サイトのアクセス許可が変更されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="dbf43-125">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="dbf43-126">AI ビルダークレジット</span><span class="sxs-lookup"><span data-stu-id="dbf43-126">AI Builder credits</span></span>

<span data-ttu-id="dbf43-127">組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-127">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="dbf43-128">ライセンス数が300未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-128">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="dbf43-129">Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-129">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="dbf43-130">カスタム Power Platform 環境を使用する場合は、 [その環境にクレジット割り当てる](/power-platform/admin/capacity-add-on)必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-130">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="dbf43-131">「[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity)」 に移動して、クレジットと使用状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-131">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="dbf43-132">SharePoint Syntex の設定</span><span class="sxs-lookup"><span data-stu-id="dbf43-132">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="dbf43-133">Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-133">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="dbf43-134">**[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-134">In the **Files and content** section, select **Automate content understanding**.</span></span> <span data-ttu-id="dbf43-135">現在の AI ビルダー クレジットの可用性は、**[概要]** セクションに表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dbf43-135">Note that your current AI Builder credit availability is shown in the **At a glance** section.</span></span><br/>

3. <span data-ttu-id="dbf43-136">[ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-136">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span> <br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dbf43-137">![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="dbf43-137">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="dbf43-138">[ **フォーム処理の構成**] ページで、特定の SharePoint ドキュメントライブラリにユーザーがフォーム処理モデルを作成できるようにするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-138">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="dbf43-139">ドキュメントライブラリのリボンには、メニューオプションが用意されています。これを有効にしている SharePoint ドキュメントライブラリで  **フォーム処理モデルを作成** します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-139">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="dbf43-140">**どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-140">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="dbf43-141">**すべての SharePoint サイトのライブラリ** は、組織内のすべての SharePoint ライブラリで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-141">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="dbf43-142">**選択した SharePoint サイトのライブラリ** は、使用可能にするサイトを選択するか、最大 50 件のサイトのリストをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-142">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="dbf43-143">**SharePointライブラリはなし** どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。</span><span class="sxs-lookup"><span data-stu-id="dbf43-143">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbf43-144">![フォーム処理サイトのオプションを構成する](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="dbf43-144">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="dbf43-145">含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。</span><span class="sxs-lookup"><span data-stu-id="dbf43-145">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="dbf43-146">複数の Power Platform 環境を構成している場合は、フォームの処理に使用する環境を選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-146">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="dbf43-147">(お持ちの環境が 1 つのみである場合、このオプションは表示されません)。</span><span class="sxs-lookup"><span data-stu-id="dbf43-147">(This option will not appear if you only have one environment.)</span></span>

    ![フォーム処理の Power Platform オプションを構成する](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="dbf43-149">**Power Platform 環境** には、以下を選択できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-149">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="dbf43-150">**既定の環境を使用** して、 Power Platform 環境を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-150">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="dbf43-151">**カスタム環境を使用** して、カスタム 環境を使用します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-151">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="dbf43-152">リストから使用する環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-152">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="dbf43-153">([カスタム環境の要件を参照してください](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)。)</span><span class="sxs-lookup"><span data-stu-id="dbf43-153">([See the requirements for a custom environment](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).</span></span>

    <span data-ttu-id="dbf43-154">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-154">Click **Next**.</span></span>

5. <span data-ttu-id="dbf43-155">**コンテンツセンターの作成** ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-155">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="dbf43-156">[**サイト名**] に、コンテンツ センター サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-156">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="dbf43-157">[ **サイトアドレス** には、サイト名に選択した内容に基づいて、サイトの URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-157">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="dbf43-158">変更する場合は、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-158">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="dbf43-159">![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="dbf43-159">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="dbf43-160">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-160">Select **Next**.</span></span>

6. <span data-ttu-id="dbf43-161">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-161">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="dbf43-162">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="dbf43-162">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="dbf43-163">[確認]ページで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-163">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="dbf43-164">**コンテンツ理解の自動作成** ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-164">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="dbf43-165">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="dbf43-165">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="dbf43-166">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dbf43-166">Assign licenses</span></span>

<span data-ttu-id="dbf43-167">SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbf43-167">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="dbf43-168">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dbf43-168">To assign licenses:</span></span>

1. <span data-ttu-id="dbf43-169">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-169">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="dbf43-170">ライセンスを付与するユーザーを選択し、**[製品ライセンスの管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-170">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="dbf43-171">ドロップダウン メニューから **[アプリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-171">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="dbf43-172">**[SharePoint Syntex のアプリを表示する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-172">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="dbf43-173">**[アプリ]** で、**Common Data Service for SharePoint Syntex**、**SharePoint Syntex**、**SharePoint Syntex - SPO type** がすべて選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbf43-173">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dbf43-174">![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="dbf43-174">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="dbf43-175">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbf43-175">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbf43-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbf43-176">See also</span></span>

[<span data-ttu-id="dbf43-177">フォーム処理モデルの概要</span><span class="sxs-lookup"><span data-stu-id="dbf43-177">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="dbf43-178">ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="dbf43-178">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="dbf43-179">Power Platform 管理センターで環境を作成して管理する</span><span class="sxs-lookup"><span data-stu-id="dbf43-179">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
