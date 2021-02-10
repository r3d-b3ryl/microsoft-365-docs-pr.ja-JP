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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) フィルタリング プロセス中にキューに入れ、延期、返送されたメッセージに関する最も一般的な質問に対する回答を見つける。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165429"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="fbf0b-103">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="fbf0b-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fbf0b-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fbf0b-104">**Applies to**</span></span>
- [<span data-ttu-id="fbf0b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fbf0b-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="fbf0b-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fbf0b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="fbf0b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbf0b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fbf0b-108">このトピックでは、Exchange Online Protection (EOP) フィルタリング プロセス中にキューに入れ、保留、返送されたメッセージに関してよく寄せられる質問に対する回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="fbf0b-109">なぜメールはキューイングされるのですか?</span><span class="sxs-lookup"><span data-stu-id="fbf0b-109">Why is mail queuing?</span></span>

<span data-ttu-id="fbf0b-110">メール配信時に受信者のサーバーに接続できない場合、メッセージはキューイングされるか保留されます。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="fbf0b-111">ただし、受信者のネットワークから 500 番台のエラーが返された場合、メッセージは保留されません。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="fbf0b-112">メッセージはどのようなときに保留状態になるのですか?</span><span class="sxs-lookup"><span data-stu-id="fbf0b-112">How does a message become deferred?</span></span>

<span data-ttu-id="fbf0b-113">受信者のサーバーに接続できず、受信者のサーバーから接続タイムアウトや接続拒否、400 番台のエラーなどの "一時的なエラー" が返された場合、メッセージは保留されます。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="fbf0b-114">500 番台のエラーなどの永続的なエラーが返された場合、メッセージは送信者に戻されます。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="fbf0b-115">メッセージが保留される期間と再試行の間隔はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="fbf0b-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="fbf0b-116">保留状態のメッセージはキューに 1 日間残ります。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="fbf0b-117">メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="fbf0b-118">最初の数回の延期は 15 分以下で、後続の再試行 (約 50 分ほど) で、複数回の再試行の間隔を最大 60 分に増やします。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="fbf0b-119">キューのサイズや内部メッセージの優先度など、複数の変数を考慮して、間隔の拡張は動的です。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="fbf0b-120">基本的には、開始は 15 分 (以下) です。その後、次の数時間でそこから最大 60 分まで展開します。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="fbf0b-121">メール サーバーが復元された後、キューイングされたメッセージはどのように配信されますか?</span><span class="sxs-lookup"><span data-stu-id="fbf0b-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="fbf0b-122">メール サーバーが復元した後、キューに格納されたすべてのメッセージは、サーバーを利用できなくなったときに受信およびキューに格納された順序で自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="fbf0b-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
