---
title: ドメイン キー識別メール (DKIM) 署名済みメッセージの検証のサポート
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection および Exchange Online での DKIM 署名済みメッセージの検証について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 111bf169d60e386dc48ef086bbe631b8760201a6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916528"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="97018-103">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="97018-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97018-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="97018-104">**Applies to**</span></span>
- [<span data-ttu-id="97018-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="97018-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="97018-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="97018-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="97018-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97018-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="97018-108">Exchange Online Protection (EOP) と Exchange Online はどちらも、ドメイン キー識別メール ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="97018-108">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="97018-109">DKIM は、電子メール メッセージが他のユーザーによってスプーフィングされ、それが送信されたと言うドメインから送信されたと検証します。</span><span class="sxs-lookup"><span data-stu-id="97018-109">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="97018-110">電子メール メッセージを送信した組織に結び付きます。</span><span class="sxs-lookup"><span data-stu-id="97018-110">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="97018-111">DKIM 検証は、IPv6 で送信されるすべてのメッセージに対して自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="97018-111">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="97018-112">Microsoft 365 では、IPv4 を使用してメールが送信される場合にも DKIM がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="97018-112">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="97018-113">(IPv6 サポートの詳細については [、「IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)を使用した匿名受信メール メッセージのサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97018-113">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="97018-114">DKIM は、メッセージ ヘッダーの DKIM-Signatureに表示されるデジタル署名されたメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="97018-114">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="97018-115">検証の結果はDKIM-SignatureヘッダーにAuthentication-Resultsされます。</span><span class="sxs-lookup"><span data-stu-id="97018-115">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="97018-116">メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。</span><span class="sxs-lookup"><span data-stu-id="97018-116">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="97018-117">ヘッダーの詳細については、「Authentication-Results RFC 7001 ( メッセージ認証の状態を示すメッセージ ヘッダー フィールド」[を参照してください](https://www.rfc-editor.org/rfc/rfc7001.txt)。</span><span class="sxs-lookup"><span data-stu-id="97018-117">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="97018-118">Microsoft の DKIM 実装は、この RFC に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="97018-118">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="97018-119">管理者は、DKIM 検証の結果 [に](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="97018-119">Admins can create Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="97018-120">これらのメール フロー ルールを使用すると、管理者は必要に応じてメッセージをフィルター処理またはルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="97018-120">These mail flow rules will allow admins to filter or route messages as needed.</span></span>