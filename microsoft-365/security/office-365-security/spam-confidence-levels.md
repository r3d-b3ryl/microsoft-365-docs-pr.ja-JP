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
description: 管理者は、電子メール (EOP) 内のメッセージに適用されるスパム信頼度 (SCL) Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7783eb0655a6e3b0457a45057b920c87388e4c05
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63682925"
---
# <a name="spam-confidence-level-scl-in-eop"></a>EOP のスパム信頼レベル (SCL)

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、受信メッセージは EOP のスパム フィルターを通過し、スパム スコアが割り当てられます。 このスコアは、X ヘッダー内のメッセージに追加される個々のスパム信頼レベル (SCL) にマップされます。 SCL が高いほど、メッセージがスパムである可能性が高くなります。 EOP は、SCL に基づいてメッセージに対してアクションを実行します。

次の表に、SCL の意味とメッセージに対して実行される既定のアクションについて説明します。 スパム フィルターの評決に基づいてメッセージに対して実行できるアクションの詳細については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。

|SCL|定義|既定のアクション|
|:---:|---|---|
|-1|メッセージはスパム フィルター処理をスキップしました。 たとえば、メッセージは差出人セーフ リストからのメッセージ、安全な受信者への送信、または IP 許可一覧の電子メール ソース サーバーからのメッセージです。 詳細については、「[EOP での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。|受信者の受信トレイにメッセージを配信します。|
|0, 1|スパム フィルターは、メッセージがスパムではないと判断しました。|受信者の受信トレイにメッセージを配信します。|
|5, 6|スパム フィルターでメッセージがスパムとしてマーク **された**|受信者の迷惑メール フォルダーにメッセージを配信します。|
|9 |スパム フィルターでメッセージが高信頼スパム **としてマークされた**|受信者の迷惑メール フォルダーにメッセージを配信します。|

SCL 2、3、4、7、8 はスパム フィルター処理では使用されません。

メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、メッセージに SCL をスタンプできます。 メール フロー ルールを使用して SCL を設定すると、値 5 または 6 が Spam のスパム フィルター 処理をトリガーし、値 7、8、または 9 が信頼度の高いスパムのスパム フィルター 処理をトリガーします。 詳細については、「[メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)」を参照してください。

SCL と同様に、バルク 苦情レベル (BCL) は、不良バルク メール (グレー メールとも呼ばれる) _を識別します_。 BCL が高いほど、バルク メール メッセージが好ましくない内容である可能性が高い (したがって、スパムである可能性が高い) ことを示します。 スパム対策ポリシーで BCL しきい値を構成します。 詳細については、「EOP でスパム対策ポリシーを構成する」、[EOP](configure-your-spam-filter-policies.md) のバルク 苦情レベル [(BCL)](bulk-complaint-level-values.md)、迷惑メールと[](what-s-the-difference-between-junk-email-and-bulk-email.md)バルク メールの違いを参照してください。

****

LinkedIn ラーニングのショート アイコンです。Office 365 を初めてお使いの場合は         、LinkedIn ラーニングによって提供された Office 365 管理者および IT プロフェッショナル向けの無料のビデオコースをご覧ください。 **新しいMicrosoft 365?** LinkedIn Microsoft 365によって提供される、管理者と **IT** プロ向け無料のビデオ コースラーニング。
