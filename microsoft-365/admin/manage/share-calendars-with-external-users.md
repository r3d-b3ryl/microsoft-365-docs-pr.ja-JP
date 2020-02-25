---
title: 予定表を外部ユーザーと共有する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'ユーザーが会議や予定の外部ユーザーと予定表を共有する方法について説明します。 '
ms.openlocfilehash: 42bce53c3963c41684644d02dab18210f9ed828a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254829"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="a1426-103">予定表を外部ユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="a1426-103">Share calendars with external users</span></span>

<span data-ttu-id="a1426-p101">多くの場合、組織外のユーザーとの会議をスケジュールする必要があります。 互いに合意できる会議時間を見つけるプロセスを簡単にするために、Office 365 では "外部ユーザー" が予定表を表示できるようにすることができます。この外部ユーザーとは、空き時間情報を確認する必要があるが、Office 365 環境のユーザー アカウントを持っていないユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="a1426-p101">It's often necessary to schedule meetings with people outside your organization. To simplify the process of finding mutually agreeable meeting times, Office 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Office 365 environment.</span></span>
  
<span data-ttu-id="a1426-106">予定表の共有はグローバル設定なので、管理者がテナント内のすべてのユーザーに対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1426-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="a1426-107">共有が有効になると、ユーザーは Outlook Web App を使用して、組織内または組織外のユーザーと予定表を共有できます。</span><span class="sxs-lookup"><span data-stu-id="a1426-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="a1426-108">組織内のユーザーは、自分とは別に、共有の予定表を並べて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a1426-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="a1426-109">組織外のユーザーには、予定表の表示に使用できる URL が送信されます。</span><span class="sxs-lookup"><span data-stu-id="a1426-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="a1426-110">ユーザーは、いつ共有するか、どの程度共有するか、どのような場合に自分の予定表を非公開にするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a1426-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1426-p103">Exchange Server 2013 (オンプレミスのソリューション) を使用する組織と予定表を共有する場合は、Exchange 管理者がクラウドとの認証リレーションシップをセットアップする必要があります。これは "フェデレーション" と呼ばれるもので、ソフトウェアの最小要件を満たす必要があります。詳細については、「[共有](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1426-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a1426-114">Microsoft 365 管理センターを使用して予定表の共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="a1426-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a1426-115">管理センターで、 [**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービスとアドイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a1426-115">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span> 
    
  
2. <span data-ttu-id="a1426-116">[**サービス&amp;アドイン**] ページで、[**予定表**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1426-116">On the **Services &amp; add-ins** page, select **Calendar**.</span></span>
  
3. <span data-ttu-id="a1426-117">開いた [**予定表**] ページで、Office 365 または Exchange を使用している組織外のユーザーと予定表を共有するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1426-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Office 365 or Exchange.</span></span>
    
4. <span data-ttu-id="a1426-118">匿名ユーザー (ログオン資格情報を持たないユーザー) が電子メール招待状を使用して予定表にアクセスできるようにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a1426-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="a1426-119">ユーザーが利用できるようにする予定表の情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1426-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="a1426-120">すべての情報を許可することも、時間、件名、場所のみに制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="a1426-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="a1426-121">予定表にアクセスできるようにユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="a1426-121">Invite people to access calendars</span></span>

<span data-ttu-id="a1426-p105">テナントで共有が有効になると、予定表の所有者は特定のユーザーを招待できます。手順については、「[予定表を共有する](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1426-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  

