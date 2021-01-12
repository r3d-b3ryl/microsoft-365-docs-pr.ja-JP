---
title: 検疫済みメッセージに関する FAQ
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
- m365initiative-defender-office365
description: 管理者は、Exchange Online Protection (EOP) で検疫済みメッセージに関してよく寄せられる質問と回答を表示できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 58ddb5847706aef3d2c3b8ea8cd9a96fd65a9b3d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794414"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="d4b11-103">検疫済みメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="d4b11-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d4b11-104">このトピックでは、Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織の検疫済み電子メール メッセージについてよく寄せられる質問と回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4b11-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="d4b11-105">スパム対策保護に関する質問と回答については、スパム対策保護に関する [FAQ を参照してください](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="d4b11-106">マルウェア対策保護に関する質問と回答については、マルウェア対策保護に関する [FAQ を参照してください](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="d4b11-107">スプーフィング対策保護に関する質問と回答については、スプーフィング対策保護に関する [FAQ を参照してください](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="d4b11-108">マルウェアに対して検疫されたメッセージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="d4b11-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="d4b11-109">マルウェアに対して検疫されたメッセージを管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="d4b11-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="d4b11-110">詳細については、「管理者として検疫 [済みメッセージとファイルを管理する」を参照してください](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="d4b11-111">スパムを検疫する方法</span><span class="sxs-lookup"><span data-stu-id="d4b11-111">How do I quarantine spam?</span></span>

<span data-ttu-id="d4b11-112">既定では、スパム フィルターによってスパムまたはバルク メールとして分類されたメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="d4b11-113">ただし、スパム対策ポリシーを作成して構成して、代わりにスパムメッセージまたはバルク メール メッセージを検疫できます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="d4b11-114">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4b11-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="d4b11-115">ユーザーに検疫へのアクセス権を与える方法</span><span class="sxs-lookup"><span data-stu-id="d4b11-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="d4b11-116">検疫で自分のメッセージにアクセスするには、ユーザーに有効なアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d4b11-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="d4b11-117">スタンドアロン EOP では、ユーザーは EOP でメール ユーザーとして表される必要があります (ディレクトリ同期を使用して手動で作成または作成)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="d4b11-118">スタンドアロン EOP 環境でのユーザー管理の詳細については、「EOP でのメール ユーザーの管理」を [参照してください](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="d4b11-119">エンド ユーザーが検疫でアクセスできるメッセージ</span><span class="sxs-lookup"><span data-stu-id="d4b11-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="d4b11-120">ユーザーは、スパム、バルク メール、および受信者である (2020 年 4 月現在) フィッシング メッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="d4b11-121">エンド ユーザーは、メール フロー ルール (トランスポート ルールとも呼ばれる) のホストされた検疫アクションにメッセージを配信するために検疫されたマルウェア、信頼度の高いフィッシング、または検疫されたメッセージにアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="d4b11-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d4b11-122">検疫済みメッセージにアクセスするユーザーの詳細については、「ユーザーとして検疫済みメッセージを検索 [して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b11-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="d4b11-123">検疫にメッセージを保持する期間はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="d4b11-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="d4b11-124">スパム対策ポリシーを使用して、スパム、フィッシング、バルク メール メッセージを検疫に保持する期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="d4b11-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="d4b11-125">既定値は 30 日で、これは最大値です。</span><span class="sxs-lookup"><span data-stu-id="d4b11-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="d4b11-126">詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="d4b11-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="d4b11-127">メール フロー ルールアクションによって検疫されたメッセージの場合 **、** ホストされた検疫にメッセージを配信すると、メッセージは 30 日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="d4b11-128">この期間は構成できない。</span><span class="sxs-lookup"><span data-stu-id="d4b11-128">You can't configure this duration.</span></span>

<span data-ttu-id="d4b11-129">期間が経過すると、メッセージは削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="d4b11-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="d4b11-130">一度に複数の検疫メッセージを解放または報告できますか。</span><span class="sxs-lookup"><span data-stu-id="d4b11-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="d4b11-131">セキュリティ/コンプライアンス センター&、一度に最大 100 件のメッセージを選択して解放できます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="d4b11-132">管理者は、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell で [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) コマンドレットと [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) コマンドレットを使用して、検疫済みメッセージを一括して検索して解放し、誤検知を一括して報告できます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="d4b11-133">隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。</span><span class="sxs-lookup"><span data-stu-id="d4b11-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="d4b11-134">特定のドメインの隔離されたメッセージを検索できますか。</span><span class="sxs-lookup"><span data-stu-id="d4b11-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="d4b11-135">セキュリティ/コンプライアンス センターでは、ワイルドカード&サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d4b11-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="d4b11-136">たとえば、送信者を検索する場合は、完全なメール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4b11-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="d4b11-137">ただし、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell ではワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4b11-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="d4b11-138">たとえば、次のコマンドを実行して、ドメイン 内のすべての送信者からのスパム検疫済みメッセージを検索contoso.com。</span><span class="sxs-lookup"><span data-stu-id="d4b11-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="d4b11-139">次に、次のコマンドを実行して、これらのメッセージを元のすべての受信者に解放します。</span><span class="sxs-lookup"><span data-stu-id="d4b11-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="d4b11-140">メッセージを解放した後は、メッセージを解放し直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4b11-140">After you release a message, you can't release it again.</span></span>
