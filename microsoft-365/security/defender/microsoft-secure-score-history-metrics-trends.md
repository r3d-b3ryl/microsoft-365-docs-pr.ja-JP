---
title: Microsoft Secure Score 履歴を追跡し、目標を達成する
description: Microsoft Secure Score に影響を与えたアクティビティに関する分析情報を取得します。 傾向を見つけて目標を設定します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender portal, 改善アクション
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
ms.openlocfilehash: 03a7a070d574ec18a12c3e70d5cef20d2161490b
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663756"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft Secure Score 履歴を追跡し、目標を達成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft Secure Score](microsoft-secure-score.md) は、組織のセキュリティ体制の測定値であり、より多くの改善アクションが実行されたことを示す数値が多くなります。 https://security.microsoft.com/securescore [Microsoft 365 Defender ポータル](microsoft-365-defender.md#the-microsoft-365-defender-portal)にあります。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>スコアに影響を与えたアクティビティに関する分析情報を取得する

[ **履歴** ] タブで、組織のスコアのグラフを時間の経過と共に表示します。

グラフの下には、選択した時間範囲内で実行されたすべてのアクションとその属性 (結果のポイントやカテゴリなど) の一覧が表示されます。 日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。

:::image type="content" source="../../media/secure-score/secure-score-history-activity.png" alt-text="Microsoft 365 Defender ポータルのアクティビティ履歴を説明するページの例" lightbox="../../media/secure-score/secure-score-history-activity.png":::

アクティビティに関連付けられている改善アクションを選択すると、完全な改善アクションポップアップが表示されます。

その特定の改善アクションのすべての履歴を表示するには、ポップアップで履歴リンクを選択します。

:::image type="content" source="../../media/secure-score/secure-score-history-flyout.png" alt-text="Microsoft 365 Defender ポータルの改善アクションに関する [履歴] ウィンドウ" lightbox="../../media/secure-score/secure-score-history-flyout.png":::

## <a name="discover-trends-and-set-goals"></a>傾向を見つけて目標を設定する

[ **メトリック&傾向** ] タブには、傾向の可視性を高め、目標を設定するためのグラフとグラフがいくつかあります。 視覚化のページ全体の日付範囲を設定できます。 視覚化には、次のものが含まれます。

* **セキュリティスコア ゾーン** - 組織の目標と、良いスコア範囲、問題のあるスコア範囲、および不適切なスコア範囲の定義に基づいてカスタマイズされます。
* **回帰傾向** - 構成、ユーザー、またはデバイスの変更が原因で回帰したポイントのタイムライン。  
* **比較傾向** - 組織のセキュリティスコアが時間の経過と共に他のユーザーと比較する方法。 このビューには、同様のシート数を持つ組織のスコア平均を表す線と、設定できるカスタム比較ビューを含めることができます。
* **リスク受け入れ傾向** - "リスクが受け入れられた" とマークされた改善アクションのタイムライン。
* **スコアの変更** - 達成されたポイントの数、回帰されたポイント、および指定した日付範囲内のスコアの変更。

### <a name="compare-your-score-to-organizations-like-yours"></a>スコアを自分のような組織と比較する

スコアが自分と似ている組織とどのように比較されるかを確認するには、2 つの場所があります。

#### <a name="comparison-bar-chart"></a>比較横棒グラフ

比較横棒グラフは、[ **概要** ] タブで使用できます。グラフにマウス ポインターを合わせると、スコアとスコアの機会が表示されます。 

:::image type="content" source="../../media/secure-score/secure-score-comparison-bar.png" alt-text="Microsoft 365 Defender ポータルでの類似組織のスコアの棒グラフの例" lightbox="../../media/secure-score/secure-score-comparison-bar.png":::

比較データは匿名化されるため、他のどのテナントが混在しているか正確にはわかりません。

![類似した組織のスコアの棒グラフ。](../../media/secure-score/secure-score-comparison-screenshot.png)

#### <a name="comparison-trend"></a>比較傾向

[ **メトリック&傾向** ] タブで、組織のセキュリティスコアが時間の経過と共に他のユーザーと比較する方法を確認します。

:::image type="content" source="../../media/secure-score/secure-score-comparison-trend.png" alt-text="Microsoft 365 Defender ポータルでの類似組織のスコアの時系列の折れ線グラフの例" lightbox="../../media/secure-score/secure-score-comparison-trend.png":::

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、 [セキュリティ、プライバシー、コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿&お知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft Secure Score の概要](microsoft-secure-score.md)
- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
