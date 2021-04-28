---
title: Outlook で誤検知と誤検知を報告する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Outlook で誤検知と誤検知を報告し、レポート メッセージとレポートフィッシング アドインを有効にする方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065174"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="1417e-103">Outlook で誤検知と誤検知を報告する</span><span class="sxs-lookup"><span data-stu-id="1417e-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1417e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1417e-104">**Applies to**</span></span>
- [<span data-ttu-id="1417e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1417e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1417e-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1417e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1417e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1417e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="1417e-108">Exchange Online メールボックスを使用する Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1417e-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="1417e-109">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417e-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="1417e-110">ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスメールボックスにメールボックスを持つ Microsoft 365 組織では、誤検知 (スパムとしてマークされた良いメール) と偽陰性 (悪い電子メールとフィッシング許可) を Exchange Online Protection (EOP) に送信できます。</span><span class="sxs-lookup"><span data-stu-id="1417e-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="1417e-111">レポート メッセージ機能を使用する前に覚えておく必要があるもの</span><span class="sxs-lookup"><span data-stu-id="1417e-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="1417e-112">最適なユーザー申請エクスペリエンスを得る場合は、レポート メッセージ アドインまたはレポート フィッシング アドインを使用します。</span><span class="sxs-lookup"><span data-stu-id="1417e-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="1417e-113">このアドインは、Web、iOS、Android、デスクトップのすべてのプラットフォームで Outlook で機能します。</span><span class="sxs-lookup"><span data-stu-id="1417e-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="1417e-114">Exchange Online メールボックスを持つ組織の管理者である場合は、セキュリティ コンプライアンス センターの申請&使用します。</span><span class="sxs-lookup"><span data-stu-id="1417e-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="1417e-115">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417e-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="1417e-116">Microsoft、指定したメールボックス、または両方にメッセージを直接送信する構成が可能です。</span><span class="sxs-lookup"><span data-stu-id="1417e-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="1417e-117">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="1417e-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="1417e-118">Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="1417e-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="1417e-119">レポート メッセージ機能を使用する</span><span class="sxs-lookup"><span data-stu-id="1417e-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="1417e-120">迷惑メールとフィッシング メッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="1417e-120">Report junk and phishing messages</span></span>

<span data-ttu-id="1417e-121">迷惑メール以外の受信トレイまたは他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。</span><span class="sxs-lookup"><span data-stu-id="1417e-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="1417e-122">選択した **メッセージの右上隅** にある [その他の操作] 楕円をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メール] または [フィッシング]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1417e-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1417e-123">![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1417e-124">![レポート メッセージ - 迷惑メールとフィッシング](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="1417e-125">選択したメッセージは、分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="1417e-126">迷惑メールとして報告された場合は、迷惑メール フォルダーに移動しました。</span><span class="sxs-lookup"><span data-stu-id="1417e-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="1417e-127">フィッシングとして報告された場合に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="1417e-128">迷惑メールではないメッセージを報告する</span><span class="sxs-lookup"><span data-stu-id="1417e-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="1417e-129">選択した **メッセージの右上隅** にある [その他のアクションの省略記号] をクリックし、ドロップダウン メニューから [メッセージの報告] をクリックし、[迷惑メールではない] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1417e-130">![レポート メッセージ - その他のアクション](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1417e-131">![レポート メッセージ - 迷惑メールではない](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="1417e-132">選択したメッセージは分析のために Microsoft に送信され、受信トレイまたは指定したその他のフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="1417e-133">レポート メッセージとレポートフィッシング アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="1417e-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="1417e-134">Outlook および Outlook on the web (以前は Outlook Web App と呼ばれる) のレポート メッセージとレポートフィッシング アドインを使用すると、ユーザーは誤検知 (悪いマークが付いた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。</span><span class="sxs-lookup"><span data-stu-id="1417e-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="1417e-135">Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。</span><span class="sxs-lookup"><span data-stu-id="1417e-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="1417e-136">たとえば、ユーザーがレポート フィッシング アドインを使用して多くのメッセージを報告するとします。</span><span class="sxs-lookup"><span data-stu-id="1417e-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="1417e-137">この情報は、セキュリティ ダッシュボードや他のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="1417e-138">組織のセキュリティ チームは、この情報をフィッシング対策ポリシーを更新する必要がある可能性を示す指標として使用できます。</span><span class="sxs-lookup"><span data-stu-id="1417e-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="1417e-139">[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1417e-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="1417e-140">ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="1417e-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="1417e-141">詳細については、「レポート メッセージ アドインを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417e-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="1417e-142">レポート メッセージ アドインには、スパム メッセージとフィッシング メッセージの両方を報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1417e-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="1417e-143">管理者は、組織のレポート メッセージ アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1417e-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="1417e-144">[フィッシングの報告] アドインには、フィッシング メッセージのみを報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1417e-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="1417e-145">管理者は組織のレポート フィッシング アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1417e-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="1417e-146">個々のユーザーの場合は、両方のアドインを自分で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1417e-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="1417e-147">f グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織のレポート メッセージ アドインとレポート フィッシング アドインを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="1417e-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="1417e-148">どちらのアドインも、集中展開を [通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="1417e-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1417e-149">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1417e-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1417e-150">レポート メッセージ アドインとレポート フィッシング アドインの両方が、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="1417e-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="1417e-151">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="1417e-151">Outlook on the web</span></span>
  - <span data-ttu-id="1417e-152">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="1417e-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="1417e-153">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="1417e-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="1417e-154">エンタープライズ向け Microsoft 365 アプリに含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="1417e-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="1417e-155">iOS と Android 用 Outlook アプリ</span><span class="sxs-lookup"><span data-stu-id="1417e-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="1417e-156">両方のアドインは、オンプレミスの Exchange 組織の共有メールボックスまたはメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1417e-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="1417e-157">既存の Web ブラウザーは、レポート メッセージ アドインとレポート フィッシング アドインの両方で動作する必要があります。ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。</span><span class="sxs-lookup"><span data-stu-id="1417e-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="1417e-158">組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417e-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="1417e-159">詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="1417e-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="1417e-160">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417e-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="1417e-161">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417e-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="1417e-162">レポート メッセージ アドインの取得</span><span class="sxs-lookup"><span data-stu-id="1417e-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="1417e-163">自分でアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="1417e-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="1417e-164">[Microsoft AppSource] に移動し <https://appsource.microsoft.com/marketplace/apps> 、レポート メッセージ アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="1417e-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="1417e-165">レポート メッセージ アドインに直接移動するには、に移動します <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="1417e-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="1417e-166">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-166">Click **GET IT NOW**.</span></span>

   ![レポート メッセージ - 今すぐ取得する](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="1417e-168">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="1417e-169">仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1417e-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="1417e-170">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="1417e-171">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="1417e-172">![Outlook のレポート メッセージ アドイン アイコン](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="1417e-173">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="1417e-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="1417e-175">組織のアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="1417e-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="1417e-176">アドインが組織に表示するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1417e-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="1417e-177">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="1417e-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="1417e-178">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="1417e-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="1417e-179">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1417e-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="1417e-181">表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="1417e-182">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-182">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="1417e-184">表示される **[アドインの選択] ページ** で、[検索]ボックスをクリックし、[レポート メッセージ] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1417e-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="1417e-185">結果の一覧で、[レポート メッセージ] **を探し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="1417e-187">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="1417e-188">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1417e-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1417e-189">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="1417e-190">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="1417e-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="1417e-191">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="1417e-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="1417e-192">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="1417e-192">**Just me**</span></span>

   - <span data-ttu-id="1417e-193">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="1417e-194">**固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="1417e-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="1417e-195">**利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。</span><span class="sxs-lookup"><span data-stu-id="1417e-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="1417e-196">**オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1417e-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![[アドインの構成] ページ](../../media/configure-add-in.png)

   <span data-ttu-id="1417e-198">完了したら、[展開] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="1417e-199">表示される **[レポート メッセージの展開** ] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="1417e-200">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-200">After you read the information, click **Next**.</span></span>

   ![[レポート メッセージの展開] ページ](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="1417e-202">表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![[アドインのアナウンス] ページ](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="1417e-204">レポート メッセージ アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="1417e-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="1417e-205">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="1417e-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="1417e-206">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="1417e-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新しい Microsoft 365 管理センターAdd-Insの [サービスとサービス] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="1417e-208">レポート メッセージ アドインを **検索して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="1417e-209">表示される **[レポート メッセージの編集** ] フライアウトで、組織に合った設定を確認および編集します。</span><span class="sxs-lookup"><span data-stu-id="1417e-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="1417e-210">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1417e-210">When you're finished, click **Save**.</span></span>

   ![レポート メッセージ アドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="1417e-212">レポートフィッシング アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="1417e-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="1417e-213">自分でアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="1417e-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="1417e-214">[Microsoft AppSource] に移動し、レポートフィッシング <https://appsource.microsoft.com/marketplace/apps> アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="1417e-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="1417e-215">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="1417e-216">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="1417e-217">仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="1417e-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="1417e-218">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="1417e-219">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-219">In Outlook, the icon looks like this:</span></span>

  ![Outlook の [フィッシング アドインのレポート] アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="1417e-221">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="1417e-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="1417e-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="1417e-223">組織のアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="1417e-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="1417e-224">アドインが組織に表示するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1417e-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="1417e-225">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="1417e-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="1417e-226">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="1417e-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="1417e-227">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1417e-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="1417e-229">表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="1417e-230">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-230">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="1417e-232">表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、[レポートフィッシング] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="1417e-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="1417e-233">結果の一覧で[レポートフィッシング] **を探し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="1417e-234">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="1417e-235">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1417e-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1417e-236">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="1417e-237">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="1417e-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="1417e-238">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="1417e-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="1417e-239">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="1417e-239">**Just me**</span></span>

   - <span data-ttu-id="1417e-240">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="1417e-241">**固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="1417e-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="1417e-242">**利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。</span><span class="sxs-lookup"><span data-stu-id="1417e-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="1417e-243">**オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1417e-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="1417e-244">完了したら、[展開] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="1417e-245">表示される **[レポートフィッシングの** 展開] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417e-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="1417e-246">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="1417e-247">表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1417e-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="1417e-248">レポートフィッシング アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="1417e-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="1417e-249">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="1417e-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="1417e-250">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="1417e-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="1417e-251">[フィッシング のレポート] **アドインを検索して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="1417e-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="1417e-252">組織に **合った設定を** 表示、確認、および編集する [レポートのフィッシングの編集] フライアウトで行います。</span><span class="sxs-lookup"><span data-stu-id="1417e-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="1417e-253">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1417e-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="1417e-254">報告されたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="1417e-254">View and review reported messages</span></span>

<span data-ttu-id="1417e-255">ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1417e-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="1417e-256">管理者申請ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1417e-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="1417e-257">詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="1417e-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="1417e-258">報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1417e-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="1417e-259">手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="1417e-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>