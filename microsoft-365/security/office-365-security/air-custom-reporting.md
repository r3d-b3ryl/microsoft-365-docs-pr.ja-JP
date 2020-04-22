---
title: 自動化された調査と対応によるカスタムレポートソリューションの使用
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
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
ms.collection: M365-security-compliance
description: 自動化された調査と応答を、カスタムまたはサードパーティのレポートソリューションと統合する方法について説明します。
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634720"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="c611c-104">カスタムまたはサードパーティのレポートソリューションに管理アクティビティ API を使用する</span><span class="sxs-lookup"><span data-stu-id="c611c-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="c611c-105">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)を使用すると、[自動調査に関する詳細情報](air-view-investigation-results.md)を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c611c-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="c611c-106">ただし、組織によっては、カスタムまたはサードパーティのレポートソリューションを使用する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c611c-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="c611c-107">このようなソリューションで自動調査に関する情報を統合する必要がある組織では、Office 365 Management Activity API を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c611c-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="c611c-108">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="c611c-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="c611c-109">リソース</span><span class="sxs-lookup"><span data-stu-id="c611c-109">Resource</span></span>  |<span data-ttu-id="c611c-110">説明</span><span class="sxs-lookup"><span data-stu-id="c611c-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="c611c-111">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="c611c-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="c611c-112">Office 365 Management Activity API は、Microsoft 365 および Azure Active Directory のアクティビティログから、さまざまなユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c611c-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="c611c-113">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="c611c-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="c611c-114">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Microsoft 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c611c-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="c611c-115">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c611c-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="c611c-116">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c611c-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="c611c-117">Office 365 Management Activity API を使用して、Microsoft 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="c611c-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="c611c-118">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c611c-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="c611c-119">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="c611c-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="c611c-120">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="c611c-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="c611c-121">関連記事</span><span class="sxs-lookup"><span data-stu-id="c611c-121">Related articles</span></span>

- [<span data-ttu-id="c611c-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c611c-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="c611c-123">Microsoft の脅威保護の自動化された調査と対応について説明します。</span><span class="sxs-lookup"><span data-stu-id="c611c-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)