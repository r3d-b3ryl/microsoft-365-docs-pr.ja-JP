---
title: 検疫に関する FAQ
ms.author: tracyp
author: MSFTTracyP
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
description: このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。
ms.openlocfilehash: d275a919e58d2a908fb10d4dff412ebe0859662f
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021843"
---
# <a name="quarantine-faq"></a><span data-ttu-id="f7256-103">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="f7256-103">Quarantine FAQ</span></span>

<span data-ttu-id="f7256-p101">このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f7256-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>

 <span data-ttu-id="f7256-106">**Q: 検疫でマルウェアによって検疫されたメッセージを管理するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="f7256-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>

<span data-ttu-id="f7256-107">セキュリティ & コンプライアンスセンターを使用して、検疫に送信されたメッセージを表示および操作するには、マルウェアが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7256-107">You need to use the Security & Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="f7256-108">詳細については、「[Office 365 でのメール メッセージの検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-108">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

 <span data-ttu-id="f7256-109">**Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**</span><span class="sxs-lookup"><span data-stu-id="f7256-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>

<span data-ttu-id="f7256-p103">A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="f7256-114">**Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**</span><span class="sxs-lookup"><span data-stu-id="f7256-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>

<span data-ttu-id="f7256-115">A.</span><span class="sxs-lookup"><span data-stu-id="f7256-115">A.</span></span> <span data-ttu-id="f7256-116">管理者は、セキュリティ/コンプライアンスセンター (SCC) で検疫されたすべての電子メールメッセージの詳細を検索して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f7256-116">As an admin, you can search for and view details about all quarantined email messages in the Security and Compliance Center (SCC).</span></span> <span data-ttu-id="f7256-117">メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7256-117">After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f7256-118">詳細については、「 [Office 365 での管理者としての検疫済みメッセージとファイルの管理](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-118">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="f7256-119">エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。</span><span class="sxs-lookup"><span data-stu-id="f7256-119">As an end user, you can manage your own spam-quarantined messages via:</span></span>

- <span data-ttu-id="f7256-120">スパム検疫ユーザー インターフェース。</span><span class="sxs-lookup"><span data-stu-id="f7256-120">The spam quarantine user interface.</span></span> <span data-ttu-id="f7256-121">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-121">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

 <span data-ttu-id="f7256-122">**Q: エンドユーザーの検疫へのアクセスを許可するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="f7256-122">**Q. How do I grant access to quarantine for my end users?**</span></span>

<span data-ttu-id="f7256-123">A.</span><span class="sxs-lookup"><span data-stu-id="f7256-123">A.</span></span> <span data-ttu-id="f7256-124">エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7256-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="f7256-125">社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7256-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="f7256-126">ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](manage-mail-users-in-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-126">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="f7256-127">EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

 <span data-ttu-id="f7256-128">**Q. エンドユーザーが検疫でアクセスできるメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f7256-128">**Q. What messages can end users access in quarantine?**</span></span>

<span data-ttu-id="f7256-129">A.</span><span class="sxs-lookup"><span data-stu-id="f7256-129">A.</span></span> <span data-ttu-id="f7256-130">エンドユーザーは、自分のフィッシング、スパム、およびバルクメールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7256-130">End users can access their own phish, spam, and bulk mail.</span></span> <span data-ttu-id="f7256-131">エンドユーザーは、自分のマルウェア、高信頼フィッシング、またはメールフロールール (トランスポートルールとも呼ばれます) に一致するメッセージにアクセスできません。これらは、管理者検疫でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7256-131">End users can't access their own malware, high confidence phish, or messages that matched a mail flow rule (also known as a transport rule); these are only available in the admin quarantine.</span></span> 

 <span data-ttu-id="f7256-132">**Q. メッセージが検疫内に保存される期間はどのくらいですか。**</span><span class="sxs-lookup"><span data-stu-id="f7256-132">**Q. For how long are messages kept in the quarantine?**</span></span>

<span data-ttu-id="f7256-133">A.</span><span class="sxs-lookup"><span data-stu-id="f7256-133">A.</span></span> <span data-ttu-id="f7256-134">既定では、スパム検疫メッセージは30日間検疫に保存されますが、メールフロールールと一致した検疫メッセージは、既定のコンテンツフィルターポリシーで設定された保持期間に基づいて最大30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="f7256-134">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="f7256-135">この期間が経過したら、メッセージは削除され、取得不能になります。</span><span class="sxs-lookup"><span data-stu-id="f7256-135">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="f7256-136">メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。</span><span class="sxs-lookup"><span data-stu-id="f7256-136">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="f7256-137">ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。</span><span class="sxs-lookup"><span data-stu-id="f7256-137">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="f7256-138">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7256-138">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="f7256-139">**Q. 一度に複数の検疫メッセージを解放または報告できますか。**</span><span class="sxs-lookup"><span data-stu-id="f7256-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>

<span data-ttu-id="f7256-140">A.</span><span class="sxs-lookup"><span data-stu-id="f7256-140">A.</span></span> <span data-ttu-id="f7256-141">はい。検疫ポータルで一度に最大100のメッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="f7256-141">Yes, up to 100 messages can be released at one time in the Quarantine portal.</span></span> <span data-ttu-id="f7256-142">さらに、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7256-142">In addition, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="f7256-143">メッセージを検索する場合は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f7256-143">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

 <span data-ttu-id="f7256-144">**Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**</span><span class="sxs-lookup"><span data-stu-id="f7256-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>

<span data-ttu-id="f7256-p110">A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7256-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>

<span data-ttu-id="f7256-148">リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f7256-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="f7256-p111">この結果は、[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="f7256-p111">The results can be passed to the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
