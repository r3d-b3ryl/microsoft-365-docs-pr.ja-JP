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
ms.openlocfilehash: 464a926b99cceeb652756ad6d1456c5e17d2a925
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988740"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a><span data-ttu-id="bd4c7-103">トピックセンターのトピックを操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="bd4c7-103">Work with topics in the topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="bd4c7-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="bd4c7-105">[Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)</span><span class="sxs-lookup"><span data-stu-id="bd4c7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>


<span data-ttu-id="bd4c7-106">トピックセンターでは、指定した SharePoint ソースの場所でマイニングされ、検出されたトピックを確認または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-106">In the topic center, a knowledge manager can review topics that have been mined and discovered in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="bd4c7-107">ナレッジマネージャーは、トピック探索で見つからなかった場合に新しいトピックページを作成して発行したり、更新する必要がある場合は既存のページを編集したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-107">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd4c7-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="bd4c7-108">Requirements</span></span>

<span data-ttu-id="bd4c7-109">トピックセンターで作業するには、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-109">In order to work in the topic center, you need to have the required permissions.</span></span> <span data-ttu-id="bd4c7-110">管理者は、 [ナレッジ管理のセットアップ](set-up-topic-experiences.md)時に、ユーザーを追加したり、 [後](give-user-permissions-to-the-topic-center.md)で新しいユーザーを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-110">Your admin can add you during [knowledge management setup](set-up-topic-experiences.md), or new users can be [added afterwards](give-user-permissions-to-the-topic-center.md).</span></span>

<span data-ttu-id="bd4c7-111">トピックセンターのユーザーには、次の2つのアクセス許可のセットを与えることができます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-111">Topic center users can be given two sets of permissions:</span></span>

- <span data-ttu-id="bd4c7-112">トピックを作成および編集する: 新しいトピックを作成するか、説明、ドキュメント、関連する人物などのトピックコンテンツを更新します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-112">Create and edit topics: Create new topics or update topic content such as the description, documents and associated persons.</span></span>

- <span data-ttu-id="bd4c7-113">トピックの管理: トピック管理ダッシュボードを使用して、組織全体のトピックをレビューします。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-113">Manage topics: Use the Topic management dashboard to review topics across the organization.</span></span> <span data-ttu-id="bd4c7-114">ユーザーは、トピックの確認や拒否などの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-114">Users can perform actions such as confirm and reject topics.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="bd4c7-115">推奨されるトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="bd4c7-115">Review suggested topics</span></span>

<span data-ttu-id="bd4c7-116">トピックセンターのホームページで、指定した SharePoint ソースの場所で検出されたトピックが [ **推奨** ] タブに一覧表示されます。トピックを管理するアクセス許可を持つユーザーは、未確認のトピックを確認して確認するか、拒否するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-116">On the topic center home page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A user with permissions to manage topics can review unconfirmed topics and choose to confirm or reject them.</span></span>


<span data-ttu-id="bd4c7-117">推奨されるトピックを確認するには:</span><span class="sxs-lookup"><span data-stu-id="bd4c7-117">To review a suggested topic:</span></span>

