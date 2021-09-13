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
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192371"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Backscatter* は、送信しなかったメッセージに対して受信する配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) です。 スパム送信者は、メッセージの 送信者アドレスを偽装 (なりすまし) し、メッセージへの信頼性を高めるために、実在するメール アドレスを使用することがよくあります。 したがって、スパム送信者が必然的に存在しない受信者にメッセージを送信する場合 (スパムは大規模な操作です)、宛先電子メール サーバーは基本的に、NDR の配信不能メッセージを From: アドレスの偽造送信者に返すようだまされます。

Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP は NDR を生成せずに疑わしいソースからのメッセージを識別し、サイレント ドロップするためにあらゆる努力を行います。 ただし、サービスを流れるボリュームメールに基づいて、EOP が意図せずにバックスカッターを送信する可能性は常にあります。

Backscatterer.org は、バックスカッターの送信を担当した電子メール サーバーのブロック リスト (DNS ブロック リストまたは DNSBL とも呼ばれる) を保持し、EOP サーバーがこの一覧に表示される場合があります。 ただし、スパム送信者のリストではないので、Backscatterer.org ブロック リストから自分自身を削除しようとはしない (独自の許可によって)。

> [!TIP]
> web Backscatter.org ( ) は、拒否モードではなく セーフ モードで受信メールを確認するサービスを使用することを推奨します (大規模なメール サービスは、ほとんどの場合、いくつかのバックスカッターを送信 <http://www.backscatterer.org/?target=usage> します)。
