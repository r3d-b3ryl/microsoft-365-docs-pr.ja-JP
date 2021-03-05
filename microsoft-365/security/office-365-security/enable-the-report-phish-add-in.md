---
title: レポートフィッシング アドインを有効にする
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Outlook および Outlook on the web 用のレポート フィッシング アドインを、個々のユーザーまたは組織全体で有効にする方法について説明します。
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453767"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="69487-103">レポート フィッシング アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="69487-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="69487-104">Exchange Online メールボックスを使用する Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69487-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="69487-105">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69487-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="69487-106">Outlook および Outlook on the web (以前は Outlook Web App と呼ばれる) のレポート メッセージとレポートフィッシング アドインを使用すると、ユーザーは誤検知 (悪いマークが付いた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。</span><span class="sxs-lookup"><span data-stu-id="69487-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="69487-107">Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。</span><span class="sxs-lookup"><span data-stu-id="69487-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="69487-108">たとえば、ユーザーがレポート フィッシング アドインを使用して多くのメッセージを報告するとします。</span><span class="sxs-lookup"><span data-stu-id="69487-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="69487-109">この情報は、セキュリティ ダッシュボード [や他のレポート](security-dashboard.md) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="69487-110">組織のセキュリティ チームは、この情報をフィッシング対策ポリシーを更新する必要がある可能性を示す指標として使用できます。</span><span class="sxs-lookup"><span data-stu-id="69487-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="69487-111">[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="69487-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="69487-112">ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="69487-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="69487-113">詳細については、「レポート メッセージ [アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="69487-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="69487-114">[フィッシングの報告] アドインには、フィッシング メッセージのみを報告するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="69487-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="69487-115">管理者は組織のレポート フィッシング アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="69487-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="69487-116">個々のユーザーである場合は、自分でレポート フィッシング [アドインを有効にできます](#get-the-report-phishing-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="69487-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="69487-117">グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織のレポート フィッシング アドイン [を有効にできます](#get-and-enable-the-report-phishing-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="69487-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="69487-118">[レポートフィッシング] Add-Inは、集中展開 [を通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="69487-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69487-119">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="69487-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="69487-120">レポート フィッシング アドインは、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="69487-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="69487-121">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="69487-121">Outlook on the web</span></span>
  - <span data-ttu-id="69487-122">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="69487-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="69487-123">Outlook 2016 for Mac 以降</span><span class="sxs-lookup"><span data-stu-id="69487-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="69487-124">エンタープライズ向け Microsoft 365 アプリに含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="69487-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="69487-125">iOS と Android 用 Outlook アプリ</span><span class="sxs-lookup"><span data-stu-id="69487-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="69487-126">レポート フィッシング アドインは、オンプレミスの Exchange 組織の共有メールボックスまたはメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="69487-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="69487-127">指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="69487-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="69487-128">詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="69487-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="69487-129">既存の Web ブラウザーは、レポート フィッシング アドインで動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69487-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="69487-130">ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。</span><span class="sxs-lookup"><span data-stu-id="69487-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="69487-131">組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69487-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="69487-132">詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="69487-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="69487-133">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69487-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="69487-134">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69487-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="69487-135">自分でレポートフィッシング アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="69487-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="69487-136">[Microsoft AppSource] に移動し、レポートフィッシング <https://appsource.microsoft.com/marketplace/apps> アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="69487-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="69487-137">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="69487-138">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="69487-139">仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="69487-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="69487-140">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="69487-141">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-141">In Outlook, the icon looks like this:</span></span>

  ![Outlook の [フィッシング アドインのレポート] アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="69487-143">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="69487-145">組織のレポート フィッシング アドインを取得して有効にする</span><span class="sxs-lookup"><span data-stu-id="69487-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="69487-146">アドインが組織に表示するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69487-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="69487-147">Microsoft 365 管理センターで、[設定アドイン] ページの [アドイン] ページに移動し、[アドイン] ページが表示しない場合は、[統合アプリ] ページの上部にある [設定統合アプリ アドイン] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="69487-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="69487-148">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="69487-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="69487-150">表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="69487-151">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-151">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="69487-153">表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、[レポートフィッシング] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="69487-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="69487-154">結果の一覧で[レポートフィッシング] **を探し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="69487-155">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="69487-156">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="69487-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="69487-157">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="69487-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="69487-158">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="69487-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="69487-159">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="69487-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="69487-160">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="69487-160">**Just me**</span></span>

   - <span data-ttu-id="69487-161">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="69487-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="69487-162">**固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="69487-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="69487-163">**利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。</span><span class="sxs-lookup"><span data-stu-id="69487-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="69487-164">**オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。</span><span class="sxs-lookup"><span data-stu-id="69487-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="69487-165">完了したら、[展開] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="69487-166">表示される **[レポートフィッシングの** 展開] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="69487-167">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="69487-168">表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="69487-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="69487-169">レポート フィッシング アドインの使い方について</span><span class="sxs-lookup"><span data-stu-id="69487-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="69487-170">アドインが割り当てられているユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="69487-171">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-171">In Outlook, the icon looks like this:</span></span>

  ![Outlook の [フィッシング アドインのレポート] アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="69487-173">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="69487-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web Report Phishing Add-in icon](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="69487-175">レポートフィッシング アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="69487-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="69487-176">Microsoft 365 管理センターで、[設定アドイン] ページの [アドイン] ページに移動し、[アドイン] ページが表示しない場合は、[統合アプリ] ページの上部にある [設定統合アプリ アドイン] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="69487-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="69487-177">[フィッシング のレポート] **アドインを検索して** 選択します。</span><span class="sxs-lookup"><span data-stu-id="69487-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="69487-178">組織に **合った設定を** 表示、確認、および編集する [レポートのフィッシングの編集] フライアウトで行います。</span><span class="sxs-lookup"><span data-stu-id="69487-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="69487-179">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69487-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="69487-180">報告されたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="69487-180">View and review reported messages</span></span>

<span data-ttu-id="69487-181">ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="69487-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="69487-182">管理者申請ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="69487-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="69487-183">詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="69487-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="69487-184">報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。</span><span class="sxs-lookup"><span data-stu-id="69487-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="69487-185">手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="69487-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