1. <span data-ttu-id="bd4c7-118">[ **推奨** される項目] タブで、トピックを選択して [トピック] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-118">On the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="bd4c7-119">[トピック] ページで、トピックページを確認し、ページに変更を加える必要がある場合は [ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-119">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="bd4c7-120">ナレッジセンターのホームページで、選択したトピックに対して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-120">On the Knowledge Center home page, for the selected topic, you can:</span></span>

    1. <span data-ttu-id="bd4c7-121">トピックを保持することを確認するには、[確認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-121">Select the check to confirm that you want to keep the topic.</span></span>
    
    1. <span data-ttu-id="bd4c7-122">トピックを拒否する場合は、[ **x** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-122">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="bd4c7-123">確認されたトピックは **未確認** のリストから削除され、[ **確認** ] タブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-123">Confirmed topics will be removed from the **Unconfirmed** list and will now display in the **Confirmed** tab.</span></span>

    <span data-ttu-id="bd4c7-124">却下されたトピックは **未確認** のリストから削除され、[ **拒否] または [除外** ] タブに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-124">Rejected topics will be removed from the **Unconfirmed** list and will now display in the **Rejected or Excluded** tab.</span></span>

## <a name="review-confirmed-topics"></a><span data-ttu-id="bd4c7-125">確認済みトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="bd4c7-125">Review confirmed topics</span></span>

<span data-ttu-id="bd4c7-126">トピックセンターのホームページでは、指定した SharePoint ソースの場所で検出され、ナレッジマネージャーが2人以上のユーザーによって確認されたトピックと、カードフィードバックメカニズムによって crowdsourced によって確認されたトピックが、[ **確認** ] タブに表示されます。トピックを管理するアクセス許可を持つユーザーは、確認されたトピックを確認して、拒否するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-126">On the topic center home page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or crowdsourced confirmed by 2 or more people through the card feedback mechanism will be listed in the **Confirmed** tab. A user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>


<span data-ttu-id="bd4c7-127">確認済みトピックを確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-127">To review a confirmed topic:</span></span>

1. <span data-ttu-id="bd4c7-128">[ **確認** ] タブで、トピックを選択して [トピック] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-128">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="bd4c7-129">[トピック] ページで、トピックページを確認し、ページに変更を加える必要がある場合は [ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-129">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="bd4c7-130">拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-130">You can reject it too</span></span>

## <a name="review-published-topics"></a><span data-ttu-id="bd4c7-131">公開されたトピックを確認する</span><span class="sxs-lookup"><span data-stu-id="bd4c7-131">Review published topics</span></span>
<span data-ttu-id="bd4c7-132">公開されたトピックは、ページを見つけた人に対して特定の情報が常に表示されるように編集されています。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-132">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="bd4c7-133">手動で作成したトピックはここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-133">Manually created topics show here.</span></span>

   
## <a name="create-a-new-topic"></a><span data-ttu-id="bd4c7-134">新しいトピックを作成する</span><span class="sxs-lookup"><span data-stu-id="bd4c7-134">Create a new topic</span></span>

<span data-ttu-id="bd4c7-135">[トピックの作成または編集のアクセス許可を持つユーザーは、必要に応じて新しいトピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-135">A user with create or edit topic permissions can create a new topic if needed.</span></span> <span data-ttu-id="bd4c7-136">この手順を実行する必要があるのは、トピックが検出されなかった場合、または AI テクノロジがトピックとして設定するのに十分な証拠を見つけられなかった場合です。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-136">You might need to do this if the topic was not discovered through discovery or if the AI technology did not find enough evidence to establish it as a topic.</span></span>

<span data-ttu-id="bd4c7-137">新しいトピックを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-137">To create a new topic:</span></span>

1. <span data-ttu-id="bd4c7-138">[トピックセンター] ページで、[ **新規** ] を選択し、[ **トピックページ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-138">On the topic center page, select **New** , then select **Topic Page**.</span></span>

    ![新しいトピック](../media/content-understanding/k-new-topic.png)

2. <span data-ttu-id="bd4c7-140">[新しいトピック] ページで、新しいトピックテンプレートの情報を入力できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-140">On the new topic page, you can fill in the information on the new topic template:</span></span>

    1. <span data-ttu-id="bd4c7-141">[ **このトピックの名前** ] セクションに、新しいトピックの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-141">In the **Name this topic** section, type the name of the new topic.</span></span>
    
    1. <span data-ttu-id="bd4c7-142">[ **代替名** ] セクションで、トピックを参照するためにも使用される名前または頭字語を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-142">In the **Alternate names** section, type names or acronyms that are also used to refer to the topic.</span></span>
    
    1. <span data-ttu-id="bd4c7-143">[ **短い説明** ] セクションに、トピックの1つまたは2つの文の説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-143">In the **Short description** section, type a one or two sentence description of the topic.</span></span> <span data-ttu-id="bd4c7-144">このテキストは、関連付けられたトピックカードに使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-144">This text will be used for the associated topic card.</span></span>
    
    1. <span data-ttu-id="bd4c7-145">[ **人** ] セクションで、トピックの該当分野の専門家の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-145">In the **People** section, type the names of subject matter experts for the topic.</span></span>
    
    1. <span data-ttu-id="bd4c7-146">[ **ファイルとページ** ] セクションで、[ **追加** ] を選択し、次のページで、関連付けられた OneDrive ファイルまたは SharePoint Online ページを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-146">In the **Files and pages** section, select **Add** and then on the next page you can select associated OneDrive files or SharePoint Online pages.</span></span>
    
    1. <span data-ttu-id="bd4c7-147">[ **サイト** ] セクションで、[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-147">In the **Sites** section, select **Add**.</span></span> <span data-ttu-id="bd4c7-148">表示される [  **サイト** ] ウィンドウで、トピックに関連付けられているサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-148">In the  **Sites** pane that displays, select the sites that are associated to the topic.</span></span>

    ![新しいトピックページ](../media/content-understanding/k-new-topic-page.png)
    
3. <span data-ttu-id="bd4c7-150">テキスト、画像、web パーツ、リンクなど、他のコンポーネントをページに追加する必要がある場合は、ページの中央にあるキャンバスアイコンを選択して、それを見つけて追加します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-150">If you need to add other components to the page, such as text, images, web parts, links, etc., select the canvas icon in the middle of the page to locate and add them.</span></span>

    ![ページにアイテムを追加する](../media/content-understanding/static-icon.png)

4. <span data-ttu-id="bd4c7-152">完了したら、[ **発行** ] を選択して、トピックページを発行します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-152">When you are done, select **Publish** to publish the topic page.</span></span> <span data-ttu-id="bd4c7-153">公開したトピックページが [ **ページ** ] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-153">Published topic pages will display in the **Pages** tab.</span></span>

> [!Note] 
> <span data-ttu-id="bd4c7-154">新しいトピックページは、 *知識ネットワークに対応* した web パーツから構成されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-154">The new topic page is made up of web parts that are *knowledge network aware*.</span></span> <span data-ttu-id="bd4c7-155">そのため、このトピックでは、AI が詳細な情報を収集することを意味します。これらの web パーツの情報は、ユーザーにとってより便利なページになるように、提案に基づいて更新されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-155">This means that as AI gathers more information on the topic, the information in these web parts will be updated with suggestions to make the page more useful to users.</span></span>


## <a name="edit-an-existing-topic-page"></a><span data-ttu-id="bd4c7-156">既存のトピックページを編集する</span><span class="sxs-lookup"><span data-stu-id="bd4c7-156">Edit an existing topic page</span></span>

<span data-ttu-id="bd4c7-157">既存のトピックページは、[ **ページ** ] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-157">Existing topic pages can be found in the **Pages** page.</span></span> 

1. <span data-ttu-id="bd4c7-158">[トピックセンター] ページで、[ **ページ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-158">On the Topic Center page, select **Pages**.</span></span>

2. <span data-ttu-id="bd4c7-159">[ **ページ** ] ページに、トピックページの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-159">On the **Pages** page, you will see a list of topic pages.</span></span> <span data-ttu-id="bd4c7-160">検索ボックスを使用して、更新するトピックページを検索します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-160">Use the Search box to find the topic page you want to update.</span></span> <span data-ttu-id="bd4c7-161">編集するトピックページの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-161">Click on the name of the topic page that you want to edit.</span></span>

3. <span data-ttu-id="bd4c7-162">[トピック] ページで、[ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-162">On the topic page, select **Edit**.</span></span>

4. <span data-ttu-id="bd4c7-163">ページに対して必要な変更を行います。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-163">Make the changes you need to the page.</span></span> <span data-ttu-id="bd4c7-164">これには、以下のフィールドの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-164">This includes updates to the following fields:</span></span>

    1. <span data-ttu-id="bd4c7-165">代替名</span><span class="sxs-lookup"><span data-stu-id="bd4c7-165">Alternate names</span></span>
    1. <span data-ttu-id="bd4c7-166">説明</span><span class="sxs-lookup"><span data-stu-id="bd4c7-166">Description</span></span>
    1. <span data-ttu-id="bd4c7-167">People</span><span class="sxs-lookup"><span data-stu-id="bd4c7-167">People</span></span>
    1. <span data-ttu-id="bd4c7-168">ファイルおよびページ</span><span class="sxs-lookup"><span data-stu-id="bd4c7-168">Files and pages</span></span>
    1. <span data-ttu-id="bd4c7-169">サイト</span><span class="sxs-lookup"><span data-stu-id="bd4c7-169">Sites</span></span>
    1. <span data-ttu-id="bd4c7-170">カンバスアイコンを選択して、テキスト、画像、リンクなどのページに静的アイテムを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-170">You can also add static items to the page—such as text, images, or link—by selecting the canvas icon.</span></span>

5. <span data-ttu-id="bd4c7-171">[ **再発行** ] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bd4c7-171">Select **Republish** to save your changes.</span></span>

<!--## See also-->


