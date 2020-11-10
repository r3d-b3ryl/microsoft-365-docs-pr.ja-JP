---
title: 'ナレッジ管理をセットアップする (プレビュー) '
description: ナレッジ管理をセットアップする方法について説明します。
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: c7c30c0f8c1ec4cf8836547e2a23e1e2e6f4f783
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48989001"
---
# <a name="set-up-knowledge-management-preview"></a><span data-ttu-id="b2388-103">ナレッジ管理をセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b2388-103">Set up Knowledge Management (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b2388-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="b2388-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b2388-105">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="b2388-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b2388-106">Microsoft 365 管理センターを使用して、 [ナレッジ管理](knowledge-management-overview.md)をセットアップして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-106">You can use the Microsoft 365 admin center to set up and configure [Knowledge Management](knowledge-management-overview.md).</span></span> 

> [!Important]
> <span data-ttu-id="b2388-107">環境でナレッジマネジメントをセットアップして構成するための最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b2388-107">It is important to plan the best way to set up and configure Knowledge Management in your environment.</span></span> <span data-ttu-id="b2388-108">たとえば、次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2388-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="b2388-109">トピックを分析する SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="b2388-109">Which SharePoint sites you want to analyze for topics.</span></span>
- <span data-ttu-id="b2388-110">トピックを表示するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2388-110">Which users you want to make topics visible to.</span></span>
- <span data-ttu-id="b2388-111">トピックセンターのトピックを管理するためのアクセス許可を付与するユーザー。</span><span class="sxs-lookup"><span data-stu-id="b2388-111">Which users you want to give permissions to manage topics in the topic center.</span></span>
- <span data-ttu-id="b2388-112">トピックセンターでトピックを作成または編集するためのアクセス許可を付与するユーザー。</span><span class="sxs-lookup"><span data-stu-id="b2388-112">Which users you want to give permissions to create or edit topics in the topic center.</span></span>
- <span data-ttu-id="b2388-113">トピックセンターに付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2388-113">What name you want to give your topic center.</span></span>

> [!Note]
> <span data-ttu-id="b2388-114">トピックの表示、トピックの管理、およびトピックの作成と編集に必要なアクセス許可をユーザーに割り当てるには、セキュリティグループを作成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="b2388-114">You may find it useful to create security groups to assign your users the permissions needed to view topics, manage topic, and create and edit topics.</span></span>

<span data-ttu-id="b2388-115">管理者は、Microsoft 365 管理センターのナレッジ管理設定を使用して、 [選択した設定をいつ](topic-experiences-discovery.md) でも変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-115">An admin can also [make changes to your selected settings anytime after setup](topic-experiences-discovery.md) through the Knowledge Management settings in the Microsoft 365 admin center.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2388-116">Requirements</span><span class="sxs-lookup"><span data-stu-id="b2388-116">Requirements</span></span> 
<span data-ttu-id="b2388-117">グローバル管理者または SharePoint 管理者のアクセス許可を持っている必要があります。これを行うには、Microsoft 365 管理センターにアクセスして、組織のナレッジタスクを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2388-117">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up Organizational knowledge tasks.</span></span>

## <a name="set-up-your-knowledge-network"></a><span data-ttu-id="b2388-118">ナレッジネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b2388-118">Set up your knowledge network</span></span>

<span data-ttu-id="b2388-119">ナレッジネットワークをセットアップするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2388-119">Setting up your knowledge network walks you through the following:</span></span>

- <span data-ttu-id="b2388-120">トピック検出: 検出から除外するトピックソースとトピックを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-120">Topic discovery: Selecting topic sources and topics to  exclude from discovery.</span></span>
- <span data-ttu-id="b2388-121">トピックの表示: [検索] および [トピックページ] で、トピックを強調表示できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-121">Topic visibility: Selecting who can view topics as highlights, in search and topic pages.</span></span>
- <span data-ttu-id="b2388-122">トピックのアクセス許可: トピックを作成、編集、および管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-122">Topic permissions: Selecting who can create, edit, and manage topics.</span></span>
- <span data-ttu-id="b2388-123">トピックセンター: トピックセンターを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2388-123">Topic center: Create your topic center.</span></span>
- <span data-ttu-id="b2388-124">レビュー: 設定を確認して適用します。</span><span class="sxs-lookup"><span data-stu-id="b2388-124">Review: Check and apply your settings.</span></span>

