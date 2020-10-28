---
title: 外部メール転送の構成と制御、自動転送、5.7.520 アクセス拒否、外部転送の無効化、管理者が外部転送を無効にした、送信スパム対策ポリシー
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: dff2ea4e144f8f8fcc0f42732141e110effe7e9e
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774095"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="e015a-103">Microsoft 365 での自動外部電子メール転送の制御</span><span class="sxs-lookup"><span data-stu-id="e015a-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e015a-104">管理者は、外部の受信者 (組織外の受信者) に自動的に転送されるメッセージを制限または制御するために、会社の要件を持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="e015a-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="e015a-105">メールの転送は便利ですが、情報が漏洩する可能性があるため、セキュリティ上のリスクが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e015a-105">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="e015a-106">攻撃者は、この情報を使用して組織またはパートナーに攻撃を仕掛けることができます。</span><span class="sxs-lookup"><span data-stu-id="e015a-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="e015a-107">Microsoft 365 では、次の種類の自動転送を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e015a-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="e015a-108">ユーザーは、メッセージを外部の送信者に自動的に転送するように [受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) を構成できます (故意または侵害されたアカウントの結果として)。</span><span class="sxs-lookup"><span data-stu-id="e015a-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="e015a-109">管理者は、外部の受信者にメッセージを自動的に転送するように、 [メールボックス転送](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (SMTP 転送とも呼ばれます) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e015a-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as SMTP forwarding) to automatically forward messages to external recipients.</span></span>

<span data-ttu-id="e015a-110">送信スパムフィルターポリシーを使用して、外部の受信者への自動転送を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e015a-110">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="e015a-111">次の3つの設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e015a-111">Three settings are available:</span></span>

- <span data-ttu-id="e015a-112">**Automatic** : 自動外部転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e015a-112">**Automatic** : Automatic external forwarding is blocked.</span></span> <span data-ttu-id="e015a-113">メッセージの内部自動転送は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="e015a-113">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="e015a-114">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="e015a-114">This is the default setting.</span></span>

- <span data-ttu-id="e015a-115">**オン** : 外部の自動転送が許可されており、制限されていません。</span><span class="sxs-lookup"><span data-stu-id="e015a-115">**On** : Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="e015a-116">**Off** : 自動外部転送が無効になり、送信者に配信不能レポート (NDR またはバウンスメッセージとも呼ばれます) が発生します。</span><span class="sxs-lookup"><span data-stu-id="e015a-116">**Off** : Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="e015a-117">これらの設定を構成する方法については、「 [EOP で送信スパムフィルターを構成](configure-the-outbound-spam-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e015a-117">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="e015a-118">また、自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイルールも無効になります。</span><span class="sxs-lookup"><span data-stu-id="e015a-118">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>
> 
>   <span data-ttu-id="e015a-119">Office 365 では、受信トレイルールまたはメールボックス構成による自動外部転送を許可しません。これにより、セキュリティで保護された既定のポリシーが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e015a-119">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mailbox configuration, which provides a secure default policy.</span></span> <span data-ttu-id="e015a-120">ただし、管理者は組織内のすべてのユーザーまたは一部のユーザーについてこれらの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e015a-120">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="e015a-121">[送信スパムポリシー](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies)を作成し、[自動転送] セクションを変更して、ユーザーによる外部送信者への自動電子メール転送を制御します。</span><span class="sxs-lookup"><span data-stu-id="e015a-121">Create [outbound spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) and modify the automatic forwarding section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="e015a-122">これは、ポリシーが適用される内部送信者に後で適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e015a-122">This can be later applied to the internal senders that the policy applies to.</span></span> <span data-ttu-id="e015a-123">内部ユーザー間でのメッセージ転送は、このような変更による影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="e015a-123">Forwarding messages between internal users isn't affected by such a modification.</span></span>
> 
> - <span data-ttu-id="e015a-124">自動転送された [メッセージレポート](mfi-auto-forwarded-messages-report.md)で、外部の受信者にメッセージを自動的に転送するユーザーに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e015a-124">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="e015a-125">送信スパムフィルターポリシーの設定が他の自動メール転送コントロールとどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="e015a-125">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="e015a-126">管理者は、電子メールの自動転送を許可またはブロックするように、既に他のコントロールを構成している場合があります。</span><span class="sxs-lookup"><span data-stu-id="e015a-126">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="e015a-127">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e015a-127">For example:</span></span>

- <span data-ttu-id="e015a-128">[リモートドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) によって、一部またはすべての外部ドメインへの自動電子メール転送を許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e015a-128">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="e015a-129">Exchange [メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポートルールとも呼ばれます) 内の条件とアクションは、外部の受信者に自動的に転送されるメッセージを検出してブロックします。</span><span class="sxs-lookup"><span data-stu-id="e015a-129">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="e015a-130">リモートドメインの設定とメールフロールールは、送信スパムフィルターポリシーの設定とは独立しています。</span><span class="sxs-lookup"><span data-stu-id="e015a-130">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="e015a-131">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e015a-131">For example:</span></span>

- <span data-ttu-id="e015a-132">リモートドメインへの自動転送を許可するが、送信スパムフィルターポリシーの自動転送をブロックする。</span><span class="sxs-lookup"><span data-stu-id="e015a-132">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="e015a-133">この例では、自動的に転送されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e015a-133">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="e015a-134">送信スパムフィルターポリシーでの自動転送を許可しますが、自動的に転送された電子メールをブロックするには、メールフロールールまたはリモートドメイン設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="e015a-134">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="e015a-135">この例では、メールフロールールまたはリモートドメインの設定は、自動的に転送されるメッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e015a-135">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="e015a-136">この機能の独立性により、送信スパムフィルターポリシーの自動転送を許可することができますが、リモートドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e015a-136">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="e015a-137">ブロックされたメール転送メッセージ</span><span class="sxs-lookup"><span data-stu-id="e015a-137">The blocked email forwarding message</span></span>

<span data-ttu-id="e015a-138">メッセージが自動的に転送されると検出され、組織のポリシーによってそのアクティビティが *ブロック* されると、次の情報を含む NDR でメッセージが送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="e015a-138">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
