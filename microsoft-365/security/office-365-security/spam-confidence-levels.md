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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のメッセージに適用されたスパム信頼レベル (SCL) について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7783eb0655a6e3b0457a45057b920c87388e4c05
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682925"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP のスパム信頼度レベル (SCL)

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Onlineメールボックスがない場合、受信メッセージは EOP でスパム フィルター処理を通過し、スパム スコアが割り当てられます。 このスコアは、X ヘッダーのメッセージに追加される個々のスパム信頼レベル (SCL) にマップされます。 SCL が高いほど、メッセージがスパムである可能性が高くなります。 EOP は、SCL に基づいてメッセージに対してアクションを実行します。

SCL の意味と、メッセージに対して実行される既定のアクションを次の表に示します。 スパム フィルターの判定に基づいてメッセージに対して実行できるアクションの詳細については、「 [EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

|SCL|定義|既定のアクション|
|:---:|---|---|
|-1|メッセージがスパム フィルター処理をスキップしました。 たとえば、メッセージは、差出人セーフ リストからのメッセージ、安全な受信者に送信されたメッセージ、または IP 許可一覧の電子メール ソース サーバーからのメッセージです。 詳細については、「[EOP での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。|受信者の受信トレイにメッセージを配信します。|
|0, 1|メッセージがスパムでないと判断されたスパム フィルター処理。|受信者の受信トレイにメッセージを配信します。|
|5, 6|メッセージをスパムとしてマークした **スパム** フィルター処理|受信者の迷惑メール フォルダーにメッセージを配信します。|
|9 |メッセージが **高信頼** スパムとしてマークされたスパム フィルター処理|受信者の迷惑メール フォルダーにメッセージを配信します。|

SCL 2、3、4、7、8 はスパム フィルターで使用されないことに気付きます。

メール フロー ルール (トランスポート ルールとも呼ばれます) を使用して、メッセージに SCL をスタンプできます。 メール フロー ルールを使用して SCL を設定する場合、値 5 または 6 は **Spam** のスパム フィルター 処理をトリガーし、値 7、8、または 9 は **高信頼スパム** のスパム フィルター処理をトリガーします。 詳細については、「[メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)」を参照してください。

SCL と同様に、一括苦情レベル (BCL) は、不適切な一括メール ( _灰色のメール_ とも呼ばれます) を識別します。 BCL が高いほど、バルク メール メッセージが好ましくない内容である可能性が高い (したがって、スパムである可能性が高い) ことを示します。 スパム対策ポリシーで BCL しきい値を構成します。 詳細については、「[EOP でのスパム対策ポリシーの構成、EOP での](configure-your-spam-filter-policies.md)[一括苦情レベル (BCL)」](bulk-complaint-level-values.md)、迷惑[メールと一括メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)については、「」を参照してください。

****

LinkedIn ラーニングのショート アイコンです。Office 365 を初めてお使いの場合は         、LinkedIn ラーニングによって提供された Office 365 管理者および IT プロフェッショナル向けの無料のビデオコースをご覧ください。 **Microsoft 365の新機能** LinkedIn ラーニングが提供する **、Microsoft 365管理者と IT 担当者** 向けの無料のビデオ コースを見つける。
