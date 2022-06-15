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
ms.openlocfilehash: 5c73b840b127770c4581dda4d03b3c95066df515
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089530"
---
# <a name="review-remediation-actions-in-the-action-center"></a>アクション センターで修復アクションを確認する

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法によっては、修復アクションが自動的に実行されるか、承認時にのみ実行される場合があります。 修復アクションの例としては、ファイルの検疫への送信、プロセスの実行の停止、スケジュールされたタスクの削除などがあります。 すべての修復アクションは、アクション センターで追跡されます。

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="アクション センターのスクリーンショット":::

**この記事では、以下について説明します。**

- [アクション センターを使用する方法](#how-to-use-the-action-center)
- [修復アクション](#remediation-actions)


## <a name="how-to-use-the-action-center"></a>アクション センターを使用する方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. 保留中のアクションを表示して承認 (または拒否) するには、**[保留中]** タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動応答アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. **[履歴]** タブを選択して、完了したアクションのリストを表示します。 

## <a name="remediation-actions"></a>修復アクション

Microsoft Defender for Businessには、いくつかの修復アクションが含まれます。 これらのアクションには、手動応答アクション、自動調査後のアクション、ライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションを示します。

| ソース  | Actions  |
|---------|---------|
| [自動調査](../defender-endpoint/automated-investigations.md)      | - ファイルの検疫 <br/>- レジストリ キーの削除 <br/>- プロセスの強制終了 <br/>- サービスの停止 <br/>- ドライバーの無効化 <br/>- スケジュールされたタスクの実行        |
| [手動応答アクション](../defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンの実行 <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターの追加       |
| [ライブ応答](../defender-endpoint/live-response.md)   | - フォレンジック データの収集 <br/>- ファイルの分析 <br/>- スクリプトの実行 <br/>- 不審なエンティティを分析のために Microsoft に送信 <br/>- ファイルの修復 <br/>- 脅威の積極的な追求         |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)