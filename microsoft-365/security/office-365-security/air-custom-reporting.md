---
title: 自動調査と対応によるカスタム レポート ソリューション
keywords: SIEM、API、AIR、autoIR、Microsoft Defender for Endpoint、自動調査、統合、カスタム レポート
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 自動調査と対応をカスタムまたはサード パーティのレポート ソリューションに統合する方法について説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275014"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="81efe-104">Microsoft Defender for microsoft Defender 用のカスタムまたはサード パーティ製のレポート Office 365</span><span class="sxs-lookup"><span data-stu-id="81efe-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="81efe-105">Microsoft [Defender for Office 365、](defender-for-office-365.md)自動調査に関する[詳細情報を取得します](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="81efe-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="81efe-106">ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。</span><span class="sxs-lookup"><span data-stu-id="81efe-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="81efe-107">組織が自動調査に関する情報を[](office-365-air.md)そのようなソリューションと統合する場合は、管理アクティビティ API Office 365使用できます。</span><span class="sxs-lookup"><span data-stu-id="81efe-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="81efe-108">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="81efe-108">**Applies to**</span></span>
- [<span data-ttu-id="81efe-109">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="81efe-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="81efe-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="81efe-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="81efe-111">Microsoft [Defender for Office 365、](defender-for-office-365.md)自動調査に関する[詳細情報を取得します](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="81efe-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="81efe-112">ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。</span><span class="sxs-lookup"><span data-stu-id="81efe-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="81efe-113">組織が自動調査に関する情報をそのようなソリューションと統合する場合は、Office 365管理アクティビティ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="81efe-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="81efe-114">関連情報</span><span class="sxs-lookup"><span data-stu-id="81efe-114">Resource</span></span>|<span data-ttu-id="81efe-115">説明</span><span class="sxs-lookup"><span data-stu-id="81efe-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="81efe-116">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="81efe-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="81efe-117">管理Office 365 API は、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を、Microsoft 365およびAzure Active Directory提供します。</span><span class="sxs-lookup"><span data-stu-id="81efe-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="81efe-118">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="81efe-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="81efe-119">このOffice 365管理 API は、Azure ADを使用して、アプリケーションがデータにアクセスする認証Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="81efe-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="81efe-120">この記事の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="81efe-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="81efe-121">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="81efe-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="81efe-122">Office 365 管理アクティビティ API を使用して、ユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を Microsoft 365 および Azure AD アクティビティ ログから取得できます。</span><span class="sxs-lookup"><span data-stu-id="81efe-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="81efe-123">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81efe-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="81efe-124">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="81efe-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="81efe-125">Office 365 管理アクティビティ[](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)API で使用できる特定の種類のデータについて学習するには、共通スキーマと Defender for [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) Office 365 および脅威の調査と応答スキーマの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="81efe-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="81efe-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="81efe-126">See also</span></span>

- [<span data-ttu-id="81efe-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="81efe-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="81efe-128">Defender での自動調査Microsoft 365対応</span><span class="sxs-lookup"><span data-stu-id="81efe-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
