---
title: IPv6 経由の匿名受信電子メールのサポートを追加する
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
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083643"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a><span data-ttu-id="ac7ad-103">Office 365 で IPv6 による匿名受信電子メールのサポートを追加する</span><span class="sxs-lookup"><span data-stu-id="ac7ad-103">Add support for anonymous inbound email over IPv6 in Office 365</span></span>

<span data-ttu-id="ac7ad-104">Exchange online メールボックスを使用しない exchange online メールボックスおよびスタンドアロンの Exchange Online Protection (EOP) 組織を使用している Office 365 組織は、IPv6 経由の匿名受信電子メールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes support anonymous inbound email over IPv6.</span></span> <span data-ttu-id="ac7ad-105">ソース IPv6 電子メールサーバーは、次の両方の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-105">The source IPv6 email server must meet both of the following requirements:</span></span>

- <span data-ttu-id="ac7ad-106">送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-106">The source IPv6 address must have a valid reverse DNS lookup (PTR) record that allows the destination to find the domain name from the IPv6 address.</span></span>

- <span data-ttu-id="ac7ad-107">また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](https://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-107">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>

<span data-ttu-id="ac7ad-108">組織が IPv6 経由で匿名受信電子メールを受信できるようにするには、管理者が Microsoft サポートに連絡して、そのことを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-108">Before your organization can receive anonymous inbound email over IPv6, an admin needs to contact Microsoft support and ask for it:</span></span>

1. <span data-ttu-id="ac7ad-109">Microsoft 365 管理センター <https://admin.microsoft.com/adminportal/home>を開き、[**ヘルプ**] (?) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-109">Open the Microsoft 365 admin center at <https://admin.microsoft.com/adminportal/home> and click **Help** (?).</span></span>

2. <span data-ttu-id="ac7ad-110">[**ヘルプが必要ですか?]** ポップアップが表示されたら、検索ボックスにわかりやすい名前 (「匿名受信 IPv6 電子メールを要求する」など) を入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-110">In the **Need help?** flyout that appears, type something descriptive in the search box (for example, "request anonymous inbound IPv6 email"), and then press ENTER.</span></span>

3. <span data-ttu-id="ac7ad-111">ページの下部にある [サポートに**お問い合わせ**ください] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-111">At the bottom of the page, click **Contact support**.</span></span>

4. <span data-ttu-id="ac7ad-112">表示される [ **contact support** ] ページで、情報を入力して確認し (必要に応じてスクロールします)、[**自分の連絡先**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-112">In the **Contact support** page that appears, fill out and verify the information (scroll down as necessary), and then click **Contact me**.</span></span>

<span data-ttu-id="ac7ad-113">組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージフィルタリングを通過します。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-113">After anonymous inbound IPv6 message support is enabled in your organization, the message will go through the normal message filtering that's provided by the service.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ac7ad-114">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ac7ad-114">Troubleshooting</span></span>

- <span data-ttu-id="ac7ad-115">送信元の電子メールサーバーに IPv6 逆引き DNS 参照レコードがない場合は、次のエラーが発生してメッセージが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-115">If the source email server doesn't have an IPv6 reverse DNS lookup record, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac7ad-116">450 4.7.25 サービスは利用できません。送信 IPv6 アドレス [2a01: 111: f200: 2004:: 240] には逆引き DNS レコードが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-116">450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.</span></span>

- <span data-ttu-id="ac7ad-117">送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-117">If the sender doesn't pass SPF or DKIM validation, the messages will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac7ad-118">450 4.7.26 サービスを使用できません。 IPv6 経由で送信されるメッセージ [2a01: 111: f200: 2004:: 240] は、SPF または DKIM 検証に合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-118">450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.</span></span>

- <span data-ttu-id="ac7ad-119">匿名の IPv6 メッセージを受信しようとすると、次のエラーが発生して、メッセージが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-119">If you try to receive anonymous IPv6 messages before you've opted in, the message will be rejected with the following error:</span></span>

  > <span data-ttu-id="ac7ad-120">550 5.2.1 サービスを使用できません。 [contoso.com] は IPv6 経由の電子メールを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="ac7ad-120">550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="ac7ad-121">関連情報</span><span class="sxs-lookup"><span data-stu-id="ac7ad-121">For more information</span></span>

[<span data-ttu-id="ac7ad-122">DKIM 署名付きメッセージの検証をサポートする</span><span class="sxs-lookup"><span data-stu-id="ac7ad-122">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
