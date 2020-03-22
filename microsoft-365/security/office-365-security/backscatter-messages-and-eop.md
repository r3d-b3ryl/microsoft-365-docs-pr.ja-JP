---
title: Backscatter and EOP
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
description: Backscatter は、偽造された電子メールアドレスに送信される自動バウンスメッセージです。 バックスキャター DNSBL は、バックスキャッターメッセージを送信するサーバーを識別します (多くの正当な電子メールソースが含まれている場合があります)。 スパム対策リストではないため、バックスキャター DNSBL から自分自身を削除しようとすることはありません。
ms.openlocfilehash: 22eeec29722cf1742e096234aad95b9f6ee407e2
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895407"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="6473f-105">Backscatter and EOP</span><span class="sxs-lookup"><span data-stu-id="6473f-105">Backscatter and EOP</span></span>

<span data-ttu-id="6473f-106">*Backscatter*は、送信していないメッセージに対して受信する配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="6473f-106">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="6473f-107">スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。</span><span class="sxs-lookup"><span data-stu-id="6473f-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="6473f-108">そのため、スパム送信者が、存在しない受信者にメッセージを送信した (スパムは大量の操作である) 場合、送信先の電子メールサーバーは本質的に、NDR 内の配信不能メッセージを From: アドレスの偽造された送信者に返すようになります。</span><span class="sxs-lookup"><span data-stu-id="6473f-108">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="6473f-109">Exchange Online Protection (EOP) は、NDR を生成せずに、不審なソースからのメッセージを特定して暗黙的に削除することをすべての努力を行います。</span><span class="sxs-lookup"><span data-stu-id="6473f-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="6473f-110">しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP が誤って backscatter を送信する可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="6473f-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="6473f-111">Backscatterer.org は、backscatter の送信を担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6473f-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="6473f-112">ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。</span><span class="sxs-lookup"><span data-stu-id="6473f-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="6473f-113">Backscatter.org web サイト (<http://www.backscatterer.org/?target=usage>) は、サービスを使用して、拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大部分の電子メールサービスでは、ほとんどの場合、何らかの散布が送信されます)。</span><span class="sxs-lookup"><span data-stu-id="6473f-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
