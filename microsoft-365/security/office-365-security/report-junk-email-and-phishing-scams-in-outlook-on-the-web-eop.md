---
title: 'Outlook on the web で迷惑メールとフィッシング詐欺を報告する '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Microsoft 365 Exchange Online メールボックスを使用しているユーザーは、web 上の Outlook (Outlook Web App) を使用して、スパム、非スパム、フィッシングメッセージを分析のために Microsoft に送信できます。
ms.openlocfilehash: 858224074ef7258d59318eef0c685a4ea4f9130f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632621"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="dda6f-103">Office 365 の Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する</span><span class="sxs-lookup"><span data-stu-id="dda6f-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="dda6f-104">Exchange Online メールボックスを使用している Microsoft 365 お客様の場合は、web 上の Outlook (旧称 Outlook Web App) の組み込みのレポート作成オプションを使用して誤検知 (迷惑メールとしてマークされている場合)、誤検知 (無効な電子メールが許可されている)、および Exchange Online Protection (EOP) へのフィッシングメッセージ</span><span class="sxs-lookup"><span data-stu-id="dda6f-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dda6f-105">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="dda6f-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dda6f-106">Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="dda6f-107">詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="dda6f-108">管理者は、ユーザーが Outlook on the web でメッセージを Microsoft に報告する機能を無効または有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="dda6f-109">詳細については、このトピックで後述する「 [web 上の Outlook で迷惑メール報告を無効または有効](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="dda6f-110">Microsoft へのメッセージの報告の詳細については、「 [Office 365 でメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="dda6f-111">Outlook on the web でスパムメッセージとフィッシングメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="dda6f-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="dda6f-112">受信トレイまたは迷惑メール以外の他の電子メールフォルダー内のメッセージの場合は、次のいずれかの方法を使用して、スパムメッセージとフィッシングメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="dda6f-113">メッセージを選択し、ツールバーの [**迷惑メール**] をクリックして、[**迷惑メール**または**フィッシング詐欺**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/owa-report-junk.png)

   - <span data-ttu-id="dda6f-115">1つ以上のメッセージを選択し、右クリックして、[**迷惑メールにマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="dda6f-116">表示されるダイアログで、[**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="dda6f-117">気が変わった場合は、[**レポートしない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-117">If you change your mind, click **Don't Report**.</span></span>

   ![[迷惑メールとして報告] ダイアログ](../../media/owa-report-as-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="dda6f-120">選択したメッセージが分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="dda6f-121">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="dda6f-122">Outlook on the web で迷惑メールフォルダーから非スパムメッセージとフィッシングメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="dda6f-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="dda6f-123">[迷惑メール] フォルダーで、次のいずれかの方法を使用して、スパム誤検知またはフィッシングメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="dda6f-124">メッセージを選択し、ツールバーの [**迷惑メール**ではない] をクリックし、[**迷惑メール**ではない] または [**フィッシング詐欺**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="dda6f-126">1つ以上のメッセージを選択して右クリックし、[**迷惑メールではないメールとしてマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="dda6f-127">表示されるダイアログで、情報を読み、[**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="dda6f-128">気が変わった場合は、[**レポートしない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-128">If you change your mind, click **Don't Report**.</span></span>

   ![[迷惑メールではないメールとして報告] ダイアログ](../../media/owa-report-as-not-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="dda6f-131">選択したメッセージが分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="dda6f-132">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="dda6f-133">Outlook on the web で迷惑メール報告を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="dda6f-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="dda6f-134">既定では、ユーザーは、web 上の Outlook で分析するために、スパム誤検知、誤ネガ、フィッシングメッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="dda6f-135">管理者は、Exchange Online PowerShell で Outlook on the web メールボックスポリシーを構成して、ユーザーがスパム誤検知を報告したり、Microsoft に迷惑メールを誤って報告したりできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-135">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="dda6f-136">ユーザーがフィッシングメッセージを Microsoft に報告する機能を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="dda6f-136">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dda6f-137">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="dda6f-137">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dda6f-138">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="dda6f-139">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda6f-139">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="dda6f-140">具体的には、**組織の管理**役割グループおよび**受信者管理**役割グループに既定で割り当てられる Exchange Online の**受信者ポリシー**または**メール受信者**の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="dda6f-140">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="dda6f-141">Exchange Online の役割グループの詳細については、「 [Exchange online で役割グループを変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-141">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="dda6f-142">すべての組織には、Owam社内 Boxpolicy-Default という名前の既定のポリシーがありますが、カスタムポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-142">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="dda6f-143">カスタムポリシーは、既定のポリシーよりも前に、スコープを指定したユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-143">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="dda6f-144">Outlook on the web メールボックスポリシーの詳細については、「 [outlook on the web mailbox policies In Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dda6f-144">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="dda6f-145">迷惑メール報告を無効にしても、Outlook on the web で迷惑メールや迷惑メールではないメッセージとしてマークする機能は削除されません。</span><span class="sxs-lookup"><span data-stu-id="dda6f-145">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="dda6f-146">[迷惑メール] フォルダー内のメッセージを選択し、[迷惑メールではない迷惑メールを受信しない]**をクリック** \>しても、メッセージは受信トレイに再び移動**さ**れます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-146">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="dda6f-147">他の電子メールフォルダーでメッセージを選択し、 **[迷惑メール] をクリック** \>しても、メッセージは **[迷惑メール**] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-147">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="dda6f-148">Microsoft にメッセージを報告するオプションとして、使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="dda6f-148">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="dda6f-149">Exchange Online PowerShell を使用して Outlook on the web で迷惑メール報告を無効または有効にする</span><span class="sxs-lookup"><span data-stu-id="dda6f-149">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="dda6f-150">既存の Outlook on the web メールボックスポリシーと、迷惑メール報告の状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-150">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="dda6f-151">Outlook on the web で迷惑メール報告を無効または有効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-151">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="dda6f-152">この例では、既定のポリシーで迷惑メール報告を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-152">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="dda6f-153">この例では、Contoso Managers という名前のカスタムポリシーで迷惑メール報告を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-153">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="dda6f-154">構文およびパラメーターの詳細については、「[収集](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)」を[参照してください。](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="dda6f-154">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dda6f-155">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="dda6f-155">How do you know this worked?</span></span>

<span data-ttu-id="dda6f-156">Outlook on the web で迷惑メール報告が正常に有効または無効にされたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-156">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="dda6f-157">Exchange Online PowerShell で次のコマンドを実行し、 **ReportJunkEmailEnabled**プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-157">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="dda6f-158">影響を受けるユーザーのメールボックスを web 上の Outlook で開きます。受信トレイでメッセージを選択し、[迷惑\> **メール**]**をクリックし**、メッセージを Microsoft に報告するかどうかを確認するメッセージが表示されないことを確認します。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dda6f-158">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="dda6f-159">影響を受けるユーザーのメールボックスを web 上の Outlook で開きます。 \> **[迷惑メール**] フォルダーでメッセージを選択し、 **[迷惑メール] をクリックし**、メッセージを Microsoft に報告するかどうかを確認するメッセージが表示されているかどうかを確認します。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="dda6f-159">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="dda6f-160"><sup>\*</sup>ユーザーはメッセージを報告するメッセージを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dda6f-160"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="dda6f-161">Outlook on the web でこの設定を確認するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="dda6f-161">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="dda6f-162">[ **Settings** ![Web 設定]](../../media/owa-settings-icon.png) \>アイコンの [outlook の設定] をクリックします。**すべての outlook 設定** \>の**迷惑メール**を表示します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-162">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="dda6f-163">[**レポート**] セクションで、[**レポートを送信する前にメッセージ**を表示する] の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="dda6f-163">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook on the web 迷惑メールの報告設定](../../media/owa-junk-email-reporting-options.png)
