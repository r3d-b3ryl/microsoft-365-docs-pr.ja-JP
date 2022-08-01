---
title: Microsoft 365 Defenderの Defender Experts for Hunting レポートを理解する
ms.reviewer: ''
description: Defender Experts for Hunting サービスは、ハンティング サービスが環境内で発生したすべての脅威を理解するのに役立つ月次レポートを発行します。
keywords: アナリスト レポート, Defender エキスパート レポート, 検出, Defender エキスパート通知, ハンティング, 通知, 脅威カテゴリ, ハンティング レポート
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 179b13d31091e2c5ec60ba467bb06f2d072f6cdd
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107246"
---
# <a name="understand-the-defender-experts-for-hunting-report-in-microsoft-365-defender"></a>Microsoft 365 Defenderの Defender Experts for Hunting レポートを理解する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Defender Experts for Hunting では、人間のインテリジェンスと専門家がトレーニングしたテクノロジを階層化し、Microsoft 365 Defender顧客が直面する重大な脅威を理解するのに役立ちます。 Defender Expert の脅威検出スキル、脅威の状況の完全な理解、および新たな脅威に関する知識が、環境内のそれらの脅威を特定、優先順位付け、対処するためにどのように役立つかを示します。 

Defender Experts for Hunting サービスは、Microsoft 365 Defender製品によって生成されたアラートと共に、環境内で発生したすべての脅威を理解するのに役立つ月次レポートを発行します。

Microsoft 365 Defender ポータルで最新のレポートを表示するには、**レポート** に移動し、**Defender Experts** > **Defender Experts for Hunting レポートを** 選択します。

## <a name="scan-the-defender-experts-for-hunting-report-to-know-what-to-prioritize"></a>Defender Experts for Hunting レポートをスキャンして、優先順位を付ける内容を把握する

レポートの各セクションは、Defender エキスパートが環境で見つけた脅威に関するより多くの分析情報を提供するように設計されています。 レポートには、次の表で説明するセクションが含まれています。

| [レポート] セクション | 説明 |
|--|--|
| ハントとトリアージ | お使いの環境で見つかった潜在的なサイバーセキュリティの問題の合計数。 |
| 調査 | その性質と範囲を決定するためにさらに分析する必要があるサイバーセキュリティの問題の数。 |
| 通知 (通知の表示) | Defender エキスパートが送信した Defender エキスパート通知の数。 これらの通知は、緊急度と影響に基づいて優先順位を付ける必要がある、環境内で調査された可能性のある脅威アクティビティに関連しています。 |
| MITRE ATT&CK の戦術が観察されました | 環境で観察され、 [MITRE ATT&CK フレームワーク](https://attack.mitre.org/)に従ってマップされた攻撃戦術と手法の数。 このセクションでは、各戦術に達した攻撃の数を視覚化し、先に進んだ攻撃を確認するなどの適切なアクションを実行できるようにします。 |
| 観察された脅威カテゴリ | カテゴリは、環境で観察される最も重大な脅威とリスクを表しています。 最も重要なカテゴリが強調表示され、脅威の既知の特性、動作、および潜在的な影響に基づいて、セキュリティ体制をさらに評価および評価するのに役立ちます。 また、対処する緊急タスクに集中して優先順位を付けることもできます。 |

サンプル レポートの次のスクリーンショットを参照してください。

![Microsoft 365 Defender ポータルの Microsoft Defender Experts for Hunting レポートのスクリーンショット。](../../media/mte/defenderexperts/defender-experts-report.png)

## <a name="view-defender-experts-notifications"></a>Defender エキスパート通知を表示する

Defender Experts Notification は、環境内で観察された Defender Experts for Hunting の重要な脅威アクティビティについて説明し、組織を修復して防御するための推奨事項を提供します。

Defender Experts for Hunting レポートには、選択した時間に Defender エキスパートが送信した Defender エキスパート通知の合計数が表示されます。 これらの通知を表示するには、[**通知**] の横にある **[通知の表示**] を選択します。

このリンクをクリックすると、Microsoft 365 Defenderインシデント ページにリダイレクトされます。 Defender Expert for Hunting アラートまたは Defender エキスパート通知には Defender エキスパートのラベルが付 **けられます**。

> [!NOTE]
> **[通知の表示]** リンクは、[**通知**] に表示される値が 1 以上の場合にのみ表示されます。

## <a name="identify-potential-attack-entry-points-and-other-security-weak-spots"></a>潜在的な攻撃エントリ ポイントとその他のセキュリティの弱点を特定する

MITRE ATT&CK 戦術は、各攻撃フェーズで達成しようとしている敵対的な目標を表します。 レポートのセクション **で観察された MITRE ATT&CK 戦術** は、到達したフェーズに対する攻撃の進行を追跡します。

1.  偵察
2.  リソース開発
3.  初期アクセス
4.  実行
3.  永続性
4.  特権エスカレーション
5.  防御回避
6.  資格情報へのアクセス
7.  検出
8.  横方向の移動
9.  コレクション
10. コマンドとコントロール
11. 流出
12. 影響

Defender Experts for Hunting によるMicrosoft 365 Defenderと調査からのシグナルは、棒グラフに示されているこれらの戦術を特定するのに役立ちます。 このグラフは、急増の場所を視覚化するのに役立ち、対応する包含と修復アクションを計画するために必要な情報を提供します。

## <a name="know-and-understand-the-prevalent-threats-in-your-environment"></a>環境内の一般的な脅威を把握し、理解する

脅威カテゴリは、セキュリティの脅威を特定してクラスに整理し、その影響を評価および評価し、環境に対するこれらの脅威を防止または軽減するための戦略を開発するのに役立ちます。 レポートの **[脅威カテゴリ** ] セクションには、環境内で検出された重大なリスクと脅威を含む横棒グラフが表示され、露出の幅と範囲を理解するのに役立ちます。

利用可能なさまざまな脅威カテゴリの中で、MITRE ATT&CK フレームワークの範囲に含まれていないため、次のカテゴリが慎重に選択されます。

- ランサムウェア
- マルウェア
- 武器化
- 搾り取る
- 配達

横棒グラフに示されているように、最も影響を受けるカテゴリに基づいて修復に優先順位を付けることができます。

