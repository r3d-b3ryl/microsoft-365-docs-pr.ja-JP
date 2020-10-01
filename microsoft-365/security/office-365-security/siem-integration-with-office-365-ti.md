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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーと Office 365 Advanced Threat Protection および関連する脅威イベントを Office 365 アクティビティ管理 API に統合します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 544093960570fe0e68ac47dc7bf9965fba2d30a1
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327167"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="29eae-103">高度な脅威保護との SIEM の統合</span><span class="sxs-lookup"><span data-stu-id="29eae-103">SIEM integration with Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="29eae-104">組織でセキュリティインシデントおよびイベント管理 (SIEM) サーバーを使用している場合は、Office 365 Advanced Threat Protection (Office 365 ATP) を SIEM サーバーに統合できます。</span><span class="sxs-lookup"><span data-stu-id="29eae-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection (Office 365 ATP) with your SIEM server.</span></span> <span data-ttu-id="29eae-105">この統合は、 [Office 365 アクティビティ管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)を使用してセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="29eae-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="29eae-106">SIEM の統合により、SIEM サーバーのレポートで、Office 365 ATP によって検出されたマルウェアやフィッシングなどの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="29eae-106">SIEM integration enables you to view information, such as malware or phish detected by Office 365 ATP, in your SIEM server reports.</span></span> 

- <span data-ttu-id="29eae-107">Office 365 ATP との SIEM の統合の例については、「 [Tech Community blog: office 365 ATP および O365 管理 API を使用した SOC の有効性を向上させる](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29eae-107">To see an example of SIEM integration with Office 365 ATP, see [Tech Community blog: Improve the Effectiveness of your SOC with Office 365 ATP and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="29eae-108">Office 365 管理 Api の詳細については、「 [office 365 管理 api の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29eae-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="29eae-109">SIEM 統合のしくみ</span><span class="sxs-lookup"><span data-stu-id="29eae-109">How SIEM integration works</span></span>

<span data-ttu-id="29eae-110">Office 365 Activity Management API は、組織の Microsoft 365 および Azure Active Directory のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="29eae-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="29eae-111">組織に Office 365 ATP プラン1または2、あるいは Office 365 E5 がある場合は、 [office 365 atp スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="29eae-111">If your organization has Office 365 ATP Plan 1 or 2, or Office 365 E5, you can use the [Office 365 ATP schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="29eae-112">最近、 [office 365](office-365-atp.md#office-365-atp-plan-1-and-plan-2) の自動調査および応答機能からのイベントが、Office 365 MANAGEMENT Activity API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="29eae-112">Recently, events from automated investigation and response capabilities in [Office 365 ATP Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="29eae-113">API には、ID、名前、状態などの主要な調査の詳細に関するデータだけでなく、調査のアクションとエンティティについての詳細な情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="29eae-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="29eae-114">SIEM サーバーまたはその他の同様のシステムが監査をポーリングして、検出イベントにアクセスし **ます** 。</span><span class="sxs-lookup"><span data-stu-id="29eae-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="29eae-115">詳細については、「 [Office 365 管理 api の使用を開始](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29eae-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="29eae-116">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="29eae-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="29eae-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="29eae-117">AuditLogRecordType</span></span>

<span data-ttu-id="29eae-118">次の表は、Office 365 ATP イベントに関連する **AuditLogRecordType** の値の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="29eae-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Office 365 ATP events:</span></span>

|<span data-ttu-id="29eae-119">値</span><span class="sxs-lookup"><span data-stu-id="29eae-119">Value</span></span>|<span data-ttu-id="29eae-120">メンバ名</span><span class="sxs-lookup"><span data-stu-id="29eae-120">Member name</span></span>|<span data-ttu-id="29eae-121">説明</span><span class="sxs-lookup"><span data-stu-id="29eae-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="29eae-122">個</span><span class="sxs-lookup"><span data-stu-id="29eae-122">28</span></span>|<span data-ttu-id="29eae-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="29eae-123">ThreatIntelligence</span></span>|<span data-ttu-id="29eae-124">Exchange Online Protection および Office 365 ATP からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="29eae-124">Phishing and malware events from Exchange Online Protection and Office 365 ATP.</span></span>|
|<span data-ttu-id="29eae-125">41</span><span class="sxs-lookup"><span data-stu-id="29eae-125">41</span></span>|<span data-ttu-id="29eae-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="29eae-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="29eae-127">[安全なリンク] Office 365 ATP からのブロック時間とブロックの上書きイベント。</span><span class="sxs-lookup"><span data-stu-id="29eae-127">Safe Links time-of-block and block override events from Office 365 ATP.</span></span>|
|<span data-ttu-id="29eae-128">47</span><span class="sxs-lookup"><span data-stu-id="29eae-128">47</span></span>|<span data-ttu-id="29eae-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="29eae-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="29eae-130">Office 365 ATP からの、SharePoint Online、OneDrive for Business、Microsoft Teams のファイルのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="29eae-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Office 365 ATP.</span></span>|
|<span data-ttu-id="29eae-131">64</span><span class="sxs-lookup"><span data-stu-id="29eae-131">64</span></span>|<span data-ttu-id="29eae-132">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="29eae-132">AirInvestigation</span></span>|<span data-ttu-id="29eae-133">Office 365 ATP Plan 2 から、調査の詳細や関連する成果物などの自動化された調査および応答イベント。</span><span class="sxs-lookup"><span data-stu-id="29eae-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Office 365 ATP Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="29eae-134">Office 365 Advanced Threat Protection との SIEM の統合をセットアップするには、全体管理者であるか、セキュリティ & コンプライアンスセンターに対してセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="29eae-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="29eae-135">Microsoft 365 環境では、監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29eae-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="29eae-136">この問題に関するヘルプを表示するには、「 [監査ログの検索を有効または無効](../../compliance/turn-audit-log-search-on-or-off.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29eae-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="29eae-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="29eae-137">See also</span></span>

[<span data-ttu-id="29eae-138">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="29eae-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="29eae-139">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="29eae-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)


