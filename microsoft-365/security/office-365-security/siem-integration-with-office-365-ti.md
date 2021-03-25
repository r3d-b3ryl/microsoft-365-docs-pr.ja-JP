---
title: SIEM との Microsoft Defender との統合 (Office 365)
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
description: 組織の SIEM サーバーを Microsoft Defender と統合して、Office 365 アクティビティ管理 API Office関連する脅威イベントを検出します。
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
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="25e37-103">SIEM との Microsoft Defender との統合 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="25e37-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="25e37-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="25e37-104">**Applies to**</span></span>
- [<span data-ttu-id="25e37-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="25e37-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="25e37-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="25e37-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="25e37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25e37-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="25e37-108">組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、Microsoft Defender for Office 365 を SIEM サーバーに統合できます。</span><span class="sxs-lookup"><span data-stu-id="25e37-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="25e37-109">この統合は [、365](/office/office-365-management-api/office-365-management-activity-api-reference)アクティビティOffice API を使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="25e37-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="25e37-110">SIEM 統合を使用すると、MICROSOFT Defender が 365 用に検出したマルウェアやOfficeなどの情報を SIEM サーバー レポートで表示できます。</span><span class="sxs-lookup"><span data-stu-id="25e37-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="25e37-111">microsoft Defender for Office 365 との SIEM 統合の例については、「Tech Community blog: Improve the EFFECTIVENESS of your SOC with [Defender for Office 365」および「O365 Management API」](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e37-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="25e37-112">365 管理 API Office詳細については [、「365 管理](/office/office-365-management-api/office-365-management-apis-overview)API Office概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25e37-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="25e37-113">SIEM 統合の仕組み</span><span class="sxs-lookup"><span data-stu-id="25e37-113">How SIEM integration works</span></span>

<span data-ttu-id="25e37-114">Office 365 アクティビティ管理 API は、組織の Microsoft 365 アクティビティ ログと Azure Active Directory アクティビティ ログから、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="25e37-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="25e37-115">組織に microsoft Defender for Office 365 Plan 1 または 2、または Office 365 E5 がある場合は、Microsoft Defender を Office [365 スキーマに使用できます](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。</span><span class="sxs-lookup"><span data-stu-id="25e37-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="25e37-116">最近では、microsoft Defender for [Office 365 プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) の自動調査と対応機能のイベントが Office 365 管理アクティビティ API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="25e37-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="25e37-117">ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、API には調査アクションやエンティティに関する高レベルの情報も含まれる。</span><span class="sxs-lookup"><span data-stu-id="25e37-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="25e37-118">SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="25e37-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="25e37-119">詳細については [、「365 管理 API のOffice」を参照してください](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="25e37-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="25e37-120">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="25e37-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="25e37-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="25e37-121">AuditLogRecordType</span></span>

<span data-ttu-id="25e37-122">次の表に、Microsoft Defender の 365 イベントに関連する **AuditLogRecordType** の値Office示します。</span><span class="sxs-lookup"><span data-stu-id="25e37-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="25e37-123">値</span><span class="sxs-lookup"><span data-stu-id="25e37-123">Value</span></span>|<span data-ttu-id="25e37-124">メンバ名</span><span class="sxs-lookup"><span data-stu-id="25e37-124">Member name</span></span>|<span data-ttu-id="25e37-125">説明</span><span class="sxs-lookup"><span data-stu-id="25e37-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="25e37-126">28</span><span class="sxs-lookup"><span data-stu-id="25e37-126">28</span></span>|<span data-ttu-id="25e37-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="25e37-127">ThreatIntelligence</span></span>|<span data-ttu-id="25e37-128">Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="25e37-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="25e37-129">41</span><span class="sxs-lookup"><span data-stu-id="25e37-129">41</span></span>|<span data-ttu-id="25e37-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="25e37-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="25e37-131">365 の Microsoft Defender からのセーフ リンクのタイム オブ ブロックイベントとブロック オーバーライド イベントOfficeします。</span><span class="sxs-lookup"><span data-stu-id="25e37-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="25e37-132">47</span><span class="sxs-lookup"><span data-stu-id="25e37-132">47</span></span>|<span data-ttu-id="25e37-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="25e37-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="25e37-134">SharePoint Online、OneDrive for Business、Microsoft Teams のファイルのフィッシングおよびマルウェア イベント (Microsoft Defender for microsoft Defender for Office 365)。</span><span class="sxs-lookup"><span data-stu-id="25e37-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="25e37-135">64</span><span class="sxs-lookup"><span data-stu-id="25e37-135">64</span></span>|<span data-ttu-id="25e37-136">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="25e37-136">AirInvestigation</span></span>|<span data-ttu-id="25e37-137">Microsoft Defender for microsoft Defender for Office 365 プラン 2 の調査の詳細や関連する成果物など、自動調査および応答イベント。</span><span class="sxs-lookup"><span data-stu-id="25e37-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="25e37-138">Microsoft Defender との SIEM 統合を 365 用にセットアップするには、グローバル管理者またはセキュリティ & コンプライアンス センターにセキュリティ管理者の役割が割り当てられているOfficeがあります。</span><span class="sxs-lookup"><span data-stu-id="25e37-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="25e37-139">Microsoft 365 環境で監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e37-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="25e37-140">このヘルプを表示するには、「監査ログ検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="25e37-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25e37-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="25e37-141">See also</span></span>

[<span data-ttu-id="25e37-142">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="25e37-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="25e37-143">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="25e37-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)