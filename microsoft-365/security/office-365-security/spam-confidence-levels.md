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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のメッセージに適用される Spam Confidence Level (SCL) について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167157"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="2b718-103">EOP の Spam Confidence Level (SCL)</span><span class="sxs-lookup"><span data-stu-id="2b718-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="2b718-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2b718-104">**Applies to**</span></span>
- [<span data-ttu-id="2b718-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2b718-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="2b718-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="2b718-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="2b718-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b718-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2b718-108">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、受信メッセージは EOP のスパム フィルターを通過し、スパム スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2b718-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="2b718-109">このスコアは、X ヘッダー内のメッセージに追加される個々の Spam Confidence Level (SCL) にマップされます。</span><span class="sxs-lookup"><span data-stu-id="2b718-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="2b718-110">SCL が高いほど、メッセージはスパムである可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="2b718-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="2b718-111">EOP は SCL に基づいてメッセージに対してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b718-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="2b718-112">SCL の意味と、メッセージに対して実行される既定のアクションを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2b718-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="2b718-113">スパム フィルターの条件に基づいてメッセージに対して実行できるアクションの詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b718-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="2b718-114">SCL</span><span class="sxs-lookup"><span data-stu-id="2b718-114">SCL</span></span>|<span data-ttu-id="2b718-115">定義</span><span class="sxs-lookup"><span data-stu-id="2b718-115">Definition</span></span>|<span data-ttu-id="2b718-116">既定のアクション</span><span class="sxs-lookup"><span data-stu-id="2b718-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="2b718-117">-1</span><span class="sxs-lookup"><span data-stu-id="2b718-117">-1</span></span>|<span data-ttu-id="2b718-118">メッセージはスパム フィルター処理をスキップしました。</span><span class="sxs-lookup"><span data-stu-id="2b718-118">The message skipped spam filtering.</span></span> <span data-ttu-id="2b718-119">たとえば、メッセージが差出人セーフ リストから送信されたメッセージ、安全な受信者に送信されたメッセージ、または IP 許可一覧の電子メール 送信元サーバーから送信されたメッセージなどです。</span><span class="sxs-lookup"><span data-stu-id="2b718-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="2b718-120">詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2b718-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="2b718-121">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="2b718-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="2b718-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="2b718-122">0, 1</span></span>|<span data-ttu-id="2b718-123">スパム フィルターによって、メッセージがスパムではないと判断された。</span><span class="sxs-lookup"><span data-stu-id="2b718-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="2b718-124">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="2b718-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="2b718-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="2b718-125">5, 6</span></span>|<span data-ttu-id="2b718-126">スパム フィルターによってメッセージがスパムとしてマーク **された**</span><span class="sxs-lookup"><span data-stu-id="2b718-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="2b718-127">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="2b718-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="2b718-128">9 </span><span class="sxs-lookup"><span data-stu-id="2b718-128">9</span></span>|<span data-ttu-id="2b718-129">スパム フィルターがメッセージを信頼度の高いスパム **としてマークしました**</span><span class="sxs-lookup"><span data-stu-id="2b718-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="2b718-130">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="2b718-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="2b718-131">SCL 2、3、4、7、および 8 はスパム フィルタリングで使用されません。</span><span class="sxs-lookup"><span data-stu-id="2b718-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="2b718-132">メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、メッセージに SCL をスタンプできます。</span><span class="sxs-lookup"><span data-stu-id="2b718-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="2b718-133">メール フロー ルールを使用して SCL を設定する場合、値 5 または 6 は **スパム** のスパム フィルター処理をトリガーし、値 7、8、または 9 は信頼度の高いスパムに対するスパム フィルター処理をトリガー **します。**</span><span class="sxs-lookup"><span data-stu-id="2b718-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="2b718-134">詳細については、「メール フロー ルール [を使用して、メッセージの Spam Confidence Level (SCL) を設定する」を参照してください](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="2b718-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="2b718-135">SCL と同様に、バルク苦情レベル (BCL) は、悪いバルク メール (グレー メールとも呼ばれる) _を識別します_。</span><span class="sxs-lookup"><span data-stu-id="2b718-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="2b718-136">BCL が高いほど、バルク メール メッセージが好ましくない内容である可能性が高い (したがって、スパムである可能性が高い) ことを示します。</span><span class="sxs-lookup"><span data-stu-id="2b718-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="2b718-137">BCL しきい値は、スパム対策ポリシーで構成します。</span><span class="sxs-lookup"><span data-stu-id="2b718-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="2b718-138">詳細については[、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」、EOP のバルク苦情レベル[(BCL)、](bulk-complaint-level-values.md)迷惑メールとバルク メールの違いを参照[してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="2b718-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="2b718-139">![LinkedIn Learning の ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 の** 新機能の短いアイコン</span><span class="sxs-lookup"><span data-stu-id="2b718-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="2b718-140">LinkedIn Learning によって **提供される、Microsoft 365** 管理者と IT プロ向け無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b718-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
