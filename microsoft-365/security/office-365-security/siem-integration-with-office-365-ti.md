---
title: SIEM との Microsoft Defender との統合 (Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 組織の SIEM サーバーを Microsoft Defender と統合して、Office 365アクティビティ管理 API Office 365関連する脅威イベントを検出します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205176"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="e369a-103">SIEM との Microsoft Defender との統合 (Office 365</span><span class="sxs-lookup"><span data-stu-id="e369a-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="e369a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e369a-104">**Applies to**</span></span>
- [<span data-ttu-id="e369a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e369a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e369a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e369a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e369a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e369a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e369a-108">組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、MICROSOFT Defender for Office 365 SIEM サーバーに統合できます。</span><span class="sxs-lookup"><span data-stu-id="e369a-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="e369a-109">この統合は、アクティビティ管理 API Office 365[使用して設定できます](/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="e369a-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="e369a-110">SIEM 統合を使用すると、SIEM サーバー レポートで Microsoft Defender によって検出されたマルウェアやフィッシングなどの情報Office 365を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e369a-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="e369a-111">microsoft Defender for Office 365 との SIEM 統合の例については、「Tech Community ブログ: Office 365 および[O365 管理 API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)の Defender を使用した SOC の有効性の向上」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e369a-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="e369a-112">管理 API の詳細については、「Office 365管理 API[のOffice 365」を参照してください](/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="e369a-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="e369a-113">SIEM 統合の仕組み</span><span class="sxs-lookup"><span data-stu-id="e369a-113">How SIEM integration works</span></span>

<span data-ttu-id="e369a-114">このOffice 365アクティビティ管理 API は、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を、組織の Microsoft 365 および Azure Active Directoryログから取得します。</span><span class="sxs-lookup"><span data-stu-id="e369a-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="e369a-115">組織に Microsoft Defender for Office 365プラン 1 または 2、または E5 Office 365がある場合は[、Microsoft Defender](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)を使用してスキーマOffice 365できます。</span><span class="sxs-lookup"><span data-stu-id="e369a-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="e369a-116">最近では、Microsoft Defender for Office 365[プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)の自動調査と対応機能のイベントが Office 365管理アクティビティ API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e369a-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="e369a-117">ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、API には調査アクションやエンティティに関する高レベルの情報も含まれる。</span><span class="sxs-lookup"><span data-stu-id="e369a-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="e369a-118">SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e369a-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="e369a-119">詳細については、「管理 API の使用[Office 365」を参照してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="e369a-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="e369a-120">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="e369a-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="e369a-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="e369a-121">AuditLogRecordType</span></span>

<span data-ttu-id="e369a-122">次の表に、Microsoft Defender のイベントに関連する **AuditLogRecordType** の値Office 365示します。</span><span class="sxs-lookup"><span data-stu-id="e369a-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="e369a-123">値</span><span class="sxs-lookup"><span data-stu-id="e369a-123">Value</span></span>|<span data-ttu-id="e369a-124">メンバ名</span><span class="sxs-lookup"><span data-stu-id="e369a-124">Member name</span></span>|<span data-ttu-id="e369a-125">説明</span><span class="sxs-lookup"><span data-stu-id="e369a-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="e369a-126">28</span><span class="sxs-lookup"><span data-stu-id="e369a-126">28</span></span>|<span data-ttu-id="e369a-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="e369a-127">ThreatIntelligence</span></span>|<span data-ttu-id="e369a-128">Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="e369a-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="e369a-129">41</span><span class="sxs-lookup"><span data-stu-id="e369a-129">41</span></span>|<span data-ttu-id="e369a-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="e369a-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="e369a-131">セーフMicrosoft Defender のタイム オブ ブロックイベントとブロック オーバーライド イベントをリンクして、Office 365。</span><span class="sxs-lookup"><span data-stu-id="e369a-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="e369a-132">47</span><span class="sxs-lookup"><span data-stu-id="e369a-132">47</span></span>|<span data-ttu-id="e369a-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="e369a-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="e369a-134">Microsoft Defender for SharePoint オンライン、OneDrive for Business、Microsoft Teamsのファイルのフィッシングイベントとマルウェア イベントOffice 365。</span><span class="sxs-lookup"><span data-stu-id="e369a-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="e369a-135">64</span><span class="sxs-lookup"><span data-stu-id="e369a-135">64</span></span>|<span data-ttu-id="e369a-136">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="e369a-136">AirInvestigation</span></span>|<span data-ttu-id="e369a-137">Microsoft Defender for microsoft Defender for Office 365プラン 2 の調査の詳細や関連する成果物などの、自動調査およびOffice 365イベント。</span><span class="sxs-lookup"><span data-stu-id="e369a-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="e369a-138">Microsoft Defender for microsoft Defender との SIEM 統合をセットアップするには、グローバル管理者またはセキュリティ & コンプライアンス センターにセキュリティ管理者の役割が割り当てられている必要Office 365。</span><span class="sxs-lookup"><span data-stu-id="e369a-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="e369a-139">監査ログは、ユーザーの環境Microsoft 365する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e369a-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="e369a-140">このヘルプを表示するには、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="e369a-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e369a-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e369a-141">See also</span></span>

[<span data-ttu-id="e369a-142">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="e369a-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="e369a-143">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="e369a-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)