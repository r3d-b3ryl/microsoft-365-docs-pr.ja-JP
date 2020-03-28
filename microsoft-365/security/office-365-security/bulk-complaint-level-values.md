---
title: バルク苦情レベルの値、一括メール広告、BCL レベル、BCL のしくみ、BCL 評価、スパム対策、スパム対策ヘッダー、バルクメールフィルター、バルクメールの停止
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Office 365 の一括コンプライアンスレベル (BCL) の値について説明します。
ms.openlocfilehash: aa839fc1bcab141fe71c76e7f27b4f6bb23048b2
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "43030154"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Office 365 のバルク苦情レベル (BCL)

バルクメール広告は、送信パターン、コンテンツ作成、受信者の取得方法によって異なります。 適切なバルクメールを使用して、必要なコンテンツを含むメッセージをサブスクライバーに送信することができます。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 一括メールプログラムからのメッセージは、バルクメールまたはグレーメールと呼ばれます。

さまざまな種類のバルクメールボックスからのメッセージを区別するには、バルクメール広告から Office 365 (exchange online またはスタンドアロンの exchange Online Protection (EOP) に追加される受信電子メールに、Exchange online メールボックスを使用せずに追加されたバルク苦情レベル (BCL) が割り当てられます。X ヘッダー内のメッセージ。 BCL は、スパムとしてメッセージを識別するために使用される[スパム信頼レベル (SCL)](spam-confidence-levels.md)に似ています。 より多くの BCL は、バルクメッセージが苦情を生み出している可能性が高いことを示します (つまり、スパムである可能性が高くなります)。 Microsoft では、内部ソースとサードパーティソースの両方を使用して、バルクメールを識別し、適切な BCL を決定します。

 スパムフィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージを**バルクメール**としてマークし、メッセージに対して指定された処理を実行します (既定のアクションは、メッセージを受信者の迷惑メールフォルダーに配信します)。 詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。

次の表で、BCL のしきい値について説明します。

|||
|:---:|---|
|**BCL**|**説明**|
|.0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、多くの苦情を生成するバルク送信者から送信されます。|
|
