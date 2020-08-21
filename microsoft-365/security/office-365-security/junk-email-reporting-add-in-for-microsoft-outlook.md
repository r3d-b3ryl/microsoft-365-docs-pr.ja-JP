---
title: Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 迷惑メール報告アドインをインストールして、スパム、非スパム、フィッシング メールを Microsoft に報告する方法について説明します。
ms.openlocfilehash: 42b38830b55ae3dbee4ec74a0e96531d920c24a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827101"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="b05f4-103">Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="b05f4-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="b05f4-104">迷惑メール報告アドインを使用している場合は、代わりに [、迷惑メール報告アドインをお勧](enable-the-report-message-add-in.md) めします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="b05f4-105">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05f4-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="b05f4-106">Microsoft Outlook 用迷惑メール報告アドインにより、ユーザーは誤検知 (優れたメールがスパムとしてマークされています)、漏えい (不適切なメールで許可される)、およびフィッシング メッセージを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="b05f4-107">組織で Exchange Online Protection (たとえば、オンプレミスの Exchange、または Exchange Online 以外のメール サービス) を使用していない場合、迷惑メールの報告送信はスパム フィルタリングに影響しません。</span><span class="sxs-lookup"><span data-stu-id="b05f4-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="b05f4-108">このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b05f4-109">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b05f4-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b05f4-110">迷惑メール報告アドインをインストールする場合は、後述 [する「迷惑メール報告アドインをインストール](#install-the-junk-email-reporting-add-in) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b05f4-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="b05f4-111">迷惑メール報告アドインは、次のバージョンの Outlook で機能します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="b05f4-112">Outlook 2013 以降</span><span class="sxs-lookup"><span data-stu-id="b05f4-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="b05f4-113">Microsoft 365 Apps for enterprise に含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="b05f4-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="b05f4-114">Microsoft へのメッセージの報告の詳細については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b05f4-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="b05f4-115">迷惑メール報告アドインを使用してスパム メッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="b05f4-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="b05f4-116">受信トレイ内のメッセージまたはその他の [迷惑メール] 以外の電子メール フォルダーに対しては、次のいずれかの方法を使用して、スパム メッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="b05f4-117">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-117">Select the message or open the message.</span></span> <span data-ttu-id="b05f4-118">リボンの **[ホーム** ] **または [メッセージ** ] タブで、[迷惑メールとして保存] **をクリックし**、[ **迷惑メールとして** レポート] または **[レポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="b05f4-120">メッセージを右クリックし、[迷惑メール **]** を選択して、[迷惑メールとして保存] または [ **フィッシ** ング **として報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="b05f4-122">複数のメッセージを選択して右クリックし、[迷惑メールとして報告] または [ **フィッシ** ング **として報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックして、複数の迷惑メール またはフィッシングメール メッセージを報告します](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="b05f4-124">表示されるダイアログで情報を読み、レポート をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="b05f4-125">後で注意が必要な場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-125">If you change your mind, click **Don't Report**.</span></span>

   ![迷惑メールとして報告](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![フィッシング ダイアログとして報告する](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="b05f4-128">選択したメッセージは、分析用に Microsoft に送信され、次の処理が行います。</span><span class="sxs-lookup"><span data-stu-id="b05f4-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="b05f4-129">スパムとして報告された場合、[迷惑メール] フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="b05f4-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="b05f4-130">フィッシングとして報告された場合は削除されます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="b05f4-131">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="b05f4-132">迷惑メール報告アドインを使用して、迷惑メール フォルダーから、スパムではないフィッシングやフィッシングのメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="b05f4-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="b05f4-133">迷惑メール フォルダーで、次のいずれかの方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="b05f4-134">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-134">Select the message or open the message.</span></span> <span data-ttu-id="b05f4-135">リボンの **[ホーム** ] **または [メッセージ** ] タブで [迷惑メールしない] をクリック **し**、[迷惑メールしない] または [ **レポート** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![[迷惑メール] フォルダーのリボンから、迷惑メールまたはフィッシングメールでないメールを報告します](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="b05f4-137">メッセージを右クリックして [迷惑 **メール]** をクリックし、[迷惑メールとして保存] を選択するか、[ **フィ** ッ **シングとして報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダーで右クリックして、迷惑メールまたはフィッシング メールでないメールを報告します](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="b05f4-139">複数のメッセージを選択して右クリックし、次に [迷惑メールしないメールとしてレポート] または [ **フ** ィッ **シングとして報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダーで右クリックして、迷惑メール メッセージまたはフィッシングメール メッセージの複数を報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="b05f4-141">表示されるダイアログで情報を読み、レポート をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="b05f4-142">後で注意が必要な場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-142">If you change your mind, click **Don't Report**.</span></span>

   ![迷惑メールでないことを報告するダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![フィッシング ダイアログとして報告する](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="b05f4-145">選択したメッセージは、分析用に Microsoft に送信され、次の処理が行います。</span><span class="sxs-lookup"><span data-stu-id="b05f4-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="b05f4-146">スパムとして報告された場合、[迷惑メール] フォルダーに移動されました。</span><span class="sxs-lookup"><span data-stu-id="b05f4-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="b05f4-147">フィッシングとして報告された場合は削除されます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="b05f4-148">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="b05f4-149">迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="b05f4-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="b05f4-150">このアドインをインストールするコンピューターの管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="b05f4-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="b05f4-151">お使 <https://www.microsoft.com/download/details.aspx?id=18275> いのバージョンに適した .msi ファイルに移動してOffice、簡単に見つけやすい場所にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="b05f4-152">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="b05f4-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="b05f4-153">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="b05f4-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="b05f4-154">Outlook 2013 以降では、前提条件は Microsoft .NET Framework 2.0 のみです。</span><span class="sxs-lookup"><span data-stu-id="b05f4-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="b05f4-155">Windows 10 では、ダウンロードからの .NET Framework 2.0 はインストールしていけない。</span><span class="sxs-lookup"><span data-stu-id="b05f4-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="b05f4-156">セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="b05f4-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="b05f4-157">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="b05f4-158">Windows 10 で、.NET Framework 2.0 が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="b05f4-159">手順については、コントロール パネル [の [.NET Framework 3.5 を有効にする] を参照してください](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。</span><span class="sxs-lookup"><span data-stu-id="b05f4-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="b05f4-160">ダウンロードした .msi ファイルを見つけ、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="b05f4-161">**[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="b05f4-162">使用許諾契約書を確認し、 **使用許諾契約書** の条項に同意します。入力条件に同意する場合は、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="b05f4-163">ウィザードが完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="b05f4-164">Outlook を起動します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-164">Start Outlook.</span></span>

<span data-ttu-id="b05f4-p109">Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="b05f4-p110">Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="b05f4-169">サイレント モードで迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="b05f4-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="b05f4-170">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="b05f4-171">Windows 10 で、次のコマンドを実行して .NET Framework 2.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="b05f4-172">ユーザー入力を行わずにアドインをインストールするには、コマンド プロンプトを開いて次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="b05f4-173">`MaxMessageSelection` 1 つの提出で選択できる最大メッセージ数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="b05f4-174">有効な値は 1 ~ 50 です。</span><span class="sxs-lookup"><span data-stu-id="b05f4-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="b05f4-175">既定値は 15 です。</span><span class="sxs-lookup"><span data-stu-id="b05f4-175">The default value is 15.</span></span>

   - <span data-ttu-id="b05f4-176">`BccEmailAddress` は、ユーザーのすべての申請のコピーを受信する追加の BCC 受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="b05f4-177">既定値は空白です (追加の BCC 受信者はありません)。</span><span class="sxs-lookup"><span data-stu-id="b05f4-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="b05f4-178">この例では、指定したパスから既定の設定で 64 ビット バージョンのアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="b05f4-179">この例では、次の追加設定を指定したパスから 32 ビット バージョンのアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="b05f4-180">1 つの送信で最大 20 のメッセージを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="b05f4-181">junkreports@contoso.comはhollyd@treyresearch.net BCC コピーを受信または受信します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b05f4-182">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b05f4-182">How do you know this worked?</span></span>

<span data-ttu-id="b05f4-183">迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で以下のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="b05f4-184">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-184">Select the message or open the message.</span></span> <span data-ttu-id="b05f4-185">リボンの **[ホーム** ] **タブまたは [** メッセージ] タブで、[迷惑メール] **を**クリックして、次のオプションを使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="b05f4-186">**迷惑メールとして報告**</span><span class="sxs-lookup"><span data-stu-id="b05f4-186">**Report as Junk**</span></span>
  - <span data-ttu-id="b05f4-187">**レポートをフィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="b05f4-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="b05f4-188">**迷惑レポート オプション**</span><span class="sxs-lookup"><span data-stu-id="b05f4-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="b05f4-189">**迷惑メールの報告に役立つヘルプ**</span><span class="sxs-lookup"><span data-stu-id="b05f4-189">**Report Junk Online Help**</span></span>

  ![リボンから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="b05f4-191">メッセージを右クリックし、[迷惑メール] **を選択して**、次のオプションが使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="b05f4-192">**迷惑メールとして報告**</span><span class="sxs-lookup"><span data-stu-id="b05f4-192">**Report as Junk**</span></span>
  - <span data-ttu-id="b05f4-193">**レポートをフィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="b05f4-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="b05f4-194">**迷惑レポート オプション**</span><span class="sxs-lookup"><span data-stu-id="b05f4-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="b05f4-195">**迷惑メールの報告に役立つヘルプ**</span><span class="sxs-lookup"><span data-stu-id="b05f4-195">**Report Junk Online Help**</span></span>

  ![右クリックから迷惑メールまたはフィッシング メールを報告する](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="b05f4-197">複数のメッセージを選択し、右クリックして、次のオプションを使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="b05f4-198">**迷惑メールとして報告**</span><span class="sxs-lookup"><span data-stu-id="b05f4-198">**Report as Junk**</span></span>
  - <span data-ttu-id="b05f4-199">**レポートをフィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="b05f4-199">**Report as Phishing**</span></span>

  ![右クリックして、複数の迷惑メール またはフィッシングメール メッセージを報告します](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="b05f4-201">[迷惑メール] フォルダーで以前の **アクションを実行し** 、以前の迷惑メール報告 **オプションが** [迷惑メールでなけなけた] **になたびないことを確認します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![[迷惑メール] フォルダーのリボンから、迷惑メールまたはフィッシングメールでないメールを報告します](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダーで右クリックして、迷惑メールまたはフィッシング メールでないメールを報告します](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダーで右クリックして、迷惑メール メッセージまたはフィッシングメール メッセージの複数を報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="b05f4-205">迷惑メール報告アドインをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="b05f4-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="b05f4-206">Outlook を終了した後、次のいずれかの手順を使用して迷惑メール報告アドインをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="b05f4-207">**[コントロール パネル]:** Windows キー + R キーを押します。開いた **[ファイル** 名を指定して実行] ダイアログ ボックスで `control appwiz.cpl` **、[OK] を入力してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="b05f4-208">一覧から **Microsoft 迷惑メール報告アドインを検索して** 選択し、[アンインストール] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="b05f4-209">**Windows インストーラ**ー パッケージ: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="b05f4-210">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="b05f4-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="b05f4-211">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="b05f4-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="b05f4-212">表示されるダイアログで **、[Outlook 用迷惑メール報告アドインを削除する** ] を選び、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b05f4-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="b05f4-213">**サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b05f4-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="b05f4-214">コマンド プロンプト ウィンドウで \<PathToFile\> 、.msi ファイルの場所を置き換え、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="b05f4-215">**32 ビット**:</span><span class="sxs-lookup"><span data-stu-id="b05f4-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="b05f4-216">**64 ビット**:</span><span class="sxs-lookup"><span data-stu-id="b05f4-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="b05f4-217">アンインストール後に Outlook を開くと、迷惑メール、迷惑メール、およびフィッシング レポート オプションがなけけないはなかもしれます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="b05f4-218">迷惑メール報告アドインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b05f4-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="b05f4-219">迷惑メール報告アドインの追加後に Outlook で問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b05f4-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="b05f4-220">このセクションでは、発生する可能性のある問題と、それらの問題を解決するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="b05f4-221">ユーザー向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b05f4-221">Troubleshooting for users</span></span>

<span data-ttu-id="b05f4-222">次の 1 つ以上の問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="b05f4-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="b05f4-223">**[迷惑メールの報告]** をクリックしても何も起こらない</span><span class="sxs-lookup"><span data-stu-id="b05f4-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="b05f4-224">電子メール メッセージを選択した後に Outlook が応答しなくなった</span><span class="sxs-lookup"><span data-stu-id="b05f4-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="b05f4-225">"配信不能" と返され、報告された迷惑メールを配信できない</span><span class="sxs-lookup"><span data-stu-id="b05f4-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="b05f4-226">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="b05f4-227">Outlook を終了して再起動します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="b05f4-228">テスト メッセージを作成して送信し、受信者がメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="b05f4-229">それが解決しない場合は、管理者に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="b05f4-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="b05f4-230">メッセージをマイクロソフトに送信するために使用できるその他の方法については、「レポート メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="b05f4-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="b05f4-231">管理者向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b05f4-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="b05f4-232">問題: システム管理者への連絡をユーザーに連絡するようにユーザーに連絡をとるエラー メッセージが連続して表示される</span><span class="sxs-lookup"><span data-stu-id="b05f4-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="b05f4-233">レジストリ キーの `LoggingLevel` 値を "Verbose" に設定します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="b05f4-234">**32 ビット Windows 上の 32 ビット Outlook**:</span><span class="sxs-lookup"><span data-stu-id="b05f4-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="b05f4-235">**32 ビット Outlook on 64 ビット Windows**:</span><span class="sxs-lookup"><span data-stu-id="b05f4-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="b05f4-236">**64 ビット Outlook**:</span><span class="sxs-lookup"><span data-stu-id="b05f4-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="b05f4-237">Outlook を再起動し、エラー メッセージが表示されたら報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b05f4-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="b05f4-238">次の場所にあるログ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="b05f4-239">Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="b05f4-240">問題: メッセージを報告するときに確認プロンプトが表示されないように選択したユーザーが、そのメッセージを返したい</span><span class="sxs-lookup"><span data-stu-id="b05f4-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="b05f4-241">値 `ConfirmReportJunk` が "True" のレジストリ キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="b05f4-242">Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="b05f4-242">Restart Outlook.</span></span>
