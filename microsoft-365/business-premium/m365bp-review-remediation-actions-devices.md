---
title: '[修復アクションの確認] Microsoft 365 Business Premium'
description: アクション センターで承認を待っている、または自動的に実行された修復を表示する方法を確認する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 160cef2ec7691fbc9debad809b20461a0d3efe23
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526638"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>[修復アクションの確認] Microsoft 365 Business Premium

脅威が検出されると、修復アクションが実行されます。 特定の脅威とセキュリティ設定の構成方法に応じて、修復アクションが自動的に実行される場合や、承認時にのみ実行される場合があります。 修復アクションの例としては、ファイルを検疫に送信する、プロセスの実行を停止する、スケジュールされたタスクを削除するなどの操作があります。 すべての修復アクションはアクション センターで追跡されます。[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="M365 のアクション センターのスクリーンショット。":::

**この記事では、次の情報について説明します**。

- [アクション センターの使い方](#how-to-use-your-action-center)

- [修復アクションの種類](#types-of-remediation-actions)


## <a name="how-to-use-your-action-center"></a>アクション センターの使い方

1. ポータル () にMicrosoft 365 Defenderし[https://security.microsoft.com](https://security.microsoft.com)、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. 保留中の **アクションを表示** および承認 (または拒否) するには、[保留中] タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動対応アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. [履歴] **タブを** 選択して、完了したアクションの一覧を表示します。 

## <a name="types-of-remediation-actions"></a>修復アクションの種類

サブスクリプションには、検出された脅威に対するさまざまな種類の修復アクションが含まれています。 これらのアクションには、手動応答アクション、自動調査後のアクション、およびライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションの一覧を示します。

| ソース  | Actions  |
|---------|---------|
| [自動化された調査](../security/defender-endpoint/automated-investigations.md)      | - ファイルを検疫する <br/>- レジストリ キーを削除する <br/>- プロセスを終了する <br/>- サービスを停止する <br/>- ドライバーを無効にする <br/>- スケジュールされたタスクを削除する        |
| [手動応答アクション](../security/defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンを実行する <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターを追加する       |
| [ライブ応答](../security/defender-endpoint/live-response.md)   | - forensic データを収集する <br/>- ファイルを分析する <br/>- スクリプトを実行する <br/>- 分析のために疑わしいエンティティを Microsoft に送信する <br/>- ファイルを修復する <br/>- 脅威を積極的に探す         |
