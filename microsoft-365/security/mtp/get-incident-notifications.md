---
title: Microsoft 365 Defender でインシデント通知を取得する
description: Microsoft 365 Defender でインシデントのメール通知を取得するルールを作成する方法について説明します。
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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668321"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="45d25-104">電子メールでインシデント通知を取得する</span><span class="sxs-lookup"><span data-stu-id="45d25-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="45d25-105">インシデント機能の電子メール通知は、現在パブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="45d25-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="45d25-106">この機能に関する一部の情報は、商用提供前に変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="45d25-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="45d25-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="45d25-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="45d25-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45d25-108">**Applies to:**</span></span>
- <span data-ttu-id="45d25-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45d25-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="45d25-110">Microsoft 365 Defender は、新しいインシデントや既存のインシデントに対する新しい更新が発生した場合に電子メールで通知する設定を行います。</span><span class="sxs-lookup"><span data-stu-id="45d25-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="45d25-111">インシデントの重大度またはデバイス グループに基づいて通知を取得できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="45d25-112">インシデントごとに最初の更新時にのみ通知を受け取るオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="45d25-113">電子メール通知で受信者を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="45d25-114">新しく追加された受信者は、インシデントが追加された後に通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="45d25-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="45d25-115">電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45d25-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="45d25-116">インシデントに直接移動して、調査を直ちに開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="45d25-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="45d25-117">インシデントの調査の詳細については [、「Microsoft 365 Defender でのインシデントの調査」を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)。</span><span class="sxs-lookup"><span data-stu-id="45d25-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="45d25-118">電子メール通知の設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="45d25-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="45d25-119">基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="45d25-120">同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づく通知のみを作成、編集、削除、および受信できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="45d25-121">インシデント通知のルールを作成する</span><span class="sxs-lookup"><span data-stu-id="45d25-121">Create rules for incident notifications</span></span>

<span data-ttu-id="45d25-122">インシデントの最初の電子メール通知を設定するには、新しいルールを作成し、電子メール通知の設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="45d25-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="45d25-123">ナビゲーション ウィンドウで、[設定インシデントの電子 **メール**  >  **通知] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="45d25-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="45d25-124">[アイテムの **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="45d25-124">Select **Add item**.</span></span>
3. <span data-ttu-id="45d25-125">ルールに名前を付け **、Description** を **指定します**。</span><span class="sxs-lookup"><span data-stu-id="45d25-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![インシデント電子メールの通知のルールウィンドウを作成する](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="45d25-127">[ **次へ] を** 選択して[通知の設定 **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="45d25-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="45d25-128">ここでは、次の項目を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-128">Here you can specify:</span></span>
    - <span data-ttu-id="45d25-129">**アラートの重大度** - インシデント通知をトリガーするアラートの重要度を選択します。</span><span class="sxs-lookup"><span data-stu-id="45d25-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="45d25-130">たとえば、重大度の高いインシデントについてのみ通知する場合は、[高] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45d25-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="45d25-131">**デバイス グループのスコープ** - このドロップダウンには、ユーザーがアクセスできるすべてのデバイス グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45d25-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="45d25-132">インシデント通知ルールを作成するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="45d25-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="45d25-133">**インシデントごとに最初に** 発生した場合にのみ通知する - このオプションを選択すると、他の選択内容と一致する最初のアラートにのみ電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="45d25-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="45d25-134">その後の更新またはインシデントに関連するアラートでは、通知はトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="45d25-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="45d25-135">**組織名を含** める - 顧客名が電子メール通知に表示されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="45d25-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="45d25-136">**テナント固有のポータル リンクを含める** - 特定のテナントへのアクセスを許可するテナント ID のリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="45d25-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![インシデントメールの通知設定ウィンドウ](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="45d25-138">[ **次へ]** を選択して [ **受信者] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="45d25-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="45d25-139">ここでは、インシデントの電子メール通知を受信する電子メール アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="45d25-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="45d25-140">すべての **メール アドレスを入力した後、[受信者の** 追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45d25-140">Select **Add a recipient** after typing every email address.</span></span>

    ![インシデントメールの通知の [受信者の追加] ウィンドウ](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="45d25-142">最後に、[次 **へ]** を選択して **[ルール** の確認] に移動し、新しいルールに関連付けられているすべての設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="45d25-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="45d25-143">受信者は、設定に基づいて電子メールでインシデント通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="45d25-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="45d25-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="45d25-144">See also</span></span>
- [<span data-ttu-id="45d25-145">Microsoft 365 Defender のインシデントの概要</span><span class="sxs-lookup"><span data-stu-id="45d25-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="45d25-146">Microsoft 365 Defender でのインシデントの優先順位付け</span><span class="sxs-lookup"><span data-stu-id="45d25-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="45d25-147">Microsoft 365 Defender でのインシデントの調査</span><span class="sxs-lookup"><span data-stu-id="45d25-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

