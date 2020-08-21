---
title: レポート メッセージ アドインを有効にする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Outlook および Web 上の Outlook のメッセージ報告アドインを、個々のユーザーまたは組織全体に対して有効にする方法を説明します。
ms.openlocfilehash: 45f67e4c88d311254a0d922baed66178c3f672a5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826639"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="24671-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="24671-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="24671-104">Exchange Online メールボックスを持つ Microsoft 365 組織の管理者の場合は、セキュリティ/コンプライアンス センターの提出ポータルを使用&ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24671-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="24671-105">詳細については、「管理者送信 [を使用して、スパム、フィッシング、URL、ファイルを Microsoft に送信する」を参照してください](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="24671-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="24671-106">Outlook および Web 上の Outlook (以前の Outlook Web App) 用迷惑メール報告アドインを使用すると、Microsoft およびその関連物に対して誤検知 (適切でないメールのマークが付けられています) や、誤って分析を行うために誤検知 (悪意のあるメールとして許可) を簡単に報告できます。</span><span class="sxs-lookup"><span data-stu-id="24671-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="24671-107">Microsoft は、これらの申請を使用して、電子メール保護テクノロジの効果を向上させております。</span><span class="sxs-lookup"><span data-stu-id="24671-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="24671-108">たとえば、多数のメッセージがフィッシングとして報告されているとします。</span><span class="sxs-lookup"><span data-stu-id="24671-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="24671-109">この情報は、セキュリティ ダッシュボードやその [他のレポート](security-dashboard.md) に示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="24671-110">組織のセキュリティ チームはこの情報を、フィッシング対策ポリシーの更新が必要かを示す上で使用できます。</span><span class="sxs-lookup"><span data-stu-id="24671-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="24671-111">また、迷惑メールとして迷惑メールとしてフラグが付けられますが、迷惑メールとして迷惑メールとして迷惑メールと報告されるメッセージの多くは、組織のセキュリティ チームがスパム対策ポリシーの調整 [を必要とする場合があります](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="24671-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="24671-112">さらに、組織で [Office 365 Advanced Threat Protection プラン 1](office-365-atp.md) またはプラン [2](office-365-ti.md)を使用している場合も、メッセージ報告アドインは組織のセキュリティ チームに役立つ情報を提供し、そのチームがセキュリティ ポリシーを確認および更新するために使用できる有用な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24671-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="24671-113">管理者は、組織に対してメッセージ報告アドインを有効にすり、個々のユーザーが自分でこのアドインをインストールできるようになります。</span><span class="sxs-lookup"><span data-stu-id="24671-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="24671-114">個別のユーザーの場合は、自分 [のユーザーのメッセージ報告アドインを有効にできます](#get-the-report-message-add-in-for-yourself)。</span><span class="sxs-lookup"><span data-stu-id="24671-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="24671-115">グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、 [組織のメッセージ報告アドインを有効にできます](#get-and-enable-the-report-message-add-in-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="24671-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="24671-116">メッセージ報告アドインは、一元展開によって [利用できるようになりました](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。</span><span class="sxs-lookup"><span data-stu-id="24671-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="24671-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="24671-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="24671-118">メッセージ報告アドインは、ほとんどの Microsoft 365 サブスクリプションと次の製品で機能します。</span><span class="sxs-lookup"><span data-stu-id="24671-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="24671-119">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="24671-119">Outlook on the web</span></span>
  - <span data-ttu-id="24671-120">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="24671-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="24671-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="24671-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="24671-122">Microsoft 365 Apps for Enterprise に含まれる Outlook</span><span class="sxs-lookup"><span data-stu-id="24671-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="24671-123">メッセージ報告アドインは、オンプレミス Exchange 組織内のメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="24671-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="24671-124">報告されたメッセージを、指定したメールボックスにコピーまたはリダイレクトする構成ができます。</span><span class="sxs-lookup"><span data-stu-id="24671-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="24671-125">詳細については [、「Exchange Online でスパムやフィッシング メッセージのユーザーを送信するためのメールボックスを指定する」を参照してください](user-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="24671-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="24671-126">既存の Web ブラウザーは、レポート メッセージ アドインを使用できるはい。</span><span class="sxs-lookup"><span data-stu-id="24671-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="24671-127">しかし、アドインが使用できないか、または期待したとおりに機能しない場合は、別のブラウザーを試してください。</span><span class="sxs-lookup"><span data-stu-id="24671-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="24671-128">組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24671-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="24671-129">詳細については、アドイン [の一元展開が組織で動作しているかどうかを判断する」を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。</span><span class="sxs-lookup"><span data-stu-id="24671-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="24671-130">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="24671-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="24671-131">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24671-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="24671-132">自分用のレポート メッセージ アドインを入手する</span><span class="sxs-lookup"><span data-stu-id="24671-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="24671-133">Microsoft AppSource に移動して <https://appsource.microsoft.com/marketplace/apps> 、レポート メッセージ アドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="24671-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="24671-134">メッセージ報告アドインに直接アクセスするには、次に進み <https://appsource.microsoft.com/product/office/wa104381180> 、.</span><span class="sxs-lookup"><span data-stu-id="24671-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="24671-135">Click **GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="24671-135">Click **GET IT NOW**.</span></span>

   ![レポート メッセージ - 今すぐ入手](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="24671-137">表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24671-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="24671-138">職場または学校のアカウント (一名: 企業用) または Microsoft アカウント (個人用使用用) を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="24671-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="24671-139">アドインをインストールして有効にすると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="24671-140">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook のメッセージ報告アドイン アイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="24671-142">Outlook on the web では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="24671-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web 報告アドイン アイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="24671-144">アドインの使用方法については、「レポート メッセージ [アドインを使用する」を参照してください](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="24671-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="24671-145">組織のレポート メッセージ報告アドインを取得し有効にする</span><span class="sxs-lookup"><span data-stu-id="24671-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="24671-146">アドインが組織に表示するまで最大 12 時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="24671-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="24671-147">Microsoft 365 管理センター ([アドインの展開 **&で、[アドインの** 展開] ページに <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="24671-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="24671-149">表示される **新しいアドイン のポップ** アップを展開するには、情報を確認して、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24671-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="24671-150">次のページで、ストアから **Choose from the Store**.</span><span class="sxs-lookup"><span data-stu-id="24671-150">On the next page, click **Choose from the Store**.</span></span>

   ![[新しいアドイン ページの展開] ページ](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="24671-152">表示される**アドインの選択ページで**、[検索] ボックスをクリック**Search**し、[レポート**メッセージ] と入力**して、[検索] アイコン**を** ![ クリックします ](../../media/search-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="24671-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="24671-153">結果の一覧で、[レポート メッセージ] **を検索し、[** 追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="24671-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![アドイン検索結果を選択する](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="24671-155">表示されるダイアログで、ライセンスとプライバシーの情報を確認し、[続行] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24671-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="24671-156">表示される **[アドインの構成]** ページで、以下の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="24671-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="24671-157">**割り当て**済みユーザー: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="24671-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="24671-158">**すべてのユーザー** (既定)</span><span class="sxs-lookup"><span data-stu-id="24671-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="24671-159">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="24671-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="24671-160">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="24671-160">**Just me**</span></span>

   - <span data-ttu-id="24671-161">**[Deployment method]**(展開方法): 次の値のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="24671-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="24671-162">**固定 (既定値)**: アドインは指定されたユーザーに自動的に展開され、ユーザーはこれを削除できません。</span><span class="sxs-lookup"><span data-stu-id="24671-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="24671-163">**使用可能**: ユーザーは、[ **自**宅でアドインを \> **取得] にインストール** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="24671-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="24671-164">**省略可能**: アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="24671-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![[アドイン] ページの構成](../../media/configure-add-in.png)

   <span data-ttu-id="24671-166">完了したら、[展開] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24671-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="24671-167">表示 **される [レポート メッセージ** の展開] ページには進行状況レポートの後に、アドインが展開されたかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="24671-168">情報を読み込んでから、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="24671-168">After you read the information, click **Next**.</span></span>

   ![[レポート メッセージの展開] ページ](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="24671-170">表示される **[アナンス] アドイン** ページで情報を確認し、[閉じる] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="24671-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![[アドインのアナンス] ページ](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="24671-172">レポート メッセージ アドインの使用方法</span><span class="sxs-lookup"><span data-stu-id="24671-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="24671-173">アドインが割り当てられたユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="24671-174">Outlook では、アイコンは次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="24671-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook のメッセージ報告アドイン アイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="24671-176">Outlook on the web では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="24671-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web 報告アドイン アイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="24671-178">ユーザーに報告報告アドインについて通知する場合は、電子メール報告アドイン [を使用するリンクを含める必要があります](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。</span><span class="sxs-lookup"><span data-stu-id="24671-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="24671-179">メッセージ報告アドインの設定の確認または編集</span><span class="sxs-lookup"><span data-stu-id="24671-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="24671-180">Microsoft 365 管理センターで、次の場所 **の &で [アドインのサービス] ページ** に移動します <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> 。</span><span class="sxs-lookup"><span data-stu-id="24671-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="24671-182">メッセージ報告アドイン **を検索** して選択します。</span><span class="sxs-lookup"><span data-stu-id="24671-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="24671-183">表示される **[レポート メッセージの編集** ] ポップアップで、組織に応じて設定を確認し、編集します。</span><span class="sxs-lookup"><span data-stu-id="24671-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="24671-184">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24671-184">When you're finished, click **Save**.</span></span>

   ![レポート メッセージ アドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="24671-186">報告されたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="24671-186">View and review reported messages</span></span>

<span data-ttu-id="24671-187">ユーザーが Microsoft に報告したメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="24671-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="24671-188">管理者の提出ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="24671-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="24671-189">詳細については、「ユーザーが [Microsoft に提出したユーザーを表示する」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="24671-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="24671-190">報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成する。</span><span class="sxs-lookup"><span data-stu-id="24671-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="24671-191">手順については、「メール フロー [ルールを使用して、ユーザーが Microsoft に報告する内容を参照する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="24671-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
