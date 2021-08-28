---
title: データの結果に基づくAdvanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: ケース ファイルのレビュー セットのAdvanced eDiscoveryを決定するのに役立つデータを提供する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: deb47c0c795a828804722085f8cfa3b002580307
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58571364"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a>関連性に基づく決定は、データのAdvanced eDiscovery
  
[関連] モジュールの Advanced eDiscovery で、[決定] タブには、ケース ファイルのレビュー セットのサイズを決定するための意思決定サポート統計の表示と使用に関する追加情報が表示されます。
  
## <a name="using-the-decide-tab"></a>[決定] タブの使用

![関連性の決定。](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
このタブには、次のコンポーネントが含まれます。
  
- **問題**: ここから、リストから関心のある問題を選択できます。

- **レビューリコール率**: 関連性スコアにAdvanced eDiscoveryレビューの比較。 グラフのカットオフ ポイントは、関連性スコアにマップされた、レビューするファイルの割合を表します。 これは、関連性テスト フェーズで、およびカリングのエクスポートしきい値として使用されます。 レビューするファイル数の既定のカットオフ ポイントは、呼び出しと精度のバランスが最適な時点です。 実際のカットオフ ポイントは、目標とコストトレードオフ (%review) とリスク (%リコール) に応じてユーザーが決定する必要があります。 スライダーを使用すると、カットオフ ポイントを調整し、グラフとパラメーターへの影響、取得する関連ファイルの割合を調整する場合、および決定を検証する前に確認できます。

- **パラメーター**: レビュー、呼び出し、次に関連するコスト パラメーター、および合計コスト パラメーターは、ケース全体のコレクションに関連するレビュー セットに関連する累積計算統計です。 これらのパラメーターの定義は次のとおりです。

  - **レビュー**: このカットオフに基づいて確認するファイルの割合。

  - **呼び** 出し : レビュー セット内の関連するファイルの割合。

  - **次に関連**: 現在レビュー セットに含されていない別の関連ファイルを確認して識別するためのコスト。

  - **合計コスト**: ケース ファイルのこの割合を確認するコスト。 コスト パラメーターの設定は、ケース マネージャーによって設定できます。

  - **関連性スコアによる配布**: 左の濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。 ツール ヒントには、関連性スコアと、ファイルの合計に関連するレビュー ファイル セット内のファイルの関連割合が表示されます。

展開された [詳細 **] ウィンドウ** には、詳細が表示されます。 コレクション図形内のファイルには、空のファイルやネビュラス なファイルは含めされません。 ファミリ ファイルの図は、関連性に読み込まれ、ファミリの一部としてカウントされていないファイルを表します。
