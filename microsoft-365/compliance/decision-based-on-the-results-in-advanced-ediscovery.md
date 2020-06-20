---
title: 高度な電子情報開示の結果に基づく決定
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
description: 'Microsoft 365 Advanced eDiscovery の [判断] タブによって、ケースファイルのレビューセットの正しいサイズを判断するのに役立つデータが提供される方法について説明します。 '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0139bc0505150a4d27aaca97b9b253f2043d649f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817906"
---
# <a name="decision-based-on-the-results-in-advanced-ediscovery-classic"></a>高度な電子情報開示の結果に基づく決定 (クラシック)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 上級電子情報開示の場合、[判断] タブでは、サポートの判断に関する詳細情報を提供して、ケースファイルのレビューセットのサイズを決定します。 
  
## <a name="using-the-decide-tab"></a>[判断] タブの使用

![関連性の決定](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
このタブには次のものが含まれます。
  
- **問題**: ここから、対象の問題をリストから選択できます。 
    
- **レビュー-取り消し率**: 関連性スコアによる高度な電子情報開示レビューの比較。 グラフのカットオフポイントは、関連性スコアにマッピングされた、確認するファイルのパーセンテージを表します。 これは、関連性テストフェーズで、カリングのエクスポートしきい値として使用されます。 既定のカットオフポイントは、確認するファイル数に対して、呼び戻しと精度の間のバランスが最適であるポイントです。 実際のカットオフポイントは、目標とコストのトレードオフ (% レビュー) およびリスク (% のリコール) に応じて、ユーザーによって決定される必要があります。スライダーを使用して、カットオフポイントを調整し、グラフおよびパラメータに対する影響を確認したり、取得する関連ファイルの割合を調整したり、決定を検証したりすることができます。
    
- **パラメーター**: Review、呼び戻し、次の関連性、およびコストの合計パラメーターは、ケース全体のコレクションに対するレビューセットに関連する累積計算された統計情報です。 これらのパラメーターの定義は次のとおりです。
    
    **レビュー**: このカットオフに基づいてレビューするファイルのパーセンテージ。 
    
    [**呼び戻し**: 校閲セット内の関連ファイルのパーセンテージ。 
    
    **次に関連**する: 現在レビューセットに含まれていない追加の関連ファイルを確認して識別するためのコスト。 
    
    **合計コスト**: この割合のケースファイルを確認するためのコスト。 コストパラメーターの設定は、ケースマネージャーで設定できます。
    
- **関連性スコア別の配布**: 濃い灰色表示のファイルは、左側にカットオフスコアの下にあります。 ツールヒントには、関連スコアと、レビューファイルセット内のファイルの関連パーセンテージが、ファイル総数に対して表示されます。
    
拡張された詳細ウィンドウには、追加の詳細が表示されます。 コレクションの図のファイルには、空または nebulous ファイルは含まれません。 ファミリーファイル図は、関連性がなく、ファミリーの一部としてカウントされているファイルを表します。
  
## <a name="related-topics"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[関連性の評価について](assessment-in-relevance-in-advanced-ediscovery.md)
  
[タグ付けと評価](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[関連性トレーニングの実行](tagging-and-assessment-in-advanced-ediscovery.md)
  
[関連性分析の追跡](track-relevance-analysis-in-advanced-ediscovery.md)
  
[関連性分析のテスト](test-relevance-analysis-in-advanced-ediscovery.md)

