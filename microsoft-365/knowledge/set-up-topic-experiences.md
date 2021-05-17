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
ms.openlocfilehash: 19395cf3a9ecc991f08f375425803cb81a2a1d35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930223"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="fc995-103">Microsoft Viva のトピックを設定する</span><span class="sxs-lookup"><span data-stu-id="fc995-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="fc995-104">管理センターの Microsoft 365を使用して、トピックを設定および構成[できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc995-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="fc995-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fc995-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="fc995-106">この記事の手順を [開始する前に、「Plan for Microsoft Viva Topics」](plan-topic-experiences.md) を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="fc995-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="fc995-107">ビバ トピックに[サブスクライブ](https://www.microsoft.com/microsoft-viva/topics)し、グローバル管理者または管理者SharePoint管理センターにアクセスし、トピックMicrosoft 365設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="fc995-108">管理対象デバイスを[SharePointするように構成](/sharepoint/control-access-from-unmanaged-devices)している場合は、必ず管理対象デバイスから Topics を設定してください。</span><span class="sxs-lookup"><span data-stu-id="fc995-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fc995-109">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="fc995-109">Video demonstration</span></span>

<span data-ttu-id="fc995-110">このビデオでは、トピックを設定するプロセスをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="fc995-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="fc995-111">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc995-111">Assign licenses</span></span>

<span data-ttu-id="fc995-112">トピックを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="fc995-113">ライセンスを持つユーザーだけが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックに関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="fc995-114">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fc995-114">To assign licenses:</span></span>

1. <span data-ttu-id="fc995-115">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc995-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="fc995-116">ライセンスを取得するユーザーを選択し、[ライセンスとアプリ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fc995-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="fc995-117">[ライセンス **] で**、[ビバ トピック] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fc995-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="fc995-118">[**アプリ]** で、[コネクタGraphインデックス付き検索 **(Viva Topics)** と **Viva Topics** の両方が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fc995-119">![Microsoft Viva Topics ライセンス (Microsoft 365センター)](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="fc995-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="fc995-120">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc995-120">Click **Save changes**.</span></span>

<span data-ttu-id="fc995-121">ライセンスが割り当てられた後、ユーザーがトピックにアクセスするには、最大で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="fc995-122">トピックを設定する</span><span class="sxs-lookup"><span data-stu-id="fc995-122">Set up Topics</span></span>

<span data-ttu-id="fc995-123">トピックを設定するには</span><span class="sxs-lookup"><span data-stu-id="fc995-123">To set up Topics</span></span>

1. <span data-ttu-id="fc995-124">管理センター [でMicrosoft 365を](https://admin.microsoft.com)選択し、[ファイルとコンテンツ]**セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="fc995-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="fc995-125">[ファイルと **コンテンツ] セクションで**、[ユーザーに **Connect] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fc995-125">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connectを知る](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="fc995-127">[ユーザー **をConnect] ページで**、[スタート]**を** クリックしてセットアップ プロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="fc995-127">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![開始する](../media/k-get-started.png) 

4. <span data-ttu-id="fc995-129">[ビバ **トピックの検索方法の選択] ページ** で、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="fc995-129">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="fc995-130">[トピック **ソースSharePoint選択**] セクションで、検出時にトピックSharePointとしてクロールするサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-130">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fc995-131">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-131">Choose from:</span></span>
    - <span data-ttu-id="fc995-132">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="fc995-132">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="fc995-133">これには、現在と今後のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc995-133">This includes current and future sites.</span></span>
    - <span data-ttu-id="fc995-134">**[すべて] (選択したサイトを** 除く): 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-134">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fc995-135">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fc995-135">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="fc995-136">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="fc995-136">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="fc995-137">**選択したサイトのみ**: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-137">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="fc995-138">サイトのリストをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fc995-138">You can also upload a list of sites.</span></span> <span data-ttu-id="fc995-139">今後作成されるサイトは、トピック検出のソースとして含められません。</span><span class="sxs-lookup"><span data-stu-id="fc995-139">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="fc995-140">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="fc995-140">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="fc995-142">[名前 **でトピックを除外する** ] セクションで、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-142">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="fc995-143">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="fc995-143">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="fc995-144">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="fc995-144">The options are:</span></span>
    - <span data-ttu-id="fc995-145">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="fc995-145">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="fc995-146">**トピックを名前で除外する**</span><span class="sxs-lookup"><span data-stu-id="fc995-146">**Exclude topics by name**</span></span>

    ![トピックを除外する](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="fc995-148">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="fc995-148">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="fc995-149">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="fc995-149">How to exclude topics by name</span></span>    

    <span data-ttu-id="fc995-150">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="fc995-150">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートのトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="fc995-152">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-152">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="fc995-153">**Name**: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-153">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="fc995-154">これを行うには次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-154">There are two ways to do this:</span></span>
        - <span data-ttu-id="fc995-155">完全一致: 正確な名前または頭字語 (Contoso や ATL *など)\*\*を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="fc995-155">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="fc995-156">部分一致: 特定の単語が含まれていますすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-156">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="fc995-157">たとえば、*円弧は、* アーク円、プラズマアーク溶接、トレーニングアークなど、アークという単語を含むすべてのトピック *を除外します*。テキストが単語の一部として含まれているトピック (Architecture など) は除外されない点に *注意してください*。</span><span class="sxs-lookup"><span data-stu-id="fc995-157">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="fc995-158">**略語 (省略可能)**: 頭字語を除外する場合は、頭字語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-158">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="fc995-159">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="fc995-159">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="fc995-160">ファイルを完了して保存したら、[参照] を.csv検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-160">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="fc995-161">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-161">Select **Next**.</span></span>

6. <span data-ttu-id="fc995-162">このページ **Whoトピックを表示し、** どこでトピックを表示できるのかページで、トピックの表示を構成します。</span><span class="sxs-lookup"><span data-stu-id="fc995-162">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="fc995-163">[トピック **Who** 表示] の設定で、強調表示されているトピック、トピック カード、検索のトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-163">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="fc995-164">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-164">You can select:</span></span>
    - <span data-ttu-id="fc995-165">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fc995-165">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fc995-166">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fc995-166">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="fc995-167">**だれも**</span><span class="sxs-lookup"><span data-stu-id="fc995-167">**No one**</span></span>

    ![Whoトピックを表示する](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="fc995-169">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス ライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-169">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="fc995-170">[トピック **管理のアクセス許可] ページ** で、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-170">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="fc995-171">[トピックを **Who編集できる]** セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-171">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="fc995-172">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fc995-172">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fc995-173">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fc995-173">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="fc995-174">**だれも**</span><span class="sxs-lookup"><span data-stu-id="fc995-174">**No one**</span></span>

    ![トピック管理のアクセス許可(トピックを作成および編集できるユーザー)](../media/ksetup3.png) 

8. <span data-ttu-id="fc995-176">[トピックWho **管理する] セクションで**、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-176">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="fc995-177">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fc995-177">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fc995-178">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fc995-178">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="fc995-180">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-180">Select **Next**.</span></span>

9. <span data-ttu-id="fc995-181">[トピック **センターの作成** ] ページで、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-181">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="fc995-182">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fc995-182">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="fc995-183">必要に応じて、[説明] ボックスに短い説明を **入力** できます。</span><span class="sxs-lookup"><span data-stu-id="fc995-183">You can optionally type a short description in the **Description** box.</span></span> 

   <span data-ttu-id="fc995-184">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-184">Select **Next**.</span></span>

   ![ナレッジ センターの作成](../media/ksetup4.png)  

10. <span data-ttu-id="fc995-186">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fc995-186">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="fc995-187">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="fc995-187">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="fc995-188">[ **ビバ トピック] が** アクティブ化されたページが表示され、選択したサイトのトピックの分析が開始され、トピック センター サイトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fc995-188">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="fc995-189">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fc995-189">Select **Done**.</span></span>

12. <span data-ttu-id="fc995-190">ユーザーからナレッジ ページにConnect **返** されます。</span><span class="sxs-lookup"><span data-stu-id="fc995-190">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="fc995-191">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="fc995-191">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![設定適用](../media/ksetup7.png)    

<span data-ttu-id="fc995-193">最初にトピックの検出を有効にすると、すべての推奨トピックが [トピックの管理] ビューに表示されるまで最大 2 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc995-193">Note that the first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="fc995-194">トピックの検出は、コンテンツの新しいコンテンツまたは更新が行われた後も継続されます。</span><span class="sxs-lookup"><span data-stu-id="fc995-194">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="fc995-195">ビバ トピックスが新しい情報を評価する場合、組織で提案されるトピックの数が変動するのが普通です。</span><span class="sxs-lookup"><span data-stu-id="fc995-195">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

## <a name="manage-topic-experiences"></a><span data-ttu-id="fc995-196">トピック エクスペリエンスの管理</span><span class="sxs-lookup"><span data-stu-id="fc995-196">Manage topic experiences</span></span>

<span data-ttu-id="fc995-197">トピックを設定したら、管理センターでセットアップ中に選択した[設定Microsoft 365できます](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)。</span><span class="sxs-lookup"><span data-stu-id="fc995-197">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="fc995-198">次の参考資料を参照してください:</span><span class="sxs-lookup"><span data-stu-id="fc995-198">See the following references:</span></span>

- [<span data-ttu-id="fc995-199">Microsoft Viva Topics でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="fc995-199">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="fc995-200">Microsoft Viva Topics でのトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="fc995-200">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="fc995-201">Microsoft Viva Topics でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="fc995-201">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="fc995-202">Microsoft Viva Topics でトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="fc995-202">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="fc995-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc995-203">See also</span></span>

[<span data-ttu-id="fc995-204">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="fc995-204">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
