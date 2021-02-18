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
description: この記事では、バックスcatter と Microsoft Exchange Online Protection (EOP) について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d9556c69e5db460933b355e8bf12903d56f21b5
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286971"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="7b9db-103">EOP のバックスキャッター</span><span class="sxs-lookup"><span data-stu-id="7b9db-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7b9db-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7b9db-104">**Applies to**</span></span>
- [<span data-ttu-id="7b9db-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7b9db-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7b9db-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7b9db-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7b9db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b9db-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7b9db-108">*バックスカター* は、送信しなかったメッセージに対して受信する配信以外のレポート (NDRs またはバウンス メッセージとも呼ばれる) です。</span><span class="sxs-lookup"><span data-stu-id="7b9db-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="7b9db-109">スパム送信者は、メッセージの From: アドレスを偽造 (スプーフィング) し、多くの場合、実際の電子メール アドレスを使用してメッセージに信用を与えます。</span><span class="sxs-lookup"><span data-stu-id="7b9db-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="7b9db-110">そのため、スパム送信者が存在しない受信者に必ずメッセージを送信する場合 (スパムは高ボリュームの操作です)、送信先の電子メール サーバーは基本的に、NDR 内の配信不能メッセージを差出人: アドレスの偽造された送信者に返すようだまされます。</span><span class="sxs-lookup"><span data-stu-id="7b9db-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="7b9db-111">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP は NDR を生成せずに、疑わしいソースからのメッセージを識別し、通知なしでメッセージをドロップするあらゆる努力を行います。</span><span class="sxs-lookup"><span data-stu-id="7b9db-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="7b9db-112">ただし、サービスを通過するボリューム メールの数が多い場合、EOP が意図せずにバックスカターを送信する可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="7b9db-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="7b9db-113">Backscatterer.orgバックスカターの送信を担当する電子メール サーバーのブロック リスト (DNS ブロック リストまたは DNSBL とも呼ばれる) が保持され、EOP サーバーがこの一覧に表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b9db-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="7b9db-114">ただし、Backscatterer.org ブロック リストはスパム送信者の一覧 (独自の受付により) ではないので、削除は試みなされません。</span><span class="sxs-lookup"><span data-stu-id="7b9db-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="7b9db-115">Backscatter.org Web サイト ( ) では、拒否モードではなくセーフ モードで受信メールをチェックするためにサービスを使用することを推奨しています (大きなメール サービスは、ほとんど常にバック <http://www.backscatterer.org/?target=usage> スカターを送信します)。</span><span class="sxs-lookup"><span data-stu-id="7b9db-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
