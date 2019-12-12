---
title: Office 365 の脅威を自動的に調査し対応する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.openlocfilehash: 3f13b1de2747dcb6672f56989ff73cdf485e49b6
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967990"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="bdb06-104">Office 365 の脅威を自動的に調査し対応する</span><span class="sxs-lookup"><span data-stu-id="bdb06-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="bdb06-105">概要</span><span class="sxs-lookup"><span data-stu-id="bdb06-105">Overview</span></span>

<span data-ttu-id="bdb06-106">サブスクリプションに応じて、 [Office 365 Advanced Threat Protection](office-365-atp.md)には、セキュリティ運用チームの時間と、アラートと脅威を処理するための労力を節約できる自動化された調査と応答 (航空) 機能が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="bdb06-106">Depending on your subscription, [Office 365 Advanced Threat Protection](office-365-atp.md) can include automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span>

- <span data-ttu-id="bdb06-107">Office 365 の自動調査および応答機能を使用するには、この記事をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-107">To get started using automated investigation and response capabilities in Office 365, use this article.</span></span> 
- <span data-ttu-id="bdb06-108">機能の概要については、「 [365 Office 2010 での自動調査と応答](automated-investigation-response-office.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-108">To get an overview of how it works, see [Automated investigation and response in Office 365](automated-investigation-response-office.md).</span></span>

> [!TIP]
> <span data-ttu-id="bdb06-109">Microsoft 365 E5 または Microsoft 365 E3 と Id & 脅威保護を組み合わせて使用していますか?</span><span class="sxs-lookup"><span data-stu-id="bdb06-109">Do you have Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection?</span></span> <span data-ttu-id="bdb06-110">[Microsoft の脅威保護で自動調査と応答 (AIR)](../mtp/mtp-autoir.md)を試行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-110">Consider trying [Automated investigation and response (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md).</span></span>

<span data-ttu-id="bdb06-111">自動調査と応答機能を使用すると、特定のアラートがトリガーされると、1つ以上のセキュリティプレイブックが開始され、自動調査プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-111">With automated investigation and response capabilities, when certain alerts are triggered, one or more security playbooks initiate, and the automated investigation process begins.</span></span> <span data-ttu-id="bdb06-112">自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-112">During and after an automated investigation process, your security team can do the following:</span></span>

- [<span data-ttu-id="bdb06-113">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="bdb06-113">View the details of an investigation</span></span>](#view-details-of-an-investigation)
- [<span data-ttu-id="bdb06-114">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="bdb06-114">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 
- [<span data-ttu-id="bdb06-115">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="bdb06-115">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!IMPORTANT]
> <span data-ttu-id="bdb06-116">この記事で説明されているタスクを実行するには、適切なアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdb06-116">To perform the tasks described in this article, you must have appropriate permissions assigned.</span></span> <span data-ttu-id="bdb06-117">[AIR 機能を使用するには、必要なアクセス許可を](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-117">See [required permissions to use AIR capabilities](automated-investigation-response-office.md#required-permissions-to-use-air-capabilities).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="bdb06-118">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="bdb06-118">View details of an investigation</span></span>

1. <span data-ttu-id="bdb06-119">に[https://protection.office.com](https://protection.office.com)移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="bdb06-119">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="bdb06-120">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-120">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="bdb06-121">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bdb06-121">Do one of the following:</span></span>

    - <span data-ttu-id="bdb06-122">[**脅威管理** > ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-122">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="bdb06-123">これにより、[セキュリティダッシュボード](security-dashboard.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-123">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="bdb06-124">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-124">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="bdb06-125">**調査の概要**などのウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-125">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="bdb06-126">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-126">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="bdb06-127">どちらの方法でも、調査の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-127">Either method takes you to a list of investigations.</span></span>

    ![AIR のメインの調査ページ](../media/air-maininvestigationpage.png) 

3. <span data-ttu-id="bdb06-129">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-129">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="bdb06-130">これにより、調査の詳細ページが開き、[調査] グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-130">This opens investigation details page, starting with the investigation graph in view.</span></span>

    ![ARI の [調査グラフ] ページ](../media/air-investigationgraphpage.png)

4. <span data-ttu-id="bdb06-132">調査の詳細については、さまざまなタブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-132">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="bdb06-133">アクションの確認と承認</span><span class="sxs-lookup"><span data-stu-id="bdb06-133">Review and approve actions</span></span>

<span data-ttu-id="bdb06-134">Office 365 では、通常、自動調査は1つまたは複数の推奨されるアクションになります。</span><span class="sxs-lookup"><span data-stu-id="bdb06-134">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="bdb06-135">ただし、セキュリティ運用チームによって承認されるまで、アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="bdb06-135">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="bdb06-136">アクションを確認して承認するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-136">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="bdb06-137">に[https://protection.office.com](https://protection.office.com)移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="bdb06-137">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="bdb06-138">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-138">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="bdb06-139">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-139">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="bdb06-140">調査の詳細ビューで、[**操作**] タブを選択します。承認待ちのすべてのアクションがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-140">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="bdb06-141">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-141">Select an item in the list.</span></span>

5. <span data-ttu-id="bdb06-142">推奨されるアクションを実行する場合は [**承認**] を選択します (アクションを行わずに調査を終了する場合は**拒否**)。</span><span class="sxs-lookup"><span data-stu-id="bdb06-142">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="bdb06-143">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="bdb06-143">View details about an alert related to an investigation</span></span>

<span data-ttu-id="bdb06-144">特定の種類の通知では、Office 365 で自動調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-144">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="bdb06-145">詳細については、「 [Alerts](automated-investigation-response-office.md#alerts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-145">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="bdb06-146">次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-146">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="bdb06-147">に[https://protection.office.com](https://protection.office.com)移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="bdb06-147">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="bdb06-148">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-148">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="bdb06-149">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-149">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="bdb06-150">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-150">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="bdb06-151">調査の詳細を開いた状態で、[**通知**] タブを選択します。調査をトリガーしたアラートが一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="bdb06-151">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="bdb06-152">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-152">Select an item in the list.</span></span> <span data-ttu-id="bdb06-153">ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-153">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="bdb06-154">ポップアップの情報を確認し、特定の通知に応じて、ユーザーの**解決**、**抑制**、または**通知**などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-154">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="bdb06-155">**解決**は通知を閉じることと同じです。</span><span class="sxs-lookup"><span data-stu-id="bdb06-155">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="bdb06-156">**抑制**すると、指定した期間、ポリシーがアラートをトリガーしなくなります。</span><span class="sxs-lookup"><span data-stu-id="bdb06-156">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="bdb06-157">**通知**ユーザーに既に入力されたユーザーのメールアドレスを使用してメールを開始し、セキュリティ運用チームがそれらのユーザーにメッセージを入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bdb06-157">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="bdb06-158">(これは、[脅威エクスプローラー](threat-explorer.md)を使用してメッセージを受信者に送信するのと似ています。)</span><span class="sxs-lookup"><span data-stu-id="bdb06-158">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="bdb06-159">カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する</span><span class="sxs-lookup"><span data-stu-id="bdb06-159">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="bdb06-160">組織でカスタムまたはサードパーティのレポートソリューションを使用している場合は、Office 365 Management Activity API を使用して、そのソリューションの自動化された調査に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-160">If your organization is using a custom or third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="bdb06-161">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-161">Use the following resources to set this up:</span></span>

|<span data-ttu-id="bdb06-162">Resource</span><span class="sxs-lookup"><span data-stu-id="bdb06-162">Resource</span></span>  |<span data-ttu-id="bdb06-163">説明</span><span class="sxs-lookup"><span data-stu-id="bdb06-163">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="bdb06-164">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="bdb06-164">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="bdb06-165">Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-165">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="bdb06-166">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="bdb06-166">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="bdb06-167">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-167">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="bdb06-168">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bdb06-168">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="bdb06-169">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="bdb06-169">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="bdb06-170">Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="bdb06-170">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="bdb06-171">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdb06-171">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="bdb06-172">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="bdb06-172">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="bdb06-173">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="bdb06-173">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="bdb06-174">次の手順</span><span class="sxs-lookup"><span data-stu-id="bdb06-174">Next steps</span></span>

- [<span data-ttu-id="bdb06-175">空気を取得し、必要なアクセス許可を確認する方法を確認する</span><span class="sxs-lookup"><span data-stu-id="bdb06-175">Find out how to get AIR and see required permissions</span></span>](automated-investigation-response-office.md#how-to-get-air)
- [<span data-ttu-id="bdb06-176">通知の詳細情報</span><span class="sxs-lookup"><span data-stu-id="bdb06-176">Learn more about alerts</span></span>](../../compliance/alert-policies.md)
- [<span data-ttu-id="bdb06-177">Office 365 で配信された悪意のある電子メールを手動で検索して調査する</span><span class="sxs-lookup"><span data-stu-id="bdb06-177">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="bdb06-178">Microsoft Defender ATP の AIR についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="bdb06-178">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="bdb06-179">Microsoft 365 ロードマップにアクセスして、近日公開予定の機能を確認する</span><span class="sxs-lookup"><span data-stu-id="bdb06-179">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)