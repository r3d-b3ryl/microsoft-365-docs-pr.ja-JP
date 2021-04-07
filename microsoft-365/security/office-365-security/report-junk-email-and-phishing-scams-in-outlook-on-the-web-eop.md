---
title: Outlook on the web で迷惑メールとフィッシングメールを報告する
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
description: 管理者は、Exchange Online の Outlook on the Web (Outlook Web App) の組み込みの迷惑メール、迷惑メール、フィッシングメールレポートオプション、およびユーザーに対してこれらのレポートオプションを無効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615214"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="5e74e-103">Exchange Online で Outlook on the web で迷惑メールとフィッシングメールを報告する</span><span class="sxs-lookup"><span data-stu-id="5e74e-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5e74e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="5e74e-104">**Applies to**</span></span>
- [<span data-ttu-id="5e74e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5e74e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5e74e-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="5e74e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5e74e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e74e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5e74e-108">ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスメールボックスにメールボックスを持つ[](../../enterprise/hybrid-modern-auth-overview.md)Microsoft 365 組織では、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5e74e-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5e74e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5e74e-110">最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージとレポート フィッシング アドインを使用することをお勧めします。詳細 [については、「レポート メッセージ アドインを有効](./enable-the-report-message-add-in.md) にする」および「レポート フィッシング アドインを [有効にする」](./enable-the-report-phish-add-in.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e74e-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="5e74e-111">Exchange Online メールボックスを使用している組織の管理者の場合は、セキュリティ コンプライアンス センターの申請ポータルを使用&勧めします。</span><span class="sxs-lookup"><span data-stu-id="5e74e-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5e74e-112">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e74e-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="5e74e-113">管理者は、Outlook on the web でユーザーが Microsoft にメッセージを報告する機能を無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="5e74e-114">詳細については、この記事の後半の [「Outlook on the Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) での迷惑メールレポートを無効または有効にする」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e74e-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="5e74e-115">指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5e74e-116">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="5e74e-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="5e74e-117">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="5e74e-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5e74e-118">Outlook on the web で迷惑メールレポートを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="5e74e-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="5e74e-119">既定では、ユーザーは、Outlook on the web で分析のために、スパムの誤検知、誤検知、フィッシング メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="5e74e-120">管理者は、Exchange Online PowerShell で Outlook on the Web メールボックス ポリシーを構成して、ユーザーがスパムの誤検知やスパムの誤検知を Microsoft に報告するのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="5e74e-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="5e74e-121">ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。</span><span class="sxs-lookup"><span data-stu-id="5e74e-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5e74e-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5e74e-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5e74e-123">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e74e-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5e74e-124">この記事の手順を実行するには、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e74e-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="5e74e-125">具体的には、既定で **組織の管理** 役割グループと受信者管理役割グループに割り当てられている受信者ポリシーまたはメール受信者の役割が必要です。 </span><span class="sxs-lookup"><span data-stu-id="5e74e-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5e74e-126">Exchange Online の役割グループの詳細については、「Exchange Online のアクセス許可」および [「Exchange Online](/exchange/permissions-exo/permissions-exo) の役割グループの [変更」を参照してください](/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="5e74e-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="5e74e-127">すべての組織に OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="5e74e-128">カスタム ポリシーは、既定のポリシーの前にスコープ付きユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="5e74e-129">Outlook on the Web メールボックス ポリシーの詳細については、「Outlook on the Web Mailbox [Policies in Exchange Online」を参照してください](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="5e74e-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="5e74e-130">迷惑メールレポートを無効にしても、Outlook on the web でメッセージを迷惑メールとしてマークしたり、迷惑メールとしてマークしたりする機能は削除されません。</span><span class="sxs-lookup"><span data-stu-id="5e74e-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="5e74e-131">迷惑メール フォルダーでメッセージを選択し、[迷惑メールではない] をクリックすると、メッセージは受信トレイ \> に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5e74e-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="5e74e-132">他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール \> ] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="5e74e-133">使用できなくなったのは、Microsoft にメッセージを報告するオプションです。</span><span class="sxs-lookup"><span data-stu-id="5e74e-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5e74e-134">Exchange Online PowerShell を使用して Outlook on the web で迷惑メールレポートを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="5e74e-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="5e74e-135">Web メールボックス ポリシー上の既存の Outlook と迷惑メールレポートの状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e74e-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="5e74e-136">Outlook on the web で迷惑メール レポートを無効または有効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e74e-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="5e74e-137">この例では、既定のポリシーで迷惑メールレポートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5e74e-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="5e74e-138">この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール レポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5e74e-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="5e74e-139">構文とパラメーターの詳細については [、「Get-OwaMailboxPolicy」](/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="5e74e-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5e74e-140">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5e74e-140">How do you know this worked?</span></span>

<span data-ttu-id="5e74e-141">Outlook on the web で迷惑メールレポートが正常に有効または無効にされたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e74e-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="5e74e-142">Exchange Online PowerShell で、次のコマンドを実行し **、ReportJunkEmailEnabled プロパティ** の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="5e74e-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="5e74e-143">影響を受けるユーザーのメールボックスを Outlook on the web で開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します \> 。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5e74e-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="5e74e-144">影響を受けるユーザーのメールボックスを Outlook on the web で開き、[迷惑メール]フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5e74e-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="5e74e-145"><sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="5e74e-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="5e74e-146">Outlook on the web でこの設定を確認するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e74e-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="5e74e-147">[Web **設定]** ![ アイコンの [Outlook の設定] アイコン [ ](../../media/owa-settings-icon.png) \> **すべての Outlook 設定の迷惑メールを** \> **表示する] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5e74e-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="5e74e-148">[レポート **] セクションで** 、値を確認します。 **レポートを送信する前に確認してください**。</span><span class="sxs-lookup"><span data-stu-id="5e74e-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook on the web Junk Email Reporting settings](../../media/owa-junk-email-reporting-options.png)