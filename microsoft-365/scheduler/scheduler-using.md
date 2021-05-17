---
title: スケジューラを使用したMicrosoft 365
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: スケジューラを使用してMicrosoft 365。
ms.openlocfilehash: 2987861856611ae4698f49dc8123a5cf733074ef
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286204"
---
# <a name="how-to-use-scheduler-for-microsoft-365"></a><span data-ttu-id="e85bf-103">スケジューラを使用してユーザーにMicrosoft 365</span><span class="sxs-lookup"><span data-stu-id="e85bf-103">How to use Scheduler for Microsoft 365</span></span>

<span data-ttu-id="e85bf-104">Cortana は自然言語を理解しています。</span><span class="sxs-lookup"><span data-stu-id="e85bf-104">Cortana understands natural language.</span></span> <span data-ttu-id="e85bf-105">他 cortana@yourdomain.com と一緒にメールにユーザーを含め、そこから Cortana が引き継ぐ。</span><span class="sxs-lookup"><span data-stu-id="e85bf-105">Include cortana@yourdomain.com in an email with other attendees, and Cortana will take over from there.</span></span> <span data-ttu-id="e85bf-106">Cortana は会議の時間を確認する電子メール通知を送信し、進捗状況を最新の状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="e85bf-106">Cortana will send email notifications confirming meeting times and keep you up to date on progress.</span></span>

<span data-ttu-id="e85bf-107">スケジューラを使用するには、会議に参加するユーザーに加えて、Cortana のメール アドレスをメールに追加します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-107">To use Scheduler, add Cortana’s email address to your email in addition to the people you want to meeting with.</span></span> <span data-ttu-id="e85bf-108">Cortana と他の出席者へのメールで、自然言語を使用して会議をスケジュールする Cortana に通知します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-108">In your email to Cortana and the other attendees, tell Cortana to schedule a meeting using natural language.</span></span>  

## <a name="when-to-use-scheduler"></a><span data-ttu-id="e85bf-109">スケジューラを使用する場合</span><span class="sxs-lookup"><span data-stu-id="e85bf-109">When to use Scheduler?</span></span>

- <span data-ttu-id="e85bf-110">**内部出席者との会議のスケジュール設定** Cortana を使用して、5 人以下の出席者で会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="e85bf-110">**Scheduling meetings with internal attendees** Use Cortana to schedule your meetings with 5 or fewer attendees.</span></span> <span data-ttu-id="e85bf-111">Cortana には、予定表内の他のユーザーに表示される空き時間情報Outlookがあります。</span><span class="sxs-lookup"><span data-stu-id="e85bf-111">Cortana has the same access to free/busy information that you see for others in Outlook calendar.</span></span> <span data-ttu-id="e85bf-112">すべてのユーザーに対して動作する時間を選択し、代理で招待を送信します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-112">It will pick a time that works for everyone and send an invite on your behalf.</span></span> <span data-ttu-id="e85bf-113">Cortana は、スケジュールTeams会議を自動的に有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e85bf-113">Cortana will automatically Teams-enable all the meetings that it schedules.</span></span> <span data-ttu-id="e85bf-114">CC 行に参加しているユーザーは、招待をオプションの出席者として受け取る予定です。</span><span class="sxs-lookup"><span data-stu-id="e85bf-114">Anyone on the CC line will receive the invite as an optional attendee.</span></span>  

- <span data-ttu-id="e85bf-115">**外部出席者との会議のスケジュール設定**</span><span class="sxs-lookup"><span data-stu-id="e85bf-115">**Scheduling meetings with external attendees**</span></span>  
<span data-ttu-id="e85bf-116">Cortana は、外部の招待者と通信して、会える時間を交渉します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-116">Cortana communicates with external invitees to negotiate times that you are available to meet.</span></span> <span data-ttu-id="e85bf-117">会議の時間を確認した後、Cortana は出席者に招待を送信し、会議がスケジュールされたと通知します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-117">After confirming a time to meet, Cortana sends an invite to attendees and notifies you that the meeting has been scheduled.</span></span>

## <a name="what-to-say-to-cortana"></a><span data-ttu-id="e85bf-118">Cortana に対して何を言いますか?</span><span class="sxs-lookup"><span data-stu-id="e85bf-118">What to say to Cortana?</span></span>

