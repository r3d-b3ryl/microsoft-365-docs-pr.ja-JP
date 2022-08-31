---
title: Microsoft Secure Score を使用してセキュリティ体制を評価する
description: Microsoft 365 Defender ポータルで Microsoft Secure Score を改善するためのアクションを実行する方法について説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender portal, 改善アクション
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: dac1fa506dbb5de8a74817d20722738640ee2719
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480429"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft Secure Score を使用してセキュリティ体制を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 https://security.microsoft.com/securescore [Microsoft 365 Defender ポータル](microsoft-365-defender.md)にあります。

必要な情報をより迅速に見つけられるように、Microsoft の改善アクションはグループにまとめられています。

- ID (Azure Active Directory アカウント & ロール)
- デバイス (Microsoft Defender for Endpoint、[デバイスの Microsoft Secure Score](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices) と呼ばれます)
- アプリ (Office 365とMicrosoft Defender for Cloud Appsを含む電子メール アプリとクラウド アプリ)

>[!NOTE]
>Microsoft Secure Score の最近のリリースでは、改良されたスコア付けモデルがリリースされ、Microsoft Secure Score は一時的に Identity Secure Score およびGraph APIと互換性がありません。 [詳細の表示](microsoft-secure-score-whats-new.md)

Microsoft Secure Score の概要ページで、これらのグループ間でポイントを分割する方法と、使用可能なポイントを確認します。 また、合計スコア、ベンチマーク比較を使用したセキュリティスコアの履歴傾向、スコアを改善するために実行できる優先順位付けされた改善アクションのオールアップ ビューを取得することもできます。

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="Microsoft 365 Defender ポータルのセキュリティスコアホームページ" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="check-your-current-score"></a>現在のスコアを確認する

現在のスコアを確認するには、Microsoft Secure Score の概要ページに移動し、[セキュリティスコア] と表示されているタイル **を探します**。 スコアはパーセンテージで表示され、合計可能なポイントのうち達成したポイントの数も表示されます。

さらに、スコアの横にある [ **含める** ] ボタンを選択した場合は、スコアのさまざまなビューを選択できます。 これらの異なるスコア ビューは、スコア タイルとポイント内訳グラフのグラフに表示されます。

全体的なスコアのビューに追加できるスコアを次に示します。これを使用すると、全体的なスコアの全体像を把握できます。

- **計画スコア: 計画** アクションが完了したときに、投影スコアを表示する
- **現在のライセンス スコア**: 現在の Microsoft ライセンスで達成できるスコアを表示する
- **達成可能なスコア**: Microsoft ライセンスと現在のリスク受け入れで達成できるスコアを表示する

このビューは、考えられるすべてのスコア ビューを含めている場合の外観です。

:::image type="content" source="../../media/secure-score/secure-score-achievable.png" alt-text="Microsoft 365 Defender ポータルでの計画スコア、現在のライセンス スコア、達成可能なスコアを含むセキュリティ スコア" lightbox="../../media/secure-score/secure-score-achievable.png":::

## <a name="take-action-to-improve-your-score"></a>スコアを上げるための対策

[ **改善アクション]** タブには、攻撃の可能性がある表面に対処するセキュリティに関する推奨事項が一覧表示されます。 また、状態 (対応、計画、リスクの受け入れ、サード パーティを通じた解決、代替軽減策による解決、完了) も含まれます。 すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。  

### <a name="ranking"></a>ランク付け

ランキングは、達成するために残されたポイントの数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。 最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。

### <a name="view-improvement-action-details"></a>改善アクションの詳細を表示する

特定の改善アクションを選択すると、完全なページ ポップアップが表示されます。  

:::image type="content" source="../../media/secure-score/secure-score-improvement-action-details.png" alt-text="Microsoft 365 Defender ポータルでの改善アクションのポップアップ" lightbox="../../media/secure-score/secure-score-improvement-action-details.png":::

この操作を完了するには、いくつかの選択肢があります。

- **Microsoft 365 Defenderで [管理**] を選択して構成画面に移動し、変更を行います。 その後、ポップアップに表示されるアクションの価値があるポイントを取得します。 ポイントの更新には、通常約 24 時間かかります。

- [ **共有** ] を選択して、改善アクションへの直接リンクをコピーします。 メール、Microsoft Teams、Microsoft Plannerなどのリンクを共有するプラットフォームを選択することもできます。

メモ **を追加** して、進行状況やコメントするその他の内容を追跡します。 改善アクションに独自の **タグ** を追加する場合は、それらのタグでフィルター処理できます。

### <a name="choose-an-improvement-action-status"></a>改善アクションの状態を選択する

改善アクションに固有の状態を選択し、メモを記録します。

- **対処するには** 、 - 改善アクションが必要であることを認識し、将来のある時点で対処する予定です。 この状態は、部分的に検出されたが完全には完了していないアクションにも適用されます。
- **計画済み** - 改善アクションを完了するための具体的な計画が用意されています。
- **リスクが許容される** - セキュリティは常に使いやすさとバランスを取る必要があり、すべての推奨事項が環境に適しているわけではありません。 このような場合は、リスクまたは残りのリスクを受け入れ、改善アクションを適用しないことを選択できます。 ポイントは与えられませんが、改善アクションの一覧にアクションは表示されなくなります。 このアクションは履歴で表示したり、いつでも元に戻したりできます。
- **サード パーティを通じて解決** され、 **別の軽減策を通じて解決** された - 改善アクションは、サードパーティのアプリケーションまたはソフトウェア、または内部ツールによって既に対処されています。 アクションの価値があるポイントが得られるので、全体的なセキュリティ体制がスコアに反映されます。 サード パーティまたは内部ツールでコントロールがカバーされなくなった場合は、別の状態を選択できます。 改善アクションがこれらの状態のいずれかとしてマークされている場合、Microsoft は実装の完全性を把握できません。

#### <a name="microsoft-defender-vulnerability-management-improvement-actions"></a>Microsoft Defender 脆弱性の管理改善アクション

[デバイス] カテゴリの改善アクションでは、状態を選択できません。 代わりに、アクションを実行するために、Microsoft 365 Defenderに関連付けられている[Microsoft Defender 脆弱性の管理セキュリティに関する推奨事項](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)が表示されます。 選択した例外と書き込む理由は、そのポータルに固有です。 Microsoft Secure Score ポータルには表示されません。

#### <a name="completed-improvement-actions"></a>完了した改善アクション

改善アクションのすべての可能なポイントが達成されると、改善アクションは "完了" 状態になります。 Microsoft データでも完了した改善アクションが確認され、状態を変更することはできません。

### <a name="assess-information-and-review-user-impact"></a>情報を評価し、ユーザーへの影響を確認する

一 **目で** わかるセクションには、カテゴリ、保護できる攻撃、製品が表示されます。

**ユーザーの影響** は、改善アクションが適用された場合にユーザーが経験するものであり、 **影響を受けるユーザー** は影響を受けるユーザーです。

### <a name="implement-the-improvement-action"></a>改善アクションを実装する

**[実装]** セクションには、改善アクションを完了するための前提条件、ステップ バイ ステップの次の手順、改善アクションの現在の実装状態、および詳細なリンクが示されています。

前提条件には、必要なライセンス、または改善アクションに対処する前に完了するアクションが含まれます。 改善アクションを完了するのに十分なシートがライセンスに含まれていることと、それらのライセンスが必要なユーザーに適用されていることを確認します。  

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、 [セキュリティ、プライバシー、コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿&お知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft Secure Score の概要](microsoft-secure-score.md)
- [Microsoft Secure Score 履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
