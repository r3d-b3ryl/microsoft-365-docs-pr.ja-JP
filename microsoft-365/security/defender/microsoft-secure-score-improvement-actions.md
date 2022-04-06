---
title: Microsoft Secure Score を通じてセキュリティの態勢を評価する
description: Microsoft Secure Score を向上させるためにアクションを実行する方法について説明します。Microsoft 365 Defenderします。
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
- m365initiative-m365-defender
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 8991c2aca277d2a08e5f8924a5e5cb354df6dc1f
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569456"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft Secure Score を使用してセキュリティの態勢を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 このファイルは、ポータルhttps://security.microsoft.com/securescoreのMicrosoft 365 Defender[があります](microsoft-365-defender.md)。

必要な情報を迅速に見つけるために、Microsoft の改善アクションはグループに整理されています。

- ID (Azure Active Directoryアカウント&ロール)
- デバイス (Microsoft Defender for Endpoint Microsoft [Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))
- アプリ (電子メール アプリとクラウド アプリ(Office 365およびMicrosoft Defender for Cloud Apps)

>[!NOTE]
>Microsoft Secure Score の最近のリリースでは、スコアリング モデルが改善され、Microsoft Secure Score は一時的に Identity Secure Score および Graph API と互換性がありません。 [詳細の表示](microsoft-secure-score-whats-new.md)

Microsoft Secure Score の概要ページで、これらのグループ間でのポイントの分割方法と使用可能なポイントを確認します。 また、合計スコアの全体表示、ベンチマーク比較によるセキュリティで保護されたスコアの履歴傾向、スコアを向上させるために実行できる優先順位付けされた改善アクションを取得できます。

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="セキュリティで保護されたスコアのホームページ (Microsoft 365 Defender ポータル)" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="check-your-current-score"></a>現在のスコアを確認する

現在のスコアを確認するには、[Microsoft Secure Score の概要] ページに移動し、[セキュリティで保護されたスコア] というタイル **を探します**。 スコアはパーセンテージで表示され、合計可能なポイント数から達成したポイント数が表示されます。

さらに、スコアの横にある **[含** める] ボタンを選択した場合は、スコアの異なるビューを選択できます。 これらの異なるスコア ビューは、スコア タイルとポイント内訳グラフのグラフに表示されます。

全体的なスコアのビューに追加できるスコアを次に示します。

- **計画スコア**: 計画されたアクションが完了すると、投影スコアを表示する
- **現在のライセンス スコア**: 現在の Microsoft ライセンスで達成できるスコアを表示する
- **達成可能なスコア**: Microsoft ライセンスと現在のリスク受け入れで達成できるスコアを表示する

このビューは、すべての可能なスコア ビューを含めた場合の外観です。

:::image type="content" source="../../media/secure-score/secure-score-achievable.png" alt-text="計画スコア、現在のライセンス スコア、および達成可能なスコアを含む、セキュリティで保護されたスコアがMicrosoft 365 Defenderポータル" lightbox="../../media/secure-score/secure-score-achievable.png":::

## <a name="take-action-to-improve-your-score"></a>スコアを上げるための対策

[ **改善アクション] タブ** には、攻撃の可能性がある表面に対処するセキュリティ推奨事項が一覧表示されます。 また、その状態 (対処、計画、リスクの受け入れ、第三者による解決、代替緩和による解決、完了) も含まれます。 すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。  

### <a name="ranking"></a>ランク付け

ランキングは、達成するために残されたポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいて行います。 最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。

### <a name="view-improvement-action-details"></a>改善アクションの詳細を表示する

特定の改善アクションを選択すると、ページ全体の飛び出しが表示されます。  

:::image type="content" source="../../media/secure-score/secure-score-improvement-action-details.png" alt-text="ポータルでの改善アクションのMicrosoft 365 Defender表示" lightbox="../../media/secure-score/secure-score-improvement-action-details.png":::

この操作を完了するには、いくつかの選択肢があります。

- [**管理] をMicrosoft 365 Defender** 構成画面に移動し、変更を行います。 その後、アクションが価値のあるポイントを取得し、フライアウトに表示されます。 ポイントの更新には通常約 24 時間かかります。

- [ **共有] を** 選択して、改善アクションへの直接リンクをコピーします。 リンクを共有するプラットフォームを選択して、電子メール、メール、Microsoft Teams、Microsoft Planner。

メモ **を追加** して、進行状況やコメントする他の項目を追跡します。 改善アクションに独自の **タグ** を追加する場合は、それらのタグでフィルター処理できます。

### <a name="choose-an-improvement-action-status"></a>改善アクションの状態を選択する

ステータスを選択し、改善アクションに固有のメモを記録します。

- **対処するには** - 改善アクションが必要と認識し、将来ある時点で対処する予定です。 この状態は、部分的に検出されたが完全には完了していないアクションにも適用されます。
- **計画済** み - 改善アクションを完了する具体的な計画が実施されています。
- **リスクの受け** 入れ - セキュリティは常に使いやすさとバランスを取り、すべての推奨事項が環境で機能する必要があります。 その場合は、リスクまたは残りのリスクを受け入れ、改善アクションを実行しない選択できます。 ポイントは指定されませんが、改善アクションの一覧にアクションが表示されなくなりました。 このアクションは履歴で表示したり、いつでも元に戻したりできます。
- **サード パーティによって解決され** 、代替の軽減策によって **解決されました。** 改善アクションは、サード パーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既に対処されています。 アクションが価値のあるポイントを得られるので、スコアは全体的なセキュリティの姿勢をよりよく反映します。 サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択できます。 改善アクションがこれらの状態のいずれかとしてマークされている場合、Microsoft は実装の完全性を確認できません。

#### <a name="threat--vulnerability-management-improvement-actions"></a>脅威& 脆弱性の管理改善アクション

[デバイス] カテゴリの改善アクションでは、状態を選択できません。 代わりに、アクションを実行する脅威と脆弱性の管理[関連付けられている](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)セキュリティMicrosoft 365 Defender指示されます。 選択した例外と、作成する正当化は、そのポータルに固有です。 Microsoft Secure Score ポータルには表示されません。

#### <a name="completed-improvement-actions"></a>改善アクションの完了

改善アクションの可能性があるすべてのポイントが達成された後、改善アクションの状態は "完了" になります。 Microsoft データを使用して、完了した改善アクションが確認され、状態を変更できない。

### <a name="assess-information-and-review-user-impact"></a>情報を評価し、ユーザーへの影響を確認する

「一目で **見る」** というセクションには、カテゴリ、保護できる攻撃、製品が表示されます。

**ユーザーの影響** は、改善アクションが実行された場合にユーザーが発生する操作であり、影響を受けるユーザーは影響を受けるユーザーです。

### <a name="implement-the-improvement-action"></a>改善アクションの実装

[ **実装]** セクションには、前提条件、改善アクションを完了するためのステップ バイ ステップの次の手順、改善アクションの現在の実装状態、および詳細なリンクが表示されます。

前提条件には、必要なライセンス、または改善アクションに対処する前に完了するアクションが含まれます。 ライセンスに十分なシートが含まれていますので、改善アクションを完了し、それらのライセンスが必要なユーザーに適用されます。  

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft Secure Score の概要](microsoft-secure-score.md)
- [Microsoft Secure Score の履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
