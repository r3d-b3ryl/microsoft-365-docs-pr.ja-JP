---
title: Microsoft Defender ウイルス対策検出の修復を構成する
description: 脅威を検出した場合の Microsoft Defender ウイルス対策の実行方法と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
keywords: 修復、修正、削除、脅威、検疫、スキャン、復元
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765061"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="ccacd-104">Microsoft Defender ウイルス対策検出の修復を構成する</span><span class="sxs-lookup"><span data-stu-id="ccacd-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ccacd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ccacd-105">**Applies to:**</span></span>

- [<span data-ttu-id="ccacd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ccacd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ccacd-107">Microsoft Defender Antivirus がスキャンを実行すると、検出された脅威を修復または削除します。</span><span class="sxs-lookup"><span data-stu-id="ccacd-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="ccacd-108">Microsoft Defender ウイルス対策で特定の脅威に対処する方法、修復する前に復元ポイントを作成する必要があるかどうか、および脅威を削除する必要がある場合を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="ccacd-109">この記事では、グループ ポリシーを使用してこれらの設定を構成する方法について説明しますが [、Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) と Microsoft Intune を [使用することもできます](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="ccacd-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="ccacd-110">PowerShell コマンドレットまたは WMI クラス[ `Set-MpPreference` を使用して](/powershell/module/defender/set-mppreference)[ `MSFT_MpPreference` これらの](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="ccacd-111">修復オプションの構成</span><span class="sxs-lookup"><span data-stu-id="ccacd-111">Configure remediation options</span></span>

1. <span data-ttu-id="ccacd-112">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ccacd-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="ccacd-113">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ccacd-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="ccacd-114">ツリーを Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  **に展開します**。</span><span class="sxs-lookup"><span data-stu-id="ccacd-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="ccacd-115">次の表を使用して場所を選択し、必要に応じてポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="ccacd-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="ccacd-116">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ccacd-116">Select **OK**.</span></span>

|<span data-ttu-id="ccacd-117">場所</span><span class="sxs-lookup"><span data-stu-id="ccacd-117">Location</span></span> | <span data-ttu-id="ccacd-118">設定</span><span class="sxs-lookup"><span data-stu-id="ccacd-118">Setting</span></span> | <span data-ttu-id="ccacd-119">説明</span><span class="sxs-lookup"><span data-stu-id="ccacd-119">Description</span></span> | <span data-ttu-id="ccacd-120">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="ccacd-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ccacd-121">スキャン</span><span class="sxs-lookup"><span data-stu-id="ccacd-121">Scan</span></span> | <span data-ttu-id="ccacd-122">システム復元ポイントの作成</span><span class="sxs-lookup"><span data-stu-id="ccacd-122">Create a system restore point</span></span> | <span data-ttu-id="ccacd-123">クリーニングまたはスキャンが試行される前に、システムの復元ポイントが毎日作成されます</span><span class="sxs-lookup"><span data-stu-id="ccacd-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="ccacd-124">無効</span><span class="sxs-lookup"><span data-stu-id="ccacd-124">Disabled</span></span>|
|<span data-ttu-id="ccacd-125">スキャン</span><span class="sxs-lookup"><span data-stu-id="ccacd-125">Scan</span></span> | <span data-ttu-id="ccacd-126">スキャン履歴フォルダーからのアイテムの削除を有効にする</span><span class="sxs-lookup"><span data-stu-id="ccacd-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="ccacd-127">スキャン履歴に保持する日数を指定する</span><span class="sxs-lookup"><span data-stu-id="ccacd-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="ccacd-128">30 日間</span><span class="sxs-lookup"><span data-stu-id="ccacd-128">30 days</span></span> |
|<span data-ttu-id="ccacd-129">ルート</span><span class="sxs-lookup"><span data-stu-id="ccacd-129">Root</span></span> | <span data-ttu-id="ccacd-130">定期的な修復をオフにする</span><span class="sxs-lookup"><span data-stu-id="ccacd-130">Turn off routine remediation</span></span> | <span data-ttu-id="ccacd-131">Microsoft Defender Antivirus が脅威を自動的に修復するか、エンドポイント ユーザーに何を行うのかを確認するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="ccacd-132">無効 (脅威は自動的に修復されます)</span><span class="sxs-lookup"><span data-stu-id="ccacd-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="ccacd-133">検疫する</span><span class="sxs-lookup"><span data-stu-id="ccacd-133">Quarantine</span></span> | <span data-ttu-id="ccacd-134">検疫フォルダーからのアイテムの削除を構成する</span><span class="sxs-lookup"><span data-stu-id="ccacd-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="ccacd-135">アイテムを削除する前に検疫に保持する日数を指定する</span><span class="sxs-lookup"><span data-stu-id="ccacd-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="ccacd-136">90 日間</span><span class="sxs-lookup"><span data-stu-id="ccacd-136">90 days</span></span> |
|<span data-ttu-id="ccacd-137">Threats</span><span class="sxs-lookup"><span data-stu-id="ccacd-137">Threats</span></span> | <span data-ttu-id="ccacd-138">検出時に既定のアクションを実行しない脅威アラート レベルを指定する</span><span class="sxs-lookup"><span data-stu-id="ccacd-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="ccacd-139">Microsoft Defender ウイルス対策によって検出された脅威には、脅威レベル (低、中、高、または重大) が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="ccacd-140">この設定を使用して、脅威レベルごとにすべての脅威を修復する方法 (検疫、削除、または無視) を定義できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="ccacd-141">該当なし</span><span class="sxs-lookup"><span data-stu-id="ccacd-141">Not applicable</span></span> |
|<span data-ttu-id="ccacd-142">Threats</span><span class="sxs-lookup"><span data-stu-id="ccacd-142">Threats</span></span> | <span data-ttu-id="ccacd-143">検出時に既定のアクションを実行しない脅威を指定する</span><span class="sxs-lookup"><span data-stu-id="ccacd-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="ccacd-144">特定の脅威 (脅威 ID を使用) を修復する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccacd-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="ccacd-145">特定の脅威を検疫、削除、または無視するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="ccacd-146">該当なし</span><span class="sxs-lookup"><span data-stu-id="ccacd-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="ccacd-147">Microsoft Defender ウイルス対策は、多くの要因に基づいてファイルを検出し、修復します。</span><span class="sxs-lookup"><span data-stu-id="ccacd-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="ccacd-148">修復を完了するには再起動が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ccacd-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="ccacd-149">検出が後で誤検知と判断された場合でも、すべての追加の修復手順が完了した場合は、再起動を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccacd-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="ccacd-150">Microsoft Defender ウイルス対策が誤検知に基づいてファイルを検疫した場合は、デバイスの再起動後に検疫からファイルを復元できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="ccacd-151">「Microsoft [Defender ウイルス対策で検疫済みファイルを復元する」を参照してください](restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ccacd-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="ccacd-152">この問題を今後回避するために、スキャンからファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="ccacd-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="ccacd-153">「Microsoft [Defender ウイルス対策スキャンの除外の構成と検証」を参照してください](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ccacd-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="ccacd-154">さらに、修復に [関連する設定については、「修復に必要なスケジュールされた完全な Microsoft Defender ウイルス](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) 対策スキャンを構成する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccacd-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccacd-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccacd-155">See also</span></span>

- [<span data-ttu-id="ccacd-156">Microsoft Defender ウイルス対策スキャン オプションの構成</span><span class="sxs-lookup"><span data-stu-id="ccacd-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-157">スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="ccacd-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-158">Microsoft Defender ウイルス対策スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="ccacd-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-159">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ccacd-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-160">エンド ユーザーの Microsoft Defender ウイルス対策の操作を構成する</span><span class="sxs-lookup"><span data-stu-id="ccacd-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-161">Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する</span><span class="sxs-lookup"><span data-stu-id="ccacd-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ccacd-162">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="ccacd-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)