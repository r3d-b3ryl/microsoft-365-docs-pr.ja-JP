---
title: バルク苦情レベルの値
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
description: 管理者は、Exchange Online Protection (EOP) で使用される一括コンプライアンス レベル (BCL) の値について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 403f79a1ce81ae13a23aa77f4cca7654939d7814
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165969"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="e0a0c-103">EOP でのバルク苦情レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="e0a0c-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0a0c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e0a0c-104">**Applies to**</span></span>
- [<span data-ttu-id="e0a0c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0a0c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="e0a0c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e0a0c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e0a0c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0a0c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e0a0c-108">Exchange Online または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はバルク メールラーからの受信メッセージに一括準拠レベル (BCL) を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="e0a0c-109">BCL は X ヘッダー内のメッセージに追加され、メッセージをスパムとして識別するために使用される [SCL (Spam Confidence Level)](spam-confidence-levels.md) に似ています。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="e0a0c-110">BCL が高いほど、バルク メッセージが苦情を発生する可能性が高くなります (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="e0a0c-111">Microsoft は、内部ソースとサード パーティソースの両方を使用してバルク メールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="e0a0c-112">バルク メール担当者は、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="e0a0c-113">優れたバルク メール担当者は、関連するコンテンツを含む必要なメッセージをサブスクライバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="e0a0c-114">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="e0a0c-115">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="e0a0c-116">バルク メールのメッセージは、バルク メールまたはグレー メールと呼ばれるものになります。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="e0a0c-117">スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージをバルク メールとしてマークし、メッセージに対して指定のアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。 </span><span class="sxs-lookup"><span data-stu-id="e0a0c-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="e0a0c-118">詳細については、「スパム対策ポリシー [を構成する](configure-your-spam-filter-policies.md) 」と「迷惑メールとバルク メールの違い [」を参照してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="e0a0c-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="e0a0c-119">BCL のしきい値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="e0a0c-120">BCL</span><span class="sxs-lookup"><span data-stu-id="e0a0c-120">BCL</span></span>|<span data-ttu-id="e0a0c-121">説明</span><span class="sxs-lookup"><span data-stu-id="e0a0c-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="e0a0c-122">0</span><span class="sxs-lookup"><span data-stu-id="e0a0c-122">0</span></span>|<span data-ttu-id="e0a0c-123">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="e0a0c-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="e0a0c-124">1, 2, 3</span></span>|<span data-ttu-id="e0a0c-125">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="e0a0c-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0a0c-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="e0a0c-127">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="e0a0c-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="e0a0c-128">8, 9</span></span>|<span data-ttu-id="e0a0c-129">メッセージは、多数の苦情を生成するバルク 送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="e0a0c-130"><sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。</span><span class="sxs-lookup"><span data-stu-id="e0a0c-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
