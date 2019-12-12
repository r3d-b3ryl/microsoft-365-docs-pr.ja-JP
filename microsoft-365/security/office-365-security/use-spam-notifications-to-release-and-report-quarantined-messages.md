---
title: Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 管理者がユーザーの通知を有効にした場合、スパム、大量、またはフィッシングメッセージとして識別されたメールボックスに送信されたメッセージを一覧表示する通知メッセージを受け取ります。 通知された後にメッセージを解放または報告することができます。
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971365"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="7dbf1-104">Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="7dbf1-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="7dbf1-105">管理者がユーザーのスパム通知を有効にした場合、スパムとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="7dbf1-106">管理者がこの機能を有効にする場合は、[既定のスパム対策ポリシーを変更](configure-your-spam-filter-policies.md)するときにオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="7dbf1-107">受信するメッセージには、スパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻または UTC) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="7dbf1-108">一覧には、各メッセージの次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="7dbf1-109">**送信者**検疫済みメッセージの送信名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="7dbf1-110">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="7dbf1-111">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="7dbf1-112">以下に、検疫済みメッセージを使用して実行できるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="7dbf1-113">[**送信者をブロック**する] Office 365 で、受信拒否リストに送信者を追加する場合。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="7dbf1-114">プレビューやリリースなどの他のアクションを実行する場合は、セキュリティ/コンプライアンスセンター内の検疫ポータルに移動することを**確認**してください。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="7dbf1-115">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-115">Be aware of the following:</span></span>

- <span data-ttu-id="7dbf1-116">メールフロールールに一致したために検疫されたメッセージは、ユーザーの検疫済みメッセージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="7dbf1-117">スパム検疫済みメッセージのみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-117">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="7dbf1-118">メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="7dbf1-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
