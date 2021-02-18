---
title: 攻撃シミュレーション トレーニングを通して洞察を得る
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft 365 セキュリティ センターの攻撃シミュレーション トレーニングが従業員に与える影響を把握し、シミュレーションとトレーニングの結果から分析情報を得る方法を学習できます。
ms.technology: mdo
ms.openlocfilehash: 43319089f604d32bf295392dd223cf65af8bd4be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288659"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="6fb08-103">攻撃シミュレーション トレーニングを通して洞察を得る</span><span class="sxs-lookup"><span data-stu-id="6fb08-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="6fb08-104">攻撃シミュレーション トレーニングの中で、Microsoft は従業員が行ったシミュレーションとトレーニングの結果に基づく分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6fb08-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="6fb08-105">これらの分析情報は、従業員の脅威の準備状況に関する情報を把握するのに役立ちます。また、従業員と環境を攻撃に対してより良く準備するための次の手順をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fb08-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="6fb08-106">We are continuously working on expanding the insights that are available to you.</span><span class="sxs-lookup"><span data-stu-id="6fb08-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="6fb08-107">現在、動作への影響と推奨されるアクションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="6fb08-108">まず、Microsoft 365 セキュリティ センターの攻撃 [シミュレーション トレーニングに向かいます](https://security.microsoft.com/attacksimulator?viewid=overview)。</span><span class="sxs-lookup"><span data-stu-id="6fb08-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="6fb08-109">侵害率に対する行動の影響</span><span class="sxs-lookup"><span data-stu-id="6fb08-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="6fb08-110">攻撃シミュレーション **トレーニング** の [概要] タブには、侵害率カードに **対する動作の影響が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="6fb08-111">このカードは、予想される侵害率とは対照的に、従業員が実行したシミュレーションに対する対処 **方法を示しています**。</span><span class="sxs-lookup"><span data-stu-id="6fb08-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="6fb08-112">これらの分析情報を使用して、同じ従業員グループに対して複数のシミュレーションを実行することで、従業員の脅威の準備状況の進行状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="6fb08-113">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-113">In the graph you can see:</span></span>

- <span data-ttu-id="6fb08-114">**攻撃シミュレーション トレーニングを** 使用する他の Microsoft 365 テナントと同じ種類のペイロードを使用するシミュレーションの平均侵害率を反映する予測妥協率。</span><span class="sxs-lookup"><span data-stu-id="6fb08-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="6fb08-115">**実際の侵害率** は、シミュレーションに落ちた従業員の割合を反映しています。</span><span class="sxs-lookup"><span data-stu-id="6fb08-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="6fb08-116">さらに、攻撃によって侵害された実際の従業員数と予測される侵害率の違い `<number> less susceptible to phishing` を反映しています。</span><span class="sxs-lookup"><span data-stu-id="6fb08-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="6fb08-117">この数の従業員は、今後の同様の攻撃によって侵害される可能性は低く、予想される侵害率とは対照的に、従業員が全体的にどのように行ったか `<percent%> better than predicted rate` を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fb08-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6fb08-118">![攻撃シミュレーション トレーニングに対する行動影響カードの概要](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="6fb08-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="6fb08-119">より詳細なレポートを表示するには、[シミュレーションとトレーニングの評価レポートの **表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6fb08-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="6fb08-120">このレポートは、シミュレーション自体からの追加コンテキストを含む同じ情報を提供します (シミュレーション手法や対象ユーザーの総数など)。</span><span class="sxs-lookup"><span data-stu-id="6fb08-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="6fb08-121">推奨処理</span><span class="sxs-lookup"><span data-stu-id="6fb08-121">Recommended actions</span></span>

<span data-ttu-id="6fb08-122">[ [**シミュレーション] タブ** で](https://security.microsoft.com/attacksimulator?viewid=simulations)シミュレーションを選択すると、シミュレーションの詳細が表示されます。ここで、[推奨されるアクション] **セクションが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="6fb08-123">推奨されるアクション セクションでは、Microsoft セキュア スコアで使用可能な推奨事項 [について詳しい説明を示します](../mtp/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="6fb08-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="6fb08-124">これらの推奨事項はシミュレーションで使用されるペイロードに基づいており、従業員と環境を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="6fb08-125">各改善アクションをクリックすると、その詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fb08-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6fb08-126">![攻撃シミュレーション トレーニングに関する推奨事項アクション セクション](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="6fb08-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="6fb08-127">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6fb08-127">Related Links</span></span>

[<span data-ttu-id="6fb08-128">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="6fb08-128">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="6fb08-129">フィッシング攻撃シミュレーションを作成する</span><span class="sxs-lookup"><span data-stu-id="6fb08-129">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="6fb08-130">ユーザーのトレーニング用のペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="6fb08-130">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
