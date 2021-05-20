---
title: 一括クレーム レベルの値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、管理者 (EOP) で使用される一括苦情レベル (BCL) Exchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11f884ec6b32795deba09c0f1ba88055a6422e9b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537945"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="e7a1c-103">EOP のバルク 苦情レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="e7a1c-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e7a1c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e7a1c-104">**Applies to**</span></span>
- [<span data-ttu-id="e7a1c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e7a1c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e7a1c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e7a1c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e7a1c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7a1c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e7a1c-108">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP はバルク メール配信者からの受信メッセージにバルク 苦情レベル (BCL) を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk complaint level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="e7a1c-109">BCL は X ヘッダーのメッセージに追加され、メッセージをスパムとして識別するために使用されるスパム信頼レベル [(SCL)](spam-confidence-levels.md) に似ています。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="e7a1c-110">BCL が高いほど、バルク メッセージが苦情を生成する可能性が高くなります (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e7a1c-111">Microsoft では、内部ソースとサード パーティソースの両方を使用してバルク メールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="e7a1c-112">バルク メールは、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="e7a1c-113">適切なバルク メール配信者は、関連するコンテンツを含む望ましいメッセージをサブスクライバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="e7a1c-114">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="e7a1c-115">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="e7a1c-116">バルク メールのメッセージは、バルク メールまたはグレー メールと呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="e7a1c-117">スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージをバルク メールとしてマークし、メッセージに対して指定されたアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。 </span><span class="sxs-lookup"><span data-stu-id="e7a1c-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="e7a1c-118">詳細については、「 [スパム](configure-your-spam-filter-policies.md) 対策ポリシーを構成する」および「迷惑メールとバルク メールの違い」 [を参照してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="e7a1c-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="e7a1c-119">テナント許可/ブロック一覧を使用して、バルク メール フィルターの例外を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-119">You can use the Tenant Allow/Block List to configure exceptions for bulk mail filtering.</span></span> <span data-ttu-id="e7a1c-120">指定されたドメインの送信者からのメッセージは、スパム対策ポリシーのバルク メールスパム フィルターの評決に対するアクションを受信しません。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-120">Messages from senders in the specified domains don't receive the action for the **Bulk email** spam filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="e7a1c-121">詳細については、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-121">For more information, see [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</span></span>

<span data-ttu-id="e7a1c-122">BCL のしきい値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-122">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="e7a1c-123">BCL</span><span class="sxs-lookup"><span data-stu-id="e7a1c-123">BCL</span></span>|<span data-ttu-id="e7a1c-124">説明</span><span class="sxs-lookup"><span data-stu-id="e7a1c-124">Description</span></span>|
|:---:|---|
|<span data-ttu-id="e7a1c-125">0</span><span class="sxs-lookup"><span data-stu-id="e7a1c-125">0</span></span>|<span data-ttu-id="e7a1c-126">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-126">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="e7a1c-127">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="e7a1c-127">1, 2, 3</span></span>|<span data-ttu-id="e7a1c-128">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-128">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="e7a1c-129">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e7a1c-129">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="e7a1c-130">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-130">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="e7a1c-131">8, 9</span><span class="sxs-lookup"><span data-stu-id="e7a1c-131">8, 9</span></span>|<span data-ttu-id="e7a1c-132">メッセージは、多数の苦情を生成する一括送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-132">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="e7a1c-133"><sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。</span><span class="sxs-lookup"><span data-stu-id="e7a1c-133"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
