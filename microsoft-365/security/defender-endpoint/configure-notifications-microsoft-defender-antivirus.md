---
title: 通知Microsoft Defender ウイルス対策構成する
description: エンドポイントの標準通知と他の通知の両方を構成Microsoft Defender ウイルス対策する方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985410"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="4239e-104">エンドポイントMicrosoft Defender ウイルス対策通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4239e-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="4239e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4239e-105">**Applies to:**</span></span>

- [<span data-ttu-id="4239e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4239e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4239e-107">このWindows 10、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。</span><span class="sxs-lookup"><span data-stu-id="4239e-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="4239e-108">Microsoft Defender ウイルス対策が完了し、脅威が検出されると、エンドポイントに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4239e-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="4239e-109">通知は、スケジュールされたスキャンと手動でトリガーされたスキャンの両方に従います。</span><span class="sxs-lookup"><span data-stu-id="4239e-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="4239e-110">これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4239e-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="4239e-111">組織のセキュリティ チームの一員である場合は、システムの再起動を求める通知や脅威が検出され修復されたという通知など、エンドポイントへの通知の表示方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4239e-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="4239e-112">グループ ポリシーまたはアプリを使用してウイルス対策Windows セキュリティ構成する</span><span class="sxs-lookup"><span data-stu-id="4239e-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="4239e-113">最近の脅威検出の概要など、追加の通知の表示は、Windows セキュリティグループ ポリシー[で](microsoft-defender-security-center-antivirus.md)構成できます。</span><span class="sxs-lookup"><span data-stu-id="4239e-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="4239e-114">このWindows 10バージョン 1607 では、この機能は拡張通知と呼ばされ、[更新プログラムの更新] Windows 設定で&  >  **構成**  >  Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="4239e-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="4239e-115">すべてのバージョンのグループ ポリシー設定で、Windows 10機能は拡張通知と **呼ばれる。**</span><span class="sxs-lookup"><span data-stu-id="4239e-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="4239e-116">グループ ポリシーを使用して追加の通知を無効にする</span><span class="sxs-lookup"><span data-stu-id="4239e-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="4239e-117">グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。</span><span class="sxs-lookup"><span data-stu-id="4239e-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4239e-118">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="4239e-119">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="4239e-120">[管理 **用テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="4239e-121">ツリーを展開して **、reporting**Windowsコンポーネント\*\*  >  **Microsoft Defender ウイルス対策>** 展開します。</span><span class="sxs-lookup"><span data-stu-id="4239e-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="4239e-122">[拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="4239e-123">次に **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4239e-123">Then select **OK**.</span></span> <span data-ttu-id="4239e-124">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="4239e-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4239e-125">追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="4239e-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="4239e-126">アプリを使用Windows セキュリティ通知を無効にする</span><span class="sxs-lookup"><span data-stu-id="4239e-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="4239e-127">タスク バーのWindows セキュリティをクリックするか、スタート メニューの [セキュリティ] を検索して、アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="4239e-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="4239e-128">[ **ウイルス&保護** ] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] & **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="4239e-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="4239e-129">[通知] セクションまで **スクロールし** 、[通知設定の **変更] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="4239e-130">スイッチを Off または **On にスライド\*\*\*\*して**、追加の通知を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="4239e-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4239e-131">追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="4239e-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="4239e-132">グループ ポリシーを使用してエンドポイントの標準通知を構成する</span><span class="sxs-lookup"><span data-stu-id="4239e-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="4239e-133">グループ ポリシーを使用すると、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4239e-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="4239e-134">ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="4239e-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="4239e-135">エンドポイントのすべての通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="4239e-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="4239e-136">エンドポイントで再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="4239e-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="4239e-137">通知の非表示は、インターフェイス全体を非表示にできない状況Microsoft Defender ウイルス対策があります。</span><span class="sxs-lookup"><span data-stu-id="4239e-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="4239e-138">詳細[については、「ユーザーがユーザー](prevent-end-user-interaction-microsoft-defender-antivirus.md)インターフェイスを表示または操作Microsoft Defender ウイルス対策する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4239e-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="4239e-139">通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="4239e-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="4239e-140">実行する必要があるアクション (再起動など) に関連する通知は、監視ダッシュボードとレポートMicrosoft エンドポイント マネージャー Endpoint Protection[表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="4239e-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="4239e-141">エンドポイント通知にカスタム連絡先情報を追加するには、「組織のアプリ[Windows セキュリティカスタマイズする」を参照してください](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="4239e-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="4239e-142">グループ ポリシーを使用して通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="4239e-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="4239e-143">グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。</span><span class="sxs-lookup"><span data-stu-id="4239e-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4239e-144">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="4239e-145">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動し、[** 管理用テンプレート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="4239e-146">ツリーを展開して **、WindowsインターフェイスMicrosoft Defender ウイルス対策**  >    >  **コンポーネントに展開します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="4239e-147">[すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="4239e-148">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4239e-148">Select **OK**.</span></span> <span data-ttu-id="4239e-149">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="4239e-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="4239e-150">グループ ポリシーを使用して再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="4239e-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="4239e-151">グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。</span><span class="sxs-lookup"><span data-stu-id="4239e-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4239e-152">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="4239e-153">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="4239e-154">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4239e-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="4239e-155">ツリーを展開して **、WindowsインターフェイスMicrosoft Defender ウイルス対策**  >    >  **コンポーネントに展開します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="4239e-156">[再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="4239e-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="4239e-157">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4239e-157">Select **OK**.</span></span> <span data-ttu-id="4239e-158">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="4239e-158">This will prevent additional notifications from appearing.</span></span>

