---
title: Microsoft Outlook の迷惑メール レポート アドインをインストールして使用する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Microsoft 迷惑メール レポート アドインをインストールして使用して、スパム、非スパム、フィッシング メッセージを Microsoft に報告する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205466"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="7deed-103">Microsoft Outlook の迷惑メール レポート アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="7deed-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7deed-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="7deed-104">**Applies to**</span></span>
- [<span data-ttu-id="7deed-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="7deed-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7deed-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="7deed-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7deed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7deed-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="7deed-108">現在迷惑メール レポート アドインを使用していない場合は、代わりにレポート メッセージ アドイン[](enable-the-report-message-add-in.md)またはレポート フィッシング[アドインをお](enable-the-report-phish-add-in.md)勧めします。</span><span class="sxs-lookup"><span data-stu-id="7deed-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="7deed-109">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7deed-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="7deed-110">Microsoft Outlook の迷惑メール レポート アドインを使用すると、ユーザーは誤検知 (スパムとしてマークされた良いメール)、誤検知 (悪いメールが許可されている)、フィッシング メッセージを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="7deed-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="7deed-111">組織で Exchange Online Protection (たとえば、Exchange Online 以外のオンプレミス Exchange または電子メール サービス) を使用しない場合、迷惑メール レポートの送信はスパム フィルター処理に影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="7deed-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="7deed-112">このトピックでは、迷惑メール レポート アドインをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7deed-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7deed-113">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7deed-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7deed-114">迷惑メール レポート アドインをインストールするには、この記事の後半にある「迷惑 [メール](#install-the-junk-email-reporting-add-in) レポート アドインのインストール」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7deed-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="7deed-115">迷惑メール レポート アドインは、次のバージョンの Outlook で動作します。</span><span class="sxs-lookup"><span data-stu-id="7deed-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="7deed-116">Outlook 2013 以降</span><span class="sxs-lookup"><span data-stu-id="7deed-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="7deed-117">エンタープライズ向け Microsoft 365 Apps に含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="7deed-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="7deed-118">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7deed-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="7deed-119">迷惑メール レポート アドインを使用してスパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="7deed-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="7deed-120">迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="7deed-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7deed-121">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="7deed-121">Select the message or open the message.</span></span> <span data-ttu-id="7deed-122">リボンの **[ホーム]** タブ **または [メッセージ**] タブで、[迷惑 **メール]** をクリックし、[迷惑メールとして報告] または [フィッシングとしてレポート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="7deed-124">メッセージを右クリックし、[迷惑メール **]** を選択し、[迷惑メールとして報告] または [フィッシング **として報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="7deed-126">複数のメッセージを選択し、右クリックし、[迷惑メールとして報告] または [フィッシング **として報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="7deed-128">表示されるダイアログで、情報を読み取り、[レポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7deed-129">気が変わる場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-129">If you change your mind, click **Don't Report**.</span></span>

   ![[迷惑メールとして報告] ダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7deed-132">選択したメッセージは、分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="7deed-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7deed-133">迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="7deed-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7deed-134">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="7deed-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="7deed-135">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="7deed-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="7deed-136">迷惑メール レポート アドインを使用して迷惑メール フォルダーからスパム以外のメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="7deed-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="7deed-137">迷惑メール フォルダーで、次の方法を使用してスパムの誤検知やフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="7deed-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7deed-138">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="7deed-138">Select the message or open the message.</span></span> <span data-ttu-id="7deed-139">リボンの **[ホーム]** タブまたは **[メッセージ**] タブで、[迷惑メールではない] をクリックし、[迷惑メールとして報告] または [フィッシングとして報告]**を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="7deed-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![[迷惑メール] フォルダーのリボンから迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="7deed-141">メッセージを右クリックし、[迷惑メール **]** をクリックし、[迷惑メールではない] または [フィッシングとして報告する **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダーで右クリックして迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="7deed-143">複数のメッセージを選択し、右クリックし、[迷惑メールとして報告する] または [フィッシング **として報告する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダー内で右クリックして複数の迷惑メールメッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="7deed-145">表示されるダイアログで、情報を読み取り、[レポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7deed-146">気が変わる場合は、[ **レポートしない] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-146">If you change your mind, click **Don't Report**.</span></span>

   ![迷惑メールではないとして報告する](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="7deed-149">選択したメッセージは、分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="7deed-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="7deed-150">迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="7deed-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="7deed-151">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="7deed-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="7deed-152">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="7deed-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="7deed-153">迷惑メール レポート アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="7deed-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="7deed-154">アドインをインストールするコンピューターに管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="7deed-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="7deed-155">ファイルのバージョンに適した .msi ファイルOffice簡単に <https://www.microsoft.com/download/details.aspx?id=18275> 見つけることができる場所に移動してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7deed-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="7deed-156">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7deed-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="7deed-157">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7deed-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="7deed-158">Outlook 2013 以降の場合、唯一の前提条件は Microsoft .NET Framework 2.0 です。</span><span class="sxs-lookup"><span data-stu-id="7deed-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="7deed-159">Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7deed-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="7deed-160">セットアップ ウィザードを使用して迷惑メール レポート アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="7deed-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="7deed-161">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="7deed-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7deed-162">Windows 10 で、2.0 .NET Frameworkが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="7deed-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="7deed-163">手順については、「コントロール パネル [で .NET Framework 3.5 を有効にする」を参照してください](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。</span><span class="sxs-lookup"><span data-stu-id="7deed-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="7deed-164">ダウンロードした .msi ファイルを見つけてダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7deed-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="7deed-165">**[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7deed-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="7deed-166">使用許諾契約書を確認し、条項 **に** 同意する場合は[使用許諾契約書に同意する] をクリックし、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="7deed-167">ウィザードが完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7deed-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="7deed-168">Outlook を起動します。</span><span class="sxs-lookup"><span data-stu-id="7deed-168">Start Outlook.</span></span>

<span data-ttu-id="7deed-p109">Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="7deed-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="7deed-p110">Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7deed-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="7deed-173">サイレント モードで迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="7deed-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="7deed-174">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="7deed-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="7deed-175">Windows 10 で、次のコマンド.NET Framework 2.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7deed-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="7deed-176">ユーザー操作なしでアドインをインストールするには、コマンド プロンプトを開き、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7deed-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="7deed-177">`MaxMessageSelection` 1 つの申請に対して選択できるメッセージの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="7deed-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="7deed-178">有効な値は 1 ~ 50 です。</span><span class="sxs-lookup"><span data-stu-id="7deed-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="7deed-179">既定値は 15 です。</span><span class="sxs-lookup"><span data-stu-id="7deed-179">The default value is 15.</span></span>

   - <span data-ttu-id="7deed-180">`BccEmailAddress` すべてのユーザー申請のコピーを受け取る追加の BCC 受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="7deed-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="7deed-181">既定値は空白です (追加の BCC 受信者はありません)。</span><span class="sxs-lookup"><span data-stu-id="7deed-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="7deed-182">次の使用例は、指定したパスから 64 ビット バージョンのアドインを既定の設定でインストールします。</span><span class="sxs-lookup"><span data-stu-id="7deed-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="7deed-183">この例では、指定したパスから 32 ビット バージョンのアドインをインストールし、次の追加設定を行います。</span><span class="sxs-lookup"><span data-stu-id="7deed-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="7deed-184">1 回の申請で最大 20 件のメッセージを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7deed-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="7deed-185">junkreports@contoso.com および hollyd@treyresearch.net、すべての申請の BCC コピーを受信します。</span><span class="sxs-lookup"><span data-stu-id="7deed-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7deed-186">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7deed-186">How do you know this worked?</span></span>

<span data-ttu-id="7deed-187">迷惑メール レポート アドインが正常にインストールされたことを確認するには、Outlook で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7deed-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="7deed-188">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="7deed-188">Select the message or open the message.</span></span> <span data-ttu-id="7deed-189">リボンの **[ホーム]** タブ **または [メッセージ** ] タブで、[迷惑 **メール]** をクリックし、次のオプションが使用できると確認します。</span><span class="sxs-lookup"><span data-stu-id="7deed-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7deed-190">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-190">**Report as Junk**</span></span>
  - <span data-ttu-id="7deed-191">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="7deed-192">**迷惑メールレポートのオプション**</span><span class="sxs-lookup"><span data-stu-id="7deed-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7deed-193">**迷惑メール のオンライン ヘルプを報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-193">**Report Junk Online Help**</span></span>

  ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="7deed-195">メッセージを右クリックし、[迷惑メール **]** を選択し、次のオプションが使用できると確認します。</span><span class="sxs-lookup"><span data-stu-id="7deed-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7deed-196">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-196">**Report as Junk**</span></span>
  - <span data-ttu-id="7deed-197">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="7deed-198">**迷惑メールレポートのオプション**</span><span class="sxs-lookup"><span data-stu-id="7deed-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="7deed-199">**迷惑メール のオンライン ヘルプを報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-199">**Report Junk Online Help**</span></span>

  ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="7deed-201">複数のメッセージを選択し、右クリックして、次のオプションが使用できると確認します。</span><span class="sxs-lookup"><span data-stu-id="7deed-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="7deed-202">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-202">**Report as Junk**</span></span>
  - <span data-ttu-id="7deed-203">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="7deed-203">**Report as Phishing**</span></span>

  ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="7deed-205">[迷惑メール] フォルダーで前の **アクションを実行** し、以前の迷惑メール レポート オプションが [迷惑メールではない] に **なっていることを確認します**。</span><span class="sxs-lookup"><span data-stu-id="7deed-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![[迷惑メール] フォルダーのリボンから迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダーで右クリックして迷惑メールやフィッシングメールを報告しない](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダー内で右クリックして複数の迷惑メールメッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="7deed-209">迷惑メール報告アドインをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="7deed-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="7deed-210">Outlook を閉じると、次の手順を使用して迷惑メール レポート アドインをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="7deed-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="7deed-211">**コントロール パネル**: Windows キー + R キーを押します。開く **[ファイル名を指定** して実行] ダイアログで `control appwiz.cpl` 、[OK] を入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="7deed-212">リストで **Microsoft 迷惑メール レポート アドイン** を検索して選択し、[アンインストール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="7deed-213">**Windows インストーラー パッケージ**: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7deed-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="7deed-214">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7deed-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="7deed-215">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="7deed-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="7deed-216">表示されるダイアログで **、[Outlook** 用 Microsoft 迷惑メール レポート アドインの削除] を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="7deed-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="7deed-217">**サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7deed-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="7deed-218">コマンド プロンプト ウィンドウで、.msi ファイルの場所に置き換え、 \<PathToFile\> 次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7deed-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="7deed-219">**32 ビット**:</span><span class="sxs-lookup"><span data-stu-id="7deed-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="7deed-220">**64 ビット**:</span><span class="sxs-lookup"><span data-stu-id="7deed-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="7deed-221">アンインストール後に Outlook を開いた場合は、迷惑メールではなく迷惑メールやフィッシング報告のオプションがなくなります。</span><span class="sxs-lookup"><span data-stu-id="7deed-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="7deed-222">迷惑メール レポート アドインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7deed-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="7deed-223">迷惑メール レポート アドインを追加した後で Outlook で問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7deed-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="7deed-224">このセクションでは、発生する可能性のある問題と、これらの問題を解決するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7deed-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="7deed-225">ユーザーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7deed-225">Troubleshooting for users</span></span>

<span data-ttu-id="7deed-226">次に示す問題が 1 つ以上発生します。</span><span class="sxs-lookup"><span data-stu-id="7deed-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="7deed-227">**[迷惑メールの報告]** をクリックしても何も起こらない</span><span class="sxs-lookup"><span data-stu-id="7deed-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="7deed-228">電子メール メッセージを選択した後に Outlook が応答しなくなった</span><span class="sxs-lookup"><span data-stu-id="7deed-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="7deed-229">"配信不能" と返され、報告された迷惑メールを配信できない</span><span class="sxs-lookup"><span data-stu-id="7deed-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="7deed-230">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7deed-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="7deed-231">Outlook を閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="7deed-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="7deed-232">テスト メッセージを作成して送信し、受信者がメッセージを受信したと確認します。</span><span class="sxs-lookup"><span data-stu-id="7deed-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="7deed-233">問題が解決しない場合は、管理者に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7deed-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="7deed-234">Microsoft にメッセージを送信するために使用できるその他のメソッドについては、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="7deed-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="7deed-235">管理者向けトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7deed-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="7deed-236">問題: システム管理者に連絡を求めるエラー メッセージが継続的に表示される</span><span class="sxs-lookup"><span data-stu-id="7deed-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="7deed-237">レジストリ キーを `LoggingLevel` "Verbose" という値に設定します。</span><span class="sxs-lookup"><span data-stu-id="7deed-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="7deed-238">**32 ビット Windows の 32 ビット Outlook:**</span><span class="sxs-lookup"><span data-stu-id="7deed-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7deed-239">**64 ビット Windows の 32 ビット Outlook:**</span><span class="sxs-lookup"><span data-stu-id="7deed-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="7deed-240">**64 ビット Outlook**:</span><span class="sxs-lookup"><span data-stu-id="7deed-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="7deed-241">Outlook を再起動し、エラー メッセージが表示されたユーザーに報告を求める。</span><span class="sxs-lookup"><span data-stu-id="7deed-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="7deed-242">次の場所にあるログ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="7deed-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="7deed-243">Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7deed-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="7deed-244">問題: メッセージを報告するときに確認メッセージを受信しないユーザーを選択し、プロンプトを戻す</span><span class="sxs-lookup"><span data-stu-id="7deed-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="7deed-245">`ConfirmReportJunk`"True" という値のレジストリ キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7deed-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="7deed-246">Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="7deed-246">Restart Outlook.</span></span>