---
title: Microsoft セキュア スコアの履歴を追跡し、目標を達成する
description: Microsoft セキュア スコアに影響を与えたアクティビティに関する洞察を得る。 傾向を発見し、目標を設定します。
keywords: Microsoft セキュア スコア, セキュア スコア, Office 365 セキュア スコア, Microsoft セキュリティ スコア, Microsoft 365 セキュリティ センター, 改善アクション
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
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
ms.openlocfilehash: c9af6a3ae6f461acfd2968897223446641d5cf09
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925674"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft セキュア スコアの履歴を追跡し、目標を達成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[Microsoft セキュア スコアは](microsoft-secure-score.md) 、組織のセキュリティ体制を測定する指標で、数値が大きいほど、より多くの改善アクションが実行されたことを示します。 https://security.microsoft.com/securescore[これは、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>スコアに影響を与えたアクティビティに関する洞察を得る

組織のスコアのグラフを [履歴] タブに **表示します。**

グラフの下には、選択した時間範囲で実行されたアクションとその属性 (結果のポイントやカテゴリなど) の一覧が表示されます。 日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

アクティビティに関連付けられている改善アクションを選択すると、完全な改善アクションのフライアウトが表示されます。

特定の改善アクションのすべての履歴を表示するには、フライアウトで履歴リンクを選択します。

![改善アクション履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>傾向を見付け、目標を設定する

[指標 **と** &] タブには、傾向の可視性を向上し、目標を設定するために、いくつかのグラフとグラフがあります。 視覚エフェクトのページ全体の日付範囲を設定できます。 視覚エフェクトには以下が含まれます。

* **セキュア スコア ゾーン** - 組織の目標と、良好、良好、および悪いスコア範囲の定義に基づいてカスタマイズされます。
* **回帰傾向** : 構成、ユーザー、またはデバイスの変更によって回帰したポイントのタイムラインです。  
* **比較傾向** - 組織のセキュア スコアと時間の流れとの比較。 このビューには、シート数が類似している組織のスコア平均を表す行と、設定できるカスタム比較ビューを含めできます。
* **リスク受け入れ傾向** - 「リスク受け入れ」としてマークされた改善アクションのタイムライン。
* **スコアの** 変更 - 取得したポイント数、ポイントの回帰数、指定した日付範囲内のスコアの変更。

### <a name="compare-your-score-to-organizations-like-yours"></a>スコアを自分のような組織と比較する

スコアと類似した組織との比較については、2 つの場所で確認できます。 どちらのグラフでも、[比較の管理] を選択 **して組織の** 情報を表示および編集できます。 業界、組織の規模、ライセンス、地域に基づいてカスタム比較を作成することもできます。

#### <a name="comparison-bar-chart"></a>比較棒グラフ

比較棒グラフは [概要] **タブ** です。グラフにカーソルを合わせると、スコアとスコアの機会が表示されます。 比較データは匿名化され、他のテナントが混在しているのが正確にわかりません。

![類似した組織のスコアの棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

- **お客様のような組織**: 次の条件で条件を満たす他のテナントの平均スコア (比較対象のテナントが少なくとも 5 つ以上ある場合)。
    1. 同じ業界
    2. 同じ組織サイズ
    3. すべての地域
    4. 使用されている Microsoft 製品が 80% 類似している
    5. テナントから 20% の範囲内の機会 (現在のライセンスで達成できる最大スコア)

- **カスタム比較**: 次の条件に基づいて[比較の管理] を選択して設定する必要があります。
    1. 選択された業界
    2. 選択した組織のサイズ
    3. 選択した地域
    4. 選択したライセンス
    5. 使用されている Microsoft 製品が 80% 類似している
    6. テナントから 20% の範囲内の機会 (現在のライセンスで達成できる最大スコア)

カスタム選択を行ったが、結果が比較できる他のテナントが 5 つ未満の場合は、「データが限られているので利用できません」と表示されます。

#### <a name="comparison-trend"></a>比較傾向

[指標 **と&]** タブで、組織のセキュア スコアと時間の流中での他のユーザーとの比較を確認します。

![同じような組織の時間のスコアの線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ/プライバシー/コンプライアンス コミュニティに投稿して [&知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) らせてください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft セキュア スコアの概要](microsoft-secure-score.md)
- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
