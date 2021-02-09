---
title: 自動調査と対応を備えたカスタム レポート ソリューション
keywords: SIEM, API, AIR, autoIR, ATP, 自動調査, 統合, カスタム レポート
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
description: 自動調査と対応をカスタムまたはサード パーティ製のレポート ソリューションに統合する方法について説明します。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142977"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="0887a-104">Microsoft Defender for Office 365 向けカスタム またはサード パーティ製のレポート ソリューション</span><span class="sxs-lookup"><span data-stu-id="0887a-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0887a-105">Microsoft [Defender for Office 365](office-365-atp.md)では、自動調査に関する [詳細情報を取得できます](air-view-investigation-results.md)。</span><span class="sxs-lookup"><span data-stu-id="0887a-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="0887a-106">ただし、一部の組織では、カスタムまたはサード パーティ製のレポート ソリューションも使用します。</span><span class="sxs-lookup"><span data-stu-id="0887a-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="0887a-107">自動調査に関する情報をそのようなソリューション[](office-365-air.md)と統合する場合は、Office 365 マネージメント アクティビティ API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0887a-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="0887a-108">統合を構成するリソース</span><span class="sxs-lookup"><span data-stu-id="0887a-108">Resources to configure integration</span></span>

|<span data-ttu-id="0887a-109">関連情報</span><span class="sxs-lookup"><span data-stu-id="0887a-109">Resource</span></span>|<span data-ttu-id="0887a-110">説明</span><span class="sxs-lookup"><span data-stu-id="0887a-110">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="0887a-111">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="0887a-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="0887a-112">Office 365 管理アクティビティ API は、Microsoft 365 と Azure Active Directory のアクティビティ ログから、さまざまなユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0887a-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="0887a-113">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="0887a-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="0887a-114">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスする認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0887a-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="0887a-115">この記事の手順に従って設定します。</span><span class="sxs-lookup"><span data-stu-id="0887a-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="0887a-116">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="0887a-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="0887a-117">Office 365 管理アクティビティ API を使用して、Microsoft 365 および Azure AD アクティビティ ログから、ユーザー、管理者、システム、およびポリシー アクションとイベントに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0887a-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="0887a-118">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0887a-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="0887a-119">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="0887a-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="0887a-120">Office 365 マネージメント アクティビティ API を通じて利用できる特定の種類のデータについて学習するには、共通スキーマと[Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)用 Defender と脅威の調査と対応スキーマの概要を説明します。 [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)</span><span class="sxs-lookup"><span data-stu-id="0887a-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="0887a-121">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="0887a-121">See also</span></span>

- [<span data-ttu-id="0887a-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0887a-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="0887a-123">Microsoft 365 Defender での自動調査と対応</span><span class="sxs-lookup"><span data-stu-id="0887a-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