<span data-ttu-id="e85bf-119">Cortana は自然言語を理解していますが、簡潔な言語をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e85bf-119">Cortana understands natural language, but concise language is recommended.</span></span> 

<span data-ttu-id="e85bf-120">会議を要求するには、次のパターンを使用します。[時間の長さ] 会議 [時間枠] をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="e85bf-120">Use the following pattern to request a meeting: Schedule a [length of time] meeting [time frame].</span></span>  

- <span data-ttu-id="e85bf-121">「来週、30 分間の会議をスケジュールする」</span><span class="sxs-lookup"><span data-stu-id="e85bf-121">“Schedule a 30-minute meeting next week.”</span></span>  
- <span data-ttu-id="e85bf-122">「1 月に会う 1 時間を見つける」</span><span class="sxs-lookup"><span data-stu-id="e85bf-122">“Find 1 hour for us to meet in January.”</span></span> 
- <span data-ttu-id="e85bf-123">"インド標準時に動作する 5 月の最初の週 45 分を検索します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-123">“Find 45 minutes the first week of May that works for India Standard Time.”</span></span> 

<span data-ttu-id="e85bf-124">時間範囲を指定しない場合、Cortana は会議を翌日に予約します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-124">If you don't specify a time range, Cortana will book the meeting as soon as the next business day.</span></span>

## <a name="scheduling-across-multiple-time-zones"></a><span data-ttu-id="e85bf-125">複数のタイム ゾーンでのスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="e85bf-125">Scheduling across multiple time zones</span></span>

<span data-ttu-id="e85bf-126">複数のタイム ゾーン会議を要求するには、次のパターンを使用します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-126">Use the following pattern to request a multi-time zone meeting: "Schedule a [length of time] meeting in [time frame] that works for [time zone]."</span></span> 

<span data-ttu-id="e85bf-127">Cortana に最初のメールで要求した場合、Cortana は別のタイム ゾーンの出席者に対応します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-127">Cortana will accommodate attendees in another time zone if you request it in the first email to Cortana.</span></span>  

<span data-ttu-id="e85bf-128">Cortana に最初の要求を送信した後、タイム ゾーンを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e85bf-128">You cannot change time zone(s) after sending the initial request to Cortana.</span></span> <span data-ttu-id="e85bf-129">一部のタイム ゾーンの省略形は同じで、最適な結果を得る場合は、完全なタイム ゾーン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-129">As some time zone abbreviations are the same, use the full time zone name for best results.</span></span>  

## <a name="organizer-guidance"></a><span data-ttu-id="e85bf-130">開催者のガイダンス</span><span class="sxs-lookup"><span data-stu-id="e85bf-130">Organizer guidance</span></span>

<span data-ttu-id="e85bf-131">場合によっては、Cortana が開催者としてガイダンスを求める場合があります。</span><span class="sxs-lookup"><span data-stu-id="e85bf-131">Occasionally, Cortana may ask you for guidance as the organizer.</span></span> <span data-ttu-id="e85bf-132">Cortana のメールの指示に従い、Cortana メールの返信ボタンを使用して返信します。</span><span class="sxs-lookup"><span data-stu-id="e85bf-132">Follow the directions in Cortana’s email and reply using the reply buttons in Cortana emails.</span></span>

## <a name="reschedule-or-cancel"></a><span data-ttu-id="e85bf-133">再スケジュールまたはキャンセル</span><span class="sxs-lookup"><span data-stu-id="e85bf-133">Reschedule or Cancel</span></span>

<span data-ttu-id="e85bf-134">スケジュールを変更またはキャンセルする必要がある場合は、会議に関して Cortana とスレッド内の電子メールに返信し、"Reschedule" または "Cancel" を要求してください。</span><span class="sxs-lookup"><span data-stu-id="e85bf-134">If you need to reschedule or cancel, just reply to an email in the thread with Cortana regarding the meeting and ask to “Reschedule” or “Cancel.”</span></span> 

> [!NOTE]
> <span data-ttu-id="e85bf-135">Cortana は、スケジューラによってスケジュールされていない会議をスケジュール変更またはキャンセルできない。</span><span class="sxs-lookup"><span data-stu-id="e85bf-135">Cortana can't reschedule or cancel meetings that were not scheduled by Scheduler.</span></span>  
