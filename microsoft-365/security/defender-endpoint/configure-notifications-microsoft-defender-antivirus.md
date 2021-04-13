---
title: Microsoft Defender ウイルス対策通知の構成
description: エンドポイントで標準の Microsoft Defender ウイルス対策通知と追加の Microsoft Defender ウイルス対策通知の両方を構成およびカスタマイズする方法について説明します。
keywords: 通知, Defender, ウイルス対策, エンドポイント, 管理, 管理者
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691419"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="cb100-104">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="cb100-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cb100-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="cb100-105">**Applies to:**</span></span>

- [<span data-ttu-id="cb100-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cb100-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cb100-107">Windows 10 では、マルウェアの検出と修復に関するアプリケーション通知の信頼性が高く、一貫性があり、簡潔になります。</span><span class="sxs-lookup"><span data-stu-id="cb100-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="cb100-108">手動でトリガーされ、スケジュールされたスキャンが完了し、脅威が検出されると、エンドポイントに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb100-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="cb100-109">これらの通知は通知センター **にも表示** され、スキャンと脅威検出の概要は一定の間隔で表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb100-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="cb100-110">また、再起動の通知や脅威が検出され修復された場合など、エンドポイントでの標準通知の表示方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb100-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="cb100-111">エンドポイントに表示される追加の通知を構成する</span><span class="sxs-lookup"><span data-stu-id="cb100-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="cb100-112">Windows セキュリティ アプリとグループ ポリシーで、最近の脅威検出の概要などの追加の通知の [表示を構成](microsoft-defender-security-center-antivirus.md) できます。</span><span class="sxs-lookup"><span data-stu-id="cb100-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="cb100-113">Windows 10 バージョン 1607 では、この機能は拡張通知と呼ばされ **、Windows 設定** 更新プログラムの [セキュリティ 更新プログラム&  >  **構成**  >  Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="cb100-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="cb100-114">Windows 10 のすべてのバージョンのグループ ポリシー設定では、拡張通知と **呼ばれる。**</span><span class="sxs-lookup"><span data-stu-id="cb100-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb100-115">追加の通知を無効にすると、脅威の検出や修復アラートなどの重要な通知は無効にされません。</span><span class="sxs-lookup"><span data-stu-id="cb100-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="cb100-116">**Windows セキュリティ アプリを使用して、追加の通知を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="cb100-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="cb100-117">タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="cb100-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="cb100-118">[ウイルス **対策]** &タイル (または左側のメニュー バーのシールド アイコン) をクリックし、[ウイルス対策] &設定ラベルを **クリック** します。</span><span class="sxs-lookup"><span data-stu-id="cb100-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="cb100-120">[通知] セクションまで **スクロールし** 、[通知設定の **変更] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb100-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="cb100-121">スイッチを Off または **On にスライド\*\*\*\*して**、追加の通知を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb100-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="cb100-122">**グループ ポリシーを使用して、追加の通知を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="cb100-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="cb100-123">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="cb100-124">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cb100-125">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb100-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="cb100-126">ツリーを **Microsoft Defender ウイルス対策レポート> Windows コンポーネント>展開します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="cb100-127">[拡張通知を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cb100-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb100-128">Click **OK**.</span></span> <span data-ttu-id="cb100-129">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="cb100-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="cb100-130">エンドポイントの標準通知を構成する</span><span class="sxs-lookup"><span data-stu-id="cb100-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="cb100-131">グループ ポリシーを使用すると、次の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb100-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="cb100-132">ユーザーがアクションを実行する必要がある場合に、エンドポイントに追加のカスタマイズされたテキストを表示する</span><span class="sxs-lookup"><span data-stu-id="cb100-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="cb100-133">エンドポイントのすべての通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="cb100-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="cb100-134">エンドポイントで再起動通知を非表示にする</span><span class="sxs-lookup"><span data-stu-id="cb100-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="cb100-135">通知の非表示は、Microsoft Defender ウイルス対策インターフェイス全体を非表示にできない状況で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cb100-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="cb100-136">詳細 [については、「ユーザーによる Microsoft Defender ウイルス](prevent-end-user-interaction-microsoft-defender-antivirus.md) 対策ユーザー インターフェイスの表示または操作を防止する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb100-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="cb100-137">通知の非表示は、ポリシーが展開されたエンドポイントでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="cb100-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="cb100-138">実行する必要があるアクション (再起動など) に関連する通知は、引き続き Microsoft Endpoint Manager Endpoint Protection の監視 [ダッシュボードとレポートに表示されます](/configmgr/protect/deploy-use/monitor-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="cb100-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="cb100-139">ユーザー [が自分のコンピューターに](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 表示する通知にカスタム連絡先情報を追加する手順については、「組織の Windows セキュリティ アプリをカスタマイズする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb100-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="cb100-140">**グループ ポリシーを使用して通知を非表示にする:**</span><span class="sxs-lookup"><span data-stu-id="cb100-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="cb100-141">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="cb100-142">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb100-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="cb100-143">Microsoft Defender Antivirus > **クライアント インターフェイス>ツリーを展開します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="cb100-144">[すべての通知を **非表示にする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cb100-145">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb100-145">Click **OK**.</span></span> <span data-ttu-id="cb100-146">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="cb100-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="cb100-147">**グループ ポリシーを使用して再起動通知を非表示にします。**</span><span class="sxs-lookup"><span data-stu-id="cb100-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="cb100-148">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="cb100-149">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cb100-150">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb100-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="cb100-151">Microsoft Defender Antivirus > **クライアント インターフェイス>ツリーを展開します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="cb100-152">[再起動通知を **抑制する] をダブルクリックし** 、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="cb100-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cb100-153">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb100-153">Click **OK**.</span></span> <span data-ttu-id="cb100-154">これにより、追加の通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="cb100-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb100-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb100-155">Related topics</span></span>

- [<span data-ttu-id="cb100-156">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="cb100-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="cb100-157">Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する</span><span class="sxs-lookup"><span data-stu-id="cb100-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)