---
title: レポート メッセージまたはレポートフィッシング アドインを有効にする
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Outlook および Outlook on the web、個々のユーザー、または組織全体に対して、レポート メッセージまたはレポート フィッシング アドインを有効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8949322b0b691d59e59e5f7b80d2b9650e4115d5
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029911"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="2282a-103">レポート メッセージまたはレポートフィッシング アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="2282a-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2282a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="2282a-104">**Applies to**</span></span>
- [<span data-ttu-id="2282a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2282a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2282a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="2282a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2282a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2282a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="2282a-108">Exchange Online メールボックスを使用する Microsoft 365 組織の管理者である場合は、Microsoft 365 Defender ポータルで申請ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2282a-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="2282a-109">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2282a-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="2282a-110">Outlook および Outlook on the web (以前は Outlook Web App と呼ばれる) のレポート メッセージとレポートフィッシング アドインを使用すると、ユーザーは誤検知 (悪いマークが付いた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。</span><span class="sxs-lookup"><span data-stu-id="2282a-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="2282a-111">Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。</span><span class="sxs-lookup"><span data-stu-id="2282a-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="2282a-112">たとえば、ユーザーがレポート フィッシング アドインを使用して多くのメッセージを報告するとします。</span><span class="sxs-lookup"><span data-stu-id="2282a-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="2282a-113">この情報は、セキュリティ ダッシュボードや他のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="2282a-114">組織のセキュリティ チームは、この情報をフィッシング対策ポリシーを更新する必要がある可能性を示す指標として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2282a-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="2282a-115">[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2282a-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="2282a-116">ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="2282a-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="2282a-117">詳細については、「レポート メッセージ アドインを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2282a-117">For more information, see Enable the Report Message add-in.</span></span>

<span data-ttu-id="2282a-118">レポート メッセージ アドインには、スパム メッセージとフィッシング メッセージの両方を報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2282a-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="2282a-119">管理者は、組織のレポート メッセージ アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2282a-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="2282a-120">[フィッシングの報告] アドインには、フィッシング メッセージのみを報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2282a-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="2282a-121">管理者は組織のレポート フィッシング アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2282a-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="2282a-122">個々のユーザーの場合は、両方のアドインを自分で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2282a-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="2282a-123">グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織のレポート メッセージ アドインとレポート フィッシング アドインを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2282a-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="2282a-124">どちらのアドインも、集中展開を [通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="2282a-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2282a-125">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="2282a-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2282a-126">レポート メッセージ アドインとレポート フィッシング アドインの両方が、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="2282a-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="2282a-127">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="2282a-127">Outlook on the web</span></span>
  - <span data-ttu-id="2282a-128">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="2282a-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="2282a-129">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="2282a-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="2282a-130">エンタープライズ向け Microsoft 365 アプリに含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="2282a-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="2282a-131">iOS と Android 用 Outlook アプリ</span><span class="sxs-lookup"><span data-stu-id="2282a-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="2282a-132">両方のアドインは、オンプレミスの Exchange 組織の共有メールボックスまたはメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2282a-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="2282a-133">既存の Web ブラウザーは、レポート メッセージ アドインとレポート フィッシング アドインの両方で動作する必要があります。ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。</span><span class="sxs-lookup"><span data-stu-id="2282a-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="2282a-134">組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2282a-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="2282a-135">詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="2282a-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="2282a-136">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2282a-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="2282a-137">詳細については [、「Microsoft 365 Defender ポータルのアクセス許可」を参照してください](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2282a-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="2282a-138">レポート メッセージ機能を使用してメッセージを報告する方法の詳細については、「Outlook で誤検知と誤検知を報告する [」を参照してください](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="2282a-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2282a-139">ユーザー申請ポリシーを使用できないので、Outlook の組み込みのレポート エクスペリエンスはお [勧めしません](./user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="2282a-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="2282a-140">代わりに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2282a-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="2282a-141">レポート メッセージ アドインの取得</span><span class="sxs-lookup"><span data-stu-id="2282a-141">Get the Report Message add-in</span></span>

### <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="2282a-142">自分でレポート メッセージ アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="2282a-142">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="2282a-143">[Microsoft AppSource] に移動し <https://appsource.microsoft.com/marketplace/apps> 、レポート メッセージ アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="2282a-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="2282a-144">レポート メッセージ アドインに直接移動するには、に移動します <https://appsource.microsoft.com/product/office/wa104381180> 。</span><span class="sxs-lookup"><span data-stu-id="2282a-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="2282a-145">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-145">Click **GET IT NOW**.</span></span>

   ![レポート メッセージ - 今すぐ取得する](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="2282a-147">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="2282a-148">仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2282a-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="2282a-149">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="2282a-150">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="2282a-151">![Outlook のレポート メッセージ アドイン アイコン](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="2282a-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="2282a-152">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="2282a-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="2282a-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="2282a-154">組織のレポート メッセージ アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="2282a-154">Get the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="2282a-155">アドインが組織に表示するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2282a-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="2282a-156">Microsoft 365 管理センターで、[設定アドイン] ページ \> **に移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="2282a-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="2282a-157">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="2282a-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="2282a-158">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2282a-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="2282a-160">表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="2282a-161">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-161">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="2282a-163">表示される **[アドインの選択] ページ** で、[検索]ボックスをクリックし、[レポート メッセージ] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2282a-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="2282a-164">結果の一覧で、[レポート メッセージ] **を探し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="2282a-166">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="2282a-167">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2282a-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2282a-168">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-168">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="2282a-169">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="2282a-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="2282a-170">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="2282a-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="2282a-171">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="2282a-171">**Just me**</span></span>

   - <span data-ttu-id="2282a-172">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-172">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="2282a-173">**固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="2282a-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="2282a-174">**利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。</span><span class="sxs-lookup"><span data-stu-id="2282a-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="2282a-175">**オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2282a-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![[アドインの構成] ページ](../../media/configure-add-in.png)

   <span data-ttu-id="2282a-177">完了したら、[展開] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="2282a-178">表示される **[レポート メッセージの展開** ] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="2282a-179">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-179">After you read the information, click **Next**.</span></span>

   ![[レポート メッセージの展開] ページ](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="2282a-181">表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![[アドインのアナウンス] ページ](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="2282a-183">レポート メッセージ アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="2282a-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="2282a-184">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="2282a-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="2282a-185">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="2282a-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![新しい Microsoft 365 管理センターAdd-Insの [サービスとサービス] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="2282a-187">レポート メッセージ アドインを **検索して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="2282a-188">表示される **[レポート メッセージの編集** ] フライアウトで、組織に合った設定を確認および編集します。</span><span class="sxs-lookup"><span data-stu-id="2282a-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="2282a-189">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2282a-189">When you're finished, click **Save**.</span></span>

   ![レポート メッセージ アドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="2282a-191">レポートフィッシング アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="2282a-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="2282a-192">自分でレポートフィッシング アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="2282a-192">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="2282a-193">[Microsoft AppSource] に移動し、レポートフィッシング <https://appsource.microsoft.com/marketplace/apps> アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="2282a-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="2282a-194">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="2282a-195">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="2282a-196">仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="2282a-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="2282a-197">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="2282a-198">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-198">In Outlook, the icon looks like this:</span></span>

  ![Outlook の [フィッシング アドインのレポート] アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="2282a-200">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="2282a-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="2282a-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="2282a-202">組織のレポート フィッシング アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="2282a-202">Get the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="2282a-203">アドインが組織に表示するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2282a-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="2282a-204">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="2282a-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="2282a-205">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="2282a-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="2282a-206">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2282a-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="2282a-208">表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="2282a-209">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-209">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="2282a-211">表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、[レポートフィッシング] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="2282a-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="2282a-212">結果の一覧で[レポートフィッシング] **を探し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="2282a-213">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="2282a-214">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2282a-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2282a-215">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-215">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="2282a-216">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="2282a-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="2282a-217">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="2282a-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="2282a-218">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="2282a-218">**Just me**</span></span>

   - <span data-ttu-id="2282a-219">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-219">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="2282a-220">**固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="2282a-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="2282a-221">**利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。</span><span class="sxs-lookup"><span data-stu-id="2282a-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="2282a-222">**オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2282a-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="2282a-223">完了したら、[展開] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="2282a-224">表示される **[レポートフィッシングの** 展開] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2282a-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="2282a-225">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="2282a-226">表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2282a-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="2282a-227">レポートフィッシング アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="2282a-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="2282a-228">Microsoft 365 管理センターの [設定アドイン]ページに \> **移動** します <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> 。</span><span class="sxs-lookup"><span data-stu-id="2282a-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="2282a-229">アドイン ページが表示しない場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] \>  \> **リンクに移動** します。</span><span class="sxs-lookup"><span data-stu-id="2282a-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="2282a-230">[フィッシング のレポート] **アドインを検索して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="2282a-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="2282a-231">組織に **合った設定を** 表示、確認、および編集する [レポートのフィッシングの編集] フライアウトで行います。</span><span class="sxs-lookup"><span data-stu-id="2282a-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="2282a-232">完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2282a-232">When you're finished, click **Save**.</span></span>
