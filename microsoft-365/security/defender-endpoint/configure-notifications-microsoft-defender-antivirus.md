---
title: 通知Microsoft Defender ウイルス対策構成する
description: エンドポイントの標準通知と追加の通知の両方を構成Microsoft Defender ウイルス対策する方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6e11c9394f250a6f3882183224f53954b1390a23
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274630"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="02e54-104">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="02e54-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02e54-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="02e54-105">**Applies to:**</span></span>

- [<span data-ttu-id="02e54-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="02e54-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="02e54-107">このWindows 10、マルウェアの検出と修復に関するアプリケーション通知は、より堅牢で一貫性があり、簡潔です。</span><span class="sxs-lookup"><span data-stu-id="02e54-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="02e54-108">手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e54-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="02e54-109">これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e54-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="02e54-110">また、再起動の通知や脅威が検出され修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="02e54-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="02e54-111">エンドポイントに表示される追加の通知を構成する</span><span class="sxs-lookup"><span data-stu-id="02e54-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="02e54-112">最近の脅威検出の概要など、追加の通知の表示は、Windows セキュリティグループ ポリシー[で](microsoft-defender-security-center-antivirus.md)構成できます。</span><span class="sxs-lookup"><span data-stu-id="02e54-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="02e54-113">このWindows 10バージョン 1607 では、この機能は拡張通知と呼ばされ、[更新プログラムの更新] Windows 設定で&  >  **構成**  >  Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="02e54-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="02e54-114">すべてのバージョンのグループ ポリシー設定で、Windows 10拡張通知 **と呼ばれる。**</span><span class="sxs-lookup"><span data-stu-id="02e54-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02e54-115">追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="02e54-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="02e54-116">**追加の通知Windows セキュリティ無効にするには、次のアプリを使用します。**</span><span class="sxs-lookup"><span data-stu-id="02e54-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="02e54-117">タスク バーのWindows セキュリティをクリックするか、Defender のスタート メニューを検索して、アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="02e54-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="02e54-118">[ウイルス **対策]** &タイル (または左側のメニュー バーのシールド アイコン) をクリックし、[ウイルス対策] &設定ラベルを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="02e54-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![アプリ内のウイルス&設定ラベルのスクリーンショットWindows セキュリティします。](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="02e54-120">[通知] セクションまで **スクロールし** 、[通知設定の **変更] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02e54-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="02e54-121">スイッチを Off または **On にスライド\*\*\*\*して**、追加の通知を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="02e54-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="02e54-122">**グループ ポリシーを使用して、追加の通知を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="02e54-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="02e54-123">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="02e54-124">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="02e54-125">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02e54-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="02e54-126">ツリーを展開して、[**レポートWindowsコンポーネント> Microsoft Defender ウイルス対策 >展開します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="02e54-127">[拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="02e54-128">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e54-128">Click **OK**.</span></span> <span data-ttu-id="02e54-129">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="02e54-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="02e54-130">エンドポイントの標準通知を構成する</span><span class="sxs-lookup"><span data-stu-id="02e54-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="02e54-131">グループ ポリシーを使用すると、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="02e54-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="02e54-132">ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="02e54-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="02e54-133">エンドポイントのすべての通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="02e54-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="02e54-134">エンドポイントで再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="02e54-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="02e54-135">通知の非表示は、インターフェイス全体を非表示にできない状況Microsoft Defender ウイルス対策があります。</span><span class="sxs-lookup"><span data-stu-id="02e54-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="02e54-136">詳細[については、「ユーザーがユーザー](prevent-end-user-interaction-microsoft-defender-antivirus.md)インターフェイスを表示または操作Microsoft Defender ウイルス対策する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e54-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="02e54-137">通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="02e54-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="02e54-138">実行する必要があるアクション (再起動など) に関連する通知は、監視ダッシュボードとレポートMicrosoft エンドポイント マネージャー Endpoint Protection[表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="02e54-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="02e54-139">ユーザー[がコンピューターにWindows セキュリティ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)通知にカスタム連絡先情報を追加する手順については、「組織のアプリをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e54-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="02e54-140">**グループ ポリシーを使用して通知を非表示にする:**</span><span class="sxs-lookup"><span data-stu-id="02e54-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="02e54-141">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="02e54-142">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02e54-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="02e54-143">ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="02e54-144">[すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="02e54-145">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e54-145">Click **OK**.</span></span> <span data-ttu-id="02e54-146">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="02e54-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="02e54-147">**グループ ポリシーを使用して再起動通知を非表示にします。**</span><span class="sxs-lookup"><span data-stu-id="02e54-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="02e54-148">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="02e54-149">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="02e54-150">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02e54-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="02e54-151">ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="02e54-152">[再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="02e54-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="02e54-153">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e54-153">Click **OK**.</span></span> <span data-ttu-id="02e54-154">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="02e54-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02e54-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="02e54-155">Related topics</span></span>

- [<span data-ttu-id="02e54-156">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="02e54-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="02e54-157">ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="02e54-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)