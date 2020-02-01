---
title: エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '検疫済みメールに関するエンドユーザーのスパム通知メッセージを管理者から取得したユーザーは、これらのメッセージに対してこれらの操作を行うことができます。 '
ms.openlocfilehash: 4d53e4866733ba0d3de96f068297a342c134e5ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598084"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="b4746-103">エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="b4746-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="b4746-p101">管理者がエンドユーザーのスパム通知を有効にした場合、ユーザーは、自分のメールボックス宛てに送信されたメッセージのうち、スパムと特定されて検疫されたメッセージがリストされている通知メッセージを受信します。このメッセージには、列挙されたスパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻 (UTC)) が含まれています。このリストで、各メッセージに関する以下の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b4746-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span>

- <span data-ttu-id="b4746-107">**Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="b4746-107">**Sender**: The sender name and email address of the quarantined message.</span></span>

- <span data-ttu-id="b4746-108">**Subject**: 検疫されたメッセージの件名のテキスト。</span><span class="sxs-lookup"><span data-stu-id="b4746-108">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="b4746-109">**日付**: メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="b4746-109">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="b4746-110">**Size**: 検疫済みメッセージのサイズをキロバイト (kb) 単位で示します。</span><span class="sxs-lookup"><span data-stu-id="b4746-110">**Size**: The size of the quarantined message, in kilobytes (KBs).</span></span>

<span data-ttu-id="b4746-111">各メッセージに対して次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4746-111">You can perform the following actions on each message:</span></span>

- <span data-ttu-id="b4746-112">**[受信トレイへの解放**]: このリンクをクリックすると、メッセージが受信トレイに送信されます。これを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b4746-112">**Release to Inbox**: Clicking this link sends the message to your inbox where you can view it.</span></span>

- <span data-ttu-id="b4746-113">**迷惑メールではないと報告**: このリンクをクリックすると、メッセージのコピーが分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b4746-113">**Report as Not Junk**: Clicking this link sends a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="b4746-114">スパム チームはメッセージの評価と分析を行い、分析結果に応じてスパム対策フィルター ルールを調整し、そのメッセージの通過を許可します。</span><span class="sxs-lookup"><span data-stu-id="b4746-114">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span>

> [!NOTE]
> <span data-ttu-id="b4746-115">メールフロールール (とも呼ばれます) が一致したために検疫されたメッセージは、エンドユーザースパム検疫済みメッセージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="b4746-115">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages.</span></span> <span data-ttu-id="b4746-116">スパム検疫済みメッセージのみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="b4746-116">Only spam-quarantined messages are listed.</span></span> <br/><br/>  <span data-ttu-id="b4746-117">メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="b4746-117">You can only release a message and report it as a false positive (not junk) once.</span></span>
