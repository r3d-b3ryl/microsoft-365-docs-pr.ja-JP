---
title: 自動化された調査と対応によるカスタムレポートソリューションの使用
keywords: SIEM、API、AIR、自動赤外線、ATP、自動調査、統合、カスタムレポート
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 自動化された調査と応答を、カスタムまたはサードパーティのレポートソリューションと統合する方法について説明します。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 9bc5de44700b7f1b7207f8fae002adcb55d32841
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446685"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="a788b-104">カスタムまたはサードパーティのレポートソリューションに管理アクティビティ API を使用する</span><span class="sxs-lookup"><span data-stu-id="a788b-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a788b-105">[Office 365 の Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)では、[自動調査に関する詳細情報](air-view-investigation-results.md)を入手できます。</span><span class="sxs-lookup"><span data-stu-id="a788b-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="a788b-106">ただし、組織によっては、カスタムまたはサードパーティのレポートソリューションを使用する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a788b-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="a788b-107">このようなソリューションで自動調査に関する情報を統合する必要がある組織では、Office 365 Management Activity API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a788b-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="a788b-108">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a788b-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="a788b-109">関連情報</span><span class="sxs-lookup"><span data-stu-id="a788b-109">Resource</span></span>|<span data-ttu-id="a788b-110">説明</span><span class="sxs-lookup"><span data-stu-id="a788b-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="a788b-111">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="a788b-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="a788b-112">Office 365 Management Activity API は、Microsoft 365 および Azure Active Directory のアクティビティログから、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a788b-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="a788b-113">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="a788b-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="a788b-114">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a788b-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="a788b-115">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a788b-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="a788b-116">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="a788b-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="a788b-117">Office 365 Management Activity API を使用して、Microsoft 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="a788b-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="a788b-118">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a788b-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="a788b-119">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="a788b-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="a788b-120">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、 [共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) と [OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="a788b-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="a788b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="a788b-121">See also</span></span>

- [<span data-ttu-id="a788b-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a788b-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="a788b-123">Microsoft 365 Defender での自動調査と応答</span><span class="sxs-lookup"><span data-stu-id="a788b-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
