---
title: バックスキャター メッセージと EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: バックスキャッターメッセージは、偽造された電子メールアドレスに送信される自動バウンスメッセージです。 バックスキャター DNSBL は、バックスキャッターメッセージを送信するサーバーを識別します (多くの正当な電子メールソースが含まれている場合があります)。 スパム対策リストではないため、バックスキャター DNSBL から自分自身を削除しようとすることはありません。
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/27/2020
ms.locfileid: "42313812"
---
# <a name="backscatter-messages-and-eop"></a>Backscatter メッセージと EOP

*バックスキャッターメッセージ*は、送信していないメッセージに対して受信した配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。 スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。 そのため、スパム送信者が、存在しない受信者 (スパムは大量の操作) にメッセージを送信した場合、送信先の電子メールサーバーはおそらく NDR 内の配信不能メッセージを返します。これは、発信者アドレスの偽造した送信者に送信されます。

Exchange Online Protection (EOP) は、NDR を生成せずに、不審なソースからのメッセージを特定して暗黙的に削除することをすべての努力を行います。 しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP がバックスキャッターメッセージを誤って送信する可能性は常にあります。

Backscatterer.org は、バックスキャッターメッセージを送信することを担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示される場合があります。 ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。

> [!TIP]
> Backscatter.org web サイト (<http://www.backscatterer.org/?target=usage>) は、サービスを使用して拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大規模な電子メールサービスでは、ほとんどの場合、一部のバック散布メッセージが送信されます)。
