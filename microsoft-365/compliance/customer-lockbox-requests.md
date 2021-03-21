---
title: 顧客ロックボックス要求
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 問題が発生した場合に Microsoft サポート エンジニアがデータにアクセスする方法を制御できるカスタマー ロックボックス要求について説明します。
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922711"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="96d67-103">顧客ロックボックス (Office 365)</span><span class="sxs-lookup"><span data-stu-id="96d67-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="96d67-104">この記事では、Customer Lockbox の展開と構成のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="96d67-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="96d67-105">Customer Lockbox は、Exchange Online、SharePoint Online、OneDrive for Business のデータへのアクセス要求をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="96d67-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="96d67-106">他のサービスのサポートをお勧めするには [、365 UserVoice](https://office365.uservoice.com/)のOffice送信してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="96d67-107">2020 年 4 月 1 日の時点で、Microsoft 365 コンプライアンス製品を含む Microsoft 365 コンプライアンス製品の恩恵を受けるユーザーにライセンスを提供するためのオプションについては、セキュリティ & コンプライアンスに関する [Microsoft 365 ライセンス ガイダンスを参照](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="96d67-108">カスタマー ロックボックスを使用すると、Microsoft は明示的な承認なしにサービス操作を実行するためにコンテンツにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="96d67-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="96d67-109">Customer Lockbox を使用すると、コンテンツにアクセスする要求の承認ワークフローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="96d67-110">Microsoft のエンジニアが、サポート プロセスで報告された問題のトラブルシューティングと修正に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="96d67-111">通常、Microsoft がサービスの広範な利用統計情報とデバッグ ツールを使用して問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="96d67-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="96d67-112">ただし、根本原因を特定して問題を解決するために、Microsoft のエンジニアが顧客コンテンツにアクセスする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="96d67-113">カスタマー ロックボックスでは、承認ワークフローの最終ステップとして、エンジニアが顧客にアクセス要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="96d67-114">これにより、組織は、これらの要求を承認または拒否し、顧客に直接アクセス制御を提供できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="96d67-115">カスタマー ロックボックスの概要ビデオ</span><span class="sxs-lookup"><span data-stu-id="96d67-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="96d67-116">カスタマー ロックボックスのワークフロー</span><span class="sxs-lookup"><span data-stu-id="96d67-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="96d67-117">次の手順では、Microsoft エンジニアが Customer Lockbox 要求を開始する際の一般的なワークフローの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="96d67-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="96d67-118">組織の誰かが Microsoft 365 メールボックスに問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="96d67-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="96d67-119">ユーザーが問題をトラブルシューティングしても解決できない場合は、Microsoft サポートでサポート要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="96d67-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="96d67-120">Microsoft サポート エンジニアは、サービス要求を確認し、Exchange Online で問題を修復するために組織のテナントにアクセスする必要性を決定します。</span><span class="sxs-lookup"><span data-stu-id="96d67-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="96d67-121">Microsoft サポート エンジニアは、Customer Lockbox 要求ツールにログインし、組織のテナント名、サービス要求番号、およびエンジニアがデータにアクセスする必要がある推定時間を含むデータ アクセス要求を行います。</span><span class="sxs-lookup"><span data-stu-id="96d67-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="96d67-122">Microsoft サポート マネージャーが要求を承認した後、カスタマー ロックボックスは、Microsoft からの保留中のアクセス要求に関する電子メール通知を組織内の指定された承認者に送信します。</span><span class="sxs-lookup"><span data-stu-id="96d67-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![顧客ロックボックスの電子メール通知の例](../media/CustomerLockbox1.png)

   <span data-ttu-id="96d67-124">Microsoft 365 管理センター [で Customer Lockbox アクセス承認](/office365/admin/add-users/about-admin-roles) 者管理者の役割が割り当てられているすべてのユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-124">Anyone who is assigned the [Customer Lockbox access approver](/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="96d67-125">承認者は Microsoft 365 管理センターにサインインし、要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="96d67-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="96d67-126">この手順では、監査ログの検索によって使用可能な監査レコードの作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="96d67-127">詳細については [、「Auditing Customer Lockbox requests」を参照してください](#auditing-customer-lockbox-requests)。</span><span class="sxs-lookup"><span data-stu-id="96d67-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="96d67-128">顧客が要求を拒否した場合、または 12 時間以内に要求を承認しない場合、要求の有効期限が切れ、Microsoft エンジニアにアクセス権は付与されません。</span><span class="sxs-lookup"><span data-stu-id="96d67-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="96d67-129">Microsoft では、ユーザーが 365 にサインインする必要があるカスタマー ロックボックスの電子メール通知にリンクOfficeされません。</span><span class="sxs-lookup"><span data-stu-id="96d67-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="96d67-130">組織からの承認者が要求を承認した後、Microsoft エンジニアは承認メッセージを受信し、Exchange Online のテナントにログインして、お客様の問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="96d67-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="96d67-131">Microsoft のエンジニアは、アクセスが自動的に取り消された後に問題を解決するために要求された期間を持っています。</span><span class="sxs-lookup"><span data-stu-id="96d67-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="96d67-132">Microsoft のエンジニアによって実行されるすべての操作は、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="96d67-133">これらの監査レコードを検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="96d67-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="96d67-134">顧客ロックボックス要求をオンまたはオフにする</span><span class="sxs-lookup"><span data-stu-id="96d67-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="96d67-135">Microsoft 365 管理センターで、カスタマー ロックボックス コントロールを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="96d67-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="96d67-136">Customer Lockbox を有効にした場合、Microsoft はテナントのコンテンツにアクセスする前に組織の承認を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="96d67-137">グローバル管理者または Customer **Lockbox** アクセス承認者の役割が割り当てられている仕事または学校のアカウントを使用して、アクセスして [https://admin.microsoft.com](https://admin.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="96d67-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="96d67-138">[組織 **の設定>設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96d67-138">Choose **Settings > Org Settings**.</span></span>

3. <span data-ttu-id="96d67-139">[**セキュリティ] & [プライバシー**] [顧客ロックボックスの編集] を選択し、トグルを [オン] または [オフ] に移動して、機能のオンと  >    >  オフを切り替えます。  </span><span class="sxs-lookup"><span data-stu-id="96d67-139">Select **Security & Privacy** > **Customer Lockbox** > **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="96d67-141">カスタマー ロックボックス要求を承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="96d67-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="96d67-142">グローバル管理者または Customer **Lockbox** アクセス承認者の役割が割り当てられている仕事または学校のアカウントを使用して、アクセスして [https://admin.microsoft.com](https://admin.microsoft.com) サインインします。</span><span class="sxs-lookup"><span data-stu-id="96d67-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="96d67-143">[ **カスタマー ロックボックス>サポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96d67-143">Choose **Support > Customer Lockbox Requests**.</span></span>

    ![[サポート] をクリックし、[カスタマー ロックボックス要求] をクリックします。](../media/CustomerLockbox5.png)

    <span data-ttu-id="96d67-145">顧客ロックボックス要求の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-145">A list of Customer Lockbox requests displays.</span></span>

    ![顧客ロックボックス要求の一覧](../media/CustomerLockbox6.png)

3. <span data-ttu-id="96d67-147">顧客ロックボックス要求を選択し、[承認] または [**拒否] を\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="96d67-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny**.</span></span>

    ![顧客ロックボックス要求を承認または拒否する](../media/CustomerLockbox7.png)

    <span data-ttu-id="96d67-149">顧客ロックボックス要求の承認に関する確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![顧客ロックボックス要求を承認または拒否する](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="96d67-151">Set-AccessToCustomerDataRequest コマンドレットを使用して、Microsoft のサポート エンジニアがデータへのアクセスを制限する Microsoft 365 カスタマー ロックボックス要求を承認、拒否、キャンセルします。</span><span class="sxs-lookup"><span data-stu-id="96d67-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="96d67-152">詳細については [、「Set-AccessToCustomerDataRequest」を参照してください](/powershell/module/exchange/set-accesstocustomerdatarequest)。</span><span class="sxs-lookup"><span data-stu-id="96d67-152">For more information, see [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="96d67-153">カスタマー ロックボックス要求を監査する</span><span class="sxs-lookup"><span data-stu-id="96d67-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="96d67-154">顧客ロックボックス要求に対応する監査レコードが監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="96d67-155">これらのログにアクセスするには、コンプライアンス[](search-the-audit-log-in-security-and-compliance.md)センターの [セキュリティ] ウィンドウの監査&使用します。</span><span class="sxs-lookup"><span data-stu-id="96d67-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="96d67-156">顧客ロックボックス要求の受け入れまたは拒否に関連するアクションと、Microsoft エンジニアが実行するアクション (アクセス要求が承認された場合) も監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-156">Actions related to accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="96d67-157">これらの監査レコードを検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="96d67-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="96d67-158">顧客ロックボックス要求に関連するアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="96d67-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="96d67-159">監査ログを使用してカスタマー ロックボックスの要求を追跡できるようにするには、監査ログを設定するためにいくつかの手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="96d67-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to set up audit logging.</span></span> <span data-ttu-id="96d67-160">詳細については、「セキュリティ コンプライアンス センターで監査ログを検索 [&する」を参照してください](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)。</span><span class="sxs-lookup"><span data-stu-id="96d67-160">For more information, see [Search the audit log in the Security & Compliance Center](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="96d67-161">セットアップが完了したら、次の手順を使用して監査ログ検索クエリを作成し、Customer Lockbox に関連する監査レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="96d67-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="96d67-162">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="96d67-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="96d67-163">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="96d67-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="96d67-164">セキュリティ コンプライアンス センターの左側のウィンドウ&、[調査監査ログの&**検索**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="96d67-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="96d67-165">[ **監査ログの検索] ページ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-165">The **Audit log search** page displays.</span></span>

    ![[監査ログの検索] ページ](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="96d67-167">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="96d67-167">Configure the following search criteria:</span></span>

    1. <span data-ttu-id="96d67-168">**[アクティビティ** ] - 検索がすべてのアクティビティの監査レコードを返す場合は、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="96d67-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="96d67-169">これは、Microsoft のエンジニアが実行するカスタマー ロックボックス要求および対応するアクティビティに関連する監査レコードを返す場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="96d67-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    1. <span data-ttu-id="96d67-170">**開始日と\*\*\*\*終了日**- 日付と時刻の範囲を選択して、その期間に発生したイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="96d67-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    1. <span data-ttu-id="96d67-171">**ユーザー** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="96d67-171">**Users** - Leave this field blank.</span></span>

    1. <span data-ttu-id="96d67-172">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="96d67-172">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="96d67-173">[**検索**] をクリックして、設定した検索条件で検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="96d67-173">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="96d67-174">検索結果が読み込まれ、しばらくすると、[監査ログ検索] ページの [結果 **] に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-174">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="96d67-175">[ **検索結果] ページの** [結果のフィルター] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96d67-175">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="96d67-176">組織の承認者に関連する監査レコードを表示するには、[アクティビティ] 列の下のボックスに **「Set-AccessToCustomerDataRequest」** と入力します。 </span><span class="sxs-lookup"><span data-stu-id="96d67-176">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="96d67-177">承認済みの顧客ロックボックス要求に応じてアクションを実行する Microsoft エンジニアに関連する監査レコードを表示するには、[ユーザー]列の下のボックスに **「Microsoft Operator」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="96d67-177">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="96d67-178">[ **アクティビティ]** 列には、エンジニアが実行したアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-178">The **Activity** column displays the action performed by the engineer.</span></span>

      ![監査レコードを表示する "Microsoft Operator" のフィルター](../media/CustomerLockbox10.png)

7. <span data-ttu-id="96d67-180">結果の一覧で、監査レコードをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="96d67-180">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="96d67-181">カスタマー ロックボックス アクセス要求の監査レコード</span><span class="sxs-lookup"><span data-stu-id="96d67-181">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="96d67-182">組織内のユーザーが Customer Lockbox 要求を承認または拒否すると、監査レコードが監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-182">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="96d67-183">このレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96d67-183">This record contains the following information.</span></span>

| <span data-ttu-id="96d67-184">監査レコードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="96d67-184">Audit record property</span></span>| <span data-ttu-id="96d67-185">説明</span><span class="sxs-lookup"><span data-stu-id="96d67-185">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="96d67-186">日付</span><span class="sxs-lookup"><span data-stu-id="96d67-186">Date</span></span>       | <span data-ttu-id="96d67-187">カスタマー ロックボックス要求が承認または拒否された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="96d67-187">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="96d67-188">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="96d67-188">IP address</span></span> | <span data-ttu-id="96d67-189">要求を承認または拒否するために使用された承認者のコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="96d67-189">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="96d67-190">ユーザー</span><span class="sxs-lookup"><span data-stu-id="96d67-190">User</span></span>       | <span data-ttu-id="96d67-191">\[customerforest .BOXServiceAccount@ のサービス アカウント \] prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="96d67-191">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="96d67-192">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="96d67-192">Activity</span></span>   | <span data-ttu-id="96d67-193">Set-AccessToCustomerDataRequest: これは、カスタマー ロックボックス要求を承認または拒否したときにログに記録される監査アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="96d67-193">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="96d67-194">アイテム</span><span class="sxs-lookup"><span data-stu-id="96d67-194">Item</span></span>       | <span data-ttu-id="96d67-195">顧客ロックボックス要求の Guid</span><span class="sxs-lookup"><span data-stu-id="96d67-195">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="96d67-196">次のスクリーンショットは、承認済みの顧客ロックボックス要求に対応する監査ログ レコードの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="96d67-196">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="96d67-197">Customer Lockbox 要求が拒否された場合 **、ApprovalDecision** パラメーターの値は Deny **になります**。</span><span class="sxs-lookup"><span data-stu-id="96d67-197">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![承認済み顧客ロックボックス要求の監査レコード](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="96d67-199">監査レコードに詳細情報を表示するには、[詳細情報] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="96d67-199">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="96d67-200">Microsoft のエンジニアによって実行されたアクションの監査レコード</span><span class="sxs-lookup"><span data-stu-id="96d67-200">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="96d67-201">カスタマー ロックボックス要求が承認された後 Microsoft のエンジニアが実行するアクション (顧客コンテンツへのアクセスにつながる可能性があります) は、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-201">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="96d67-202">これらのレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="96d67-202">These records contain the following information.</span></span>

| <span data-ttu-id="96d67-203">監査レコードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="96d67-203">Audit record property</span></span>| <span data-ttu-id="96d67-204">説明</span><span class="sxs-lookup"><span data-stu-id="96d67-204">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="96d67-205">日付</span><span class="sxs-lookup"><span data-stu-id="96d67-205">Date</span></span>       | <span data-ttu-id="96d67-206">アクションが実行された日時。</span><span class="sxs-lookup"><span data-stu-id="96d67-206">Date time when the action was performed.</span></span> <span data-ttu-id="96d67-207">このアクションが実行された時刻は、カスタマー ロックボックス要求が承認されてから 4 時間以内であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-207">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="96d67-208">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="96d67-208">IP address</span></span> | <span data-ttu-id="96d67-209">Microsoft のエンジニア使用したコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="96d67-209">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="96d67-210">ユーザー</span><span class="sxs-lookup"><span data-stu-id="96d67-210">User</span></span>       | <span data-ttu-id="96d67-211">Microsoft のオペレーター。この値は、このレコードがカスタマー ロックボックス要求に関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="96d67-211">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="96d67-212">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="96d67-212">Activity</span></span>   | <span data-ttu-id="96d67-213">Microsoft のエンジニアが実行したアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="96d67-213">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="96d67-214">項目</span><span class="sxs-lookup"><span data-stu-id="96d67-214">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="96d67-215">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="96d67-215">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="96d67-216">カスタマー ロックボックスが適用する Microsoft 365 サービス</span><span class="sxs-lookup"><span data-stu-id="96d67-216">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="96d67-217">カスタマー ロックボックスは現在、Exchange Online、SharePoint Online、OneDrive for Business でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="96d67-217">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="96d67-218">顧客ロックボックスは、すべての顧客が利用できますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-218">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="96d67-219">カスタマー ロックボックスは、Microsoft 365 または Office 365 E5 サブスクリプションに含まれており、情報保護とコンプライアンス、または高度なコンプライアンス アドオン サブスクリプションを使用して他のプランに追加できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-219">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="96d67-220">詳細については [、「プランと価格」](https://products.office.com/business/office-365-enterprise-e5-business-software) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-220">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="96d67-221">顧客コンテンツとは</span><span class="sxs-lookup"><span data-stu-id="96d67-221">What is customer content?</span></span>

<span data-ttu-id="96d67-222">顧客コンテンツは、Microsoft 365 サービスおよびアプリケーションのユーザーによって作成されたデータです。</span><span class="sxs-lookup"><span data-stu-id="96d67-222">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="96d67-223">顧客コンテンツの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="96d67-223">Examples of customer content include:</span></span>

- <span data-ttu-id="96d67-224">電子メール本文またはメールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="96d67-224">Email body or email attachments</span></span>

- <span data-ttu-id="96d67-225">SharePoint サイトのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="96d67-225">SharePoint site contents</span></span>

- <span data-ttu-id="96d67-226">SharePoint ファイルの本文に含まれる情報</span><span class="sxs-lookup"><span data-stu-id="96d67-226">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="96d67-227">Skype for Business プレゼンテーション ファイル本文</span><span class="sxs-lookup"><span data-stu-id="96d67-227">Skype for Business presentation file body</span></span>

- <span data-ttu-id="96d67-228">インスタント メッセージ (IM) または音声会話</span><span class="sxs-lookup"><span data-stu-id="96d67-228">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="96d67-229">顧客が生成した blob または構造化ストレージ データ (SQL コンテナーなど)</span><span class="sxs-lookup"><span data-stu-id="96d67-229">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="96d67-230">顧客が所有するセキュリティ情報 (証明書、暗号化キー、パスワードなど)</span><span class="sxs-lookup"><span data-stu-id="96d67-230">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="96d67-231">顧客コンテンツが残っている場合の推論とそれ以降のすべての推論</span><span class="sxs-lookup"><span data-stu-id="96d67-231">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="96d67-232">Office 365 の顧客コンテンツの詳細については、「Office [365 Trust Center」を参照してください](https://products.office.com/business/office-365-trust-center-privacy/)。</span><span class="sxs-lookup"><span data-stu-id="96d67-232">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="96d67-233">自分のコンテンツにアクセスする要求がある場合、誰に通知されますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-233">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="96d67-234">グローバル管理者と、Customer Lockbox アクセス承認者管理者の役割が割り当てられているすべてのユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-234">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="96d67-235">これらは、顧客ロックボックス要求に対して承認できるユーザーと同じです。</span><span class="sxs-lookup"><span data-stu-id="96d67-235">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="96d67-236">組織内でこれらの要求を承認または拒否できるユーザー</span><span class="sxs-lookup"><span data-stu-id="96d67-236">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="96d67-237">グローバル管理者と、Customer Lockbox アクセス承認者管理者の役割が割り当てられているユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="96d67-238">お客様は、組織でこれらの役割の割り当てを制御します。</span><span class="sxs-lookup"><span data-stu-id="96d67-238">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="96d67-239">カスタマー ロックボックスにオプトインする方法</span><span class="sxs-lookup"><span data-stu-id="96d67-239">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="96d67-240">グローバル管理者は、Microsoft 365 または Microsoft 365 管理センターで顧客ロックボックスを有効にして構成できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-240">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="96d67-241">Customer Lockbox 要求を承認した場合、エンジニアは何を行い、Microsoft エンジニアが何を行ったのかをどのように知るのですか?</span><span class="sxs-lookup"><span data-stu-id="96d67-241">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="96d67-242">Customer Lockbox 要求を承認すると、Microsoft エンジニアは事前承認されたコマンドレットを使用して顧客コンテンツにアクセスするために必要なこれらの特権を付与しました。</span><span class="sxs-lookup"><span data-stu-id="96d67-242">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="96d67-243">Microsoft のエンジニアがカスタマー ロックボックス要求に応答して実行したアクションは、セキュリティ コンプライアンス センターの監査ログに記録され&アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="96d67-243">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="96d67-244">Microsoft が承認プロセスに従っているのを知る方法</span><span class="sxs-lookup"><span data-stu-id="96d67-244">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="96d67-245">Microsoft 365 管理センターの顧客ロックボックス要求履歴を使用して、組織内の管理者および承認者に送信される電子メール承認通知を相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-245">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="96d67-246">顧客ロックボックスは、最新の [SOC 1 SSAE 16 監査レポートに含まれています](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。</span><span class="sxs-lookup"><span data-stu-id="96d67-246">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="96d67-247">詳細については、Microsoft Service Trust Portal で最新のレポート [を確認できます](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)。</span><span class="sxs-lookup"><span data-stu-id="96d67-247">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="96d67-248">Microsoft はテナントの承認者の一覧を変更できますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-248">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="96d67-249">それではない場合、どのように防止されますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-249">If not, how is it prevented?</span></span>

<span data-ttu-id="96d67-250">組織内のグローバル管理者だけが、顧客ロックボックス要求を承認できるユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-250">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="96d67-251">つまり、要求を承認できるユーザーを指定できるのは、Azure Active Directory のグローバル管理者グループのメンバーのみです。</span><span class="sxs-lookup"><span data-stu-id="96d67-251">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="96d67-252">Azure Active Directory のグローバル管理者グループのメンバーシップは、組織によってのみ管理されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-252">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="96d67-253">コンテンツ アクセス要求を承認するために詳細な情報が必要な場合は、どうしますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-253">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="96d67-254">各 Customer Lockbox 要求には、Microsoft 365 サービス要求番号が含まれている。</span><span class="sxs-lookup"><span data-stu-id="96d67-254">Each Customer Lockbox request contains a Microsoft 365 service request number.</span></span> <span data-ttu-id="96d67-255">要求の詳細については、Microsoft サポートに問い合わせ、このサービス番号を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-255">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="96d67-256">Customer Lockbox 要求が承認されると、アクセス許可はどのくらい有効ですか?</span><span class="sxs-lookup"><span data-stu-id="96d67-256">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="96d67-257">現在、Microsoft のエンジニアに付与されるアクセス許可の最長期間は 4 時間です。</span><span class="sxs-lookup"><span data-stu-id="96d67-257">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="96d67-258">Microsoft のエンジニアは、より短い期間を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="96d67-258">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="96d67-259">すべての Customer Lockbox 要求の履歴を取得する方法</span><span class="sxs-lookup"><span data-stu-id="96d67-259">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="96d67-260">すべての顧客ロックボックス要求は、Microsoft 365 管理センターで表示されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-260">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="96d67-261">コンテンツ アクセス要求と関連する監査ログを関連付ける方法</span><span class="sxs-lookup"><span data-stu-id="96d67-261">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="96d67-262">コンプライアンス センターアクティビティ フィードには、Customer Lockbox のログ アクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="96d67-262">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="96d67-263">顧客は、アクティビティ フィードから Customer Lockbox ログ アクティビティを受信した電子メール要求と相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="96d67-263">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="96d67-264">顧客が Customer Lockbox 要求に応答しない場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="96d67-264">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="96d67-265">カスタマー ロックボックス要求の既定の期間は 12 時間です。</span><span class="sxs-lookup"><span data-stu-id="96d67-265">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="96d67-266">12 時間以内に要求に応答しない場合、要求の有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="96d67-266">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="96d67-267">顧客が顧客ロックボックス要求を拒否した場合、Microsoft は何をしますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-267">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="96d67-268">顧客が Customer Lockbox 要求を拒否した場合、顧客コンテンツへのアクセスは行われません。</span><span class="sxs-lookup"><span data-stu-id="96d67-268">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="96d67-269">組織内のユーザーが引き続きサービスの問題が発生し、Microsoft が問題を解決するために顧客コンテンツにアクセスする必要がある場合、サービスの問題が解決しない可能性があります。Microsoft は、この問題についてユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="96d67-269">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="96d67-270">顧客ロックボックスは、法執行機関や他の第三者からのデータ要求から保護しますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-270">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="96d67-271">いいえ。</span><span class="sxs-lookup"><span data-stu-id="96d67-271">No.</span></span> <span data-ttu-id="96d67-272">Microsoft は、顧客データに対するサードパーティの要求を真剣に受け止める。</span><span class="sxs-lookup"><span data-stu-id="96d67-272">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="96d67-273">クラウド サービス プロバイダーとして、Microsoft は常に顧客データのプライバシーを主張しています。</span><span class="sxs-lookup"><span data-stu-id="96d67-273">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="96d67-274">Subpoena が取得された場合、Microsoft は常に第三者を顧客にリダイレクトして情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="96d67-274">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="96d67-275">(Brad Smith のブログを読む: 政府のスヌーピングから顧客データ [を保護する](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。</span><span class="sxs-lookup"><span data-stu-id="96d67-275">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="96d67-276">Microsoft が受け [取る法執行](https://www.microsoft.com/corporate-responsibility/lerr) 機関の要求に関する詳細情報を定期的に公開します。</span><span class="sxs-lookup"><span data-stu-id="96d67-276">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="96d67-277">詳細については [、サードパーティ](https://www.microsoft.com/trustcenter/default.aspx) のデータ要求に関する Microsoft Trust Center と [、Online Services](https://www.microsoft.com/Licensing/product-licensing/products.aspx) の利用規約の「顧客データの開示」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-277">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="96d67-278">Microsoft では、365 のアプリケーションでスタッフのメンバーが顧客コンテンツに常にアクセスOffice方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="96d67-278">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="96d67-279">Microsoft は、アクセス制御システムを通じて広範な予防措置を実施し、これらのアクセス制御システムを回避しようとする試みを特定して対処するための探偵対策を実施しています。</span><span class="sxs-lookup"><span data-stu-id="96d67-279">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="96d67-280">Microsoft 365 は、最小特権と Just-in-time アクセスの原則を使用して動作します。</span><span class="sxs-lookup"><span data-stu-id="96d67-280">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="96d67-281">したがって、Microsoft の担当者は、継続的に顧客コンテンツにアクセスする権限を持てない。</span><span class="sxs-lookup"><span data-stu-id="96d67-281">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="96d67-282">アクセス許可が付与されている場合は、期間が制限されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-282">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="96d67-283">Microsoft 365 では *、Lockbox* と呼ばれるアクセス制御システムを使用して、サービス内で運用および管理機能を実行する権限の要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="96d67-283">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="96d67-284">オペレーターは、Lockbox を使用して顧客コンテンツへのアクセスを要求する必要があります。その後、アクセスが許可される前に、2 人目が要求に対してアクションを実行する (承認するなど) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-284">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="96d67-285">その 2 人目は要求者になけり、顧客コンテンツへのアクセスを承認するように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96d67-285">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="96d67-286">要求が承認された場合にのみ、オペレーターは顧客コンテンツへの一時的なアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="96d67-286">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="96d67-287">昇格期間が経過すると、Lockbox はアクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="96d67-287">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="96d67-288">Microsoft の一般的な [セキュリティプラクティスの](https://www.microsoft.com/licensing/product-licensing/products) 詳細については、「Online Services Terms」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96d67-288">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="96d67-289">Microsoft のエンジニアは、どのような状況で自分のコンテンツにアクセスする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="96d67-289">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="96d67-290">Microsoft エンジニアが顧客コンテンツにアクセスする必要がある最も一般的なシナリオは、お客様がトラブルシューティングにアクセスする必要があるサポート要求を行う場合です。</span><span class="sxs-lookup"><span data-stu-id="96d67-290">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="96d67-291">Microsoft 365 の基本原則は、サービスが Microsoft が顧客コンテンツにアクセスせずに動作する点です。</span><span class="sxs-lookup"><span data-stu-id="96d67-291">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="96d67-292">Microsoft によって実行されるサービス操作のほぼすべては完全に自動化され、人間の関与は高度に制御され、顧客コンテンツから抽象化されます。</span><span class="sxs-lookup"><span data-stu-id="96d67-292">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="96d67-293">Microsoft 365 の目標は、お客様が Microsoft アクセスの特定の要求を承認するまで、サービスをサポートするために顧客コンテンツにアクセスする必要が無い点です。</span><span class="sxs-lookup"><span data-stu-id="96d67-293">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="96d67-294">Microsoft クラウドでデータが安全だと既に思っていたので、なぜカスタマー ロックボックスが必要なのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="96d67-294">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="96d67-295">顧客ロックボックスは、サービス操作に対して明示的なアクセス許可を与える機能を顧客に提供することで、追加の制御層を提供します。</span><span class="sxs-lookup"><span data-stu-id="96d67-295">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="96d67-296">顧客ロックボックスは、明示的なデータ アクセス承認のための手順が実施されているという実証によって、HIPAA や FEDRAMP などの特定のコンプライアンス義務を満たすのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="96d67-296">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>