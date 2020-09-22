---
title: DKIM 署名付きメッセージの検証をサポートする
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
description: Exchange Online Protection と Exchange Online での DKIM 署名付きメッセージの検証について
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202139"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="79448-103">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="79448-103">Support for validation of DKIM signed messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="79448-104">Exchange Online Protection (EOP) および Exchange Online では、ドメインキー識別メール ([Dkim](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="79448-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="79448-105">DKIM は、メッセージがドメインから送信されたことを検証する方法です。これは、そのメッセージが送信者からのものであり、他のユーザーによってスプーフィングされていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="79448-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="79448-106">これにより、電子メール メッセージがその送信を担当する組織に対応付けられます。</span><span class="sxs-lookup"><span data-stu-id="79448-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="79448-107">DKIM 検証は、IPv6 通信で送信されるすべてのメッセージに対して自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="79448-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="79448-108">また、Microsoft 365 は、メールが IPv4 経由で送信されるときに、DKIM をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="79448-108">Microsoft 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="79448-109">(IPv6 のサポートの詳細については、「 [ipv6 経由の匿名受信電子メールメッセージのサポート](support-for-anonymous-inbound-email-messages-over-ipv6.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="79448-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>

<span data-ttu-id="79448-p102">DKIM は、メッセージ ヘッダー内の DKIM 署名ヘッダーに表示されるデジタル署名付きメッセージを検証します。DKIM 署名検証の結果は RFC 7001 ([メッセージ認証状態を示すためのメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)) に準拠した認証結果ヘッダー内でスタンプされます。メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。</span><span class="sxs-lookup"><span data-stu-id="79448-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

<span data-ttu-id="79448-113">管理者は、DKIM 検証の結果に対して Exchange [メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポートルールとも呼ばれます) を作成し、必要に応じてメッセージをフィルター処理またはルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="79448-113">Admins can create Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span>
