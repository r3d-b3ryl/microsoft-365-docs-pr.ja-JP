---
title: Microsoft Defender for Business の修復アクションを確認する (プレビュー)
description: アクション センターで承認を待っている、または自動的に実行された修復を表示する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 0b71088421b71f117eff4521eee1d8f5ef87971a
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507382"
---
# <a name="review-remediation-actions-in-the-action-center"></a>アクション センターで修復アクションを確認する

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法に応じて、修復アクションが自動的に実行される場合や、承認時にのみ実行される場合があります。 修復アクションの例としては、ファイルを検疫に送信する、プロセスの実行を停止する、スケジュールされたタスクを削除するなどの操作があります。 すべての修復アクションは、アクション センターで追跡されます。

:::image type="content" source="../../media/defender-business/mdb-actioncenter.png" alt-text="アクション センターのスクリーンショット":::

**この記事では、以下について説明します**。

- [アクション センターの使い方](#how-to-use-the-action-center)
- [修復アクション](#remediation-actions)

## <a name="how-to-use-the-action-center"></a>アクション センターの使い方

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. 保留中の **アクションを表示** および承認 (または拒否) するには、[保留中] タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動対応アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. [履歴] **タブを** 選択して、完了したアクションの一覧を表示します。 

## <a name="remediation-actions"></a>修復アクション

Microsoft Defender for Business (プレビュー) には、いくつかの修復アクションが含まれています。 これらのアクションには、手動応答アクション、自動調査後のアクション、およびライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションの一覧を示します。

| ソース  | Actions  |
|---------|---------|
| [自動化された調査](../defender-endpoint/automated-investigations.md)      | - ファイルを検疫する <br/>- レジストリ キーを削除する <br/>- プロセスを終了する <br/>- サービスを停止する <br/>- ドライバーを無効にする <br/>- スケジュールされたタスクを削除する        |
| [手動応答アクション](../defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンを実行する <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターを追加する       |
| [ライブ応答](../defender-endpoint/live-response.md)   | - forensic データを収集する <br/>- ファイルを分析する <br/>- スクリプトを実行する <br/>- 分析のために疑わしいエンティティを Microsoft に送信する <br/>- ファイルを修復する <br/>- 脅威を積極的に探す         |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [Microsoft Defender for Business でデバイスを管理する (プレビュー)](mdb-manage-devices.md)