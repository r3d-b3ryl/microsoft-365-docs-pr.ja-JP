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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: ユーザーが会議や予定の予定表を外部ユーザーと共有する方法について学習します。
ms.openlocfilehash: 8204dc025f843953af13cba58fa0cf2e4d76de45
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760056"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="489ab-103">予定表を外部ユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="489ab-103">Share calendars with external users</span></span>

<span data-ttu-id="489ab-104">ユーザーが組織外のユーザーとの会議をスケジュールする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="489ab-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="489ab-105">一般的な会議時間を見つけるプロセスを簡素化するために、Microsoft 365 を使用すると、これらのユーザーが予定表を使用できます。</span><span class="sxs-lookup"><span data-stu-id="489ab-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="489ab-106">これらは、組織内のユーザーの空き時間情報を表示する必要があるが、Microsoft 365 組織のユーザー アカウントを持っている必要があるユーザーです。</span><span class="sxs-lookup"><span data-stu-id="489ab-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="489ab-107">Microsoft 365 管理センターでは、組織内のすべてのユーザーに対して予定表の共有を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="489ab-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="489ab-108">共有を有効にすると、ユーザーは Outlook Web App を使用して組織内外のユーザーと予定表を共有できます。</span><span class="sxs-lookup"><span data-stu-id="489ab-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="489ab-109">組織内のユーザーは、自分の予定表と一緒に共有の予定表を表示できます。</span><span class="sxs-lookup"><span data-stu-id="489ab-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="489ab-110">組織外のユーザーには、予定表の表示に使用できる URL が送信されます。</span><span class="sxs-lookup"><span data-stu-id="489ab-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="489ab-111">組織内のユーザーは、共有する時間と共有する量を決定します。</span><span class="sxs-lookup"><span data-stu-id="489ab-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="489ab-112">Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="489ab-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="489ab-113">これはフェデレーションと呼ばれるので、ソフトウェアの最小要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="489ab-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="489ab-114">詳細については、「[共有](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="489ab-114">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="489ab-115">Microsoft 365 管理センターを使用して予定表の共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="489ab-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="489ab-116">管理センターで、[設定組織の設定 **]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="489ab-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="489ab-117">[サービス] **タブで** 、[予定表] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="489ab-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="489ab-118">[予定表 **] ページ** で、Microsoft 365 または Exchange を持つ組織外のユーザーと予定表を共有するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="489ab-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="489ab-119">匿名ユーザー (資格情報のないユーザー) が電子メールの招待状を介して予定表にアクセスできるかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="489ab-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="489ab-120">ユーザーが利用できる予定表情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="489ab-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="489ab-121">すべての情報を許可するか、時間のみ、または時間、件名、場所にのみ制限できます。</span><span class="sxs-lookup"><span data-stu-id="489ab-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="489ab-122">予定表にアクセスできるようにユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="489ab-122">Invite people to access calendars</span></span>

<span data-ttu-id="489ab-123">共有を有効にすると、予定表の所有者は特定のユーザーに招待を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="489ab-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="489ab-124">手順については、「[予定表を共有する](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="489ab-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>