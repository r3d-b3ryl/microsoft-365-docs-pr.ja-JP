---
title: 'ナレッジ管理をセットアップする (プレビュー) '
description: ナレッジ管理をセットアップする方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: ba8cb8ceb3c98019099bfe5438d274c9d2b32280
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612550"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="4342e-103">ナレッジ管理をセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4342e-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4342e-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="4342e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4342e-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4342e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4342e-106">Microsoft 365 管理センターを使用して、[ナレッジ管理](knowledge-management-overview.md)をセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4342e-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="4342e-107">環境でナレッジマネジメントをセットアップして構成するための最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4342e-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="4342e-108">たとえば、次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4342e-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="4342e-109">トピックを分析する SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="4342e-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="4342e-110">トピックを表示するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="4342e-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="4342e-111">トピックセンターのトピックを管理するためのアクセス許可を付与するユーザー。</span><span class="sxs-lookup"><span data-stu-id="4342e-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="4342e-112">トピックセンターでトピックを作成または編集するためのアクセス許可を付与するユーザー。</span><span class="sxs-lookup"><span data-stu-id="4342e-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="4342e-113">トピックセンターに付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="4342e-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="4342e-114">トピックの表示、トピックの管理、およびトピックの作成と編集に必要なアクセス許可をユーザーに割り当てるには、セキュリティグループを作成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="4342e-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="4342e-115">管理者は、Microsoft 365 管理センターのナレッジ管理設定を使用して、[選択した設定をいつ](manage-knowledge-network.md)でも変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4342e-115">An admin can also [make changes to your selected settings anytime after setup](manage-knowledge-network.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="4342e-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="4342e-116">Requirements</span></span> 
<span data-ttu-id="4342e-117">グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。これを行うには、Microsoft 365 管理センターにアクセスして、組織のナレッジタスクを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4342e-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="4342e-118">ナレッジネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4342e-118">Set up your knowledge network</span></span>

<span data-ttu-id="4342e-119">ナレッジネットワークをセットアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4342e-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="4342e-120">トピック検出: 検出から除外するトピックソースとトピックを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="4342e-121">トピックの表示: [検索] および [トピックページ] で、トピックを強調表示できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="4342e-122">トピックのアクセス許可: トピックを作成、編集、および管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="4342e-123">トピックセンター: トピックセンターを作成します。</span><span class="sxs-lookup"><span data-stu-id="4342e-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="4342e-124">レビュー: 設定を確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="4342e-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="4342e-125">ナレッジネットワークをセットアップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4342e-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="4342e-126">Microsoft 365 管理センター (admin.microsoft.com) で、[**セットアップ**] を選択し、[**組織ナレッジ**] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="4342e-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup**, and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="4342e-127">[**組織ナレッジ**] セクションで、[**ユーザーをナレッジに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4342e-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![ユーザーを知識に結び付ける](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="4342e-129">[**ユーザーをナレッジに接続**する] ページで、[**開始**] をクリックして、セットアッププロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="4342e-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![作業の開始](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="4342e-131">[**ナレッジネットワークでトピックを検索する方法を選択**してください] ページで、トピック検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="4342e-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="4342e-132">**[Sharepoint トピックソースの選択**] セクションで、検出時にトピックのソースとしてクロールする sharepoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="4342e-133">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4342e-133">This includes:</span></span></br>
    <span data-ttu-id="4342e-134">a.</span><span class="sxs-lookup"><span data-stu-id="4342e-134">a.</span></span> <span data-ttu-id="4342e-135">**すべてのサイト**: テナント内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="4342e-135">**All sites**: All SharePoint sites in your tenant.</span></span> <span data-ttu-id="4342e-136">これにより、現在および今後のサイトがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="4342e-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="4342e-137">b.</span><span class="sxs-lookup"><span data-stu-id="4342e-137">b.</span></span> <span data-ttu-id="4342e-138">**[すべて]: 選択したサイトを除き、** 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4342e-138">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="4342e-139">また、探索対象から除外するサイトの一覧をアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4342e-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="4342e-140">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="4342e-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="4342e-141">c. </span><span class="sxs-lookup"><span data-stu-id="4342e-141">c.</span></span> <span data-ttu-id="4342e-142">[**選択したサイトのみ**: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4342e-142">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="4342e-143">サイトのリストをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4342e-143">You can also upload a list of sites.</span></span> <span data-ttu-id="4342e-144">今後作成されるサイトは、トピック検出のソースとしては含まれません。</span><span class="sxs-lookup"><span data-stu-id="4342e-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![トピックの検索方法を選択する](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="4342e-146">[**トピックを名前で除外**する] セクションで、検出された結果に含めるトピックの名前を含めることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="4342e-147">この設定を使用して、機密性の高いトピックがナレッジネットワークの一部として含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="4342e-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="4342e-148">次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="4342e-148">Your options include:</span></span></br>
    <span data-ttu-id="4342e-149">a.</span><span class="sxs-lookup"><span data-stu-id="4342e-149">a.</span></span> <span data-ttu-id="4342e-150">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="4342e-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="4342e-151">b.</span><span class="sxs-lookup"><span data-stu-id="4342e-151">b.</span></span> <span data-ttu-id="4342e-152">**次の用語を含むトピックを除外**します。ユーザーに表示したくないトピックがある場合は、ナレッジネットワークの一部として表示されません。</span><span class="sxs-lookup"><span data-stu-id="4342e-152">**Exclude topic that contain these terms**:  If you have topics you don’t want shown to users as part of the knowledge network.</span></span>
   <span data-ttu-id="4342e-153">-提供されたテンプレートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4342e-153">- Download the provided template.</span></span>
   <span data-ttu-id="4342e-154">-除外するトピック名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4342e-154">- Enter the topic names you want to exclude.</span></span> <span data-ttu-id="4342e-155">一致の種類を exact または partial として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4342e-155">You must indicate the match type as exact or partial.</span></span> <span data-ttu-id="4342e-156">完全一致の場合は、完全に一致する用語が除外されます。</span><span class="sxs-lookup"><span data-stu-id="4342e-156">Exact match means that topics that fit the exact term will be excluded.</span></span> <span data-ttu-id="4342e-157">部分一致は厳密であり、用語を含むトピックは除外されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4342e-157">Partial match is stricter and means that topics that contain the term will be excluded.</span></span> <span data-ttu-id="4342e-158">たとえば、トピック名として「 *doc* 」と入力すると、 *Docker*ではなく、 *doc アセンブリ*が除外されます。</span><span class="sxs-lookup"><span data-stu-id="4342e-158">For example, if you enter *Doc* as the topic name, *Doc assembly* will be excluded while *Docker* won't.</span></span> <span data-ttu-id="4342e-159">トピック名の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="4342e-159">Topic names are case insensitive.</span></span>  
        <span data-ttu-id="4342e-160">-  **+**   完了した CSV ファイルをインポートする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-160">- Select **+** to import your completed CSV file.</span></span> <span data-ttu-id="4342e-161">[**アップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-161">Then select **Upload**.</span></span> <span data-ttu-id="4342e-162">ファイルが正常に処理された場合は、緑色のチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4342e-162">You’ll see a green check mark if your file has been processed successfully.</span></span> <span data-ttu-id="4342e-163">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-163">Select **Next**.</span></span></br>


6. <span data-ttu-id="4342e-164">[**トピックを見ることができるユーザー] および**それらのページが表示される場所については、トピックの表示を構成します。</span><span class="sxs-lookup"><span data-stu-id="4342e-164">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="4342e-165">[ナレッジネットワーク設定] の [**トピックを参照できるユーザー** ] で、強調表示されているトピック、トピックカード、トピックの回答、トピックページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-165">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="4342e-166">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-166">You can select:</span></span></br>
    <span data-ttu-id="4342e-167">a.</span><span class="sxs-lookup"><span data-stu-id="4342e-167">a.</span></span> <span data-ttu-id="4342e-168">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="4342e-168">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4342e-169">b.</span><span class="sxs-lookup"><span data-stu-id="4342e-169">b.</span></span> <span data-ttu-id="4342e-170">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="4342e-170">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="4342e-171">c. </span><span class="sxs-lookup"><span data-stu-id="4342e-171">c.</span></span> <span data-ttu-id="4342e-172">**だれも**</span><span class="sxs-lookup"><span data-stu-id="4342e-172">**No one**</span></span></br>

    ![トピックを参照できるユーザー](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="4342e-174">この設定では、組織内のユーザーを選択できますが、ナレッジ管理ライセンスが割り当てられているユーザーのみがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-174">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="4342e-175">[**トピック管理のアクセス許可**] ページで、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-175">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="4342e-176">[**トピックの作成と編集が可能なユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-176">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="4342e-177">a.</span><span class="sxs-lookup"><span data-stu-id="4342e-177">a.</span></span> <span data-ttu-id="4342e-178">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="4342e-178">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4342e-179">b.</span><span class="sxs-lookup"><span data-stu-id="4342e-179">b.</span></span> <span data-ttu-id="4342e-180">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="4342e-180">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="4342e-181">[**トピックを管理できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-181">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="4342e-182">a.</span><span class="sxs-lookup"><span data-stu-id="4342e-182">a.</span></span> <span data-ttu-id="4342e-183">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="4342e-183">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="4342e-184">b.</span><span class="sxs-lookup"><span data-stu-id="4342e-184">b.</span></span> <span data-ttu-id="4342e-185">**選択されたユーザーまたはセキュリティグループ**</span><span class="sxs-lookup"><span data-stu-id="4342e-185">**Selected people or security groups**</span></span></br>

    ![トピック管理のアクセス許可](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="4342e-187">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-187">Select **Next**.</span></span></br>
9. <span data-ttu-id="4342e-188">[**トピックセンターの作成**] ページでトピックセンターサイトを作成し、トピックページを表示したり、トピックを管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4342e-188">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="4342e-189">[**トピックセンター名**] ボックスに、トピックセンターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4342e-189">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="4342e-190">必要に応じて、簡単な説明を [**サイトの説明**] ボックスに入力できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-190">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="4342e-191">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-191">Select **Next**.</span></span></br>

   ![ナレッジセンターを作成する](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="4342e-193">[**確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4342e-193">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="4342e-194">選択内容に問題がなければ、[**アクティブ化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-194">If you are satisfied with your selections, select **Activate**.</span></span>

    ![完了して確認する](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="4342e-196">[**ナレッジネットワークがアクティブ化**されました] ページが表示され、選択したサイトの分析が開始され、ナレッジセンターサイトが作成されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-196">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="4342e-197">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4342e-197">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="4342e-199">**ユーザーをナレッジに接続**するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="4342e-199">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="4342e-200">このページでは、[**管理**] を選択して構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="4342e-200">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="4342e-202">セットアップ後、管理者はこのページに戻って、[選択したナレッジ管理設定を](manage-knowledge-network.md)いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="4342e-202">After setup, an admin can [make changes to your selected knowledge management settings](manage-knowledge-network.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="4342e-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="4342e-203">See also</span></span>



  






