---
title: Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する
description: Microsoft のセキュリティで保護されたスコアに影響を与えたアクティビティについての洞察を得ることができます。 傾向を検出し、目標を設定します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769246"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[Microsoft セキュリティスコア](microsoft-secure-score.md) は、組織のセキュリティに関する状況の測定値で、より多くの改善アクションが行われたことを示しています。 この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>スコアに影響を与える状況を把握する

[ **履歴** ] タブで、組織のスコアのグラフを時間の経過と共に表示します。

グラフの下には、選択した時間範囲内で実行されるすべてのアクションとその属性 (結果として得られる点やカテゴリなど) の一覧が表示されます。 日付範囲をカスタマイズし、カテゴリ別にフィルター処理できます。

![アクティビティ履歴](../../media/secure-score/secure-score-history-activity.png)

アクティビティに関連付けられている改善アクションを選択すると、[完全な改善] アクションのポップアップが表示されます。

その特定の改善アクションの履歴をすべて表示するには、フライアウトの [履歴] リンクを選択します。

![向上アクションの履歴](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>傾向を検出し、目標を設定する

[ **指標 & の傾向** ] タブには、傾向を把握し、目標を設定するのに役立つグラフやグラフがいくつかあります。 視覚エフェクトのページ全体の日付範囲を設定できます。 視覚エフェクトは次のとおりです。

* **セキュリティで保護されたスコアゾーン** -組織の目標と、適切、適正、および悪いスコアの範囲の定義に基づいてカスタマイズされます。
* **回帰傾向** -構成、ユーザー、またはデバイスの変更によって regressed を持つポイントのタイムライン。  
* **比較傾向** -組織のセキュリティスコアと他のユーザーとの間の比較方法。 このビューには、同じような座席数を持つ組織の平均スコアを表す行と、設定可能なカスタムの比較ビューを含めることができます。
* **リスク許容傾向** -向上したリスクとしてマークされた改善アクションのタイムライン。
* **スコアの変更** 。指定された日付範囲で、獲得したポイント数と、それ以降のスコア変更と regressed をポイントします。

### <a name="compare-your-score-to-organizations-like-yours"></a>自分のスコアを組織と同じように比較する

自分に似た組織とスコアがどのように比較されるかを確認するには、2つの場所があります。 両方のグラフで [比較の **管理** ] を選択して、組織の情報を表示および編集できます。 また、業界、組織の規模、ライセンス、地域に基づいて、カスタム比較を作成することもできます。

#### <a name="comparison-bar-chart"></a>比較横棒グラフ

比較横棒グラフは [ **概要** ] タブです。グラフをポイントすると、スコアとスコアの機会が表示されます。 比較データは匿名化で、他のテナントが混在していることを正確に知ることはできません。

![類似する組織のスコアの横棒グラフ](../../media/secure-score/secure-score-comparison-bar.png)

- **自分の組織のよう** になります。次の条件に該当する、他のテナントの平均スコアが提供されます (比較するテナントが少なくとも5つ以上ある場合)。
    1. 同じ業種
    2. 同じ組織サイズ
    3. すべての地域
    4. 使用されている Microsoft 製品は80% に似ています。
    5. テナントから20% の範囲内の営業案件 (現在のライセンスによって達成できる最大スコア)

- **カスタム比較** : 次の条件に基づいて、[ **Manage Comparison** (複数のテナントが見つかった場合のみ)] を選択して最初にセットアップする必要があります。
    1. 選択された業界 (s)
    2. 選択されている組織のサイズ
    3. 選択した地域 (s)
    4. 選択されたライセンス
    5. 使用されている Microsoft 製品は80% に似ています。
    6. テナントから20% の範囲内の営業案件 (現在のライセンスによって達成できる最大スコア)

比較に使用できる他のテナントが5個未満になるように、選択範囲の選択をカスタマイズするためのオプションを選択していない場合は、「データが制限されているため、利用できません」と表示されます。

#### <a name="comparison-trend"></a>比較傾向

[ **指標 & の傾向** ] タブで、組織のセキュリティスコアが他のユーザーとどのように比較されるかを表示します。

![類似の組織のスコアの折れ線グラフ](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft セキュリティスコアの概要](microsoft-secure-score.md)
- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
