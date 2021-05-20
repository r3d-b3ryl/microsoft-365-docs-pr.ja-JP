---
title: Microsoft Defender ウイルス対策通知の構成
description: エンドポイントで標準通知と追加Microsoft Defender ウイルス対策通知の両方を構成およびカスタマイズする方法について説明します。
keywords: 通知, 擁護者, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572347"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="510e0-104">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="510e0-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="510e0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="510e0-105">**Applies to:**</span></span>

- [<span data-ttu-id="510e0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="510e0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="510e0-107">Windows 10では、マルウェアの検出と修復に関するアプリケーション通知がより堅牢で、一貫性があり、簡潔になります。</span><span class="sxs-lookup"><span data-stu-id="510e0-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="510e0-108">手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="510e0-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="510e0-109">これらの通知は **通知センター** にも表示され、スキャンと脅威検出の概要は一定の間隔で表示されます。</span><span class="sxs-lookup"><span data-stu-id="510e0-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="510e0-110">また、再起動の通知や脅威が検出および修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="510e0-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="510e0-111">エンドポイントに表示される追加の通知を構成する</span><span class="sxs-lookup"><span data-stu-id="510e0-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="510e0-112">最新の脅威検出の概要などの追加の通知の表示は[、Windows セキュリティ アプリ](microsoft-defender-security-center-antivirus.md)とグループ ポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="510e0-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="510e0-113">Windows 10 バージョン 1607 では、この機能は **拡張通知** と呼ばれ  >  **、Windows 設定 Update & セキュリティ**  >  **Windows Defender** で構成できます。</span><span class="sxs-lookup"><span data-stu-id="510e0-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="510e0-114">すべてのバージョンのWindows 10のグループ ポリシー設定では、**拡張通知** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="510e0-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="510e0-115">追加の通知を無効にしても、脅威の検出や修復のアラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="510e0-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="510e0-116">**Windows セキュリティ アプリを使用して、追加の通知を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="510e0-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="510e0-117">タスク バーの盾アイコンをクリックするか、または [**セキュリティ**] の [スタート] メニューを検索して、Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="510e0-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="510e0-118">[**ウイルス&脅威対策** タイル(または左側のメニュー バーの盾アイコン)を選択し、[**ウイルス&脅威対策の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="510e0-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="510e0-119">[ **通知** ] セクションまでスクロールし、[ **通知設定の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="510e0-120">スイッチを **[オフ]** または **[オン] に** スライドして、追加の通知を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="510e0-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="510e0-121">**グループ ポリシーを使用して、追加の通知を無効にする:**</span><span class="sxs-lookup"><span data-stu-id="510e0-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="510e0-122">グループ ポリシー管理コンピュータで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして 、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="510e0-123">グループ **ポリシー管理エディタ** で、[ **コンピュータの構成]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="510e0-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="510e0-124">[ **管理用テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="510e0-125">ツリーを展開して **コンポーネントをWindows> Microsoft Defender ウイルス対策 >レポート** を作成します。</span><span class="sxs-lookup"><span data-stu-id="510e0-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="510e0-126">[ **拡張通知をオフにする** ] をダブルクリックし、オプションを **[有効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="510e0-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="510e0-127">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-127">Click **OK**.</span></span> <span data-ttu-id="510e0-128">これにより、追加の通知が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="510e0-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="510e0-129">エンドポイントでの標準通知の構成</span><span class="sxs-lookup"><span data-stu-id="510e0-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="510e0-130">グループ ポリシーを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="510e0-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="510e0-131">ユーザーがアクションを実行する必要がある場合にエンドポイントに追加のカスタマイズテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="510e0-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="510e0-132">エンドポイントのすべての通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="510e0-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="510e0-133">エンドポイントでの再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="510e0-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="510e0-134">通知を非表示にすると、Microsoft Defender ウイルス対策インターフェイス全体を非表示にできない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="510e0-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="510e0-135">詳細については[、「Microsoft Defender ウイルス対策ユーザー インターフェイスをユーザーが表示したり、操作したりできないように](prevent-end-user-interaction-microsoft-defender-antivirus.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="510e0-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="510e0-136">通知を非表示にするのは、ポリシーが展開されているエンドポイントでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="510e0-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="510e0-137">実行する必要があるアクションに関連する通知 (再起動など) は[、Microsoft エンドポイント マネージャー Endpoint Protection監視ダッシュボードとレポート](/configmgr/protect/deploy-use/monitor-endpoint-protection)に表示されます。</span><span class="sxs-lookup"><span data-stu-id="510e0-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="510e0-138">ユーザーが自分のコンピューターに表示される通知にカスタム連絡先情報を追加する手順については、「[組織のWindows セキュリティアプリをカスタマイズ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="510e0-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="510e0-139">**グループ ポリシーを使用して通知を非表示にする:**</span><span class="sxs-lookup"><span data-stu-id="510e0-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="510e0-140">グループ ポリシー管理コンピュータで、グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックして、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="510e0-141">グループ **ポリシー管理エディタ** で[ **コンピュータの構成]** に移動し、[ **管理用テンプレート**]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="510e0-142">ツリーを展開して **、クライアント インターフェイス> Microsoft Defender ウイルス対策 >コンポーネントをWindows** します。</span><span class="sxs-lookup"><span data-stu-id="510e0-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="510e0-143">[ **すべての通知を抑制** する] をダブルクリックし、オプションを **[有効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="510e0-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="510e0-144">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-144">Click **OK**.</span></span> <span data-ttu-id="510e0-145">これにより、追加の通知が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="510e0-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="510e0-146">**グループ ポリシーを使用して再起動通知を非表示にする:**</span><span class="sxs-lookup"><span data-stu-id="510e0-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="510e0-147">グループ ポリシー管理コンピュータで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして 、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="510e0-148">グループ **ポリシー管理エディタ** で、[ **コンピュータの構成]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="510e0-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="510e0-149">[ **管理用テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="510e0-150">ツリーを展開して **、クライアント インターフェイス> Microsoft Defender ウイルス対策 >コンポーネントをWindows** します。</span><span class="sxs-lookup"><span data-stu-id="510e0-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="510e0-151">[ **再起動通知を抑制する** ] をダブルクリックし、オプションを **[有効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="510e0-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="510e0-152">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="510e0-152">Click **OK**.</span></span> <span data-ttu-id="510e0-153">これにより、追加の通知が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="510e0-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="510e0-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="510e0-154">Related topics</span></span>

- [<span data-ttu-id="510e0-155">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="510e0-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="510e0-156">Microsoft Defender ウイルス対策とのエンド ユーザーの対話を構成する</span><span class="sxs-lookup"><span data-stu-id="510e0-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
