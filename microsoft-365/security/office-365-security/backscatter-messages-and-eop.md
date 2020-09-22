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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、バック散布と Microsoft Exchange Online Protection (EOP) について説明します。
ms.openlocfilehash: 2a752c89e2430f24441d14178942b89362736322
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203589"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*Backscatter* は、送信していないメッセージに対して受信する配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。 スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。 そのため、スパム送信者が、存在しない受信者にメッセージを送信した (スパムは大量の操作である) 場合、送信先の電子メールサーバーは本質的に、NDR 内の配信不能メッセージを From: アドレスの偽造された送信者に返すようになります。

Exchange online メールボックスを使用しない Exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP によって、NDR を生成せずに不審なソースからのメッセージを特定し、黙って削除することができます。 しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP が誤って backscatter を送信する可能性は常にあります。

Backscatterer.org は、backscatter の送信を担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示されることがあります。 ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。

> [!TIP]
> Backscatter.org web サイト ( <http://www.backscatterer.org/?target=usage> ) は、サービスを使用して、拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大部分の電子メールサービスでは、ほとんどの場合、何らかの散布が送信されます)。
