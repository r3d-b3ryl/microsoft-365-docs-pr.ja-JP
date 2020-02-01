---
title: バルク苦情レベルの値、一括メール広告、BCL レベル、BCL のしくみ、BCL 評価、スパム対策、スパム対策ヘッダー、バルクメールフィルター、バルクメールの停止
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Office 365 での、バルク文句レベル (BCL) の値について説明します。
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599724"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="6b8c6-103">バルク苦情レベルの値</span><span class="sxs-lookup"><span data-stu-id="6b8c6-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="6b8c6-104">バルク メール業者によって、送信パターン、コンテンツ作成、およびリスト取得方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="6b8c6-105">中には、関連コンテンツを含む、必要なメッセージをサブスクライバーに送信する優良なバルク メール業者もいます。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="6b8c6-106">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="6b8c6-107">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="6b8c6-108">これらのバルク メール業者の種類を区別するために、バルク メール業者からのメッセージにバルク苦情レベル (BCL) 格付けが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="6b8c6-109">バルク メール業者のレベルに応じた 1 ～ 9 の BCL 格付け範囲が苦情を生み出す程度を表します。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="6b8c6-110">BCL が 9 の送信者は受信者からの苦情が多い可能性があるのに対して、BCL が 3 の送信者は受信者からの苦情が少ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="6b8c6-111">Microsoft では、内部ソースとサード パーティ ソースの両方を使用して、バルク メールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="6b8c6-112">このメッセージ ヘッダーの詳細については、「 [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="6b8c6-113">評価が9のバルクメールの場合、苦情が発生する可能性があるため、既定の BCL は7です。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="6b8c6-114">これは、メッセージが7になると、その後もメールが受け入れられないようになるまで、バルクメールは受け付けられることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="6b8c6-115">レーティングが低いほど、送信されるバルクメールは受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="6b8c6-116">ユーザーがで、仕事がバルクメールに依存しており、BCL が4に設定されている場合は、4より大きい BCL を使用したバルクメールは受け付けられません。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="6b8c6-117">BCL 値を使用して組織に必要なバルク フィルタリング レベルを設定するには、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="6b8c6-118">次の表では、現在使用されている BCL 値について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6b8c6-119">**BCL 値**</span><span class="sxs-lookup"><span data-stu-id="6b8c6-119">**BCL Value**</span></span>|<span data-ttu-id="6b8c6-120">**説明**</span><span class="sxs-lookup"><span data-stu-id="6b8c6-120">**Description**</span></span>|
|<span data-ttu-id="6b8c6-121">.0</span><span class="sxs-lookup"><span data-stu-id="6b8c6-121">0</span></span>|<span data-ttu-id="6b8c6-122">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="6b8c6-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="6b8c6-123">1, 2, 3</span></span>|<span data-ttu-id="6b8c6-124">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="6b8c6-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="6b8c6-125">4, 5, 6, 7</span></span>|<span data-ttu-id="6b8c6-126">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="6b8c6-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="6b8c6-127">8, 9</span></span>|<span data-ttu-id="6b8c6-128">メッセージは、多くの苦情を生成するバルク送信者から送信されます。</span><span class="sxs-lookup"><span data-stu-id="6b8c6-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
