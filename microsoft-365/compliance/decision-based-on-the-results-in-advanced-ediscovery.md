---
title: Advanced eDiscovery の結果に基づく決定
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
description: Advanced eDiscovery の [決定] タブで、ケース ファイルのレビュー セットの正しいサイズを判断するのに役立つデータを提供する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0423a21520375f1d9de8e2eaeca142b979ff1883
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759869"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) の結果に基づく決定

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
 Advanced eDiscovery では、[決定] タブには、ケース ファイルのレビュー セットのサイズを決定するための意思決定サポート統計を表示および使用するための追加情報が表示されます。 
  
## <a name="using-the-decide-tab"></a>[決定] タブの使用

![関連性の決定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
このタブには、次のコンポーネントが含まれます。
  
- **問題**: ここから、リストから関心のある問題を選択できます。 
    
- **レビューリコール率**: 関連性スコアに従った Advanced eDiscovery レビューの比較。 グラフの切り離し点は、関連性スコアにマップされた、レビューするファイルの割合を表します。 これは、関連性テスト フェーズで使用され、カリングのエクスポートしきい値として使用されます。 レビューするファイル数の既定の切り離し点は、取り消しと精度のバランスが最適な時点です。 実際の切り離しポイントは、目標とコストのトレードオフ (%review) とリスク (%recall) に応じてユーザーが決定する必要があります。 スライダーを使って、カットオフ ポイントを調整し、グラフとパラメーターへの影響、取得する関連ファイルの割合を調整する場合、および決定を検証する前に確認できます。
    
- **パラメーター**: レビュー、取り消し、次の関連する総コストパラメーターは、ケース全体のコレクションに関連するレビュー セットに関連する累積計算された統計です。 これらのパラメーターの定義は次のとおりです。
    
    **Review**: このカットオフに基づいて確認するファイルの割合。 
    
    **取** り消し : レビュー セット内の関連ファイルの割合。 
    
    **次に関連**: 現在レビュー セットに含されていない追加の関連ファイルを確認して識別するためのコスト。 
    
    **総コスト**: ケース ファイルのこの割合を確認するコスト。 コスト パラメーターの設定は、ケース マネージャーが設定できます。
    
- **関連性スコアによる配布**: 左に濃い灰色の表示のファイルは、カットオフ スコアの下に表示されます。 ツール ヒントには、ファイルの合計に関連する、レビュー ファイル セット内のファイルの関連性スコアと関連する割合が表示されます。
    
展開された [詳細] ウィンドウには、追加の詳細が表示されます。 コレクションの図に含まれるファイルには、空のファイルや大きいなファイルは含めされません。 ファミリ ファイルの図は、関連性に読み込まれなのにファミリの一部としてカウントされているファイルを表します。
  
