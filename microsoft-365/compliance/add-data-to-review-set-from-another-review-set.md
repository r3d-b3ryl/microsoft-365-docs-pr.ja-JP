---
title: 1つのレビューセットから別のレビューセットにデータを追加する
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
description: 1つの校閲セットからドキュメントを選択し、それらを別のセットで個別に操作する方法について説明します。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285182"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="75c18-103">別のレビュー セットからレビュー セットにデータを追加</span><span class="sxs-lookup"><span data-stu-id="75c18-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="75c18-104">場合によっては、1つの校閲セットからドキュメントを選択して、別のレビューセットで個別に操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75c18-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="75c18-105">これは、レビューセットのコンテンツを選別して、データのサブセットに対して 分析を実行する場合に、特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="75c18-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="75c18-106">この記事のワークフローに従って、ある校閲セットから別のレビューセットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="75c18-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="75c18-107">レビューセットを作成する</span><span class="sxs-lookup"><span data-stu-id="75c18-107">Create a review set</span></span>

<span data-ttu-id="75c18-108">開始する前に、データを追加するためのレビューセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75c18-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="75c18-109">ケースの [ **レビューセット** ] タブに新しいレビューセットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="75c18-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="75c18-110">詳細については、「 [レビューセットを作成する](managing-review-sets.md#create-a-review-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75c18-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="75c18-111">手順 1: 別のレビューセットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="75c18-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="75c18-112">ソース レビュー セットの特定のドキュメントを選択するか、レビュー セット クエリで返されたすべてのアイテムを選択し、レビュー セットから別のレビュー セットにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="75c18-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="75c18-113">選択したアイテムを追加している場合は、アイテムを選択し、[ **アクション**] を選択してから、[ **別のレビューセットに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="75c18-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![[アクション] メニューの別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="75c18-115">手順 2: 別のレビューセットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="75c18-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="75c18-116">[ **別のレビューセットオプションポップアップに追加** ] ページで、アイテムを追加するレビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="75c18-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="75c18-117">**すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="75c18-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="75c18-118">**その他の情報** には、アイテムのすべてのメタデータを含めるオプションと、ドキュメントが新しいレビューセットに追加されたときにソースレビューセットからタグを含める ( **ラベル** チェックボックスをオンにする) 必要があるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75c18-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![別のレビューセットにデータを追加するためのオプション](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="75c18-120">[ **Ok]** をクリックすると、別のレビューセットにコンテンツを追加するための新しいジョブ ( **別のレビューセットへのデータの追加**) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="75c18-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="75c18-121">[ **ジョブ** ] タブに移動して、このジョブの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="75c18-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="75c18-122">詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75c18-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
