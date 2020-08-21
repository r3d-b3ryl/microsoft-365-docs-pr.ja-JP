---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のメッセージに適用される Spam Confidence Level (SCL) について学習できます。
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827399"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP の Spam Confidence Level (SCL)

Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信メッセージは EOP のスパム フィルタリングを通過し、スパム スコアが割り当てられます。 そのスコアは、X ヘッダー内のメッセージに追加される個々の Spam Confidence Level (SCL) にマップされます。 SCL が高いと、メッセージがスパムである可能性が高いことを示します。 EOP は SCL に基づいてメッセージに対してアクションを実行します。

メッセージに対して実行される SCL の意味と既定のアクションについて、以下の表で説明します。 スパム フィルターの確認に基づいてメッセージに対して実行できるアクションの詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

****

|SCL|定義|既定のアクション|
|:---:|---|---|
|-1|メッセージはスパム フィルター処理をスキップしました。 たとえば、メッセージが差出人セーフ リストから差出人セーフに送信されたか、または IP 許可一覧のメール送信元サーバーからのメッセージである場合です。 詳細については、「EOP で差出 [人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。|受信者の受信トレイにメッセージを配信します。|
|0, 1|スパム フィルターが、メッセージがスパムでないと判断しました。|受信者の受信トレイにメッセージを配信します。|
|5, 6|スパム フィルターがメッセージをスパムとしてマーク **した**|受信者の迷惑メール フォルダーにメッセージを配信します。|
|9 |スパム フィルター処理によってメッセージが **信頼度が高いスパムとしてマークされた**|受信者の迷惑メール フォルダーにメッセージを配信します。|
|

SCL 2、3、4、7、8 はスパム フィルター処理により使用されていない場合に確認できます。

メール フロー ルール (別名トランスポート ルール) は、メッセージに SCL をスタンプするために使用できます。 メール フロー ルールを使用して SCL を設定する場合、値 5 または 6 は **Spam**に対してスパム フィルター処理をトリガーし、7、8、9 のいずれかの値によって高信頼スパムに対するスパム フィルター **処理がトリガーされます**。 詳細については、「メール フロー [ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

SCL と同様に、バルク アル クアマーク レベル (BCL) は、不正なバルク メール (グレー メール _とも呼ばれる) を識別します_。 BCL が高い場合、バルク メール メッセージが不合を不用意にする可能性が高いことを示します (したがって、スパムである可能性が高くなります)。 スパム対策ポリシーで BCL しきい値を構成します。 詳細については[、「EOP で迷惑メール対策ポリシーを構成する」、「EOP でバル](configure-your-spam-filter-policies.md)ク コントライド レベル[(BCL)」を構成して](bulk-complaint-level-values.md)[、迷惑メール](what-s-the-difference-between-junk-email-and-bulk-email.md)とバルク メールの違いを確認してください。

|<!-- -->|
|---|
|![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 の小さいアイコン** LinkedIn Learning が提供する **Microsoft 365**管理者および IT プロダッシー向けの無料のビデオ コースをご覧ください。|
