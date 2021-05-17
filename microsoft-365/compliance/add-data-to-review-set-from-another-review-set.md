---
title: 1 つのレビュー セットから別のレビュー セットにデータを追加する
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
description: 1 つのレビュー セットからドキュメントを選択し、別のケースの別のセットで個別に作業するAdvanced eDiscoveryします。
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
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="a4bb2-103">別のレビュー セットからレビュー セットにデータを追加</span><span class="sxs-lookup"><span data-stu-id="a4bb2-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="a4bb2-104">場合によっては、あるレビュー セットからドキュメントを選択し、別のレビュー セットで個別に作業する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="a4bb2-105">これは、レビューセットのコンテンツを選別して、データのサブセットに対して 分析を実行する場合に、特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="a4bb2-106">この記事のワークフローに従って、あるレビュー セットから別のレビュー セットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="a4bb2-107">レビュー セットを作成する</span><span class="sxs-lookup"><span data-stu-id="a4bb2-107">Create a review set</span></span>

<span data-ttu-id="a4bb2-108">開始する前に、データを追加するレビュー セットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="a4bb2-109">ケースの [レビュー セット] タブに新しい **レビュー** セットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="a4bb2-110">詳細については、「レビュー セットを [作成する」を参照してください](managing-review-sets.md#create-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="a4bb2-111">手順 1: 別のレビュー セットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="a4bb2-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="a4bb2-112">ソース レビュー セットの特定のドキュメントを選択するか、レビュー セット クエリで返されたすべてのアイテムを選択し、レビュー セットから別のレビュー セットにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="a4bb2-113">選択したアイテムを追加する場合は、アイテムを選択し、[アクション] を選択し、[別のレビュー セットに追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![[アクション] メニューの別のレビュー セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="a4bb2-115">手順 2: 別のレビュー セットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="a4bb2-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="a4bb2-116">[別の **レビュー セット オプションに追加] フライ** アウト ページで、アイテムを追加するレビュー セットを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="a4bb2-117">[すべての検索結果] または [ **選択されたアイテム]** **を追加するかどうかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="a4bb2-118">追加情報には、アイテムのすべてのメタデータを含めるオプションと、ドキュメントが新しいレビュー セットに追加される際に、ソース レビュー セットからタグを含める ([ラベル] チェック ボックスをオンにして) 含めるオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![別のレビュー セットにデータを追加するためのオプション](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="a4bb2-120">[OK] **をクリックすると**、新しいジョブ ([別のレビュー セットにデータを追加 **する]** という名前) が作成され、コンテンツが別のレビュー セットに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="a4bb2-121">[ジョブ] タブに **移動** して、このジョブの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="a4bb2-122">詳細については、「ジョブの管理 [」を参照してください](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="a4bb2-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
