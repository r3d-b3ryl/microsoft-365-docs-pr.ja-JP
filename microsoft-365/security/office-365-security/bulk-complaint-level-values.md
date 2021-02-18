---
title: バルク苦情レベルの値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用される一括コンプライアンス レベル (BCL) の値について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289903"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP でのバルク苦情レベル (BCL)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はバルク メールラーからの受信メッセージに一括準拠レベル (BCL) を割り当てします。 BCL は X ヘッダー内のメッセージに追加され、メッセージをスパムとして識別するために使用される [SCL (Spam Confidence Level)](spam-confidence-levels.md) に似ています。 BCL が高いほど、バルク メッセージが苦情を発生する可能性が高くなります (したがって、スパムである可能性が高くなります)。 Microsoft は、内部ソースとサード パーティソースの両方を使用してバルク メールを識別し、適切な BCL を決定します。

バルク メールは、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。 優れたバルク メール担当者は、関連するコンテンツを含む必要なメッセージをサブスクライバーに送信します。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 バルク メールのメッセージは、バルク メールまたはグレー メールと呼ばれるものになります。

 スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージをバルク メールとしてマークし、メッセージに対して指定のアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。  詳細については、「スパム対策ポリシー [を構成](configure-your-spam-filter-policies.md) する」と「迷惑メールとバルク メールの違い [」を参照してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)

BCL のしきい値を次の表に示します。

****

|BCL|説明|
|:---:|---|
|0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7<sup>\*</sup>|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、多数の苦情を生成するバルク 送信者からのメッセージです。|
|

<sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。
