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
ms.openlocfilehash: 519bc48e7285283ad0570b8f3ac598615b132875
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638286"
---
# <a name="spam-confidence-level-scl-in-office-365"></a><span data-ttu-id="1b8a8-103">Office 365 でのスパム信頼度 (SCL)</span><span class="sxs-lookup"><span data-stu-id="1b8a8-103">Spam confidence level (SCL) in Office 365</span></span>

<span data-ttu-id="1b8a8-104">Microsoft 365 (exchange online またはスタンドアロンの exchange Online Protection (EOP) が Exchange Online メールボックスを使用しない) が受信メールメッセージを受信すると、メッセージはスパムフィルタリングを通過し、スパムスコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-104">When Microsoft 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) receives an inbound email message, the message goes through spam filtering, and is assigned a spam score.</span></span> <span data-ttu-id="1b8a8-105">このスコアは、X ヘッダー内のメッセージに追加される個々のスパム信頼レベル (SCL) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="1b8a8-106">SCL が高いほど、メッセージがスパムである可能性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="1b8a8-107">サービスは、SCL に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-107">The service takes action on the message based on the SCL.</span></span>

<span data-ttu-id="1b8a8-108">SCL の意味と、メッセージに対して実行される既定のアクションについて、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="1b8a8-109">スパムフィルター verdict に基づいてメッセージに対して実行できるアクションの詳細については、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

||||
|:---:|---|---|
|<span data-ttu-id="1b8a8-110">**SCL**</span><span class="sxs-lookup"><span data-stu-id="1b8a8-110">**SCL**</span></span>|<span data-ttu-id="1b8a8-111">**定義**</span><span class="sxs-lookup"><span data-stu-id="1b8a8-111">**Definition**</span></span>|<span data-ttu-id="1b8a8-112">**既定のアクション**</span><span class="sxs-lookup"><span data-stu-id="1b8a8-112">**Default action**</span></span>|
|<span data-ttu-id="1b8a8-113">-1</span><span class="sxs-lookup"><span data-stu-id="1b8a8-113">-1</span></span>|<span data-ttu-id="1b8a8-114">メッセージは、スパムフィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-114">The message skipped spam filtering.</span></span> <span data-ttu-id="1b8a8-115">たとえば、メッセージが差出人セーフリストから送信された、または宛先セーフリストに送信された、または IP 許可一覧にある電子メールソースサーバーのメッセージである場合です。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="1b8a8-116">詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-116">For more information, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="1b8a8-117">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1b8a8-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="1b8a8-118">0, 1</span></span>|<span data-ttu-id="1b8a8-119">スパムフィルターは、メッセージがスパムではないことを確認しました。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="1b8a8-120">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="1b8a8-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="1b8a8-121">5, 6</span></span>|<span data-ttu-id="1b8a8-122">メッセージが**スパム**としてマークされたスパムフィルター</span><span class="sxs-lookup"><span data-stu-id="1b8a8-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="1b8a8-123">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="1b8a8-124">9 </span><span class="sxs-lookup"><span data-stu-id="1b8a8-124">9</span></span>|<span data-ttu-id="1b8a8-125">スパムフィルターがメッセージを**高信頼スパム**としてマークしました</span><span class="sxs-lookup"><span data-stu-id="1b8a8-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="1b8a8-126">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="1b8a8-127">SCL 2、3、4、7、および8は、スパムフィルター処理によって使用されていないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="1b8a8-128">メールフロールール (トランスポートルールとも呼ばれます) を使用して、メッセージに SCL をスタンプすることができます。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="1b8a8-129">メールフロールールを使用して SCL を設定する場合は、5または6の値によって**スパムに対するスパム**フィルター処理がトリガーされ、**精度の高いスパム**に対しては7、8、または9の値がスパムフィルター処理をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="1b8a8-130">詳細については、「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="1b8a8-131">SCL と同じように、バルク苦情レベル (BCL) は、不適切なバルクメール (_灰色のメール_) を特定します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="1b8a8-132">上位の BCL は、バルクメールメッセージが苦情を生み出している可能性が高いことを示します (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="1b8a8-133">「スパム対策ポリシー」で、BCL のしきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="1b8a8-134">詳細については、「 [office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」、「 [office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」、および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in Office 365)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

||
|:-----|
|<span data-ttu-id="1b8a8-135">![LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png)の短いアイコン**を Office 365 に追加しますか?**</span><span class="sxs-lookup"><span data-stu-id="1b8a8-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="1b8a8-136">LinkedIn ラーニングによって提供される**Microsoft 365 管理者および IT プロフェッショナル**向けの無料のビデオコースを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1b8a8-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
