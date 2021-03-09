---
title: Microsoft Viva のトピックを設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva のトピックを設定する方法について説明します。
ms.openlocfilehash: cc420a0631f5b861341116abcd50cfe90e15450e
ms.sourcegitcommit: 6e260f5f5842debe1098138eecea9068330dc17f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "50551893"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="97447-103">Microsoft Viva のトピックを設定する</span><span class="sxs-lookup"><span data-stu-id="97447-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="97447-104">Microsoft 365 管理センターを使用して、トピックを設定および構成 [できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="97447-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="97447-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="97447-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="97447-106">この記事の手順を [開始する前に、「Plan for Microsoft Viva Topics」](plan-topic-experiences.md) を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="97447-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="97447-107">Microsoft 365 管理センターにアクセスしてトピックを設定するには、 [ビ](https://www.microsoft.com/microsoft-viva/topics) バ トピックをサブスクライブし、グローバル管理者または SharePoint 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="97447-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="97447-108">管理デバイスを必要とするように[](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)SharePoint を構成している場合は、管理デバイスからトピックを設定してください。</span><span class="sxs-lookup"><span data-stu-id="97447-108">If you have configured SharePoint to [require managed devices](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="97447-109">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="97447-109">Video demonstration</span></span>

<span data-ttu-id="97447-110">このビデオでは、Microsoft 365 でトピックを設定するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="97447-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a><span data-ttu-id="97447-111">トピックを設定する</span><span class="sxs-lookup"><span data-stu-id="97447-111">Set up Topics</span></span>

<span data-ttu-id="97447-112">トピックを設定するには</span><span class="sxs-lookup"><span data-stu-id="97447-112">To set up Topics</span></span>

1. <span data-ttu-id="97447-113">Microsoft [365 管理センターで](https://admin.microsoft.com)、[ **セットアップ]** を選択し、[ファイルとコンテンツ] **セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="97447-113">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="97447-114">[ファイルと **コンテンツ] セクションで** 、[ユーザーをナレッジ **に接続する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="97447-114">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![ユーザーをナレッジに接続する](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="97447-116">[ユーザーを **ナレッジに接続する] ページ** で、[スタート] **を** クリックしてセットアップ プロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="97447-116">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![概要](../media/k-get-started.png) 

4. <span data-ttu-id="97447-118">[ビバ **トピックの検索方法の選択] ページ** で、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="97447-118">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="97447-119">**[SharePoint トピック ソースの選択**] セクションで、検出中にトピックのソースとしてクロールする SharePoint サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-119">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="97447-120">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-120">Choose from:</span></span>
    - <span data-ttu-id="97447-121">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="97447-121">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="97447-122">これには、現在および将来のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="97447-122">This includes current and future sites.</span></span>
    - <span data-ttu-id="97447-123">**[すべて] (選択したサイトを** 除く): 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-123">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="97447-124">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="97447-124">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="97447-125">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="97447-125">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="97447-126">**選択したサイトのみ**: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-126">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="97447-127">サイトのリストをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="97447-127">You can also upload a list of sites.</span></span> <span data-ttu-id="97447-128">今後作成されるサイトは、トピック検出のソースとして含まれません。</span><span class="sxs-lookup"><span data-stu-id="97447-128">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="97447-129">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="97447-129">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="97447-131">[名前 **でトピックを除外する** ] セクションで、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="97447-131">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="97447-132">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="97447-132">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="97447-133">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="97447-133">The options are:</span></span>
    - <span data-ttu-id="97447-134">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="97447-134">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="97447-135">**トピックを名前で除外する**</span><span class="sxs-lookup"><span data-stu-id="97447-135">**Exclude topics by name**</span></span>

    ![トピックを除外する](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="97447-137">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="97447-137">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="97447-138">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="97447-138">How to exclude topics by name</span></span>    

    <span data-ttu-id="97447-139">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="97447-139">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートのトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="97447-141">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-141">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="97447-142">**名前**: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-142">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="97447-143">これを行うには 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="97447-143">There are two ways to do this:</span></span>
        - <span data-ttu-id="97447-144">完全一致: 正確な名前または頭字語 (Contoso や ATL *など)\*\*を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="97447-144">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="97447-145">部分一致: 特定の単語が含まれていますすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="97447-145">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="97447-146">たとえば、*円弧は、* アーク円、プラズマアーク溶接、トレーニングアークなど、アークという単語を含むすべてのトピック *を除外します*。テキストが単語の一部として含まれているトピック (Architecture など) は除外されない点に *注意してください*。</span><span class="sxs-lookup"><span data-stu-id="97447-146">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="97447-147">**略語 (省略可能)**: 頭字語を除外する場合は、頭字語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-147">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="97447-148">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="97447-148">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="97447-149">.csv ファイルを完了して保存したら、[参照] を選択して検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-149">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="97447-150">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-150">Select **Next**.</span></span>

6. <span data-ttu-id="97447-151">[トピック **を表示できるユーザーと** トピックを表示できる場所] ページで、トピックの表示を構成します。</span><span class="sxs-lookup"><span data-stu-id="97447-151">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="97447-152">[トピック **を表示** できるユーザー] 設定で、強調表示されているトピック、トピック カード、検索のトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-152">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="97447-153">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="97447-153">You can select:</span></span>
    - <span data-ttu-id="97447-154">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="97447-154">**Everyone in my organization**</span></span>
    - <span data-ttu-id="97447-155">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="97447-155">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="97447-156">**だれも**</span><span class="sxs-lookup"><span data-stu-id="97447-156">**No one**</span></span>

    ![トピックを表示できるユーザー](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="97447-158">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス ライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97447-158">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="97447-159">[トピック **管理のアクセス許可] ページ** で、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-159">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="97447-160">[トピック **を作成および編集できるユーザー** ] セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="97447-160">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="97447-161">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="97447-161">**Everyone in my organization**</span></span>
    - <span data-ttu-id="97447-162">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="97447-162">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="97447-163">**だれも**</span><span class="sxs-lookup"><span data-stu-id="97447-163">**No one**</span></span>

    ![トピック管理のアクセス許可(トピックを作成および編集できるユーザー)](../media/ksetup3.png) 

8. <span data-ttu-id="97447-165">[トピック **を管理できるユーザー] セクション** で、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="97447-165">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="97447-166">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="97447-166">**Everyone in my organization**</span></span>
    - <span data-ttu-id="97447-167">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="97447-167">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="97447-169">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-169">Select **Next**.</span></span>

9. <span data-ttu-id="97447-170">[トピック **センターの作成** ] ページで、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97447-170">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="97447-171">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="97447-171">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="97447-172">必要に応じて、[説明] ボックスに短い説明を **入力** できます。</span><span class="sxs-lookup"><span data-stu-id="97447-172">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="97447-173">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-173">Select **Next**.</span></span>

   ![ナレッジ センターの作成](../media/ksetup4.png)  

10. <span data-ttu-id="97447-175">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="97447-175">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="97447-176">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="97447-176">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="97447-177">[ **ビバ トピック] が** アクティブ化されたページが表示され、選択したサイトのトピックの分析が開始され、トピック センター サイトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="97447-177">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="97447-178">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="97447-178">Select **Done**.</span></span>

12. <span data-ttu-id="97447-179">[ユーザーをナレッジに接続 **する] ページに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="97447-179">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="97447-180">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="97447-180">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![適用される設定](../media/ksetup7.png)    

## <a name="assign-licenses"></a><span data-ttu-id="97447-182">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="97447-182">Assign licenses</span></span>

<span data-ttu-id="97447-183">トピック エクスペリエンスを構成したら、トピックを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="97447-183">Once you have configured topic experiences, you must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="97447-184">ライセンスを持つユーザーだけが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="97447-184">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="97447-185">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="97447-185">To assign licenses:</span></span>

1. <span data-ttu-id="97447-186">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="97447-186">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="97447-187">ライセンスを取得するユーザーを選択し、[ライセンスとアプリ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="97447-187">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="97447-188">[ライセンス **] で**、[ビバ トピック] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="97447-188">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="97447-189">[ **アプリ]** で **、[Graph Connectors Search with Index (Viva Topics)** と **Viva Topics の** 両方が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="97447-189">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

    ![Microsoft 365 管理センターの Microsoft Viva Topics ライセンス](../media/topic-experiences-licenses.png)

5. <span data-ttu-id="97447-191">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97447-191">Click **Save changes**.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="97447-192">トピック エクスペリエンスの管理</span><span class="sxs-lookup"><span data-stu-id="97447-192">Manage topic experiences</span></span>

<span data-ttu-id="97447-193">トピックを設定したら [、Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)管理センターでセットアップ時に選択した設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="97447-193">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="97447-194">次の参考資料を参照してください:</span><span class="sxs-lookup"><span data-stu-id="97447-194">See the following references:</span></span>

- [<span data-ttu-id="97447-195">Microsoft Viva Topics でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="97447-195">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="97447-196">Microsoft Viva Topics でのトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="97447-196">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="97447-197">Microsoft Viva Topics でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="97447-197">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="97447-198">Microsoft Viva Topics でトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="97447-198">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="97447-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="97447-199">See also</span></span>

[<span data-ttu-id="97447-200">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="97447-200">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
