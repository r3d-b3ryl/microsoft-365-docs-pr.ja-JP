---
title: Microsoft Secure Score の履歴を追跡し、目標を達成する
description: Microsoft Secure Score に影響を与えたアクティビティに関する分析情報を取得します。 傾向を発見し、目標を設定します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender ポータル, 改善アクション
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d740ab4fb999697edc9ce7c8f662f6d5c6681fdf
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500499"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft Secure Score の履歴を追跡し、目標を達成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score](microsoft-secure-score.md) は、組織のセキュリティ体制の測定で、より多くの改善アクションが実行されたことを示す数値が高くなります。 このファイルは、ポータルhttps://security.microsoft.com/securescoreのMicrosoft 365 Defender[があります](microsoft-365-defender.md#the-microsoft-365-defender-portal)。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>スコアに影響を与えたアクティビティに関する分析情報を取得する

[履歴] タブで、時間の過ぎた組織のスコアのグラフ **を表示** します。

グラフの下には、選択した時間範囲で行ったすべてのアクションとその属性 (結果のポイントやカテゴリなど) の一覧が表示されます。 日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。

:::image type="content" source="../../media/secure-score/secure-score-history-activity.png" alt-text="ポータル内のアクティビティ履歴を説明するページのMicrosoft 365 Defender例" lightbox="../../media/secure-score/secure-score-history-activity.png":::

アクティビティに関連付けられた改善アクションを選択すると、完全な改善アクションのフライアウトが表示されます。

特定の改善アクションのすべての履歴を表示するには、フライアウトで履歴リンクを選択します。

:::image type="content" source="../../media/secure-score/secure-score-history-flyout.png" alt-text="ポータルの改善アクションに関する履歴ウィンドウMicrosoft 365 Defenderします。" lightbox="../../media/secure-score/secure-score-history-flyout.png":::

## <a name="discover-trends-and-set-goals"></a>傾向を発見し、目標を設定する

[指標 **の傾向&** ] タブには、傾向の可視性を高め、目標を設定するグラフとグラフがいくつかあります。 視覚エフェクトのページ全体の日付範囲を設定できます。 視覚化には、次のものが含まれます。

* **Secure Score Zone** - 組織の目標と、良好、大丈夫、および悪いスコア範囲の定義に基づいてカスタマイズされます。
* **回帰傾向** - 構成、ユーザー、またはデバイスの変更のために回帰したポイントのタイムライン。  
* **比較傾向** - 組織の Secure Score が他のユーザーの時間と比較する方法。 このビューには、同じようなシート数を持つ組織のスコア平均を表す線と、設定できるカスタム比較ビューを含めできます。
* **リスク受け入れ** 傾向 - "リスクが受け入れられる" とマークされた改善アクションのタイムライン。
* **スコアの** 変更 - 達成されたポイント数、ポイントが後退し、指定した日付範囲のスコアに対する変更。

### <a name="compare-your-score-to-organizations-like-yours"></a>スコアを自分のような組織と比較する

スコアが類似している組織とどのように比較されるのかについては、2 つの場所で確認できます。

#### <a name="comparison-bar-chart"></a>比較棒グラフ

比較棒グラフは、[概要] タブ **で使用** できます。グラフにカーソルを合わせると、スコアとスコアの機会が表示されます。 

:::image type="content" source="../../media/secure-score/secure-score-comparison-bar.png" alt-text="ポータル内の類似の組織のスコアの棒グラフMicrosoft 365 Defender例" lightbox="../../media/secure-score/secure-score-comparison-bar.png":::

比較データは匿名化され、他のテナントが混在しているかどうかは正確にはわかりません。

![類似する組織のスコアの棒グラフ。](../../media/secure-score/secure-score-comparison-screenshot.png)

#### <a name="comparison-trend"></a>比較傾向

[指標 **と&]** タブで、組織の Secure Score が他のユーザーの時間と比較する方法を確認します。

:::image type="content" source="../../media/secure-score/secure-score-comparison-trend.png" alt-text="サイト ポータルでの類似した組織のスコアのMicrosoft 365 Defender例" lightbox="../../media/secure-score/secure-score-comparison-trend.png":::

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft Secure Score の概要](microsoft-secure-score.md)
- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
