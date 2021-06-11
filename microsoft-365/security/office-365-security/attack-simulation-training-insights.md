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
description: 管理者は、Microsoft 365 Defender ポータルでの攻撃シミュレーション トレーニングが従業員にどのように影響するかを学習し、シミュレーションとトレーニングの結果から分析情報を得る方法について説明します。
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878378"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="009d3-103">攻撃シミュレーション トレーニングを通して洞察を得る</span><span class="sxs-lookup"><span data-stu-id="009d3-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="009d3-104">**Microsoft** Defender for [Office 365プラン 2 に適用されます](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="009d3-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="009d3-105">攻撃シミュレーション トレーニングでは、従業員が行ったシミュレーションとトレーニングの結果に基づいて分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="009d3-105">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="009d3-106">これらの分析情報は、従業員の脅威の準備状況に関する情報を提供し続けるのに役立ちます。また、従業員と環境を攻撃に備える次の手順を推奨します。</span><span class="sxs-lookup"><span data-stu-id="009d3-106">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="009d3-107">お客様が利用できる分析情報の拡大に継続的に取り組み続けます。</span><span class="sxs-lookup"><span data-stu-id="009d3-107">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="009d3-108">動作への影響と推奨されるアクションは現在利用できます。</span><span class="sxs-lookup"><span data-stu-id="009d3-108">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="009d3-109">まず、Defender ポータルの攻撃シミュレーション トレーニングにMicrosoft 365[します](https://security.microsoft.com/attacksimulator?viewid=overview)。</span><span class="sxs-lookup"><span data-stu-id="009d3-109">To start, head over to [Attack simulation training in the Microsoft 365 Defender portal](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="009d3-110">侵害率に対する動作の影響</span><span class="sxs-lookup"><span data-stu-id="009d3-110">Behavior impact on compromise rate</span></span>

<span data-ttu-id="009d3-111">攻撃シミュレーション **トレーニングの** [概要] タブで、侵害率カードに対する動作 **の影響を確認** できます。</span><span class="sxs-lookup"><span data-stu-id="009d3-111">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="009d3-112">このカードは、予想される妥協率とは対照的に、従業員が実行したシミュレーションに対する従業員の対処 **方法を示しています**。</span><span class="sxs-lookup"><span data-stu-id="009d3-112">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="009d3-113">これらの分析情報を使用して、同じ従業員グループに対して複数のシミュレーションを実行することで、従業員の脅威の準備状況の進捗状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="009d3-113">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="009d3-114">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009d3-114">In the graph you can see:</span></span>

- <span data-ttu-id="009d3-115">**攻撃シミュレーション トレーニングを** 使用する他のテナント間で同じ種類のペイロードを使用するシミュレーションの平均妥協率を反映Microsoft 365予測された妥協率。</span><span class="sxs-lookup"><span data-stu-id="009d3-115">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="009d3-116">**実際の妥協率** は、シミュレーションで低下した従業員の割合を反映します。</span><span class="sxs-lookup"><span data-stu-id="009d3-116">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="009d3-117">さらに、攻撃によって侵害された従業員の実際の数と予想される妥協率の `<number> less susceptible to phishing` 違いを反映しています。</span><span class="sxs-lookup"><span data-stu-id="009d3-117">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="009d3-118">この数の従業員は、将来同様の攻撃によって侵害される可能性は低く、従業員が予想される妥協率とは対照的に全体的にどのように行ったか `<percent%> better than predicted rate` 示しています。</span><span class="sxs-lookup"><span data-stu-id="009d3-118">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="009d3-119">![攻撃シミュレーション トレーニングの概要に対する動作の影響カード](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="009d3-119">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="009d3-120">より詳細なレポートを表示するには、[シミュレーションとトレーニングの有効性レポートの **表示] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="009d3-120">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="009d3-121">このレポートは、シミュレーション自体からの追加のコンテキスト (シミュレーション手法や対象ユーザーの総数など) と同じ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="009d3-121">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="009d3-122">推奨処理</span><span class="sxs-lookup"><span data-stu-id="009d3-122">Recommended actions</span></span>

<span data-ttu-id="009d3-123">[シミュレーション [**] タブ** で](https://security.microsoft.com/attacksimulator?viewid=simulations)シミュレーションを選択すると、シミュレーションの詳細が表示されます。[推奨されるアクション] **セクションが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="009d3-123">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="009d3-124">推奨されるアクション セクションでは、Microsoft Secure Score で使用可能な推奨事項 [の詳細を示します](../defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="009d3-124">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="009d3-125">これらの推奨事項は、シミュレーションで使用されるペイロードに基づいており、従業員と環境の保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="009d3-125">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="009d3-126">各改善アクションをクリックすると、その詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="009d3-126">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="009d3-127">![攻撃シミュレーション トレーニングの推奨事項のアクション セクション](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="009d3-127">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="009d3-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="009d3-128">Related Links</span></span>

[<span data-ttu-id="009d3-129">攻撃シミュレーション トレーニングの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="009d3-129">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="009d3-130">フィッシング攻撃シミュレーションの作成</span><span class="sxs-lookup"><span data-stu-id="009d3-130">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="009d3-131">ユーザーをトレーニングするペイロードを作成する</span><span class="sxs-lookup"><span data-stu-id="009d3-131">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
