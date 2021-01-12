---
title: 攻撃シミュレーション トレーニングを通して洞察を得る
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Microsoft 365 セキュリティ センターの攻撃シミュレーション トレーニングが従業員に与える影響を把握し、シミュレーションとトレーニングの結果から分析情報を得る方法を学習できます。
ms.openlocfilehash: 54855a4ce8e64f4d58b9ff2697395ed684be2773
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794558"
---
# <a name="gain-insights-through-attack-simulation-training"></a>攻撃シミュレーション トレーニングを通して洞察を得る

攻撃シミュレーション トレーニングの中で、Microsoft は従業員が行ったシミュレーションとトレーニングの結果に基づく分析情報を提供します。 これらの分析情報は、従業員の脅威の準備状況に関する情報を把握するのに役立ちます。また、従業員と環境を攻撃に対してより良く準備するための次の手順をお勧めします。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

We are continuously working on expanding the insights that are available to you. 現在、動作への影響と推奨されるアクションを利用できます。 まず、Microsoft 365 セキュリティ センターの攻撃 [シミュレーション トレーニングに向かいます](https://security.microsoft.com/attacksimulator?viewid=overview)。

## <a name="behavior-impact-on-compromise-rate"></a>侵害率に対する行動の影響

攻撃シミュレーション **トレーニング** の [概要] タブには、侵害率カードに **対する動作の影響が表示** されます。 このカードは、予想される侵害率とは対照的に、従業員が実行したシミュレーションに対する対処 **方法を示しています**。 これらの分析情報を使用して、同じ従業員グループに対して複数のシミュレーションを実行することで、従業員の脅威の準備状況の進行状況を追跡できます。

グラフには次の情報が表示されます。

- **攻撃シミュレーション トレーニングを** 使用する他の Microsoft 365 テナントと同じ種類のペイロードを使用するシミュレーションの平均侵害率を反映する予測妥協率。
- **実際の侵害率** は、シミュレーションに落ちた従業員の割合を反映しています。

さらに、攻撃によって侵害された実際の従業員数と予測される侵害率の違い `<number> less susceptible to phishing` を反映しています。 この数の従業員は、今後の同様の攻撃によって侵害される可能性は低く、予想される侵害率とは対照的に、従業員がどのように全体的に行ったか `<percent%> better than predicted rate` を示しています。

> [!div class="mx-imgBorder"]
> ![攻撃シミュレーション トレーニングに対する行動影響カードの概要](../../media/attack-sim-preview-behavior-impact-card.png)

より詳細なレポートを表示するには、[シミュレーションとトレーニングの評価レポートの **表示] をクリックします**。 このレポートは、シミュレーション自体からの追加コンテキストを含む同じ情報を提供します (シミュレーション手法や対象ユーザーの総数など)。

## <a name="recommended-actions"></a>推奨処理

[ [**シミュレーション] タブ** で](https://security.microsoft.com/attacksimulator?viewid=simulations)シミュレーションを選択すると、シミュレーションの詳細が表示されます。ここで、[推奨されるアクション] **セクションが表示** されます。

推奨されるアクション セクションでは、Microsoft セキュア スコアで使用可能な推奨事項 [について詳しい説明を示します](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。 これらの推奨事項はシミュレーションで使用されるペイロードに基づいており、従業員と環境を保護するのに役立ちます。 各改善アクションをクリックすると、その詳細が表示されます。

> [!div class="mx-imgBorder"]
> ![攻撃シミュレーション トレーニングに関する推奨事項アクション セクション](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>関連リンク

**攻撃シミュレータ**[フィッシング攻撃シミュレーションを作成し](attack-simulation-training.md)、[ユーザーをトレーニングするペイロードを作成する](attack-simulation-training-payloads.md)
