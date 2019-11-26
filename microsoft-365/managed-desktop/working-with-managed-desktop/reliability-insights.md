---
title: 信頼性の分析情報
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257035"
---
# <a name="reliability-insights"></a>信頼性の分析情報

このビューでは、管理対象デバイスの正常性の概要が提供されます。 信頼性データを表示するには、[**信頼性**] タブを選択します。


![信頼性ウィンドウ](images/insights_reliability.png)

「 **Devices**による信頼性」セクションでは、過去14日間にわたる展開の迅速な正常性の概要を提供します。これにより、"正常" と見なされているデバイスの割合と前回報告されたエラー以降に監視された平均時間を報告します。 

 
右上の [時間] グラフの**信頼性**は、重大なエラーが発生したデバイスの数と、時間の経過とともに観測された重大なエラーの合計数を報告します。

「**上位の問題**」セクションでは、管理対象デバイスの少なくとも5% に影響する特定の問題を検出しました。 報告される詳細情報は次のとおりです。

- 問題の種類
    - アプリケーションがクラッシュし、アプリが動作しなくなったか、アプリケーションが予期せず停止する
    - アプリケーションがハングし、アプリケーションが入力への応答を停止する
    - 重大なエラー。 Windows が回復できない問題が発生したときに発生します。
- 同じ問題によって影響を受けるデバイスの数
- 番号が表す管理対象デバイスの割合
- 特定の問題の出現回数の合計
- 問題のソースとして表示されるソフトウェアコンポーネント
- Microsoft Managed Desktop 操作の現在の状態は、この問題の調査と remediates

