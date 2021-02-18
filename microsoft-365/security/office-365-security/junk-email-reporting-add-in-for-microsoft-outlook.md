---
title: Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する
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
description: Microsoft 迷惑メール報告アドインをインストールして使用して、スパム、非スパム、フィッシング メッセージを Microsoft に報告する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22a1364e8d7a1447bbcf518cc339a681c57a8af
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286623"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="c6d27-103">Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する</span><span class="sxs-lookup"><span data-stu-id="c6d27-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6d27-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c6d27-104">**Applies to**</span></span>
- [<span data-ttu-id="c6d27-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c6d27-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c6d27-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c6d27-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c6d27-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6d27-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="c6d27-108">迷惑メール報告アドインを現在使用していない場合は、代わりに迷惑メール報告アドインまたは Report [](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)アドインをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="c6d27-109">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d27-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="c6d27-110">Microsoft Outlook 用迷惑メール報告アドインを使用すると、ユーザーは誤検知 (スパムとしてマークされた良いメール)、偽陰性 (不正なメールが許可されている)、フィッシング メッセージを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="c6d27-111">組織が Exchange Online Protection (オンプレミスの Exchange や Exchange Online 以外のメール サービスなど) を使用していない場合、迷惑メール レポートの送信はスパム フィルター処理に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6d27-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="c6d27-112">このトピックでは、迷惑メール報告アドインをインストールして使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6d27-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c6d27-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6d27-114">迷惑メール報告アドインをインストールするには、この記事の後半[](#install-the-junk-email-reporting-add-in)にある「迷惑メール報告アドインのインストール」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6d27-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="c6d27-115">迷惑メール報告アドインは、次のバージョンの Outlook で動作します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="c6d27-116">Outlook 2013 以降</span><span class="sxs-lookup"><span data-stu-id="c6d27-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="c6d27-117">Microsoft 365 Apps for enterprise に含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="c6d27-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="c6d27-118">Microsoft にメッセージを報告する方法の詳細については、「メッセージとファイルを Microsoft に報告する」 [を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d27-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="c6d27-119">迷惑メール報告アドインを使用してスパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="c6d27-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="c6d27-120">迷惑メール以外の受信トレイまたは他の電子メール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="c6d27-121">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-121">Select the message or open the message.</span></span> <span data-ttu-id="c6d27-122">リボンの **[ホーム]** タブまたは **[メッセージ**] タブで、[迷惑メール] をクリックし、[迷惑メールとして報告] または [フィッシングとして報告] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="c6d27-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="c6d27-124">メッセージを右クリックし、[迷惑メール]**を選択** し、[迷惑メールとして報告] または [フィッシングとして **報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="c6d27-126">複数のメッセージを選択し、右クリックして、[迷惑メールとして報告 **]** または [フィッシングとして報告 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="c6d27-128">表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c6d27-129">If you change your mind, click **Don't Report**.</span><span class="sxs-lookup"><span data-stu-id="c6d27-129">If you change your mind, click **Don't Report**.</span></span>

   ![迷惑メールとして報告するダイアログ](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="c6d27-132">選択したメッセージは分析のために Microsoft に送信され、次の処理が行されます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="c6d27-133">迷惑メールとして報告された場合は、[迷惑メール] フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="c6d27-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="c6d27-134">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="c6d27-135">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="c6d27-136">迷惑メール報告アドインを使用して、[迷惑メール] フォルダーから非スパムメッセージとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="c6d27-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="c6d27-137">迷惑メール フォルダーで、次の方法を使用して、スパムの誤検知またはフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="c6d27-138">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-138">Select the message or open the message.</span></span> <span data-ttu-id="c6d27-139">リボンの **[ホーム]** タブまたは **[メッセージ**] タブで、[迷惑メールではないメール] をクリックし、[迷惑メールではないメールとして報告] または [フィッシングとして報告] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="c6d27-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![[迷惑メール] フォルダーのリボンから迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="c6d27-141">メッセージを右クリックし、[迷惑メール]**をクリック** して、[迷惑メールではないメールとして報告] または [フィッシングとして報告]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダー内の右クリックからの迷惑メールやフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="c6d27-143">複数のメッセージを選択し、右クリックして、[迷惑メールではないメールとして報告] または [フィッシング **として報告] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![迷惑メール フォルダー内で右クリックした複数の迷惑メール メッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="c6d27-145">表示されるダイアログで、情報を読み取り、[レポート] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c6d27-146">If you change your mind, click **Don't Report**.</span><span class="sxs-lookup"><span data-stu-id="c6d27-146">If you change your mind, click **Don't Report**.</span></span>

   ![迷惑メールではないとして報告するダイアログ](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![[フィッシングとして報告] ダイアログ](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="c6d27-149">選択したメッセージは分析のために Microsoft に送信され、次の処理が行されます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="c6d27-150">迷惑メールとして報告された場合は、[迷惑メール] フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="c6d27-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="c6d27-151">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="c6d27-152">メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="c6d27-153">迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="c6d27-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="c6d27-154">アドインをインストールするコンピューターに管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="c6d27-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="c6d27-155">ご使用のバージョンのファイルに適した .msi ファイルOffice見つけやすい場所 <https://www.microsoft.com/download/details.aspx?id=18275> に移動してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="c6d27-156">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c6d27-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="c6d27-157">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c6d27-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="c6d27-158">Outlook 2013 以降の場合、前提条件は Microsoft .NET Framework 2.0 のみです。</span><span class="sxs-lookup"><span data-stu-id="c6d27-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="c6d27-159">Windows 10 では、ダウンロードから .NET Framework 2.0 をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6d27-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="c6d27-160">セットアップ ウィザードを使用して迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="c6d27-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="c6d27-161">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="c6d27-162">Windows 10 で、.NET Framework 2.0 が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="c6d27-163">手順については、「コントロール パネル [で .NET Framework 3.5 を有効にする」を参照してください](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)。</span><span class="sxs-lookup"><span data-stu-id="c6d27-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="c6d27-164">ダウンロードした .msi ファイルを見つけてダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="c6d27-165">**[Microsoft 迷惑メール報告アドイン セットアップにようこそ]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="c6d27-166">使用許諾契約書を確認し、条項に同意する場合は[使用許諾契約書に同意します] をクリックし、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="c6d27-167">ウィザードが完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="c6d27-168">Outlook を起動します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-168">Start Outlook.</span></span>

<span data-ttu-id="c6d27-p109">Outlook のリボンで、 **[迷惑メール]** ボタンを探してください。これで、受信トレイで迷惑メール メッセージを選択して、 **[迷惑メールを報告]** ボタンをクリックすると、迷惑メール メッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="c6d27-p110">Microsoft にフィッシング詐欺メールを報告する場合は、 **[迷惑メール]** の隣にある下矢印を選択し、 **[フィッシングとして報告]** などのオプションを選択してください。メールが誤って迷惑メールに識別された場合、[迷惑メール] フォルダー中で、 **[迷惑メールではないことを報告]** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="c6d27-173">サイレント モードで迷惑メール報告アドインをインストールする</span><span class="sxs-lookup"><span data-stu-id="c6d27-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="c6d27-174">お使いのコンピューターで Outlook を終了します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="c6d27-175">Windows 10 では、次のコマンドを実行して .NET Framework 2.0 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="c6d27-176">ユーザーの操作なしでアドインをインストールするには、コマンド プロンプトを開き、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="c6d27-177">`MaxMessageSelection` 1 回の申請に対して選択できるメッセージの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="c6d27-178">有効な値は 1 ~ 50 です。</span><span class="sxs-lookup"><span data-stu-id="c6d27-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="c6d27-179">既定値は 15 です。</span><span class="sxs-lookup"><span data-stu-id="c6d27-179">The default value is 15.</span></span>

   - <span data-ttu-id="c6d27-180">`BccEmailAddress` すべてのユーザー提出のコピーを受け取る追加の BCC 受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="c6d27-181">既定値は空白です (BCC 受信者は追加されません)。</span><span class="sxs-lookup"><span data-stu-id="c6d27-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="c6d27-182">この例では、既定の設定を使用して、指定したパスから 64 ビット バージョンのアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="c6d27-183">この例では、次の追加設定を使用して、指定したパスから 32 ビット バージョンのアドインをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="c6d27-184">1 回の申請で最大 20 件のメッセージを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="c6d27-185">junkreports@contoso.comとhollyd@treyresearch.netすべての提出の BCC コピーを受け取る。</span><span class="sxs-lookup"><span data-stu-id="c6d27-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c6d27-186">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c6d27-186">How do you know this worked?</span></span>

<span data-ttu-id="c6d27-187">迷惑メール報告アドインが正常にインストールされたことを確認するには、Outlook で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="c6d27-188">メッセージを選択するか、メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6d27-188">Select the message or open the message.</span></span> <span data-ttu-id="c6d27-189">リボンの **[ホーム]** タブまたは [**メッセージ**] タブで [迷惑メール] をクリックし、次のオプションが使用可能な場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c6d27-190">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-190">**Report as Junk**</span></span>
  - <span data-ttu-id="c6d27-191">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="c6d27-192">**迷惑メール報告オプション**</span><span class="sxs-lookup"><span data-stu-id="c6d27-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="c6d27-193">**迷惑メール のヘルプを報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-193">**Report Junk Online Help**</span></span>

  ![リボンから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="c6d27-195">メッセージを右クリックし、[迷惑メール] **を選択して**、次のオプションが使用可能な場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c6d27-196">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-196">**Report as Junk**</span></span>
  - <span data-ttu-id="c6d27-197">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="c6d27-198">**迷惑メール報告オプション**</span><span class="sxs-lookup"><span data-stu-id="c6d27-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="c6d27-199">**迷惑メール のヘルプを報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-199">**Report Junk Online Help**</span></span>

  ![右クリックから迷惑メールまたはフィッシングメールを報告する](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="c6d27-201">複数のメッセージを選択し、右クリックして、次のオプションが使用可能なか確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c6d27-202">**迷惑メールとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-202">**Report as Junk**</span></span>
  - <span data-ttu-id="c6d27-203">**フィッシングとして報告する**</span><span class="sxs-lookup"><span data-stu-id="c6d27-203">**Report as Phishing**</span></span>

  ![右クリックから複数の迷惑メールまたはフィッシングメール メッセージを報告する](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="c6d27-205">[迷惑メール] フォルダーで以前の操作を行い、以前の迷惑メール報告オプションが [迷惑メールではない] に **なことを確認します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![[迷惑メール] フォルダーのリボンから迷惑メールまたはフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![迷惑メール フォルダー内の右クリックからの迷惑メールやフィッシングメールではないメールを報告する](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![迷惑メール フォルダー内で右クリックした複数の迷惑メール メッセージやフィッシングメール メッセージを報告する](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="c6d27-209">迷惑メール報告アドインをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="c6d27-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="c6d27-210">Outlook を終了した後、次の手順を使用して迷惑メール報告アドインをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="c6d27-211">**コントロール パネル**: Windows キー + R キーを押します。[ファイル名 **を指定** して実行] ダイアログボックスが開いたら `control appwiz.cpl` **、「OK」** と入力してクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="c6d27-212">一覧で **Microsoft 迷惑メール報告アドインを** 見つけて選択し、[アンインストール] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="c6d27-213">**Windows インストーラー パッケージ**: 適切な .msi ファイルを検索またはダウンロードし、ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="c6d27-214">**32 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c6d27-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="c6d27-215">**64 ビット**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c6d27-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="c6d27-216">表示されるダイアログで **、[Outlook** 用 Microsoft 迷惑メール報告アドインの削除] を選択し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c6d27-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="c6d27-217">**サイレント モード**: 適切な .msi ファイルを検索またはダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c6d27-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="c6d27-218">コマンド プロンプト ウィンドウで、.msi ファイルの場所に置き換え、次 \<PathToFile\> のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="c6d27-219">**32 ビット**:</span><span class="sxs-lookup"><span data-stu-id="c6d27-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="c6d27-220">**64 ビット**:</span><span class="sxs-lookup"><span data-stu-id="c6d27-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="c6d27-221">アンインストール後に Outlook を開いた場合、迷惑メール、迷惑メール、フィッシング報告のオプションがなくなります。</span><span class="sxs-lookup"><span data-stu-id="c6d27-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="c6d27-222">迷惑メール報告アドインのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c6d27-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="c6d27-223">迷惑メール報告アドインを追加した後、Outlook で問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c6d27-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="c6d27-224">このセクションでは、発生する可能性のある問題と、これらの問題を解決するためのヒントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="c6d27-225">ユーザーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c6d27-225">Troubleshooting for users</span></span>

<span data-ttu-id="c6d27-226">次の 1 つ以上の問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="c6d27-227">**[迷惑メールの報告]** をクリックしても何も起こらない</span><span class="sxs-lookup"><span data-stu-id="c6d27-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="c6d27-228">電子メール メッセージを選択した後に Outlook が応答しなくなった</span><span class="sxs-lookup"><span data-stu-id="c6d27-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="c6d27-229">"配信不能" と返され、報告された迷惑メールを配信できない</span><span class="sxs-lookup"><span data-stu-id="c6d27-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="c6d27-230">この問題を解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="c6d27-231">Outlook を閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="c6d27-232">テスト メッセージを作成して送信し、受信者がメッセージを受信したのを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="c6d27-233">問題が解決しない場合は、管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c6d27-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="c6d27-234">Microsoft にメッセージを送信するために使用できる他のメソッドについては、「メッセージとファイルを Microsoft に報告する」を [参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="c6d27-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="c6d27-235">管理者向けトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c6d27-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="c6d27-236">問題: システム管理者に連絡を求めるエラー メッセージが継続的に表示される</span><span class="sxs-lookup"><span data-stu-id="c6d27-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="c6d27-237">レジストリ キーの値 `LoggingLevel` を "Verbose" に設定します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="c6d27-238">**32 ビット Windows 上の 32 ビット Outlook:**</span><span class="sxs-lookup"><span data-stu-id="c6d27-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="c6d27-239">**64 ビット Windows 上の 32 ビット Outlook:**</span><span class="sxs-lookup"><span data-stu-id="c6d27-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="c6d27-240">**64 ビット Outlook**:</span><span class="sxs-lookup"><span data-stu-id="c6d27-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="c6d27-241">Outlook を再起動し、エラー メッセージが表示された場合にユーザーに報告を求める。</span><span class="sxs-lookup"><span data-stu-id="c6d27-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="c6d27-242">次の場所にあるログ情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="c6d27-243">Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="c6d27-244">問題: ユーザーがメッセージを報告するときに確認プロンプトを受信しない選択をしたが、プロンプトを戻す</span><span class="sxs-lookup"><span data-stu-id="c6d27-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="c6d27-245">値が `ConfirmReportJunk` "True" のレジストリ キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="c6d27-246">Outlook を再起動します。</span><span class="sxs-lookup"><span data-stu-id="c6d27-246">Restart Outlook.</span></span>
