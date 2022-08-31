---
title: EOP のバックスキャッター
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Backscatter と Microsoft Exchange Online Protection (EOP) について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 5cc6bacfa7d66f9fa4f520f7826d8712861e98e2
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483258"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* は、送信しなかったメッセージに対して受信する配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) です。 Backscatter は、スパム送信者がメッセージ内の From アドレス (または P2 アドレスとも呼ばれます `5322.From` ) を偽装 (スプーフィング) することによって発生します。 スパム送信者は、多くの場合、実際の電子メール アドレスを差出人アドレスとして使用して、メッセージに信頼性を提供します。 スパムが存在しない受信者に送信されると、宛先電子メール サーバーは本質的に、NDR の配信不能メッセージを差出人アドレスの偽造された送信者に返すようにだまされます。

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含む Microsoft 365 組織では、Exchange Onlineメールボックスがない場合、EOP は NDR を生成せずに疑わしいソースからメッセージを識別し、サイレント ドロップするようあらゆる努力を行います。 しかし、サービスを流れる膨大な量のメールに基づいて、EOP が意図せずにバックスキャッターを送信する可能性は常にあります。

Backscatterer.org は、バックスキャッターの送信を担当する電子メール サーバーのブロックリスト (DNS ブロックリストまたは DNSBL とも呼ばれます) を保持し、EOP サーバーがこの一覧に表示される可能性があります。 ただし、Backscatterer.org ブロックリストから自分自身を削除しようとはしません。(自分のアドミッションによって) そのリストはスパム送信者のリストではないためです。

> [!TIP]
> Backscatterer.org Web サイト (<http://www.backscatterer.org/?target=usage>) では、ほとんどの場合、大規模な電子メール サービスがバックスキャッターを送信するため、拒否モードではなくセーフ モードでサービスを使用することをお勧めします。
