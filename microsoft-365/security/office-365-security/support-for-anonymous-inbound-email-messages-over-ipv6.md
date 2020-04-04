---
title: IPv6 経由の匿名受信メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online および Exchange Online Protection の IPv6 ソースからの匿名受信電子メールのサポートを構成する方法について説明します。
ms.openlocfilehash: 414c10f3387138ed7e62f2de4e8549e45d128d2e
ms.sourcegitcommit: 256184cf731c1851b04a07dd7d59ecf020d02635
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131521"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="c7eaa-103">Office 365 で IPv6 による匿名受信電子メールのサポートを追加する</span><span class="sxs-lookup"><span data-stu-id="c7eaa-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="c7eaa-104">Exchange online メールボックスを使用しない exchange online メールボックスおよびスタンドアロンの Exchange Online Protection (EOP) 組織を使用している Office 365 組織は、IPv6 経由の匿名受信電子メールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="c7eaa-105">ソース IPv6 電子メールサーバーは、次の両方の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="c7eaa-106">送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="c7eaa-107">また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](https://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="c7eaa-108">組織が IPv6 経由で匿名受信電子メールを受信できるようにするには、管理者が Microsoft サポートに連絡して要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it.</span></span> <span data-ttu-id="c7eaa-109">サポートリクエストを開く方法については、「一般[法人向け製品サポートへのお問い合わせ-管理者向けヘルプ](../../admin/contact-support-for-business-products.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-109">For instructions about how to open a support request, see [Contact support for business products - Admin Help](../../admin/contact-support-for-business-products.md).</span></span>

<span data-ttu-id="c7eaa-110">組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージフィルタリングを通過します。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-110">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c7eaa-111">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c7eaa-111">Troubleshooting</span></span>

- <span data-ttu-id="c7eaa-112">送信元の電子メールサーバーに IPv6 逆引き DNS 参照レコードがない場合は、次のエラーが発生してメッセージが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-112">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c7eaa-113">450 4.7.25 サービスは利用できません。送信 IPv6 アドレス [2a01: 111: f200: 2004:: 240] には逆引き DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-113">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="c7eaa-114">送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-114">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="c7eaa-115">450 4.7.26 サービスを使用できません。 IPv6 経由で送信されるメッセージ [2a01: 111: f200: 2004:: 240] は、SPF または DKIM 検証に合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-115">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="c7eaa-116">匿名の IPv6 メッセージを受信しようとすると、次のエラーが発生して、メッセージが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-116">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="c7eaa-117">550 5.2.1 サービスを使用できません。 [contoso.com] は IPv6 経由の電子メールを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="c7eaa-117">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="c7eaa-118">関連情報</span><span class="sxs-lookup"><span data-stu-id="c7eaa-118">For more information</span></span>

[<span data-ttu-id="c7eaa-119">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="c7eaa-119">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
