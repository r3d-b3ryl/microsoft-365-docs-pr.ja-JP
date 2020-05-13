---
title: バルク苦情レベルの値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用されるバルクコンプライアンスレベル (BCL) の値について説明しています。
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209609"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP でのバルク苦情レベル (BCL)

Exchange online メールボックスを使用しない Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織内のメールボックスを持つ Microsoft 365 組織では、EOP はバルクメールボックスからの受信メッセージに一括準拠レベル (BCL) を割り当てます。 BCL は X ヘッダー内のメッセージに追加され、スパムとしてメッセージを識別するために使用される[スパム信頼度 (SCL)](spam-confidence-levels.md)に似ています。 より多くの BCL は、バルクメッセージが苦情を生み出している可能性が高いことを示します (つまり、スパムである可能性が高くなります)。 Microsoft では、内部ソースとサードパーティソースの両方を使用して、バルクメールを識別し、適切な BCL を決定します。

バルクメール広告は、送信パターン、コンテンツ作成、受信者の取得方法によって異なります。 適切なバルクメール広告は、該当するコンテンツを持つ必要なメッセージをサブスクライバーに送信します。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 バルクメール送信からのメッセージは、バルクメールまたはグレーメールと呼ばれます。

 スパムフィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージを**バルクメール**としてマークし、メッセージに対して指定された処理を実行します (既定のアクションは、メッセージを受信者の迷惑メールフォルダーに配信します)。 詳細については、「[スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。

次の表で、BCL のしきい値について説明します。

|||
|:---:|---|
|**BCL**|**説明**|
|.0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、多くの苦情を生成するバルク送信者から送信されます。|
|
