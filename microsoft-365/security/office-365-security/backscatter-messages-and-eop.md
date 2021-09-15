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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Backscatter および Microsoft Exchange Online保護 (EOP) について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31af8d1467d1e38287c8308dcbac5e55fb7478bf
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356115"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* は、送信しなかったメッセージに対して受信する配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) です。 Backscatter は、スパム送信者がメッセージ内の From アドレス (または P2 アドレスとも呼ばれる) を偽造 (スプーフィング `5322.From` ) することで発生します。 スパム送信者は、多くの場合、実際の電子メール アドレスを From アドレスとして使用して、メッセージに信頼性を与えます。 スパムが存在しない受信者に送信される場合、宛先の電子メール サーバーは基本的に、NDR の配信不能メッセージを差出人アドレスの偽造送信者に返します。

Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP は NDR を生成せずに疑わしいソースからのメッセージを識別し、サイレント ドロップするためにあらゆる努力を行います。 ただし、サービスを流れるボリュームメールに基づいて、EOP が意図せずにバックスカッターを送信する可能性は常にあります。

Backscatterer.org は、バックスカッターの送信を担当した電子メール サーバーのブロックリスト (DNS ブロックリストまたは DNSBL とも呼ばれる) を保持し、EOP サーバーがこの一覧に表示される場合があります。 ただし、リストはスパム送信者のリストではないので、Backscatterer.org ブロックリストから自分自身を削除しようとはしない。

> [!TIP]
> 大規模 Backscatterer.org サービスはほとんど常にいくつかのバックスカッターを送信するため、Backscatterer.org Web サイト ( ) では、拒否モードではなく セーフ モードでサービスを使用することを <http://www.backscatterer.org/?target=usage> 推奨しています。
