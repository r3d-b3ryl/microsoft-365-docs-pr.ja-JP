---
title: Office 365 でメール メッセージを検疫する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルク、フィッシングメール、マルウェアとしてフィルター処理された受信メールメッセージを後で確認するために保持することができます。
ms.openlocfilehash: f7669f69abb711d71362057f2019b0dd7e30443b
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021853"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="7ecaa-103">Office 365 でメール メッセージを検疫する</span><span class="sxs-lookup"><span data-stu-id="7ecaa-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="7ecaa-104">Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含むメール、および指定されたメールフロールール (trasport ルールとも呼ばれる) に一致するメールを後で保持することができます。中.</span><span class="sxs-lookup"><span data-stu-id="7ecaa-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule (also known as a trasport rule) can be kept for later review.</span></span>
  
<span data-ttu-id="7ecaa-105">既定では、フィッシング、マルウェア、およびメールフロールールに対してフィルター処理されたメッセージは検疫に送信されますが、スパムとしてフィルター処理されたメッセージとバルクメールは、受信者の迷惑メールフォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-105">By default, messages that were filtered for phishing, malware, and mail flow rules are sent to quarantine, while messages that were filtered as spam and bulk mail are sent to the recipients' Junk Email folder.</span></span> <span data-ttu-id="7ecaa-106">管理者は、スパムフィルターポリシー (コンテンツフィルターポリシーとも呼ばれます) を設定して、スパムやバルクメールメッセージを検疫に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-106">As an admin, you can set up spam filter policies (also known as content filter policies) to send spam and bulk mail messages to quarantine instead.</span></span> <span data-ttu-id="7ecaa-107">詳細については、「[スパム フィルター ポリシーを構成する](configure-your-spam-filter-policies.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-107">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="7ecaa-108">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="7ecaa-109">ユーザーは、隔離された独自のフィルター処理されたメッセージのみを操作できます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="7ecaa-110">管理者は、すべてのユーザーの検疫済みメッセージを検索し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="7ecaa-111">信頼度の高いフィッシングメッセージおよびメールフロールールアクションによって検疫されたメッセージは、管理者検疫でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-111">High confidence phish messages and messages quarantined by mail flow rule actions are only available in the admin quarantine.</span></span> <span data-ttu-id="7ecaa-112">ユーザーは、自分のフィッシング、スパム、およびバルクメールメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-112">Users can access their own phish, spam, and bulk mail messages.</span></span> 
  
<span data-ttu-id="7ecaa-113">検疫済みメッセージの使用の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ecaa-113">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="7ecaa-114">管理者として検疫済みメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="7ecaa-114">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="7ecaa-115">ユーザーが検閲済みメッセージを検出して解放する</span><span class="sxs-lookup"><span data-stu-id="7ecaa-115">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="7ecaa-116">ユーザースパム通知を使用してスパム検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="7ecaa-116">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="7ecaa-117">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="7ecaa-117">Quarantine FAQ</span></span>](quarantine-faq.md)
