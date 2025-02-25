---
title: Microsoft 365 Business Premium の修復アクションを確認する
description: アクション センターで自動的に行われたか、承認待ちの修復を表示する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 847095a4dcfb1905cf3c95b9cbf393298b1c7c3d
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894495"
---
# <a name="review-remediation-actions-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の修復アクションを確認する

セキュリティ違反が検出されましたが、どうしますか? その性質によって異なります。

修復アクションの例としては、検疫へのファイルの送信、プロセスの実行の停止、スケジュールされたタスクの完全な削除などがあります。 すべての修復アクションは、[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) にあるアクション センターで追跡されます。

:::image type="content" source="../media/defender-business/mdb-actioncenter.png" alt-text="M365 のアクション センターのスクリーンショット。":::

**この記事では、以下について説明します。**

- [アクション センターを使用する方法](#how-to-use-your-action-center)。
- [修復アクションの種類](#types-of-remediation-actions)。


## <a name="how-to-use-your-action-center"></a>アクション センターを使用する方法

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. 保留中のアクションを表示して承認 (または拒否) するには、**[保留中]** タブを選択します。 このようなアクションは、ウイルス対策/マルウェア対策保護、自動調査、手動応答アクティビティ、またはライブ応答セッションから発生する可能性があります。

4. **[履歴]** タブを選択して、完了したアクションのリストを表示します。

## <a name="types-of-remediation-actions"></a>修復アクションの種類

サブスクリプションには、検出された脅威に対するいくつかの異なる種類の修復アクションが含まれています。 これらのアクションには、手動応答アクション、自動調査後のアクション、ライブ応答アクションが含まれます。

次の表に、使用可能な修復アクションを示します。

| ソース  | Actions  |
|---------|---------|
| [自動調査](../security/defender-endpoint/automated-investigations.md)      | - ファイルの検疫 <br/>- レジストリ キーの削除 <br/>- プロセスの強制終了 <br/>- サービスの停止 <br/>- ドライバーの無効化 <br/>- スケジュールされたタスクの実行        |
| [手動応答アクション](../security/defender-endpoint/respond-machine-alerts.md)   | - ウイルス対策スキャンの実行 <br/>- デバイスの分離 <br/>- 停止と検疫 <br/>- ファイルをブロックまたは許可するインジケーターの追加       |
| [ライブ応答](../security/defender-endpoint/live-response.md)   | - フォレンジック データの収集 <br/>- ファイルの分析 <br/>- スクリプトの実行 <br/>- 不審なエンティティを分析のために Microsoft に送信 <br/>- ファイルの修復 <br/>- 脅威の積極的な追求         |
