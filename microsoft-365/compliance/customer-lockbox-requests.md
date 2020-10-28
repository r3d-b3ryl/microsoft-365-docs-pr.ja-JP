---
title: 顧客のロックボックス要求
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
description: 問題が発生したときに Microsoft サポートエンジニアがデータにアクセスする方法を制御するための、カスタマーロックボックス要求について説明します。
ms.openlocfilehash: b475c9af80d0e28961360825788d9e19a426dc69
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48768865"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="e7b3c-103">Office 365 のカスタマーロックボックス</span><span class="sxs-lookup"><span data-stu-id="e7b3c-103">Customer Lockbox in Office 365</span></span>

<span data-ttu-id="e7b3c-104">この記事では、お客様のロックボックスの展開と構成に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-104">This article provides deployment and configuration guidance for Customer Lockbox.</span></span> <span data-ttu-id="e7b3c-105">Customer ロックボックスは、Exchange Online、SharePoint Online、OneDrive for business のデータにアクセスするための要求をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-105">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="e7b3c-106">他のサービスのサポートを推奨するには、 [Office 365 UserVoice](https://office365.uservoice.com/)で要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-106">To recommend support for other services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

<span data-ttu-id="e7b3c-107">Microsoft 365 のコンプライアンスの提供 (2020 年4月1日現在) を利用してユーザーにライセンスを付与するためのオプションを確認するには、「 [microsoft 365 ライセンスガイダンス (セキュリティ & 法令遵守](https://aka.ms/ComplianceSD)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-107">To see the options for licensing your users to benefit from Microsoft 365 compliance offerings, including this one, as of April 1, 2020, see the [Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).</span></span>

<span data-ttu-id="e7b3c-108">カスタマーロックボックスを使用すると、明示的な承認なしにサービス操作を実行するために、Microsoft がコンテンツにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-108">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="e7b3c-109">お客様のロックボックスによって、コンテンツにアクセスする要求の承認ワークフローに入ります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-109">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="e7b3c-110">Microsoft のエンジニアは、サポートプロセスでお客様から報告された問題のトラブルシューティングと修正に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-110">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="e7b3c-111">通常、問題は広範なテレメトリおよびデバッグツールによって Microsoft がサービスに適用されています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-111">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="e7b3c-112">ただし、場合によっては、Microsoft のエンジニアにお客様のコンテンツにアクセスして、根本的な原因を特定し、問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-112">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="e7b3c-113">カスタマー ロックボックスでは、承認ワークフローの最終ステップとして、エンジニアが顧客にアクセス要求を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-113">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="e7b3c-114">これにより、組織はこれらの要求を承認または拒否し、顧客への直接アクセスコントロールを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-114">This gives organizations the option to approve or deny these requests, and provide direct-access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="e7b3c-115">顧客ロックボックスの概要ビデオ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-115">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="e7b3c-116">カスタマー ロックボックスのワークフロー</span><span class="sxs-lookup"><span data-stu-id="e7b3c-116">Customer Lockbox workflow</span></span>

<span data-ttu-id="e7b3c-117">次の手順では、Microsoft のエンジニアがカスタマーロックボックス要求を開始するときの一般的なワークフローの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-117">The following steps outline the typical workflow when a Microsoft engineer initiates a Customer Lockbox request:</span></span>

1. <span data-ttu-id="e7b3c-118">組織内の誰かが Microsoft 365 メールボックスで問題を経験している。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-118">Someone at an organization experiences an issue with their Microsoft 365 mailbox.</span></span>

2. <span data-ttu-id="e7b3c-119">ユーザーが問題のトラブルシューティングを行った後、問題を修正できない場合は、Microsoft サポートにサポートリクエストを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-119">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="e7b3c-120">Microsoft サポートエンジニアがサービス要求を確認し、Exchange Online の問題を修復するために組織のテナントにアクセスする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-120">A Microsoft support engineer reviews the service request and determines a need to access the organization's tenant to repair the issue in Exchange Online.</span></span>

4. <span data-ttu-id="e7b3c-121">Microsoft サポートエンジニアは、カスタマーロックボックス要求ツールにログインして、組織のテナント名、サービス要求番号、およびエンジニアリングがデータにアクセスする予想時間を含むデータアクセス要求を行います。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-121">The Microsoft support engineer logs into the Customer Lockbox request tool and makes a data access request that includes the organization's tenant name, service request number, and the estimated time the engineer needs access to the data.</span></span>

5. <span data-ttu-id="e7b3c-122">Microsoft サポート マネージャーが要求を承認した後、カスタマー ロックボックスは、Microsoft からの保留中のアクセス要求に関する電子メール通知を組織内の指定された承認者に送信します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-122">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the organization an email notification about the pending access request from Microsoft.</span></span>

    ![顧客のロックボックス電子メール通知の例](../media/CustomerLockbox1.png)

   <span data-ttu-id="e7b3c-124">Microsoft 365 管理センターで [カスタマーロックボックスアクセス承認](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) 者の役割を割り当てられたすべてのユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-124">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

6. <span data-ttu-id="e7b3c-125">承認者は、Microsoft 365 管理センターにサインインし、要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-125">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="e7b3c-126">この手順では、監査ログの検索によって使用可能な監査レコードの作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-126">This step triggers the creation of an audit record available by searching the audit log.</span></span> <span data-ttu-id="e7b3c-127">詳細については、「 [顧客ロックボックス要求の監査](#auditing-customer-lockbox-requests)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-127">For more information, see [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests).</span></span>

   <span data-ttu-id="e7b3c-128">顧客が要求を拒否した場合、または要求を12時間以内に承認しなかった場合、要求は有効期限が切れ、Microsoft のエンジニアにはアクセス権が付与されません。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-128">If the customer rejects the request or doesn't approve the request within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e7b3c-129">Microsoft では、Office 365 にサインインする必要がある、カスタマーロックボックスの電子メール通知にリンクは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-129">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

7. <span data-ttu-id="e7b3c-130">組織からの承認者が要求を承認した後、Microsoft エンジニアは承認メッセージを受信し、Exchange Online のテナントにログインして、お客様の問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-130">After the approver from the organization approves the request, the Microsoft engineer receives the approval message, logs into the tenant in Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="e7b3c-131">Microsoft のエンジニアは、要求された期間に、アクセスが自動的に取り消される前に問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-131">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="e7b3c-132">Microsoft のエンジニアによって実行されるすべての操作は、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-132">All actions performed by a Microsoft engineer are logged in the audit log.</span></span> <span data-ttu-id="e7b3c-133">これらの監査レコードを検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-133">You can search for and review these audit records.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="e7b3c-134">カスタマーロックボックス要求を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e7b3c-134">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="e7b3c-135">Microsoft 365 管理センターで、カスタマー ロックボックス コントロールを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-135">You can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e7b3c-136">カスタマーロックボックスをオンにすると、テナントのコンテンツにアクセスする前に、Microsoft は組織の承認を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-136">When you turn on Customer Lockbox, Microsoft must obtain your organization's approval before accessing any of your tenant's content.</span></span>

1. <span data-ttu-id="e7b3c-137">グローバル管理者または [ **カスタマーロックボックス] [アクセス承認** ] 役割が割り当てられている職場または学校のアカウントを使用して、に移動 [https://admin.microsoft.com](https://admin.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-137">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="e7b3c-138">[ **組織設定 > 設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-138">Choose **Settings > Org Settings** .</span></span>

3. <span data-ttu-id="e7b3c-139">[ **セキュリティ & プライバシー** ] [  >  **カスタマーロックボックス** の  >  **編集** ] を選択 **On** し、トグルをオンまたは **オフ** にして、機能をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-139">Select **Security & Privacy** > **Customer Lockbox** > **Edit** , and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="e7b3c-141">カスタマー ロックボックス要求を承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="e7b3c-141">Approve or deny a Customer Lockbox request</span></span>

1. <span data-ttu-id="e7b3c-142">グローバル管理者または [ **カスタマーロックボックス] [アクセス承認** ] 役割が割り当てられている職場または学校のアカウントを使用して、に移動 [https://admin.microsoft.com](https://admin.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-142">Using a work or school account that has either the global administrator or the **Customer Lockbox access approver** role assigned, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in.</span></span>

2. <span data-ttu-id="e7b3c-143">[ **Support > Customer のロックボックス要求** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-143">Choose **Support > Customer Lockbox Requests** .</span></span>

    ![[サポート] をクリックし、[カスタマーロックボックス要求] をクリックします。](../media/CustomerLockbox5.png)

    <span data-ttu-id="e7b3c-145">顧客のロックボックス要求の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-145">A list of Customer Lockbox requests displays.</span></span>

    ![顧客ロックボックス要求の一覧](../media/CustomerLockbox6.png)

3. <span data-ttu-id="e7b3c-147">顧客のロックボックス要求を選択し、[ **承認** または **拒否** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-147">Select a Customer Lockbox request, and then choose **Approve** or **Deny** .</span></span>

    ![カスタマーロックボックス要求を承認または拒否する](../media/CustomerLockbox7.png)

    <span data-ttu-id="e7b3c-149">顧客のロックボックス要求の承認に関する確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-149">A confirmation message about the approval of the Customer Lockbox request displays.</span></span>

    ![カスタマーロックボックス要求を承認または拒否する](../media/CustomerLockbox8.png)

> [!NOTE]
> <span data-ttu-id="e7b3c-151">Set-AccessToCustomerDataRequest コマンドレットを使用して、Microsoft のサポート エンジニアがデータへのアクセスを制限する Microsoft 365 カスタマー ロックボックス要求を承認、拒否、キャンセルします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-151">Use the Set-AccessToCustomerDataRequest cmdlet to approve, deny, or cancel Microsoft 365 customer lockbox requests that control access to your data by Microsoft support engineers.</span></span> <span data-ttu-id="e7b3c-152">詳細については、「 [AccessToCustomerDataRequest](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-152">For more information, see [Set-AccessToCustomerDataRequest](https://docs.microsoft.com/powershell/module/exchange/set-accesstocustomerdatarequest).</span></span>


## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="e7b3c-153">カスタマー ロックボックス要求を監査する</span><span class="sxs-lookup"><span data-stu-id="e7b3c-153">Auditing Customer Lockbox requests</span></span>

<span data-ttu-id="e7b3c-154">顧客のロックボックス要求に対応する監査レコードは、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-154">Audit records that correspond to the Customer Lockbox requests are logged in the audit log.</span></span> <span data-ttu-id="e7b3c-155">これらのログには、セキュリティ & コンプライアンスセンターの [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md) を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-155">You can access these logs by using the [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="e7b3c-156">カスタマーロックボックス要求の承諾または拒否に関連する操作 (アクセス要求が承認された場合) は、監査ログにも記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-156">Actions related to accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are also logged in the audit log.</span></span> <span data-ttu-id="e7b3c-157">これらの監査レコードを検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-157">You can search for and review these audit records.</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="e7b3c-158">カスタマーロックボックス要求に関連するアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="e7b3c-158">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="e7b3c-159">監査ログを使用してカスタマー ロックボックスの要求を追跡できるようにするには、監査ログを設定するためにいくつかの手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-159">Before you can use the audit log to track requests for Customer Lockbox, there are some steps you need to take to set up audit logging.</span></span> <span data-ttu-id="e7b3c-160">詳細については、「 [セキュリティ & のコンプライアンスセンターでの監査ログの検索](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-160">For more information, see [Search the audit log in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span> <span data-ttu-id="e7b3c-161">セットアップが完了したら、次の手順を使用して監査ログ検索クエリを作成し、顧客ロックボックスに関連する監査レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-161">Once you've completed setup, use these steps to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="e7b3c-162">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="e7b3c-163">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-163">Sign in using your work or school account.</span></span>

3. <span data-ttu-id="e7b3c-164">[セキュリティ & コンプライアンスセンター] の左側のウィンドウで、[ **検索 & 調査**  >  **監査ログの検索** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-164">In the left pane of the Security & Compliance Center, choose **Search & investigation** > **Audit log search** .</span></span>

    <span data-ttu-id="e7b3c-165">[ **監査ログの検索** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-165">The **Audit log search** page displays.</span></span>

    ![監査ログの検索ページ](../media/auditlogsearch1.png)
  
4. <span data-ttu-id="e7b3c-167">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-167">Configure the following search criteria:</span></span>

    1. <span data-ttu-id="e7b3c-168">**アクティビティ** -検索ですべてのアクティビティの監査レコードが返されるようにするには、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="e7b3c-169">これは、カスタマーロックボックス要求と、Microsoft のエンジニアによって実行される対応するアクティビティに関連する監査レコードを返すために必要です。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    1. <span data-ttu-id="e7b3c-170">**開始** 日と **終了日** -その期間内に発生したイベントを表示する日付と時刻の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-170">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    1. <span data-ttu-id="e7b3c-171">**ユーザー** -このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-171">**Users** - Leave this field blank.</span></span>

    1. <span data-ttu-id="e7b3c-172">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-172">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="e7b3c-173">[ **検索** ] をクリックして、設定した検索条件で検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-173">Click **Search** to run the search using your search criteria.</span></span>

    <span data-ttu-id="e7b3c-174">検索結果が読み込まれ、しばらくすると、[ **監査ログの検索** ] ページの [ **結果** ] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-174">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="e7b3c-175">[検索結果] ページで [ **結果のフィルター処理** ] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-175">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="e7b3c-176">組織内の承認者に関連する監査レコードを表示するには、顧客のロックボックス要求を承認または拒否します。 [ **アクティビティ** ] 列の下のボックスに「 **AccessToCustomerDataRequest** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-176">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest** .</span></span>

   - <span data-ttu-id="e7b3c-177">Microsoft のエンジニアに関連する監査レコードを表示するには、承認された顧客ロックボックス要求に対する処理を実行します。 [ **ユーザー** ] 列の下のボックスに、「 **Microsoft Operator** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-177">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator** .</span></span> <span data-ttu-id="e7b3c-178">[ **Activity** ] 列には、エンジニアが実行したアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-178">The **Activity** column displays the action performed by the engineer.</span></span>

      ![監査レコードを表示するには、"Microsoft Operator" のフィルターを適用します。](../media/CustomerLockbox10.png)

7. <span data-ttu-id="e7b3c-180">結果の一覧で、監査レコードをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-180">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="e7b3c-181">カスタマー ロックボックス アクセス要求の監査レコード</span><span class="sxs-lookup"><span data-stu-id="e7b3c-181">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="e7b3c-182">組織内のユーザーがカスタマーロックボックス要求を承認または拒否すると、監査ログが監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-182">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the audit log.</span></span> <span data-ttu-id="e7b3c-183">このレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-183">This record contains the following information.</span></span>

| <span data-ttu-id="e7b3c-184">監査レコードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-184">Audit record property</span></span>| <span data-ttu-id="e7b3c-185">説明</span><span class="sxs-lookup"><span data-stu-id="e7b3c-185">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="e7b3c-186">日付</span><span class="sxs-lookup"><span data-stu-id="e7b3c-186">Date</span></span>       | <span data-ttu-id="e7b3c-187">カスタマー ロックボックス要求が承認または拒否された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-187">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="e7b3c-188">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e7b3c-188">IP address</span></span> | <span data-ttu-id="e7b3c-189">要求を承認または拒否するために使用された承認者のコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-189">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="e7b3c-190">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e7b3c-190">User</span></span>       | <span data-ttu-id="e7b3c-191">Prod.outlook.com のサービスアカウント BOXServiceAccount@ \[ \] 。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-191">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="e7b3c-192">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-192">Activity</span></span>   | <span data-ttu-id="e7b3c-193">Set-AccessToCustomerDataRequest: これは、カスタマー ロックボックス要求を承認または拒否したときにログに記録される監査アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-193">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="e7b3c-194">アイテム</span><span class="sxs-lookup"><span data-stu-id="e7b3c-194">Item</span></span>       | <span data-ttu-id="e7b3c-195">顧客のロックボックス要求の Guid</span><span class="sxs-lookup"><span data-stu-id="e7b3c-195">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="e7b3c-196">次のスクリーンショットは、承認された顧客ロックボックス要求に対応する監査ログレコードの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-196">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="e7b3c-197">顧客のロックボックス要求が拒否された場合、 **Approvaldecision** パラメーターの値は **Deny** になります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-197">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny** .</span></span>

![承認された顧客ロックボックス要求の監査レコード](../media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="e7b3c-199">監査レコードに詳細情報を表示するには、[ **詳細情報** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-199">To display more detailed information in an audit record, click **More information** .</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="e7b3c-200">Microsoft のエンジニアによって実行されたアクションの監査レコード</span><span class="sxs-lookup"><span data-stu-id="e7b3c-200">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="e7b3c-201">カスタマー ロックボックス要求が承認された後 Microsoft のエンジニアが実行するアクション (顧客コンテンツへのアクセスにつながる可能性があります) は、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-201">The actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="e7b3c-202">これらのレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-202">These records contain the following information.</span></span>

| <span data-ttu-id="e7b3c-203">監査レコードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-203">Audit record property</span></span>| <span data-ttu-id="e7b3c-204">説明</span><span class="sxs-lookup"><span data-stu-id="e7b3c-204">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="e7b3c-205">日付</span><span class="sxs-lookup"><span data-stu-id="e7b3c-205">Date</span></span>       | <span data-ttu-id="e7b3c-206">アクションが実行された日時。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-206">Date time when the action was performed.</span></span> <span data-ttu-id="e7b3c-207">このアクションが実行された時刻は、カスタマー ロックボックス要求が承認されてから 4 時間以内であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-207">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="e7b3c-208">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="e7b3c-208">IP address</span></span> | <span data-ttu-id="e7b3c-209">Microsoft のエンジニア使用したコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-209">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="e7b3c-210">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e7b3c-210">User</span></span>       | <span data-ttu-id="e7b3c-211">Microsoft のオペレーター。この値は、このレコードがカスタマー ロックボックス要求に関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-211">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="e7b3c-212">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-212">Activity</span></span>   | <span data-ttu-id="e7b3c-213">Microsoft のエンジニアが実行したアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-213">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="e7b3c-214">項目</span><span class="sxs-lookup"><span data-stu-id="e7b3c-214">Item</span></span>       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a><span data-ttu-id="e7b3c-215">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e7b3c-215">Frequently asked questions</span></span>

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="e7b3c-216">どの Microsoft 365 サービスが顧客ロックボックスに適用されますか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-216">Which Microsoft 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="e7b3c-217">お客様のロックボックスは現在、Exchange Online、SharePoint Online、OneDrive for business でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-217">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-customers"></a><span data-ttu-id="e7b3c-218">お客様のロックボックスはすべてのお客様が利用できますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-218">Is Customer Lockbox available to all customers?</span></span>

<span data-ttu-id="e7b3c-219">カスタマーロックボックスは、Microsoft 365 または Office 365 E5 サブスクリプションに含まれており、情報の保護とコンプライアンス、または高度なコンプライアンスアドオンサブスクリプションを使用して他のプランに追加できます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-219">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="e7b3c-220">詳細については [、「プランと価格](https://products.office.com/business/office-365-enterprise-e5-business-software) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-220">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="e7b3c-221">顧客コンテンツとは</span><span class="sxs-lookup"><span data-stu-id="e7b3c-221">What is customer content?</span></span>

<span data-ttu-id="e7b3c-222">顧客コンテンツは、Microsoft 365 のサービスとアプリケーションのユーザーによって作成されたデータです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-222">Customer content is the data created by users of Microsoft 365 services and applications.</span></span> <span data-ttu-id="e7b3c-223">顧客コンテンツの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-223">Examples of customer content include:</span></span>

- <span data-ttu-id="e7b3c-224">電子メール本文またはメールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="e7b3c-224">Email body or email attachments</span></span>

- <span data-ttu-id="e7b3c-225">SharePoint サイトのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="e7b3c-225">SharePoint site contents</span></span>

- <span data-ttu-id="e7b3c-226">SharePoint ファイルの本文に含まれる情報</span><span class="sxs-lookup"><span data-stu-id="e7b3c-226">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="e7b3c-227">Skype for Business プレゼンテーションファイルの本文</span><span class="sxs-lookup"><span data-stu-id="e7b3c-227">Skype for Business presentation file body</span></span>

- <span data-ttu-id="e7b3c-228">インスタント メッセージ (IM) または音声会話</span><span class="sxs-lookup"><span data-stu-id="e7b3c-228">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="e7b3c-229">顧客が生成した blob または構造化ストレージ データ (SQL コンテナーなど)</span><span class="sxs-lookup"><span data-stu-id="e7b3c-229">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="e7b3c-230">顧客が所有するセキュリティ情報 (証明書、暗号化キー、パスワードなど)</span><span class="sxs-lookup"><span data-stu-id="e7b3c-230">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="e7b3c-231">お客様のコンテンツが残っている場合の推論、以降のすべての推論</span><span class="sxs-lookup"><span data-stu-id="e7b3c-231">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="e7b3c-232">Office 365 の顧客コンテンツの詳細については、「 [office 365 のセキュリティセンター](https://products.office.com/business/office-365-trust-center-privacy/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-232">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="e7b3c-233">自分のコンテンツへのアクセスを要求された場合、だれに通知されますか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-233">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="e7b3c-234">グローバル管理者と、カスタマーロックボックスアクセス許可管理者役割に割り当てられているユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-234">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="e7b3c-235">これらのユーザーは、顧客のロックボックス要求の承認を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-235">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="e7b3c-236">組織内でこれらの要求を承認または拒否できるユーザー</span><span class="sxs-lookup"><span data-stu-id="e7b3c-236">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="e7b3c-237">グローバル管理者と顧客ロックボックスアクセス許可管理者ロールに割り当てられたユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-237">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="e7b3c-238">お客様は、組織内でこれらの役割の割り当てを制御します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-238">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="e7b3c-239">お客様のロックボックスにどのように選択しますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-239">How do I opt in to Customer Lockbox?</span></span>

<span data-ttu-id="e7b3c-240">グローバル管理者は、Microsoft 365 または Microsoft 365 管理センターでカスタマーロックボックスを有効にして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-240">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="e7b3c-241">カスタマーロックボックス要求を承認した場合、エンジニアは何をすることができますか。また、Microsoft のエンジニアが何をしたかを知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-241">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="e7b3c-242">カスタマーロックボックス要求を承認した後、Microsoft のエンジニアは、事前承認済みコマンドレットを使用して、お客様のコンテンツにアクセスするためにこれらの必要な権限を付与しました。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-242">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="e7b3c-243">カスタマーロックボックス要求に対応して Microsoft のエンジニアが実行するアクションは、セキュリティ & コンプライアンスセンターの監査ログでログに記録され、アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-243">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="e7b3c-244">Microsoft が承認プロセスに従うことをどのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-244">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="e7b3c-245">組織内の管理者および承認者に送信される電子メールの承認通知は、Microsoft 365 管理センターのカスタマーロックボックス要求の履歴と相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-245">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e7b3c-246">お客様のロックボックスは、最新の [SOC 1 SSAE 16 監査レポート](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-246">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="e7b3c-247">詳細については、 [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)の最新レポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-247">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="e7b3c-248">Microsoft は、自分のテナントの承認者の一覧を変更できますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-248">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="e7b3c-249">そうでない場合は、どのような方法で回避できますか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-249">If not, how is it prevented?</span></span>

<span data-ttu-id="e7b3c-250">顧客のロックボックス要求を承認できるユーザーを指定できるのは、組織内のグローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-250">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="e7b3c-251">これは、Azure Active Directory の全体管理者グループのメンバーのみが、要求を承認できるユーザーを指定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-251">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="e7b3c-252">Azure Active Directory の全体管理者グループのメンバーシップは、組織によってのみ管理されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-252">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="e7b3c-253">承認のためにコンテンツアクセス要求に関する詳細情報が必要な場合は、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-253">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="e7b3c-254">各顧客ロックボックス要求には、Microsoft 365 サービス要求番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-254">Each Customer Lockbox request contains a Microsoft 365 service request number.</span></span> <span data-ttu-id="e7b3c-255">要求に関する詳細情報を取得するには、Microsoft サポートに連絡して、このサービス番号を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-255">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="e7b3c-256">顧客のロックボックス要求が承認されると、アクセス許可はどのくらいの期間有効になりますか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-256">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="e7b3c-257">現在、Microsoft のエンジニアに付与されるアクセス許可の最長期間は 4 時間です。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-257">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="e7b3c-258">Microsoft のエンジニアは、より短い期間を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-258">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="e7b3c-259">すべてのカスタマーロックボックス要求の履歴を取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-259">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="e7b3c-260">すべてのカスタマーロックボックス要求は、Microsoft 365 管理センターで表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-260">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="e7b3c-261">コンテンツアクセス要求を関連する監査ログと関連付けるにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-261">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="e7b3c-262">コンプライアンスセンターのアクティビティフィードには、顧客ロックボックスのログアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-262">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="e7b3c-263">顧客は、受信した電子メール要求に対して、顧客のロックボックスログアクティビティをアクティビティフィードから相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-263">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="e7b3c-264">お客様がお客様のロックボックス要求に応答しない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-264">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="e7b3c-265">カスタマー ロックボックス要求の既定の期間は 12 時間です。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-265">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="e7b3c-266">12時間以内に要求に応答しない場合、要求は有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-266">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="e7b3c-267">顧客が顧客のロックボックス要求を拒否した場合、Microsoft は何を行いますか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-267">What does Microsoft do when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="e7b3c-268">顧客が顧客のロックボックス要求を拒否した場合、顧客コンテンツへのアクセスは行われません。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-268">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="e7b3c-269">この問題を解決するために Microsoft がお客様のコンテンツにアクセスする必要があるというサービスの問題が組織内のユーザーから引き続き発生する場合、サービスの問題が持続する可能性があり、Microsoft はそのことをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-269">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="e7b3c-270">カスタマーロックボックスは、法律執行機関または他のサードパーティからのデータ要求に対して保護されるものですか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-270">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="e7b3c-271">いいえ。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-271">No.</span></span> <span data-ttu-id="e7b3c-272">Microsoft は、お客様のデータに関するサードパーティの要求を真剣に引き受けます。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-272">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="e7b3c-273">クラウドサービスプロバイダーとして、Microsoft はお客様のデータのプライバシーを常に重視しています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-273">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="e7b3c-274">召喚を受け取った場合、Microsoft は常にお客様に情報を取得するためにサードパーティのリダイレクトを試行します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-274">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="e7b3c-275">(行政スミスのブログ: [政府からのお客様データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-275">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="e7b3c-276">Microsoft が受け取る法的執行機関の要求に関する [詳細情報](https://www.microsoft.com/corporate-responsibility/lerr) を定期的に公開しています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-276">We periodically publish [detailed information](https://www.microsoft.com/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="e7b3c-277">詳細については、「[オンラインサービス用語](https://www.microsoft.com/Licensing/product-licensing/products.aspx)」の「サードパーティのデータ要求に関する[Microsoft セキュリティセンター](https://www.microsoft.com/trustcenter/default.aspx) 」と「顧客データの開示」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-277">See the [Microsoft Trust Center](https://www.microsoft.com/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="e7b3c-278">Microsoft では、Office 365 アプリケーションの顧客コンテンツへの継続的なアクセス権を、スタッフのメンバーが持っているかどうかを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-278">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="e7b3c-279">Microsoft は、アクセス制御システムを使用して広範な予防措置を実装しており、これらのアクセス制御システムを回避する試みを識別して対処するための検出対策を行います。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-279">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="e7b3c-280">Microsoft 365 は、最小限の特権とジャストインタイムアクセスの原則を使用して操作します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-280">Microsoft 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="e7b3c-281">そのため、Microsoft の担当者は、継続的にお客様のコンテンツにアクセスするためのアクセス許可を持っていません。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-281">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="e7b3c-282">アクセス許可が付与されている場合は、期間に制限があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-282">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="e7b3c-283">Microsoft 365 は、 *ロックボックス* と呼ばれるアクセス制御システムを使用して、サービス内で運用および管理機能を実行する機能を付与するアクセス許可に対する要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-283">Microsoft 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="e7b3c-284">オペレーターは、ロックボックスを使用してユーザーのコンテンツへのアクセスを要求する必要があります。その後、アクセス許可が付与される前に、要求に対してアクションを実行する (たとえば、承認する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-284">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="e7b3c-285">この2番目のユーザーはリクエスターになることができず、顧客コンテンツへのアクセスを承認するように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-285">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="e7b3c-286">要求が承認された場合にのみ、オペレーターは顧客コンテンツへの一時的なアクセス権を取得します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-286">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="e7b3c-287">昇格期間が過ぎると、ロックボックスはアクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-287">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="e7b3c-288">Microsoft の一般的なセキュリティ対策の詳細については、 [オンラインサービス](https://www.microsoft.com/licensing/product-licensing/products) の使用条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-288">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="e7b3c-289">Microsoft のエンジニアがコンテンツにアクセスする必要があるのはどのような状況ですか。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-289">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="e7b3c-290">Microsoft のエンジニアがお客様のコンテンツへのアクセスを必要とする最も一般的なシナリオは、お客様がトラブルシューティングのためのアクセス権を必要とするサポート要求を行った場合です。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-290">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="e7b3c-291">Microsoft 365 の基本原則は、Microsoft がお客様のコンテンツにアクセスしなくてもサービスを運用できることです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-291">A foundational principle of Microsoft 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="e7b3c-292">Microsoft によって実行されるほとんどすべてのサービス操作は完全に自動化されており、人的関与はユーザーのコンテンツによって高度に制御および抽象化されています。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-292">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="e7b3c-293">Microsoft 365 の目標は、お客様が Microsoft access の特定の要求を承認するまで、サービスをサポートするためにお客様のコンテンツにアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-293">The goal for Microsoft 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="e7b3c-294">Microsoft クラウドでデータをセキュリティで保護したことが既に考えられていますが、なぜお客様のロックボックスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="e7b3c-294">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="e7b3c-295">カスタマーロックボックスは、サービス操作の明示的なアクセス承認を提供する機能をお客様に提供することによって、特別な制御層を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-295">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="e7b3c-296">明示的なデータアクセス承認のためにプロシージャが配置されていることを示すことにより、お客様のロックボックスは、顧客が HIPAA、FEDRAMP などの特定のコンプライアンス義務を満たすのを支援します。</span><span class="sxs-lookup"><span data-stu-id="e7b3c-296">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
