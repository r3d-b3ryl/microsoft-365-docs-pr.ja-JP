---
title: バルク苦情レベルの値
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
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
description: Office 365 の一括コンプライアンスレベル (BCL) の値について説明します。
ms.openlocfilehash: 82c006f05ce3d37ff23ca1e522b653bd26efeed8
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035570"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="26efd-103">Office 365 のバルク苦情レベル (BCL)</span><span class="sxs-lookup"><span data-stu-id="26efd-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="26efd-104">バルクメール広告は、送信パターン、コンテンツ作成、受信者の取得方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="26efd-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="26efd-105">適切なバルクメールを使用して、必要なコンテンツを含むメッセージをサブスクライバーに送信することができます。</span><span class="sxs-lookup"><span data-stu-id="26efd-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="26efd-106">このようなメッセージが受信者の苦情につながることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="26efd-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="26efd-107">他のバルク メール業者は、スパムによく似た未承諾のメッセージを送りつけ、多くの受信者の苦情を生んでいます。</span><span class="sxs-lookup"><span data-stu-id="26efd-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="26efd-108">一括メールプログラムからのメッセージは、バルクメールまたはグレーメールと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="26efd-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="26efd-109">さまざまな種類のバルクメールボックスからのメッセージを区別するために、バルクメール業者からの受信メール (exchange online またはスタンドアロンの exchange Online Protection (EOP) が Exchange Online メールボックスを使用しない場合) には、X ヘッダー内のメッセージに追加されるバルク苦情レベル (BCL) が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="26efd-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="26efd-110">BCL は、スパムとしてメッセージを識別するために使用される[スパム信頼レベル (SCL)](spam-confidence-levels.md)に似ています。</span><span class="sxs-lookup"><span data-stu-id="26efd-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="26efd-111">より多くの BCL は、バルクメッセージが苦情を生み出している可能性が高いことを示します (つまり、スパムである可能性が高くなります)。</span><span class="sxs-lookup"><span data-stu-id="26efd-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="26efd-112">Microsoft では、内部ソースとサードパーティソースの両方を使用して、バルクメールを識別し、適切な BCL を決定します。</span><span class="sxs-lookup"><span data-stu-id="26efd-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="26efd-113">スパムフィルターは、BCL しきい値 (既定値または指定した値) に基づいてメッセージを**バルクメール**としてマークし、メッセージに対して指定された処理を実行します (既定のアクションは、メッセージを受信者の迷惑メールフォルダーに配信します)。</span><span class="sxs-lookup"><span data-stu-id="26efd-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="26efd-114">詳細については、「[スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」および「[迷惑メールとバルクメールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26efd-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="26efd-115">次の表で、BCL のしきい値について説明します。</span><span class="sxs-lookup"><span data-stu-id="26efd-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="26efd-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="26efd-116">**BCL**</span></span>|<span data-ttu-id="26efd-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="26efd-117">**Description**</span></span>|
|<span data-ttu-id="26efd-118">.0</span><span class="sxs-lookup"><span data-stu-id="26efd-118">0</span></span>|<span data-ttu-id="26efd-119">バルク送信者からのメッセージではありません。</span><span class="sxs-lookup"><span data-stu-id="26efd-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="26efd-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="26efd-120">1, 2, 3</span></span>|<span data-ttu-id="26efd-121">苦情がほとんどないバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="26efd-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="26efd-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="26efd-122">4, 5, 6, 7</span></span>|<span data-ttu-id="26efd-123">苦情の件数がさまざまなバルク送信者からのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="26efd-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="26efd-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="26efd-124">8, 9</span></span>|<span data-ttu-id="26efd-125">メッセージは、多くの苦情を生成するバルク送信者から送信されます。</span><span class="sxs-lookup"><span data-stu-id="26efd-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
