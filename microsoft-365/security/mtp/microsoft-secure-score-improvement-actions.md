---
title: Microsoft セキュリティスコアを使用してセキュリティの姿勢を評価する
description: Microsoft 365 セキュリティセンターで Microsoft セキュリティスコアを向上させるための処置を行う方法について説明します。
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
ms.openlocfilehash: cb2aad70b8ba6ccd9075513b5f383ede42ebd6c0
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295130"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Microsoft セキュリティスコアを使用してセキュリティの姿勢を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。

必要な情報を迅速に把握できるように、Microsoft の改善のための処置は次のグループに分類されています。

* Identity (Azure Active Directory アカウント & の役割)
* データ (Microsoft Information Protection)
* デバイス (Microsoft Defender ATP、 [デバイスの Microsoft セキュリティスコア](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)と呼ばれる)
* アプリ (Office 365 や Microsoft Cloud App Security を含む、メール アプリとクラウド アプリ)
* インフラストラクチャ (現在のところ、改善のための処置はありません)

>[!NOTE]
>Microsoft Secure Score の最近のリリースでは、Microsoft セキュリティスコアを Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がない、向上したスコアリングモデルがリリースされました。 [詳細の表示](microsoft-secure-score-whats-new.md)

[Microsoft セキュリティスコアの概要] ページで、これらのグループ間のポイントの分割方法と、使用可能なポイントを参照してください。 また、ベンチマークの総合スコア、セキュリティスコアの履歴傾向、ベンチマーク比較を使用して、スコアを向上させるために実行できる改善措置の優先順位を取得することもできます。

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>現在のスコアを確認する

現在のスコアを確認するには、Microsoft の [セキュリティスコアの概要] ページに移動して、 **セキュリティで保護さ**れたスコアを示すタイルを探します。 スコアは、パーセンテージとして表示され、総ポイント数で得られたポイント数として表示されます。

また、スコアの横にある [ **追加** ] ボタンを選択すると、スコアのさまざまなビューを選択できます。 これらの異なるスコア表示は、スコアタイルおよび点の内訳グラフのグラフに表示されます。

次のスコアは、全体的なスコアの表示に追加して、全体的なスコアをより正確に把握することができます。

- **予定スコア**: 計画されたアクションが完了したときに予想されるスコアを表示する
- **現在のライセンススコア**: 現在の Microsoft ライセンスで達成できるスコアを表示する
- **実現**可能なスコア: Microsoft のライセンスと現在のリスクの受け入れによって得られるスコアを表示します。

このビューは、次のように表示されます。すべてのスコアの表示が含まれている場合は、以下のようになります。

![予定スコア、現在のライセンススコア、実現可能スコアを含む、セキュリティで保護されたスコア](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>スコアを上げるための対策

[ **向上** したアクション] タブには、攻撃対象となる可能性のあるセキュリティ推奨が一覧表示されます。 また、それらの状態 (住所、計画済み、リスクの承諾、サードパーティによる解決、代替の軽減による解決、完了) も含まれます。 すべての改善のための処置の検索、フィルター処理、グループ化を行うことができます。  

### <a name="ranking"></a>ランク付け

ランク付けは、残されているポイント数、実装の難易度、ユーザーへの影響、および複雑さに基づいています。 最高ランクの改善のための処置では、難易度、ユーザーへの影響度、複雑度は低く、高ポイントを取ることができます。

### <a name="view-improvement-action-details"></a>向上アクションの詳細を表示する

特定の改善アクションを選択すると、完全なページポップアップが表示されます。  

![改善アクションのポップアップの例 ](../../media/secure-score/secure-score-improvement-action-details.png)
 *図 2: 改善アクションのポップアップの例*

この操作を完了するには、いくつかの選択肢があります。

* [ **管理** ] を選択して、構成画面に移動し、変更を行います。 その後、そのアクションに価値があるポイントを取得します。通常、更新には約24時間かかります。

* [ **共有** ] を選択して、[改善] アクションへの直接リンクをコピーします。 また、電子メール、Microsoft Teams、Microsoft Planner、または ServiceNow など、リンクを共有するプラットフォームを選択することもできます。 ServiceNow を選択すると、[変更チケット] を作成できます。このチケットは ServiceNow と Microsoft 365 セキュリティセンターのホームに表示されます。 詳細については、「 [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)」を参照してください。

### <a name="choose-an-improvement-action-status"></a>改善アクションの状態を選択する

[改善] アクションに固有の状態を選択し、メモを記録します。

- **To アドレス** -改善アクションが必要であることを認識し、将来のある時点での対処を計画します。 この状態は、部分的に検出されたが完全に完了していないアクションにも適用されます。
- **計画** 済み-改善アクションを完了するための具体的なプランが用意されています。
- **承認済みリスク** -セキュリティは常にユーザビリティにバランスをとる必要があり、お客様の環境ですべての推奨事項が機能するわけではありません。 その場合は、リスクを受け入れるか、またはリスクを軽減するかを選択して、改善アクションが実行されないようにすることができます。 ポイントは表示されませんが、改善アクションの一覧には表示されなくなります。 このアクションは履歴で表示したり、いつでも元に戻したりできます。
- **サード** パーティによって解決され、 **別の軽減** によって解決されました。改善アクションは、サードパーティ製のアプリケーションまたはソフトウェア、または内部ツールによって既に対処されています。 この操作に必要なポイントが得られます。このため、スコアは全体的なセキュリティ対策をより適切に反映できます。 サードパーティまたは内部ツールがコントロールをカバーしなくなった場合は、別の状態を選択することができます。 改善アクションがこれらの状態のどちらかとしてマークされている場合、Microsoft は、実装の完全性を確認できません。

#### <a name="threat--vulnerability-management-improvement-actions"></a>脅威 & 脆弱性管理の改善アクション

"デバイス" カテゴリの向上アクションについては、状態を選択できません。 代わりに、 [Microsoft Defender セキュリティセンター](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)の関連する[脅威 & 脆弱性管理 (tvm) セキュリティに関する推奨事項](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)に従ってアクションを実行します。 選択する例外と、作成する根拠は、そのポータルに固有のものになります。 これは、Microsoft セキュリティスコアポータルには含まれません。

#### <a name="completed-improvement-actions"></a>完了した改善アクション

改善アクションのすべての可能なポイントが達成されたら、改善アクションの状態は "完了" になります。 完了した改善アクションは Microsoft データによって確認され、状態を変更することはできません。

### <a name="assess-information-and-review-user-impact"></a>情報を評価し、ユーザーへの影響を確認する

「 **ひとめで** 」というセクションでは、カテゴリ、保護できる攻撃、および製品について説明します。

**ユーザーへの影響**は、改善アクションが実行された場合にユーザーが**受ける**影響を示しています。

### <a name="implement-the-improvement-action"></a>向上アクションを実装する

[ **実装** ] セクションには、すべての前提条件、[改善] アクションを完了するためのステップバイステップの手順、向上アクションの現在の実装状態、詳細なリンクが表示されます。

前提条件は、取得する必要があるライセンス、または改善アクションが解決される前に完了する必要があるアクションを含みます。 改善アクションを完了し、それらのライセンスが必要なユーザーに適用されるように、ライセンスに十分な座席があることを確認してください。  

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [Microsoft セキュリティスコアの概要](microsoft-secure-score.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
