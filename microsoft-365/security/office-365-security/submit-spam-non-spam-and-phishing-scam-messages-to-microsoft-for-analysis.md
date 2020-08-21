---
title: 分析用に Microsoft に手動でメッセージを送信する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理者とエンド ユーザーは、Microsoft への分析を行う必要なメッセージ (不適切なメールや不適切なメールの受信のマーク) を確認できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94f00f8399164a84d2cb9dae0c4c416b73dfb0dc
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827811"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>分析用に Microsoft に手動でメッセージを送信する

> [!NOTE]
> Exchange Online メールボックスを持つ組織内の管理者は、セキュリティ/コンプライアンス センターの提出ポータルを&ことをお勧めします。 詳細については、「管理者送信 [を使用して、スパム、フィッシング、URL、ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

組織のユーザーが受信トレイで迷惑メール メッセージ (スパム) やフィッシング メッセージを受信したり、当該電子メール メッセージが迷惑メールとしてマークされたため受信されなけない場合に、イライラする可能性があります。 迷惑メール フィルターは、いつも調整していくために、より高い結果が生じないでいい場合も当てはまりはありません。

組織とユーザーは、誤検知 (良いメールが悪いメール)、誤検知 (不正なメールの許可)、分析用に Microsoft にフィッシング メールを送信することで、このプロセスをサポートできます。

> [!NOTE]
> 弊回の送出量が多いため、分析を受けたすべての要求に回答できない場合があります。

## <a name="submit-false-negatives-to-microsoft"></a>Microsoft に偽の漏れを送信する

> [!TIP]
> 次の手順を使用して誤検知を報告する代わりに、Outlook および Web 上の Outlook (Outlook Web App) のユーザーは Microsoft Outlook 用の報告メッセージ アドインを使用できます。 このツールをインストールして使用する方法については、「レポート [メッセージ アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。

スパム フィルター処理を通過したメッセージを受信し、スパムまたはフィッシングとして識別されるメッセージを受信した場合、そのメッセージを Microsoft スパム分析チームおよび Microsoft Phishing Analysis チームに送信できます。 アナリストはメッセージを確認し、分類条件に一致する場合はサービス全体のフィルターに追加します。

1. 空の電子メール メッセージを作成し、次の受信者のいずれかを設定します。

   - **迷惑メール**: `junk@office365.microsoft.com`

   - **フィッシング**: `phish@office365.microsoft.com`

2. 迷惑メールまたはフィッシング メール メッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、迷惑メールまたはフィッシングのメッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしてはいけません (メッセージのヘッダーを検かけ出すには、元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージ内の複数のメッセージを添付することができます。 すべてのメッセージの種類が同一であること (フィッシング メッセージか迷惑メール メッセージのどちらか) を確認します。
   >
   > - 新しいメッセージの本文は空のままにします。
   >
   > - 添付されたメッセージには, .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式のいずれかを使用します。

3. 完了したら、[送信] を **クリックします**。

> [!TIP]
> 管理者は、スパムとして識別されていない特定のメッセージをブロックするためのいくつかの方法を利用できます。 詳細については、「EOP でブロック [する送信者リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> 以下の手順を使用して誤検知を報告する代わりに、Outlook や Outlook on the web のユーザーは Microsoft Outlook のメッセージ報告アドインを使用できます。 このツールをインストールして使用する方法については、「レポート [メッセージ アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。

メッセージが誤ってスパムとして識別された場合は、Microsoft スパム分析チームに送信することができます。 アナリストはメッセージを評価し、このメッセージが許可される場合はサービス全体のフィルターを調整できます。

1. 受信者として新しい空のメール メッセージ `not_junk@office365.microsoft.com` を作成します。

2. 識別されていないメッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、識別されていないメッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けたり、メッセージを転送したりしてはいけません (メッセージのヘッダーを検かけ出すには、元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージ内の複数のメッセージを添付することができます。 すべてのメッセージの種類が同一であること (フィッシング メッセージか迷惑メール メッセージのどちらか) を確認します。
   >
   > - 新しいメッセージの本文は空のままにします。
   >
   > - 添付されたメッセージには, .msg (既定の Outlook 形式) または .eml (既定の Outlook on the Web 形式) 形式のいずれかを使用します。

3. 完了したら、[送信] を **クリックします**。

> [!TIP]
> 管理者は、特定のメッセージにスパム フィルターをスキップするさまざまな方法を用いることができます。 詳細については、「EOP で差 [出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する

手順については、「メール フロー [ルールを使用して、ユーザーが Microsoft に報告する内容を参照する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
