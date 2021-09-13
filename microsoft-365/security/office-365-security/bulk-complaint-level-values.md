---
title: 一括クレーム レベルの値
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
description: 管理者は、管理者 (EOP) で使用される一括苦情レベル (BCL) Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192380"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>EOP のバルク 苦情レベル (BCL)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP はバルク メール配信者からの受信メッセージにバルク 苦情レベル (BCL) を割り当てる。 BCL は X ヘッダーのメッセージに追加され、メッセージをスパムとして識別するために使用されるスパム信頼レベル [(SCL)](spam-confidence-levels.md) に似ています。 BCL が高いほど、バルク メッセージが苦情を生成する可能性が高くなります (したがって、スパムである可能性が高くなります)。 Microsoft では、内部ソースとサード パーティソースの両方を使用してバルク メールを識別し、適切な BCL を決定します。

バルク メールは、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。 適切なバルク メール配信者は、関連するコンテンツを含む望ましいメッセージをサブスクライバーに送信します。 このようなメッセージが受信者の苦情につながることはあまりありません。 他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。 バルク メールのメッセージは、バルク メールまたはグレー メールと呼ばれる。

 スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージをバルク メールとしてマークし、メッセージに対して指定されたアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。  詳細については、「 [スパム](configure-your-spam-filter-policies.md) 対策ポリシーを構成する」および「迷惑メールとバルク メールの違い」 [を参照してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)

テナント許可/ブロック一覧を使用して、バルク メール フィルターの例外を構成できます。 指定されたドメインの送信者からのメッセージは、スパム対策ポリシーのバルク メールスパム フィルターの評決に対するアクションを受信しません。 詳細については、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。

BCL のしきい値を次の表に示します。

****

|BCL|説明|
|:---:|---|
|0|バルク送信者からのメッセージではありません。|
|1, 2, 3|苦情がほとんどないバルク送信者からのメッセージです。|
|4, 5, 6, 7<sup>\*</sup>|苦情の件数がさまざまなバルク送信者からのメッセージです。|
|8, 9|メッセージは、多数の苦情を生成する一括送信者からのメッセージです。|
|

<sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。
