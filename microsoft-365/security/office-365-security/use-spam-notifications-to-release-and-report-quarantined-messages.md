---
title: Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c9cd0849f826e66411695a3758f271ec70d24c9b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598024"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="3a05c-104">Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="3a05c-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="3a05c-105">管理者がユーザーのスパム通知を有効にした場合、スパムとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3a05c-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="3a05c-106">管理者がこの機能を有効にする場合は、[既定のスパム対策ポリシーを変更](configure-your-spam-filter-policies.md)するときにオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a05c-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="3a05c-107">受信するメッセージには、スパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻または UTC) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3a05c-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="3a05c-108">一覧には、各メッセージの次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a05c-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="3a05c-109">**送信者**検疫済みメッセージの送信名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="3a05c-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="3a05c-110">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="3a05c-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="3a05c-111">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="3a05c-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="3a05c-112">以下に、検疫済みメッセージを使用して実行できるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="3a05c-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="3a05c-113">[**送信者をブロック**する] Office 365 で、受信拒否リストに送信者を追加する場合。</span><span class="sxs-lookup"><span data-stu-id="3a05c-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="3a05c-114">メッセージがスパムではなく、Office 365 がメールボックスにメッセージを送信する場合は、**リリースを解放**します。</span><span class="sxs-lookup"><span data-stu-id="3a05c-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="3a05c-115">プレビューやリリースなどの他のアクションを実行する場合は、セキュリティ/コンプライアンスセンター内の検疫ポータルに移動することを**確認**してください。</span><span class="sxs-lookup"><span data-stu-id="3a05c-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="3a05c-116">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="3a05c-116">Be aware of the following:</span></span>

- <span data-ttu-id="3a05c-117">メールフロールールに一致したために検疫されたメッセージは、ユーザーの検疫済みメッセージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="3a05c-117">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="3a05c-118">スパム検疫済みメッセージのみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="3a05c-118">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="3a05c-119">メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="3a05c-119">You can only release a message and report it as a false positive (not junk) once.</span></span>
