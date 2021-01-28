---
title: フィッシング報告アドインを有効にする
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
description: 個々のユーザーまたは組織全体に対して、Outlook および Outlook on the web の Report Phishing アドインを有効にする方法について説明します。
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029140"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="c90ef-103">レポート フィッシング アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="c90ef-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c90ef-104">Exchange Online メールボックスを使用している Microsoft 365 組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータルを&勧めします。</span><span class="sxs-lookup"><span data-stu-id="c90ef-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c90ef-105">詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c90ef-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c90ef-106">Outlook および Outlook on the web (旧称 Outlook Web App) 用の Report Message and Report Phishing アドインを使用すると、分析のために誤検知 (良いメールが悪いとマークされている) や検出検出 (不正な電子メールを許可) を Microsoft とその関連会社に簡単に報告できます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c90ef-107">Microsoft は、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c90ef-108">たとえば、ユーザーが Report Phishing アドインを使用して多数のメッセージを報告するとします。</span><span class="sxs-lookup"><span data-stu-id="c90ef-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c90ef-109">この情報は、セキュリティ ダッシュボード [および他のレポート](security-dashboard.md) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c90ef-110">組織のセキュリティ チームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があるという指標として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="c90ef-111">レポート メッセージ アドインまたは Report Phishing アドインをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c90ef-112">ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c90ef-113">詳細については、「メッセージ報告 [アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c90ef-114">Report Phishing アドインは、フィッシング メッセージのみを報告するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c90ef-115">管理者は組織の Report Phishing アドインを有効にし、個々のユーザーが自分でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c90ef-116">個人ユーザーの場合は、自分で [Report Phishing アドインを有効にできます](#get-the-report-phishing-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="c90ef-117">グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織の Report [Phishing アドインを有効にできます](#get-and-enable-the-report-phishing-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="c90ef-118">Report Phishing Add-Inは、一元展開 [で利用できます](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c90ef-119">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c90ef-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c90ef-120">レポート フィッシング アドインは、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c90ef-121">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="c90ef-121">Outlook on the web</span></span>
  - <span data-ttu-id="c90ef-122">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="c90ef-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c90ef-123">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="c90ef-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c90ef-124">エンタープライズ向け Microsoft 365 アプリに含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="c90ef-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="c90ef-125">レポート フィッシング アドインは、オンプレミスの Exchange 組織のメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c90ef-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c90ef-126">指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c90ef-127">詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c90ef-128">既存の Web ブラウザーは、Report Phishing アドインで動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c90ef-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="c90ef-129">ただし、アドインが使用できないか、期待通り動作しない場合は、別のブラウザーを試してください。</span><span class="sxs-lookup"><span data-stu-id="c90ef-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c90ef-130">組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c90ef-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c90ef-131">詳細については、「アドインの一元展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c90ef-132">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c90ef-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c90ef-133">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c90ef-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="c90ef-134">自分用の Report Phishing アドインを取得する</span><span class="sxs-lookup"><span data-stu-id="c90ef-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="c90ef-135">Microsoft AppSource に移動し <https://appsource.microsoft.com/marketplace/apps> 、フィッシング報告アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c90ef-136">[今 **すぐ取得] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c90ef-137">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c90ef-138">(業務用) または Microsoft アカウント (個人使用の場合) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c90ef-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c90ef-139">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c90ef-140">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook のフィッシング報告アドイン アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c90ef-142">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web Report Phishing アドイン アイコン](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="c90ef-144">組織の Report Phishing アドインを取得して有効にする</span><span class="sxs-lookup"><span data-stu-id="c90ef-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c90ef-145">アドインが組織に表示されるには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c90ef-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c90ef-146">Microsoft 365 管理センターで、[設定アドイン] ページに移動します。[アドイン] ページが表示されな場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="c90ef-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c90ef-147">ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c90ef-149">表示される **新しいアドイン の展開** のフライアウトで、情報を確認し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c90ef-150">次のページで、[ストアから **選択] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-150">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドイン ページを展開する](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c90ef-152">表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、「Report **Phishing」** と入力して、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="c90ef-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c90ef-153">結果の一覧で[レポートフィッシング] **を** 見つけ、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c90ef-154">表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c90ef-155">表示される **[アドインの構成]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c90ef-156">**割り当てられたユーザー**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c90ef-157">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="c90ef-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="c90ef-158">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="c90ef-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="c90ef-159">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="c90ef-159">**Just me**</span></span>

   - <span data-ttu-id="c90ef-160">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c90ef-161">**固定 (既定値)**: アドインは指定されたユーザーに自動的に展開され、削除できない。</span><span class="sxs-lookup"><span data-stu-id="c90ef-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c90ef-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="c90ef-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c90ef-163">**オプション**: アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c90ef-164">完了したら、[展開] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c90ef-165">表示 **される [レポートフィッシング** の展開] ページに、進行状況レポートの後に、アドインが展開されたという確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c90ef-166">情報を読んだら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c90ef-167">表示された **[アドインのアナウンス** ] ページで情報を確認し、[閉じる] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c90ef-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="c90ef-168">レポート フィッシング アドインの使い方について</span><span class="sxs-lookup"><span data-stu-id="c90ef-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="c90ef-169">アドインが割り当てられているユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c90ef-170">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-170">In Outlook, the icon looks like this:</span></span>

  ![Outlook のフィッシング報告アドイン アイコン](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c90ef-172">Outlook on the web では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="c90ef-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web Report Phishing Add-in アイコン](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c90ef-174">レポート フィッシング アドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="c90ef-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c90ef-175">Microsoft 365 管理センターで、[設定アドイン] ページに移動します。[アドイン] ページが表示されな場合は、[統合アプリ] ページの上部にある [統合アプリの設定] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  </span><span class="sxs-lookup"><span data-stu-id="c90ef-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c90ef-176">フィッシング報告アドイン **を見つけて** 選択します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c90ef-177">組織に **応じて表示** 、確認、および編集の設定を行う [レポートフィッシングの編集] フライアウトで。</span><span class="sxs-lookup"><span data-stu-id="c90ef-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c90ef-178">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c90ef-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c90ef-179">報告されたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="c90ef-179">View and review reported messages</span></span>

<span data-ttu-id="c90ef-180">ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c90ef-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c90ef-181">管理者提出ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c90ef-182">詳細については、「Microsoft へのユーザー [申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c90ef-183">メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、報告されたメッセージのコピーを送信します。</span><span class="sxs-lookup"><span data-stu-id="c90ef-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c90ef-184">手順については、「メール フロー ルール [を使用して、ユーザーが Microsoft に報告している情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="c90ef-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>