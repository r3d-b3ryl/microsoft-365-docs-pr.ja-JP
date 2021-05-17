---
title: スマート タグを設定Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: スマート タグを使用すると、ケース内のコンテンツを確認するときに機械学習機能をAdvanced eDiscoveryできます。 スマート タグ グループを使用して、弁護士クライアント特権モデルなどの機械学習検出モデルの結果を表示します。
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081084"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="ca4b5-104">スマート タグを設定Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ca4b5-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="ca4b5-105">機械学習 (ML) 機能Advanced eDiscovery、レビュー セットでケース ドキュメントを確認する際に、意思決定プロセスをより効率的に行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="ca4b5-106">スマート タグは、レビュー中にドキュメントMLタグ付けする際に、意思決定が記録される場所に、重要な機能を提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="ca4b5-107">スマート タグ グループを作成すると、スマート タグ グループに関連付けられた ML モデルの結果である決定がタグ グループ内のタグと一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="ca4b5-108">これにより、特定のドキュメントML確認するときに、検索結果情報を一覧で確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="ca4b5-109">スマート タグ グループを設定する方法</span><span class="sxs-lookup"><span data-stu-id="ca4b5-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="ca4b5-110">レビュー セットで、[レビュー セットの管理] **をクリックし** 、[タグの管理] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="ca4b5-111">[タグ **グループの追加] をクリック** し、[スマート タグ **グループの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="ca4b5-112">タグ グループMLするモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="ca4b5-113">これにより、タグ グループと *N 子タグが* 作成されます。 *ここで、N* はモデルの出力可能な数です。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="ca4b5-114">たとえば、弁護士クライアント特権 [検出モデルには](attorney-privilege-detection.md) 、次の 2 つの出力があります。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="ca4b5-115">**Positive** – 弁護士クライアント特権コンテンツを含むドキュメントにタグ付けする場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="ca4b5-116">**負** – 弁護士-クライアント特権コンテンツを含むドキュメントにタグを付け設定します。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="ca4b5-117">このモデルを選択すると、レビュー セットに 2 つの子タグを持つタグ グループ (1 つの子タグが **正** で、もう 1 つは **負**) が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="ca4b5-118">この例では、各子タグは、弁護士とクライアントの特権検出モデルで使用できる出力の 1 つに対応しています。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="ca4b5-119">必要に応じて、タグ グループと子タグの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="ca4b5-120">たとえば、正のタグの名前を **[特権**] に、負のタグ **を [\*\*\*\*特権ではありません] に変更できます**。 </span><span class="sxs-lookup"><span data-stu-id="ca4b5-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="ca4b5-121">スマート タグの使い方</span><span class="sxs-lookup"><span data-stu-id="ca4b5-121">How to use smart tags</span></span>

<span data-ttu-id="ca4b5-122">ドキュメントを確認すると、モデルの結果が適切な子タグの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="ca4b5-123">たとえば、弁護士クライアント特権検出用のスマート タグ グループを持ち、潜在的に特権のあるドキュメントを確認した場合、その結論の理由が適切なタグの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="ca4b5-124">タグがドキュメントに自動的に適用されるのではない点に注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="ca4b5-125">レビューアーは、ドキュメントにタグを付け方を決定します。</span><span class="sxs-lookup"><span data-stu-id="ca4b5-125">The reviewer makes the decision about how to tag the document.</span></span>
