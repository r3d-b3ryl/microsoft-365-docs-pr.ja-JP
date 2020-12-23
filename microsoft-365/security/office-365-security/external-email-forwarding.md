---
title: 外部電子メール転送の構成と制御, 自動転送, 5.7.520 アクセスが拒否されました, 外部転送を無効にする, 管理者が外部転送を無効にしました, 送信スパム対策ポリシー
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
ms.openlocfilehash: f75504941e8481d35458ad2ae6b5e8a72c5e8c8c
ms.sourcegitcommit: a49338bde6923b13132c7b9e4c6bb75c14163c72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2020
ms.locfileid: "49728190"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a><span data-ttu-id="c66bb-103">Microsoft 365 で外部メールの自動転送を制御する</span><span class="sxs-lookup"><span data-stu-id="c66bb-103">Control automatic external email forwarding in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c66bb-104">管理者として、自動的に転送されるメッセージを外部の受信者 (組織外の受信者) に制限または制御する会社の要件がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c66bb-104">As an admin, you might have company requirements to restrict or control automatically forwarded messages to external recipients (recipients outside of your organization).</span></span> <span data-ttu-id="c66bb-105">電子メールの転送は便利な機能ですが、情報が開示される可能性のためにセキュリティ上のリスクが生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="c66bb-105">Email forwarding can be a useful feature, but can also pose a security risk due to the potential disclosure of information.</span></span> <span data-ttu-id="c66bb-106">攻撃者はこの情報を使用して、組織やパートナーを攻撃する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c66bb-106">Attackers might use this information to attack your organization or partners.</span></span>

<span data-ttu-id="c66bb-107">Microsoft 365 では、次の種類の自動転送を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-107">The following types of automatic forwarding are available in Microsoft 365:</span></span>

