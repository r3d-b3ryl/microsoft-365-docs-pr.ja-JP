---
title: 隔ドされたメッセージに関する FAQ
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
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 管理者は、検疫済みメッセージに関するよく寄せられる質問と回答を Exchange Online Protection (EOP) で表示できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 896a83d4a09e8d0fcafeb6885cf2c63b6d8bb045
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826791"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="38acc-103">隔ドされたメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="38acc-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="38acc-104">このトピックでは、Exchange Online メールボックスを使用している Microsoft 365 組織または Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織向けの検疫済み電子メール メッセージに関するよく寄せられる質問と回答について取り上示します。</span><span class="sxs-lookup"><span data-stu-id="38acc-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="38acc-105">スパム対策保護に関する質問と回答については、「スパム対策保護 [のよく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="38acc-106">マルウェア対策保護に関する質問と回答については、「マルウェア対策保護 [」に関する FAQ を参照してください](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="38acc-107">スプーフィング対策保護に関する質問と回答については、「スプーフィング [対策保護に関する FAQ」を参照してください](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="38acc-108">マルウェアのために検疫されたメッセージはどのように管理しますか?</span><span class="sxs-lookup"><span data-stu-id="38acc-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="38acc-109">マルウェアのために検疫されたメッセージを管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="38acc-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="38acc-110">詳細については、管理者として [検疫済みメッセージとファイルの管理に関するトピックを参照してください](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="38acc-111">スパムを検疫する方法</span><span class="sxs-lookup"><span data-stu-id="38acc-111">How do I quarantine spam?</span></span>

<span data-ttu-id="38acc-112">既定では、スパム フィルター処理によってスパムまたはバルク メールとして分類されたメッセージはユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="38acc-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="38acc-113">ただし、スパム対策ポリシーを作成して構成し、スパムまたはバルク メール メッセージを検疫できます。</span><span class="sxs-lookup"><span data-stu-id="38acc-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="38acc-114">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38acc-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="38acc-115">ユーザーに検疫へのアクセス許可を付与する方法を示しますか?</span><span class="sxs-lookup"><span data-stu-id="38acc-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="38acc-116">ユーザーは、検疫内の自分のメッセージにアクセスするために有効なアカウントを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="38acc-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="38acc-117">スタンドアロン EOP では、ユーザーが EOP のメール ユーザーとして表される必要があります (手動で作成またはディレクトリ同期による作成)。</span><span class="sxs-lookup"><span data-stu-id="38acc-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="38acc-118">スタンドアロン EOP 環境でのユーザー管理の詳細については、「EOP でメール [ユーザーを管理する」を参照してください](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="38acc-119">検疫でエンド ユーザーがアクセスできるメッセージは何ですか。</span><span class="sxs-lookup"><span data-stu-id="38acc-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="38acc-120">ユーザーは、スパム、バルク メール、(2020 年 4 月現在) のフィッシング メッセージにアクセスできます。2020 年 4 月以降、これらのメッセージは受信者です。</span><span class="sxs-lookup"><span data-stu-id="38acc-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="38acc-121">エンド ユーザーは、検疫されたマルウェア、高い信頼度フィッシング、または検疫されたメッセージにメッセージをメール フロー ルール (トランスポート ルールとも呼ばれる) の **ホスト** された検疫アクションに配信するために処理されたメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="38acc-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="38acc-122">検疫済みメッセージにアクセスするユーザーの詳細については、ユーザーが検疫 [済みメッセージを検索して解放する必要があります](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="38acc-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="38acc-123">メッセージは検疫内に保持される期間はどれよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="38acc-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="38acc-124">スパム対策ポリシーを使用して、スパム、フィッシング、およびバルク メール メッセージを検疫に保存する期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="38acc-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="38acc-125">既定値は 30 日で、これは上限で当されます。</span><span class="sxs-lookup"><span data-stu-id="38acc-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="38acc-126">詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="38acc-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="38acc-127">メール フロー ルールのアクションによって検疫されたメッセージが **ホストされた検疫に配信された場合**、メッセージは検疫に 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="38acc-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="38acc-128">この期間は構成できます。</span><span class="sxs-lookup"><span data-stu-id="38acc-128">You can't configure this duration.</span></span>

<span data-ttu-id="38acc-129">期間が過ぎると、メッセージは削除され、回復不可能になります。</span><span class="sxs-lookup"><span data-stu-id="38acc-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="38acc-130">一度に複数の検疫メッセージを解放または報告できますか。</span><span class="sxs-lookup"><span data-stu-id="38acc-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="38acc-131">コンプライアンス センターでは&、同時に最大 100 個のメッセージを選択して解放することができます。</span><span class="sxs-lookup"><span data-stu-id="38acc-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="38acc-132">管理者は、Exchange Online PowerShell [の Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) コマンドレットと [Release-QuarantineMessage コマンドレット](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) またはスタンドアロン EOP PowerShell を使用して、検疫済みメッセージを一括で検索して解放したり、誤検知を一括で報告したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="38acc-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="38acc-133">隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。</span><span class="sxs-lookup"><span data-stu-id="38acc-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="38acc-134">特定のドメインの隔離されたメッセージを検索できますか。</span><span class="sxs-lookup"><span data-stu-id="38acc-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="38acc-135">ワイルドカードは、セキュリティ、コンプライアンス センターでは &サポートされません。</span><span class="sxs-lookup"><span data-stu-id="38acc-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="38acc-136">たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38acc-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="38acc-137">ただし、ワイルドカードは、Exchange Online PowerShell でも、スタンドアロン EOP PowerShell でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="38acc-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="38acc-138">たとえば、ドメイン名の受信者すべてからスパム検疫済みメッセージを検索するには、次のコマンドをcontoso.com。</span><span class="sxs-lookup"><span data-stu-id="38acc-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="38acc-139">その後、次のコマンドを実行して、それらのメッセージを元のすべての受信者にリリースします。</span><span class="sxs-lookup"><span data-stu-id="38acc-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="38acc-140">メッセージを解放した後は、もう一度メッセージを解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="38acc-140">After you release a message, you can't release it again.</span></span>
