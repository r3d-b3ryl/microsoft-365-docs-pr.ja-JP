---
title: 'トピックセンターのトピックを操作する (プレビュー) '
description: トピックセンターのトピックを操作する方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 82a1b1990f464a892b8216caa26e0422b093bf37
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948056"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a><span data-ttu-id="12e2a-103">トピックセンターのトピックを操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="12e2a-103">Work with topics in the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="12e2a-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="12e2a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="12e2a-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12e2a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="12e2a-106">トピックセンターでは、指定した SharePoint ソースの場所でマイニングされ、検出されたトピックを確認または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-106">In the topic center, a knowledge manager can review topics that have been mined and discovered in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="12e2a-107">ナレッジマネージャーは、トピック探索で見つからなかった場合に新しいトピックページを作成して発行したり、更新する必要がある場合は既存のページを編集したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-107">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="requirements"></a><span data-ttu-id="12e2a-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="12e2a-108">Requirements</span></span>

<span data-ttu-id="12e2a-109">トピックセンターで作業するには、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="12e2a-109">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="12e2a-110">管理者は、 [ナレッジ管理のセットアップ](set-up-knowledge-network.md)時に、ユーザーを追加したり、 [後](give-user-permissions-to-the-topic-center.md)で新しいユーザーを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-110">Your admin can add you during [knowledge management setup](set-up-knowledge-network.md), or new users can be [added afterwards](give-user-permissions-to-the-topic-center.md).</span></span>

<span data-ttu-id="12e2a-111">トピックセンターのユーザーには、次の2つのアクセス許可のセットを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-111">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="12e2a-112">トピックを作成および編集する: 新しいトピックを作成するか、説明、ドキュメント、関連付けられた人物などのトピックコンテンツを更新する</span><span class="sxs-lookup"><span data-stu-id="12e2a-112">Create and edit topics: Create new topics or update topic content such as the description, documents and associated persons</span></span>
- <span data-ttu-id="12e2a-113">トピックの管理: トピック管理ダッシュボードを使用して、組織全体のトピックをレビューします。</span><span class="sxs-lookup"><span data-stu-id="12e2a-113">Manage topics: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="12e2a-114">ユーザーは、トピックの確認と拒否などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-114">Users can perform actions such as confirm and reject topics</span></span>


## <a name="review-unconfirmed-topics"></a><span data-ttu-id="12e2a-115">未確認のトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="12e2a-115">Review unconfirmed topics</span></span>

<span data-ttu-id="12e2a-116">トピックセンターのホームページで、指定した SharePoint ソースの場所で検出されたトピックが [ **未確認** ] タブに一覧表示されます。トピックを管理するアクセス許可を持つユーザーは、未確認のトピックを確認して確認するか、拒否するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-116">On the topic center home page, topics that were discovered in your specified SharePoint source locations will be listed in the **Unconfirmed** tab. A user with permissions to manage topics can review unconfirmed topics and choose to confirm or reject them.</span></span>


<span data-ttu-id="12e2a-117">未確認のトピックを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="12e2a-117">To review an unconfirmed topic:</span></span>

