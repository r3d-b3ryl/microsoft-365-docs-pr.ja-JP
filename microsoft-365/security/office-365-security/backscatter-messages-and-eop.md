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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d132ed56c02989987da9e0ce32e7d4593e85e651
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648219"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* は、送信しなかったメッセージに対して受信する配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) です。 Backscatter は、スパム送信者がメッセージ内の From アドレス (または P2 アドレスとも呼ばれます `5322.From` ) を偽装 (スプーフィング) することによって発生します。 スパム送信者は、多くの場合、実際の電子メール アドレスを差出人アドレスとして使用して、メッセージに信頼性を提供します。 スパムが存在しない受信者に送信されると、宛先電子メール サーバーは本質的に、NDR の配信不能メッセージを差出人アドレスの偽造された送信者に返すようにだまされます。

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを持つMicrosoft 365組織では、Exchange Onlineメールボックスがない場合、EOP は NDR を生成することなく、疑わしいソースからメッセージを識別してサイレント ドロップするようあらゆる努力を行います。 しかし、サービスを流れる膨大な量のメールに基づいて、EOP が意図せずにバックスキャッターを送信する可能性は常にあります。

Backscatterer.org は、バックスキャッターの送信を担当する電子メール サーバーのブロックリスト (DNS ブロックリストまたは DNSBL とも呼ばれます) を保持し、EOP サーバーがこの一覧に表示される可能性があります。 ただし、Backscatterer.org ブロックリストから自分自身を削除しようとはしません。(自分のアドミッションによって) そのリストはスパム送信者のリストではないためです。

> [!TIP]
> Backscatterer.org Web サイト (<http://www.backscatterer.org/?target=usage>) では、拒否モードではなくセーフ モードでサービスを使用することをお勧めします。大規模な電子メール サービスでは、ほとんどの場合、バックスキャッターが送信されるためです。
