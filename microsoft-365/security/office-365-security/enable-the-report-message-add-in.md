---
title: レポート メッセージ アドインを有効にする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 個々のユーザーまたは組織全体で、Outlook および outlook on the web 用のレポートメッセージアドインを有効にする方法について説明します。
ms.openlocfilehash: 0024e8c87ef6326c1df4547349631c4f1fd4cab8
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921578"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="72146-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="72146-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="72146-104">Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="72146-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="72146-105">詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72146-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="72146-106">Outlook 用のレポートメッセージアドインと web 上の Outlook (旧称 Outlook Web App) を使用すると、ユーザーは、誤検知 (不良としてマークされた良好な電子メール) や誤検知 (無効な電子メールが許可されている) を Microsoft および分析のための関連会社に簡単に報告できます。</span><span class="sxs-lookup"><span data-stu-id="72146-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="72146-107">Microsoft では、これらの送信を使用して、電子メール保護テクノロジの有効性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="72146-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="72146-108">たとえば、ユーザーが大量のメッセージをフィッシングとして報告しているとします。</span><span class="sxs-lookup"><span data-stu-id="72146-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="72146-109">この情報は、[セキュリティダッシュボード](security-dashboard.md)やその他のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="72146-110">組織のセキュリティチームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があることを示すものとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="72146-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="72146-111">または、レポートメッセージアドインを使用して迷惑メールではないというフラグが付いたメッセージを多数報告している場合は、組織のセキュリティチームが[スパム対策ポリシー](configure-your-spam-filter-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72146-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="72146-112">さらに、組織で[Office 365 Advanced Threat Protection プラン 1](office-365-atp.md)または[Plan 2](office-365-ti.md)を使用している場合は、レポートメッセージアドインにより、組織のセキュリティチームに対して、セキュリティポリシーの確認と更新に使用できる有用な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="72146-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="72146-113">管理者は、組織に対してレポートメッセージアドインを有効にすることができます。また、個々のユーザーが自分でこのアドインをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="72146-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="72146-114">個人ユーザーの場合は、[レポートメッセージアドインを自分自身に対して有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="72146-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="72146-115">グローバル管理者または Exchange Online 管理者であり、Exchange が OAuth 認証を使用するように構成されている場合は、[組織に対してレポートメッセージアドインを有効](#get-and-enable-the-report-message-add-in-for-your-organization)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="72146-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="72146-116">これで、レポートメッセージアドインが[一元展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)によって利用可能になりました。</span><span class="sxs-lookup"><span data-stu-id="72146-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="72146-117">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="72146-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="72146-118">レポートメッセージアドインは、ほとんどの Microsoft 365 サブスクリプションと、次の製品で機能します。</span><span class="sxs-lookup"><span data-stu-id="72146-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="72146-119">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="72146-119">Outlook on the web</span></span>
  - <span data-ttu-id="72146-120">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="72146-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="72146-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="72146-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="72146-122">Outlook は、Microsoft 365 apps for Enterprise に含まれています。</span><span class="sxs-lookup"><span data-stu-id="72146-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="72146-123">レポートメッセージアドインは現在、次の場合には使用できません。</span><span class="sxs-lookup"><span data-stu-id="72146-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="72146-124">オンプレミスの Exchange 組織内のメールボックス</span><span class="sxs-lookup"><span data-stu-id="72146-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="72146-125">GCC、GCC HIGH、または DoD サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="72146-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="72146-126">指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="72146-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="72146-127">詳細については、「 [Office 365 でスパムおよびフィッシングのメッセージをユーザーが送信するためのメールボックスを指定](user-submission.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72146-127">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="72146-128">既存の web ブラウザーは、レポートメッセージアドインと共に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72146-128">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="72146-129">しかし、アドインが使用できない、または正常に動作しないことが判明した場合は、別のブラウザーを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="72146-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="72146-130">組織をインストールするには、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72146-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="72146-131">詳細については、「[組織でアドインの一元展開が機能するかどうかを判断](../../admin/manage/centralized-deployment-of-add-ins.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72146-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="72146-132">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="72146-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="72146-133">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72146-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="72146-134">自分用のレポートメッセージアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="72146-134">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="72146-135">Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps>に移動し、レポートメッセージアドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="72146-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="72146-136">レポートメッセージアドインに直接移動するには、に<https://appsource.microsoft.com/product/office/wa104381180>移動します。</span><span class="sxs-lookup"><span data-stu-id="72146-136">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="72146-137">[**今すぐダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-137">Click **GET IT NOW**.</span></span>

   ![レポートメッセージ-今すぐ取得](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="72146-139">表示されるダイアログで、使用条件とプライバシーポリシーを確認し、[**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-139">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="72146-140">職場または学校アカウントを使用してサインインします (一般法人向け)。または Microsoft アカウント (個人使用)。</span><span class="sxs-lookup"><span data-stu-id="72146-140">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="72146-141">アドインがインストールされて有効になると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-141">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="72146-142">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-142">In Outlook, the icon looks like this:</span></span>

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="72146-144">Web 上の Outlook では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="72146-144">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="72146-146">アドインの使用方法については、「[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72146-146">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="72146-147">組織のレポートメッセージアドインを取得して有効にする</span><span class="sxs-lookup"><span data-stu-id="72146-147">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="72146-148">組織にアドインが表示されるまで、最大で12時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="72146-148">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="72146-149">Microsoft 365 管理センターで、[ **Services & アドイン**] ページ<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>に移動し、[**アドインの展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-149">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="72146-151">[**新しいアドインの展開**] ポップアップが表示されたら、情報を確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="72146-152">次のページで、[**ストアから選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-152">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドインページを展開する](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="72146-154">[**アドインの選択**] ページが表示されたら、**検索**ボックスをクリックして、[**レポートメッセージ**] と入力し](../../media/search-icon.png)、[**検索** ![検索] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="72146-155">結果の一覧で、[**レポート] メッセージ**を見つけ、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="72146-157">表示されるダイアログで、ライセンスとプライバシーの情報を確認し、[**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="72146-158">[**アドインの構成**] ページが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="72146-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="72146-159">[**割り当て済みのユーザー**]: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="72146-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="72146-160">**Everyone** (既定)</span><span class="sxs-lookup"><span data-stu-id="72146-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="72146-161">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="72146-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="72146-162">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="72146-162">**Just me**</span></span>

   - <span data-ttu-id="72146-163">**展開方法**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="72146-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="72146-164">**Fixed (既定)**: アドインは、指定されたユーザーに自動的に展開され、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="72146-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="72146-165">**利用可能**: ユーザーは、**自宅** \> **Get add-ins** \>でアドインをインストールできます。**管理者が管理**するアドイン</span><span class="sxs-lookup"><span data-stu-id="72146-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="72146-166">**省略可能**: アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="72146-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![アドインページを構成する](../../media/configure-add-in.png)

   <span data-ttu-id="72146-168">完了したら、[**配置**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-168">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="72146-169">[**レポートメッセージの展開**] ページに、進行状況レポートの後に、アドインが展開されたことを示す確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="72146-170">情報を読み終えたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-170">After you read the information, click **Next**.</span></span>

   ![レポートのメッセージを展開するページ](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="72146-172">表示される [**アドインのアナウンス**] ページで情報を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![アドインページをアナウンスする](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="72146-174">レポートメッセージアドインの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="72146-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="72146-175">アドインに割り当てられているユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="72146-176">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="72146-176">In Outlook, the icon looks like this:</span></span>

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="72146-178">Web 上の Outlook では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="72146-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="72146-180">レポートメッセージアドインについてユーザーに通知する場合は、[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)するためのリンクを含めます。</span><span class="sxs-lookup"><span data-stu-id="72146-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="72146-181">レポートメッセージアドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="72146-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="72146-182">Microsoft 365 管理センターで、[ **Services & アドイン**] ページに移動<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>します。</span><span class="sxs-lookup"><span data-stu-id="72146-182">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="72146-184">**レポートメッセージ**アドインを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="72146-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="72146-185">表示される [**レポートメッセージの編集**] ポップアップで、組織に合わせて設定を確認して編集します。</span><span class="sxs-lookup"><span data-stu-id="72146-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="72146-186">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72146-186">When you're finished, click **Save**.</span></span>

   ![レポートメッセージアドインの設定](../../media/EditReportMessageAddIn.png)
