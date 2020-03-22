---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 管理者は、スパム信頼レベル (SCL) によって、メッセージがスパムであるかどうか、また、スパムフィルターが SCL に基づいてメッセージに対して実行する既定のアクションを決定する方法について理解できます。
ms.openlocfilehash: b8f194f9aecc31896fb816433e71d1b26de708f7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893696"
---
# <a name="spam-confidence-level-scl-in-office-365"></a><span data-ttu-id="4fa65-103">Office 365 でのスパム信頼度 (SCL)</span><span class="sxs-lookup"><span data-stu-id="4fa65-103">Spam confidence level (SCL) in Office 365</span></span>

<span data-ttu-id="4fa65-104">Office 365 (exchange online メールボックスがない exchange online またはスタンドアロンの Exchange Online Protection (EOP)) が受信電子メールメッセージを受信すると、メッセージはスパムフィルタリングを通過し、スパムスコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4fa65-104">When Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) receives an inbound email message, the message goes through spam filtering, and is assigned a spam score.</span></span> <span data-ttu-id="4fa65-105">このスコアは、X ヘッダー内のメッセージに追加される個々のスパム信頼レベル (SCL) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="4fa65-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="4fa65-106">SCL が高いほど、メッセージがスパムである可能性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="4fa65-107">サービスは、SCL に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-107">The service takes action on the message based on the SCL.</span></span>

<span data-ttu-id="4fa65-108">SCL の意味と、メッセージに対して実行される既定のアクションについて、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="4fa65-109">スパムフィルター verdict に基づいてメッセージに対して実行できるアクションの詳細については、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa65-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

||||
|:---:|---|---|
|<span data-ttu-id="4fa65-110">**SCL**</span><span class="sxs-lookup"><span data-stu-id="4fa65-110">**SCL**</span></span>|<span data-ttu-id="4fa65-111">**定義**</span><span class="sxs-lookup"><span data-stu-id="4fa65-111">**Definition**</span></span>|<span data-ttu-id="4fa65-112">**既定のアクション**</span><span class="sxs-lookup"><span data-stu-id="4fa65-112">**Default action**</span></span>|
|<span data-ttu-id="4fa65-113">-1</span><span class="sxs-lookup"><span data-stu-id="4fa65-113">-1</span></span>|<span data-ttu-id="4fa65-114">メッセージは、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="4fa65-114">The message skipped spam filtering.</span></span> <span data-ttu-id="4fa65-115">たとえば、メッセージが差出人セーフリストから送信された、または宛先セーフリストに送信された、または IP 許可一覧にある電子メールソースサーバーのメッセージである場合です。</span><span class="sxs-lookup"><span data-stu-id="4fa65-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="4fa65-116">詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa65-116">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="4fa65-117">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4fa65-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="4fa65-118">0, 1</span></span>|<span data-ttu-id="4fa65-119">スパムフィルターは、メッセージがスパムではないことを確認しました。</span><span class="sxs-lookup"><span data-stu-id="4fa65-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="4fa65-120">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="4fa65-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="4fa65-121">5, 6</span></span>|<span data-ttu-id="4fa65-122">メッセージが**スパム**としてマークされたスパムフィルター</span><span class="sxs-lookup"><span data-stu-id="4fa65-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="4fa65-123">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="4fa65-124">9 </span><span class="sxs-lookup"><span data-stu-id="4fa65-124">9</span></span>|<span data-ttu-id="4fa65-125">スパムフィルターがメッセージを**高信頼スパム**としてマークしました</span><span class="sxs-lookup"><span data-stu-id="4fa65-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="4fa65-126">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="4fa65-127">SCL 2、3、4、7、および8は、スパムフィルター処理によって使用されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="4fa65-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="4fa65-128">メールフロールール (トランスポートルールとも呼ばれます) を使用して、メッセージに SCL をスタンプすることができます。</span><span class="sxs-lookup"><span data-stu-id="4fa65-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="4fa65-129">メールフロールールを使用して SCL を設定する場合は、5または6の値によって**スパムに対するスパム**フィルター処理がトリガーされ、**精度の高いスパム**に対しては7、8、または9の値がスパムフィルター処理をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4fa65-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="4fa65-130">詳細については、「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa65-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="4fa65-131">SCL と同じように、バルク苦情レベル (BCL) は、不適切なバルクメール (_灰色のメール_) を特定します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="4fa65-132">上位の BCL は、バルクメールメッセージが苦情を生み出している可能性が高いことを示します (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="4fa65-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="4fa65-133">「スパム対策ポリシー」で、BCL のしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="4fa65-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="4fa65-134">詳細については、「 [office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」、「 [office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」、および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fa65-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in Office 365)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

||
|:-----|
|<span data-ttu-id="4fa65-p106">![LinkedIn Learning の小さいアイコン](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4fa65-p106">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
