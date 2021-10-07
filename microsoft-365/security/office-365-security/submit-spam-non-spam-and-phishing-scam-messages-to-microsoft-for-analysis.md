---
title: 分析のために、メッセージを手動で Microsoft に送信する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 管理者とエンド ユーザーは、分析のために Microsoft にメッセージ (悪いメールまたは悪いメールとしてマークされた良いメール) を電子メールで送信する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 42c384966b5ba5b1f7e52e26212f60c446d9bc58
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180665"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>分析のために、メッセージを手動で Microsoft に送信する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 組織の管理者がメールボックスを使用している場合Exchange Onlineポータルの [申請] ページを使用することをおMicrosoft 365 Defenderします。 詳細については、「Submits ポータルを使用して疑わしいスパム、フィッシング、URL、ファイルを Microsoft に提出する」 [を参照してください](admin-submission.md)。

組織内のユーザーが受信トレイで迷惑メール (スパム) またはフィッシング メッセージを受信した場合や、迷惑メールとしてマークされた正当な電子メール メッセージを受信しない場合は、イライラする可能性があります。 スパム フィルターの精度を高め、常に微調整を行っています。

ユーザーとユーザーは、誤検知 (悪いマークが付いた良いメール)、誤検知 (悪いメールが許可されている)、フィッシング メッセージを分析のために Microsoft に送信することで、このプロセスを支援できます。

> [!NOTE]
> 送信が多いので、分析のすべての要求に回答できない場合があります。

## <a name="submit-false-negatives-to-microsoft"></a>False negatives を Microsoft に送信する

> [!TIP]
> Outlook と Outlook on the web (以前は Outlook Web App と呼ばれる) のユーザーは、次の手順を使用して誤検知を報告する代わりに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用できます。 これらのツールをインストールして使用する方法の詳細については、「[](enable-the-report-message-add-in.md)レポート メッセージ アドインを有効にする」および「レポート フィッシング アドインを有効にする」[を参照してください](enable-the-report-phish-add-in.md)。

スパムまたはフィッシングとして識別されている必要があるスパム フィルターを通過したメッセージを受信した場合は、必要に応じて Microsoft Spam Analysis チームと Microsoft フィッシング分析チームにメッセージを送信できます。 アナリストはメッセージを確認し、分類条件を満たす場合はサービス全体のフィルターに追加します。

1. 次のいずれかの受信者を含む、新しい空白の電子メール メッセージを作成します。

   - **迷惑** メール : `junk@office365.microsoft.com`
   - **フィッシング**: `phish@office365.microsoft.com`

2. 迷惑メールまたはフィッシング メッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、迷惑メールまたはフィッシング メッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けるか、メッセージを転送したりしません (メッセージ ヘッダーを調べたい場合は、元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージに複数のメッセージを添付できます。 すべてのメッセージがフィッシング メッセージまたは迷惑メール メッセージのいずれかと同じ種類に設定されている必要があります。
   > - 新しいメッセージの本文は空のままにします。
   > - 添付メッセージには、.msg (既定Outlook形式) または .eml (Web 形式の既定のOutlook) 形式を使用します。

3. 完了したら、[送信] を **クリックします**。

> [!TIP]
> 管理者は、スパムと誤認されている特定のメッセージをブロックするさまざまな方法があります。 詳細については [、「EOP で受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="submit-false-positives-to-microsoft"></a>Microsoft に誤検知を送信する

> [!TIP]
> Outlook および Outlook on the web のユーザーは、次の手順を使用して誤検知を報告する代わりに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用できます。 これらのツールをインストールして使用する方法の詳細については、「[](enable-the-report-message-add-in.md)レポート メッセージ アドインを有効にする」および「レポート フィッシング アドインを有効にする」[を参照してください](enable-the-report-phish-add-in.md)。

メッセージがスパムとして誤って識別された場合は、Microsoft スパム分析チームにメッセージを送信できます。 アナリストはメッセージを評価し、(分析の結果に応じて) サービス全体のフィルターを調整してメッセージを通過できます。

1. 受信者として新しい空白の電子メール `not_junk@office365.microsoft.com` メッセージを作成します。

2. 誤認されたメッセージを新しいメッセージにドラッグ アンド ドロップします。 これにより、誤認されたメッセージが新しいメッセージの添付ファイルとして保存されます。 メッセージの内容をコピーして貼り付けるか、メッセージを転送したりしません (メッセージ ヘッダーを調べたい場合は、元のメッセージが必要です)。

   > [!NOTE]
   >
   > - 新しいメッセージに複数のメッセージを添付できます。 すべてのメッセージがフィッシング メッセージまたは迷惑メール メッセージのいずれかと同じ種類に設定されている必要があります。
   > - 新しいメッセージの本文は空のままにします。
   > - 添付メッセージには、.msg (既定Outlook形式) または .eml (Web 形式の既定のOutlook) 形式を使用します。

3. 完了したら、[送信] を **クリックします**。

> [!TIP]
> 管理者は、特定のメッセージがスパム フィルター処理をスキップできるさまざまな方法があります。 詳細については [、「EOP で差出人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>申請から Microsoft へのデータはどこに保存されますか?

データは、北米のデータ センター Office 365コンプライアンス境界に存在します。 データは、フィルターの有効性を向上させるため、エンジニアリング チームのアナリストによってレビューされます。

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Microsoft に報告されたメッセージのコピーを受信するメール フロー ルールを作成する

手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
