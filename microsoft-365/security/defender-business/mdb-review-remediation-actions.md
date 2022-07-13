---
title: Microsoft Defender for Businessで修復アクションを確認する
description: Defender for Business で検出された脅威に対して実行された修復を表示します。 アクションは、Microsoft 365 Defender ポータルのアクション センターで表示できます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 63bbeb218693174402264bb59a6c014e63e14bef
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66770979"
---
# <a name="review-remediation-actions-in-the-action-center"></a>アクション センターで修復アクションを確認する

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法によっては、修復アクションが自動的に実行されるか、承認時にのみ実行される場合があります。 修復アクションの例を次に示します。 
- ファイルを検疫に送信する
- プロセスの実行を停止する
- スケジュールされたタスクの実行

すべての修復アクションは、アクション センターで追跡されます。

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="アクション センターのスクリーンショット":::

**この記事では、以下について説明します。**

- [アクション センターを使用する方法](#how-to-use-the-action-center)
- [修復アクション](#remediation-actions)


## <a name="how-to-use-the-action-center"></a>アクション センターを使用する方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. 保留中のアクションを表示して承認 (または拒否) するには、**[保留中]** タブを選択します。 アクションは、ウイルス対策/マルウェア対策保護、自動調査、手動応答アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. **[履歴]** タブを選択して、完了したアクションのリストを表示します。

## <a name="remediation-actions"></a>修復アクション

Defender for Business には、いくつかの修復アクションが含まれています。 これらのアクションには、手動応答アクション、自動調査後のアクション、ライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションの一覧を示します。

| ソース  | Actions  |
|---------|---------|
| [自動調査](../defender-endpoint/automated-investigations.md)      |<ul><li>ファイルの検疫</li><li>レジストリ キーの削除</li><li>プロセスの強制終了</li><li>サービスの停止</li><li>ドライバーの無効化</li><li>スケジュールされたタスクの実行 </li></ul> |
| [手動応答アクション](../defender-endpoint/respond-machine-alerts.md)   |<ul><li>ウイルス対策スキャンの実行</li><li>デバイスを分離する</li><li>停止と検疫</li><li>ファイルをブロックまたは許可するインジケーターを追加する</li></ul> |
| [ライブ応答](../defender-endpoint/live-response.md)   |<ul><li>フォレンジック データを収集する</li><li>ファイルを分析する</li><li>スクリプトの実行</li><li>分析のために疑わしいエンティティを Microsoft に送信する</li><li>ファイルを修復する </li><li>積極的に脅威を捜索する</li></ul>|

## <a name="next-steps"></a>次の手順

- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [Defender for Business でデバイスを管理する](mdb-manage-devices.md)
