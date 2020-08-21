---
title: バルク コンプト レベル値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用される一括コンプライアンス レベル (BCL) 値について学習できます。
ms.openlocfilehash: e24c0c97afcca2e7aa014d929d7b2131c6a2d074
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827435"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="165b4-103">EOP のバルク コンプト レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="165b4-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="165b4-104">Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP はバルク メール サーバーからの受信メッセージに対してバルクに対応するレベル (BCL) を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="165b4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="165b4-105">BCL は X-ヘッダーのメッセージに追加され、メッセージをスパムとして [識別するために使用される Spam Confidence Level (SCL)](spam-confidence-levels.md) に似ています。</span><span class="sxs-lookup"><span data-stu-id="165b4-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="165b4-106">BCL が高い場合、バルク メッセージでは不合意がある (したがって、スパムである可能性が高い) ことを示します。</span><span class="sxs-lookup"><span data-stu-id="165b4-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="165b4-107">Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="165b4-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="165b4-108">バルク メール ツールでは、送信パターン、コンテンツ作成、受信者取得方法が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="165b4-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="165b4-109">バルク メールを送信する優れた大会議を送付者は、関連するコンテンツを含む必要なメッセージをユーザーのサブスクライバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="165b4-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="165b4-110">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="165b4-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="165b4-111">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="165b4-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="165b4-112">バルク メール システムからのメッセージは、バルク メールまたは灰色メールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="165b4-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="165b4-113">スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいて、メッセージに対してバルク メールのマークを付け、指定されたアクションをメッセージに対して実行します (既定の操作では、メッセージは受信者の迷惑メール フォルダーに配信されます)。 **Bulk email**</span><span class="sxs-lookup"><span data-stu-id="165b4-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="165b4-114">詳細については、「スパム [対策ポリシーを構成する」、](configure-your-spam-filter-policies.md) および [迷惑メールとバルク メールの違いを確認する](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="165b4-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="165b4-115">次の表で、BCL しきい値について説明します。</span><span class="sxs-lookup"><span data-stu-id="165b4-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="165b4-116">BCL</span><span class="sxs-lookup"><span data-stu-id="165b4-116">BCL</span></span>|<span data-ttu-id="165b4-117">説明</span><span class="sxs-lookup"><span data-stu-id="165b4-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="165b4-118">0</span><span class="sxs-lookup"><span data-stu-id="165b4-118">0</span></span>|<span data-ttu-id="165b4-119">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="165b4-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="165b4-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="165b4-120">1, 2, 3</span></span>|<span data-ttu-id="165b4-121">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="165b4-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="165b4-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="165b4-122">4, 5, 6, 7</span></span>|<span data-ttu-id="165b4-123">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="165b4-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="165b4-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="165b4-124">8, 9</span></span>|<span data-ttu-id="165b4-125">メッセージは、探しの結果が大きいバルク送信者からのものです。</span><span class="sxs-lookup"><span data-stu-id="165b4-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
