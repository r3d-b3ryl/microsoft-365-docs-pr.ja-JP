---
title: EOP のキューイング、保留、返送されるメッセージに関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) のフィルター処理中にキューに入れられたメッセージ、延期、または返送されたメッセージに関してよく寄せられる質問に対する回答を示します。
ms.openlocfilehash: 4ae38e871c0d6e4321bd7586c5cfd0bea3aeef81
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202941"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="8e6b2-103">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="8e6b2-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8e6b2-104">このトピックでは、Exchange Online Protection (EOP) のフィルター処理中にキュー、延期、または返送されたメッセージに関してよく寄せられる質問への回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="8e6b2-105">なぜメールはキューイングされるのですか?</span><span class="sxs-lookup"><span data-stu-id="8e6b2-105">Why is mail queuing?</span></span>

<span data-ttu-id="8e6b2-106">メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="8e6b2-107">ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="8e6b2-108">メッセージはどのようなときに保留状態になるのですか?</span><span class="sxs-lookup"><span data-stu-id="8e6b2-108">How does a message become deferred?</span></span>

<span data-ttu-id="8e6b2-109">受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="8e6b2-110">500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="8e6b2-111">メッセージが保留される期間と再試行の間隔はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="8e6b2-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="8e6b2-112">延期されたメッセージは、1日の間、キューに残ります。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="8e6b2-113">メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="8e6b2-114">最初のいくつかの deferrals は15分以内で、以降の再試行 (次の半周期以上) では、複数回の再試行の間隔が最大60分に増加します。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="8e6b2-115">間隔の期間の展開は動的であり、キューのサイズや内部メッセージの優先度などの複数の変数を考慮します。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="8e6b2-116">基本的には、15分 (またはそれ以下) から開始します。その後、次の数時間で最大60分に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="8e6b2-117">メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?</span><span class="sxs-lookup"><span data-stu-id="8e6b2-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="8e6b2-118">メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="8e6b2-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
