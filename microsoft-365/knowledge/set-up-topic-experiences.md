---
title: Microsoft のトピックをセットアップする
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft のトピックをセットアップする方法について説明します。
ms.openlocfilehash: e8cfe1d849ba5df903f377fd001a8d067f80b608
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107922"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="efcd8-103">Microsoft のトピックをセットアップする</span><span class="sxs-lookup"><span data-stu-id="efcd8-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="efcd8-104">Microsoft 365 管理センターを使用して、トピックを設定および構成 [できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="efcd8-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="efcd8-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="efcd8-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="efcd8-106">この記事の手順を [開始する前に、「Microsoft のトピック](plan-topic-experiences.md) を計画する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efcd8-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="efcd8-107">Microsoft 365 管理センターにアクセスしてトピックを設定するには、全体管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="efcd8-107">You must be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="efcd8-108">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="efcd8-108">Video demonstration</span></span>

<span data-ttu-id="efcd8-109">このビデオでは、Microsoft 365 のトピックをセットアップするプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-109">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="efcd8-110">トピックの設定</span><span class="sxs-lookup"><span data-stu-id="efcd8-110">Set up Topics</span></span>

<span data-ttu-id="efcd8-111">トピックを設定するには</span><span class="sxs-lookup"><span data-stu-id="efcd8-111">To set up Topics</span></span>

1. <span data-ttu-id="efcd8-112">Microsoft [365 管理センターで、[](https://admin.microsoft.com)セットアップ] **を選択し**、[ファイルとコンテンツ] **セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-112">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="efcd8-113">[ファイルと **コンテンツ] セクションで** 、[ユーザーをナレッジに **接続する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="efcd8-113">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![ユーザーを知識に接続する](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="efcd8-115">[知識 **へのユーザーの** 接続] ページで、[開始 **]** をクリックしてセットアップ プロセスの手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-115">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![作業の開始](../media/k-get-started.png) 

4. <span data-ttu-id="efcd8-117">[ **トピックを検索する方法の** 選択] ページで、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-117">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="efcd8-118">**[SharePoint トピック ソース** の選択] セクションで、検出時にトピックのソースとしてクロールする SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-118">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="efcd8-119">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-119">Choose from:</span></span>
    - <span data-ttu-id="efcd8-120">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="efcd8-120">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="efcd8-121">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-121">This includes current and future sites.</span></span>
    - <span data-ttu-id="efcd8-122">**すべて (選択したサイトを** 除く): 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-122">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="efcd8-123">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-123">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="efcd8-124">今後作成されるサイトは、トピック検出のソースとして含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="efcd8-124">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="efcd8-125">**選択したサイト** のみ: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-125">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="efcd8-126">サイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-126">You can also upload a list of sites.</span></span> <span data-ttu-id="efcd8-127">将来作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="efcd8-127">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="efcd8-128">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="efcd8-128">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="efcd8-130">[名前 **で除外するトピック] セクション** では、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-130">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="efcd8-131">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-131">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="efcd8-132">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="efcd8-132">The options are:</span></span>
    - <span data-ttu-id="efcd8-133">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="efcd8-133">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="efcd8-134">**名前でトピックを除外する**</span><span class="sxs-lookup"><span data-stu-id="efcd8-134">**Exclude topics by name**</span></span>

    ![除外トピック](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="efcd8-136">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="efcd8-136">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="efcd8-137">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="efcd8-137">How to exclude topics by name</span></span>    

    <span data-ttu-id="efcd8-138">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-138">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートでトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="efcd8-140">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-140">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="efcd8-141">**[名前**]: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-141">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="efcd8-142">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="efcd8-142">There are two ways to do this:</span></span>
        - <span data-ttu-id="efcd8-143">完全一致: 正確な名前または頭字語 *(Contoso* や ATL など) *を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="efcd8-143">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="efcd8-144">部分一致: 特定の単語を含むすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-144">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="efcd8-145">たとえば、円弧 *には*、円弧の円、円弧の円弧、トレーニング用の円弧など、単語の円弧を含むすべてのトピック *が除外されます*。 Architecture など、単語の一部としてテキストが含まれるトピックは除外されない点に注意 *してください*。</span><span class="sxs-lookup"><span data-stu-id="efcd8-145">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="efcd8-146">**略式 (省略可能)**: 頭字語を除外する場合は、略語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-146">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="efcd8-147">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="efcd8-147">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="efcd8-148">.csv ファイルを完成して保存したら、[参照] を **選択して** 検索し、選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-148">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="efcd8-149">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-149">Select **Next**.</span></span>

6. <span data-ttu-id="efcd8-150">[トピック **を表示できるユーザーと** トピックを表示できる場所] ページで、トピックの可視性を構成します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-150">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="efcd8-151">[トピック **を表示** できるユーザー] 設定では、強調表示されたトピック、トピック カード、検索でのトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-151">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="efcd8-152">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-152">You can select:</span></span>
    - <span data-ttu-id="efcd8-153">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="efcd8-153">**Everyone in my organization**</span></span>
    - <span data-ttu-id="efcd8-154">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="efcd8-154">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="efcd8-155">**だれも**</span><span class="sxs-lookup"><span data-stu-id="efcd8-155">**No one**</span></span>

    ![トピックを表示できるユーザー](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="efcd8-157">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス のライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-157">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="efcd8-158">[トピック **管理のアクセス許可]** ページで、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-158">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="efcd8-159">[トピック **を作成および編集できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-159">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="efcd8-160">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="efcd8-160">**Everyone in my organization**</span></span>
    - <span data-ttu-id="efcd8-161">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="efcd8-161">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="efcd8-162">**だれも**</span><span class="sxs-lookup"><span data-stu-id="efcd8-162">**No one**</span></span>

    ![トピックを作成および編集できるトピック管理のアクセス許可](../media/ksetup3.png) 

8. <span data-ttu-id="efcd8-164">[トピック **を管理できるユーザー] セクション** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-164">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="efcd8-165">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="efcd8-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="efcd8-166">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="efcd8-166">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="efcd8-168">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-168">Select **Next**.</span></span>

9. <span data-ttu-id="efcd8-169">[ **トピック センターの** 作成] ページでは、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-169">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="efcd8-170">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-170">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="efcd8-171">必要に応じて、[説明] ボックスに簡単な説明 **を入力** できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-171">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="efcd8-172">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-172">Select **Next**.</span></span>

   ![ナレッジ センターを作成する](../media/ksetup4.png)  

10. <span data-ttu-id="efcd8-174">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-174">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="efcd8-175">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="efcd8-175">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="efcd8-176">アクティブ **化された [多** くのトピック] ページが表示され、選択したサイトのトピックの分析とトピック センター サイトの作成がシステムによって開始されます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-176">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="efcd8-177">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="efcd8-177">Select **Done**.</span></span>

12. <span data-ttu-id="efcd8-178">[Connect people to knowledge] (知識への接続 **) ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="efcd8-178">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="efcd8-179">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-179">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="efcd8-181">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="efcd8-181">Assign licenses</span></span>

<span data-ttu-id="efcd8-182">トピック エクスペリエンスを構成したら、トピックを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="efcd8-182">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="efcd8-183">ライセンスを持つユーザーだけが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-183">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="efcd8-184">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="efcd8-184">To assign licenses:</span></span>

1. <span data-ttu-id="efcd8-185">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="efcd8-185">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="efcd8-186">ライセンスを取得するユーザーを選択し、[ライセンスとアプリ **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="efcd8-186">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="efcd8-187">[ **アプリ]** で、[ **インデックス付き Graph コネクタ検索]** と [多くのトピック] の両方 **が** 選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="efcd8-187">Under **Apps**, make sure **Graph Connectors Search with Index** and **Viva Topics** are both selected.</span></span>

4. <span data-ttu-id="efcd8-188">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="efcd8-188">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="efcd8-189">トピック エクスペリエンスを管理する</span><span class="sxs-lookup"><span data-stu-id="efcd8-189">Manage topic experiences</span></span>

<span data-ttu-id="efcd8-190">トピックの設定が完了したら [、Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理センターでセットアップ時に選択した設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="efcd8-190">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="efcd8-191">次のリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efcd8-191">See the following references:</span></span>

- [<span data-ttu-id="efcd8-192">Microsoft のトピックの検出を管理するトピック</span><span class="sxs-lookup"><span data-stu-id="efcd8-192">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="efcd8-193">Microsoft のトピックに関するトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="efcd8-193">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="efcd8-194">Microsoft のトピックのアクセス許可を管理するトピック</span><span class="sxs-lookup"><span data-stu-id="efcd8-194">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="efcd8-195">Microsoft のトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="efcd8-195">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="efcd8-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="efcd8-196">See also</span></span>

[<span data-ttu-id="efcd8-197">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="efcd8-197">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
