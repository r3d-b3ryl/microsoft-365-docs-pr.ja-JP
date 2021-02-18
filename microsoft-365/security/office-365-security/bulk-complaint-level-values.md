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
ms.openlocfilehash: c68314cf992d39a105293955b6fade7b1a2bec56
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289903"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="61141-103">EOP でのバルク苦情レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="61141-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61141-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="61141-104">**Applies to**</span></span>
- [<span data-ttu-id="61141-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61141-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="61141-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="61141-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="61141-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61141-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="61141-108">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はバルク メールラーからの受信メッセージに一括準拠レベル (BCL) を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="61141-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="61141-109">BCL は X ヘッダー内のメッセージに追加され、メッセージをスパムとして識別するために使用される [SCL (Spam Confidence Level)](spam-confidence-levels.md) に似ています。</span><span class="sxs-lookup"><span data-stu-id="61141-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="61141-110">BCL が高いほど、バルク メッセージが苦情を発生する可能性が高くなります (したがって、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="61141-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="61141-111">Microsoft は、内部ソースとサード パーティソースの両方を使用してバルク メールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="61141-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="61141-112">バルク メールは、送信パターン、コンテンツの作成、受信者の取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="61141-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="61141-113">優れたバルク メール担当者は、関連するコンテンツを含む必要なメッセージをサブスクライバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="61141-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="61141-114">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="61141-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="61141-115">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="61141-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="61141-116">バルク メールのメッセージは、バルク メールまたはグレー メールと呼ばれるものになります。</span><span class="sxs-lookup"><span data-stu-id="61141-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="61141-117">スパム フィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージをバルク メールとしてマークし、メッセージに対して指定のアクションを実行します (既定のアクションは、受信者の迷惑メール フォルダーにメッセージを配信します)。 </span><span class="sxs-lookup"><span data-stu-id="61141-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="61141-118">詳細については、「スパム対策ポリシー [を構成](configure-your-spam-filter-policies.md) する」と「迷惑メールとバルク メールの違い [」を参照してください。](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="61141-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="61141-119">BCL のしきい値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="61141-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="61141-120">BCL</span><span class="sxs-lookup"><span data-stu-id="61141-120">BCL</span></span>|<span data-ttu-id="61141-121">説明</span><span class="sxs-lookup"><span data-stu-id="61141-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="61141-122">0</span><span class="sxs-lookup"><span data-stu-id="61141-122">0</span></span>|<span data-ttu-id="61141-123">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="61141-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="61141-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="61141-124">1, 2, 3</span></span>|<span data-ttu-id="61141-125">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="61141-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="61141-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="61141-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="61141-127">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="61141-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="61141-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="61141-128">8, 9</span></span>|<span data-ttu-id="61141-129">メッセージは、多数の苦情を生成するバルク 送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="61141-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="61141-130"><sup>\*</sup> これは、スパム対策ポリシーで使用される既定のしきい値です。</span><span class="sxs-lookup"><span data-stu-id="61141-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
