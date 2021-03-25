---
title: 検疫済みメッセージに関するよく寄せられる質問
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、Exchange Online Protection (EOP) で検疫済みメッセージに関するよく寄せられる質問と回答を表示できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 342f6b7f27c99352c4e5906799ce463b658e0c87
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206630"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="3c776-103">検疫済みメッセージに関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3c776-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3c776-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3c776-104">**Applies to**</span></span>
- [<span data-ttu-id="3c776-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3c776-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3c776-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="3c776-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3c776-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c776-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3c776-108">このトピックでは、Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織の検疫済み電子メール メッセージに関するよく寄せられる質問と回答を提供します。</span><span class="sxs-lookup"><span data-stu-id="3c776-108">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="3c776-109">スパム対策保護に関する質問と回答については、「スパム対策保護に関する [よく寄せられる質問」を参照してください](anti-spam-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="3c776-110">マルウェア対策保護に関する質問と回答については、「マルウェア対策の [保護に関するよく寄せられる質問」を参照してください](anti-malware-protection-faq-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="3c776-111">スプーフィング対策保護に関する質問と回答については、「スプーフィング防止に関するよく寄せられる質問 [」を参照してください](anti-spoofing-protection-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-111">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="3c776-112">マルウェアに対して検疫されたメッセージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="3c776-112">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="3c776-113">マルウェアに対して検疫されたメッセージを管理できるのは管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="3c776-113">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="3c776-114">詳細については、「検疫済み [メッセージとファイルを管理者として管理する」を参照してください](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-114">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="3c776-115">スパムを検疫する方法</span><span class="sxs-lookup"><span data-stu-id="3c776-115">How do I quarantine spam?</span></span>

<span data-ttu-id="3c776-116">既定では、スパム フィルターによってスパムまたはバルク メールとして分類されたメッセージは、ユーザーのメールボックスに配信され、迷惑メール フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="3c776-116">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="3c776-117">ただし、スパムまたはバルク メール メッセージを検疫するスパム対策ポリシーを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="3c776-117">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="3c776-118">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c776-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="3c776-119">検疫へのアクセス権をユーザーに与える方法</span><span class="sxs-lookup"><span data-stu-id="3c776-119">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="3c776-120">検疫で自分のメッセージにアクセスするには、有効なアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c776-120">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="3c776-121">スタンドアロン EOP では、ユーザーが EOP でメール ユーザーとして表される必要があります (手動で作成またはディレクトリ同期によって作成されます)。</span><span class="sxs-lookup"><span data-stu-id="3c776-121">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="3c776-122">スタンドアロン EOP 環境でのユーザーの管理の詳細については、「EOP でメール ユーザーを管理する」 [を参照してください](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-122">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="3c776-123">検疫でエンド ユーザーがアクセスできるメッセージ</span><span class="sxs-lookup"><span data-stu-id="3c776-123">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="3c776-124">ユーザーは、スパム、バルク メール、および (2020 年 4 月現在) フィッシング メッセージ (受信者である) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3c776-124">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="3c776-125">エンド ユーザーは、メール フロー ルール (トランスポート ルールとも呼ばれる) でホストされた検疫アクションにメッセージを配信するために検疫されたマルウェア、信頼性の高いフィッシング、またはメッセージにアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="3c776-125">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3c776-126">検疫済みメッセージにアクセスするユーザーの詳細については、「検疫済みメッセージをユーザーとして検索して解放する」 [を参照してください](find-and-release-quarantined-messages-as-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="3c776-126">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="3c776-127">検疫に保持されるメッセージの期間</span><span class="sxs-lookup"><span data-stu-id="3c776-127">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="3c776-128">スパム対策ポリシーを使用して、スパム、フィッシング、バルク メール メッセージが検疫に保持される期間を構成します。</span><span class="sxs-lookup"><span data-stu-id="3c776-128">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="3c776-129">既定値は 30 日で、最大値です。</span><span class="sxs-lookup"><span data-stu-id="3c776-129">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="3c776-130">詳細については [、「EOP でスパム対策ポリシーを構成する」を参照してください。](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3c776-130">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="3c776-131">[メール フロー ルール] アクションによって検疫されたメッセージの場合 **、** メッセージをホストされた検疫に配信すると、メッセージは検疫に 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="3c776-131">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="3c776-132">この期間は構成できない。</span><span class="sxs-lookup"><span data-stu-id="3c776-132">You can't configure this duration.</span></span>

<span data-ttu-id="3c776-133">期間が経過すると、メッセージは削除され、回復できません。</span><span class="sxs-lookup"><span data-stu-id="3c776-133">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="3c776-134">一度に複数の検疫メッセージを解放または報告できますか。</span><span class="sxs-lookup"><span data-stu-id="3c776-134">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="3c776-135">セキュリティ コンプライアンス センター&、一度に最大 100 件のメッセージを選択して解放できます。</span><span class="sxs-lookup"><span data-stu-id="3c776-135">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="3c776-136">管理者は、Exchange Online PowerShell またはスタンドアロン EOP PowerShell の [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) コマンドレットと [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) コマンドレットを使用して、検疫済みメッセージを一括で検索および解放し、誤検知を一括して報告できます。</span><span class="sxs-lookup"><span data-stu-id="3c776-136">Admins can use the the [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="3c776-137">隔離されたメッセージを検索する場合にワイルドカードはサポートされますか。</span><span class="sxs-lookup"><span data-stu-id="3c776-137">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="3c776-138">特定のドメインの隔離されたメッセージを検索できますか。</span><span class="sxs-lookup"><span data-stu-id="3c776-138">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="3c776-139">ワイルドカードは、セキュリティ コンプライアンス センター&サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3c776-139">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="3c776-140">たとえば、送信者を検索する場合は、完全な電子メール アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c776-140">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="3c776-141">ただし、Exchange Online PowerShell またはスタンドアロン EOP PowerShell ではワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c776-141">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="3c776-142">たとえば、次の PowerShell コードを NotePad にコピーし、ファイルを見つけやすい場所 (たとえば、C:\Data\QuarantineRelease.ps1) に .ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="3c776-142">For example, copy the following PowerShell code into NotePad and save the file as .ps1 in a location that's easy for you to find (for example, C:\Data\QuarantineRelease.ps1).</span></span>

<span data-ttu-id="3c776-143">次に [、Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) または [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)に接続した後、次のコマンドを実行してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c776-143">Then, after you connect to [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) or [Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell), run the following command to run the script:</span></span>

```powershell
& C:\Data\QuarantineRelease.ps1
```

<span data-ttu-id="3c776-144">スクリプトは、次のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c776-144">The script does the following actions:</span></span>

- <span data-ttu-id="3c776-145">fabrikam ドメイン内のすべての送信者からスパムとして検疫された未発表のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="3c776-145">Find unreleased messages that were quarantined as spam from all senders in the fabrikam domain.</span></span> <span data-ttu-id="3c776-146">結果の最大数は 50,000 (1000 結果の 50 ページ) です。</span><span class="sxs-lookup"><span data-stu-id="3c776-146">The maximum number of results is 50,000 (50 pages of 1000 results).</span></span>
- <span data-ttu-id="3c776-147">結果を CSV ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="3c776-147">Save the results to a CSV file.</span></span>
- <span data-ttu-id="3c776-148">一致する検疫済みメッセージを元のすべての受信者に解放します。</span><span class="sxs-lookup"><span data-stu-id="3c776-148">Release the matching quarantined messages to all original recipients.</span></span>

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

<span data-ttu-id="3c776-149">メッセージをリリースした後は、もう一度メッセージをリリースし直す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c776-149">After you release a message, you can't release it again.</span></span>