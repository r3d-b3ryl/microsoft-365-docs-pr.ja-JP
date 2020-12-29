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
ms.openlocfilehash: 3ff822d863e99f7e52089d3efde3d597df9957c7
ms.sourcegitcommit: 806536f859ac864228797f1f2f23b8f41040a6b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/28/2020
ms.locfileid: "49735812"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a><span data-ttu-id="95f00-103">Microsoft 365 でのトピック エクスペリエンスのセットアップ</span><span class="sxs-lookup"><span data-stu-id="95f00-103">Set up topic experiences in Microsoft 365</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

</br>

<span data-ttu-id="95f00-104">Microsoft 365 管理センターを使用して、トピックエクスペリエンスを設定および [構成できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="95f00-104">You can use the Microsoft 365 admin center to set up and configure [topic experiences](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="95f00-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="95f00-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="95f00-106">この記事の手順を開始 [する前に、「](plan-topic-experiences.md) トピックエクスペリエンスを計画する」を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="95f00-106">Be sure to read [Plan topic experiences](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="95f00-107">Microsoft 365 管理センターにアクセスしてトピックエクスペリエンスを設定するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f00-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up topic experiences.</span></span>

## <a name="set-up-topic-experiences"></a><span data-ttu-id="95f00-108">トピック エクスペリエンスを設定する</span><span class="sxs-lookup"><span data-stu-id="95f00-108">Set up topic experiences</span></span>

<span data-ttu-id="95f00-109">Microsoft 365 でトピック エクスペリエンスを設定するには</span><span class="sxs-lookup"><span data-stu-id="95f00-109">To set up topic experiences in Microsoft 365</span></span>

1. <span data-ttu-id="95f00-110">Microsoft [365 管理センターで、[](https://admin.microsoft.com)セットアップ] **を選択し**、[ファイルとコンテンツ] **セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="95f00-110">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="95f00-111">[ファイルと **コンテンツ] セクションで** 、[ユーザーをナレッジ **に接続する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95f00-111">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="95f00-113">[知識 **へのユーザーの** 接続] ページで、[開始 **]** をクリックしてセットアップ プロセスの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="95f00-113">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![開始する](../media/k-get-started.png) 

4. <span data-ttu-id="95f00-115">[ナレッジ **ネットワークでトピックを検索する方法** の選択] ページで、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="95f00-115">On the **Choose how the knowledge network can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="95f00-116">**[SharePoint トピック ソース** の選択] セクションで、検出時にトピックのソースとしてクロールする SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-116">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="95f00-117">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-117">Choose from:</span></span>
    - <span data-ttu-id="95f00-118">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="95f00-118">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="95f00-119">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f00-119">This includes current and future sites.</span></span>
    - <span data-ttu-id="95f00-120">**選択したサイトを除く** すべてのサイト: 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-120">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="95f00-121">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="95f00-121">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="95f00-122">将来作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f00-122">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="95f00-123">**選択したサイト** のみ: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-123">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="95f00-124">サイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="95f00-124">You can also upload a list of sites.</span></span> <span data-ttu-id="95f00-125">将来作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="95f00-125">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="95f00-126">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="95f00-126">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="95f00-128">[名前 **で除外するトピック] セクション** では、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-128">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="95f00-129">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f00-129">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="95f00-130">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="95f00-130">The options are:</span></span>
    - <span data-ttu-id="95f00-131">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="95f00-131">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="95f00-132">**名前でトピックを除外する**</span><span class="sxs-lookup"><span data-stu-id="95f00-132">**Exclude topics by name**</span></span>

    ![除外トピック](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="95f00-134">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="95f00-134">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="95f00-135">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="95f00-135">How to exclude topics by name</span></span>    

    <span data-ttu-id="95f00-136">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="95f00-136">If you need to exclude topics, after selecting **Exclude topics by name**, select download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="95f00-138">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-138">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="95f00-139">**[名前**]: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-139">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="95f00-140">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="95f00-140">There are two ways to do this:</span></span>
        - <span data-ttu-id="95f00-141">完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="95f00-141">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="95f00-142">部分一致: 特定の単語を含むすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-142">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="95f00-143">たとえば、円弧 *には*、円弧の円、円弧の円弧、トレーニング用の円弧など、単語の円弧を含むすべてのトピック *が除外されます*。 ただし、Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に *注意してください*。</span><span class="sxs-lookup"><span data-stu-id="95f00-143">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="95f00-144">**略式 (省略可能)**: 頭字語を除外する場合は、略語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-144">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="95f00-145">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="95f00-145">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="95f00-146">.csv ファイルを完成して保存したら、[参照] を **選択して** 検索し、選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-146">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="95f00-147">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-147">Select **Next**.</span></span>

6. <span data-ttu-id="95f00-148">[トピック **を表示できるユーザーと** トピックを表示できる場所] ページで、トピックの可視性を構成します。</span><span class="sxs-lookup"><span data-stu-id="95f00-148">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="95f00-149">[ナレッジ **ネットワーク** の設定でトピックを表示できるユーザー] で、強調表示されているトピック、トピック カード、検索でのトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-149">In the **Who can see topics in the knowledge network** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="95f00-150">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-150">You can select:</span></span>
    - <span data-ttu-id="95f00-151">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="95f00-151">**Everyone in my organization**</span></span>
    - <span data-ttu-id="95f00-152">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="95f00-152">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="95f00-153">**だれも**</span><span class="sxs-lookup"><span data-stu-id="95f00-153">**No one**</span></span>

    ![トピックを表示できるユーザー](../media/ksetup2.png)  

 > [!Note] 
 > <span data-ttu-id="95f00-155">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス のライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-155">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="95f00-156">[トピック **管理のアクセス許可]** ページで、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-156">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="95f00-157">[トピック **を作成および編集できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-157">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="95f00-158">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="95f00-158">**Everyone in my organization**</span></span>
    - <span data-ttu-id="95f00-159">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="95f00-159">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="95f00-160">**だれも**</span><span class="sxs-lookup"><span data-stu-id="95f00-160">**No one**</span></span>

    ![トピックを作成および編集できるトピック管理のアクセス許可](../media/ksetup3.png) 

8. <span data-ttu-id="95f00-162">[トピック **を管理できるユーザー] セクション** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-162">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="95f00-163">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="95f00-163">**Everyone in my organization**</span></span>
    - <span data-ttu-id="95f00-164">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="95f00-164">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="95f00-166">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-166">Select **Next**.</span></span>

9. <span data-ttu-id="95f00-167">[ **トピック センターの** 作成] ページでは、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-167">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="95f00-168">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="95f00-168">In the **Site name** box, type a name for your Topic center.</span></span> <span data-ttu-id="95f00-169">必要に応じて、[説明] ボックスに簡単な説明 **を入力** できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-169">You can optionally type a short description in the **Description** box.</span></span> 

<span data-ttu-id="95f00-170">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-170">Select **Next**.</span></span>

   ![ナレッジ センターを作成する](../media/ksetup4.png)  

10. <span data-ttu-id="95f00-172">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="95f00-172">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="95f00-173">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="95f00-173">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="95f00-174">サポート **技術情報ネットワークがアクティブ** 化されたページが表示され、選択したサイトのトピックの分析とナレッジ センター サイトの作成がシステムによって開始されるのを確認します。</span><span class="sxs-lookup"><span data-stu-id="95f00-174">The **Knowledge network activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the Knowledge Center site.</span></span> <span data-ttu-id="95f00-175">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-175">Select **Done**.</span></span>

12. <span data-ttu-id="95f00-176">[Connect people to knowledge] (知識への接続 **) ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="95f00-176">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="95f00-177">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="95f00-177">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="95f00-179">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="95f00-179">Assign licenses</span></span>

<span data-ttu-id="95f00-180">トピック エクスペリエンスを構成したら、トピック エクスペリエンスを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f00-180">Once you have configured topic experiences, you must assign licenses for the users who will be using topic experiences.</span></span> <span data-ttu-id="95f00-181">ライセンスを持つユーザーだけが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-181">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="95f00-182">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="95f00-182">To assign licenses:</span></span>

1. <span data-ttu-id="95f00-183">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="95f00-183">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="95f00-184">ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95f00-184">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="95f00-185">[**もっと割り当てる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="95f00-185">Select **Assign more**.</span></span>

4. <span data-ttu-id="95f00-186">[ライセンス **] で**、[トピックエクスペリエンス] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="95f00-186">Under **Licenses**, select **Topic Experiences**.</span></span>

5. <span data-ttu-id="95f00-187">[ **アプリ]** で、[ **インデックス付き Graph コネクタ検索]** と [トピック エクスペリエンス] の **両方が** 選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f00-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Topic Experiences** are both selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="95f00-188">![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="95f00-188">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

6. <span data-ttu-id="95f00-189">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95f00-189">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="95f00-190">トピック エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="95f00-190">Manage topic experiences</span></span>

<span data-ttu-id="95f00-191">トピックエクスペリエンスを設定したら [、Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理センターでセットアップ中に選択した設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="95f00-191">Once you have set up topic experiences, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="95f00-192">次のリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f00-192">See the following references:</span></span>

- [<span data-ttu-id="95f00-193">Microsoft 365 でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="95f00-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="95f00-194">Microsoft 365 でトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="95f00-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="95f00-195">Microsoft 365 でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="95f00-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="95f00-196">Microsoft 365 のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="95f00-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="95f00-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="95f00-197">See also</span></span>

[<span data-ttu-id="95f00-198">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="95f00-198">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
