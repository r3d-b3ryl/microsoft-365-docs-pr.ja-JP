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
ms.openlocfilehash: 83e7a3c9c097968c4d773e6e2092bb3c50154cc3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285283"
---
# <a name="tag-documents-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="da7b6-103">レビュー セット内のドキュメントにタグを付Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="da7b6-103">Tag documents in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="da7b6-104">電子情報開示プロセスでさまざまなワークフローを完了するには、レビュー セットでコンテンツを整理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="da7b6-104">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="da7b6-105">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-105">This includes:</span></span>

- <span data-ttu-id="da7b6-106">不要なコンテンツをカリングする</span><span class="sxs-lookup"><span data-stu-id="da7b6-106">Culling unnecessary content</span></span>

- <span data-ttu-id="da7b6-107">関連するコンテンツの識別</span><span class="sxs-lookup"><span data-stu-id="da7b6-107">Identifying relevant content</span></span>
 
- <span data-ttu-id="da7b6-108">専門家または弁護士が確認する必要のあるコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="da7b6-108">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="da7b6-109">専門家、弁護士、または他のユーザーがレビュー セット内のコンテンツを確認すると、コンテンツに関連する意見をタグを使用してキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-109">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="da7b6-110">たとえば、不要なコンテンツを作成する目的がある場合、ユーザーは"応答しない" などのタグでドキュメントにタグを付けできます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-110">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as "non-responsive".</span></span> <span data-ttu-id="da7b6-111">コンテンツがレビューおよびタグ付けされた後、レビュー セット検索を作成して、"応答しない" としてタグ付けされたコンテンツを除外できます。これにより、このコンテンツは電子情報開示ワークフローの次の手順から除外されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-111">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as "non-responsive", which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="da7b6-112">タグ パネルは、タグが意図したレビュー ワークフローをサポートできるよう、すべてのケースに合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-112">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="da7b6-113">タグの種類</span><span class="sxs-lookup"><span data-stu-id="da7b6-113">Tag types</span></span>

<span data-ttu-id="da7b6-114">Advanced eDiscoveryには、次の 2 種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="da7b6-114">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="da7b6-115">**単一選択タグ** - グループ内で 1 つのタグを選択するユーザーを制限します。</span><span class="sxs-lookup"><span data-stu-id="da7b6-115">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="da7b6-116">これは、ユーザーが "レスポンシブ" や "応答しない" などの競合するタグを選択しない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-116">This can be useful to ensure users don't select conflicting tags such as "responsive" and "non-responsive".</span></span> <span data-ttu-id="da7b6-117">これらはラジオ ボタンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-117">These will appear as radio buttons.</span></span>

- <span data-ttu-id="da7b6-118">**複数選択タグ** - ユーザーがグループ内で複数のタグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-118">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="da7b6-119">これらはチェック ボックスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-119">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="da7b6-120">タグ構造</span><span class="sxs-lookup"><span data-stu-id="da7b6-120">Tag structure</span></span>

<span data-ttu-id="da7b6-121">タグの種類に加えて、タグ パネルでのタグの整理方法の構造を使用して、タグ付けドキュメントをより直感的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-121">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="da7b6-122">タグはセクション別にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-122">Tags are grouped by sections.</span></span> <span data-ttu-id="da7b6-123">レビュー セットの検索では、タグとタグセクションで検索する機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="da7b6-123">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="da7b6-124">つまり、レビュー セット検索を作成して、セクション内の任意のタグでタグ付けされたドキュメントを取得できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-124">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![タグ パネルのタグ セクション](../media/Tagtypes.png)

<span data-ttu-id="da7b6-126">タグはセクション内に入れ子にすることで、さらに整理できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-126">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="da7b6-127">たとえば、特権コンテンツを識別してタグ付けする目的の場合、入れ子を使用して、ユーザーがドキュメントに "Privileged" としてタグを付け、適切な入れ子になったタグをチェックして特権の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-127">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as "Privileged" and select the type of privilege by checking the appropriate nested tag.</span></span>

![タグ セクション内の入れ子になったタグ](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="da7b6-129">タグの適用</span><span class="sxs-lookup"><span data-stu-id="da7b6-129">Applying tags</span></span>

<span data-ttu-id="da7b6-130">コンテンツにタグを適用するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="da7b6-130">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="da7b6-131">1 つのドキュメントのタグ付け</span><span class="sxs-lookup"><span data-stu-id="da7b6-131">Tagging a single document</span></span>

<span data-ttu-id="da7b6-132">レビュー セットでドキュメントを表示する場合は、[タグ付け] パネルをクリックすると、レビューで使用できるタグ **を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="da7b6-132">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![[タグ] パネルをクリックしてタグ パネルを表示する](../media/Singledoctag.png)

<span data-ttu-id="da7b6-134">これで、ビューアーに表示されるドキュメントにタグを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-134">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="da7b6-135">一括タグ付け</span><span class="sxs-lookup"><span data-stu-id="da7b6-135">Bulk tagging</span></span>

<span data-ttu-id="da7b6-136">一括タグ付けは、結果グリッドで複数のファイルを選択し、[タグ付け]パネルのタグを使用して、単一のドキュメントにタグを付けるのと同様に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-136">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="da7b6-137">タグを 2 回選択すると、一括タグ解除を実行できます。最初のクリックでタグが適用され、2 つ目の選択によって、選択したファイルのタグが確実にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-137">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![自動的に生成された携帯電話の説明のスクリーンショット](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="da7b6-139">一括タグ付けの場合、タグ付けパネルには、パネル内の各タグにタグ付けされたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-139">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="da7b6-140">他のレビュー パネルでのタグ付け</span><span class="sxs-lookup"><span data-stu-id="da7b6-140">Tagging in other review panels</span></span>

<span data-ttu-id="da7b6-141">ドキュメントを確認する場合は、他のレビュー パネルを使用して、結果グリッド内のドキュメントの他の特性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-141">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="da7b6-142">これには、他の関連ドキュメント、電子メール スレッド、重複に近い、ハッシュ重複の確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-142">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="da7b6-143">たとえば、関連するドキュメントを確認する場合 ([ドキュメント ファミリレビュー] パネルを使用して)、関連するドキュメントに一括タグを付け、レビュー時間を大幅に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-143">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="da7b6-144">たとえば、電子メール メッセージに複数の添付ファイルが含まれていますが、ファミリ全体が一貫してタグ付けされている必要がある場合です。</span><span class="sxs-lookup"><span data-stu-id="da7b6-144">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="da7b6-145">たとえば、[ドキュメント ファミリ] レビュー パネルを使用する場合は、[タグ付け] パネルを **表示する方法を次に** 示します。</span><span class="sxs-lookup"><span data-stu-id="da7b6-145">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="da7b6-146">選択したドキュメントのレビュー パネルを開いた後 (たとえば、[ドキュメント ファミリレビュー] パネルに関連コンテンツの一覧を表示する場合など)、[ドキュメント ファミリレビュー] パネルの下の [ドキュメントにタグを付け] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da7b6-146">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="da7b6-147">タグ付けパネルがポップアップ ウィンドウとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="da7b6-147">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="da7b6-148">1 つ以上のタグを選択して、選択したドキュメントを適用します。</span><span class="sxs-lookup"><span data-stu-id="da7b6-148">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="da7b6-149">すべてのドキュメントにタグを付けするには、[ドキュメント ファミリ] パネルですべてのドキュメントを選択し、[ドキュメントにタグを付け] をクリックし、ドキュメントファミリ全体に適用するタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="da7b6-149">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![自動的に生成されたソーシャル メディア投稿の説明のスクリーンショット](../media/Relatedtag.png)
