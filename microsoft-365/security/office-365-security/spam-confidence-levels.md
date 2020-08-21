---
title: Spam Confidence Level
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のメッセージに適用される Spam Confidence Level (SCL) について学習できます。
ms.openlocfilehash: 44687b8234e38e7f818aee908d1b65f382c908fe
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827399"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="38c51-103">EOP の Spam Confidence Level (SCL)</span><span class="sxs-lookup"><span data-stu-id="38c51-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="38c51-104">Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信メッセージは EOP のスパム フィルタリングを通過し、スパム スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="38c51-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="38c51-105">そのスコアは、X ヘッダー内のメッセージに追加される個々の Spam Confidence Level (SCL) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="38c51-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="38c51-106">SCL が高いと、メッセージがスパムである可能性が高いことを示します。</span><span class="sxs-lookup"><span data-stu-id="38c51-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="38c51-107">EOP は SCL に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="38c51-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="38c51-108">メッセージに対して実行される SCL の意味と既定のアクションについて、以下の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="38c51-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="38c51-109">スパム フィルターの確認に基づいてメッセージに対して実行できるアクションの詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="38c51-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="38c51-110">SCL</span><span class="sxs-lookup"><span data-stu-id="38c51-110">SCL</span></span>|<span data-ttu-id="38c51-111">定義</span><span class="sxs-lookup"><span data-stu-id="38c51-111">Definition</span></span>|<span data-ttu-id="38c51-112">既定のアクション</span><span class="sxs-lookup"><span data-stu-id="38c51-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="38c51-113">-1</span><span class="sxs-lookup"><span data-stu-id="38c51-113">-1</span></span>|<span data-ttu-id="38c51-114">メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="38c51-114">The message skipped spam filtering.</span></span> <span data-ttu-id="38c51-115">たとえば、メッセージが差出人セーフ リストから差出人セーフに送信されたか、または IP 許可一覧のメール送信元サーバーからのメッセージである場合です。</span><span class="sxs-lookup"><span data-stu-id="38c51-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="38c51-116">詳細については、「EOP で差出 [人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="38c51-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="38c51-117">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="38c51-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="38c51-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="38c51-118">0, 1</span></span>|<span data-ttu-id="38c51-119">スパム フィルターが、メッセージがスパムでないと判断しました。</span><span class="sxs-lookup"><span data-stu-id="38c51-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="38c51-120">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="38c51-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="38c51-121">5, 6</span><span class="sxs-lookup"><span data-stu-id="38c51-121">5, 6</span></span>|<span data-ttu-id="38c51-122">スパム フィルターがメッセージをスパムとしてマーク **した**</span><span class="sxs-lookup"><span data-stu-id="38c51-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="38c51-123">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="38c51-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="38c51-124">9 </span><span class="sxs-lookup"><span data-stu-id="38c51-124">9</span></span>|<span data-ttu-id="38c51-125">スパム フィルター処理によってメッセージが **信頼度が高いスパムとしてマークされた**</span><span class="sxs-lookup"><span data-stu-id="38c51-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="38c51-126">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="38c51-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="38c51-127">SCL 2、3、4、7、8 はスパム フィルター処理により使用されていない場合に確認できます。</span><span class="sxs-lookup"><span data-stu-id="38c51-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="38c51-128">メール フロー ルール (別名トランスポート ルール) は、メッセージに SCL をスタンプするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="38c51-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="38c51-129">メール フロー ルールを使用して SCL を設定する場合、値 5 または 6 は **Spam**に対してスパム フィルター処理をトリガーし、7、8、9 のいずれかの値によって高信頼スパムに対するスパム フィルター **処理がトリガーされます**。</span><span class="sxs-lookup"><span data-stu-id="38c51-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="38c51-130">詳細については、「メール フロー [ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="38c51-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="38c51-131">SCL と同様に、バルク アル クアマーク レベル (BCL) は、不正なバルク メール (グレー メール _とも呼ばれる) を識別します_。</span><span class="sxs-lookup"><span data-stu-id="38c51-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="38c51-132">BCL が高い場合、バルク メール メッセージが不合を不用意にする可能性が高いことを示します (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="38c51-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="38c51-133">スパム対策ポリシーで BCL しきい値を構成します。</span><span class="sxs-lookup"><span data-stu-id="38c51-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="38c51-134">詳細については[、「EOP で迷惑メール対策ポリシーを構成する」、「EOP でバル](configure-your-spam-filter-policies.md)ク コントライド レベル[(BCL)」を構成して](bulk-complaint-level-values.md)[、迷惑メール](what-s-the-difference-between-junk-email-and-bulk-email.md)とバルク メールの違いを確認してください。</span><span class="sxs-lookup"><span data-stu-id="38c51-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="38c51-135">![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 の小さいアイコン**</span><span class="sxs-lookup"><span data-stu-id="38c51-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="38c51-136">LinkedIn Learning が提供する **Microsoft 365**管理者および IT プロダッシー向けの無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="38c51-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
