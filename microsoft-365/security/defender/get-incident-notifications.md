---
title: Defender で電子メールでインシデント通知をMicrosoft 365する
description: Defender でインシデントのメール通知を取得するルールを作成するMicrosoft 365する
keywords: インシデント、電子メール、電子メールの通知、構成、ユーザー、メールボックス、電子メール、インシデント、分析、応答
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
ms.openlocfilehash: 2e47b35646a1cd6e1075d80f9ed0550e8e1e819f
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651394"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="f8709-104">電子メールでインシデント通知を取得する</span><span class="sxs-lookup"><span data-stu-id="f8709-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8709-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f8709-105">**Applies to:**</span></span>
- <span data-ttu-id="f8709-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8709-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f8709-107">新しいインシデントやMicrosoft 365に関するメールをスタッフに通知するために、Defender をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="f8709-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="f8709-108">次に基づいて通知を受け取る方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f8709-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="f8709-109">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="f8709-109">Incident severity.</span></span>
- <span data-ttu-id="f8709-110">デバイス グループ。</span><span class="sxs-lookup"><span data-stu-id="f8709-110">Device group.</span></span>
- <span data-ttu-id="f8709-111">インシデントごとの最初の更新のみ。</span><span class="sxs-lookup"><span data-stu-id="f8709-111">Only on the first update per incident.</span></span>

<span data-ttu-id="f8709-112">電子メール通知には、インシデント名、重大度、カテゴリなど、インシデントに関する重要な詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8709-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="f8709-113">インシデントに直接移動し、分析を直に開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8709-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="f8709-114">詳細については、「インシデントの [調査」を参照してください](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="f8709-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="f8709-115">電子メール通知で受信者を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f8709-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="f8709-116">新しい受信者は、インシデントが追加された後に通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="f8709-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="f8709-117">電子メール通知の設定を構成するには、[セキュリティ設定の管理] アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f8709-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="f8709-118">基本的なアクセス許可管理を使用する場合は、セキュリティ管理者またはグローバル管理者の役割を持つユーザーが電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f8709-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="f8709-119">同様に、組織が役割ベースのアクセス制御 (RBAC) を使用している場合は、管理が許可されているデバイス グループに基づいて通知を作成、編集、削除、および受信できます。</span><span class="sxs-lookup"><span data-stu-id="f8709-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="f8709-120">電子メール通知のルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f8709-120">Create a rule for email notifications</span></span>

<span data-ttu-id="f8709-121">次の手順に従って、新しいルールを作成し、電子メール通知設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="f8709-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="f8709-122">ナビゲーション ウィンドウで、[インシデントメール通知]**設定 > Microsoft 365 Defender >を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="f8709-123">[アイテム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-123">Select **Add item**.</span></span>
3. <span data-ttu-id="f8709-124">[基本 **] ページで** 、ルール名と説明を入力し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="f8709-125">[通知の **設定] ページで** 、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="f8709-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="f8709-126">**アラートの重大度** - インシデント通知をトリガーするアラートの重大度を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="f8709-127">たとえば、重大度の高いインシデントのみを通知する場合は、[高] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="f8709-128">**デバイス グループスコープ** - すべてのデバイス グループを指定するか、テナント内のデバイス グループの一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="f8709-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="f8709-129">**インシデントごとに最初に発生した** 場合にのみ通知する - 他の選択内容に一致する最初のアラートにのみ通知を表示する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="f8709-130">インシデントに関連する後の更新やアラートでは、追加の通知は送信されません。</span><span class="sxs-lookup"><span data-stu-id="f8709-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="f8709-131">**[電子メールに組織名を** 含める] - 組織名を電子メール通知に表示する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="f8709-132">**[テナント固有のポータル リンクを含める**] - 特定のテナントにアクセスするために、電子メール通知にテナント ID を含むリンクをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="f8709-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="インシデントメール通知の通知設定":::

5. <span data-ttu-id="f8709-134">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-134">Select **Next**.</span></span> <span data-ttu-id="f8709-135">[受信者 **] ページ** で、インシデント通知を受信する電子メール アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="f8709-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="f8709-136">新しい **メール アドレスを** 入力した後、[追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="f8709-137">通知をテストし、受信者が受信トレイで受信を確認するには、[テストメールの送信 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="f8709-138">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-138">Select **Next**.</span></span> <span data-ttu-id="f8709-139">[ルール **の確認] ページ** で、ルールの設定を確認し、[ルールの作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="f8709-140">受信者は、設定に基づいて電子メールを介してインシデント通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="f8709-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="f8709-141">既存のルールを編集するには、ルールの一覧からルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="f8709-142">ルール名を持つウィンドウで、[ルールの編集] を選択し、[基本]ページ、[通知設定] ページ、および [受信者] ページで変更を **行** います。 </span><span class="sxs-lookup"><span data-stu-id="f8709-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="f8709-143">ルールを削除するには、ルールの一覧からルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8709-143">To delete a rule, select it from the list of rules.</span></span> <span data-ttu-id="f8709-144">ルール名を持つウィンドウで、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f8709-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8709-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8709-145">See also</span></span>
- [<span data-ttu-id="f8709-146">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="f8709-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f8709-147">インシデントの優先度設定</span><span class="sxs-lookup"><span data-stu-id="f8709-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f8709-148">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="f8709-148">Investigate incidents</span></span>](investigate-incidents.md)
