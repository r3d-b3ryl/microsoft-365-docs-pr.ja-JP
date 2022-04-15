---
title: Microsoft Defender for Businessで修復アクションを確認する
description: 自動的に実行された修復、またはアクション センターで承認を待っている修復を表示する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 15a64491f6e97137d1e919aa126d4bf134c47999
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862216"
---
# <a name="review-remediation-actions-in-the-action-center"></a>アクション センターで修復アクションを確認する

> [!NOTE]
> Microsoft Defender for Businessが[Microsoft 365 Business Premium](../../business-premium/index.md)に含まれるようになりました。 

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法によっては、修復アクションが自動的に実行されるか、承認時にのみ実行される場合があります。 修復アクションの例としては、ファイルの検疫への送信、プロセスの実行の停止、スケジュールされたタスクの削除などがあります。 すべての修復アクションは、アクション センターで追跡されます。

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="アクション センターのスクリーンショット":::

**この記事では、次について説明します**。

- [アクション センターを使用する方法](#how-to-use-the-action-center)
- [修復アクション](#remediation-actions)

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="how-to-use-the-action-center"></a>アクション センターを使用する方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. **保留中** のアクションを表示および承認 (または拒否) するには、[保留中] タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動応答アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. [ **履歴** ] タブを選択すると、完了したアクションの一覧が表示されます。 

## <a name="remediation-actions"></a>修復アクション

Microsoft Defender for Businessには、いくつかの修復アクションが含まれます。 これらのアクションには、手動の応答アクション、自動調査後のアクション、ライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションを示します。

| Source  | 操作  |
|---------|---------|
| [自動化された調査](../defender-endpoint/automated-investigations.md)      | - ファイルを検疫する <br/>- レジストリ キーを削除する <br/>- プロセスを強制終了する <br/>- サービスを停止する <br/>- ドライバーを無効にする <br/>- スケジュールされたタスクを削除する        |
| [手動応答アクション](../defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンを実行する <br/>- デバイスを分離する <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターを追加する       |
| [ライブ応答](../defender-endpoint/live-response.md)   | - フォレンジック データを収集する <br/>- ファイルを分析する <br/>- スクリプトを実行する <br/>- 分析のために疑わしいエンティティを Microsoft に送信する <br/>- ファイルを修復する <br/>- プロアクティブに脅威を探す         |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [Microsoft Defender for Businessでデバイスを管理する](mdb-manage-devices.md)