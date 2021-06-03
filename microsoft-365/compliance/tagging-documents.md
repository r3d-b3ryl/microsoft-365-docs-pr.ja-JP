---
title: レビュー セット内のドキュメントをタグ付けする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: レビュー セット内のドキュメントにタグを付けると、不要なコンテンツを削除し、関連するコンテンツを特定Advanced eDiscoveryできます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6d6a933f24a034aced99a8eaa70c6ee951765ca0
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736272"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="3d2c8-103">レビュー セット内のドキュメントにタグを付Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3d2c8-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="3d2c8-104">電子情報開示プロセスでさまざまなワークフローを完了するには、レビュー セットでコンテンツを整理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="3d2c8-105">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-105">This includes:</span></span>

- <span data-ttu-id="3d2c8-106">不要なコンテンツをカリングする</span><span class="sxs-lookup"><span data-stu-id="3d2c8-106">Culling unnecessary content</span></span>

- <span data-ttu-id="3d2c8-107">関連するコンテンツの識別</span><span class="sxs-lookup"><span data-stu-id="3d2c8-107">Identifying relevant content</span></span>

- <span data-ttu-id="3d2c8-108">専門家または弁護士が確認する必要のあるコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="3d2c8-108">Identifying content that must be reviewed by an expert or attorney</span></span>

<span data-ttu-id="3d2c8-109">専門家、弁護士、または他のユーザーがレビュー セット内のコンテンツを確認すると、コンテンツに関連する意見をタグを使用してキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="3d2c8-110">たとえば、不要なコンテンツを作成する目的がある場合、ユーザーは"応答しない" などのタグでドキュメントにタグを付けできます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="3d2c8-111">コンテンツがレビューおよびタグ付けされた後、レビュー セット検索を作成して、"応答しない" としてタグ付けされたコンテンツを除外できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive".</span></span> <span data-ttu-id="3d2c8-112">このプロセスでは、電子情報開示ワークフローの次の手順から応答しないコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-112">This process eliminates the non-responsive content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="3d2c8-113">レビュー セットのタグ付けパネルは、ケースごとにカスタマイズして、タグがケースの意図したレビュー ワークフローをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-113">The tagging panel in a review set can be customized for every case so that the tags support the intended review workflow for the case.</span></span>

> [!NOTE]
> <span data-ttu-id="3d2c8-114">タグの範囲は、大文字と小文字Advanced eDiscoveryです。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-114">The scope of tags is an Advanced eDiscovery case.</span></span> <span data-ttu-id="3d2c8-115">つまり、レビュー担当者がレビュー セット ドキュメントにタグを付けできるタグのセットは 1 つのみケースに設定できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-115">That means a case can only have one set of tags that reviewers can use to tag review set documents.</span></span> <span data-ttu-id="3d2c8-116">同じケースで異なるレビュー セットで使用する別のタグセットを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-116">You can't set up a different set of tags for use in different review sets in the same case.</span></span>

## <a name="tag-types"></a><span data-ttu-id="3d2c8-117">タグの種類</span><span class="sxs-lookup"><span data-stu-id="3d2c8-117">Tag types</span></span>

<span data-ttu-id="3d2c8-118">Advanced eDiscoveryには、次の 2 種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-118">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="3d2c8-119">**単一選択タグ**: グループ内で 1 つのタグを選択するレビュー担当者を制限します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-119">**Single choice tags**: Restricts reviewers to selecting a single tag within a group.</span></span> <span data-ttu-id="3d2c8-120">このような種類のタグは、レビュー担当者が "レスポンシブ" や "応答しない" などの競合するタグを選択しない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-120">These types of tags can be useful to ensure that reviewers don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="3d2c8-121">単一選択タグはラジオ ボタンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-121">Single choice tags appear as radio buttons.</span></span>

- <span data-ttu-id="3d2c8-122">**複数選択タグ**: グループ内で複数のタグを選択するレビューを許可します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-122">**Multiple choice tags**: Allow reviews to select multiple tags within a group.</span></span> <span data-ttu-id="3d2c8-123">これらの種類のタグは、チェック ボックスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-123">These types of tags appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="3d2c8-124">タグ構造</span><span class="sxs-lookup"><span data-stu-id="3d2c8-124">Tag structure</span></span>

<span data-ttu-id="3d2c8-125">タグの種類に加えて、タグ パネルでのタグの整理方法の構造を使用して、タグ付けドキュメントをより直感的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-125">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="3d2c8-126">タグはセクション別にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-126">Tags are grouped by sections.</span></span> <span data-ttu-id="3d2c8-127">レビュー セットの検索では、タグとタグセクションで検索する機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-127">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="3d2c8-128">つまり、レビュー セット検索を作成して、セクション内の任意のタグでタグ付けされたドキュメントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-128">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![タグ パネルのタグ セクション](../media/TagTypes.png)

