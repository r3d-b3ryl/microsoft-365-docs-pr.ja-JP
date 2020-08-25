---
title: Advanced Threat Protection と SIEM 統合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Office 365 Activity Management API で、Office 365 Advanced Threat Protection と関連する脅威イベントと組織の SIEM サーバーを統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860691"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="e3517-103">Advanced Threat Protection と SIEM 統合</span><span class="sxs-lookup"><span data-stu-id="e3517-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="e3517-104">組織でセキュリティ インシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection (Office 365 ATP) を SIEM サーバーと統合できます。</span><span class="sxs-lookup"><span data-stu-id="e3517-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="e3517-105">この統合は [、Office 365 アクティビティ管理 API を使用してセットアップできます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="e3517-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="e3517-106">SIEM 統合を使用すると、SIEM サーバー レポート内で、Office 365 ATP によって検出されたマルウェアやフィッシング対策などの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3517-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="e3517-107">Office 365 ATP との SIEM 統合の例については、テクニカル [ブログ: Office 365 ATP および O365 Management API を使用して SOC の効果を向上させる方法を参照してください](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。</span><span class="sxs-lookup"><span data-stu-id="e3517-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="e3517-108">Office 365 Management API の詳細については [、Office 365 管理 API の概要を参照してください](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="e3517-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="e3517-109">SIEM 統合のしくみ</span><span class="sxs-lookup"><span data-stu-id="e3517-109">How SIEM integration works</span></span>

<span data-ttu-id="e3517-110">Office 365 アクティビティ管理 API は、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を、組織の Microsoft 365 および Azure Active Directory のアクティビティ ログから取得します。</span><span class="sxs-lookup"><span data-stu-id="e3517-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="e3517-111">組織が Office 365 ATP プラン 1 または Office office 365 E5 を利用している場合は [、Office 365 ATP スキーマを使用できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="e3517-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="e3517-112">最近では [、Office 365 ATP](office-365-atp.md#office-365-atp-plan-1-and-plan-2) プラン 2 の自動調査および対応機能のイベントが、Office 365 管理アクティビティ API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e3517-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="e3517-113">ID、名前、状態などの主要な調査の詳細に関するデータを含めることに加えて、API には調査処理とエンティティに関する詳細な情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3517-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="e3517-114">SIEM サーバーまたはその他の類似システムは **、audit.general workload をポーリング** して検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e3517-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="e3517-115">詳細については [、「Get started with Office 365 Management APIs (Office 365 Management API の使用を開始する」を参照してください](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="e3517-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 


## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="e3517-116">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="e3517-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="e3517-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="e3517-117">AuditLogRecordType</span></span>

<span data-ttu-id="e3517-118">次の表は、ATP の **ATP イベントに関連する AuditLogRecordType** Officeの値をまとしたしています。</span><span class="sxs-lookup"><span data-stu-id="e3517-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="e3517-119">値</span><span class="sxs-lookup"><span data-stu-id="e3517-119">Value</span></span>|<span data-ttu-id="e3517-120">メンバ名</span><span class="sxs-lookup"><span data-stu-id="e3517-120">Member name</span></span>|<span data-ttu-id="e3517-121">説明</span><span class="sxs-lookup"><span data-stu-id="e3517-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="e3517-122">28</span><span class="sxs-lookup"><span data-stu-id="e3517-122">28</span></span>|<span data-ttu-id="e3517-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="e3517-123">ThreatIntelligence</span></span>|<span data-ttu-id="e3517-124">Exchange Online Protection と 365 ATP からのフィッシングとマルウェアOfficeと。</span><span class="sxs-lookup"><span data-stu-id="e3517-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="e3517-125">41</span><span class="sxs-lookup"><span data-stu-id="e3517-125">41</span></span>|<span data-ttu-id="e3517-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="e3517-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="e3517-127">ATP の安全なリンク時のブロック時 --、365 ATP からのイベントOfficeブロックします。</span><span class="sxs-lookup"><span data-stu-id="e3517-127">ATP Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="e3517-128">47</span><span class="sxs-lookup"><span data-stu-id="e3517-128">47</span></span>|<span data-ttu-id="e3517-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="e3517-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="e3517-130">SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに対するフィッシングとマルウェアのイベント (Office 365 ATP)。</span><span class="sxs-lookup"><span data-stu-id="e3517-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="e3517-131">64</span><span class="sxs-lookup"><span data-stu-id="e3517-131">64</span></span>|<span data-ttu-id="e3517-132">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="e3517-132">AirInvestigation</span></span>|<span data-ttu-id="e3517-133">Office 365 ATP プラン 2 の調査の詳細や関連する成果物などの自動調査および対応イベント。</span><span class="sxs-lookup"><span data-stu-id="e3517-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="e3517-134">SIEM と Office 365 Advanced Threat Protection の統合をセットアップするには、グローバル管理者であるか、セキュリティ & コンプライアンス センターにセキュリティ管理者ロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3517-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="e3517-135">Microsoft 365 環境に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3517-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="e3517-136">この問題についてヘルプを参照するには、「監査 [ログの検索を有効または無効にする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="e3517-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3517-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3517-137">See also</span></span>

[<span data-ttu-id="e3517-138">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="e3517-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="e3517-139">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="e3517-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


