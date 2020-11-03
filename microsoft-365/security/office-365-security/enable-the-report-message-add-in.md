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
description: 個々のユーザーまたは組織全体で、Outlook および outlook on the web 用のレポートメッセージアドインを有効にする方法について説明します。
ms.openlocfilehash: d760aa5d58e628872682131efae9d9c3b3c46734
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842454"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="08c07-103">レポート メッセージ アドインを有効にする</span><span class="sxs-lookup"><span data-stu-id="08c07-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="08c07-104">Microsoft 365 組織の Exchange Online メールボックスを使用している管理者の場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="08c07-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="08c07-105">詳細については、「 [管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="08c07-106">Outlook 用のレポートメッセージアドインと web 上の Outlook (旧称 Outlook Web App) を使用すると、ユーザーは、誤検知 (不良としてマークされた良好な電子メール) や誤検知 (無効な電子メールが許可されている) を Microsoft および分析のための関連会社に簡単に報告できます。</span><span class="sxs-lookup"><span data-stu-id="08c07-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="08c07-107">Microsoft では、これらの送信を使用して、電子メール保護テクノロジの有効性を向上させています。</span><span class="sxs-lookup"><span data-stu-id="08c07-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="08c07-108">たとえば、ユーザーが大量のメッセージをフィッシングとして報告しているとします。</span><span class="sxs-lookup"><span data-stu-id="08c07-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="08c07-109">この情報は、 [セキュリティダッシュボード](security-dashboard.md) やその他のレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="08c07-110">組織のセキュリティチームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があることを示すものとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="08c07-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="08c07-111">または、レポートメッセージアドインを使用して迷惑メールではないというフラグが付いたメッセージを多数報告している場合は、組織のセキュリティチームが [スパム対策ポリシー](configure-your-spam-filter-policies.md)を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08c07-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="08c07-112">さらに、組織で [Microsoft Defender For Office 365 プラン 1](office-365-atp.md) または [plan 2](office-365-ti.md)を使用している場合は、レポートメッセージアドインにより、組織のセキュリティチームに対して、セキュリティポリシーの確認と更新に使用できる有用な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-112">In addition, if your organization is using [Microsoft Defender for Office 365 Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="08c07-113">管理者は、組織に対してレポートメッセージアドインを有効にすることができます。また、個々のユーザーが自分でこのアドインをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="08c07-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="08c07-114">個人ユーザーの場合は、 [レポートメッセージアドインを自分自身に対して有効に](#get-the-report-message-add-in-for-yourself)することができます。</span><span class="sxs-lookup"><span data-stu-id="08c07-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="08c07-115">グローバル管理者または Exchange Online 管理者であり、Exchange が OAuth 認証を使用するように構成されている場合は、 [組織に対してレポートメッセージアドインを有効](#get-and-enable-the-report-message-add-in-for-your-organization)にすることができます。</span><span class="sxs-lookup"><span data-stu-id="08c07-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="08c07-116">レポートメッセージ Add-In は、 [一元展開](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)によって使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="08c07-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="08c07-117">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="08c07-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="08c07-118">レポートメッセージアドインは、ほとんどの Microsoft 365 サブスクリプションと、次の製品で機能します。</span><span class="sxs-lookup"><span data-stu-id="08c07-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="08c07-119">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="08c07-119">Outlook on the web</span></span>
  - <span data-ttu-id="08c07-120">Outlook 2013 SP1 以降</span><span class="sxs-lookup"><span data-stu-id="08c07-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="08c07-121">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="08c07-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="08c07-122">Outlook は、Microsoft 365 apps for Enterprise に含まれています。</span><span class="sxs-lookup"><span data-stu-id="08c07-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="08c07-123">このレポートメッセージアドインは、オンプレミスの Exchange 組織のメールボックスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="08c07-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="08c07-124">指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="08c07-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="08c07-125">詳細については、「 [ユーザーの送信ポリシー](user-submission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="08c07-126">既存の web ブラウザーは、レポートメッセージアドインと共に動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08c07-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="08c07-127">しかし、アドインが使用できない、または正常に動作しないことが判明した場合は、別のブラウザーを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="08c07-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="08c07-128">組織をインストールするには、OAuth 認証を使用するように組織を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08c07-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="08c07-129">詳細については、「 [組織でアドインの一元展開が機能するかどうかを判断](../../admin/manage/centralized-deployment-of-add-ins.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="08c07-130">管理者は、グローバル管理者役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08c07-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="08c07-131">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="08c07-132">自分用のレポートメッセージアドインを取得する</span><span class="sxs-lookup"><span data-stu-id="08c07-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="08c07-133">Microsoft AppSource に移動し、 <https://appsource.microsoft.com/marketplace/apps> レポートメッセージアドインを検索します。</span><span class="sxs-lookup"><span data-stu-id="08c07-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="08c07-134">レポートメッセージアドインに直接移動するには、に移動し <https://appsource.microsoft.com/product/office/wa104381180> ます。</span><span class="sxs-lookup"><span data-stu-id="08c07-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="08c07-135">[ **今すぐダウンロード** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-135">Click **GET IT NOW**.</span></span>

   ![レポートメッセージ-今すぐ取得](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="08c07-137">表示されるダイアログで、使用条件とプライバシーポリシーを確認し、[ **続行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="08c07-138">職場または学校アカウントを使用してサインインします (一般法人向け)。または Microsoft アカウント (個人使用)。</span><span class="sxs-lookup"><span data-stu-id="08c07-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="08c07-139">アドインがインストールされて有効になると、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="08c07-140">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-140">In Outlook, the icon looks like this:</span></span>

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="08c07-142">Web 上の Outlook では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="08c07-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="08c07-144">アドインの使用方法については、「 [レポートメッセージアドインを使用](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="08c07-145">組織のレポートメッセージアドインを取得して有効にする</span><span class="sxs-lookup"><span data-stu-id="08c07-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="08c07-146">組織にアドインが表示されるまで、最大で12時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08c07-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="08c07-147">Microsoft 365 管理センターで、[ **設定]、[統合アプリ & アドイン** ] ページに移動し、 <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> [アドインの **展開** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-147">In the Microsoft 365 admin center, go to the **Settings, integrated Apps & Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, and then click **Deploy Add-In**.</span></span>

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="08c07-149">[ **新しいアドインの展開** ] ポップアップが表示されたら、情報を確認して、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="08c07-150">次のページで、[ **ストアから選択** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-150">On the next page, click **Choose from the Store**.</span></span>

   ![新しいアドインページを展開する](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="08c07-152">[ **アドインの選択** ] ページが表示されたら、 **検索** ボックスをクリックして、[ **レポートメッセージ** ] と入力し、[ **検索** ![ 検索] アイコンをクリックし ](../../media/search-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="08c07-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message** , and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="08c07-153">結果の一覧で、[ **レポート] メッセージ** を見つけ、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="08c07-155">表示されるダイアログで、ライセンスとプライバシーの情報を確認し、[ **続行** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="08c07-156">[ **アドインの構成** ] ページが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="08c07-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="08c07-157">[ **割り当て済みのユーザー** ]: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="08c07-157">**Assigned users** : Select one of the following values:</span></span>

     - <span data-ttu-id="08c07-158">**Everyone** (既定)</span><span class="sxs-lookup"><span data-stu-id="08c07-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="08c07-159">**特定のユーザー/グループ**</span><span class="sxs-lookup"><span data-stu-id="08c07-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="08c07-160">**私だけです**</span><span class="sxs-lookup"><span data-stu-id="08c07-160">**Just me**</span></span>

   - <span data-ttu-id="08c07-161">**展開方法** : 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="08c07-161">**Deployment method** : Select one of the following values:</span></span>

     - <span data-ttu-id="08c07-162">**Fixed (既定)** : アドインは、指定されたユーザーに自動的に展開され、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="08c07-162">**Fixed (Default)** : The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="08c07-163">**利用可能** : ユーザーは、 **自宅** でアドインをインストールできます \> **Get add-ins** \> 。 **管理者が管理** するアドイン</span><span class="sxs-lookup"><span data-stu-id="08c07-163">**Available** : Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="08c07-164">**省略可能** : アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="08c07-164">**Optional** : The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![アドインページを構成する](../../media/configure-add-in.png)

   <span data-ttu-id="08c07-166">完了したら、[ **配置** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="08c07-167">[ **レポートメッセージの展開** ] ページに、進行状況レポートの後に、アドインが展開されたことを示す確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="08c07-168">情報を読み終えたら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-168">After you read the information, click **Next**.</span></span>

   ![レポートのメッセージを展開するページ](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="08c07-170">表示される [ **アドインのアナウンス** ] ページで情報を確認し、[ **閉じる** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![アドインページをアナウンスする](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="08c07-172">レポートメッセージアドインの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="08c07-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="08c07-173">アドインに割り当てられているユーザーには、次のアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="08c07-174">Outlook のアイコンは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="08c07-174">In Outlook, the icon looks like this:</span></span>

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="08c07-176">Web 上の Outlook では、アイコンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="08c07-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="08c07-178">レポートメッセージアドインについてユーザーに通知する場合は、 [レポートメッセージアドインを使用](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)するためのリンクを含めます。</span><span class="sxs-lookup"><span data-stu-id="08c07-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="08c07-179">レポートメッセージアドインの設定を確認または編集する</span><span class="sxs-lookup"><span data-stu-id="08c07-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="08c07-180">Microsoft 365 管理センターで、[ **Services & アドイン** ] ページに移動 <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> します。</span><span class="sxs-lookup"><span data-stu-id="08c07-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![新しい Microsoft 365 管理センターのサービスと Add-Ins ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="08c07-182">**レポートメッセージ** アドインを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="08c07-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="08c07-183">表示される [ **レポートメッセージの編集** ] ポップアップで、組織に合わせて設定を確認して編集します。</span><span class="sxs-lookup"><span data-stu-id="08c07-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="08c07-184">完了したら、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08c07-184">When you're finished, click **Save**.</span></span>

   ![レポートメッセージアドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="08c07-186">レポートされたメッセージの表示と確認</span><span class="sxs-lookup"><span data-stu-id="08c07-186">View and review reported messages</span></span>

<span data-ttu-id="08c07-187">ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="08c07-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="08c07-188">管理者提出ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="08c07-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="08c07-189">詳細については、「 [Microsoft へのユーザー送信の表示](admin-submission.md#view-user-submissions-to-microsoft)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="08c07-190">メールフロールール (トランスポートルールとも呼ばれる) を作成して、報告されたメッセージのコピーを送信します。</span><span class="sxs-lookup"><span data-stu-id="08c07-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="08c07-191">手順については、「 [メールフロールールを使用して、ユーザーが Microsoft に報告する内容を確認する」を](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="08c07-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
