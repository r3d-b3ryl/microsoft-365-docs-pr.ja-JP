---
title: レビュー セット内のドキュメントをタグ付けする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 1c0eaed5d5971a55e4e9851bac3133bcd961eb36
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557697"
---
# <a name="tag-documents-in-a-review-set"></a><span data-ttu-id="c06e5-102">レビュー セット内のドキュメントをタグ付けする</span><span class="sxs-lookup"><span data-stu-id="c06e5-102">Tag documents in a review set</span></span>

<span data-ttu-id="c06e5-103">レビューセットのコンテンツを整理することは、電子情報開示プロセスでさまざまなワークフローを完了するために重要です。</span><span class="sxs-lookup"><span data-stu-id="c06e5-103">Organizing content in a review set is important to complete various workflows in the eDiscovery process.</span></span> <span data-ttu-id="c06e5-104">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-104">This includes:</span></span>

- <span data-ttu-id="c06e5-105">不要なコンテンツのカリング</span><span class="sxs-lookup"><span data-stu-id="c06e5-105">Culling unnecessary content</span></span>

- <span data-ttu-id="c06e5-106">関連するコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="c06e5-106">Identifying relevant content</span></span>
 
- <span data-ttu-id="c06e5-107">専門家または弁護士が確認する必要があるコンテンツを特定する</span><span class="sxs-lookup"><span data-stu-id="c06e5-107">Identifying content that must be reviewed by an expert or an attorney</span></span>

<span data-ttu-id="c06e5-108">専門家、弁護士、または他のユーザーがレビューセットのコンテンツをレビューする場合、コンテンツに関連する意見をタグを使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-108">When experts, attorneys, or other users review content in a review set, their opinions related to the content can be captured by using tags.</span></span> <span data-ttu-id="c06e5-109">たとえば、不要なコンテンツをカリングすることが目的の場合、ユーザーは "応答不可" などのタグを持つドキュメントにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-109">For example, if the intent is to cull unnecessary content, a user can tag documents with a tag such as “non-responsive”.</span></span> <span data-ttu-id="c06e5-110">コンテンツをレビューしてタグ付けした後は、レビューセット検索を作成して、"応答不可" とタグ付けされたコンテンツを除外することができます。これにより、電子情報開示ワークフローの次のステップからそのコンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-110">After content has been reviewed and tagged, a review set search can be created to exclude any content tagged as “non-responsive”, which eliminates this content from the next steps in the eDiscovery workflow.</span></span> <span data-ttu-id="c06e5-111">タグパネルは、すべてのケースについてカスタマイズできます。そのため、タグが目的のレビューワークフローをサポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c06e5-111">The tag panel can be customized for every case so that the tags can support the intended review workflow.</span></span>

## <a name="tag-types"></a><span data-ttu-id="c06e5-112">タグの種類</span><span class="sxs-lookup"><span data-stu-id="c06e5-112">Tag types</span></span>

<span data-ttu-id="c06e5-113">上級電子情報開示には、次の2種類のタグがあります。</span><span class="sxs-lookup"><span data-stu-id="c06e5-113">Advanced eDiscovery provides two types of tags:</span></span>

- <span data-ttu-id="c06e5-114">**単一選択タグ**-ユーザーがグループ内の1つのタグを選択できるように制限します。</span><span class="sxs-lookup"><span data-stu-id="c06e5-114">**Single choice tags** - Restricts users to select a single tag within a group.</span></span> <span data-ttu-id="c06e5-115">これは、ユーザーが "応答可能" や "応答不可" などの競合するタグを選択しないようにするのに便利です。</span><span class="sxs-lookup"><span data-stu-id="c06e5-115">This can be useful to ensure users don’t select conflicting tags such as “responsive” and “non-responsive”.</span></span> <span data-ttu-id="c06e5-116">これらはラジオボタンとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-116">These will appear as radio buttons.</span></span>

- <span data-ttu-id="c06e5-117">**複数選択タグ**-ユーザーがグループ内で複数のタグを選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c06e5-117">**Multiple choice tags** - Allow users to select multiple tags within a group.</span></span> <span data-ttu-id="c06e5-118">これらはチェックボックスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-118">These will appear as checkboxes.</span></span>

## <a name="tag-structure"></a><span data-ttu-id="c06e5-119">タグ構造</span><span class="sxs-lookup"><span data-stu-id="c06e5-119">Tag structure</span></span>

<span data-ttu-id="c06e5-120">タグの種類に加えて、タグパネルでタグを構成する方法の構造を使用して、タグ付きドキュメントをより直観的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-120">In addition to the tag types, the structure of how tags are organized in the tag panel can be used to make tagging documents more intuitive.</span></span> <span data-ttu-id="c06e5-121">タグはセクションごとにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-121">Tags are grouped by sections.</span></span> <span data-ttu-id="c06e5-122">レビューセット検索は、タグとタグで検索する機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c06e5-122">Review set search supports the ability to search by tag and by tag section.</span></span> <span data-ttu-id="c06e5-123">つまり、レビューセット検索を作成して、セクション内のタグでタグ付けされたドキュメントを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-123">This means you can create a review set search to retrieve documents tagged with any tag in a section.</span></span>

![タグパネル内のタグセクション](../media/Tagtypes.png)

<span data-ttu-id="c06e5-125">タグは、セクション内にネストすることで、さらに整理することができます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-125">Tags can be further organized by nesting them within a section.</span></span> <span data-ttu-id="c06e5-126">たとえば、権限のあるコンテンツを識別し、タグ付けすることを目的としている場合は、ネストを使用して、ユーザーがドキュメントを "特権付き" としてタグ設定し、適切なネストされたタグをチェックすることで特権の種類を選択できることを明確にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-126">For example, if the intent is to identify and tag privileged content, nesting can be used to make it clear that a user can tag a document as “Privileged” and select the type of privilege by checking the appropriate nested tag.</span></span>