- <span data-ttu-id="c66bb-108">ユーザー [は、(](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 意図的に、またはアカウントが侵害された結果として) メッセージを外部の送信者に自動的に転送する受信トレイ ルールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-108">Users can configure [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) to automatically forward messages to external senders (deliberately or as a result of a compromised account).</span></span>

- <span data-ttu-id="c66bb-109">管理者は、メッセージを外部 [の受信者に](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 自動的に転送するメールボックス転送 _(SMTP_ 転送とも呼ばれる) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-109">Admins can configure [mailbox forwarding](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_) to automatically forward messages to external recipients.</span></span> <span data-ttu-id="c66bb-110">管理者は、単にメッセージを転送するか、転送されたメッセージのコピーをメールボックスに保持するか選択できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-110">The admin can choose whether to simply forward messages, or keep copies of forwarded messages in the mailbox.</span></span>

<span data-ttu-id="c66bb-111">送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-111">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="c66bb-112">次の 3 つの設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-112">Three settings are available:</span></span>

- <span data-ttu-id="c66bb-113">**自動**: 外部自動転送がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-113">**Automatic**: Automatic external forwarding is blocked.</span></span> <span data-ttu-id="c66bb-114">メッセージの内部自動転送は引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="c66bb-114">Internal automatic forwarding of messages will continue to work.</span></span> <span data-ttu-id="c66bb-115">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="c66bb-115">This is the default setting.</span></span>
- <span data-ttu-id="c66bb-116">**オン**: 外部自動転送は許可され、制限されません。</span><span class="sxs-lookup"><span data-stu-id="c66bb-116">**On**: Automatic external forwarding is allowed and not restricted.</span></span>
- <span data-ttu-id="c66bb-117">**オフ**: 外部自動転送が無効になり、送信者に配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-117">**Off**: Automatic external forwarding is disabled and will result in a non-delivery report (also known as an NDR or bounce message) to the sender.</span></span>

<span data-ttu-id="c66bb-118">これらの設定を構成する方法については [、「EOP](configure-the-outbound-spam-policy.md)で送信スパム フィルターを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c66bb-118">For instructions on how to configure these settings, see [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c66bb-119">自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。</span><span class="sxs-lookup"><span data-stu-id="c66bb-119">Disabling automatic forwarding disables any Inbox rules (users) or mailbox forwarding (admins) that redirect messages to external addresses.</span></span>
>
> - <span data-ttu-id="c66bb-120">内部ユーザー間のメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受けしません。</span><span class="sxs-lookup"><span data-stu-id="c66bb-120">Automatic forwarding of messages between internal users isn't affected by the settings in outbound spam filter policies.</span></span>
>
> - <span data-ttu-id="c66bb-121">自動転送されたメッセージ レポートで、外部の受信者に自動的にメッセージを転送するユーザーに関する情報 [を確認できます](mfi-auto-forwarded-messages-report.md)。</span><span class="sxs-lookup"><span data-stu-id="c66bb-121">You can see information about users that are automatically forwarding messages to external recipients in the [Auto-forwarded messages report](mfi-auto-forwarded-messages-report.md).</span></span>

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a><span data-ttu-id="c66bb-122">送信スパム フィルター ポリシー設定と他の自動電子メール転送コントロールの動作方法</span><span class="sxs-lookup"><span data-stu-id="c66bb-122">How the outbound spam filter policy settings work with other automatic email forwarding controls</span></span>

<span data-ttu-id="c66bb-123">管理者として、メールの自動転送を許可またはブロックする他のコントロールが既に構成されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c66bb-123">As an admin, you might have already configured other controls to allow or block automatic email forwarding.</span></span> <span data-ttu-id="c66bb-124">例:</span><span class="sxs-lookup"><span data-stu-id="c66bb-124">For example:</span></span>

- <span data-ttu-id="c66bb-125">[一部またはすべての](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 外部ドメインへの電子メールの自動転送を許可またはブロックするリモート ドメイン。</span><span class="sxs-lookup"><span data-stu-id="c66bb-125">[Remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) to allow or block automatic email forwarding to some or all external domains.</span></span>

- <span data-ttu-id="c66bb-126">Exchange メール フロー [ルール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれる) の条件とアクション。外部の受信者に自動的に転送されるメッセージを検出してブロックします。</span><span class="sxs-lookup"><span data-stu-id="c66bb-126">Conditions and actions in Exchange [mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to detect and block automatically forwarded messages to external recipients.</span></span>

<span data-ttu-id="c66bb-127">リモート ドメイン設定とメール フロー ルールは、送信スパム フィルター ポリシーの設定とは独立しています。</span><span class="sxs-lookup"><span data-stu-id="c66bb-127">Remote domain settings and mail flow rules are independent of the settings in outbound spam filter policies.</span></span> <span data-ttu-id="c66bb-128">例:</span><span class="sxs-lookup"><span data-stu-id="c66bb-128">For example:</span></span>

- <span data-ttu-id="c66bb-129">リモート ドメインの自動転送は許可しますが、送信スパム フィルター ポリシーでは自動転送をブロックします。</span><span class="sxs-lookup"><span data-stu-id="c66bb-129">You allow automatic forwarding for a remote domain, but you block automatic forwarding in outbound spam filter policies.</span></span> <span data-ttu-id="c66bb-130">この例では、自動的に転送されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-130">In this example, automatically forwarded messages are blocked.</span></span>

- <span data-ttu-id="c66bb-131">送信スパム フィルター ポリシーでは自動転送を許可しますが、メール フロー ルールまたはリモート ドメイン設定を使用して、自動的に転送される電子メールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c66bb-131">You allow automatic forwarding in outbound spam filter policies, but you use mail flow rules or remote domain settings to block automatically forwarded email.</span></span> <span data-ttu-id="c66bb-132">この例では、メール フロー ルールまたはリモート ドメイン設定によって、自動的に転送されるメッセージがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-132">In this example, the mail flow rules or remote domain settings will block automatically forwarded messages.</span></span>

<span data-ttu-id="c66bb-133">この機能の独立性により、送信スパム フィルター ポリシーでの自動転送を許可する (たとえば) が、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-133">This feature independence allows you to (for example) allow automatic forwarding in outbound spam filter policies, but use remote domains to control the external domains that users can forward messages to.</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="c66bb-134">ブロックされた電子メール転送メッセージ</span><span class="sxs-lookup"><span data-stu-id="c66bb-134">The blocked email forwarding message</span></span>

<span data-ttu-id="c66bb-135">メッセージが自動的に転送されると検出され、組織のポリシーによってそのアクティビティがブロックされると、メッセージは次の情報を含む NDR 内の送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="c66bb-135">When a message is detected as automatically forwarded, and the organizational policy *blocks* that activity, the message is returned to the sender in an NDR that contains the following information:</span></span>

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
