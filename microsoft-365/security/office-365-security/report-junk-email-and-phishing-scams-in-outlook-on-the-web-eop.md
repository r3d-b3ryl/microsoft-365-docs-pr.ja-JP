---
title: Outlook on the web で迷惑メールとフィッシングメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online の Outlook on the web (Outlook Web App) の組み込みの迷惑メール、迷惑メールではないメール、フィッシングメール報告オプション、およびユーザーに対してこれらのレポート オプションを無効にする方法について説明します。
ms.openlocfilehash: 0032e807961aed60128d6863899ae0de32d1a627
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659317"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="b58b7-103">Exchange Online の Outlook on the web で迷惑メールとフィッシングメールを報告する</span><span class="sxs-lookup"><span data-stu-id="b58b7-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b58b7-104">Exchange Online にメールボックスを持つ Microsoft 365 組織では、Outlook on the web (旧称 Outlook Web App) の組み込みのレポート オプションを使用して、誤検知 (スパムとしてマークされた良いメール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b58b7-105">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b58b7-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b58b7-106">Exchange Online メールボックスを使用している組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータル&勧めします。</span><span class="sxs-lookup"><span data-stu-id="b58b7-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="b58b7-107">詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b58b7-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="b58b7-108">管理者は、ユーザーが Outlook on the web で Microsoft にメッセージを報告する機能を無効または有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="b58b7-109">詳細については、この記事の後半 [の「Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) で迷惑メール報告を無効または有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b58b7-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="b58b7-110">指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="b58b7-111">詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="b58b7-112">メッセージを Microsoft に報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="b58b7-113">Outlook on the web でスパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="b58b7-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="b58b7-114">迷惑メール以外の受信トレイまたは他の電子メール フォルダー内のメッセージの場合は、次のいずれかの方法を使用してスパム メッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="b58b7-115">メッセージを選択し、ツール バーの **[迷惑メール** ] をクリックして、[迷惑メール] または [フィッシング **]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/owa-report-junk.png)

   - <span data-ttu-id="b58b7-117">1 つ以上のメッセージを選択し、右クリックして、[迷惑メール **としてマーク] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="b58b7-118">表示されるダイアログで、[レポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="b58b7-119">If you change your mind, click **Don't Report**.</span><span class="sxs-lookup"><span data-stu-id="b58b7-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="b58b7-120">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="b58b7-120">Junk</span></span>|<span data-ttu-id="b58b7-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="b58b7-121">Phishing</span></span>|
   |:---:|:---:|
   |![迷惑メールとして報告するダイアログ](../../media/owa-report-as-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="b58b7-124">選択したメッセージは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="b58b7-125">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="b58b7-126">Outlook on the web の [迷惑メール] フォルダーから非スパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="b58b7-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="b58b7-127">迷惑メール フォルダーで、次のいずれかの方法を使用して、スパム誤検知またはフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="b58b7-128">メッセージを選択し、ツール バー **の [迷惑メール** ではない] をクリックして、[迷惑メールやフィッシング **ではない]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![リボンからの迷惑メールまたはフィッシングメールではないメールを報告する](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="b58b7-130">1 つ以上のメッセージを選択し、右クリックして、[迷惑メール **ではないメールとしてマークする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="b58b7-131">表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="b58b7-132">If you change your mind, click **Don't Report**.</span><span class="sxs-lookup"><span data-stu-id="b58b7-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="b58b7-133">迷惑メールではないメール</span><span class="sxs-lookup"><span data-stu-id="b58b7-133">Not Junk</span></span>|<span data-ttu-id="b58b7-134">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="b58b7-134">Phishing</span></span>|
   |:---:|:---:|
   |![迷惑メールではないとして報告するダイアログ](../../media/owa-report-as-not-junk-dialog.png)|![[フィッシングとして報告] ダイアログ](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="b58b7-137">選択したメッセージは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="b58b7-138">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="b58b7-139">Outlook on the web で迷惑メール報告を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="b58b7-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="b58b7-140">既定では、ユーザーはスパムの誤検知、偽陰性、フィッシング メッセージを Outlook on the web で分析するために Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="b58b7-141">管理者は、Exchange Online PowerShell で Outlook on the web メールボックス ポリシーを構成して、ユーザーがスパムの誤検知やスパムの検出検出を Microsoft に報告するのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="b58b7-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="b58b7-142">ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。</span><span class="sxs-lookup"><span data-stu-id="b58b7-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b58b7-143">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b58b7-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b58b7-144">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b58b7-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b58b7-145">この記事の手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b58b7-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="b58b7-146">具体的には、既定で組織の管理役割グループと受信者管理役割グループに割り当てられる受信者ポリシーまたはメール受信者の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="b58b7-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="b58b7-147">Exchange Online の役割グループの詳細については、「Exchange Online のアクセス許可」および [「Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) の役割グループの変更」を [参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="b58b7-148">すべての組織には OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="b58b7-149">カスタム ポリシーは、既定のポリシーの前にスコープ設定されたユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="b58b7-150">Outlook on the web メールボックス ポリシーの詳細については、Exchange Online の Outlook on the web メールボックス [ポリシーを参照してください](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="b58b7-151">迷惑メール報告を無効にしても、Outlook on the web でメッセージを迷惑メールとしてマークする機能や迷惑メールではないメッセージとしてマークする機能は削除されません。</span><span class="sxs-lookup"><span data-stu-id="b58b7-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="b58b7-152">[迷惑メール] フォルダーでメッセージを選択し、[迷惑メールではないメッセージ] をクリックすると、メッセージは受信トレイ \> に戻ります。</span><span class="sxs-lookup"><span data-stu-id="b58b7-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="b58b7-153">他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール] \> フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="b58b7-154">利用できなくなったのは、メッセージを Microsoft に報告するオプションです。</span><span class="sxs-lookup"><span data-stu-id="b58b7-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="b58b7-155">Exchange Online PowerShell を使用して Outlook on the web で迷惑メール報告を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="b58b7-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="b58b7-156">既存の Outlook on the web メールボックス ポリシーと迷惑メール報告の状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="b58b7-157">Outlook on the web で迷惑メール報告を無効または有効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="b58b7-158">この例では、既定のポリシーで迷惑メール報告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b58b7-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="b58b7-159">この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール報告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b58b7-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="b58b7-160">構文およびパラメーターの詳細については [、「Get-OwaMailboxPolicy」](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b58b7-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b58b7-161">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b58b7-161">How do you know this worked?</span></span>

<span data-ttu-id="b58b7-162">Outlook on the web で迷惑メール報告が正常に有効または無効にされたことを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="b58b7-163">Exchange Online PowerShell で次のコマンドを実行し **、ReportJunkEmailEnabled** プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="b58b7-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="b58b7-164">影響を受けるユーザーのメールボックスを Outlook on the web で開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示しないか確認します。 \> <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b58b7-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="b58b7-165">影響を受けるユーザーのメールボックスを Outlook on the web で開き、[迷惑メール]フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示しないか確認します。 \> <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b58b7-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="b58b7-166"><sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="b58b7-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="b58b7-167">Outlook on the web でこの設定を確認するには:</span><span class="sxs-lookup"><span data-stu-id="b58b7-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="b58b7-168">Click **Settings** ![ Outlook on the web settings icon View all ](../../media/owa-settings-icon.png) \> **Outlook settings** \> **Junk email**.</span><span class="sxs-lookup"><span data-stu-id="b58b7-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="b58b7-169">[レポート **] セクションで** 、次の値を確認します。 **レポートを送信する前に確認してください**。</span><span class="sxs-lookup"><span data-stu-id="b58b7-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook on the web の迷惑メール報告の設定](../../media/owa-junk-email-reporting-options.png)