1. <span data-ttu-id="12e2a-118">[ **未確認** ] タブで、トピックを選択して [トピック] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-118">On the **Unconfirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="12e2a-119">[トピック] ページで、トピックページを確認し、ページに変更を加える必要がある場合は [ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-119">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>
3. <span data-ttu-id="12e2a-120">ナレッジセンターのホームページで、選択したトピックに対して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-120">On the Knowledge Center home page, for the selected topic, you can:</span></span></br>
    <span data-ttu-id="12e2a-121">a. </span><span class="sxs-lookup"><span data-stu-id="12e2a-121">a.</span></span> <span data-ttu-id="12e2a-122">トピックを保持することを確認するには、[確認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-122">Select the check to confirm that you want to keep the topic.</span></span></br>
    <span data-ttu-id="12e2a-123">b. </span><span class="sxs-lookup"><span data-stu-id="12e2a-123">b.</span></span> <span data-ttu-id="12e2a-124">トピックを拒否する場合は、[ **x** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-124">Select the **x** if you want to reject the topic.</span></span></br>

    <span data-ttu-id="12e2a-125">確認されたトピックは **未確認** のリストから削除され、[ **確認** ] タブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="12e2a-125">Confirmed topics will be removed from the **Unconfirmed** list and will now display in the **Confirmed** tab.</span></span></br>

    <span data-ttu-id="12e2a-126">却下されたトピックは **未確認** のリストから削除され、[ **拒否] または [除外** ] タブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="12e2a-126">Rejected topics will be removed from the **Unconfirmed** list and will now display in the **Rejected or Excluded** tab.</span></span></br>
    
   
## <a name="create-a-new-topic"></a><span data-ttu-id="12e2a-127">新しいトピックを作成する</span><span class="sxs-lookup"><span data-stu-id="12e2a-127">Create a new topic</span></span>

<span data-ttu-id="12e2a-128">[トピックの作成または編集のアクセス許可を持つユーザーは、必要に応じて新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-128">A user with create or edit topic permissions can create a new topic if needed.</span></span> <span data-ttu-id="12e2a-129">この手順を実行する必要があるのは、トピックが検出されなかった場合、または AI テクノロジがトピックとして設定するのに十分な証拠を見つけられなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="12e2a-129">You might need to do this if the topic was not discovered through discovery or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

<span data-ttu-id="12e2a-130">新しいトピックを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="12e2a-130">To create a new topic:</span></span>
1. <span data-ttu-id="12e2a-131">[トピックセンター] ページで、[ **新規**] を選択し、[ **トピックページ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-131">On the topic center page, select **New**, then select **Topic Page**.</span></span></br>

    ![新しいトピック](../media/content-understanding/k-new-topic.png) </br>

2. <span data-ttu-id="12e2a-133">[新しいトピック] ページで、新しいトピックテンプレートの情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-133">On the new topic page, you can fill in the information on the new topic template:</span></span></br>
    <span data-ttu-id="12e2a-134">a. </span><span class="sxs-lookup"><span data-stu-id="12e2a-134">a.</span></span> <span data-ttu-id="12e2a-135">[ **このトピックの名前** ] セクションに、新しいトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-135">In the **Name this topic** section, type the name of the new topic.</span></span></br>
    <span data-ttu-id="12e2a-136">b. </span><span class="sxs-lookup"><span data-stu-id="12e2a-136">b.</span></span> <span data-ttu-id="12e2a-137">[ **代替名** ] セクションで、トピックを参照するためにも使用される名前または頭字語を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-137">In the **Alternate names** section, type names or acronyms that are also used to refer to the topic.</span></span></br>
    <span data-ttu-id="12e2a-138">c. </span><span class="sxs-lookup"><span data-stu-id="12e2a-138">c.</span></span> <span data-ttu-id="12e2a-139">[ **短い説明** ] セクションに、トピックの1つまたは2つの文の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-139">In the **Short description** section, type a one or two sentence description of the topic.</span></span> <span data-ttu-id="12e2a-140">このテキストは、関連付けられたトピックカードに使用されます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-140">This text will be used for the associated topic card.</span></span></br>
    <span data-ttu-id="12e2a-141">d. </span><span class="sxs-lookup"><span data-stu-id="12e2a-141">d.</span></span> <span data-ttu-id="12e2a-142">[ **人** ] セクションで、トピックの該当分野の専門家の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-142">In the **People** section, type the names of subject matter experts for the topic.</span></span></br>
    <span data-ttu-id="12e2a-143">e. </span><span class="sxs-lookup"><span data-stu-id="12e2a-143">e.</span></span> <span data-ttu-id="12e2a-144">[ **ファイルとページ** ] セクションで、[ **追加** ] を選択し、次のページで、関連付けられた OneDrive ファイルまたは SharePoint Online ページを選択できます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-144">In the **Files and pages** section, select **Add** and then on the next page you can select associated OneDrive files or SharePoint Online pages.</span></span></br>
    <span data-ttu-id="12e2a-145">f.</span><span class="sxs-lookup"><span data-stu-id="12e2a-145">f.</span></span> <span data-ttu-id="12e2a-146">[ **サイト** ] セクションで、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-146">In the **Sites** section, select **Add**.</span></span> <span data-ttu-id="12e2a-147">表示される [  **サイト** ] ウィンドウで、トピックに関連付けられているサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-147">In the  **Sites** pane that displays, select the sites that are associated to the topic.</span></span></br>

    ![新しいトピックページ](../media/content-understanding/k-new-topic-page.png) </br>
3. <span data-ttu-id="12e2a-149">テキスト、画像、web パーツ、リンクなど、他のコンポーネントをページに追加する必要がある場合は、ページの中央にあるキャンバスアイコンを選択して、それを見つけて追加します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-149">If you need to add other components to the page, such as text, images, webparts, links, etc., select the canvas icon in the middle of the page to locate and add them.</span></span>
    <span data-ttu-id="12e2a-150">![ページにアイテムを追加する](../media/content-understanding/static-icon.png)</span><span class="sxs-lookup"><span data-stu-id="12e2a-150">![Add items to page](../media/content-understanding/static-icon.png)</span></span> </br> 

4. <span data-ttu-id="12e2a-151">完了したら、[ **発行** ] を選択して、トピックページを発行します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-151">When you are done, select **Publish** to publish the topic page.</span></span> <span data-ttu-id="12e2a-152">公開したトピックページが [ **ページ** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-152">Published topic pages will display in the **Pages** tab.</span></span>

> [!Note] 
> <span data-ttu-id="12e2a-153">新しいトピックページは、 *知識ネットワークに対応*した web パーツから構成されます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-153">The new topic page is made up of web parts that are *knowledge network aware*.</span></span> <span data-ttu-id="12e2a-154">そのため、このトピックでは、AI が詳細な情報を収集することを意味します。これらの web パーツの情報は、ユーザーにとってより便利なページになるように、提案に基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-154">This means that as AI gathers more information on the topic, the information in these web parts will be updated with suggestions to make the page more useful to users.</span></span>


## <a name="edit-an-existing-topic-page"></a><span data-ttu-id="12e2a-155">既存のトピックページを編集する</span><span class="sxs-lookup"><span data-stu-id="12e2a-155">Edit an existing topic page</span></span>

<span data-ttu-id="12e2a-156">既存のトピックページは、[ **ページ** ] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="12e2a-156">Existing topic pages can be found in the **Pages** page.</span></span> 

1. <span data-ttu-id="12e2a-157">[トピックセンター] ページで、[ **ページ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-157">On the Topic Center page, select **Pages**.</span></span></br>
2. <span data-ttu-id="12e2a-158">[ **ページ** ] ページに、トピックページの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-158">On the **Pages** page, you will see a list of topic pages.</span></span> <span data-ttu-id="12e2a-159">検索ボックスを使用して、更新するトピックページを検索します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-159">Use the Search box to find the topic page you want to update.</span></span> <span data-ttu-id="12e2a-160">編集するトピックページの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="12e2a-160">Click on the name of the topic page that you want to edit.</span></span></br>
3. <span data-ttu-id="12e2a-161">[トピック] ページで、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-161">On the topic page, select **Edit**.</span></span> </br>
4. <span data-ttu-id="12e2a-162">ページに対して必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="12e2a-162">Make the changes you need to the page.</span></span> <span data-ttu-id="12e2a-163">これには、以下のフィールドの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-163">This includes updates to the following fields:</span></span></br>
    <span data-ttu-id="12e2a-164">a. </span><span class="sxs-lookup"><span data-stu-id="12e2a-164">a.</span></span> <span data-ttu-id="12e2a-165">代替名</span><span class="sxs-lookup"><span data-stu-id="12e2a-165">Alternate names</span></span></br>
    <span data-ttu-id="12e2a-166">b. </span><span class="sxs-lookup"><span data-stu-id="12e2a-166">b.</span></span> <span data-ttu-id="12e2a-167">Description</span><span class="sxs-lookup"><span data-stu-id="12e2a-167">Description</span></span></br>
    <span data-ttu-id="12e2a-168">c. </span><span class="sxs-lookup"><span data-stu-id="12e2a-168">c.</span></span> <span data-ttu-id="12e2a-169">ユーザー</span><span class="sxs-lookup"><span data-stu-id="12e2a-169">People</span></span></br>
    <span data-ttu-id="12e2a-170">d. </span><span class="sxs-lookup"><span data-stu-id="12e2a-170">d.</span></span> <span data-ttu-id="12e2a-171">ファイルおよびページ</span><span class="sxs-lookup"><span data-stu-id="12e2a-171">Files and pages</span></span></br>
    <span data-ttu-id="12e2a-172">e. </span><span class="sxs-lookup"><span data-stu-id="12e2a-172">e.</span></span> <span data-ttu-id="12e2a-173">サイト</span><span class="sxs-lookup"><span data-stu-id="12e2a-173">Sites</span></span></br>
    <span data-ttu-id="12e2a-174">f.</span><span class="sxs-lookup"><span data-stu-id="12e2a-174">f.</span></span> <span data-ttu-id="12e2a-175">また、キャンバスアイコンを選択して、テキスト、画像、リンクなどの静的アイテムをページに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="12e2a-175">You can also add static items to the page - such as text, images, or link - by selecting the canvas icon.</span></span></br>

5. <span data-ttu-id="12e2a-176">[ **再発行** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="12e2a-176">Select **Republish** to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="12e2a-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="12e2a-177">See also</span></span>



  






