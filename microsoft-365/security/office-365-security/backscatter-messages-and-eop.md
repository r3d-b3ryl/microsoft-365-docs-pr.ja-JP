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
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205113"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="90519-103">EOP のバックスキャッター</span><span class="sxs-lookup"><span data-stu-id="90519-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90519-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="90519-104">**Applies to**</span></span>
- [<span data-ttu-id="90519-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="90519-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90519-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="90519-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="90519-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90519-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="90519-108">*Backscatter* は、送信しなかったメッセージに対して受信する配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="90519-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="90519-109">スパム送信者は、メッセージの 送信者アドレスを偽装 (なりすまし) し、メッセージへの信頼性を高めるために、実在するメール アドレスを使用することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="90519-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="90519-110">したがって、スパム送信者が必然的に存在しない受信者にメッセージを送信する場合 (スパムは大規模な操作です)、宛先電子メール サーバーは基本的に、NDR の配信不能メッセージを From: アドレスの偽造送信者に返すようだまされます。</span><span class="sxs-lookup"><span data-stu-id="90519-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="90519-111">Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP は NDR を生成せずに疑わしいソースからのメッセージを識別し、サイレント ドロップするためにあらゆる努力を行います。</span><span class="sxs-lookup"><span data-stu-id="90519-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="90519-112">ただし、サービスを流れるボリュームメールに基づいて、EOP が意図せずにバックスカッターを送信する可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="90519-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="90519-113">Backscatterer.org は、バックスカッターの送信を担当した電子メール サーバーのブロック リスト (DNS ブロック リストまたは DNSBL とも呼ばれる) を保持し、EOP サーバーがこの一覧に表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="90519-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="90519-114">ただし、スパム送信者のリストではないので、Backscatterer.org ブロック リストから自分自身を削除しようとはしない (独自の許可によって)。</span><span class="sxs-lookup"><span data-stu-id="90519-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="90519-115">web Backscatter.org ( ) は、拒否モードではなく セーフ モードで受信メールを確認するサービスを使用することを推奨します (大規模なメール サービスは、ほとんどの場合、いくつかのバックスカッターを送信 <http://www.backscatterer.org/?target=usage> します)。</span><span class="sxs-lookup"><span data-stu-id="90519-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
