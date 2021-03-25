---
title: Microsoft Defender for Endpoint でアラート通知を構成する
description: Microsoft Defender for Endpoint を使用すると、重大度や他の条件に基づいて、セキュリティアラートの電子メール通知設定を構成できます。
keywords: 電子メール通知、アラート通知の構成、Microsoft Defender atp 通知、Microsoft Defender atp アラート、Windows 10 enterprise、Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d8b68e6b6dc42de5730aa634386406d4762b1fa2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163685"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a><span data-ttu-id="d33b5-104">Microsoft Defender ATP でアラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="d33b5-104">Configure alert notifications in Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d33b5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d33b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="d33b5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d33b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d33b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d33b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d33b5-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d33b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d33b5-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d33b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="d33b5-110">Defender for Endpoint を構成して、新しい通知のために指定した受信者に電子メール通知を送信できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="d33b5-111">この機能を使用すると、直ちに通知を受け取り、重大度に基づいてアラートに基づいて行動できる個人のグループを識別できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="d33b5-112">[セキュリティ設定の管理] 権限を持つユーザーだけが電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="d33b5-113">基本的なアクセス許可管理の使用を選択した場合、セキュリティ管理者またはグローバル管理者の役割を持つユーザーは、電子メール通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="d33b5-114">通知をトリガーするアラートの重大度レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="d33b5-115">電子メール通知の受信者を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="d33b5-116">新しい受信者は、追加後に発生したアラートに関する通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="d33b5-116">New recipients get notified about alerts encountered after they are added.</span></span> <span data-ttu-id="d33b5-117">アラートの詳細については、「アラート キューの [表示と整理」を参照してください](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="d33b5-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="d33b5-118">役割ベースのアクセス制御 (RBAC) を使用している場合、受信者は通知ルールで構成されたデバイス グループに基づく通知のみを受信します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="d33b5-119">適切なアクセス許可を持つユーザーは、デバイス グループ管理スコープに限定された通知のみを作成、編集、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="d33b5-120">グローバル管理者ロールに割り当てられたユーザーだけが、すべてのデバイス グループに対して構成されている通知ルールを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="d33b5-121">電子メール通知には、アラートに関する基本情報と、さらに調査を行うポータルへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d33b5-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="d33b5-122">アラート通知のルールを作成する</span><span class="sxs-lookup"><span data-stu-id="d33b5-122">Create rules for alert notifications</span></span>
<span data-ttu-id="d33b5-123">電子メール通知を送信するデバイスとアラートの重大度と通知受信者を決定するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="d33b5-124">ナビゲーション ウィンドウで、[設定アラート通知 **]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-124">In the navigation pane, select **Settings** > **Alert notifications**.</span></span>

2. <span data-ttu-id="d33b5-125">[通知 **ルールの追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-125">Click **Add notification rule**.</span></span>

3. <span data-ttu-id="d33b5-126">[全般] 情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-126">Specify the General information:</span></span>
    - <span data-ttu-id="d33b5-127">**ルール名** - 通知ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="d33b5-128">**[組織名を含** める] - 電子メール通知に表示される顧客名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="d33b5-129">**[テナント固有のポータル リンクを含める** ] - 特定のテナントへのアクセスを許可するテナント ID を含むリンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="d33b5-130">**[デバイス情報を含** める] - 電子メール通知本文にデバイス名を含める。</span><span class="sxs-lookup"><span data-stu-id="d33b5-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="d33b5-131">この情報は、Defender for Endpoint データで選択した地理的な場所ではない受信者メール サーバーによって処理される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d33b5-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="d33b5-132">**[デバイス** ] - すべてのデバイス (グローバル管理者の役割のみ) または選択したデバイス グループの通知を受信者に通知するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="d33b5-133">詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="d33b5-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="d33b5-134">**アラートの重大度** - アラートの重大度レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="d33b5-135">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d33b5-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="d33b5-136">受信者のメール アドレスを入力し、[受信者の追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="d33b5-137">複数のメール アドレスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d33b5-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="d33b5-138">[テストメールの送信] を選択して、電子メール受信者が電子メール通知を **受信できると確認します**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-138">Check that email recipients are able to receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="d33b5-139">[通知 **ルールの保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="d33b5-140">通知ルールの編集</span><span class="sxs-lookup"><span data-stu-id="d33b5-140">Edit a notification rule</span></span>
1. <span data-ttu-id="d33b5-141">編集する通知ルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="d33b5-142">[全般] タブと [受信者] タブ情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="d33b5-143">[通知 **ルールの保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d33b5-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="d33b5-144">通知ルールの削除</span><span class="sxs-lookup"><span data-stu-id="d33b5-144">Delete notification rule</span></span>

1. <span data-ttu-id="d33b5-145">削除する通知ルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="d33b5-146">**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d33b5-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="d33b5-147">アラートの電子メール通知のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d33b5-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="d33b5-148">このセクションでは、アラートに電子メール通知を使用するときに発生する可能性があるさまざまな問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="d33b5-149">**問題:** 対象の受信者は、通知を取得していないと報告します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-149">**Problem:** Intended recipients report they are not getting the notifications.</span></span>

<span data-ttu-id="d33b5-150">**ソリューション:** 通知がメール フィルターによってブロックされないのを確認します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-150">**Solution:** Make sure that the notifications are not blocked by email filters:</span></span>

1. <span data-ttu-id="d33b5-151">Defender for Endpoint の電子メール通知が迷惑メール フォルダーに送信されないか確認します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-151">Check that the Defender for Endpoint email notifications are not sent to the Junk Email folder.</span></span> <span data-ttu-id="d33b5-152">[迷惑メールではない] としてマークします。</span><span class="sxs-lookup"><span data-stu-id="d33b5-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="d33b5-153">メール セキュリティ製品が Defender for Endpoint からの電子メール通知をブロックしていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-153">Check that your email security product is not blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="d33b5-154">Defender for Endpoint の電子メール通知をキャッチして移動する可能性がある電子メール アプリケーションルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="d33b5-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d33b5-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="d33b5-155">Related topics</span></span>
- [<span data-ttu-id="d33b5-156">データ保持設定の更新</span><span class="sxs-lookup"><span data-stu-id="d33b5-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="d33b5-157">高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="d33b5-157">Configure advanced features</span></span>](advanced-features.md)