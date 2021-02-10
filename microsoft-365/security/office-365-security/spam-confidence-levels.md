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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のメッセージに適用される Spam Confidence Level (SCL) について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167157"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP の Spam Confidence Level (SCL)

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、受信メッセージは EOP のスパム フィルターを通過し、スパム スコアが割り当てられます。 このスコアは、X ヘッダー内のメッセージに追加される個々の Spam Confidence Level (SCL) にマップされます。 SCL が高いほど、メッセージはスパムである可能性が高くなります。 EOP は SCL に基づいてメッセージに対してアクションを実行します。

SCL の意味と、メッセージに対して実行される既定のアクションを次の表に示します。 スパム フィルターの条件に基づいてメッセージに対して実行できるアクションの詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

****

|SCL|定義|既定のアクション|
|:---:|---|---|
|-1|メッセージはスパム フィルター処理をスキップしました。 たとえば、メッセージが差出人セーフ リストから送信されたメッセージ、安全な受信者に送信されたメッセージ、または IP 許可一覧の電子メール 送信元サーバーから送信されたメッセージなどです。 詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。|受信者の受信トレイにメッセージを配信します。|
|0, 1|スパム フィルターによって、メッセージがスパムではないと判断された。|受信者の受信トレイにメッセージを配信します。|
|5, 6|スパム フィルターによってメッセージがスパムとしてマーク **された**|受信者の迷惑メール フォルダーにメッセージを配信します。|
|9 |スパム フィルターがメッセージを信頼度の高いスパム **としてマークしました**|受信者の迷惑メール フォルダーにメッセージを配信します。|
|

SCL 2、3、4、7、および 8 はスパム フィルタリングで使用されません。

メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、メッセージに SCL をスタンプできます。 メール フロー ルールを使用して SCL を設定する場合、値 5 または 6 は **スパム** のスパム フィルター処理をトリガーし、値 7、8、または 9 は信頼度の高いスパムに対するスパム フィルター処理をトリガー **します。** 詳細については、「メール フロー ルール [を使用して、メッセージの Spam Confidence Level (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。

SCL と同様に、バルク苦情レベル (BCL) は、悪いバルク メール (グレー メールとも呼ばれる) _を識別します_。 BCL が高いほど、バルク メール メッセージが好ましくない内容である可能性が高い (したがって、スパムである可能性が高い) ことを示します。 BCL しきい値は、スパム対策ポリシーで構成します。 詳細については[、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」、EOP のバルク苦情レベル[(BCL)、](bulk-complaint-level-values.md)迷惑メールとバルク メールの違いを参照[してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![LinkedIn Learning の ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 の** 新機能の短いアイコン LinkedIn Learning によって **提供される、Microsoft 365** 管理者と IT プロ向け無料のビデオ コースをご覧ください。
