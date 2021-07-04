---
title: Microsoft 365 監査ソリューション
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365 組織内のユーザーや管理者のアクティビティを監査する方法をご紹介します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4a753a640b98125bc6ad02bd6043f28336e29b7
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256761"
---
# <a name="auditing-solutions-in-microsoft-365"></a><span data-ttu-id="e71c8-103">Microsoft 365 での監査ソリューション</span><span class="sxs-lookup"><span data-stu-id="e71c8-103">Auditing solutions in Microsoft 365</span></span>

<span data-ttu-id="e71c8-104">Microsoft 365 監査ソリューションは、セキュリティ イベント、フォレンジック調査、内部調査、コンプライアンス義務に組織が効果的に対応するための統合ソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-104">Microsoft 365 auditing solutions provide an integrated solution to help organizations effectively respond to security events, forensic investigations, internal investigations, and compliance obligations.</span></span> <span data-ttu-id="e71c8-105">何十もの Microsoft 365 サービスやソリューションで実行された何千ものユーザーや管理者の操作は、組織の統一された監査ログにキャプチャされ、記録されて保持されます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-105">Thousands of user and admin operations performed in dozens of Microsoft 365 services and solutions are captured, recorded, and retained in your organization's unified audit log.</span></span> <span data-ttu-id="e71c8-106">これらのイベントの監査記録は、組織内のセキュリティ オペレーション、IT 管理者、インサイダー リスク チーム、コンプライアンスや法務調査担当者が検索できます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-106">Audit records for these events are searchable by security ops, IT admins, insider risk teams, and compliance and legal investigators in your organization.</span></span> <span data-ttu-id="e71c8-107">この機能により、Microsoft 365 の組織全体で行われているアクティビティを可視化することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-107">This capability provides visibility into the activities performed across your Microsoft 365 organization.</span></span>

## <a name="microsoft-365-auditing-solutions"></a><span data-ttu-id="e71c8-108">Microsoft 365 監査ソリューション</span><span class="sxs-lookup"><span data-stu-id="e71c8-108">Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="e71c8-109">Microsoft 365 には、基本的な監査と高度な監査の 2 つの監査ソリューションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-109">Microsoft 365 provides two auditing solutions: Basic Audit and Advanced Audit.</span></span>

