---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、管理者はスパム信頼レベル (SCL) がスパムとしてのメッセージの likeliness をどのように決定するかについて説明します。
ms.openlocfilehash: 9448b1fd99878dbb85bc8699afc0719bc62dd951
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035250"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Office 365 でのスパム信頼度 (SCL)

Microsoft 365 (exchange online またはスタンドアロンの exchange Online Protection (EOP) が Exchange Online メールボックスを使用しない) が受信メールメッセージを受信すると、メッセージはスパムフィルタリングを通過し、スパムスコアが割り当てられます。 このスコアは、X ヘッダー内のメッセージに追加される個々のスパム信頼レベル (SCL) にマップされます。 SCL が高いほど、メッセージがスパムである可能性が高いことを示します。 サービスは、SCL に基づいてメッセージに対してアクションを実行します。

SCL の意味と、メッセージに対して実行される既定のアクションについて、次の表で説明します。 スパムフィルター verdict に基づいてメッセージに対して実行できるアクションの詳細については、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

||||
|:---:|---|---|
|**SCL**|**定義**|**既定のアクション**|
|-1|メッセージは、スパムフィルター処理をスキップしました。 たとえば、メッセージが差出人セーフリストから送信された、または宛先セーフリストに送信された、または IP 許可一覧にある電子メールソースサーバーのメッセージである場合です。 詳細については、「[Office 365 での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。|受信者の受信トレイにメッセージを配信します。|
|0, 1|スパムフィルターは、メッセージがスパムではないことを確認しました。|受信者の受信トレイにメッセージを配信します。|
|5, 6|メッセージが**スパム**としてマークされたスパムフィルター|受信者の迷惑メール フォルダーにメッセージを配信します。|
|9 |スパムフィルターがメッセージを**高信頼スパム**としてマークしました|受信者の迷惑メール フォルダーにメッセージを配信します。|
|

SCL 2、3、4、7、および8は、スパムフィルター処理によって使用されていないことがわかります。

メールフロールール (トランスポートルールとも呼ばれます) を使用して、メッセージに SCL をスタンプすることができます。 メールフロールールを使用して SCL を設定する場合は、5または6の値によって**スパムに対するスパム**フィルター処理がトリガーされ、**精度の高いスパム**に対しては7、8、または9の値がスパムフィルター処理をトリガーします。 詳細については、「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。

SCL と同じように、バルク苦情レベル (BCL) は、不適切なバルクメール (_灰色のメール_) を特定します。 上位の BCL は、バルクメールメッセージが苦情を生み出している可能性が高いことを示します (したがって、スパムである可能性が高くなります)。 「スパム対策ポリシー」で、BCL のしきい値を構成します。 詳細については、「 [office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」、「 [office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」、および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。

||
|:-----|
|![LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png)の短いアイコン**を Office 365 に追加しますか?**         LinkedIn ラーニングによって提供される**Microsoft 365 管理者および IT プロフェッショナル**向けの無料のビデオコースを見つけることができます。|
