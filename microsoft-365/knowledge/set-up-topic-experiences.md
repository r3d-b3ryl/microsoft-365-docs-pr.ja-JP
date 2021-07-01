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
ms.openlocfilehash: 42f84b9b792907d7fe118e0b15c3767674ddf19b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229589"
---
# <a name="set-up-microsoft-viva-topics"></a><span data-ttu-id="fb0de-103">Microsoft Viva のトピックを設定する</span><span class="sxs-lookup"><span data-stu-id="fb0de-103">Set up Microsoft Viva Topics</span></span>

<span data-ttu-id="fb0de-104">[トピック] セクションを使用Microsoft 365 管理センタートピックを設定および構成[できます](topic-experiences-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fb0de-104">You can use the Microsoft 365 admin center to set up and configure [Topics](topic-experiences-overview.md).</span></span> 

<span data-ttu-id="fb0de-105">環境内でトピックをセットアップおよび構成する最善の方法を計画することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fb0de-105">It is important to plan the best way to set up and configure topics in your environment.</span></span> <span data-ttu-id="fb0de-106">この記事の手順を [開始する前に、「Plan for Microsoft Viva Topics」](plan-topic-experiences.md) を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="fb0de-106">Be sure to read [Plan for Microsoft Viva Topics](plan-topic-experiences.md) before you begin the procedures in this article.</span></span>

<span data-ttu-id="fb0de-107">ビバ トピックに[アクセスして](https://www.microsoft.com/microsoft-viva/topics)トピックを設定するには、ビバ トピックにサブスクライブし、グローバル管理者または管理者SharePoint Microsoft 365 管理センター管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-107">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="fb0de-108">管理対象デバイスを[SharePointするように構成](/sharepoint/control-access-from-unmanaged-devices)している場合は、必ず管理対象デバイスから Topics を設定してください。</span><span class="sxs-lookup"><span data-stu-id="fb0de-108">If you have configured SharePoint to [require managed devices](/sharepoint/control-access-from-unmanaged-devices), be sure to set up Topics from a managed device.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fb0de-109">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="fb0de-109">Video demonstration</span></span>

<span data-ttu-id="fb0de-110">このビデオでは、トピックを設定するプロセスをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="fb0de-110">This video shows the process for setting up Topics in Microsoft 365.</span></span>

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a><span data-ttu-id="fb0de-111">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fb0de-111">Assign licenses</span></span>

<span data-ttu-id="fb0de-112">トピックを使用するユーザーにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-112">You must assign licenses for the users who will be using Topics.</span></span> <span data-ttu-id="fb0de-113">ライセンスのあるユーザーのみが、ハイライト、トピック カード、トピック ページ、トピック センターなどのトピックの情報を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-113">Only users with a license can see information on topics including highlights, topic cards, topic pages and the topic center.</span></span> 

<span data-ttu-id="fb0de-114">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fb0de-114">To assign licenses:</span></span>

1. <span data-ttu-id="fb0de-115">Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb0de-115">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="fb0de-116">ライセンスを取得するユーザーを選択し、[ライセンスとアプリ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fb0de-116">Select the users that you want to license, and click **Licenses and apps**.</span></span>

3. <span data-ttu-id="fb0de-117">[ライセンス **] で**、[ビバ トピック] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fb0de-117">Under **Licenses**, select **Viva Topics**.</span></span>

4. <span data-ttu-id="fb0de-118">[**アプリ]** で、[コネクタGraphインデックス付き検索 **(Viva Topics)** と **Viva Topics** の両方が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-118">Under **Apps**, make sure **Graph Connectors Search with Index (Viva Topics)** and **Viva Topics** are both selected.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fb0de-119">![Microsoft Viva Topics のライセンスは、Microsoft 365 管理センター](../media/topic-experiences-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="fb0de-119">![Microsoft Viva Topics licenses in the Microsoft 365 admin center](../media/topic-experiences-licenses.png)</span></span>

5. <span data-ttu-id="fb0de-120">**[変更の保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb0de-120">Click **Save changes**.</span></span>

<span data-ttu-id="fb0de-121">ライセンスが割り当てられた後、ユーザーがトピックにアクセスするには、最大で 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-121">It may take up to an hour for users to get access to Topics after the licenses are assigned.</span></span>

## <a name="set-up-topics"></a><span data-ttu-id="fb0de-122">トピックを設定する</span><span class="sxs-lookup"><span data-stu-id="fb0de-122">Set up Topics</span></span>

> [!Note]
> <span data-ttu-id="fb0de-123">初めてトピックの検出を有効にすると、[トピックの管理] ビューに提案されているトピックすべてが表示されるまで最大 2 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-123">The first time topic discovery is enabled, it may take up to two weeks for all suggested topics to appear in the Manage Topics view.</span></span> <span data-ttu-id="fb0de-124">トピックの検出は、コンテンツの新しいコンテンツまたは更新が行われた後も継続されます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-124">Topic discovery continues as new content or updates to content are made.</span></span> <span data-ttu-id="fb0de-125">Viva トピックが新しい情報を評価するため、組織内でのおすすめのトピック数が変動するのは普通のことです。</span><span class="sxs-lookup"><span data-stu-id="fb0de-125">It is normal to have fluctuations in the number of suggested topics in your organization as Viva Topics evaluates new information.</span></span>

<span data-ttu-id="fb0de-126">トピックを設定するには</span><span class="sxs-lookup"><span data-stu-id="fb0de-126">To set up Topics</span></span>
1. <span data-ttu-id="fb0de-127">[ファイル] [Microsoft 365 管理センター[](https://admin.microsoft.com)**セットアップ**] を選択し、[ファイルとコンテンツ]**セクションを表示** します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-127">In the [Microsoft 365 admin center](https://admin.microsoft.com), select **Setup**, and then view the **Files and content** section.</span></span>
2. <span data-ttu-id="fb0de-128">[ファイルと **コンテンツ] セクションで**、[ユーザーに **Connect] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fb0de-128">In the **Files and content** section, click **Connect people to knowledge**.</span></span>

    ![Connectを知る](../media/admin-org-knowledge-options.png) 

3. <span data-ttu-id="fb0de-130">[ユーザー **をConnect] ページで**、[スタート]**を** クリックしてセットアップ プロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-130">On the **Connect people to knowledge** page, click **Get started** to walk you through the setup process.</span></span>

    ![作業の開始](../media/k-get-started.png) 

4. <span data-ttu-id="fb0de-132">[ビバ **トピックの検索方法の選択] ページ** で、トピックの検出を構成します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-132">On the **Choose how Viva Topics can find topics** page, you will configure topic discovery.</span></span> <span data-ttu-id="fb0de-133">[トピック **ソースSharePoint選択**] セクションで、検出時にトピックSharePointとしてクロールするサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-133">In the **Select SharePoint topic sources** section, select which SharePoint sites will be crawled as sources for your topics during discovery.</span></span> <span data-ttu-id="fb0de-134">次から選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-134">Choose from:</span></span>
    - <span data-ttu-id="fb0de-135">**すべてのサイト**: 組織内のすべての SharePoint サイト。</span><span class="sxs-lookup"><span data-stu-id="fb0de-135">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="fb0de-136">これには、現在と今後のサイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-136">This includes current and future sites.</span></span>
    - <span data-ttu-id="fb0de-137">**[すべて] (選択したサイトを** 除く): 除外するサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-137">**All, except selected sites**: Type the names of the sites you want to exclude.</span></span>  <span data-ttu-id="fb0de-138">検出からオプトアウトするサイトの一覧をアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-138">You can also upload a list of sites that you want to opt out from discovery.</span></span> <span data-ttu-id="fb0de-139">今後作成されるサイトは、トピック検出のソースとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-139">Sites created in future will be included as sources for topic discovery.</span></span> 
    - <span data-ttu-id="fb0de-140">**選択したサイトのみ**: 含めるサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-140">**Only selected sites**: Type the names of the sites you want to include.</span></span> <span data-ttu-id="fb0de-141">サイトのリストをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-141">You can also upload a list of sites.</span></span> <span data-ttu-id="fb0de-142">今後作成されるサイトは、トピック検出のソースとして含められません。</span><span class="sxs-lookup"><span data-stu-id="fb0de-142">Sites created in the future will not be included as sources for topic discovery.</span></span>
    - <span data-ttu-id="fb0de-143">**サイトなし**: SharePoint サイトを含めない。</span><span class="sxs-lookup"><span data-stu-id="fb0de-143">**No sites**: Do not include any SharePoint sites.</span></span>

    ![トピックの検索方法を選択する](../media/ksetup1.png) 
   
5. <span data-ttu-id="fb0de-145">[名前 **でトピックを除外する** ] セクションで、トピックの検出から除外するトピックの名前を追加できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-145">In the **Exclude topics by name** section, you can add names of topics you want to exclude from topic discovery.</span></span> <span data-ttu-id="fb0de-146">機密情報がトピックとして含まれるのを防ぐには、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-146">Use this setting to prevent sensitive information from being included as topics.</span></span> <span data-ttu-id="fb0de-147">以下のオプションがあります:</span><span class="sxs-lookup"><span data-stu-id="fb0de-147">The options are:</span></span>
    - <span data-ttu-id="fb0de-148">**トピックを除外しない**</span><span class="sxs-lookup"><span data-stu-id="fb0de-148">**Don't exclude any topics**</span></span> 
    - <span data-ttu-id="fb0de-149">**トピックを名前で除外する**</span><span class="sxs-lookup"><span data-stu-id="fb0de-149">**Exclude topics by name**</span></span>

    ![トピックを除外する](../media/topics-excluded-by-name.png) 

    <span data-ttu-id="fb0de-151">(ナレッジ マネージャーは、検出後にトピック センターのトピックを除外できます)。</span><span class="sxs-lookup"><span data-stu-id="fb0de-151">(Knowledge managers can also exclude topics in the topic center after discovery.)</span></span>

    #### <a name="how-to-exclude-topics-by-name"></a><span data-ttu-id="fb0de-152">トピックを名前で除外する方法</span><span class="sxs-lookup"><span data-stu-id="fb0de-152">How to exclude topics by name</span></span>    

    <span data-ttu-id="fb0de-153">トピックを除外する必要がある場合は、[名前でトピックを除外する] を選択した後、.csv テンプレートをダウンロードし、検出結果から除外するトピックの一覧で更新します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-153">If you need to exclude topics, after selecting **Exclude topics by name**, download the .csv template and update it with the list of topics that you want to exclude from your discovery results.</span></span>

    ![CSV テンプレートのトピックを除外する](../media/exclude-topics-csv.png) 

    <span data-ttu-id="fb0de-155">CSV テンプレートで、除外するトピックに関する次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-155">In the CSV template, enter the following information about the topics you want to exclude:</span></span>

    - <span data-ttu-id="fb0de-156">**Name**: 除外するトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-156">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="fb0de-157">これを行うには次に示す 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fb0de-157">There are two ways to do this:</span></span>
        - <span data-ttu-id="fb0de-158">完全一致: 正確な名前または頭字語 (Contoso や ATL *など)\*\*を含めできます*。</span><span class="sxs-lookup"><span data-stu-id="fb0de-158">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
        - <span data-ttu-id="fb0de-159">部分一致: 特定の単語が含まれていますすべてのトピックを除外できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-159">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="fb0de-160">たとえば、*円弧は、* アーク円、プラズマアーク溶接、トレーニングアークなど、アークという単語を含むすべてのトピック *を除外します*。テキストが単語の一部として含まれているトピック (Architecture など) は除外されない点に *注意してください*。</span><span class="sxs-lookup"><span data-stu-id="fb0de-160">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
    - <span data-ttu-id="fb0de-161">**略語 (省略可能)**: 頭字語を除外する場合は、頭字語の略語を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-161">**Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.</span></span>
    - <span data-ttu-id="fb0de-162">**MatchType-Exact/Partial**: 入力した名前が完全一致型か部分一致型 *かを入力します*。</span><span class="sxs-lookup"><span data-stu-id="fb0de-162">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>

    <span data-ttu-id="fb0de-163">ファイルを完了して保存したら、[参照] を.csv検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-163">After you've completed and saved your .csv file, select **Browse** to locate and select it.</span></span>
    
    <span data-ttu-id="fb0de-164">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-164">Select **Next**.</span></span>

6. <span data-ttu-id="fb0de-165">このページ **Whoトピックを表示し、** どこでトピックを表示できるのかページで、トピックの表示を構成します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-165">On the **Who can see topics and where can they see them** page, you will configure topic visibility.</span></span> <span data-ttu-id="fb0de-166">[トピック **Who** 表示] の設定で、強調表示されているトピック、トピック カード、検索のトピック回答、トピック ページなど、トピックの詳細にアクセスできるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-166">In the **Who can see topics** setting, you choose who will have access to topic details, such as highlighted topics, topic cards, topic answers in search, and topic pages.</span></span> <span data-ttu-id="fb0de-167">次のものが選択できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-167">You can select:</span></span>
    - <span data-ttu-id="fb0de-168">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fb0de-168">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fb0de-169">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fb0de-169">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="fb0de-170">**だれも**</span><span class="sxs-lookup"><span data-stu-id="fb0de-170">**No one**</span></span>

    ![Whoトピックを表示する](../media/ksetup2.png)  

    > [!Note] 
    > <span data-ttu-id="fb0de-172">この設定では組織内の任意のユーザーを選択することができますが、トピック エクスペリエンス ライセンスが割り当てられているユーザーだけがトピックを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-172">While this setting allows you to select any user in your organization, only users who have Topic Experiences licenses assigned to them will be able to view topics.</span></span>

7. <span data-ttu-id="fb0de-173">[トピック **管理のアクセス許可] ページ** で、トピックを作成、編集、または管理できるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-173">In the **Permissions for topic management** page, you choose who will be able to create, edit, or manage topics.</span></span> <span data-ttu-id="fb0de-174">[トピックを **Who編集できる]** セクションで、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-174">In the **Who can create and edit topics** section, you can select:</span></span>
    - <span data-ttu-id="fb0de-175">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fb0de-175">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fb0de-176">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fb0de-176">**Only selected people or security groups**</span></span>
    - <span data-ttu-id="fb0de-177">**だれも**</span><span class="sxs-lookup"><span data-stu-id="fb0de-177">**No one**</span></span>

    ![トピック管理のアクセス許可(トピックを作成および編集できるユーザー)](../media/ksetup3.png) 

8. <span data-ttu-id="fb0de-179">[トピックWho **管理する] セクションで**、次の項目を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-179">In the **Who can manage topics** section, you can select:</span></span>
    - <span data-ttu-id="fb0de-180">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="fb0de-180">**Everyone in my organization**</span></span>
    - <span data-ttu-id="fb0de-181">**選択したユーザーまたはセキュリティ グループのみ**</span><span class="sxs-lookup"><span data-stu-id="fb0de-181">**Only selected people or security groups**</span></span>

    ![トピック管理のアクセス許可](../media/km-setup-create-edit-topics.png) 

    <span data-ttu-id="fb0de-183">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-183">Select **Next**.</span></span>

9. <span data-ttu-id="fb0de-184">[トピック **センターの作成** ] ページで、トピック ページを表示し、トピックを管理できるトピック センター サイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-184">On the **Create topic center** page, you can create your topic center site in which topic pages can be viewed and topics can be managed.</span></span> <span data-ttu-id="fb0de-185">[サイト **名] ボックス** に、トピック センターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-185">In the **Site name** box, type a name for your topic center.</span></span> <span data-ttu-id="fb0de-186">URL を変更する場合は、鉛筆アイコンをクリックできます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-186">You can click the pencil icon if you want to change the URL.</span></span> <span data-ttu-id="fb0de-187">必要に応じて、[説明] ボックスに短い説明 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-187">Optionally, type a short description in the **Description** box.</span></span> 

   > [!Important]
   > <span data-ttu-id="fb0de-188">後でサイト名を変更できますが、ウィザードの完了後は URL を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-188">You can change the site name later, but you can't change the URL after you complete the wizard.</span></span>

   <span data-ttu-id="fb0de-189">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-189">Select **Next**.</span></span>

   ![ナレッジ センターの作成](../media/ksetup4.png)  

10. <span data-ttu-id="fb0de-191">[ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-191">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="fb0de-192">選択内容に問題がない場合は、[**ライセンス認証**]を行います。</span><span class="sxs-lookup"><span data-stu-id="fb0de-192">If you are satisfied with your selections, select **Activate**.</span></span>

11. <span data-ttu-id="fb0de-193">[ **ビバ トピック] が** アクティブ化されたページが表示され、選択したサイトのトピックの分析が開始され、トピック センター サイトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-193">The **Viva Topics activated** page will display, confirming that the system will now start analyzing your selected sites for topics and creating the topic center site.</span></span> <span data-ttu-id="fb0de-194">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb0de-194">Select **Done**.</span></span>

12. <span data-ttu-id="fb0de-195">ユーザーからナレッジ ページにConnect **返** されます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-195">You'll be returned to your **Connect people to knowledge** page.</span></span> <span data-ttu-id="fb0de-196">このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="fb0de-196">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

    ![設定適用](../media/ksetup7.png)    

## <a name="manage-topic-experiences"></a><span data-ttu-id="fb0de-198">トピック エクスペリエンスの管理</span><span class="sxs-lookup"><span data-stu-id="fb0de-198">Manage topic experiences</span></span>

<span data-ttu-id="fb0de-199">トピックの設定が完了したら、セットアップ時に選択した設定を [トピック] で変更[Microsoft 365 管理センター。](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)</span><span class="sxs-lookup"><span data-stu-id="fb0de-199">Once you have set up Topics, you can change the settings that you chose during setup in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement).</span></span> <span data-ttu-id="fb0de-200">次の参考資料を参照してください:</span><span class="sxs-lookup"><span data-stu-id="fb0de-200">See the following references:</span></span>

- [<span data-ttu-id="fb0de-201">Microsoft Viva Topics でトピックの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="fb0de-201">Manage topic discovery in Microsoft Viva Topics</span></span>](topic-experiences-discovery.md)
- [<span data-ttu-id="fb0de-202">Microsoft Viva Topics でのトピックの表示を管理する</span><span class="sxs-lookup"><span data-stu-id="fb0de-202">Manage topic visibility in Microsoft Viva Topics</span></span>](topic-experiences-knowledge-rules.md)
- [<span data-ttu-id="fb0de-203">Microsoft Viva Topics でトピックのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="fb0de-203">Manage topic permissions in Microsoft Viva Topics</span></span>](topic-experiences-user-permissions.md)
- [<span data-ttu-id="fb0de-204">Microsoft Viva Topics でトピック センターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="fb0de-204">Change the name of the topic center in Microsoft Viva Topics</span></span>](topic-experiences-administration.md)

## <a name="see-also"></a><span data-ttu-id="fb0de-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb0de-205">See also</span></span>

[<span data-ttu-id="fb0de-206">トピック エクスペリエンスの概要</span><span class="sxs-lookup"><span data-stu-id="fb0de-206">Topic Experiences Overview</span></span>](topic-experiences-overview.md)
