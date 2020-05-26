---
title: 検疫済みメッセージに関する FAQ
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
description: 管理者は、Exchange Online Protection (EOP) で、検疫されたメッセージについてよく寄せられる質問と回答を確認できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0a231e363d5764465547ee1e80cc080c3d7c006c
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351097"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="8efc3-103">検疫済みメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="8efc3-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="8efc3-104">このトピックでは、exchange Online にメールボックスがある Microsoft 365 組織の検疫済み電子メールメッセージ、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織についてよく寄せられる質問とその回答について説明します。</span><span class="sxs-lookup"><span data-stu-id="8efc3-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="8efc3-105">スパム対策保護に関する質問と回答については、「[スパム対策保護](anti-spam-protection-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="8efc3-106">マルウェア対策保護に関する質問と回答については、「[マルウェア対策保護](anti-malware-protection-faq-eop.md)に関する faq」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="8efc3-107">スプーフィング対策保護に関する質問と回答については、「[スプーフィング対策保護](anti-spoofing-protection-faq.md)に関する FAQ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="8efc3-108">マルウェア用に検疫されたメッセージを管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="8efc3-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="8efc3-109">管理者のみが、マルウェア用に検疫されたメッセージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="8efc3-110">詳細については、「[管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="8efc3-111">スパムを検疫する方法</span><span class="sxs-lookup"><span data-stu-id="8efc3-111">How do I quarantine spam?</span></span>

<span data-ttu-id="8efc3-112">既定では、スパムフィルターによってスパムまたはバルクメールとして分類されるメッセージは、ユーザーのメールボックスに配信され、[迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="8efc3-113">ただし、スパムまたはバルクメールメッセージを検疫するスパム対策ポリシーを作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="8efc3-114">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="8efc3-115">ユーザーに検疫へのアクセスを許可するには、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="8efc3-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="8efc3-116">ユーザーは、検疫で自分のメッセージにアクセスするための有効なアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8efc3-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="8efc3-117">スタンドアロン EOP では、ユーザーが EOP のメールユーザーとして表されている必要があります (手動で作成またはディレクトリ同期経由で作成されます)。</span><span class="sxs-lookup"><span data-stu-id="8efc3-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="8efc3-118">スタンドアロン EOP 環境でのユーザーの管理の詳細については、「 [Manage mail users IN EOP](manage-mail-users-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="8efc3-119">エンドユーザーが検疫でアクセスできるメッセージ</span><span class="sxs-lookup"><span data-stu-id="8efc3-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="8efc3-120">ユーザーは、スパム、バルクメール、および (2020 年4月) の受信者であるフィッシングメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="8efc3-121">エンドユーザーは、メールフロールール (トランスポートルールとも呼ばれる) でホストされた**検疫アクションにメッセージを配信**するため、検疫されたマルウェア、信頼性の高いフィッシング、またはメッセージを検疫済みメッセージにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8efc3-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="8efc3-122">検疫済みメッセージにアクセスするユーザーの詳細については、「[ユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="8efc3-123">メッセージは検疫に保持される期間はどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="8efc3-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="8efc3-124">スパム対策ポリシーを使用して、スパム、フィッシング、およびバルクメールメッセージを検疫に保持する期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="8efc3-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="8efc3-125">既定値は30日で、これも最大数です。</span><span class="sxs-lookup"><span data-stu-id="8efc3-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="8efc3-126">詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8efc3-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="8efc3-127">メールフロールールアクションによって検疫されたメッセージは、ホストされた**検疫にメッセージを配信する**ため、メッセージは30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="8efc3-128">この期間を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="8efc3-128">You can't configure this duration.</span></span>

<span data-ttu-id="8efc3-129">期間が過ぎると、メッセージは削除され、復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="8efc3-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="8efc3-130">一度に複数の検疫メッセージを解放または報告できますか。</span><span class="sxs-lookup"><span data-stu-id="8efc3-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="8efc3-131">セキュリティ & コンプライアンスセンターでは、一度に最大100のメッセージを選択して解放することができます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="8efc3-132">管理者は、Exchange Online PowerShell またはスタンドアロン EOP PowerShell で[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)および[get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)コマンドレットを使用して、検疫済みメッセージを一括で検索して解放し、誤検知を一括で報告することができます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="8efc3-133">隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。</span><span class="sxs-lookup"><span data-stu-id="8efc3-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="8efc3-134">特定のドメインの隔離されたメッセージを検索できますか。</span><span class="sxs-lookup"><span data-stu-id="8efc3-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="8efc3-135">セキュリティ & コンプライアンスセンターでは、ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8efc3-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="8efc3-136">たとえば、送信者を検索する場合は、完全な電子メールアドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8efc3-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="8efc3-137">ただし、Exchange Online PowerShell またはスタンドアロンの EOP PowerShell でワイルドカードを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8efc3-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="8efc3-138">たとえば、次のコマンドを実行して、ドメイン contoso.com のすべての送信者からスパム検疫済みメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="8efc3-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="8efc3-139">その後、次のコマンドを実行して、これらのメッセージを元の受信者すべてに解放します。</span><span class="sxs-lookup"><span data-stu-id="8efc3-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="8efc3-140">メッセージを解放した後で、再度解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="8efc3-140">After you release a message, you can't release it again.</span></span>
