---
title: Microsoft Defender for Business の修復アクションを確認する
description: アクション センターで承認を待っている、または自動的に実行された修復を表示する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 5550892a1d16ff8872d2a634f8a7560932cef6e0
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375679"
---
# <a name="review-remediation-actions-in-the-action-center"></a>アクション センターで修復アクションを確認する

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

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

Microsoft Defender for Business には、いくつかの修復アクションが含まれています。 これらのアクションには、手動応答アクション、自動調査後のアクション、およびライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションの一覧を示します。

| ソース  | Actions  |
|---------|---------|
| [自動化された調査](../defender-endpoint/automated-investigations.md)      | - ファイルを検疫する <br/>- レジストリ キーを削除する <br/>- プロセスを終了する <br/>- サービスを停止する <br/>- ドライバーを無効にする <br/>- スケジュールされたタスクを削除する        |
| [手動応答アクション](../defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンを実行する <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターを追加する       |
| [ライブ応答](../defender-endpoint/live-response.md)   | - forensic データを収集する <br/>- ファイルを分析する <br/>- スクリプトを実行する <br/>- 分析のために疑わしいエンティティを Microsoft に送信する <br/>- ファイルを修復する <br/>- 脅威を積極的に探す         |

## <a name="next-steps"></a>次の手順

- [Microsoft Defender for Business での脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [Microsoft Defender for Business でデバイスを管理する](mdb-manage-devices.md)