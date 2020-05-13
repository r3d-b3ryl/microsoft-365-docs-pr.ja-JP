---
title: バルク苦情レベルの値
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) で使用されるバルクコンプライアンスレベル (BCL) の値について説明しています。
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209609"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="29ac4-103">EOP でのバルク苦情レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="29ac4-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="29ac4-104">Exchange online メールボックスを使用しない Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織内のメールボックスを持つ Microsoft 365 組織では、EOP はバルクメールボックスからの受信メッセージに一括準拠レベル (BCL) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="29ac4-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="29ac4-105">BCL は X ヘッダー内のメッセージに追加され、スパムとしてメッセージを識別するために使用される[スパム信頼度 (SCL)](spam-confidence-levels.md)に似ています。</span><span class="sxs-lookup"><span data-stu-id="29ac4-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="29ac4-106">より多くの BCL は、バルクメッセージが苦情を生み出している可能性が高いことを示します (つまり、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="29ac4-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="29ac4-107">Microsoft では、内部ソースとサードパーティソースの両方を使用して、バルクメールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="29ac4-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="29ac4-108">バルクメール広告は、送信パターン、コンテンツ作成、受信者の取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="29ac4-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="29ac4-109">適切なバルクメール広告は、該当するコンテンツを持つ必要なメッセージをサブスクライバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="29ac4-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="29ac4-110">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="29ac4-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="29ac4-111">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="29ac4-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="29ac4-112">バルクメール送信からのメッセージは、バルクメールまたはグレーメールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="29ac4-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="29ac4-113">スパムフィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージを**バルクメール**としてマークし、メッセージに対して指定された処理を実行します (既定のアクションは、メッセージを受信者の迷惑メールフォルダーに配信します)。</span><span class="sxs-lookup"><span data-stu-id="29ac4-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="29ac4-114">詳細については、「[スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29ac4-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="29ac4-115">次の表で、BCL のしきい値について説明します。</span><span class="sxs-lookup"><span data-stu-id="29ac4-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="29ac4-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="29ac4-116">**BCL**</span></span>|<span data-ttu-id="29ac4-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="29ac4-117">**Description**</span></span>|
|<span data-ttu-id="29ac4-118">.0</span><span class="sxs-lookup"><span data-stu-id="29ac4-118">0</span></span>|<span data-ttu-id="29ac4-119">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="29ac4-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="29ac4-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="29ac4-120">1, 2, 3</span></span>|<span data-ttu-id="29ac4-121">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="29ac4-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="29ac4-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="29ac4-122">4, 5, 6, 7</span></span>|<span data-ttu-id="29ac4-123">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="29ac4-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="29ac4-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="29ac4-124">8, 9</span></span>|<span data-ttu-id="29ac4-125">メッセージは、多くの苦情を生成するバルク送信者から送信されます。</span><span class="sxs-lookup"><span data-stu-id="29ac4-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
