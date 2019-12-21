---
title: バックスキャター メッセージと EOP
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
ms.openlocfilehash: f6e8398565837f7a380c8a6a5c4cd8de422cc215
ms.sourcegitcommit: ca4ce9e8c7e4b433608cd059857740ffd5a472c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2019
ms.locfileid: "40840166"
---
# <a name="backscatter-messages-and-eop"></a>バックスキャター メッセージと EOP

*バックスキャッターメッセージ*は、送信していないメッセージに対して受信した配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。 スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。 そのため、存在しない受信者にメッセージを必然的に送信する (スパムは大量の操作である) 場合、送信先の電子メールサーバーは NDR を dutifully 応答する可能性があります。これは、送信者アドレスの偽造した送信者に送信されます。

Exchange Online Protection (EOP) は、NDR を生成せずに、不審なソースからのメッセージを特定して暗黙的に削除することをすべての努力を行います。 しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP がバックスキャッターメッセージを誤って送信する可能性は常にあります。

Backscatterer.org は、バックスキャッターメッセージを送信することを担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示される場合があります。 ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。

> [!TIP]
> バックスキャッターまたは web サイト (`http://www.backscatterer.org/?target=usage`) によれば、サービスを使用して、拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大規模な電子メールサービスでは、ほとんどの場合、一部のバック散布メッセージが送信されます)。