<span data-ttu-id="b2388-125">ナレッジネットワークをセットアップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b2388-125">To set up your knowledge network:</span></span>

1. <span data-ttu-id="b2388-126">Microsoft 365 管理センター (admin.microsoft.com) で、[ **セットアップ** ] を選択し、[ **組織ナレッジ** ] セクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="b2388-126">In the Microsoft 365 admin center (admin.microsoft.com), select **Setup** , and then view the **Organizational Knowledge** section.</span></span>
2. <span data-ttu-id="b2388-127">[ **組織ナレッジ** ] セクションで、[ **ユーザーをナレッジに接続する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2388-127">In the **Organizational Knowledge** section, click **Connect people to knowledge**.</span></span><br/>

    ![ユーザーを知識に結び付ける](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. <span data-ttu-id="b2388-129">[ **ユーザーをナレッジに接続** する] ページで、[ **開始** ] をクリックして、セットアッププロセスを案内します。</span><span class="sxs-lookup"><span data-stu-id="b2388-129">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![概要](../media/content-understanding/k-get-started.png) </br>

4. <span data-ttu-id="b2388-131">[ **ナレッジネットワークでトピックを検索する方法を選択** してください] ページで、トピック検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2388-131">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="b2388-132">**[Sharepoint トピックソースの選択** ] セクションで、検出時にトピックのソースとしてクロールする sharepoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-132">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="b2388-133">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2388-133">This includes:</span></span></br>
    <span data-ttu-id="b2388-134">a.</span><span class="sxs-lookup"><span data-stu-id="b2388-134">a.</span></span> <span data-ttu-id="b2388-135">**すべてのサイト** : テナント内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="b2388-135">**All sites** : All SharePoint sites in your tenant.</span></span> <span data-ttu-id="b2388-136">これにより、現在および今後のサイトがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="b2388-136">This captures current and future sites.</span></span></br>
    <span data-ttu-id="b2388-137">b.</span><span class="sxs-lookup"><span data-stu-id="b2388-137">b.</span></span> <span data-ttu-id="b2388-138">**[すべて]: 選択したサイトを除き、** 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-138">**All, except selected sites** : Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="b2388-139">また、探索対象から除外するサイトの一覧をアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2388-139">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="b2388-140">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2388-140">Sites created in future will be included as sources for topic discovery.</span></span> </br>
    <span data-ttu-id="b2388-141">c.</span><span class="sxs-lookup"><span data-stu-id="b2388-141">c.</span></span> <span data-ttu-id="b2388-142">[ **選択したサイトのみ** : 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-142">**Only selected sites** : Type the names of the sites you want to include.</span></span> <span data-ttu-id="b2388-143">サイトのリストをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b2388-143">You can also upload a list of sites.</span></span> <span data-ttu-id="b2388-144">今後作成されるサイトは、トピック検出のソースとしては含まれません。</span><span class="sxs-lookup"><span data-stu-id="b2388-144">Sites created in the future will not be included as sources for topic discovery.</span></span> </br>

    ![トピックの検索方法を選択する](../media/content-understanding/ksetup1.png) </br>
   
5. <span data-ttu-id="b2388-146">[ **トピックを名前で除外** する] セクションで、検出された結果に含めるトピックの名前を含めることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-146">In the **Exclude topics by name** section, you can choose to includes names of topics you don't want to be in the discovered results.</span></span> <span data-ttu-id="b2388-147">この設定を使用して、機密性の高いトピックがナレッジネットワークの一部として含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="b2388-147">Use this setting to prevent sensitive topics from being included as part of the knowledge network.</span></span> <span data-ttu-id="b2388-148">次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b2388-148">Your options include:</span></span></br>
    <span data-ttu-id="b2388-149">a.</span><span class="sxs-lookup"><span data-stu-id="b2388-149">a.</span></span> <span data-ttu-id="b2388-150">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="b2388-150">**Don't exclude any topics**</span></span> </br>
    <span data-ttu-id="b2388-151">b.</span><span class="sxs-lookup"><span data-stu-id="b2388-151">b.</span></span> <span data-ttu-id="b2388-152">**トピックを名前で除外** する: ナレッジネットワークの一部としてユーザーに表示されないトピックがある場合。</span><span class="sxs-lookup"><span data-stu-id="b2388-152">**Exclude topics by name** :  If you have topics you don’t want shown to users as part of the knowledge network.</span></span></br>

    ![トピックを除外する](../media/content-understanding/topics-excluded-by-name.png) </br>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="b2388-154">名前によってトピックを除外する方法</span><span class="sxs-lookup"><span data-stu-id="b2388-154">How to exclude topics by name</span></span>    

    <span data-ttu-id="b2388-155">トピックを除外する必要がある場合は、[ **名前でトピックを除外** する] を選択した後、[ **.Csv テンプレートをダウンロード** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-155">If you need to exclude topics, after selecting **Exclude topics by name** , select **Download the .csv template**.</span></span> <span data-ttu-id="b2388-156">Excel を使用します。CSV テンプレートを使用して、検出結果から除外するトピックの一覧を追加します。</span><span class="sxs-lookup"><span data-stu-id="b2388-156">Use the Excel .CSV template to include a list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/content-understanding/csv1.png) </br>

    <span data-ttu-id="b2388-158">CSV テンプレートで、除外するトピックについて次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-158">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="b2388-159">[ **名前** : 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-159">**Name** : Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="b2388-160">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b2388-160">There are two ways to do this:</span></span></br>
        - <span data-ttu-id="b2388-161">完全一致: 完全に一致する名前または頭字語 (たとえば、 *Contoso* または *ATL* ) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-161">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL* ).</span></span></br>
        - <span data-ttu-id="b2388-162">部分一致: 特定の単語が含まれるすべてのトピックを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-162">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="b2388-163">たとえば、 *arc* は、円弧の *円* 、 *プラズマの円弧溶接* 、 *教育* 用の円弧など *、弧が単語で* あるすべてのトピックを除外します。テキストが *アーキテクチャ* などの単語の一部として含まれるトピックは除外されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b2388-163">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle* , *Plasma arc welding* , or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span></br>
    - <span data-ttu-id="b2388-164">**拡張 (省略可能)** : 頭字語を除外する場合は、頭字語という単語を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-164">**Expansion (optional)** : If you want to exclude an acronym, type the words the acronym stands for.</span></span></br>
    - <span data-ttu-id="b2388-165">**MatchType-exact/partial** : 入力した名前が、 *完全* 一致または *一部* 一致の種類であるかどうかを入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-165">**MatchType-Exact/Partial** : Type whether the name you entered was an *exact* or *partial* match type.</span></span></br>

    <span data-ttu-id="b2388-166">CSV テンプレートファイルが完成して保存されたら、[ **参照** ] を選択して、それを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-166">After you've completed and saved your CSV template file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="b2388-167">[ **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-167">Select **Next**.</span></span></br>

6. <span data-ttu-id="b2388-168">[ **トピックを見ることができるユーザー] および** それらのページが表示される場所については、トピックの表示を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2388-168">On the **Who can see topics and where they can see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="b2388-169">[ナレッジネットワーク設定] の [ **トピックを参照できるユーザー** ] で、強調表示されているトピック、トピックカード、トピックの回答、トピックページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-169">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="b2388-170">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-170">You can select:</span></span></br>
    <span data-ttu-id="b2388-171">a.</span><span class="sxs-lookup"><span data-stu-id="b2388-171">a.</span></span> <span data-ttu-id="b2388-172">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b2388-172">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b2388-173">b.</span><span class="sxs-lookup"><span data-stu-id="b2388-173">b.</span></span> <span data-ttu-id="b2388-174">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="b2388-174">**Only selected people or security groups**</span></span></br>
    <span data-ttu-id="b2388-175">c.</span><span class="sxs-lookup"><span data-stu-id="b2388-175">c.</span></span> <span data-ttu-id="b2388-176">**だれも**</span><span class="sxs-lookup"><span data-stu-id="b2388-176">**No one**</span></span></br>

    ![トピックを参照できるユーザー](../media/content-understanding/ksetup2.png) </br> 

 > [!Note] 
 > <span data-ttu-id="b2388-178">この設定では、組織内のユーザーを選択できますが、ナレッジ管理ライセンスが割り当てられているユーザーのみがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-178">While this setting allows you to select any user in your organization, only users who have knowledge management licenses assigned to them will be able to view topics.</span></span> 

7. <span data-ttu-id="b2388-179">[ **トピック管理のアクセス許可** ] ページで、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-179">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="b2388-180">[ **トピックの作成と編集が可能なユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-180">In the **Who can create and edit topics** section, you can select:</span></span></br>
    <span data-ttu-id="b2388-181">a.</span><span class="sxs-lookup"><span data-stu-id="b2388-181">a.</span></span> <span data-ttu-id="b2388-182">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b2388-182">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b2388-183">b.</span><span class="sxs-lookup"><span data-stu-id="b2388-183">b.</span></span> <span data-ttu-id="b2388-184">**選択したユーザーまたはセキュリティグループのみ**</span><span class="sxs-lookup"><span data-stu-id="b2388-184">**Only selected people or security groups**</span></span></br>
8. <span data-ttu-id="b2388-185">[ **トピックを管理できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-185">In the **Who can manage topics** section, you can select:</span></span></br>
    <span data-ttu-id="b2388-186">a.</span><span class="sxs-lookup"><span data-stu-id="b2388-186">a.</span></span> <span data-ttu-id="b2388-187">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b2388-187">**Everyone in your organization**</span></span></br>
    <span data-ttu-id="b2388-188">b.</span><span class="sxs-lookup"><span data-stu-id="b2388-188">b.</span></span> <span data-ttu-id="b2388-189">**選択されたユーザーまたはセキュリティグループ**</span><span class="sxs-lookup"><span data-stu-id="b2388-189">**Selected people or security groups**</span></span></br>

    ![トピック管理のアクセス許可](../media/content-understanding/ksetup3.png) </br>

    <span data-ttu-id="b2388-191">[ **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-191">Select **Next**.</span></span></br>
9. <span data-ttu-id="b2388-192">[ **トピックセンターの作成** ] ページでトピックセンターサイトを作成し、トピックページを表示したり、トピックを管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-192">On the **Create Topic  Center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span>  <span data-ttu-id="b2388-193">[ **トピックセンター名** ] ボックスに、トピックセンターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2388-193">In the **Topic center name** box, type a name for your Topic center.</span></span> <span data-ttu-id="b2388-194">必要に応じて、簡単な説明を [ **サイトの説明** ] ボックスに入力できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-194">You can optionally type a short description in the **Site description** box.</span></span> </br>

<span data-ttu-id="b2388-195">[ **次へ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-195">Select **Next**.</span></span></br>

   ![ナレッジセンターを作成する](../media/content-understanding/ksetup4.png) </br> 

10. <span data-ttu-id="b2388-197">[ **確認と完了** ] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-197">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b2388-198">選択内容に問題がない場合は、[ **ライセンス認証** ]を行います。</span><span class="sxs-lookup"><span data-stu-id="b2388-198">If you are satisfied with your selections, select **Activate**.</span></span>

    ![完了して確認する](../media/content-understanding/ksetup5.png) </br> 

11. <span data-ttu-id="b2388-200">[ **ナレッジネットワークがアクティブ化** されました] ページが表示され、選択したサイトの分析が開始され、ナレッジセンターサイトが作成されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-200">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="b2388-201">[ **完了** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2388-201">Select **Done**.</span></span></br>

    ![Activated](../media/content-understanding/ksetup6.png) </br> 

12. <span data-ttu-id="b2388-203">**ユーザーをナレッジに接続** するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b2388-203">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="b2388-204">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="b2388-204">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/content-understanding/ksetup7.png) </br>   

> [!Note]
> <span data-ttu-id="b2388-206">セットアップ後、管理者はこのページに戻って、 [選択したナレッジ管理設定を](topic-experiences-discovery.md) いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="b2388-206">After setup, an admin can [make changes to your selected knowledge management settings](topic-experiences-discovery.md) any time by returning to this page.</span></span>


## <a name="see-also"></a><span data-ttu-id="b2388-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2388-207">See also</span></span>



  






