---
title: 攻撃シミュレーション トレーニングを通して洞察を得る
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365 セキュリティセンターの攻撃シミュレーショントレーニングが従業員にどのように影響し、シミュレーションおよびトレーニングの結果から得られるかについて説明します。
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615182"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="eb2d9-103">攻撃シミュレーション トレーニングを通して洞察を得る</span><span class="sxs-lookup"><span data-stu-id="eb2d9-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="eb2d9-104">攻撃シミュレーショントレーニングの範囲内では、シミュレーションの結果と、従業員が出てきたトレーニングに基づいて、Microsoft が洞察を提供しています。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="eb2d9-105">これらの洞察は、従業員が脅威への対応についての進行状況を把握するのに役立つだけでなく、従業員やお客様の攻撃に備えた環境をより適切に準備するための次のステップも提供します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="eb2d9-106">現在利用できる拡張された洞察を継続的に作業しており、動作に影響を与え、推奨される処置を現在利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="eb2d9-107">開始するには、 [Microsoft 365 セキュリティセンターで、攻撃シミュレーショントレーニング](https://security.microsoft.com/attacksimulator?viewid=overview)に向かいます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="eb2d9-108">侵害率に対する動作の影響</span><span class="sxs-lookup"><span data-stu-id="eb2d9-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="eb2d9-109">[アタックシミュレーショントレーニングの **概要** ] タブでは、 **妥協率カードに対する動作の影響** を確認できます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="eb2d9-110">このカードは、予想される **妥協率** と対比して実行したシミュレーションで従業員がどのように処理されたかを示しています。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="eb2d9-111">これらの洞察を使用して、同じ従業員グループに対して複数のシミュレーションを実行することによって、従業員の脅威の準備状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="eb2d9-112">グラフには次のものが表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-112">In the graph you can see:</span></span>

- <span data-ttu-id="eb2d9-113">[予測される **侵害率**] 攻撃シミュレーショントレーニングを使用して、テナント全体で同じ種類のペイロードを使用したシミュレーションの平均妥協率を表します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="eb2d9-114">[**実際の侵害率**] は、シミュレーションを使用した従業員のパーセンテージを表します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="eb2d9-115">さらに、 `<number> less susceptible to phishing` 攻撃によって侵害された実際の従業員数と予想される妥協率の違いを反映しています。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="eb2d9-116">この数人の従業員は今後同様の攻撃によって侵害される可能性が低くなりますが、 `<percent%> better than predicted rate` 予想される妥協率と比較して従業員全体がどのように影響を受けたかを示します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eb2d9-117">![攻撃に影響を与える動作のシミュレーショントレーニングの概要](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="eb2d9-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="eb2d9-118">詳細なレポートを表示するには、シミュレーション手法や対象ユーザー総数など、シミュレーション自体からの追加コンテキストに関する情報を提供する [ **シミュレーションとトレーニングの有効性の表示] レポート** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="eb2d9-119">推奨処理</span><span class="sxs-lookup"><span data-stu-id="eb2d9-119">Recommended actions</span></span>

<span data-ttu-id="eb2d9-120">[シミュレーション[  ] タブ](https://security.microsoft.com/attacksimulator?viewid=simulations)で、シミュレーションのいずれかを選択すると、シミュレーションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="eb2d9-121">ここでは、[ **推奨** されるアクション] セクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="eb2d9-122">「推奨されるアクション」セクションでは、 [Microsoft セキュリティスコア](../mtp/microsoft-secure-score.md)で利用できる推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="eb2d9-123">これらの推奨事項は、シミュレーションで使用されるペイロードに基づいており、従業員や環境を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="eb2d9-124">各改善アクションをクリックすると、その詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb2d9-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eb2d9-125">![アタックシミュレーショントレーニングの推奨事項のセクション](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="eb2d9-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="eb2d9-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="eb2d9-126">Related Links</span></span>

<span data-ttu-id="eb2d9-127">**アタックシミュレータ**[フィッシング攻撃シミュレーションを作成](attack-simulation-training.md)し、[ユーザーをトレーニングするためのペイロードを作成](attack-simulation-training-payloads.md)する</span><span class="sxs-lookup"><span data-stu-id="eb2d9-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
