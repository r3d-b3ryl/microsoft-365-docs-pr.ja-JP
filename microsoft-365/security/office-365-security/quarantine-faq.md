---
title: 検疫に関する FAQ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
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
ms.openlocfilehash: f8d7d0820685671c4cbe9ae7671058cc60d8e637
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971555"
---
# <a name="quarantine-faq"></a><span data-ttu-id="2ae6e-103">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2ae6e-103">Quarantine FAQ</span></span>

<span data-ttu-id="2ae6e-p101">このトピックでは、ホストされた検疫についてのよく寄せられる質問 (FAQ) とその回答を紹介します。回答は Microsoft Exchange Online および Exchange Online Protection のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>

 <span data-ttu-id="2ae6e-106">**Q: 検疫でマルウェアによって検疫されたメッセージを管理するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>

<span data-ttu-id="2ae6e-107">検疫に送信された&amp;メッセージにマルウェアが含まれている場合に、そのメッセージを表示および操作するには、セキュリティコンプライアンスセンターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-107">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="2ae6e-108">詳細については、「[Office 365 でのメール メッセージの検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-108">For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

 <span data-ttu-id="2ae6e-109">**Q. スパム検疫済みメッセージを検疫に送るには、どのようにサービスを構成しますか?**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>

<span data-ttu-id="2ae6e-p103">A. 既定では、コンテンツ フィルターで処理されたメッセージは受信者の迷惑メール フォルダーに送信されます。しかし管理者は、代わりにコンテンツ フィルター ポリシーを構成することで、スパム検疫済みメッセージを検疫に送ることができます。コンテンツ フィルターで処理されたメッセージに対して実行できるさまざまな操作の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="2ae6e-114">**Q. このサービスには、スパム検疫メッセージの管理者およびエンド ユーザー管理はありますか?**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>

<span data-ttu-id="2ae6e-p104">A. 管理者は、検疫された電子メール メッセージすべてに関する詳細を Exchange 管理センター (EAC) で検索し、表示することができます。メッセージを検索したら、特定のユーザーに解放し、さらにオプションとして Microsoft スパム分析チームに誤検知 (迷惑メールではない) として報告することもできます。詳細については、「[管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

<span data-ttu-id="2ae6e-119">エンド ユーザーとして、自分のスパム検疫メッセージを以下を通じて管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-119">As an end user, you can manage your own spam-quarantined messages via:</span></span>

- <span data-ttu-id="2ae6e-120">スパム検疫ユーザー インターフェース。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-120">The spam quarantine user interface.</span></span> <span data-ttu-id="2ae6e-121">詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-121">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

 <span data-ttu-id="2ae6e-122">**Q. エンド ユーザーにスパム検疫へのアクセスを許可するにはどのようにすればよいですか。**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>

<span data-ttu-id="2ae6e-123">A.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-123">A.</span></span> <span data-ttu-id="2ae6e-124">エンドユーザーのスパム検疫にアクセスするには、エンドユーザーが有効な Office 365 ユーザー ID とパスワードを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-124">In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="2ae6e-125">社内メールボックスを保護している EOP のお客様は、ディレクトリ同期または EAC を使用して作成された有効な電子メールユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-125">EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC.</span></span> <span data-ttu-id="2ae6e-126">ユーザーの管理の詳細については、EOP 管理者が[EOP でメールユーザーを管理](manage-mail-users-in-eop.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-126">For more information about managing users, EOP admins can refer to [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="2ae6e-127">EOP スタンドアロンのお客様の場合は、ディレクトリ同期を使用し、ディレクトリベースのエッジブロックを有効にすることをお勧めします。詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-127">For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

 <span data-ttu-id="2ae6e-128">**Q. スパム以外のものを検疫に送信できますか?**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>

<span data-ttu-id="2ae6e-129">A.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-129">A.</span></span> <span data-ttu-id="2ae6e-130">はい。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-130">Yes.</span></span> <span data-ttu-id="2ae6e-131">フィッシングとして識別されたメッセージと共に、メールフロールール (トランスポートルールとも呼ばれます) に一致するメッセージを、管理者検疫に送信することもできます (構成済みのアクションの場合)。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-131">Messages that match a mail flow rule (also known as a transport rule) along with messages identified as phish can also be sent to the administrator quarantine, if that's the configured action.</span></span> <span data-ttu-id="2ae6e-132">エンドユーザー検疫は、スパムのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-132">The end user quarantine is for spam only.</span></span>

 <span data-ttu-id="2ae6e-133">**Q. メッセージが検疫内に保存される期間はどのくらいですか。**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-133">**Q. For how long are messages kept in the quarantine?**</span></span>

<span data-ttu-id="2ae6e-134">A.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-134">A.</span></span> <span data-ttu-id="2ae6e-135">既定では、スパム検疫メッセージは30日間検疫に保存されますが、メールフロールールと一致した検疫メッセージは、既定のコンテンツフィルターポリシーで設定された保持期間に基づいて最大30日間検疫に保持されます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-135">By default, spam-quarantined messages are kept in the quarantine for 30 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for up to 30 days based on the retention period set in your default content filter policy.</span></span> <span data-ttu-id="2ae6e-136">この期間が経過したら、メッセージは削除され、取得不能になります。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-136">After this period of time the messages are deleted and are not retrievable.</span></span> <span data-ttu-id="2ae6e-137">メールフロールールと一致した検疫済みメッセージの保持期間は構成できません。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-137">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="2ae6e-138">ただし、スパム検疫メッセージの保持期間は、コンテンツ フィルター ポリシーの **[次の期間スパムを保持する (日)]** の設定によって短縮できます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-138">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="2ae6e-139">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-139">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

 <span data-ttu-id="2ae6e-140">**Q. 一度に複数の検疫メッセージを解放または報告できますか。**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-140">**Q. Can I release or report more than one quarantined message at a time?**</span></span>

<span data-ttu-id="2ae6e-141">A.</span><span class="sxs-lookup"><span data-stu-id="2ae6e-141">A.</span></span> <span data-ttu-id="2ae6e-142">はい。検疫ポータルで一度に最大100のメッセージを解放することができます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-142">Yes, up to 100 messages can be released at one time in the Quarantine portal.</span></span> <span data-ttu-id="2ae6e-143">さらに、管理者はリモート Windows PowerShell スクリプトを作成してこのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-143">In addition, admins can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="2ae6e-144">メッセージを検索する場合は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットを使用し、それらを解放する場合は [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-144">Use the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for messages, and the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet to release them.</span></span>

 <span data-ttu-id="2ae6e-145">**Q. 隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。特定のドメインの隔離されたメッセージを検索できますか。**</span><span class="sxs-lookup"><span data-stu-id="2ae6e-145">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>

<span data-ttu-id="2ae6e-p110">A. Exchange 管理センターで検索条件を指定する場合、ワイルドカードはサポートされません。たとえば、送信者を検索する場合には、完全な電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>

<span data-ttu-id="2ae6e-149">リモート Windows PowerShell を使用すれば、管理者は [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) コマンドレットで指定して、特定のドメイン (contoso.com など) の隔離されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-149">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="2ae6e-p111">この結果は、[Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) コマンドレットに渡すことができます。メッセージをすべての受信者に解放するために、ReleaseToAll パラメーターを組み込みます。いったんメッセージが解放されると、再び解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="2ae6e-p111">The results can be passed to the [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span>

```powershell
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```
