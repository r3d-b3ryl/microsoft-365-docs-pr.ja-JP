---
title: 分析のためにメッセージを Microsoft に手動で送信する
f1.keywords:
- NOCSH
ms.author: siosulli
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
description: 管理者とエンド ユーザーは、分析のためにメッセージ (悪いメールまたは悪いメールとしてマークされた良いメールが許可されている) を Microsoft に電子メールで送信する方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe8e3c5ed44c7578764ed0bf19408f4db16e3740
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751561"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>分析のためにメッセージを Microsoft に手動で送信する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。 詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

組織内のユーザーが受信トレイで迷惑メール メッセージ (スパム) またはフィッシング メッセージを受信した場合や、正当な電子メール メッセージが迷惑メールとしてマークされたため受信しない場合は、不満が生じます。 スパム フィルターをより正確に調整するために、弊社では常に微調整を行っています。

お客様とユーザーは、誤検知 (良いメールが悪いとマークされている)、偽陰性 (不正メールの許可) メッセージ、フィッシング メッセージを分析のために Microsoft に送信することで、このプロセスを支援できます。

> [!NOTE]
> 受信する提出の量が多いので、分析要求の一部に回答できない場合があります。

## <a name="submit-false-negatives-to-microsoft"></a>偽陰性を Microsoft に提出する

> [!TIP]
> 次の手順を使用して検出検出を報告する代わりに、Outlook および Web 上の Outlook (旧 Outlook Web App) のユーザーは、Microsoft Outlook 用のレポート メッセージ アドインを使用できます。 このツールをインストールして使用する方法については、「レポート メッセージ アドインを有効にする」 [を参照してください](enable-the-report-message-add-in.md)。

スパム フィルターを通過してスパムまたはフィッシングとして識別されるメッセージを受信した場合は、必要に応じて Microsoft スパム分析チームと Microsoft Phishing Analysis チームにメッセージを送信できます。 アナリストはメッセージを確認し、分類条件を満たす場合はサービス全体のフィルターに追加します。

1. 次のいずれかの受信者を含む新しい空の電子メール メッセージを作成します。

   - **迷惑メール**: `junk@office365.microsoft.com`

   - **フィッシング :**`phish@office365.microsoft.com`

2. 迷惑メールまたはフィッシングメッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、迷惑メールメッセージまたはフィッシング メッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するには元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージに複数のメッセージを添付できます。 すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。
   >
   > - 新しいメッセージの本文は空のままにします。
   >
   > - 添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Web 上の Outlook 形式) 形式を使用します。

3. 完了したら、[送信] をクリック **します**。

> [!TIP]
> 管理者は、スパムとして誤って特定されている特定のメッセージをブロックするさまざまな方法があります。 詳細については [、「EOP で受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>誤検知を Microsoft に送信する

> [!TIP]
> Outlook および Outlook on the web のユーザーは、次の手順を使用して誤検知を報告する代わりに、Microsoft Outlook のメッセージ報告アドインを使用できます。 このツールをインストールして使用する方法については、「レポート メッセージ アドインを有効にする」 [を参照してください](enable-the-report-message-add-in.md)。

メッセージが誤ってスパムとして識別された場合は、そのメッセージを Microsoft スパム分析チームに送信できます。 アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整してメッセージを許可できます。

1. 受信者として新しい空の電子メール `not_junk@office365.microsoft.com` メッセージを作成します。

2. 誤って特定されたメッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、誤って特定されたメッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付け、メッセージを転送したりしません (メッセージ ヘッダーを検査するために元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージに複数のメッセージを添付できます。 すべてのメッセージがフィッシング メッセージと迷惑メール メッセージの種類が同じことを確認します。
   >
   > - 新しいメッセージの本文は空のままにします。
   >
   > - 添付メッセージに .msg (既定の Outlook 形式) または .eml (既定の Web 上の Outlook 形式) 形式を使用します。

3. 完了したら、[送信] をクリック **します**。

> [!TIP]
> 管理者は、特定のメッセージがスパム フィルター処理をスキップできるさまざまな方法があります。 詳細については [、「EOP で差出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Microsoft への提出からのデータはどこに保存されますか?

データは、北米のデータ センター Office 365 コンプライアンス境界に存在します。 データは、フィルターの有効性を向上させるために、エンジニアリング チームのアナリストによってレビューされます。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する

手順については、「メール フロー ルール [を使用して、ユーザーが Microsoft に報告している情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
