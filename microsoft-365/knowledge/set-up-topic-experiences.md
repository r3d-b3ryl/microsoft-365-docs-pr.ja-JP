---
title: Microsoft 365 でのトピック エクスペリエンスのセットアップ
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 でトピック エクスペリエンスをセットアップする方法について説明します。
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749613"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="b208a-103">Microsoft 365 でのトピック エクスペリエンスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b208a-103">Set up topic experiences in Microsoft 365</span></span>

<span data-ttu-id="b208a-104">Microsoft 365 管理センターを使用して、トピックエクスペリエンスを設定および [構成できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b208a-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="b208a-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b208a-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="b208a-106">この記事の手順を開始 [する前に、「](plan-topic-experiences.md) トピックエクスペリエンスを計画する」を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="b208a-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="b208a-107">Microsoft 365 管理センターにアクセスしてトピックエクスペリエンスを設定するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b208a-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="b208a-108">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="b208a-108">Video demonstration</span></span>

<span data-ttu-id="b208a-109">このビデオでは、Microsoft 365 でトピック エクスペリエンスを設定するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="b208a-109">This video shows the process for setting up topic experiences in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="b208a-110">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="b208a-110">Set up topic experiences</span></span>

<span data-ttu-id="b208a-111">Microsoft 365 でトピック エクスペリエンスを設定するには</span><span class="sxs-lookup"><span data-stu-id="b208a-111">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="b208a-112">Microsoft [365 管理センターで、[](https://admin.microsoft.com)セットアップ] **を選択し**、[ファイルとコンテンツ] **セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="b208a-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="b208a-113">[ファイルと **コンテンツ] セクションで** 、[ユーザーをナレッジ **に接続する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b208a-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="b208a-115">[知識 **へのユーザーの** 接続] ページで、[開始 **]** をクリックしてセットアップ プロセスの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b208a-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![概要](../media/k-get-started.png) 

4. <span data-ttu-id="b208a-117">[ナレッジ **ネットワークでトピックを検索する方法** の選択] ページで、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="b208a-117">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="b208a-118">**[SharePoint トピック ソース** の選択] セクションで、検出時にトピックのソースとしてクロールする SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="b208a-119">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-119">Choose from:</span></span>
    - <span data-ttu-id="b208a-120">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="b208a-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="b208a-121">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b208a-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="b208a-122">**選択したサイトを除く** すべてのサイト: 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="b208a-123">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="b208a-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="b208a-124">今後作成されるサイトは、トピック検出のソースとして含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="b208a-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="b208a-125">**選択したサイト** のみ: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="b208a-126">サイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="b208a-126">You can also upload a list of sites.</span></span> <span data-ttu-id="b208a-127">将来作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="b208a-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="b208a-128">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="b208a-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="b208a-130">[名前 **で除外するトピック] セクション** では、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="b208a-131">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="b208a-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="b208a-132">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="b208a-132">The options are:</span></span>
    - <span data-ttu-id="b208a-133">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="b208a-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="b208a-134">**名前でトピックを除外する**</span><span class="sxs-lookup"><span data-stu-id="b208a-134">**Exclude topics by name**</span></span>

    ![除外トピック](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="b208a-136">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="b208a-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="b208a-137">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="b208a-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="b208a-138">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="b208a-138">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="b208a-140">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="b208a-141">**[名前**]: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="b208a-142">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b208a-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="b208a-143">完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="b208a-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="b208a-144">部分一致: 特定の単語を含むすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="b208a-145">たとえば、円弧 *には*、円弧の円、円弧の円弧、トレーニング用の円弧など、単語の円弧を含むすべてのトピック *が除外されます*。 Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に注意 *してください*。</span><span class="sxs-lookup"><span data-stu-id="b208a-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="b208a-146">**略語 (省略可能)**: 頭字語を除外する場合は、略語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="b208a-147">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="b208a-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="b208a-148">.csv ファイルを完成して保存したら、[参照] を **選択して** 検索し、選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="b208a-149">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-149">Select **Next**.</span></span>

6. <span data-ttu-id="b208a-150">[トピック **を表示できるユーザーと** トピックを表示できる場所] ページで、トピックの可視性を構成します。</span><span class="sxs-lookup"><span data-stu-id="b208a-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="b208a-151">[ナレッジ **ネットワーク** の設定でトピックを表示できるユーザー] で、強調表示されているトピック、トピック カード、検索内のトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-151">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="b208a-152">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-152">You can select:</span></span>
    - <span data-ttu-id="b208a-153">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b208a-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b208a-154">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="b208a-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="b208a-155">**だれも**</span><span class="sxs-lookup"><span data-stu-id="b208a-155">**No one**</span></span>

    ![トピックを表示できるユーザー](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="b208a-157">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス のライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="b208a-158">[トピック **管理のアクセス許可]** ページで、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="b208a-159">[トピック **を作成および編集できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="b208a-160">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b208a-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b208a-161">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="b208a-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="b208a-162">**だれも**</span><span class="sxs-lookup"><span data-stu-id="b208a-162">**No one**</span></span>

    ![トピックを作成および編集できるトピック管理のアクセス許可](../media/ksetup3.png) 

8. <span data-ttu-id="b208a-164">[トピック **を管理できるユーザー] セクション** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="b208a-165">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b208a-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="b208a-166">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="b208a-166">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="b208a-168">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-168">Select **Next**.</span></span>

9. <span data-ttu-id="b208a-169">[ **トピック センターの** 作成] ページでは、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="b208a-170">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b208a-170">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="b208a-171">必要に応じて、[説明] ボックスに簡単な説明 **を入力** できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-171">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="b208a-172">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-172">Select **Next**.</span></span>

   ![ナレッジ センターを作成する](../media/ksetup4.png)  

10. <span data-ttu-id="b208a-174">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b208a-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b208a-175">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="b208a-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="b208a-176">サポート **技術情報ネットワークがアクティブ** 化されたページが表示され、選択したサイトのトピックの分析とナレッジ センター サイトの作成がシステムによって開始されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="b208a-176">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="b208a-177">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-177">Select **Done**.</span></span>

12. <span data-ttu-id="b208a-178">[Connect people to knowledge] (知識への接続 **) ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="b208a-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="b208a-179">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="b208a-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="b208a-181">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b208a-181">Assign licenses</span></span>

<span data-ttu-id="b208a-182">トピック エクスペリエンスを構成したら、トピック エクスペリエンスを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b208a-182">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="b208a-183">ライセンスを持つユーザーだけが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="b208a-184">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b208a-184">To assign licenses:</span></span>

1. <span data-ttu-id="b208a-185">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b208a-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="b208a-186">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b208a-186">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="b208a-187">[**もっと割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b208a-187">Select **Assign more**.</span></span>

4. <span data-ttu-id="b208a-188">[ライセンス **] で**、[トピックエクスペリエンス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b208a-188">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="b208a-189">[ **アプリ]** で、[ **インデックス付き Graph コネクタ検索]** と [トピック エクスペリエンス] の **両方が** 選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b208a-189">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b208a-190">![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="b208a-190">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="b208a-191">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b208a-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="b208a-192">トピック エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="b208a-192">Manage topic experiences</span></span>

<span data-ttu-id="b208a-193">トピックエクスペリエンスを設定したら [、Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理センターでセットアップ中に選択した設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b208a-193">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="b208a-194">次のリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b208a-194">See the following references:</span></span>

- [<span data-ttu-id="b208a-195">Microsoft 365 でのトピック検出の管理</span><span class="sxs-lookup"><span data-stu-id="b208a-195">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="b208a-196">Microsoft 365 でトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="b208a-196">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="b208a-197">Microsoft 365 でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="b208a-197">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="b208a-198">Microsoft 365 のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="b208a-198">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="b208a-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="b208a-199">See also</span></span>

[<span data-ttu-id="b208a-200">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="b208a-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
