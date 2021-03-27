---
title: Advanced eDiscovery (プレビュー) の予測コーディング モジュール
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Advanced eDiscovery の新しい予測コーディング モジュールでは、機械学習を使用して、ケースまたは調査に関連するドキュメントを予測するレビュー セット内のドキュメントを分析します。
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382975"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a><span data-ttu-id="83b79-103">Advanced eDiscovery (プレビュー) の予測コーディング モジュール</span><span class="sxs-lookup"><span data-stu-id="83b79-103">Predictive coding module for Advanced eDiscovery (preview)</span></span>

<span data-ttu-id="83b79-104">Advanced eDiscovery の新しい予測コーディング モジュールを使用すると、最も関連性の高いドキュメントから始まるドキュメントのレビューに優先順位を付けるモデルを作成および構築できます。</span><span class="sxs-lookup"><span data-stu-id="83b79-104">Using the new predictive coding module in Advanced eDiscovery, you can create and build a model to prioritize review of documents starting with the most relevant documents.</span></span> <span data-ttu-id="83b79-105">開始するには、モデルを作成し、最大 50 のドキュメントにラベルを付け、モデル予測スコアでドキュメントをフィルター処理して、関連する関連しないドキュメントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="83b79-105">To get started, you can create a model, label as few as 50 documents, and then filter documents by model prediction scores to review relevant non-relevant documents.</span></span>

<span data-ttu-id="83b79-106">ワークフローの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="83b79-106">Here’s a quick overview of the workflow:</span></span>

1. <span data-ttu-id="83b79-107">レビュー セットで予測コーディング モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="83b79-107">Open the predictive coding module in a review set.</span></span>

   ![レビューの [分析] ドロップダウン リストをクリックして、[予測コーディング] モジュールに移動します。](..\media\PredictiveCoding1.png)

2. <span data-ttu-id="83b79-109">[予測 **コーディング モデル] ページで** 、[新しいモデル] **をクリックして** 、新しい予測コーディング モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="83b79-109">On the **Predictive coding models** page, click **New model** to create a new predictive coding model.</span></span>

   ![新しいモデルを作成する](..\media\PredictiveCoding2.png)

3. <span data-ttu-id="83b79-111">少なくとも 50 件のドキュメントに[関連] または [ **関連しない]** **のラベルを付けします**。</span><span class="sxs-lookup"><span data-stu-id="83b79-111">Label at least 50 documents as **Relevant** or **Not relevant**.</span></span> <span data-ttu-id="83b79-112">このラベル付けは、システムのトレーニングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="83b79-112">This labeling is used to train the system.</span></span>

   ![システムのトレーニングに関連する、または関連性の高い文書にラベルを付け](..\media\PredictiveCoding3.png)

4. <span data-ttu-id="83b79-114">モデルの **予測スコア フィルター** をレビュー セットに適用します。</span><span class="sxs-lookup"><span data-stu-id="83b79-114">Apply the **Prediction score** filter for your model to the review set.</span></span> <span data-ttu-id="83b79-115">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83b79-115">To do this:</span></span>

   1. <span data-ttu-id="83b79-116">レビュー セットで、[フィルター] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="83b79-116">In the review set, click **Filters**.</span></span>
   2. <span data-ttu-id="83b79-117">[フィルター **] フライ** アウト ページで、[**分析/ML] セクションを** 展開し、適用するモデルの [予測スコア] チェック ボックスをオンにします。 </span><span class="sxs-lookup"><span data-stu-id="83b79-117">In the **Filters** flyout page, expand the **Analytics/ML** section and then select **Prediction score** checkbox for the model you want to apply.</span></span>
   3. <span data-ttu-id="83b79-118">[予測スコア **] フィルター** で、予測スコアを指定します。</span><span class="sxs-lookup"><span data-stu-id="83b79-118">In the **Prediction score** filter, specify a prediction score.</span></span> <span data-ttu-id="83b79-119">フィルターは、予測スコアに一致するレビュー セット内のドキュメントを表示します。</span><span class="sxs-lookup"><span data-stu-id="83b79-119">The filter will display the documents in the review set that match the prediction score.</span></span>

      ![予測スコアを指定してドキュメントをフィルター処理する](..\media\PredictiveCoding4.png)

5. <span data-ttu-id="83b79-121">モデルのパフォーマンス、状態、安定性を監視します。</span><span class="sxs-lookup"><span data-stu-id="83b79-121">Monitor the performance, status, and stability of your model.</span></span>

   ![モデルのパフォーマンス、状態、安定性を監視する](..\media\PredictiveCoding5.png)
