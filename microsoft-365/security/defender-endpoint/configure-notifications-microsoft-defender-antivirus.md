---
title: 通知Microsoft Defender ウイルス対策構成する
description: エンドポイントの標準通知と追加の通知の両方を構成Microsoft Defender ウイルス対策する方法について説明します。
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926240"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="6f754-104">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6f754-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="6f754-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6f754-105">**Applies to:**</span></span>

- [<span data-ttu-id="6f754-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f754-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6f754-107">このWindows 10、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。</span><span class="sxs-lookup"><span data-stu-id="6f754-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="6f754-108">手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f754-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="6f754-109">これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f754-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="6f754-110">また、再起動の通知や脅威が検出され修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6f754-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="6f754-111">エンドポイントに表示される追加の通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6f754-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="6f754-112">最近の脅威検出の概要など、追加の通知の表示は、Windows セキュリティグループ ポリシー[で](microsoft-defender-security-center-antivirus.md)構成できます。</span><span class="sxs-lookup"><span data-stu-id="6f754-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6f754-113">このWindows 10バージョン 1607 では、この機能は拡張通知と呼ばされ、[更新プログラムの更新] Windows 設定で&  >  **構成**  >  Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="6f754-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="6f754-114">すべてのバージョンのグループ ポリシー設定で、Windows 10拡張通知 **と呼ばれる。**</span><span class="sxs-lookup"><span data-stu-id="6f754-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f754-115">追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="6f754-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="6f754-116">**追加の通知Windows セキュリティ無効にするには、次のアプリを使用します。**</span><span class="sxs-lookup"><span data-stu-id="6f754-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="6f754-117">タスク バーのWindows セキュリティをクリックするか、スタート メニューの [セキュリティ] を検索して、アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="6f754-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="6f754-118">[ **ウイルス&保護** ] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] & **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="6f754-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="6f754-119">[通知] セクションまで **スクロールし** 、[通知設定の **変更] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6f754-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="6f754-120">スイッチを Off または **On にスライド\*\*\*\*して**、追加の通知を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="6f754-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="6f754-121">**グループ ポリシーを使用して、追加の通知を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="6f754-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="6f754-122">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6f754-123">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6f754-124">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6f754-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="6f754-125">ツリーを展開して、[**レポートWindowsコンポーネント> Microsoft Defender ウイルス対策 >展開します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="6f754-126">[拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="6f754-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f754-127">Click **OK**.</span></span> <span data-ttu-id="6f754-128">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f754-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="6f754-129">エンドポイントの標準通知を構成する</span><span class="sxs-lookup"><span data-stu-id="6f754-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="6f754-130">グループ ポリシーを使用すると、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f754-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="6f754-131">ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="6f754-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="6f754-132">エンドポイントのすべての通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="6f754-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="6f754-133">エンドポイントで再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="6f754-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="6f754-134">通知の非表示は、インターフェイス全体を非表示にできない状況Microsoft Defender ウイルス対策があります。</span><span class="sxs-lookup"><span data-stu-id="6f754-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="6f754-135">詳細[については、「ユーザーがユーザー](prevent-end-user-interaction-microsoft-defender-antivirus.md)インターフェイスを表示または操作Microsoft Defender ウイルス対策する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f754-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f754-136">通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="6f754-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="6f754-137">実行する必要があるアクション (再起動など) に関連する通知は、監視ダッシュボードとレポートMicrosoft エンドポイント マネージャー Endpoint Protection[表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="6f754-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="6f754-138">ユーザー[がコンピューターにWindows セキュリティ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)通知にカスタム連絡先情報を追加する手順については、「組織のアプリをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f754-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="6f754-139">**グループ ポリシーを使用して通知を非表示にする:**</span><span class="sxs-lookup"><span data-stu-id="6f754-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="6f754-140">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="6f754-141">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6f754-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="6f754-142">ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="6f754-143">[すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="6f754-144">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f754-144">Click **OK**.</span></span> <span data-ttu-id="6f754-145">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f754-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="6f754-146">**グループ ポリシーを使用して再起動通知を非表示にします。**</span><span class="sxs-lookup"><span data-stu-id="6f754-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="6f754-147">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6f754-148">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6f754-149">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6f754-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="6f754-150">ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="6f754-151">[再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="6f754-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="6f754-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f754-152">Click **OK**.</span></span> <span data-ttu-id="6f754-153">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f754-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6f754-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f754-154">Related topics</span></span>

- [<span data-ttu-id="6f754-155">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="6f754-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="6f754-156">ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6f754-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