![タグセクション内の入れ子になったタグ](../media/Nestingtags.png)

## <a name="applying-tags"></a><span data-ttu-id="c06e5-128">タグの適用</span><span class="sxs-lookup"><span data-stu-id="c06e5-128">Applying tags</span></span>

<span data-ttu-id="c06e5-129">コンテンツにタグを適用するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="c06e5-129">There are several ways to apply a tag to content.</span></span>

### <a name="tagging-a-single-document"></a><span data-ttu-id="c06e5-130">1つのドキュメントにタグを付けます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-130">Tagging a single document</span></span>

<span data-ttu-id="c06e5-131">校閲セットでドキュメントを表示するときに、[タグ**付けパネル]** をクリックすると、レビューで使用できるタグを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-131">When viewing a document in a review set, you can display the tags that a review can use by clicking **Tagging panel**.</span></span>

![[タグパネル] をクリックして、タグパネルを表示します。](../media/Singledoctag.png)

<span data-ttu-id="c06e5-133">これにより、ビューアーに表示されるドキュメントにタグを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-133">This will enable you to apply tags to the document displayed in the viewer.</span></span>

### <a name="bulk-tagging"></a><span data-ttu-id="c06e5-134">一括タグ付け</span><span class="sxs-lookup"><span data-stu-id="c06e5-134">Bulk tagging</span></span>

<span data-ttu-id="c06e5-135">一括タグ付けを行うには、結果グリッドで複数のファイルを選択し、1つのドキュメントにタグ付けするのと同じように、タグ**付けパネル**のタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="c06e5-135">Bulk tagging can be done by selecting multiple files in the results grid and then using the tags in the **Tagging panel** similar to tagging single documents.</span></span> <span data-ttu-id="c06e5-136">タグを2回選択することで一括でのタグの解除を行うことができます。最初のクリックでタグが適用され、2番目の選択によって、選択されているすべてのファイルのタグがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-136">Bulk un-tagging can be done by selecting tags twice; the first click will apply the tag, and the second selection will ensure that tag is cleared for all selected files.</span></span>

![携帯電話の説明のスクリーンショットが自動的に生成される](../media/Bulktag.png)

> [!NOTE]
> <span data-ttu-id="c06e5-138">一括タグ付けの場合、タグ付けパネルには、パネル内の各タグに対してタグ付けされたファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-138">When bulk tagging, the tagging panel will display a count of files that are tagged for each tag in the panel.</span></span>

### <a name="tagging-in-other-review-panels"></a><span data-ttu-id="c06e5-139">他のレビューパネルでのタグ付け</span><span class="sxs-lookup"><span data-stu-id="c06e5-139">Tagging in other review panels</span></span>

<span data-ttu-id="c06e5-140">ドキュメントを確認するときは、他のレビューパネルを使用して、結果グリッド内のドキュメントの他の特性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-140">When reviewing documents, you can use the other review panels to review other characteristics of documents in the results grid.</span></span> <span data-ttu-id="c06e5-141">これには、その他の関連ドキュメント、電子メールスレッド、ほぼ重複、ハッシュの重複の確認が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-141">This includes reviewing other related documents, email threads, near duplicates, and hash duplicates.</span></span> <span data-ttu-id="c06e5-142">たとえば、[**ドキュメントファミリ**レビュー] パネルを使用して関連ドキュメントをレビューしている場合は、関連するドキュメントを一括でタグ付けすることで、レビュー時間を大幅に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-142">For example, when you're reviewing related documents (by using the **Document family** review panel), you can significantly reduce review time by bulk tagging related documents.</span></span> <span data-ttu-id="c06e5-143">たとえば、電子メールメッセージに複数の添付ファイルがあり、ファミリー全体が一貫してタグ付けされるようにする場合などです。</span><span class="sxs-lookup"><span data-stu-id="c06e5-143">For example, if an email message has several attachments and you want to ensure that the entire family is tagged consistently.</span></span>

<span data-ttu-id="c06e5-144">たとえば、**ドキュメントファミリー**レビューパネルを使用しているときに**タグ付けパネル**を表示する方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c06e5-144">For example, here's how to display the **Tagging panel** when using the **Document family** review panel:</span></span>

1. <span data-ttu-id="c06e5-145">選択したドキュメントに対してレビューパネルを開き (たとえば、関連するコンテンツのリストを**ドキュメントファミリー**レビューパネルに表示する)、ドキュメントファミリーレビューパネルの下の [**タグ付けドキュメント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c06e5-145">With the review panel open for a selected document (for example, displaying the list of related content in the **Document family** review panel, click **Tag documents** under the document family review panel.</span></span>

   <span data-ttu-id="c06e5-146">タグパネルはポップアップウィンドウとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="c06e5-146">The tagging panel is displayed as a pop-up window.</span></span>

2. <span data-ttu-id="c06e5-147">1つ以上のタグを選択して、選択したドキュメントを適用します。</span><span class="sxs-lookup"><span data-stu-id="c06e5-147">Choose one or more tags to apply the selected document.</span></span> 

3. <span data-ttu-id="c06e5-148">すべてのドキュメントにタグ付けするには、**ドキュメントファミリー**パネルで [すべてのドキュメント] を選択し、[**ドキュメントのタグ付け**] をクリックして、ドキュメントのファミリー全体に適用するタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="c06e5-148">To tag all documents, select all documents in the **Document family** panel, click **Tag documents**, and then choose the tags to apply to the entire family of documents.</span></span>

![ソーシャルメディア投稿の説明が自動的に生成されたスクリーンショット](../media/Relatedtag.png)
