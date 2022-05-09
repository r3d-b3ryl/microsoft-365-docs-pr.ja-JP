---
title: 一括苦情レベルの値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用される一括苦情レベル (BCL) の値について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c50ca25a355ca142e36c67d03fad42c3aa461a2
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679876"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP の一括苦情レベル (BCL)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Online メールボックスがない場合、EOP は一括メーラーからの受信メッセージに一括苦情レベル (BCL) を割り当てます。 BCL は X ヘッダーのメッセージに追加され、メッセージをスパムとして識別するために使用される [スパム信頼レベル (SCL)](spam-confidence-levels.md) に似ています。 BCL が高いほど、一括メッセージが苦情を生成する可能性が高いことを示します (したがって、スパムである可能性が高くなります)。 Microsoft は、内部およびサード パーティの両方のソースを使用して、一括メールを識別し、適切な BCL を決定します。

バルク メーラーは、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。 適切な一括メーラーは、関連するコンテンツを含む目的のメッセージをサブスクライバーに送信します。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 一括メーラーからのメッセージは、一括メールまたは灰色のメールと呼ばれます。

 スパム フィルターは、BCL しきい値 (指定した既定値または値) に基づいてメッセージを **一括メール** としてマークし、メッセージに対して指定されたアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。 詳細については、「 [スパム対策ポリシーの構成](configure-your-spam-filter-policies.md) 」と「 [迷惑メールと一括メールの違いは何ですか?](what-s-the-difference-between-junk-email-and-bulk-email.md)

次の表では、BCL のしきい値について説明します。

|BCL|説明|
|:---:|---|
|0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7<sup>\*</sup>|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、大量の苦情を生成する一括送信者からのメッセージです。|

<sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。
