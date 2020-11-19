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
ms.openlocfilehash: 6a8ee15f14475a1cebb169ab49bdb0f490c81345
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357353"
---
# <a name="gain-insights-through-attack-simulation-training"></a>攻撃シミュレーション トレーニングを通して洞察を得る

攻撃シミュレーショントレーニングの範囲内では、シミュレーションの結果と、従業員が出てきたトレーニングに基づいて、Microsoft が洞察を提供しています。 これらの洞察は、従業員が脅威への対応についての進行状況を把握するのに役立つだけでなく、従業員やお客様の攻撃に備えた環境をより適切に準備するための次のステップも提供します。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

現在利用できる拡張された洞察を継続的に作業しており、動作に影響を与え、推奨される処置を現在利用できます。
開始するには、 [Microsoft 365 セキュリティセンターで、攻撃シミュレーショントレーニング](https://security.microsoft.com/attacksimulator?viewid=overview)に向かいます。

## <a name="behavior-impact-on-compromise-rate"></a>侵害率に対する動作の影響

[アタックシミュレーショントレーニングの **概要** ] タブでは、 **妥協率カードに対する動作の影響** を確認できます。 このカードは、予想される **妥協率** と対比して実行したシミュレーションで従業員がどのように処理されたかを示しています。 これらの洞察を使用して、同じ従業員グループに対して複数のシミュレーションを実行することによって、従業員の脅威の準備状況を追跡できます。

グラフには次のものが表示されます。

- [予測される **侵害率**] 攻撃シミュレーショントレーニングを使用して、テナント全体で同じ種類のペイロードを使用したシミュレーションの平均妥協率を表します。
- [**実際の侵害率**] は、シミュレーションを使用した従業員のパーセンテージを表します。

さらに、 `<number> less susceptible to phishing` 攻撃によって侵害された実際の従業員数と予想される妥協率の違いを反映しています。 この数人の従業員は今後同様の攻撃によって侵害される可能性が低くなりますが、 `<percent%> better than predicted rate` 予想される妥協率と比較して従業員全体がどのように影響を受けたかを示します。

> [!div class="mx-imgBorder"]
> ![攻撃に影響を与える動作のシミュレーショントレーニングの概要](../../media/attack-sim-preview-behavior-impact-card.png)

詳細なレポートを表示するには、シミュレーション手法や対象ユーザー総数など、シミュレーション自体からの追加コンテキストに関する情報を提供する [ **シミュレーションとトレーニングの有効性の表示] レポート** をクリックします。

## <a name="recommended-actions"></a>推奨処理

[シミュレーション [ **Simulations** ] タブ](https://security.microsoft.com/attacksimulator?viewid=simulations)で、シミュレーションのいずれかを選択すると、シミュレーションの詳細が表示されます。 ここでは、[ **推奨** されるアクション] セクションについて説明します。

「推奨されるアクション」セクションでは、 [Microsoft セキュリティスコア](../mtp/microsoft-secure-score.md)で利用できる推奨事項について説明します。 これらの推奨事項は、シミュレーションで使用されるペイロードに基づいており、従業員や環境を保護するのに役立ちます。 各改善アクションをクリックすると、その詳細が表示されます。

> [!div class="mx-imgBorder"]
> ![アタックシミュレーショントレーニングの推奨事項のセクション](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>関連リンク

**アタックシミュレータ**[フィッシング攻撃シミュレーションを作成](attack-simulation-training.md)し、[ユーザーをトレーニングするためのペイロードを作成](attack-simulation-training-payloads.md)する
