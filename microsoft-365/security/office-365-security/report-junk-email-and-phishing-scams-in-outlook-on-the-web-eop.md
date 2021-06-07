---
title: Web で迷惑メールやフィッシングメールをOutlookメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online の web (Outlook Web App) の Outlook の組み込みの迷惑メール、迷惑メール、フィッシングメール報告オプション、およびユーザーに対してこれらのレポート オプションを無効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788309"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="0bbc3-103">迷惑メールとフィッシングメールを web Outlookで報告するExchange Online</span><span class="sxs-lookup"><span data-stu-id="0bbc3-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0bbc3-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0bbc3-104">**Applies to**</span></span>
- [<span data-ttu-id="0bbc3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0bbc3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0bbc3-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0bbc3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0bbc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bbc3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0bbc3-108">ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスのメールボックスにメールボックスを持つ Microsoft 365[](../../enterprise/hybrid-modern-auth-overview.md)組織では、誤検知 (スパムとしてマークされた良い電子メール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0bbc3-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0bbc3-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bbc3-110">ユーザー申請には、レポート メッセージ アドインまたはレポート フィッシング アドインをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="0bbc3-111">詳細については、「レポート メッセージまたはレポート フィッシング アドインを有効にする[」を参照してください](./enable-the-report-message-add-in.md)。ユーザー申請ポリシーを使用できないので、Outlookの組み込みレポート エクスペリエンス[はお勧めしません](./user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="0bbc3-112">ユーザーがメールボックスを使用している組織の管理者Exchange Online、コンプライアンス センターのセキュリティ &ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="0bbc3-113">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="0bbc3-114">管理者は、ユーザーが Web 上で Microsoft にメッセージを報告する機能を無効Outlook有効にできます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="0bbc3-115">詳細については、この記事の後半の「Web サイトの迷惑Outlook[報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)を無効または有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="0bbc3-116">指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="0bbc3-117">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="0bbc3-118">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="0bbc3-119">Web 上の迷惑メール レポートを無効Outlook有効にする</span><span class="sxs-lookup"><span data-stu-id="0bbc3-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="0bbc3-120">既定では、ユーザーはスパムの誤検知、誤検知、およびフィッシング メッセージを Microsoft に報告して、web 上Outlook分析できます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="0bbc3-121">管理者は、Outlook PowerShell の Exchange Online Web メールボックス ポリシーでユーザーがスパムの誤検知やスパムの誤検知を Microsoft に報告し、そのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="0bbc3-122">ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0bbc3-123">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0bbc3-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0bbc3-124">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0bbc3-125">この記事の手順を実行するには、Exchange Onlineにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="0bbc3-126">具体的には、既定で **組織の管理** 役割グループと受信者管理役割グループに割り当てられている受信者ポリシーまたはメール受信者の役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="0bbc3-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="0bbc3-127">グループ内の役割グループの詳細については、「Exchange Onlineのアクセス許可[](/exchange/permissions-exo/permissions-exo)」および「Exchange Online の役割グループの変更」[を参照Exchange Online。](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="0bbc3-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="0bbc3-128">すべての組織に OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="0bbc3-129">カスタム ポリシーは、既定のポリシーの前にスコープ付きユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="0bbc3-130">Web メールボックス ポリシーのOutlook詳細については、「Outlookの Web メールボックス ポリシーの詳細」[を参照Exchange Online。](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="0bbc3-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="0bbc3-131">迷惑メールレポートを無効にしても、メッセージを迷惑メールとしてマークしたり、Web 上の迷惑メールOutlook削除したりする機能は削除されません。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="0bbc3-132">迷惑メール フォルダーでメッセージを選択し、[迷惑メールではない] をクリックすると、メッセージは受信トレイ \> に戻ります。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="0bbc3-133">他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール \> ] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="0bbc3-134">使用できなくなったのは、Microsoft にメッセージを報告するオプションです。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="0bbc3-135">PowerShell Exchange Onlineを使用して、Web 上の迷惑メール レポートを無効Outlook有効にする</span><span class="sxs-lookup"><span data-stu-id="0bbc3-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="0bbc3-136">Web メールボックス ポリシーと迷惑Outlookレポートの状態で既存のメール を検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="0bbc3-137">Web 上の迷惑メール レポートを無効Outlook有効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="0bbc3-138">この例では、既定のポリシーで迷惑メールレポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="0bbc3-139">この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール レポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="0bbc3-140">構文とパラメーターの詳細については [、「Get-OwaMailboxPolicy」](/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0bbc3-141">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0bbc3-141">How do you know this worked?</span></span>

<span data-ttu-id="0bbc3-142">Web 上で迷惑メールレポートが正常に有効または無効Outlookするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="0bbc3-143">PowerShell Exchange Onlineで、次のコマンドを実行し **、ReportJunkEmailEnabled プロパティ** の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="0bbc3-144">web 上の Outlook で影響を受けるユーザーのメールボックスを開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bbc3-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="0bbc3-145">web 上の Outlook で影響を受けるユーザーのメールボックスを開き、[迷惑メール] フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0bbc3-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="0bbc3-146"><sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="0bbc3-147">Web 上でこの設定Outlook確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="0bbc3-148">[web **設定Outlook]** アイコンをクリックして、[すべての設定 ![ を表示 ](../../media/owa-settings-icon.png) \> **Outlook迷惑メール** \> **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="0bbc3-149">[レポート **] セクションで** 、値を確認します。 **レポートを送信する前に確認してください**。</span><span class="sxs-lookup"><span data-stu-id="0bbc3-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook迷惑メールレポートの設定を確認する](../../media/owa-junk-email-reporting-options.png)
