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
description: Microsoft 迷惑メール報告アドインをインストールおよび使用して、スパム、非スパム、フィッシングメッセージを Microsoft に報告する方法について説明します。
ms.openlocfilehash: 096bd83c53149360e6cdd3ba8e73aacce5b1106f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199687"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="ad646-103">Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="ad646-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ad646-104">現在迷惑メール報告アドインを使用していない場合は、代わりに [レポートメッセージアドイン](enable-the-report-message-add-in.md) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad646-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="ad646-105">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad646-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="ad646-106">Microsoft Outlook 用迷惑メール報告アドインを使用すると、誤検知 (スパムとしてマークされた良好な電子メール)、誤検知 (無効な電子メールが許可されている)、およびフィッシングメッセージを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="ad646-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="ad646-107">組織が Exchange Online Protection (たとえば、オンプレミスの Exchange や Exchange Online 以外の電子メールサービスなど) を使用していない場合、迷惑メールレポートの送信はスパムフィルターに影響しません。</span><span class="sxs-lookup"><span data-stu-id="ad646-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="ad646-108">このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad646-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad646-109">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ad646-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad646-110">迷惑メール報告アドインをインストールするには、このトピックで後述する「 [迷惑メール報告アドインをインストール](#install-the-junk-email-reporting-add-in) する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad646-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="ad646-111">迷惑メール報告アドインは、次のバージョンの Outlook で動作します。</span><span class="sxs-lookup"><span data-stu-id="ad646-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="ad646-112">Outlook 2013 以降</span><span class="sxs-lookup"><span data-stu-id="ad646-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="ad646-113">Outlook は、Microsoft 365 Apps for enterprise に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad646-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="ad646-114">Microsoft へのメッセージの報告の詳細については、「 [microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad646-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="ad646-115">迷惑メール報告アドインを使用してスパムおよびフィッシングメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="ad646-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="ad646-116">受信トレイまたは迷惑メール以外のその他の電子メールフォルダー内のメッセージの場合、次のいずれかの方法を使用して、スパムメッセージとフィッシングメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="ad646-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="ad646-117">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad646-117">Select the message or open the message.</span></span> <span data-ttu-id="ad646-118">リボンの [ **ホーム** ] タブまたは [ **メッセージ** ] タブで、[ **迷惑メール**] をクリックし、[ **迷惑メール** として報告] または [ **フィッシングとして報告**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="ad646-120">メッセージを右クリックし、[ **迷惑メール**] を選択して、[ **迷惑メールと** して報告] または [ **フィッシングとして報告**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックで迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="ad646-122">複数のメッセージを選択して右クリックし、[ **迷惑メールと** して報告] または [ **フィッシングとして**報告] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックで複数の迷惑メールまたはフィッシング詐欺メールメッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="ad646-124">表示されるダイアログで、情報を読み、[ **レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ad646-125">気が変わった場合は、[ **レポートしない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-125">If you change your mind, click **Don't Report**.</span></span>

   ![[迷惑メールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ad646-128">選択したメッセージが分析のために Microsoft に送信され、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ad646-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="ad646-129">迷惑メールフォルダーがスパムとして報告された場合は、そのフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ad646-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="ad646-130">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ad646-130">Deleted if it was reported as phishing.</span></span>
   
   <span data-ttu-id="ad646-131">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ad646-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="ad646-132">迷惑メール報告アドインを使用して迷惑メールフォルダーからの非スパムメッセージとフィッシング詐欺メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="ad646-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="ad646-133">[迷惑メール] フォルダーで、次のいずれかの方法を使用してスパム誤検知またはフィッシングメッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="ad646-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="ad646-134">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad646-134">Select the message or open the message.</span></span> <span data-ttu-id="ad646-135">リボンの [ **ホーム** ] タブまたは [ **メッセージ** ] タブで、[ **迷惑メール**ではない] をクリックし、[ **迷惑メール** ではないと報告] または [ **フィッシングとし**て報告する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メールフォルダーのリボンから迷惑メールまたはフィッシング詐欺メールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="ad646-137">メッセージを右クリックし、[ **迷惑メール**] をクリックして、[ **迷惑メールではないメール** として報告] または [ **フィッシングとして報告**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メールフォルダーを右クリックして迷惑メールではないことを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="ad646-139">複数のメッセージを選択し、右クリックして、[ **迷惑メール** ではないと報告] または [ **フィッシングとし**て報告する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad646-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メールフォルダー内の複数の迷惑メールまたはフィッシング詐欺メールメッセージを右クリックして報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="ad646-141">表示されるダイアログで、情報を読み、[ **レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="ad646-142">気が変わった場合は、[ **レポートしない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-142">If you change your mind, click **Don't Report**.</span></span>

   ![[迷惑メールではないメールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![フィッシングとして報告するダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="ad646-145">選択したメッセージが分析のために Microsoft に送信され、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ad646-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="ad646-146">迷惑メールフォルダーがスパムとして報告された場合は、そのフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ad646-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="ad646-147">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="ad646-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="ad646-148">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="ad646-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="ad646-149">迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="ad646-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="ad646-150">アドインをインストールするコンピューターで管理者特権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad646-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="ad646-151">に移動 <https://www.microsoft.com/download/details.aspx?id=18275> して、お使いの Office のバージョンに対応する .msi ファイルを、見つけやすい場所にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ad646-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="ad646-152">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ad646-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="ad646-153">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ad646-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="ad646-154">Outlook 2013 以降の場合、唯一の前提条件は、Microsoft .NET Framework 2.0 です。</span><span class="sxs-lookup"><span data-stu-id="ad646-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="ad646-155">Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールすることはありません。</span><span class="sxs-lookup"><span data-stu-id="ad646-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="ad646-156">セットアップウィザードを使用して迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="ad646-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="ad646-157">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="ad646-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ad646-158">Windows 10 で、.NET Framework 2.0 が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="ad646-159">手順については、「 [コントロールパネルで .Net Framework 3.5 を有効にする](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad646-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="ad646-160">ダウンロードした .msi ファイルを見つけ、それをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="ad646-161">**[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="ad646-162">使用許諾契約書の内容を確認し、条項に同意する場合は [ **使用許諾契約書の条項に同意** します] をクリックし、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="ad646-163">ウィザードが完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="ad646-164">Outlook を起動します。</span><span class="sxs-lookup"><span data-stu-id="ad646-164">Start Outlook.</span></span>

<span data-ttu-id="ad646-p109">Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="ad646-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="ad646-p110">Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad646-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="ad646-169">サイレント モードで迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="ad646-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="ad646-170">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="ad646-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="ad646-171">Windows 10 では、次のコマンドを実行して .NET Framework 2.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad646-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="ad646-172">ユーザーの操作なしでアドインをインストールするには、コマンドプロンプトを開き、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad646-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="ad646-173">`MaxMessageSelection` 1回の送信に対して選択できるメッセージの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad646-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="ad646-174">有効な値は 1 ~ 50 です。</span><span class="sxs-lookup"><span data-stu-id="ad646-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="ad646-175">既定値は 15 です。</span><span class="sxs-lookup"><span data-stu-id="ad646-175">The default value is 15.</span></span>

   - <span data-ttu-id="ad646-176">`BccEmailAddress` すべてのユーザー送信のコピーを受信する追加の Bcc 受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="ad646-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="ad646-177">既定値は空白です (追加の Bcc 受信者は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="ad646-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="ad646-178">この例では、既定の設定を使用して、指定されたパスから64ビット版のアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad646-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="ad646-179">この例では、次の追加設定を使用して、指定されたパスから32ビットバージョンのアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad646-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="ad646-180">1回の送信で最大20個のメッセージを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ad646-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="ad646-181">junkreports@contoso.com および hollyd@treyresearch.net は、すべての送信の Bcc コピーを受信します。</span><span class="sxs-lookup"><span data-stu-id="ad646-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ad646-182">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="ad646-182">How do you know this worked?</span></span>

<span data-ttu-id="ad646-183">迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad646-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="ad646-184">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad646-184">Select the message or open the message.</span></span> <span data-ttu-id="ad646-185">リボンの [ **ホーム** ] タブまたは [ **メッセージ** ] タブで、[ **迷惑メール**] をクリックし、次のオプションが使用可能になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ad646-186">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-186">**Report as Junk**</span></span>
  - <span data-ttu-id="ad646-187">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="ad646-188">**迷惑メール報告オプション**</span><span class="sxs-lookup"><span data-stu-id="ad646-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ad646-189">**迷惑メールを報告するオンラインヘルプ**</span><span class="sxs-lookup"><span data-stu-id="ad646-189">**Report Junk Online Help**</span></span>

  ![リボンから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="ad646-191">メッセージを右クリックし、[ **迷惑メール**] を選択して、次のオプションが使用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ad646-192">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-192">**Report as Junk**</span></span>
  - <span data-ttu-id="ad646-193">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="ad646-194">**迷惑メール報告オプション**</span><span class="sxs-lookup"><span data-stu-id="ad646-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="ad646-195">**迷惑メールを報告するオンラインヘルプ**</span><span class="sxs-lookup"><span data-stu-id="ad646-195">**Report Junk Online Help**</span></span>

  ![右クリックで迷惑メールまたはフィッシング詐欺メールを報告する](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="ad646-197">複数のメッセージを選択し、右クリックして、次のオプションが使用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="ad646-198">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-198">**Report as Junk**</span></span>
  - <span data-ttu-id="ad646-199">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="ad646-199">**Report as Phishing**</span></span>

  ![右クリックで複数の迷惑メールまたはフィッシング詐欺メールメッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="ad646-201">**[迷惑メール**] フォルダー内の以前のアクションを実行し、以前の**迷惑**レポートオプションが迷惑メールでは**ない**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![迷惑メールフォルダーのリボンから迷惑メールまたはフィッシング詐欺メールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メールフォルダーを右クリックして迷惑メールではないことを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メールフォルダー内の複数の迷惑メールまたはフィッシング詐欺メールメッセージを右クリックして報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="ad646-205">迷惑メール報告アドインをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="ad646-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="ad646-206">Outlook を閉じた後、次のいずれかの手順を使用して、迷惑メール報告アドインをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad646-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="ad646-207">**コントロールパネル**: Windows キー + R を押します。開いた [ **実行** ] ダイアログで、enter と入力し、 `control appwiz.cpl` [ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="ad646-208">一覧で **Microsoft 迷惑メール報告アドイン** を見つけて選択し、[ **アンインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="ad646-209">**Windows インストーラーパッケージ**: 該当する .msi ファイルを検索またはダウンロードし、それをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="ad646-210">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ad646-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="ad646-211">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="ad646-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="ad646-212">表示されるダイアログで、[ **Outlook 用 Microsoft 迷惑メール報告アドインを削除** する] を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad646-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="ad646-213">**サイレントモード**: 適切な .msi ファイルを検索またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ad646-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="ad646-214">コマンドプロンプトウィンドウで、を \<PathToFile\> .msi ファイルの場所に置き換えて、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad646-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="ad646-215">**32 ビット**:</span><span class="sxs-lookup"><span data-stu-id="ad646-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="ad646-216">**64 ビット**:</span><span class="sxs-lookup"><span data-stu-id="ad646-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="ad646-217">アンインストール後に Outlook を開くと、迷惑メール、迷惑メールではない迷惑メールの報告オプションは表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="ad646-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="ad646-218">迷惑メール報告アドインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ad646-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="ad646-219">迷惑メール報告アドインを追加した後、Outlook で問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ad646-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="ad646-220">このセクションでは、発生する可能性のある問題と、それらの問題を解決するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ad646-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="ad646-221">ユーザー向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ad646-221">Troubleshooting for users</span></span>

<span data-ttu-id="ad646-222">次の1つまたは複数の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="ad646-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="ad646-223">**[迷惑メールの報告]** をクリックしても何も起こらない</span><span class="sxs-lookup"><span data-stu-id="ad646-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="ad646-224">電子メール メッセージを選択した後に Outlook が応答しなくなった</span><span class="sxs-lookup"><span data-stu-id="ad646-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="ad646-225">"配信不能" と返され、報告された迷惑メールを配信できない</span><span class="sxs-lookup"><span data-stu-id="ad646-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="ad646-226">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad646-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="ad646-227">Outlook を閉じて、再起動します。</span><span class="sxs-lookup"><span data-stu-id="ad646-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="ad646-228">テストメッセージを作成して送信し、受信者がメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad646-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="ad646-229">問題が解決しない場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ad646-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="ad646-230">Microsoft にメッセージを送信するために使用できるその他の方法については、「Microsoft へのメッセージ [とファイルの報告](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad646-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="ad646-231">管理者向けのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ad646-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="ad646-232">問題: ユーザーにシステム管理者に問い合わせるように求めるエラーメッセージが継続的に表示される</span><span class="sxs-lookup"><span data-stu-id="ad646-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="ad646-233">`LoggingLevel`レジストリキーの値を "Verbose" に設定していることを確認または設定します。</span><span class="sxs-lookup"><span data-stu-id="ad646-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="ad646-234">**32 ビット版32の Windows 上の Outlook**:</span><span class="sxs-lookup"><span data-stu-id="ad646-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ad646-235">**32 ビット版64の Windows 上の Outlook**:</span><span class="sxs-lookup"><span data-stu-id="ad646-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="ad646-236">**64 ビット Outlook**:</span><span class="sxs-lookup"><span data-stu-id="ad646-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="ad646-237">Outlook を再起動し、エラーメッセージが表示された場合にユーザーに報告するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="ad646-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="ad646-238">次の場所にあるログ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="ad646-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="ad646-239">Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad646-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="ad646-240">問題: ユーザーがメッセージを報告するときに確認のメッセージを表示しないように選択したときに、プロンプトが戻る</span><span class="sxs-lookup"><span data-stu-id="ad646-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="ad646-241">値が `ConfirmReportJunk` "True" のレジストリキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad646-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="ad646-242">Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="ad646-242">Restart Outlook.</span></span>
