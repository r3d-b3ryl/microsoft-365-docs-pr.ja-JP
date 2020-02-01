---
title: Office 365 Advanced Threat Protection との SIEM の統合
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
ms.openlocfilehash: 8a870e02a37ea7f4961d0b8dc42a49cb59d2bace
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598284"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a><span data-ttu-id="8bf66-103">Office 365 Advanced Threat Protection との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="8bf66-103">SIEM integration with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="8bf66-104">組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection を SIEM サーバーに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="8bf66-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="8bf66-105">SIEM の統合により、SIEM サーバーのレポートにある、Office 365 Advanced Protection によって検出されたマルウェアやフィッシングなどの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8bf66-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="8bf66-106">SIEM 統合をセットアップするには、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8bf66-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="8bf66-107">Office 365 Activity Management API は、組織の Office 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8bf66-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="8bf66-108">[Office 365 Advanced Threat protection スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)は Advanced threat protection と共に動作するため、組織が Office 365 Advanced Threat protection プラン1または Plan 2 または Office 365 E5 を使用している場合でも、SIEM サーバー統合に同じ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bf66-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="8bf66-109">最近の更新プログラムの一部として、office 365 Management Activity API 内の Office 365 ATP Plan 2 の自動調査および応答機能からのイベントも追加されました。</span><span class="sxs-lookup"><span data-stu-id="8bf66-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="8bf66-110">ID、名前、状態などの主要な調査の詳細に関するデータに加えて、調査のアクションおよびエンティティに関する概要情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bf66-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="8bf66-111">SIEM サーバーまたはその他の同様のシステムが監査をポーリングする必要があり**ます。一般的な**ワークロードを検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8bf66-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="8bf66-112">詳細については、「 [Office 365 Management api の概要](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bf66-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="8bf66-113">また、 **AuditLogRecordType**の次の値は、OFFICE 365 ATP イベントに関連しています。</span><span class="sxs-lookup"><span data-stu-id="8bf66-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="8bf66-114">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="8bf66-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="8bf66-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="8bf66-115">AuditLogRecordType</span></span>

|<span data-ttu-id="8bf66-116">値</span><span class="sxs-lookup"><span data-stu-id="8bf66-116">Value</span></span>|<span data-ttu-id="8bf66-117">メンバ名</span><span class="sxs-lookup"><span data-stu-id="8bf66-117">Member name</span></span>|<span data-ttu-id="8bf66-118">説明</span><span class="sxs-lookup"><span data-stu-id="8bf66-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8bf66-119">個</span><span class="sxs-lookup"><span data-stu-id="8bf66-119">28</span></span>|<span data-ttu-id="8bf66-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="8bf66-120">ThreatIntelligence</span></span>|<span data-ttu-id="8bf66-121">Exchange Online Protection と Office 365 Advanced Threat Protection からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="8bf66-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="8bf66-122">41</span><span class="sxs-lookup"><span data-stu-id="8bf66-122">41</span></span>|<span data-ttu-id="8bf66-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="8bf66-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="8bf66-124">ATP の安全なリンクは、Office 365 Advanced Threat Protection からのイベントをブロックする時間とブロックします。</span><span class="sxs-lookup"><span data-stu-id="8bf66-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="8bf66-125">47</span><span class="sxs-lookup"><span data-stu-id="8bf66-125">47</span></span>|<span data-ttu-id="8bf66-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="8bf66-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="8bf66-127">SharePoint Online、OneDrive for Business、および Microsoft Teams for Office 365 Advanced Threat Protection のファイルのフィッシングとマルウェアイベント。</span><span class="sxs-lookup"><span data-stu-id="8bf66-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="8bf66-128">64</span><span class="sxs-lookup"><span data-stu-id="8bf66-128">64</span></span>|<span data-ttu-id="8bf66-129">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="8bf66-129">AirInvestigation</span></span>|<span data-ttu-id="8bf66-130">Office 365 Advanced Threat Protection プラン2の調査詳細や関連する成果物など、自動化された調査および応答イベント。</span><span class="sxs-lookup"><span data-stu-id="8bf66-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="8bf66-131">Office 365 のグローバル管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。 Office 365 Advanced Threat Protection との SIEM の統合をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf66-131">You must be an Office 365 global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="8bf66-132">Office 365 環境の監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf66-132">Audit logging must be turned on for your Office 365 environment.</span></span> <span data-ttu-id="8bf66-133">この問題に関するヘルプを表示するには、「 [Office 365 監査ログ検索をオンまたはオフに](../../compliance/turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bf66-133">To get help with this, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bf66-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bf66-134">Related topics</span></span>

[<span data-ttu-id="8bf66-135">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="8bf66-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="8bf66-136">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="8bf66-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="8bf66-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8bf66-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="8bf66-138">Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと洞察</span><span class="sxs-lookup"><span data-stu-id="8bf66-138">Smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="8bf66-139">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="8bf66-139">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
