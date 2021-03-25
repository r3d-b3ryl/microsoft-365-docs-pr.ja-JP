---
title: 自動調査と対応によるカスタム レポート ソリューション
keywords: SIEM、API、AIR、autoIR、ATP、自動調査、統合、カスタム レポート
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 82f3b38e5b6e31313c94f5ac389e883f6b076540
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206720"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="cbec3-104">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cbec3-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cbec3-105">Microsoft [Defender for Office 365 では](defender-for-office-365.md)、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="cbec3-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="cbec3-106">ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。</span><span class="sxs-lookup"><span data-stu-id="cbec3-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="cbec3-107">組織が自動調査に関する情報を[](office-365-air.md)そのようなソリューションと統合する場合は、Office 365 Management Activity API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbec3-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="cbec3-108">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cbec3-108">**Applies to**</span></span>
- [<span data-ttu-id="cbec3-109">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="cbec3-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cbec3-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbec3-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cbec3-111">Microsoft [Defender for Office 365 では](defender-for-office-365.md)、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="cbec3-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="cbec3-112">ただし、一部の組織ではカスタムまたはサード パーティのレポート ソリューションも使用します。</span><span class="sxs-lookup"><span data-stu-id="cbec3-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="cbec3-113">組織が自動調査に関する情報をそのようなソリューションと統合する場合は、365 管理アクティビティ API Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbec3-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="cbec3-114">関連情報</span><span class="sxs-lookup"><span data-stu-id="cbec3-114">Resource</span></span>|<span data-ttu-id="cbec3-115">説明</span><span class="sxs-lookup"><span data-stu-id="cbec3-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="cbec3-116">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="cbec3-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="cbec3-117">365 Office管理アクティビティ API は、Microsoft 365 および Azure Active Directory アクティビティ ログからのさまざまなユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbec3-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="cbec3-118">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="cbec3-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="cbec3-119">365 Office 365 管理 API は、Azure ADを使用して、アプリケーションが Microsoft 365 データにアクセスする認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cbec3-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="cbec3-120">この記事の手順に従って、これを設定します。</span><span class="sxs-lookup"><span data-stu-id="cbec3-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="cbec3-121">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="cbec3-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="cbec3-122">Office 365 管理アクティビティ API を使用して、Microsoft 365 および Azure AD アクティビティ ログからユーザー、管理者、システム、ポリシーのアクションとイベントに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="cbec3-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="cbec3-123">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbec3-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="cbec3-124">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="cbec3-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="cbec3-125">[Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の共通スキーマと Defender と脅威の調査と応答スキーマの概要を確認し、Office 365 管理アクティビティ API で利用できる特定の種類のデータについて説明します。 [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)</span><span class="sxs-lookup"><span data-stu-id="cbec3-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="cbec3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbec3-126">See also</span></span>

- [<span data-ttu-id="cbec3-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="cbec3-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cbec3-128">Microsoft 365 Defender での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="cbec3-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
