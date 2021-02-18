---
title: IPv6 経由の匿名受信メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online および Exchange Online Protection で IPv6 ソースからの匿名受信電子メールのサポートを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290275"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a><span data-ttu-id="c3a37-103">Microsoft 365 で IPv6 を使用して匿名受信メールのサポートを追加する</span><span class="sxs-lookup"><span data-stu-id="c3a37-103">Add support for anonymous inbound email over IPv6 in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c3a37-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c3a37-104">**Applies to**</span></span>
- [<span data-ttu-id="c3a37-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c3a37-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c3a37-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c3a37-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c3a37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3a37-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c3a37-108">Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織は、IPv6 を使用した匿名受信電子メールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c3a37-108">Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="c3a37-109">送信元 IPv6 電子メール サーバーは、次の両方の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3a37-109">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="c3a37-110">送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3a37-110">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="c3a37-111">また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3a37-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="c3a37-112">組織が IPv6 を使用して匿名の受信メールを受信するには、管理者が Microsoft サポートに問い合わせ、それを求める必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3a37-112">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="c3a37-113">サポートリクエストを開く方法については、「一部のビジネス製品のサポートに問い合わせ - 管理者向け [ヘルプ」を参照してください](../../admin/contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a37-113">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="c3a37-114">組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージ フィルター処理を通過します。</span><span class="sxs-lookup"><span data-stu-id="c3a37-114">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c3a37-115">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c3a37-115">Troubleshooting</span></span>

- <span data-ttu-id="c3a37-116">送信元の電子メール サーバーに IPv6 逆引き DNS 参照レコードが存在しない場合、メッセージは次のエラーで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c3a37-116">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c3a37-117">450 4.7.25 サービスが利用できません。IPv6 アドレス [2a01:111:f200:2004::240] を送信するには、逆引き DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c3a37-117">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="c3a37-118">送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c3a37-118">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c3a37-119">450 4.7.26 サービスが利用できません。IPv6 を通して送信されるメッセージ [2a01:111:f200:2004::240] は、SPF または DKIM 検証に合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3a37-119">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="c3a37-120">オプトインする前に匿名 IPv6 メッセージを受信すると、メッセージは次のエラーで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c3a37-120">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="c3a37-121">550 5.2.1 サービスは利用できません。[contoso.com] は IPv6 を使用した電子メールを受け入れできません。</span><span class="sxs-lookup"><span data-stu-id="c3a37-121">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3a37-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3a37-122">Related topics</span></span>

[<span data-ttu-id="c3a37-123">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="c3a37-123">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