<span data-ttu-id="3d2c8-130">セクション内にタグを入れ子にすることで、タグをさらに整理できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-130">You can further organize tags by nesting them within a section.</span></span> <span data-ttu-id="3d2c8-131">たとえば、特権コンテンツを識別してタグ付けする目的の場合、入れ子を使用して、レビューアーがドキュメントに "Privileged" としてタグ付けし、適切な入れ子になったタグをチェックして特権の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-131">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a reviewer can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![タグ セクション内の入れ子になったタグ](../media/NestingTags.png)

## <a name="create-tags"></a><span data-ttu-id="3d2c8-133">タグの作成</span><span class="sxs-lookup"><span data-stu-id="3d2c8-133">Create tags</span></span>

<span data-ttu-id="3d2c8-134">レビュー セット内のドキュメントにタグを適用する前に、タグ構造を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-134">Before applying tags to documents in the review set, you need to create a tag structure.</span></span>

1. <span data-ttu-id="3d2c8-135">レビュー セットを開き、コマンド バーに移動し、[クエリで **タグ付け] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-135">Open a review set and navigate to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3d2c8-136">タグ付けパネルで、[タグ オプションの **管理] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="3d2c8-136">In the tagging panel, select **Manage tag options**</span></span>

3. <span data-ttu-id="3d2c8-137">[タグ **の追加] セクションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-137">Select **Add tag section**.</span></span>

4. <span data-ttu-id="3d2c8-138">タグ グループのタイトルとオプションの説明を入力し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-138">Type a tag group title and an optional description, and then click **Save**.</span></span>

5. <span data-ttu-id="3d2c8-139">タグ グループのタイトルの横にある [トリプル ドット] ドロップダウン メニューを選択し、[追加] チェック ボックス **または** [追加] **オプション ボタンをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-139">Select the triple dot dropdown menu next to the tag group title and click **Add check box** or **Add option button**.</span></span>

6. <span data-ttu-id="3d2c8-140">チェック ボックスまたはオプション ボタンの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-140">Type a name and description for the checkbox or option button.</span></span>

7. <span data-ttu-id="3d2c8-141">この手順を繰り返して、新しいタグ セクション、タグ オプション、およびチェック ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-141">Repeat this process to create new tag sections, tag options, and checkboxes.</span></span>

   ![タグ構造の構成](../media/ManageTagOptions3.png)

## <a name="applying-tags"></a><span data-ttu-id="3d2c8-143">タグの適用</span><span class="sxs-lookup"><span data-stu-id="3d2c8-143">Applying tags</span></span>

<span data-ttu-id="3d2c8-144">タグ構造を設定すると、レビュー担当者はレビュー セット内のドキュメントにタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-144">With the tag structure in place, reviewers can apply tags to documents in a review set.</span></span> <span data-ttu-id="3d2c8-145">タグを適用するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-145">There are two different ways to apply tags:</span></span>

- <span data-ttu-id="3d2c8-146">タグ ファイル</span><span class="sxs-lookup"><span data-stu-id="3d2c8-146">Tag files</span></span>

- <span data-ttu-id="3d2c8-147">クエリによるタグ付け</span><span class="sxs-lookup"><span data-stu-id="3d2c8-147">Tag by query</span></span>

### <a name="tag-files"></a><span data-ttu-id="3d2c8-148">タグ ファイル</span><span class="sxs-lookup"><span data-stu-id="3d2c8-148">Tag files</span></span>

<span data-ttu-id="3d2c8-149">1 つのアイテムを選択するか、レビュー セット内の複数のアイテムを選択した場合でも、コマンドバーの [タグ ファイル] をクリックして、選択内容にタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-149">Whether you select a single item or several items in a review set, you can apply tags to their selection by clicking **Tag files** in the command bar.</span></span> <span data-ttu-id="3d2c8-150">タグパネルでタグを選択すると、選択したドキュメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-150">In the tagging panel, you can select a tag and it is automatically applied to the selected documents.</span></span>

![選択したファイルにタグを付ける](../media/TagFile2.png)

> [!NOTE]
> <span data-ttu-id="3d2c8-152">タグは、アイテムのリスト内の選択したアイテムにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-152">Tags will be applied only to selected items in the list of items.</span></span>

### <a name="tag-by-query"></a><span data-ttu-id="3d2c8-153">クエリによるタグ付け</span><span class="sxs-lookup"><span data-stu-id="3d2c8-153">Tag by query</span></span>

<span data-ttu-id="3d2c8-154">クエリによるタグ付けでは、現在レビュー セットに適用されているフィルター クエリによって表示されるアイテムにタグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-154">Tagging by query lets you apply tags to all items displayed by a filter query that's currently applied in the review set.</span></span>

