---
title: Outlook on the web で迷惑メールとフィッシング メールを報告する
f1.keywords:
- NOCSH
ms.author: chrisda
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
description: 管理者は、Exchange Online の Outlook on the web (Outlook Web App) に組み込まれている迷惑メール、迷惑メール、フィッシング メールのレポート オプション、およびユーザーに対してこれらのレポート オプションを無効にする方法について学習できます。
ms.openlocfilehash: 947f9bb9c1c686b549d83b27c262e86eda0d5008
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826543"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="5c513-103">Exchange Online の Outlook on the web で迷惑メールとフィッシング メールを報告する</span><span class="sxs-lookup"><span data-stu-id="5c513-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="5c513-104">Exchange Online にメールボックスがある Microsoft 365 組織では、Web 上の Outlook の組み込みのレポート オプション (Outlook Web App) を使用して、誤検知 (迷惑メールとしてマークされているメール)、偽陽性 (不適切なメールが許可される)、漏えいのメッセージ (不適切なメールで許可されます)、Exchange Online Protection (EOP) へのフィッシング メールを送信できます。</span><span class="sxs-lookup"><span data-stu-id="5c513-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c513-105">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5c513-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5c513-106">Exchange Online メールボックスを持つ組織内の管理者は、セキュリティ/コンプライアンス センターの提出ポータルを&ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c513-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5c513-107">詳細については、「管理者送信 [を使用して、スパム、フィッシング、URL、ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="5c513-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="5c513-108">管理者は、ユーザーが Web 上の Outlook でメッセージを Microsoft に報告する機能を無効にするか有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5c513-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="5c513-109">詳細については、このトピックに後 [述する「Web 上の Outlook での迷惑メール レポートを無効にするまたは有効](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c513-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="5c513-110">報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。</span><span class="sxs-lookup"><span data-stu-id="5c513-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5c513-111">詳細については [、「Exchange Online でスパムやフィッシング メッセージのユーザーを送信するためのメールボックスを指定する」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="5c513-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="5c513-112">Microsoft へのメッセージの報告の詳細については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="5c513-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="5c513-113">Outlook on the web でスパムやフィッシングのメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="5c513-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="5c513-114">受信トレイにあるメッセージまたはその他の [迷惑メール] 以外のメール フォルダーについては、以下のいずれかの方法を使用してスパム メッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="5c513-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="5c513-115">メッセージを選択し、ツール バー **の** [迷惑メール] をクリックして、[迷惑 **メールまたはフ** ィッシ **ングメール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/owa-report-junk.png)

   - <span data-ttu-id="5c513-117">1 つ以上のメッセージを選択し、右クリックして、迷惑メール **としてマークを付けて選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="5c513-118">表示されたダイアログ で、[レポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5c513-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="5c513-119">後で注意が必要な場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5c513-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="5c513-120">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="5c513-120">Junk</span></span>|<span data-ttu-id="5c513-121">フィッシング</span><span class="sxs-lookup"><span data-stu-id="5c513-121">Phishing</span></span>|
   |:---:|:---:|
   |![迷惑メールとして報告](../../media/owa-report-as-junk-dialog.png)|![フィッシング ダイアログとして報告する](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="5c513-124">選択したメッセージが分析用に Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c513-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="5c513-125">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c513-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="5c513-126">Outlook on the web の [迷惑メール] フォルダーから、スパム以外やフィッシングしていないメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="5c513-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="5c513-127">迷惑メール フォルダーで、次のいずれかの方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="5c513-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="5c513-128">メッセージを選択し、ツール バー **上の [迷惑** メールしない] をクリックして、[ **迷惑メールやフィッ** シ **ングメール] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="5c513-130">1 つ以上のメッセージを選択し、右クリックして、迷惑メールでないメール **としてマークをマークします**。</span><span class="sxs-lookup"><span data-stu-id="5c513-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="5c513-131">表示されるダイアログで情報を読み、レポート をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="5c513-132">後で注意が必要な場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5c513-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="5c513-133">迷惑メールではないメール</span><span class="sxs-lookup"><span data-stu-id="5c513-133">Not Junk</span></span>|<span data-ttu-id="5c513-134">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="5c513-134">Phishing</span></span>|
   |:---:|:---:|
   |![迷惑メールでないことを報告するダイアログ](../../media/owa-report-as-not-junk-dialog.png)|![フィッシング ダイアログとして報告する](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="5c513-137">選択したメッセージが分析用に Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c513-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="5c513-138">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="5c513-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5c513-139">Web 上の Outlook で迷惑メール レポートを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="5c513-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="5c513-140">既定では、ユーザーは Outlook on the web で分析するために、スパムの誤検知、検知漏れ、フィッシング メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="5c513-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="5c513-141">管理者は Exchange Online PowerShell で Web 上の Outlook のメールボックス ポリシーを構成して、ユーザーがスパムの誤検知やスパムの誤検知を Microsoft に報告しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c513-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="5c513-142">フィッシング メッセージを Microsoft に報告する機能を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5c513-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c513-143">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5c513-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5c513-144">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c513-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5c513-145">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c513-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="5c513-146">具体的には、Exchange Online**の受信者ポリシー\*\*\*\*またはメール受信者**の役割が必要です。既定で **、組織管理役割**グループと**Recipient Management 役割グループに割**り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5c513-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5c513-147">Exchange Online の役割グループの詳細については、「Exchange Online で役割 [グループを変更する」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="5c513-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="5c513-148">各組織には、OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5c513-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="5c513-149">カスタム ポリシーは、既定のポリシーの前に、範囲を指定したユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5c513-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="5c513-150">Web 上の Outlook のメールボックス ポリシーの詳細については、Exchange Online の [Outlook on the web のメールボックス ポリシーを参照してください](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)。</span><span class="sxs-lookup"><span data-stu-id="5c513-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="5c513-151">迷惑メール報告を無効にしても、Outlook on the web でメッセージを迷惑メール、または迷惑メールでないメールとしてマークする機能は削除されません。</span><span class="sxs-lookup"><span data-stu-id="5c513-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="5c513-152">迷惑メール フォルダー内のメッセージを選択して、**迷惑**メールでないメールを \> **Not junk**クリックしても、メッセージは引き続き受信トレイに移動します。</span><span class="sxs-lookup"><span data-stu-id="5c513-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="5c513-153">Selecting a message in any **Junk** other email folder and clicking \> **Junk** still moves the message into the Junk Email folder.</span><span class="sxs-lookup"><span data-stu-id="5c513-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="5c513-154">利用できなくなった機能は、メッセージを Microsoft に報告するオプションです。</span><span class="sxs-lookup"><span data-stu-id="5c513-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5c513-155">Exchange Online PowerShell を使用して、Web 上の Outlook で迷惑メール レポートを無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="5c513-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="5c513-156">既存の Outlook on the web メールボックス ポリシーと迷惑メール レポートの状態を検索するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5c513-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="5c513-157">Web 上の Outlook で迷惑メール レポートを無効または有効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c513-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="5c513-158">この例では、既定のポリシーの迷惑メール報告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5c513-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="5c513-159">この例では、Contoso Managers という名前のカスタム ポリシーの迷惑メール報告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5c513-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="5c513-160">構文およびパラメーターの詳細については[、「Get-OwaMailboxPolicy」と](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy)[「Set-OwaMailboxPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="5c513-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5c513-161">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5c513-161">How do you know this worked?</span></span>

<span data-ttu-id="5c513-162">Web 上の Outlook での迷惑メール レポートが正常に有効または無効にされたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c513-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="5c513-163">Exchange Online PowerShell で次のコマンドを実行し **、ReportJunkEmailEnabled プロパティの値** を確認します。</span><span class="sxs-lookup"><span data-stu-id="5c513-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="5c513-164">影響を受けるユーザーのメールボックスを Outlook on the web で開き、[受信トレイ] でメッセージを選択して [**迷惑**メール] を \> **Junk**クリックし、メッセージを Microsoft に報告するプロンプトが表示されていないことを確認します。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c513-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="5c513-165">影響を受けるユーザーのメールボックスを Outlook on the web で開き、[迷惑メール] フォルダーでメッセージを選択して [迷惑メール]**を** \> **Junk**クリックし、メッセージを Microsoft に報告するプロンプトが表示されていないことを確認します。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5c513-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="5c513-166"><sup>\*</sup> メッセージの報告中に、メッセージを報告するプロンプトを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c513-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="5c513-167">Outlook on the web でこの設定を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c513-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="5c513-168">[Web **上の** ![ Outlook 設定] アイコンをクリックすると ](../../media/owa-settings-icon.png) \> **、[Outlook の設定をすべて迷惑メール]** \> **に表示します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="5c513-169">[レポート **] セクション** で、次の値を確認します。 **レポートを送信する前に、次のことを確認します**。</span><span class="sxs-lookup"><span data-stu-id="5c513-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook on the web の迷惑メール報告設定](../../media/owa-junk-email-reporting-options.png)
