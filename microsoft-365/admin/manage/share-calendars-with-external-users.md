---
title: 予定表を外部ユーザーと共有する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: ユーザーが組織の内部または外部Microsoft 365 管理センター予定表を共有できるよう、予定表の共有を有効にします。
ms.openlocfilehash: 21dbf12ec495f3a22a45d8a23af807ffd34fef72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392457"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="3cc49-103">予定表を外部ユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="3cc49-103">Share calendars with external users</span></span>

<span data-ttu-id="3cc49-104">ユーザーが組織外のユーザーとの会議をスケジュールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cc49-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="3cc49-105">会議の一般的な時間を見つけるプロセスを簡略化するために、Microsoft 365ユーザーが予定表を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="3cc49-106">これらは、組織内のユーザーの空き時間とビジー時間を表示する必要があるが、組織のユーザー アカウントを持Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="3cc49-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="3cc49-107">組織内のすべてのユーザーに対して予定表の共有を有効にMicrosoft 365 管理センター。</span><span class="sxs-lookup"><span data-stu-id="3cc49-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3cc49-108">共有が有効になると、ユーザーは組織の内部Outlook Web App外部のユーザーと予定表を共有できます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="3cc49-109">組織内のユーザーは、自分の予定表と共に共有予定表を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="3cc49-110">組織外のユーザーには、予定表の表示に使用できる URL が送信されます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="3cc49-111">組織内のユーザーは、共有する時間と共有する量を決定します。</span><span class="sxs-lookup"><span data-stu-id="3cc49-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="3cc49-112">Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc49-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="3cc49-113">これはフェデレーションと呼ばれる、最低限のソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc49-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="3cc49-114">詳細については、「[共有](/exchange/sharing-exchange-2013-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cc49-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="3cc49-115">[予定表] を使用して予定表の共有を有効Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="3cc49-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="3cc49-116">管理センターで、[組織の管理]**設定** \> **に移動設定。**</span><span class="sxs-lookup"><span data-stu-id="3cc49-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="3cc49-117">[サービス] **タブで** 、[予定表] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3cc49-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="3cc49-118">[予定表 **] ページ** で、ユーザーが自分の予定表を組織外のユーザーと共有するかどうかを選択Microsoft 365またはExchange。</span><span class="sxs-lookup"><span data-stu-id="3cc49-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="3cc49-119">匿名ユーザー (資格情報のないユーザー) がメールの招待を介して予定表にアクセスできるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3cc49-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="3cc49-120">ユーザーが利用できる予定表情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cc49-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="3cc49-121">すべての情報を許可するか、時間のみ、または時間、件名、場所にのみ制限できます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="3cc49-122">予定表にアクセスできるようにユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="3cc49-122">Invite people to access calendars</span></span>

<span data-ttu-id="3cc49-123">共有が有効になると、予定表の所有者は特定のユーザーに招待を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="3cc49-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="3cc49-124">手順については、「カレンダーを[共有する」を参照Outlook Web App。](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)</span><span class="sxs-lookup"><span data-stu-id="3cc49-124">For instructions, see [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5).</span></span>

## <a name="related-content"></a><span data-ttu-id="3cc49-125">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="3cc49-125">Related content</span></span>

<span data-ttu-id="3cc49-126">[サイトの外部共有をオンまたはオフにする](/sharepoint/change-external-sharing-site) (記事)</span><span class="sxs-lookup"><span data-stu-id="3cc49-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>\
<span data-ttu-id="3cc49-127">[アプリケーションの概要 (Microsoft 365 管理センター)\](../../business-video/admin-center-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3cc49-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)\</span></span>
<span data-ttu-id="3cc49-128">[メールと予定表の管理](../email/index.yml) (リンク ページ)</span><span class="sxs-lookup"><span data-stu-id="3cc49-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>