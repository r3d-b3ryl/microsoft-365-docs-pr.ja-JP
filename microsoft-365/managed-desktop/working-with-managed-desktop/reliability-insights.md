---
title: 信頼性の分析情報
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950344"
---
# <a name="reliability-insights"></a>信頼性の分析情報

このビューには、管理対象デバイスの正常性の概要が表示されます。 信頼性データを表示するには、[信頼性] **タブを選択** します。


![[信頼性] ウィンドウ: 左上のデバイス間の信頼性、右上の時間のグラフの信頼性、下部の上の問題の表。 右下のヘルプボタンとフィードバック ボタン。](../../media/insights_reliability.png)

[ **デバイス** 間の信頼性] セクションでは、"正常" と見なされるデバイスの割合と、前回報告されたエラー以降に観察された平均時間を報告することで、過去 14 日間の展開の正常性の概要を簡単に説明します。 

 
右側 **の [時間の間の** 信頼性] グラフは、重大なエラーが発生したデバイスの数と、時間の間に観測された重大なエラーの総数を報告します。

[ **上位の問題]** セクションでは、管理対象デバイスの少なくとも 5% に影響する特定の検出された問題について詳しくは説明します。 報告された詳細には、次のものが含まれます。

- 問題の種類
    - アプリケーションがクラッシュし、アプリが機能を停止するか、予期せず停止する
    - アプリケーションがハングし、アプリケーションが入力への応答を停止する
    - 重大なエラー(Windows で回復できない問題が発生した場合に発生する)
- 同じ問題の影響を受けるデバイスの数
- 数が表す管理対象デバイスの割合
- 特定の問題の発生回数の合計
- 問題の発生源と思えるソフトウェア コンポーネント
- 検出された問題のカテゴリ:
    - ブラウザー (エッジ、クロム、IE)
    - 不明 (Microsoft 以外のコンポーネント)
    - ドライバー (オーディオ、グラフィックス、その他のドライバー)
    - 生産性 (Slack、G-Suites、Microsoft Officeアドオンまたは拡張機能 Teams)
    - メディア (画像、音楽、またはビデオ アプリ)
    - セキュリティ (Windows セキュリティ コンポーネント)
- Microsoft Managed Desktop Operations が問題を調査および修復する現在の状態

