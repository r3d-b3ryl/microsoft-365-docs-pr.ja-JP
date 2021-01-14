---
title: ドメイン キー識別メール (DKIM) 署名済みメッセージの検証のサポート
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online Protection と Exchange Online での DKIM 署名済みメッセージの検証について説明します。
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845061"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="2c530-103">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="2c530-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2c530-104">Exchange Online Protection (EOP) と Exchange Online はどちらも、ドメイン キー識別メール[(DKIM)](https://www.rfc-editor.org/rfc/rfc6376.txt)メッセージの受信検証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2c530-104">Exchange Online Protection (EOP) and Exchange Online both support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span>

<span data-ttu-id="2c530-105">DKIM は、電子メール メッセージが他のユーザーによってスプーフィングされたのではないこと、およびメールメッセージが送信されたと言うドメインから送信されたと検証します。</span><span class="sxs-lookup"><span data-stu-id="2c530-105">DKIM validates that an email message wasn't *spoofed* by someone else, and was sent from the domain it *says* it came from.</span></span> <span data-ttu-id="2c530-106">電子メール メッセージを送信した組織に関連付けします。</span><span class="sxs-lookup"><span data-stu-id="2c530-106">It ties an email message to the organization that sent it.</span></span> <span data-ttu-id="2c530-107">DKIM 検証は、IPv6 と一緒に送信される全メッセージに対して自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c530-107">DKIM verification is used automatically for all messages sent with IPv6.</span></span> <span data-ttu-id="2c530-108">Microsoft 365 は、メールが IPv4 を使用して送信される場合にも DKIM をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2c530-108">Microsoft 365 also supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="2c530-109">(IPv6 サポートの詳細については、「IPv6 を使用した匿名受信電子メール メッセージのサポート」を[参照してください)。](support-for-anonymous-inbound-email-messages-over-ipv6.md)</span><span class="sxs-lookup"><span data-stu-id="2c530-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="2c530-110">DKIM は、メッセージ ヘッダーの DKIM-Signatureに表示されるデジタル署名されたメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="2c530-110">DKIM validates a digitally signed message that appears in the DKIM-Signature header of the message headers.</span></span> <span data-ttu-id="2c530-111">検証の結果DKIM-SignatureヘッダーにスタンプAuthentication-Resultsされます。</span><span class="sxs-lookup"><span data-stu-id="2c530-111">The results of a DKIM-Signature validation are stamped in the Authentication-Results header.</span></span> <span data-ttu-id="2c530-112">メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。</span><span class="sxs-lookup"><span data-stu-id="2c530-112">The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> <span data-ttu-id="2c530-113">このヘッダーの詳細についてはAuthentication-Results RFC 7001 ( Message[Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span><span class="sxs-lookup"><span data-stu-id="2c530-113">For more information about the Authentication-Results header, see RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt).</span></span> <span data-ttu-id="2c530-114">Microsoft の DKIM 実装は、この RFC に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="2c530-114">Microsoft's DKIM implementation conforms with this RFC.</span></span>

<span data-ttu-id="2c530-115">管理者は、DKIM 検証 [の結果に対](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) して Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2c530-115">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of DKIM validation.</span></span> <span data-ttu-id="2c530-116">これらのメール フロー ルールにより、管理者は必要に応じてメッセージをフィルター処理またはルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="2c530-116">These mail flow rules will allow admins to filter or route messages as needed.</span></span>