1. <span data-ttu-id="3d2c8-155">レビュー セット内のすべてのアイテムの選択を解除し、コマンド バーに移動し、[クエリで **タグ付け] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-155">Unselect all items in the review set and go to the command bar and select **Tag by query**.</span></span>

2. <span data-ttu-id="3d2c8-156">タグ付けパネルで、適用するタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-156">In the tagging panel, select the tag that you want to apply.</span></span>

3. <span data-ttu-id="3d2c8-157">[タグ **の選択] ドロップダウン** の下に、タグを適用するアイテムを指定する 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-157">Under the **Tag selection** dropdown, there are three options that dictate which items to apply the tag to.</span></span>

   - <span data-ttu-id="3d2c8-158">**適用されたクエリに一致するアイテム**: フィルター クエリ条件に一致する特定のアイテムにタグを適用します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-158">**Items that match applied query**: Applies tags to specific items that match the filter query conditions.</span></span>

   - <span data-ttu-id="3d2c8-159">**関連付けられたファミリ アイテム** を含める: フィルター クエリ条件と関連付けられたファミリ アイテムに一致する特定のアイテムにタグを適用します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-159">**Include associated family items**: Applies tags to specific items that match the filter query conditions and their associated family items.</span></span> <span data-ttu-id="3d2c8-160">*ファミリ アイテムは* 、同じ FamilyId メタデータ値を共有するアイテムです。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-160">*Family items* are items that share the same FamilyId metadata value.</span></span>  

   - <span data-ttu-id="3d2c8-161">**関連付けられた会話アイテムを** 含める: フィルター クエリの条件と関連付けられた会話アイテムに一致するアイテムにタグを適用します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-161">**Include associated conversation items**: Applies tags to items that match the filter query conditions and their associated conversation items.</span></span> <span data-ttu-id="3d2c8-162">*会話アイテムは* 、同じ ConversationId メタデータ値を共有するアイテムです。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-162">*Conversation items* are items that share the same ConversationId metadata values.</span></span>

   ![タグの選択](../media/TagByQuery2.png)

4. <span data-ttu-id="3d2c8-164">[タグ **付けジョブの開始] をクリック** して、タグ付けジョブをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-164">Click **Start tagging job** to trigger the tagging job.</span></span>

## <a name="tag-filter"></a><span data-ttu-id="3d2c8-165">タグ フィルター</span><span class="sxs-lookup"><span data-stu-id="3d2c8-165">Tag filter</span></span>

<span data-ttu-id="3d2c8-166">レビュー セットのタグ フィルターを使用して、アイテムのタグ付け方法に基づいてクエリ結果からアイテムをすばやく検索または除外します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-166">Use the tag filter in review set to quickly find or exclude items from the query results based on how an item is tagged.</span></span> 

1. <span data-ttu-id="3d2c8-167">[フィルター **] を** 選択してフィルター パネルを展開します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-167">Select **Filters** to expand the filter panel.</span></span>

2. <span data-ttu-id="3d2c8-168">Item プロパティを **選択して展開します**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-168">Select and expand **Item properties**.</span></span>

3. <span data-ttu-id="3d2c8-169">下にスクロールして Tag という名前のフィルター **を見つけ**、チェック ボックスをオンにして、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-169">Scroll down to find the filter named **Tag**, select the checkbox, and then click **Done**.</span></span>

4. <span data-ttu-id="3d2c8-170">特定のタグを持つアイテムをクエリに含めるか除外するには、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-170">To include or exclude items with a specific tag from a query, do one of the following:</span></span>

   - <span data-ttu-id="3d2c8-171">**アイテムを含** める: タグの値を選択し、ドロップダウン メニューで **[任意に** 等しい] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-171">**Include items**: Select the tag value and select **Equal any of** in the dropdown menu.</span></span>

      <span data-ttu-id="3d2c8-172">または</span><span class="sxs-lookup"><span data-stu-id="3d2c8-172">Or</span></span>

   - <span data-ttu-id="3d2c8-173">**アイテムを除外** する: タグの値を選択し、ドロップダウン **メニューで [なし]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-173">**Exclude items**: Select the tag value and select **Equals none of** in dropdown menu.</span></span>

     ![タグ フィルターの除外アイテム](../media/TagFilterExclude.png)

> [!NOTE]
> <span data-ttu-id="3d2c8-175">タグ フィルターがタグ構造に対する最新の変更を表示するには、必ずページを更新してください。</span><span class="sxs-lookup"><span data-stu-id="3d2c8-175">Be sure to refresh the page to ensure that the tag filter displays the latest changes to the tag structure.</span></span>
