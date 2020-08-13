---
title: 高度な脅威保護との SIEM の統合
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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと Office 365 Advanced Threat Protection および関連する脅威イベントを Office 365 アクティビティ管理 API に統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656601"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="14a9d-103">高度な脅威保護との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="14a9d-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="14a9d-104">組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection を SIEM サーバーに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="14a9d-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="14a9d-105">SIEM の統合により、SIEM サーバーのレポートにある、Office 365 Advanced Protection によって検出されたマルウェアやフィッシングなどの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="14a9d-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="14a9d-106">SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。</span><span class="sxs-lookup"><span data-stu-id="14a9d-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="14a9d-107">Office 365 Activity Management API は、組織の Microsoft 365 for business および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="14a9d-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="14a9d-108">[Office 365 Advanced Threat protection スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)は Advanced threat protection と共に動作するため、組織が Office 365 Advanced Threat protection プラン1または Plan 2 または Office 365 E5 を使用している場合でも、SIEM サーバー統合に同じ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="14a9d-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span>

<span data-ttu-id="14a9d-109">最近の更新プログラムの一部として、office 365 Management Activity API 内の Office 365 ATP Plan 2 の自動調査および応答機能からのイベントも追加されました。</span><span class="sxs-lookup"><span data-stu-id="14a9d-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="14a9d-110">ID、名前、状態などの主要な調査の詳細に関するデータに加えて、調査のアクションおよびエンティティに関する概要情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="14a9d-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="14a9d-111">SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり **ます。一般的な** ワークロードを検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="14a9d-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="14a9d-112">詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a9d-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="14a9d-113">また、 **AuditLogRecordType** の次の値は、OFFICE 365 ATP イベントに関連しています。</span><span class="sxs-lookup"><span data-stu-id="14a9d-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="14a9d-114">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="14a9d-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="14a9d-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="14a9d-115">AuditLogRecordType</span></span>

****

|<span data-ttu-id="14a9d-116">値</span><span class="sxs-lookup"><span data-stu-id="14a9d-116">Value</span></span>|<span data-ttu-id="14a9d-117">メンバ名</span><span class="sxs-lookup"><span data-stu-id="14a9d-117">Member name</span></span>|<span data-ttu-id="14a9d-118">説明</span><span class="sxs-lookup"><span data-stu-id="14a9d-118">Description</span></span>|
|---|---|---|
|<span data-ttu-id="14a9d-119">個</span><span class="sxs-lookup"><span data-stu-id="14a9d-119">28</span></span>|<span data-ttu-id="14a9d-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="14a9d-120">ThreatIntelligence</span></span>|<span data-ttu-id="14a9d-121">Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="14a9d-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="14a9d-122">41</span><span class="sxs-lookup"><span data-stu-id="14a9d-122">41</span></span>|<span data-ttu-id="14a9d-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="14a9d-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="14a9d-124">ATP の安全なリンクは、Office 365 Advanced Threat Protection からのイベントをブロックする時間とブロックします。</span><span class="sxs-lookup"><span data-stu-id="14a9d-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="14a9d-125">47</span><span class="sxs-lookup"><span data-stu-id="14a9d-125">47</span></span>|<span data-ttu-id="14a9d-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="14a9d-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="14a9d-127">SharePoint Online、OneDrive for Business、および Microsoft Teams for Office 365 Advanced Threat Protection のファイルのフィッシングとマルウェアイベント。</span><span class="sxs-lookup"><span data-stu-id="14a9d-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="14a9d-128">64</span><span class="sxs-lookup"><span data-stu-id="14a9d-128">64</span></span>|<span data-ttu-id="14a9d-129">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="14a9d-129">AirInvestigation</span></span>|<span data-ttu-id="14a9d-130">Office 365 Advanced Threat Protection プラン2の調査詳細や関連する成果物など、自動化された調査および応答イベント。</span><span class="sxs-lookup"><span data-stu-id="14a9d-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="14a9d-131">Office 365 Advanced Threat Protection との SIEM の統合をセットアップするには、全体管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14a9d-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="14a9d-132">Microsoft 365 環境では、監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14a9d-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="14a9d-133">この問題に関するヘルプを表示するには、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14a9d-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="14a9d-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="14a9d-134">Related topics</span></span>

[<span data-ttu-id="14a9d-135">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="14a9d-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="14a9d-136">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="14a9d-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="14a9d-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="14a9d-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="14a9d-138">セキュリティ/コンプライアンスセンターのスマートレポートと洞察 &amp;</span><span class="sxs-lookup"><span data-stu-id="14a9d-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="14a9d-139">セキュリティ/コンプライアンスセンターのアクセス許可 &amp;</span><span class="sxs-lookup"><span data-stu-id="14a9d-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
