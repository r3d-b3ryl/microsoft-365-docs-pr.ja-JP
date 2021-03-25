---
title: 外部メール転送の構成と制御、自動転送、5.7.520 Access Denied、外部転送の無効化、管理者が外部転送、送信スパム対策ポリシーを無効にしました
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205413"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="1b489-103">Microsoft 365 での外部メールの自動転送を制御する</span><span class="sxs-lookup"><span data-stu-id="1b489-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1b489-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1b489-104">**Applies to**</span></span>
- [<span data-ttu-id="1b489-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1b489-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1b489-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1b489-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1b489-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b489-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1b489-108">管理者として、自動的に転送されるメッセージを外部受信者 (組織外の受信者) に制限または制御する会社の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b489-108">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="1b489-109">電子メールの転送は便利ですが、情報の漏えいによるセキュリティ リスクを引き起す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b489-109">Email forwarding can be a useful, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="1b489-110">攻撃者は、この情報を使用して組織またはパートナーを攻撃する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b489-110">Attackers might use this information to attack your organization or partners.</span></span>


<span data-ttu-id="1b489-111">Microsoft 365 では、次の種類の自動転送を利用できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-111">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="1b489-112">ユーザーは受信 [トレイ ルールを](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 構成して、メッセージを外部の送信者に自動的に転送できます (意図的に、またはアカウントが侵害された結果)。</span><span class="sxs-lookup"><span data-stu-id="1b489-112">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="1b489-113">管理者は、メールボックス転送 _(SMTP_[転送](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)とも呼ばれる) を構成して、メッセージを外部受信者に自動的に転送できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-113">Admins can configure [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="1b489-114">管理者は、単にメッセージを転送するか、転送されたメッセージのコピーをメールボックスに保持するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-114">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="1b489-115">送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-115">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="1b489-116">次の 3 つの設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-116">Three settings are available:</span></span>

- <span data-ttu-id="1b489-117">**自動**: 外部自動転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1b489-117">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="1b489-118">メッセージの内部自動転送は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="1b489-118">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="1b489-119">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="1b489-119">This is the default setting.</span></span>
- <span data-ttu-id="1b489-120">**On**: 自動外部転送は許可され、制限されません。</span><span class="sxs-lookup"><span data-stu-id="1b489-120">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="1b489-121">**Off**: 自動外部転送が無効になり、送信者に配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) が発生します。</span><span class="sxs-lookup"><span data-stu-id="1b489-121">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="1b489-122">これらの設定を構成する方法については、「EOP で送信スパム フィルターを構成する」 [を参照してください](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1b489-122">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="1b489-123">自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。</span><span class="sxs-lookup"><span data-stu-id="1b489-123">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="1b489-124">内部ユーザー間のメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="1b489-124">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="1b489-125">メッセージを外部受信者に自動的に転送するユーザーに関する情報は、自動転送メッセージ レポート [で確認できます](mfi-auto-forwarded-messages-report.md)。</span><span class="sxs-lookup"><span data-stu-id="1b489-125">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="1b489-126">送信スパム フィルター ポリシー設定が他の自動メール転送コントロールとどのように機能する</span><span class="sxs-lookup"><span data-stu-id="1b489-126">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="1b489-127">管理者は、電子メールの自動転送を許可またはブロックするように他のコントロールを既に構成している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b489-127">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="1b489-128">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b489-128">For example:</span></span>

- <span data-ttu-id="1b489-129">[一部またはすべての](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 外部ドメインへの自動メール転送を許可またはブロックするリモート ドメイン。</span><span class="sxs-lookup"><span data-stu-id="1b489-129">[Remote domains](/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="1b489-130">[Exchange](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)メール フロー ルール (トランスポート ルールとも呼ばれる) の条件とアクションで、自動的に転送されたメッセージを検出して外部受信者にブロックします。</span><span class="sxs-lookup"><span data-stu-id="1b489-130">Conditions and actions in Exchange [mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="1b489-131">リモート ドメイン設定とメール フロー ルールは、送信スパム フィルター ポリシーの設定とは独立しています。</span><span class="sxs-lookup"><span data-stu-id="1b489-131">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="1b489-132">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b489-132">For example:</span></span>

- <span data-ttu-id="1b489-133">リモート ドメインの自動転送を許可しますが、送信スパム フィルター ポリシーでの自動転送をブロックします。</span><span class="sxs-lookup"><span data-stu-id="1b489-133">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="1b489-134">この例では、自動的に転送されたメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1b489-134">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="1b489-135">送信スパム フィルター ポリシーで自動転送を許可しますが、メール フロー ルールまたはリモート ドメイン設定を使用して、自動的に転送されるメールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="1b489-135">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="1b489-136">この例では、メール フロー ルールまたはリモート ドメイン設定によって、自動的に転送されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1b489-136">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="1b489-137">この機能の独立性により、(たとえば) 送信スパム フィルター ポリシーでの自動転送を許可できますが、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1b489-137">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="blocked-email-forwarding-messages"></a><span data-ttu-id="1b489-138">ブロックされたメール転送メッセージ</span><span class="sxs-lookup"><span data-stu-id="1b489-138">Blocked email forwarding messages</span></span>

<span data-ttu-id="1b489-139">メッセージが自動的に転送されると検出され、送信スパム フィルター[](configure-the-outbound-spam-policy.md)ポリシーによってそのアクティビティがブロックされると、次の情報を含む NDR の送信者にメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="1b489-139">When a message is detected as automatically forwarded, and the [outbound spam filter](configure-the-outbound-spam-policy.md) policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`