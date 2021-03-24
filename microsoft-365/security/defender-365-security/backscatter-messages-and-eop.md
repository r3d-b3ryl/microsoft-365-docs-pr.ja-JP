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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065452"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* は、送信しなかったメッセージに対して受信する配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) です。 スパム送信者はメッセージの From: アドレスを偽造 (スプーフィング) し、多くの場合、実際の電子メール アドレスを使用してメッセージに信頼性を与えます。 したがって、スパム送信者が必然的に存在しない受信者にメッセージを送信する場合 (スパムは大規模な操作です)、宛先電子メール サーバーは基本的に、NDR の配信不能メッセージを From: アドレスの偽造送信者に返すようだまされます。

Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、EOP は NDR を生成せずに疑わしいソースからのメッセージを識別し、サイレント ドロップするためにあらゆる努力を行います。 ただし、サービスを流れるボリュームメールに基づいて、EOP が意図せずにバックスカッターを送信する可能性は常にあります。

Backscatterer.org は、バックスカッターの送信を担当した電子メール サーバーのブロック リスト (DNS ブロック リストまたは DNSBL とも呼ばれる) を保持し、EOP サーバーがこの一覧に表示される場合があります。 ただし、スパム送信者のリストではないので、Backscatterer.org ブロック リストから自分自身を削除しようとはしない (独自の許可によって)。

> [!TIP]
> web Backscatter.org ( ) は、拒否モードではなくセーフ モードで受信メールを確認するサービスを使用することを推奨します (大規模なメール サービスはほとんど常にいくつかのバックスカ <http://www.backscatterer.org/?target=usage> ッターを送信します)。
