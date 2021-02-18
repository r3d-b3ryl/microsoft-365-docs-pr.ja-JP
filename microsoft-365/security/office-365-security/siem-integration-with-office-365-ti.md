---
title: siem integration with Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Office 365 アクティビティ管理 API で、組織の SIEM サーバーを Microsoft Defender for Office 365 および関連する脅威イベントと統合します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290395"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="27586-103">siem integration with Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="27586-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="27586-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="27586-104">**Applies to**</span></span>
- [<span data-ttu-id="27586-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="27586-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="27586-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="27586-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="27586-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27586-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="27586-108">組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、Microsoft Defender for Office 365 を SIEM サーバーと統合できます。</span><span class="sxs-lookup"><span data-stu-id="27586-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="27586-109">この統合は、Office [365 Activity Management API を使用して設定できます](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="27586-109">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="27586-110">SIEM 統合を使用すると、Microsoft Defender for Office 365 で検出されたマルウェアやフィッシングなどの情報を SIEM サーバー レポートで表示できます。</span><span class="sxs-lookup"><span data-stu-id="27586-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="27586-111">Office 365 向け Microsoft Defender との SIEM 統合の例については、Tech Community ブログを参照してください。Office [365 および O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)管理 API の Defender を使用して SOC の効果を向上させる。</span><span class="sxs-lookup"><span data-stu-id="27586-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="27586-112">Office 365 管理 API の詳細については、「Office [365 管理 API の概要」を参照してください](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。</span><span class="sxs-lookup"><span data-stu-id="27586-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="27586-113">SIEM 統合のしくみ</span><span class="sxs-lookup"><span data-stu-id="27586-113">How SIEM integration works</span></span>

<span data-ttu-id="27586-114">Office 365 アクティビティ管理 API は、組織の Microsoft 365 および Azure Active Directory アクティビティ ログから、ユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="27586-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="27586-115">Office 365 プラン 1 または 2 用の Microsoft Defender または Office 365 E5 を使用している組織では [、microsoft Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)スキーマを使用できます。</span><span class="sxs-lookup"><span data-stu-id="27586-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="27586-116">最近 [、microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) の自動調査および対応機能のイベントが Office 365 マネージメント アクティビティ API に追加されました。</span><span class="sxs-lookup"><span data-stu-id="27586-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="27586-117">ID、名前、状態などの主要な調査の詳細に関するデータを含めるだけでなく、この API には調査アクションとエンティティに関する高レベルの情報も含まれる。</span><span class="sxs-lookup"><span data-stu-id="27586-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="27586-118">SIEM サーバーまたは他の同様のシステムは **、audit.general** ワークロードをポーリングして、検出イベントにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="27586-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="27586-119">詳細については、「Office [365 Management API の使用を開始する」を参照してください](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="27586-119">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="27586-120">列挙値: AuditLogRecordType - 型: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="27586-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="27586-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="27586-121">AuditLogRecordType</span></span>

<span data-ttu-id="27586-122">次の表に、365 イベントの Microsoft Defender に関連する **AuditLogRecordType** Office示します。</span><span class="sxs-lookup"><span data-stu-id="27586-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="27586-123">値</span><span class="sxs-lookup"><span data-stu-id="27586-123">Value</span></span>|<span data-ttu-id="27586-124">メンバ名</span><span class="sxs-lookup"><span data-stu-id="27586-124">Member name</span></span>|<span data-ttu-id="27586-125">説明</span><span class="sxs-lookup"><span data-stu-id="27586-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="27586-126">28</span><span class="sxs-lookup"><span data-stu-id="27586-126">28</span></span>|<span data-ttu-id="27586-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="27586-127">ThreatIntelligence</span></span>|<span data-ttu-id="27586-128">Exchange Online Protection と Microsoft Defender for Office 365 からのフィッシングとマルウェアのイベント。</span><span class="sxs-lookup"><span data-stu-id="27586-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="27586-129">41</span><span class="sxs-lookup"><span data-stu-id="27586-129">41</span></span>|<span data-ttu-id="27586-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="27586-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="27586-131">「安全なリンク」のブロック時間と、365 年 365 日の Microsoft Defender からのオーバーライド イベントOfficeブロックします。</span><span class="sxs-lookup"><span data-stu-id="27586-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="27586-132">47</span><span class="sxs-lookup"><span data-stu-id="27586-132">47</span></span>|<span data-ttu-id="27586-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="27586-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="27586-134">Microsoft Defender for Office 365 の SharePoint Online、OneDrive for Business、Microsoft Teams のファイルに対するフィッシングおよびマルウェア イベント。</span><span class="sxs-lookup"><span data-stu-id="27586-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="27586-135">64</span><span class="sxs-lookup"><span data-stu-id="27586-135">64</span></span>|<span data-ttu-id="27586-136">AIR 調査</span><span class="sxs-lookup"><span data-stu-id="27586-136">AirInvestigation</span></span>|<span data-ttu-id="27586-137">Microsoft Defender for Office 365 プラン 2 の調査および対応イベント (調査の詳細や関連アーティファクトなど)</span><span class="sxs-lookup"><span data-stu-id="27586-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="27586-138">Office 365 向け Microsoft Defender との SIEM 統合をセットアップするには、グローバル管理者か、セキュリティ & コンプライアンス センターにセキュリティ管理者の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="27586-138">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="27586-139">Microsoft 365 環境で監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27586-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="27586-140">このヘルプについては、「監査ログの検索 [を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="27586-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="27586-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="27586-141">See also</span></span>

[<span data-ttu-id="27586-142">Office 365 脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="27586-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="27586-143">Office 365 での自動調査および対応 (AIR)</span><span class="sxs-lookup"><span data-stu-id="27586-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

