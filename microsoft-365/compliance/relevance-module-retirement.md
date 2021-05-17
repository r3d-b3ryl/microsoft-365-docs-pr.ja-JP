---
title: 関連モジュールのAdvanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 2021 年 3 月 10 日Advanced eDiscoveryの関連性モジュールは廃止されます。 この記事では、関連性が廃止される前の操作について説明します。 具体的には、バッチ計算を実行して未完成のモデルを終了し、モデルからメタデータを保持できます。
ms.openlocfilehash: 22a7fc37a62dc665d4d798525d5e1e55250d0cb1
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122536"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="3b9f9-105">[関連] モジュールを使用Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3b9f9-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="3b9f9-106">2021 年 3 月 10 日に、関連モジュールは 2021 年 3 月 10 日に廃止Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="3b9f9-107">この削除は、組織が関連性モジュールにアクセスできなくなった  >  ([Advanced eDiscovery ケースでレビュー セットの関連性を管理する] にアクセスするか、既存の関連性モデルにアクセスできなくなるという意味です。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="3b9f9-108">廃止される現在の関連性モジュールは、Q2 CY 2021 の新しい予測コーディング ソリューションに置き換えられる予定です。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="3b9f9-109">この新機能により、組織は、より簡単で直感的なワークフローで独自の予測コーディング モデルを構築できます。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="3b9f9-110">この今後の退職に備え、関連性モジュールを使用する組織は、既存のすべてのモデルに対してバッチ計算を実行して、モデルの出力を退職日より前にエクスポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="3b9f9-111">モデルのすべての関連性スコアは、対応するレビュー セットに完全に保存され、ドキュメントをエクスポートするときにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="3b9f9-112">関連性スコアは、読み込みファイル内のメタデータとして保持されます。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="3b9f9-113">また、関連性スコアに基づいてレビュー セット内のコンテンツをフィルター処理し、関連性モデルによって生成されたメタデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="3b9f9-114">完全な未完成モデル</span><span class="sxs-lookup"><span data-stu-id="3b9f9-114">Complete unfinished models</span></span>

<span data-ttu-id="3b9f9-115">未完成の関連性モデルについては、レビュー セット内のドキュメントにモデルを適用できるよう、評価、トレーニング、およびバッチ計算を完了してください。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="3b9f9-116">バッチ計算を完了すると、関連性モジュールの終了日後に情報が保持されます。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="3b9f9-117">未完成のモデルを完了する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="3b9f9-118">モデルが安定してバッチ計算の準備が整うまで、モデルをトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="3b9f9-119">「 [タグ付けと関連性のトレーニング」を参照してください](tagging-and-relevance-training-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="3b9f9-120">次のスクリーンショットは、バッチ計算の準備ができているモジュールを示しています。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="3b9f9-121">評価とトレーニングが完了し、次にバッチ計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![バッチ計算の準備ができているモデルのスクリーンショット](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="3b9f9-123">バッチ計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-123">Run the Batch calculation.</span></span> <span data-ttu-id="3b9f9-124">「 [バッチ計算の実行」を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation)。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="3b9f9-125">バッチ計算が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="3b9f9-126">「 [バッチ計算の結果」を参照してください](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results)。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="3b9f9-127">未完成の関連性モデルの完成に関するヘルプについては、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3b9f9-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
