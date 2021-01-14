---
title: Microsoft 365 Defender でインシデント通知を取得する
description: Microsoft 365 Defender でインシデントのメール通知を取得するルールを作成する方法について説明します
keywords: インシデント, 電子メール, 電子メール通知, 構成, ユーザー, メールボックス, 電子メール, インシデント
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848893"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="bd7eb-104">電子メールでインシデント通知を取得する</span><span class="sxs-lookup"><span data-stu-id="bd7eb-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bd7eb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bd7eb-105">**Applies to:**</span></span>
- <span data-ttu-id="bd7eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd7eb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bd7eb-107">Microsoft 365 Defender をセットアップして、新しいインシデントや既存のインシデントに対する新しい更新が発生した場合に電子メールで通知することができます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="bd7eb-108">インシデントの重大度またはデバイス グループに基づいて通知を取得できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="bd7eb-109">インシデントごとに最初の更新時にのみ通知を受け取るオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="bd7eb-110">電子メール通知で受信者を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="bd7eb-111">新しく追加された受信者は、追加後にインシデントに関する通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="bd7eb-112">電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="bd7eb-113">インシデントに直接移動して、調査を直ちに開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="bd7eb-114">インシデントの調査の詳細については [、「Microsoft 365 Defender でのインシデントの調査」を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="bd7eb-115">電子メール通知の設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="bd7eb-116">基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="bd7eb-117">同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合、作成、編集、削除、および受信できるのは、管理が許可されているデバイス グループに基づく通知のみです。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="bd7eb-118">インシデント通知のルールを作成する</span><span class="sxs-lookup"><span data-stu-id="bd7eb-118">Create rules for incident notifications</span></span>

<span data-ttu-id="bd7eb-119">インシデントの最初の電子メール通知を設定するには、新しいルールを作成し、電子メール通知の設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="bd7eb-120">ナビゲーション ウィンドウで、[設定インシデントの電子 **メール**  >  **通知] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="bd7eb-121">[アイテム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-121">Select **Add item**.</span></span>
3. <span data-ttu-id="bd7eb-122">ルールに名前を付け **、Description** を **指定します**。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![インシデント電子メールの通知のルール ウィンドウを作成する](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="bd7eb-124">[ **次へ] を** 選択して[通知の設定 **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="bd7eb-125">ここでは、次の項目を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-125">Here you can specify:</span></span>
    - <span data-ttu-id="bd7eb-126">**アラートの重要度** - インシデント通知をトリガーするアラートの重要度を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="bd7eb-127">たとえば、重大度の高いインシデントについてのみ通知する場合は、[高] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="bd7eb-128">**デバイス グループのスコープ** - このドロップダウンには、ユーザーがアクセスできるすべてのデバイス グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="bd7eb-129">インシデント通知ルールを作成するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="bd7eb-130">**インシデントごとに最初に** 発生した場合にのみ通知する - このオプションを選択すると、他の選択内容と一致する最初のアラートにのみ電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="bd7eb-131">その後の更新やインシデントに関連するアラートでは、通知はトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="bd7eb-132">**組織名を含** める - 顧客名が電子メール通知に表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="bd7eb-133">**テナント固有のポータル リンクを含める** - 特定のテナントへのアクセスを許可するテナント ID のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![インシデントメールの通知設定ウィンドウ](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="bd7eb-135">[ **次へ]** を選択して [ **受信者] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="bd7eb-136">ここでは、インシデントの電子メール通知を受信する電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="bd7eb-137">すべてのメール **アドレスを入力した後、[受信者の** 追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-137">Select **Add a recipient** after typing every email address.</span></span>

    ![インシデントメールの通知の [受信者の追加] ウィンドウ](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="bd7eb-139">最後に、[次 **へ]** を選択して **[ルール** の確認] に移動し、新しいルールに関連付けられているすべての設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="bd7eb-140">受信者は、設定に基づいて電子メールでインシデント通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="bd7eb-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd7eb-141">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="bd7eb-141">See also</span></span>
- [<span data-ttu-id="bd7eb-142">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="bd7eb-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="bd7eb-143">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="bd7eb-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="bd7eb-144">Microsoft 365 Defender でのインシデントの調査</span><span class="sxs-lookup"><span data-stu-id="bd7eb-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

