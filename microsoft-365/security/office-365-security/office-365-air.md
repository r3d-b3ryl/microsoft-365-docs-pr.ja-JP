---
title: Office 365 の脅威を自動的に調査し対応する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動インシデント対応機能の使用を開始します。
ms.openlocfilehash: 13f7e95829b8cf3adf17a40cf7b02c5322b15ea7
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673423"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="ecbf0-104">Office 365 の脅威を自動的に調査し対応する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="ecbf0-105">概要</span><span class="sxs-lookup"><span data-stu-id="ecbf0-105">Overview</span></span>

<span data-ttu-id="ecbf0-106">サブスクリプションによっては、 [Office 365 Advanced Threat Protection](office-365-atp.md)には、セキュリティ運用チームの時間と、アラートと脅威を処理するための労力を節約できる自動化されたインシデント対応 (航空) 機能が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated incident response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="ecbf0-107">Office 365 の AIR 機能の使用を開始するには、この記事をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-107">To get started using AIR capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="ecbf0-108">空気のしくみの概要については、「Office 2010 の[自動インシデント対応 (AIR) 365](automated-investigation-response-office.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-108">To get an overview of how AIR works, see [Automated incident response (AIR) in Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="ecbf0-109">AIR を使用すると、特定のアラートがトリガーされ、1つ以上のセキュリティプレイブックが開始され、自動調査が開始します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="ecbf0-110">自動化された調査プロセスの最中および実行後に、管理者およびセキュリティ運用チームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="ecbf0-111">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="ecbf0-112">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="ecbf0-113">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="ecbf0-114">この記事で説明されているタスクを実行するには、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-114">You must have appropriate permissions to perform the tasks described in this article.</span></span> <span data-ttu-id="ecbf0-115">たとえば、myst はグローバル管理者、セキュリティ管理者、セキュリティオペレーター、またはセキュリティ閲覧者になります。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-115">For example, you myst be a global administrator, security administrator, security operator, or security reader.</span></span> <span data-ttu-id="ecbf0-116">[Microsoft 365 セキュリティセンターの役割とアクセス許可の詳細について説明](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-116">[Learn more about Microsoft 365 security center roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="ecbf0-117">AIR は次のサブスクリプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-117">AIR is included in the following subscriptions:</span></span>
- <span data-ttu-id="ecbf0-118">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ecbf0-118">Microsoft 365 E5</span></span>
- <span data-ttu-id="ecbf0-119">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="ecbf0-119">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="ecbf0-120">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ecbf0-120">Office 365 E5</span></span>
- <span data-ttu-id="ecbf0-121">Office 365 Advanced Threat Protection プラン 2</span><span class="sxs-lookup"><span data-stu-id="ecbf0-121">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="ecbf0-122">これらのサブスクリプションのいずれかがない場合は、[無料試用版を開始](https://go.microsoft.com/fwlink/p/?LinkID=698279)します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-122">If you don't have one of these subscriptions, [start a free trial](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="ecbf0-123">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-123">View details of an investigation</span></span>

1. <span data-ttu-id="ecbf0-124">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-124">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="ecbf0-125">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-125">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="ecbf0-126">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-126">Do one of the following:</span></span>

    - <span data-ttu-id="ecbf0-127">[**脅威管理** > ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-127">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="ecbf0-128">これにより、[セキュリティダッシュボード](security-dashboard.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-128">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="ecbf0-129">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-129">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="ecbf0-130">**調査の概要**などのウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-130">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="ecbf0-131">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-131">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="ecbf0-132">どちらの方法でも、調査の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-132">Either method takes you to a list of investigations.</span></span>

    ![AIR のメインの調査ページ](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="ecbf0-134">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-134">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="ecbf0-135">これにより、調査の詳細ページが開き、[調査] グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-135">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![ARI の [調査グラフ] ページ](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="ecbf0-137">調査の詳細については、さまざまなタブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-137">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="ecbf0-138">アクションの確認と承認</span><span class="sxs-lookup"><span data-stu-id="ecbf0-138">Review and approve actions</span></span>

<span data-ttu-id="ecbf0-139">Office 365 では、通常、自動調査は1つまたは複数の推奨されるアクションになります。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-139">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="ecbf0-140">ただし、セキュリティ運用チームによって承認されるまで、アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-140">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="ecbf0-141">アクションを確認して承認するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-141">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="ecbf0-142">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-142">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="ecbf0-143">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="ecbf0-144">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-144">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="ecbf0-145">調査の詳細ビューで、[**操作**] タブを選択します。承認待ちのすべてのアクションがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-145">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="ecbf0-146">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-146">Select an item in the list.</span></span>

5. <span data-ttu-id="ecbf0-147">推奨されるアクションを実行する場合は [**承認**] を選択します (アクションを行わずに調査を終了する場合は**拒否**)。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-147">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="ecbf0-148">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-148">View details about an alert related to an investigation</span></span>

<span data-ttu-id="ecbf0-149">特定の種類の通知では、Office 365 で自動調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-149">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="ecbf0-150">詳細については、「 [Alerts](automated-investigation-response-office.md#alerts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-150">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="ecbf0-151">次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-151">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="ecbf0-152">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-152">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="ecbf0-153">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-153">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="ecbf0-154">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-154">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="ecbf0-155">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-155">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="ecbf0-156">調査の詳細を開いた状態で、[**通知**] タブを選択します。調査をトリガーしたアラートが一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-156">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="ecbf0-157">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-157">Select an item in the list.</span></span> <span data-ttu-id="ecbf0-158">ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-158">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="ecbf0-159">ポップアップの情報を確認し、特定の通知に応じて、ユーザーの**解決**、**抑制**、または**通知**などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-159">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="ecbf0-160">**解決**は通知を閉じることと同じです。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-160">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="ecbf0-161">**抑制**すると、指定した期間、ポリシーがアラートをトリガーしなくなります。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-161">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="ecbf0-162">**通知**ユーザーに既に入力されたユーザーのメールアドレスを使用してメールを開始し、セキュリティ運用チームがそれらのユーザーにメッセージを入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-162">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="ecbf0-163">(これは、[脅威エクスプローラー](threat-explorer.md)を使用してメッセージを受信者に送信するのと似ています。)</span><span class="sxs-lookup"><span data-stu-id="ecbf0-163">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="ecbf0-164">カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-164">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="ecbf0-165">組織でカスタムまたはサードパーティのレポートソリューションを使用している場合は、Office 365 Management Activity API を使用して、そのソリューションの自動化された調査に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-165">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="ecbf0-166">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-166">Use the following resources to set this up:</span></span>

|<span data-ttu-id="ecbf0-167">リソース</span><span class="sxs-lookup"><span data-stu-id="ecbf0-167">Resource</span></span>  |<span data-ttu-id="ecbf0-168">説明</span><span class="sxs-lookup"><span data-stu-id="ecbf0-168">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="ecbf0-169">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="ecbf0-169">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="ecbf0-170">Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-170">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="ecbf0-171">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-171">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="ecbf0-172">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-172">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="ecbf0-173">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-173">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="ecbf0-174">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="ecbf0-174">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="ecbf0-175">Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-175">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="ecbf0-176">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-176">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="ecbf0-177">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="ecbf0-177">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="ecbf0-178">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="ecbf0-178">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="ecbf0-179">次の手順</span><span class="sxs-lookup"><span data-stu-id="ecbf0-179">Next steps</span></span>

[<span data-ttu-id="ecbf0-180">通知の詳細情報</span><span class="sxs-lookup"><span data-stu-id="ecbf0-180">Learn more about alerts</span></span>](../../compliance/alert-policies.md)

[<span data-ttu-id="ecbf0-181">Office 365 で配信された悪意のある電子メールを手動で検索して調査する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-181">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="ecbf0-182">Microsoft Defender ATP の AIR についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="ecbf0-182">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="ecbf0-183">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="ecbf0-183">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)