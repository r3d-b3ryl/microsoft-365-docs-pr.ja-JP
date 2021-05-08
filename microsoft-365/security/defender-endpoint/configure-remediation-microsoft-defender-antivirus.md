---
title: Microsoft Defender ウイルス対策検出の修復を構成する
description: 脅威をMicrosoft Defender ウイルス対策するときに実行する必要がある操作と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
keywords: 修復、修正、削除、脅威、検疫、スキャン、復元
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 45886b94ec5ea11f01bfe23092eef4bd72691554
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274510"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a><span data-ttu-id="82eea-104">Microsoft Defender ウイルス対策検出の修復を構成する</span><span class="sxs-lookup"><span data-stu-id="82eea-104">Configure remediation for Microsoft Defender Antivirus detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82eea-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="82eea-105">**Applies to:**</span></span>

- [<span data-ttu-id="82eea-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82eea-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="82eea-107">スキャンMicrosoft Defender ウイルス対策、検出された脅威を修復または削除します。</span><span class="sxs-lookup"><span data-stu-id="82eea-107">When Microsoft Defender Antivirus runs a scan, it attempts to remediate or remove threats that are detected.</span></span> <span data-ttu-id="82eea-108">特定の脅威Microsoft Defender ウイルス対策対処する方法、修復する前に復元ポイントを作成する必要があるかどうか、および脅威を削除する必要がある場合を構成できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-108">You can configure how Microsoft Defender Antivirus should address certain threats, whether a restore point should be created before remediating, and when threats should be removed.</span></span>

<span data-ttu-id="82eea-109">この記事では、グループ ポリシーを使用してこれらの設定を構成する方法について説明しますが、グループ ポリシーとグループ ポリシー [Microsoft Endpoint Configuration Manager使用](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)[Microsoft Intune。](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="82eea-109">This article describes how to configure these settings by using Group Policy, but you can also use [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) and [Microsoft Intune](/intune/device-restrictions-configure).</span></span> 

<span data-ttu-id="82eea-110">PowerShell コマンドレットまたは WMI クラス[ `Set-MpPreference` を使用して](/powershell/module/defender/set-mppreference)[ `MSFT_MpPreference` これらの](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="82eea-110">You can also use the [`Set-MpPreference` PowerShell cmdlet](/powershell/module/defender/set-mppreference) or [`MSFT_MpPreference` WMI class](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) to configure these settings.</span></span>

## <a name="configure-remediation-options"></a><span data-ttu-id="82eea-111">修復オプションの構成</span><span class="sxs-lookup"><span data-stu-id="82eea-111">Configure remediation options</span></span>

1. <span data-ttu-id="82eea-112">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="82eea-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="82eea-113">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82eea-113">In the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="82eea-114">ツリーを展開して、Windows **コンポーネントMicrosoft Defender ウイルス対策。**  >  </span><span class="sxs-lookup"><span data-stu-id="82eea-114">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**.</span></span> 

4. <span data-ttu-id="82eea-115">次の表を使用して場所を選択し、必要に応じてポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="82eea-115">Using the table below, select a location, and then edit the policy as needed.</span></span> 

5. <span data-ttu-id="82eea-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82eea-116">Select **OK**.</span></span>

|<span data-ttu-id="82eea-117">Location</span><span class="sxs-lookup"><span data-stu-id="82eea-117">Location</span></span> | <span data-ttu-id="82eea-118">Setting</span><span class="sxs-lookup"><span data-stu-id="82eea-118">Setting</span></span> | <span data-ttu-id="82eea-119">説明</span><span class="sxs-lookup"><span data-stu-id="82eea-119">Description</span></span> | <span data-ttu-id="82eea-120">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="82eea-120">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="82eea-121">スキャン</span><span class="sxs-lookup"><span data-stu-id="82eea-121">Scan</span></span> | <span data-ttu-id="82eea-122">システム復元ポイントの作成</span><span class="sxs-lookup"><span data-stu-id="82eea-122">Create a system restore point</span></span> | <span data-ttu-id="82eea-123">クリーニングまたはスキャンが試行される前に、システムの復元ポイントが毎日作成されます</span><span class="sxs-lookup"><span data-stu-id="82eea-123">A system restore point will be created each day before cleaning or scanning is attempted</span></span> | <span data-ttu-id="82eea-124">無効</span><span class="sxs-lookup"><span data-stu-id="82eea-124">Disabled</span></span>|
|<span data-ttu-id="82eea-125">スキャン</span><span class="sxs-lookup"><span data-stu-id="82eea-125">Scan</span></span> | <span data-ttu-id="82eea-126">スキャン履歴フォルダーからのアイテムの削除を有効にする</span><span class="sxs-lookup"><span data-stu-id="82eea-126">Turn on removal of items from scan history folder</span></span> | <span data-ttu-id="82eea-127">スキャン履歴に保持する日数を指定する</span><span class="sxs-lookup"><span data-stu-id="82eea-127">Specify how many days items should be kept in the scan history</span></span> | <span data-ttu-id="82eea-128">30 日間</span><span class="sxs-lookup"><span data-stu-id="82eea-128">30 days</span></span> |
|<span data-ttu-id="82eea-129">ルート</span><span class="sxs-lookup"><span data-stu-id="82eea-129">Root</span></span> | <span data-ttu-id="82eea-130">定期的な修復をオフにする</span><span class="sxs-lookup"><span data-stu-id="82eea-130">Turn off routine remediation</span></span> | <span data-ttu-id="82eea-131">脅威を自動的に修復Microsoft Defender ウイルス対策するか、エンドポイント ユーザーに何を行うのかを確認するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-131">You can specify whether Microsoft Defender Antivirus automatically remediates threats, or if it should ask the endpoint user what to do.</span></span> | <span data-ttu-id="82eea-132">無効 (脅威は自動的に修復されます)</span><span class="sxs-lookup"><span data-stu-id="82eea-132">Disabled (threats are remediated automatically)</span></span> |
|<span data-ttu-id="82eea-133">検疫する</span><span class="sxs-lookup"><span data-stu-id="82eea-133">Quarantine</span></span> | <span data-ttu-id="82eea-134">検疫フォルダーからのアイテムの削除を構成する</span><span class="sxs-lookup"><span data-stu-id="82eea-134">Configure removal of items from Quarantine folder</span></span> | <span data-ttu-id="82eea-135">アイテムを削除する前に検疫に保持する日数を指定する</span><span class="sxs-lookup"><span data-stu-id="82eea-135">Specify how many days items should be kept in quarantine before being removed</span></span> | <span data-ttu-id="82eea-136">90 日間</span><span class="sxs-lookup"><span data-stu-id="82eea-136">90 days</span></span> |
|<span data-ttu-id="82eea-137">Threats</span><span class="sxs-lookup"><span data-stu-id="82eea-137">Threats</span></span> | <span data-ttu-id="82eea-138">検出時に既定のアクションを実行しない脅威アラート レベルを指定する</span><span class="sxs-lookup"><span data-stu-id="82eea-138">Specify threat alert levels at which default action should not be taken when detected</span></span> | <span data-ttu-id="82eea-139">ユーザーが検出した脅威Microsoft Defender ウイルス対策レベル (低、中、高、または重大) が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="82eea-139">Every threat that is detected by Microsoft Defender Antivirus is assigned a threat level (low, medium, high, or severe).</span></span> <span data-ttu-id="82eea-140">この設定を使用して、脅威レベルごとにすべての脅威を修復する方法 (検疫、削除、または無視) を定義できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-140">You can use this setting to define how all threats for each of the threat levels should be remediated (quarantined, removed, or ignored)</span></span> | <span data-ttu-id="82eea-141">該当なし</span><span class="sxs-lookup"><span data-stu-id="82eea-141">Not applicable</span></span> |
|<span data-ttu-id="82eea-142">Threats</span><span class="sxs-lookup"><span data-stu-id="82eea-142">Threats</span></span> | <span data-ttu-id="82eea-143">検出時に既定のアクションを実行しない脅威を指定する</span><span class="sxs-lookup"><span data-stu-id="82eea-143">Specify threats upon which default action should not be taken when detected</span></span> | <span data-ttu-id="82eea-144">特定の脅威 (脅威 ID を使用) を修復する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="82eea-144">Specify how specific threats (using their threat ID) should be remediated.</span></span> <span data-ttu-id="82eea-145">特定の脅威を検疫、削除、または無視するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-145">You can specify whether the specific threat should be quarantined, removed, or ignored</span></span> | <span data-ttu-id="82eea-146">該当なし</span><span class="sxs-lookup"><span data-stu-id="82eea-146">Not applicable</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="82eea-147">Microsoft Defender ウイルス対策多くの要因に基づいてファイルを検出し、修復します。</span><span class="sxs-lookup"><span data-stu-id="82eea-147">Microsoft Defender Antivirus detects and remediates files based on many factors.</span></span> <span data-ttu-id="82eea-148">修復を完了するには再起動が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="82eea-148">Sometimes, completing a remediation requires a reboot.</span></span> <span data-ttu-id="82eea-149">検出が後で誤検知と判断された場合でも、すべての追加の修復手順が完了した場合は、再起動を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82eea-149">Even if the detection is later determined to be a false positive, the reboot must be completed to ensure all additional remediation steps have been completed.</span></span>
>
> <span data-ttu-id="82eea-150">誤検知に基Microsoft Defender ウイルス対策ファイルを検疫する必要がある場合は、デバイスの再起動後に検疫からファイルを復元できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-150">If you are certain Microsoft Defender Antivirus quarantined a file based on a false positive, you can restore the file from quarantine after the device reboots.</span></span> <span data-ttu-id="82eea-151">「[検疫済みファイルを復元する」を参照Microsoft Defender ウイルス対策。](restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82eea-151">See [Restore quarantined files in Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> 
> <span data-ttu-id="82eea-152">この問題を今後回避するために、スキャンからファイルを除外できます。</span><span class="sxs-lookup"><span data-stu-id="82eea-152">To avoid this problem in the future, you can exclude files from the scans.</span></span> <span data-ttu-id="82eea-153">詳細については[、「除外の構成と検証」を参照Microsoft Defender ウイルス対策してください](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="82eea-153">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="82eea-154">さらに、修復に[関連する設定については、「](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)修復に必要なスケジュールされた完全Microsoft Defender ウイルス対策スキャンを構成する」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="82eea-154">Also see [Configure remediation-required scheduled full Microsoft Defender Antivirus scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="82eea-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="82eea-155">See also</span></span>

- [<span data-ttu-id="82eea-156">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="82eea-156">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-157">スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="82eea-157">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-158">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="82eea-158">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-159">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="82eea-159">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-160">エンド ユーザー の操作をMicrosoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="82eea-160">Configure end-user Microsoft Defender Antivirus interaction</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-161">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="82eea-161">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eea-162">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="82eea-162">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)