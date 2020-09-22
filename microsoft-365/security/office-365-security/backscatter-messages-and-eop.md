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
# <a name="backscatter-in-eop"></a><span data-ttu-id="ef171-103">EOP のバックスキャッター</span><span class="sxs-lookup"><span data-stu-id="ef171-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ef171-104">*Backscatter* は、送信していないメッセージに対して受信する配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="ef171-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="ef171-105">スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。</span><span class="sxs-lookup"><span data-stu-id="ef171-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="ef171-106">そのため、スパム送信者が、存在しない受信者にメッセージを送信した (スパムは大量の操作である) 場合、送信先の電子メールサーバーは本質的に、NDR 内の配信不能メッセージを From: アドレスの偽造された送信者に返すようになります。</span><span class="sxs-lookup"><span data-stu-id="ef171-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="ef171-107">Exchange online メールボックスを使用しない Exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP によって、NDR を生成せずに不審なソースからのメッセージを特定し、黙って削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ef171-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="ef171-108">しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP が誤って backscatter を送信する可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="ef171-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="ef171-109">Backscatterer.org は、backscatter の送信を担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ef171-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="ef171-110">ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。</span><span class="sxs-lookup"><span data-stu-id="ef171-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="ef171-111">Backscatter.org web サイト ( <http://www.backscatterer.org/?target=usage> ) は、サービスを使用して、拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大部分の電子メールサービスでは、ほとんどの場合、何らかの散布が送信されます)。</span><span class="sxs-lookup"><span data-stu-id="ef171-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
