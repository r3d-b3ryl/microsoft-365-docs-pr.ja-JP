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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739813"
---
# <a name="reliability-insights"></a>信頼性の分析情報

このビューには、マネージド デバイスの正常性の概要が表示されます。 信頼性データを表示するには、[ **信頼性** ] タブを選択します。


![[信頼性] ウィンドウ: 左上のデバイス間の信頼性、右上の時間経過に伴う信頼性のグラフ、下部の上の問題テーブル。 右下のヘルプ ボタンとフィードバック ボタン。](../../media/insights_reliability.png)

[ **デバイス間の信頼性** ] セクションでは、"正常" と見なされるデバイスの割合と、最後に報告された障害以降に観察された平均時間を報告することで、過去 14 日間のデプロイの正常性の概要を簡単に示します。 

 
右側の **時間の経過に伴う信頼性** グラフは、重大なエラーが発生したデバイスの数と、時間の経過と共に観察された重大なエラーの合計数を報告します。

[ **上位の問題]** セクションでは、マネージド デバイスの少なくとも 5% に影響する特定の検出された問題について詳しく説明します。 報告される詳細は次のとおりです。

- 問題の種類
    - アプリケーションがクラッシュし、アプリが機能しなくなったり、予期せず停止したりする
    - アプリケーションがハングし、アプリケーションが入力への応答を停止する
    - 重大なエラー。これは、Windowsから回復できない問題が発生したときに発生します
- 同じ問題の影響を受けるデバイスの数
- 数が表すマネージド デバイスの割合
- 特定の問題の発生の合計数
- 問題の原因と思われるソフトウェア コンポーネント
- 検出された問題のカテゴリ:
    - ブラウザー (Edge、Chrome、IE)
    - 不明 (Microsoft 以外のコンポーネント)
    - ドライバー (オーディオ、グラフィックス、またはその他のドライバー)
    - 生産性 (Slack、G スイート、Microsoft Officeおよびそのアドオンまたは拡張機能(Teams)
    - メディア (画像、音楽、またはビデオ アプリ)
    - セキュリティ (Windows セキュリティ コンポーネント)
- Microsoft Managed Desktop Operations が問題を調査して修復する現在の状態