![基本的な監査と高度な監査の主な機能](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a><span data-ttu-id="e71c8-111">基本的な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-111">Basic Audit</span></span>

<span data-ttu-id="e71c8-112">基本的な監査では、監査されたアクティビティのログや検索を行い、フォレンジック調査、IT 調査、コンプライアンス調査、法務調査などに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-112">Basic Audit provides with you with the ability to log and search for audited activities and power your forensic, IT, compliance, and legal investigations.</span></span>

- <span data-ttu-id="e71c8-113">**既定で有効**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-113">**Enabled by default**.</span></span> <span data-ttu-id="e71c8-114">基本的な監査は、適切なサブスクリプションを持つすべての組織で既定でオンになります。</span><span class="sxs-lookup"><span data-stu-id="e71c8-114">Basic Audit is turned on by default for all organizations with the appropriate subscription.</span></span> <span data-ttu-id="e71c8-115">つまり、監査されたアクティビティの記録がキャプチャされ、検索可能になるということです。</span><span class="sxs-lookup"><span data-stu-id="e71c8-115">That means records for audited activities will be captured and searchable.</span></span> <span data-ttu-id="e71c8-116">必要な設定は、監査ログ検索ツール (および対応するコマンドレット) にアクセスするために必要なアクセス許可を割り当て、ユーザーに [高度な監査] 機能の正しいライセンスが割り当てられていることを確認することだけです。</span><span class="sxs-lookup"><span data-stu-id="e71c8-116">The only setup that required is to assign the necessary permissions to access the audit log search tool (and the corresponding cmdlet) and make sure that user's are assigned the right license for Advanced Audit features.</span></span>
- <span data-ttu-id="e71c8-117">**検索可能な数千件の監査イベント**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-117">**Thousands of searchable audit events**.</span></span> <span data-ttu-id="e71c8-118">組織内のほとんどの Microsoft 365 のサービスで発生する、幅広く監査されるアクティビティを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-118">You can search for a wide-range of audited activities that occur is most of the Microsoft 365 services in your organization.</span></span> <span data-ttu-id="e71c8-119">検索可能なアクティビティの一部のリストについては、「[監査されるアクティビティ](search-the-audit-log-in-security-and-compliance.md#audited-activities)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-119">For a partial list of the activities you can search for, see [Audited activities](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span> <span data-ttu-id="e71c8-120">監査活動をサポートするサービスや機能のリストについては、「[監査ログ記録タイプ](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-120">For a list of the services and features that support audited activities, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span>
- <span data-ttu-id="e71c8-121">**Microsoft 365 コンプライアンス センターの監査ログ検索ツール**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-121">**Audit search tool in the Microsoft 365 compliance center**.</span></span> <span data-ttu-id="e71c8-122">Microsoft 365 コンプライアンス センターで監査ログ検索ツールを使用して監査記録を検索します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-122">Use the Audit log search tool in the Microsoft 365 compliance center to search for audit records.</span></span> <span data-ttu-id="e71c8-123">特定のアクティビティ、特定のユーザーが行ったアクティビティ、日付の範囲内で発生したアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-123">You can search for specific activities, for activities performed by specific users, and activities that occurred with a date range.</span></span> <span data-ttu-id="e71c8-124">こちらは、コンプライアンス センターの監査検索ツールのスクリーンショットです。</span><span class="sxs-lookup"><span data-stu-id="e71c8-124">Here's a screenshot of the Audit search tool in the compliance center.</span></span>

   ![Microsoft 365 コンプライアンス センターの監査ログ検索ツール](../media/AuditLogSearchToolMCC.png)

- <span data-ttu-id="e71c8-126">**Search-UnifiedAuditLog コマンドレット**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-126">**Search-UnifiedAuditLog cmdlet**.</span></span> <span data-ttu-id="e71c8-127">Exchange Online PowerShell の **Search-UnifiedAuditLog** コマンドレット (検索ツールの基礎となるコマンドレット) を使用して、監査イベントを検索したり、スクリプトで使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-127">You can also use the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell (the underlying cmdlet for the search tool) to search for audit events or to use in a script.</span></span> <span data-ttu-id="e71c8-128">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-128">For more information, see:</span></span>

  - [<span data-ttu-id="e71c8-129">Search-UnifiedAuditLog コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="e71c8-129">Search-UnifiedAuditLog cmdlet reference</span></span>](/powershell/module/exchange/search-unifiedauditlog)
  - [<span data-ttu-id="e71c8-130">PowerShell スクリプトを使用して監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="e71c8-130">Use a PowerShell script to search the audit log</span></span>](audit-log-search-script.md)

- <span data-ttu-id="e71c8-131">**監査記録を CSV ファイルにエクスポートします**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-131">**Export audit records to a CSV file**.</span></span> <span data-ttu-id="e71c8-132">コンプライアンス センターで監査ログ検索ツールを実行した後、検索で返された監査記録を CSV ファイルにエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-132">After running the Audit log search tool in the compliance center, you can export the audit records returned by the search to a CSV file.</span></span> <span data-ttu-id="e71c8-133">これにより、Microsoft Excel を使用して、異なる監査レコードのプロパティで並べ替えやフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-133">This lets you use Microsoft Excel sort and filter on different audit record properties.</span></span> <span data-ttu-id="e71c8-134">また、Excel Power Query の変換機能を使って、AuditData JSON オブジェクトの各プロパティを個別の列に分割することもできます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-134">You can also use Excel Power Query transform functionality to split each property in the AuditData JSON object into its own column.</span></span> <span data-ttu-id="e71c8-135">これにより、異なるイベントの類似データを効果的に表示し、比較することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-135">This lets you effectively view and compare similar data for different events.</span></span> <span data-ttu-id="e71c8-136">詳細については、「[監査ログ レコードをエクスポート、構成、表示する](export-view-audit-log-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-136">For more information, see [Export, configure, and view audit log records](export-view-audit-log-records.md).</span></span>

- <span data-ttu-id="e71c8-137">**Office 365 マネージメント アクティビティ API を介した監査ログにアクセスします**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-137">**Access to audit logs via Office 365 Management Activity API**.</span></span> <span data-ttu-id="e71c8-138">監査記録にアクセスして取得する 3 つ目の方法は、Office 365 マネージメント アクティビティ API を使用することです。</span><span class="sxs-lookup"><span data-stu-id="e71c8-138">A third method for accessing and retrieving audit records is to use the Office 365 Management Activity API.</span></span> <span data-ttu-id="e71c8-139">これにより、企業は監査データを既定の 90 日よりも長い期間保持し、監査データを SIEM ソリューションにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-139">This lets organizations retain auditing data for longer periods than the default 90 days and lets them import their auditing data to a SIEM solution.</span></span> <span data-ttu-id="e71c8-140">詳細については、「[Office 365 管理アクティビティ API のリファレンス](/office/office-365-management-api/office-365-management-activity-api-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-140">For more information, see [Office 365 Management Activity API reference](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

- <span data-ttu-id="e71c8-141">**90 日間の監査ログの保持**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-141">**90-day audit log retention**.</span></span> <span data-ttu-id="e71c8-142">監査されたアクティビティがユーザーや管理者によって実行されると、監査記録が生成され、組織の監査ログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-142">When an audited activity is performed by a user or admin, an audit record is generated and stored in the audit log for your organization.</span></span> <span data-ttu-id="e71c8-143">基本的な監査では、記録は 90 日間保持されるため、過去 3 か月以内に発生したアクティビティを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-143">In Basic Audit, records are retained for 90 days, which means you can search for activities that occurred within the past three months.</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="e71c8-144">高度な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-144">Advanced Audit</span></span>

<span data-ttu-id="e71c8-145">高度な監査は、基本的な監査の機能をベースに、監査ログの保持ポリシー、監査記録の長期保持、価値の高い重要なイベント、Office 365 マネージメント アクティビティ API への高い帯域幅でのアクセスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-145">Advanced Audit builds on the capabilities of Basic Audit by providing audit log retention policies, longer retention of audit records, high-value crucial events, and higher bandwidth access to the Office 365 Management Activity API.</span></span>

- <span data-ttu-id="e71c8-146">**監査ログの保持ポリシー**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-146">**Audit log retention policies**.</span></span> <span data-ttu-id="e71c8-147">カスタマイズした監査ログの保持ポリシーを作成すれば、最大 1 年間 (必要なアドオン ライセンスを持つユーザーは最大 10 年間)、長期にわたって監査レコードを保持できます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-147">You can create customized audit log retention policies to retain audit records for longer periods of time up to one year (and up to 10 years for users with required add-on license).</span></span> <span data-ttu-id="e71c8-148">監査されたアクティビティが発生するサービス、特定の監査されたアクティビティ、または監査されたアクティビティを実行するユーザーに基づいて、監査記録を保持するポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-148">You can create a policy to retain audit records based the service where the audited activities occur, specific audited activities, or the user who performs an audited activity.</span></span>

- <span data-ttu-id="e71c8-149">**監査記録の長期保持**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-149">**Longer retention of audit records**.</span></span> <span data-ttu-id="e71c8-150">Exchange、SharePoint、および Azure Active Directory の監査レコードは、既定で 1 年間保持されます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-150">Exchange, SharePoint, and Azure Active Directory audit records are retained for one year by default.</span></span> <span data-ttu-id="e71c8-151">その他のアクティビティの監査記録は、既定では 90 日間保持されますが、監査ログの保持ポリシーを使用して、より長い保持期間を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-151">Audit records for all other activities are retained for 90 days by default, or you can use audit log retention policies to configure longer retention periods.</span></span>

- <span data-ttu-id="e71c8-152">**価値の高い、重要なイベント**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-152">**High-value, crucial events**.</span></span> <span data-ttu-id="e71c8-153">重要なイベントの監査記録は、いつメール項目がアクセスされたか、いつメール項目が返信されたか、または転送されたか、ユーザーがいつ何を Exchange Online や SharePoint Online で検索したかなどの可視性を提供することで、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e71c8-153">Audit records for crucial events can help your organization conduct forensic and compliance investigations by providing visibility to events such as when mail items were accessed, or when mail items were replied to and forwarded, or when and what a user searched for in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="e71c8-154">これらの重要なイベントは、起こりうる侵害を調査し、侵害の範囲を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-154">These crucial events can help you investigate possible breaches and determine the scope of compromise.</span></span>

- <span data-ttu-id="e71c8-155">**Office 365 管理アクティビティ API への高帯域幅**。</span><span class="sxs-lookup"><span data-stu-id="e71c8-155">**Higher bandwidth to the Office 365 Management Activity API**.</span></span> <span data-ttu-id="e71c8-156">高度な監査は、組織が Office 365 マネージメント アクティビティ API を通じて監査ログにアクセスするための帯域幅を増やします。</span><span class="sxs-lookup"><span data-stu-id="e71c8-156">Advanced Audit provides organizations with more bandwidth to access auditing logs through the Office 365 Management Activity API.</span></span> <span data-ttu-id="e71c8-157">すべての組織 (基本的な監査または高度な監査を使用している組織) には、最初に 1 分あたり 2,000 リクエストの基準値が割り当てられますが、この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-157">Although all organizations (that have Basic Audit or Advanced Audit) are initially allocated a baseline of 2,000 requests per minute, this limit will dynamically increase depending on an organization's seat count and their licensing subscription.</span></span> <span data-ttu-id="e71c8-158">この結果、高度な監査を導入した組織は、基本的な監査を導入した組織の約 2 倍の帯域幅を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-158">This results in organizations with Advanced Audit getting about twice the bandwidth as organizations with Basic Audit.</span></span>

<span data-ttu-id="e71c8-159">高度な監査機能の詳細については、「[Microsoft 365 の高度な監査](advanced-audit.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-159">For more detailed information about Advanced Audit features, see [Advanced Audit in Microsoft 365](advanced-audit.md).</span></span>

## <a name="comparison-of-key-capabilities"></a><span data-ttu-id="e71c8-160">主要機能の比較</span><span class="sxs-lookup"><span data-stu-id="e71c8-160">Comparison of key capabilities</span></span>

<span data-ttu-id="e71c8-161">次の表は、基本的な監査と高度な監査で使用できる主な機能を比較したものです。</span><span class="sxs-lookup"><span data-stu-id="e71c8-161">The following table compares the key capabilities available in Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="e71c8-162">基本的な監査機能はすべて高度な監査に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-162">All Basic Audit functionality is included in Advanced Audit.</span></span>

|<span data-ttu-id="e71c8-163">機能</span><span class="sxs-lookup"><span data-stu-id="e71c8-163">Capability</span></span>|<span data-ttu-id="e71c8-164">基本的な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-164">Basic Audit</span></span>|<span data-ttu-id="e71c8-165">高度な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-165">Advanced Audit</span></span>|
|:------|:-------------|:-------------|
|<span data-ttu-id="e71c8-166">既定で有効</span><span class="sxs-lookup"><span data-stu-id="e71c8-166">Enabled by default</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-169">検索可能な数千件の監査イベント</span><span class="sxs-lookup"><span data-stu-id="e71c8-169">Thousands of searchable audit events</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-172">Microsoft 365 コンプライアンス センターの監査検索ツール</span><span class="sxs-lookup"><span data-stu-id="e71c8-172">Audit search tool in the Microsoft 365 compliance center</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-175">Search-UnifiedAuditLog コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e71c8-175">Search-UnifiedAuditLog cmdlet</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-178">監査記録を CSV ファイルにエクスポートします</span><span class="sxs-lookup"><span data-stu-id="e71c8-178">Export audit records to CSV file</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-181">Office 365 マネージメント アクティビティ API <sup>1</sup> を介した監査ログにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e71c8-181">Access to audit logs via Office 365 Management Activity API <sup>1</sup></span></span>|![サポート](../media/check-mark.png)|<span data-ttu-id="e71c8-183">![サポート対象](../media/check-mark.png)</sup></span><span class="sxs-lookup"><span data-stu-id="e71c8-183">![Supported](../media/check-mark.png)</sup></span></span>|
|<span data-ttu-id="e71c8-184">90 日間の監査ログの保持</span><span class="sxs-lookup"><span data-stu-id="e71c8-184">90-day audit log retention</span></span>|![サポート](../media/check-mark.png)|![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-187">1 年間の監査ログの保持</span><span class="sxs-lookup"><span data-stu-id="e71c8-187">1-year audit log retention</span></span>||![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-189">10 年間の監査ログの保持 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e71c8-189">10-year audit log retention <sup>2</sup></span></span>||![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-191">監査ログの保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="e71c8-191">Audit log retention policies</span></span>||![サポート](../media/check-mark.png)|
|<span data-ttu-id="e71c8-193">価値の高い、重要なイベント</span><span class="sxs-lookup"><span data-stu-id="e71c8-193">High-value, crucial events</span></span>||![サポート](../media/check-mark.png)|
||||
> [!NOTE]
> <span data-ttu-id="e71c8-195"><sup>1</sup> 高度な監査には、Office 365 マネージメント アクティビティ API へのより高い帯域幅のアクセスが含まれており、監査データへのアクセスが高速化されます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-195"><sup>1</sup> Advanced Audit includes higher bandwidth access to the Office 365 Management Activity API, which provides faster access to audit data.</span></span><br/><span data-ttu-id="e71c8-196"><sup>2</sup> 高度な監査に必要なライセンス (次のセクションで説明) に加えて、監査記録を 10 年間保持するためには、ユーザーはライセンスに 10 年監査ログ保持を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71c8-196"><sup>2</sup> In addition to the required licensing for Advanced Audit (described in the next section), a user must be assigned a 10-Year Audit Log Retention add on license to retain their audit records for 10 years.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="e71c8-197">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="e71c8-197">Licensing requirements</span></span>

<span data-ttu-id="e71c8-198">以下のセクションでは、基本的な監査と高度な監査のライセンス要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-198">The following sections identify the licensing requirements for Basic Audit and Advanced Audit.</span></span> <span data-ttu-id="e71c8-199">基本的な監査機能は高度な監査に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-199">Basic Audit functionality is included with Advanced Auditing.</span></span>

### <a name="basic-audit"></a><span data-ttu-id="e71c8-200">基本的な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-200">Basic Audit</span></span>

- <span data-ttu-id="e71c8-201">Microsoft 365 Enterprise E3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-201">Microsoft 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="e71c8-202">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e71c8-202">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="e71c8-203">Microsoft 365 Education A3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-203">Microsoft 365 Education A3 subscription</span></span>
- <span data-ttu-id="e71c8-204">Microsoft 365 Government G3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-204">Microsoft 365 Government G3 subscription</span></span>
- <span data-ttu-id="e71c8-205">Microsoft 365 Government G1 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-205">Microsoft 365 Government G1 subscription</span></span>
- <span data-ttu-id="e71c8-206">Office 365 Enterprise E3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-206">Office 365 Enterprise E3 subscription</span></span>
- <span data-ttu-id="e71c8-207">Office 365 Enterprise E1 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-207">Office 365 Enterprise E1 subscription</span></span>
- <span data-ttu-id="e71c8-208">Office 365 Education A1 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-208">Office 365 Education A1 subscription</span></span>
- <span data-ttu-id="e71c8-209">Office 365 Education A3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-209">Office 365 Education A3 subscription</span></span>

### <a name="advanced-audit"></a><span data-ttu-id="e71c8-210">高度な監査</span><span class="sxs-lookup"><span data-stu-id="e71c8-210">Advanced Audit</span></span>

- <span data-ttu-id="e71c8-211">Microsoft 365 Enterprise E5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-211">Microsoft 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="e71c8-212">Microsoft 365 E5 コンプライアンス アドオンが含まれている Microsoft 365 Enterprise E3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-212">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="e71c8-213">Microsoft 365 E5 電子情報開示および監査アドオンが含まれている Microsoft 365 Enterprise E3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-213">Microsoft 365 Enterprise E3 subscription + the Microsoft 365 E5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="e71c8-214">Microsoft 365 Education A5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-214">Microsoft 365 Education A5 subscription</span></span>
- <span data-ttu-id="e71c8-215">Microsoft 365 A5 コンプライアンス アドオンが含まれている Microsoft 365 Education A3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-215">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="e71c8-216">Microsoft 365 A5 電子情報開示および監査アドオンが含まれている Microsoft 365 Education A3 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-216">Microsoft 365 Education A3 subscription + the Microsoft 365 A5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="e71c8-217">Microsoft 365 Government G5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-217">Microsoft 365 Government G5 subscription</span></span>
- <span data-ttu-id="e71c8-218">Microsoft 365 G5 コンプライアンス アドオンが含まれている Microsoft 365 Government G5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-218">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="e71c8-219">Microsoft 365 G5 電子情報開示および監査アドオンが含まれている Microsoft 365 Government G5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-219">Microsoft 365 Government G5 subscription + the Microsoft 365 G5 eDiscovery and Audit add-on</span></span>
- <span data-ttu-id="e71c8-220">Office 365 Enterprise E5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-220">Office 365 Enterprise E5 subscription</span></span>
- <span data-ttu-id="e71c8-221">Office 365 Education A5 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="e71c8-221">Office 365 Education A5 subscription</span></span>
- <span data-ttu-id="e71c8-222">Office 365 Advanced Compliance アドオンが含まれている Office 365 Enterprise E3 サブスクリプション (新しいサブスクリプションでは利用できなくなりました)</span><span class="sxs-lookup"><span data-stu-id="e71c8-222">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions)</span></span>

## <a name="set-up-microsoft-365-auditing-solutions"></a><span data-ttu-id="e71c8-223">Microsoft 365 監査ソリューションの設定</span><span class="sxs-lookup"><span data-stu-id="e71c8-223">Set up Microsoft 365 auditing solutions</span></span>

<span data-ttu-id="e71c8-224">Microsoft 365 の監査ソリューションの使用を開始するには、以下のセットアップ ガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-224">To get started using the auditing solutions in Microsoft 365, see the following setup guidance.</span></span>

### <a name="set-up-basic-audit"></a><span data-ttu-id="e71c8-225">基本的な監査の設定</span><span class="sxs-lookup"><span data-stu-id="e71c8-225">Set up Basic Audit</span></span>

<span data-ttu-id="e71c8-226">最初の手順は、基本的な監査を設定し、監査ログ検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-226">The first step is to set up Basic Audit and then start running audit log searches.</span></span>

![高度な監査を設定するためのワークフロー](../media/BasicAuditingWorkflow.png)

1. <span data-ttu-id="e71c8-228">基本的な監査をサポートするサブスクリプションと、必要に応じて高度な監査をサポートするサブスクリプションが組織にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-228">Verify that your organization has a subscription that supports Basic Audit and if applicable, a subscription that supports Advanced Audit.</span></span>

2. <span data-ttu-id="e71c8-229">Microsoft 365 コンプライアンス センターの監査ログ検索ツールまたは **Search-UnifiedAuditLog** コマンドレットを使用する組織内のユーザーに、Exchange Online でアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-229">Assign permissions in Exchange Online to people in your organization who will use the audit log search tool in the Microsoft 365 compliance center or use the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="e71c8-230">具体的には、ユーザーは Exchange Online で閲覧限定の監査ログまたは監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71c8-230">Specifically, users must be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online.</span></span>

3. <span data-ttu-id="e71c8-p116">監査ログを検索します。手順 1 と手順 2 が完了したら、組織内のユーザーは監査ログ検索ツール (または対応するコマンドレット) を使用して、監査されたアクティビティを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-p116">Search the audit log. After completing step 1 and step 2, users in your organization can use the audit log search tool (or corresponding cmdlet) to search for audited activities.</span></span>

<span data-ttu-id="e71c8-233">詳しい説明は、「[基本的な監査の設定](set-up-basic-audit.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-233">For more detailed instructions, see [Set up Basic Audit](set-up-basic-audit.md).</span></span>

### <a name="set-up-advanced-audit"></a><span data-ttu-id="e71c8-234">高度な監査の設定</span><span class="sxs-lookup"><span data-stu-id="e71c8-234">Set up Advanced Audit</span></span>

<span data-ttu-id="e71c8-235">高度な監査をサポートするサブスクリプションがある場合は、以下の手順で高度な監査の追加機能を設定し、使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-235">If your organization has a subscription that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![高度な監査を設定するためのワークフロー](../media/AdvancedAuditWorkflow.png)

1. <span data-ttu-id="e71c8-237">ユーザーの高度な監査を設定します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-237">Set up Advanced Audit for users.</span></span> <span data-ttu-id="e71c8-238">この手順は、次のタスクで構成されています。</span><span class="sxs-lookup"><span data-stu-id="e71c8-238">This step consists of the following tasks:</span></span>

   - <span data-ttu-id="e71c8-239">ユーザーに高度な監査の適切なライセンスまたはアドオン・ライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71c8-239">Verifying that users are assigned the appropriate license or add-on license for Advanced Audit.</span></span>
  
   - <span data-ttu-id="e71c8-240">それらのユーザーに対して高度な監査アプリ/サービス プランを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e71c8-240">Turning on the Advanced Audit app/service plan must be for those users.</span></span>
  
   - <span data-ttu-id="e71c8-241">重要なイベントの監査を有効にして、そのユーザーに高度な監査アプリやサービス プランをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e71c8-241">Enabling the auditing of crucial events and then turning on the Advanced Auditing app/service plan for those users.</span></span>

2. <span data-ttu-id="e71c8-242">ユーザーが Exchange Online や SharePoint Online で検索を行った場合に、重要なイベントをログに記録することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-242">Enable crucial events to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span>

3. <span data-ttu-id="e71c8-p118">監査ログの保持ポリシーを設定します。Exchange、SharePoint、および Azure AD の監査記録を 1 年間保持する既定のポリシーに加えて、組織のセキュリティ運用チーム、IT チーム、およびコンプライアンス チームの要件に合わせて、監査ログの保持ポリシーを追加で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-p118">Set up audit log retention policies. In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span>

4. <span data-ttu-id="e71c8-p119">フォレンジック調査を行う場合、重要なイベントやその他のアクティビティを検索することができます。手順 1 と手順 2 が完了したら、侵害されたアカウントのフォレンジック調査や、その他の種類のセキュリティ調査やコンプライアンス調査を行う場合に、重要なイベントやその他のアクティビティを監査ログで検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-p119">Search for crucial events and other activities when conducting forensic investigations. After completing step 1 and step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span>

<span data-ttu-id="e71c8-247">詳しい説明は、「[高度な監査の設定](set-up-advanced-audit.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e71c8-247">For more detailed instructions, see [Set up Advanced Audit](set-up-advanced-audit.md).</span></span>

## <a name="training"></a><span data-ttu-id="e71c8-248">トレーニング</span><span class="sxs-lookup"><span data-stu-id="e71c8-248">Training</span></span>

<span data-ttu-id="e71c8-249">セキュリティ運用チーム、IT 管理者、コンプライアンス調査チームに基本的な監査と高度な監査の基礎についてトレーニングを行うことで、組織がより迅速に監査を利用して調査に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="e71c8-249">Training your security operations team, IT administrators, and compliance investigators team in the fundamentals for Basic Audit and Advanced Audit can help your organization get started more quickly using auditing to help with your investigations.</span></span> <span data-ttu-id="e71c8-250">Microsoft 365 は、組織内のこれらのユーザーが監査を始めるのに役立つ以下のリソースを提供します: [Microsoft 365 の電子情報開示と監査機能を説明する](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)。</span><span class="sxs-lookup"><span data-stu-id="e71c8-250">Microsoft 365 provides the following resource to help these users in your organization getting started with auditing: [Describe the eDiscovery and audit capabilities of Microsoft 365](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).</span></span>
