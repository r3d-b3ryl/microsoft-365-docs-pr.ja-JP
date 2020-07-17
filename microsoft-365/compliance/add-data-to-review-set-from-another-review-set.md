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
ms.openlocfilehash: 433e59629ec40dbdf66b8daf6437ce84e41a3a33
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818604"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="4f712-103">別のレビューセットからのレビューセットへのデータの追加</span><span class="sxs-lookup"><span data-stu-id="4f712-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="4f712-104">場合によっては、1つの校閲セットからドキュメントを選択して、別のレビューセットで個別に操作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f712-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="4f712-105">これは、校閲セットのコンテンツをカリングし、データのサブセットに対して分析を実行する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="4f712-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="4f712-106">この記事のワークフローに従って、ある校閲セットから別のレビューセットにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="4f712-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="4f712-107">レビューセットを作成する</span><span class="sxs-lookup"><span data-stu-id="4f712-107">Create a review set</span></span>

<span data-ttu-id="4f712-108">開始する前に、データを追加するためのレビューセットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f712-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="4f712-109">ケースの [**レビューセット**] タブに新しいレビューセットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f712-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="4f712-110">詳細については、「[レビューセットを作成する](managing-review-sets.md#create-a-review-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f712-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="4f712-111">手順 1: 別のレビューセットに追加するコンテンツを識別する</span><span class="sxs-lookup"><span data-stu-id="4f712-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="4f712-112">ソースレビューセット内の特定のドキュメントを選択するか、またはレビューセットクエリによって返されるすべてのアイテムを選択することによって、1つのレビューセットから別のレビューセットにコンテンツを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f712-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="4f712-113">選択したアイテムを追加している場合は、アイテムを選択し、[**アクション**] を選択してから、[**別のレビューセットに追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f712-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![別の校閲セットに追加する](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="4f712-115">手順 2: 別のレビューセットに追加するためのオプションを指定する</span><span class="sxs-lookup"><span data-stu-id="4f712-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="4f712-116">[**別のレビューセットオプションポップアップに追加**] ページで、アイテムを追加するレビューセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f712-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="4f712-117">**すべての検索結果**または**選択したアイテム**を追加するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f712-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="4f712-118">**その他の情報**には、アイテムのすべてのメタデータを含めるオプションと、ドキュメントが新しいレビューセットに追加されたときにソースレビューセットからタグを含める (**ラベル**チェックボックスをオンにする) 必要があるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f712-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![別の校閲セットに追加する](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="4f712-120">[ **Ok]** をクリックすると、別のレビューセットにコンテンツを追加するための新しいジョブ (**別のレビューセットへのデータの追加**) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f712-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="4f712-121">[**ジョブ**] タブに移動して、このジョブの進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="4f712-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="4f712-122">詳細については、「 [Manage jobs](managing-jobs-ediscovery20.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f712-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
