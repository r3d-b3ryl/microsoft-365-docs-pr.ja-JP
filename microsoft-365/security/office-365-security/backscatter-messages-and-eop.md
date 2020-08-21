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
description: この記事では、バックスキャターと保護 (EOP) Microsoft Exchange Online について説明します。
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827787"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="361ff-103">EOP のバックスキャッター</span><span class="sxs-lookup"><span data-stu-id="361ff-103">Backscatter in EOP</span></span>

<span data-ttu-id="361ff-104">*バックスキャターは* 、送信していないメッセージに対して受信した配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="361ff-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="361ff-105">スパム送信者は、メッセージの From: アドレスを偽の対象として偽のメール アドレスを偽用 (なりすまし) 代わりとして使用します。多くの場合、実際のメール アドレスは、メッセージに対する分かりにくい状態のためです。</span><span class="sxs-lookup"><span data-stu-id="361ff-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="361ff-106">したがって、スパム送信者が存在しない受信者に間でメッセージを送信すると (スパムは大量の操作)、送信先メール サーバーは基本的に、NDR 内の配信不可能なメッセージが From: アドレスの差出人に返されるのを試みます。</span><span class="sxs-lookup"><span data-stu-id="361ff-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="361ff-107">Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP はすべての取り組みを行い、NDR を生成することなく、その不正な送信元からのメッセージを自動的に識別して通知なしに削除します。</span><span class="sxs-lookup"><span data-stu-id="361ff-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="361ff-108">しかし、サービスを介した流れを経由するボリュームの電子メールに基づいて、EOP が意図しないバックスキャターを送信する可能性は常に存在します。</span><span class="sxs-lookup"><span data-stu-id="361ff-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="361ff-109">Backscatterer.orgはバックスキャターの送信を行う電子メール サーバーの禁止一覧 (DNS 禁止リストまたは DNSBL とも呼ばれる) を維持し、この一覧に EOP サーバーが表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="361ff-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="361ff-110">しかし、Backscatterer.org のブロック リストから (独自の導入によって) そのものを削除しようとはしません。</span><span class="sxs-lookup"><span data-stu-id="361ff-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="361ff-111">大Backscatter.org Web サイト <http://www.backscatterer.org/?target=usage> () は、受信メールを拒否モードではなくセーフ モードで確認するようにお勧めします (大きなメール サービスでは、ほぼ常にバックスキャターが送信されます)。</span><span class="sxs-lookup"><span data-stu-id="361ff-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
