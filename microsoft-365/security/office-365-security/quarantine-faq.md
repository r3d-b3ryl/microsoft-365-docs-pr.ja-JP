---
title: 検疫に関する FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Office 365 の検疫に関してよく寄せられる質問への回答。
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856907"
---
# <a name="quarantine-faq-in-office-365"></a><span data-ttu-id="2de9e-103">Office 365 の検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2de9e-103">Quarantine FAQ in Office 365</span></span>

<span data-ttu-id="2de9e-104">このトピックでは、exchange online またはスタンドアロンの exchange online Protection (EOP) のお客様が Exchange online メールボックスを使用していない場合に、メールボックスを持つ Office 365 ユーザーの検疫に関してよく寄せられる質問と回答を示します。</span><span class="sxs-lookup"><span data-stu-id="2de9e-104">This topic provides frequently asked questions and answers about quarantine for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="2de9e-105">Q: マルウェア用に検疫されたメッセージを管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2de9e-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="2de9e-106">管理者のみが、マルウェア用に検疫されたメッセージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="2de9e-107">詳細については、「 [Office 365 での管理者としての検疫済みメッセージとファイルの管理](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="2de9e-108">Q: スパムの検疫方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="2de9e-109">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-109">A.</span></span> <span data-ttu-id="2de9e-110">既定では、スパムフィルターによってスパムまたはバルクメールとして分類されるメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="2de9e-111">ただし、スパムまたはバルクメールメッセージを検疫するスパム対策ポリシーを作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="2de9e-112">詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="2de9e-113">Q: ユーザーに検疫へのアクセスを許可する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="2de9e-114">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-114">A.</span></span> <span data-ttu-id="2de9e-115">ユーザーは、検疫で自分のメッセージにアクセスするための有効なアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2de9e-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="2de9e-116">スタンドアロン EOP では、ユーザーが EOP のメールユーザーとして表されている必要があります (手動で作成またはディレクトリ同期経由で作成されます)。</span><span class="sxs-lookup"><span data-stu-id="2de9e-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="2de9e-117">スタンドアロン EOP 環境でのユーザーの管理の詳細については、「 [Manage mail users IN EOP](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="2de9e-118">Q: エンドユーザーが検疫でアクセスできるメッセージは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2de9e-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="2de9e-119">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-119">A.</span></span> <span data-ttu-id="2de9e-120">ユーザーは、スパム、バルクメール、および (2020 年4月) の受信者であるフィッシングメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="2de9e-121">エンドユーザーは、メールフロールール (トランスポートルールとも呼ばれる) でホストされた**検疫アクションにメッセージを配信**するため、検疫されたマルウェア、信頼性の高いフィッシング、またはメッセージを検疫済みメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2de9e-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="2de9e-122">検疫済みメッセージにアクセスするユーザーの詳細については、「 [Office 365 のユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="2de9e-123">Q: 検疫内のメッセージはどのくらいの期間保持されますか?</span><span class="sxs-lookup"><span data-stu-id="2de9e-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="2de9e-124">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-124">A.</span></span> <span data-ttu-id="2de9e-125">スパム対策ポリシーを使用して、スパム、フィッシング、およびバルクメールメッセージを検疫に保持する期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="2de9e-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="2de9e-126">既定値は30日で、これも最大数です。</span><span class="sxs-lookup"><span data-stu-id="2de9e-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="2de9e-127">詳細については、「 [Office のスパム対策ポリシーを構成する 365](configure-your-spam-filter-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de9e-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="2de9e-128">メールフロールールアクションによって検疫されたメッセージは、ホストされた**検疫にメッセージを配信する**ため、メッセージは30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="2de9e-129">この期間を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2de9e-129">You can't configure this duration.</span></span>

<span data-ttu-id="2de9e-130">期間が過ぎると、メッセージは削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="2de9e-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="2de9e-131">Q: 一度に複数の検疫済みメッセージを解放またはレポートすることはできますか。</span><span class="sxs-lookup"><span data-stu-id="2de9e-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="2de9e-132">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-132">A.</span></span> <span data-ttu-id="2de9e-133">セキュリティ & コンプライアンスセンターでは、一度に最大100のメッセージを選択して解放することができます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="2de9e-134">管理者は、Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell で Get-quarantinemessage および[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)コマンドレットを使用して、検疫[済み](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)メッセージを一括で検索して解放し、誤検知を一括で報告することができます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="2de9e-135">Q: 検疫されたメッセージを検索する場合、ワイルドカードはサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="2de9e-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="2de9e-136">特定のドメインの隔離されたメッセージを検索できますか。</span><span class="sxs-lookup"><span data-stu-id="2de9e-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="2de9e-137">A.</span><span class="sxs-lookup"><span data-stu-id="2de9e-137">A.</span></span> <span data-ttu-id="2de9e-138">セキュリティ & コンプライアンスセンターでは、ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2de9e-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="2de9e-139">たとえば、送信者を検索する場合は、完全な電子メールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2de9e-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="2de9e-140">ただし、Exchange Online の PowerShell または Exchange Online Protection の PowerShell でワイルドカードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2de9e-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="2de9e-141">たとえば、次のコマンドを実行して、ドメイン contoso.com のすべての送信者からスパム検疫済みメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="2de9e-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="2de9e-142">その後、次のコマンドを実行して、これらのメッセージを元の受信者すべてに解放します。</span><span class="sxs-lookup"><span data-stu-id="2de9e-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

<span data-ttu-id="2de9e-143">メッセージを解放した後で、再度解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="2de9e-143">After you release a message, you can't release it again.</span></span>
