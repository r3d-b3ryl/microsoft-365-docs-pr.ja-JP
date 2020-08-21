---
title: バルク コンプト レベル値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用される一括コンプライアンス レベル (BCL) 値について学習できます。
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827435"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP のバルク コンプト レベル (BCL)

Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP はバルク メール サーバーからの受信メッセージに対してバルクに対応するレベル (BCL) を割り当てています。 BCL は X-ヘッダーのメッセージに追加され、メッセージをスパムとして [識別するために使用される Spam Confidence Level (SCL)](spam-confidence-levels.md) に似ています。 BCL が高い場合、バルク メッセージでは不合意がある (したがって、スパムである可能性が高い) ことを示します。 Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。

バルク メール ツールでは、送信パターン、コンテンツ作成、受信者取得方法が異なる場合があります。 バルク メールを送信する優れた大会議を送付者は、関連するコンテンツを含む必要なメッセージをユーザーのサブスクライバーに送信します。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 バルク メール システムからのメッセージは、バルク メールまたは灰色メールと呼ばれます。

 スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいて、メッセージに対してバルク メールのマークを付け、指定されたアクションをメッセージに対して実行します (既定の操作では、メッセージは受信者の迷惑メール フォルダーに配信されます)。 **Bulk email** 詳細については、「スパム [対策ポリシーを構成する」、](configure-your-spam-filter-policies.md) および [迷惑メールとバルク メールの違いを確認する](what-s-the-difference-between-junk-email-and-bulk-email.md)

次の表で、BCL しきい値について説明します。

****

|BCL|説明|
|:---:|---|
|0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、探しの結果が大きいバルク送信者からのものです。|
|
