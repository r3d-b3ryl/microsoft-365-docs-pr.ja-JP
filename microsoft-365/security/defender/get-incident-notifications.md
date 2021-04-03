---
title: Microsoft 365 Defender でインシデント通知を取得する
description: Microsoft 365 Defender でインシデントのメール通知を取得するルールを作成する方法について説明します。
keywords: インシデント、電子メール、電子メールの通知、構成、ユーザー、メールボックス、電子メール、インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fec2263599f3ed727d3d9d70023927084eb1c094
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501071"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="9d6fd-104">電子メールでインシデント通知を取得する</span><span class="sxs-lookup"><span data-stu-id="9d6fd-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9d6fd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9d6fd-105">**Applies to:**</span></span>
- <span data-ttu-id="9d6fd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d6fd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9d6fd-107">Microsoft 365 Defender をセットアップして、新しいインシデントや既存のインシデントに対する新しい更新が発生する度に電子メールで通知できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="9d6fd-108">インシデントの重大度またはデバイス グループに基づいて通知を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="9d6fd-109">また、インシデントごとの最初の更新時にのみ通知を受け取る場合も選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="9d6fd-110">電子メール通知で受信者を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="9d6fd-111">新しく追加された受信者は、インシデントが追加された後に通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="9d6fd-112">電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="9d6fd-113">インシデントに直接移動して、調査を直ちから開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="9d6fd-114">インシデントの調査の詳細については [、「Microsoft 365 Defender](./investigate-incidents.md)でのインシデントの調査」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="9d6fd-115">電子メール通知設定を構成するには、「セキュリティ設定の管理」権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="9d6fd-116">基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="9d6fd-117">同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいて通知を作成、編集、削除、および受信できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="9d6fd-118">インシデント通知のルールを作成する</span><span class="sxs-lookup"><span data-stu-id="9d6fd-118">Create rules for incident notifications</span></span>

<span data-ttu-id="9d6fd-119">インシデントの最初の電子メール通知を設定するには、新しいルールを作成し、電子メール通知設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="9d6fd-120">ナビゲーション ウィンドウで、[設定インシデントの電子 **メール**  >  **通知] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="9d6fd-121">[アイテム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-121">Select **Add item**.</span></span>
3. <span data-ttu-id="9d6fd-122">[名前] でルールに名前を **付け、[** 説明] を **指定します**。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![インシデント メールの notifs のルール ウィンドウを作成する](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="9d6fd-124">[次 **へ] を** 選択して、[通知の **設定] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="9d6fd-125">ここでは、以下を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-125">Here you can specify:</span></span>
    - <span data-ttu-id="9d6fd-126">**アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="9d6fd-127">たとえば、重大度の高いインシデントのみを通知する場合は、[高] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="9d6fd-128">**デバイス グループスコープ** - このドロップダウンには、ユーザーがアクセスできるすべてのデバイス グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="9d6fd-129">インシデント通知ルールを作成するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="9d6fd-130">**インシデントごとに最初に発生した** 場合にのみ通知する - このオプションを選択すると、他の選択内容に一致する最初のアラートにのみ電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="9d6fd-131">後でインシデントに関連する更新プログラムまたはアラートは通知をトリガーしない。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="9d6fd-132">**[組織名を含** める] - 顧客名が電子メール通知に表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="9d6fd-133">**[テナント固有のポータル リンクを含める** ] - 特定のテナントへのアクセスを許可するテナント ID を含むリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![インシデントメールの Notif 設定ウィンドウ](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="9d6fd-135">[次 **へ] を** 選択して[ **受信者] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="9d6fd-136">ここでは、インシデントメール通知を受信する電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="9d6fd-137">[すべての **メール アドレスを入力した後に** 受信者を追加する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-137">Select **Add a recipient** after typing every email address.</span></span>

    ![インシデント 電子メールの notifs の [受信者の追加] ウィンドウ](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="9d6fd-139">最後に、[ **次へ] を** 選択して **[ルール** の確認] に移動し、新しいルールに関連付けられているすべての設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="9d6fd-140">受信者は、設定に基づいて電子メールを介してインシデント通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="9d6fd-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d6fd-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d6fd-141">See also</span></span>
- [<span data-ttu-id="9d6fd-142">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="9d6fd-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="9d6fd-143">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="9d6fd-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="9d6fd-144">Microsoft 365 Defender のインシデントを調査する</span><span class="sxs-lookup"><span data-stu-id="9d6fd-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)
