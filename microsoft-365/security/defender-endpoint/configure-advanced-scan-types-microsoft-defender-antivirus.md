---
title: ユーザーのスキャン オプションを構成Microsoft Defender ウイルス対策
description: Microsoft Defender AV を構成して、電子メール ストレージ ファイル、バックアップまたは再解析ポイント、ネットワーク ファイル、アーカイブ されたファイル (.zip ファイルなど) をスキャンできます。
keywords: 高度なスキャン、スキャン、電子メール、アーカイブ、zip、rar、アーカイブ、再解析スキャン
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1efa72d5b8d204b6aec1cef05fe3c8afe1ca82f7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275308"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="dff02-104">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-104">Configure Microsoft Defender Antivirus scanning options</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dff02-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dff02-105">**Applies to:**</span></span>

- [<span data-ttu-id="dff02-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dff02-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="dff02-107">スキャン オプションMicrosoft Intune構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dff02-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="dff02-108">詳細[については、「デバイス制限](/intune/device-restrictions-configure)設定の構成」を参照Microsoft Intune Intune Microsoft Defender ウイルス対策デバイス制限設定Windows 10[デバイス](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)制限設定を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff02-108">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="dff02-109">スキャン オプションMicrosoft エンドポイント マネージャー構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="dff02-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="dff02-110">詳細[については、「マルウェア対策ポリシーを作成](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)して展開する方法: スキャン設定」を参照Microsoft エンドポイント マネージャー (現在のブランチ) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff02-110">See [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="dff02-111">グループ ポリシーを使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-111">Use Group Policy to configure scanning options</span></span>

<span data-ttu-id="dff02-112">次の表で説明するグループ ポリシー設定を構成するには、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dff02-112">To configure the Group Policy settings described in the following table:</span></span>

1. <span data-ttu-id="dff02-113">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dff02-113">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dff02-114">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dff02-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="dff02-115">ツリーを展開して **、Windowsコンポーネント> Microsoft Defender ウイルス対策** 次に、次の表で指定した **場所** を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-115">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="dff02-116">下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-116">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="dff02-117">**[OK] を** クリックし、他の設定を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dff02-117">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="dff02-118">説明</span><span class="sxs-lookup"><span data-stu-id="dff02-118">Description</span></span> | <span data-ttu-id="dff02-119">場所と設定</span><span class="sxs-lookup"><span data-stu-id="dff02-119">Location and setting</span></span> | <span data-ttu-id="dff02-120">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="dff02-120">Default setting (if not configured)</span></span> | <span data-ttu-id="dff02-121">クラスの PowerShell `Set-MpPreference` パラメーターまたは WMI `MSFT_MpPreference` プロパティ</span><span class="sxs-lookup"><span data-stu-id="dff02-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span>
---|---|---|---
<span data-ttu-id="dff02-122">電子メール のスキャン 電子メール [スキャンの制限を参照してください。](#ref1)</span><span class="sxs-lookup"><span data-stu-id="dff02-122">Email scanning See [Email scanning limitations](#ref1)</span></span>| <span data-ttu-id="dff02-123">スキャン>電子メール スキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="dff02-123">Scan > Turn on e-mail scanning</span></span> | <span data-ttu-id="dff02-124">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-124">Disabled</span></span> | `-DisableEmailScanning`
<span data-ttu-id="dff02-125">再 [解析ポイントのスキャン](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="dff02-125">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> | <span data-ttu-id="dff02-126">スキャン >再解析ポイント スキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="dff02-126">Scan > Turn on reparse point scanning</span></span> | <span data-ttu-id="dff02-127">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-127">Disabled</span></span> | <span data-ttu-id="dff02-128">利用不可</span><span class="sxs-lookup"><span data-stu-id="dff02-128">Not available</span></span>
<span data-ttu-id="dff02-129">マップされたネットワーク ドライブをスキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-129">Scan mapped network drives</span></span> | <span data-ttu-id="dff02-130">スキャン > マップされたネットワーク ドライブでフル スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="dff02-130">Scan > Run full scan on mapped network drives</span></span> | <span data-ttu-id="dff02-131">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-131">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`
 <span data-ttu-id="dff02-132">アーカイブ ファイルをスキャンする (.zipファイル.rarします。</span><span class="sxs-lookup"><span data-stu-id="dff02-132">Scan archive files (such as .zip or .rar files).</span></span> <span data-ttu-id="dff02-133">拡張機能 [の除外リストは、](configure-extension-file-exclusions-microsoft-defender-antivirus.md) この設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="dff02-133">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span> | <span data-ttu-id="dff02-134">[スキャン> アーカイブ ファイルのスキャン]</span><span class="sxs-lookup"><span data-stu-id="dff02-134">Scan > Scan archive files</span></span> | <span data-ttu-id="dff02-135">有効</span><span class="sxs-lookup"><span data-stu-id="dff02-135">Enabled</span></span> | `-DisableArchiveScanning`
<span data-ttu-id="dff02-136">ネットワーク上のファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-136">Scan files on the network</span></span> | <span data-ttu-id="dff02-137">ネットワーク ファイル>スキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-137">Scan > Scan network files</span></span> | <span data-ttu-id="dff02-138">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-138">Disabled</span></span> | `-DisableScanningNetworkFiles`
<span data-ttu-id="dff02-139">パックされた実行可能ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-139">Scan packed executables</span></span> | <span data-ttu-id="dff02-140">スキャン>パックされた実行可能ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-140">Scan > Scan packed executables</span></span> | <span data-ttu-id="dff02-141">有効</span><span class="sxs-lookup"><span data-stu-id="dff02-141">Enabled</span></span> | <span data-ttu-id="dff02-142">利用不可</span><span class="sxs-lookup"><span data-stu-id="dff02-142">Not available</span></span>
<span data-ttu-id="dff02-143">フル スキャン時にのみリムーバブル ドライブをスキャンする</span><span class="sxs-lookup"><span data-stu-id="dff02-143">Scan removable drives during full scans only</span></span> | <span data-ttu-id="dff02-144">[スキャン>リムーバブル ドライブのスキャン]</span><span class="sxs-lookup"><span data-stu-id="dff02-144">Scan > Scan removable drives</span></span> | <span data-ttu-id="dff02-145">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-145">Disabled</span></span> | `-DisableRemovableDriveScanning`
<span data-ttu-id="dff02-146">スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する</span><span class="sxs-lookup"><span data-stu-id="dff02-146">Specify the level of subfolders within an archive folder to scan</span></span> | <span data-ttu-id="dff02-147">[スキャン> アーカイブ ファイルをスキャンする最大深度を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-147">Scan > Specify the maximum depth to scan archive files</span></span> | <span data-ttu-id="dff02-148">0</span><span class="sxs-lookup"><span data-stu-id="dff02-148">0</span></span> | <span data-ttu-id="dff02-149">利用不可</span><span class="sxs-lookup"><span data-stu-id="dff02-149">Not available</span></span>
 <span data-ttu-id="dff02-150">スキャン中の CPU の最大負荷 (パーセンテージ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-150">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <span data-ttu-id="dff02-151">注: これはハードリミットではなく、スキャン エンジンが平均してこの最大値を超えないようにするガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="dff02-151">Note: This is not a hard limit but rather a guidance for the scanning engine to not exceed this maximum on average.</span></span> | <span data-ttu-id="dff02-152">スキャン>スキャン中の CPU 使用率の最大割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-152">Scan > Specify the maximum percentage of CPU utilization during a scan</span></span> | <span data-ttu-id="dff02-153">50</span><span class="sxs-lookup"><span data-stu-id="dff02-153">50</span></span> |  `-ScanAvgCPULoadFactor`
 <span data-ttu-id="dff02-154">スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-154">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <span data-ttu-id="dff02-155">既定値の **0** は、制限なしを適用します。</span><span class="sxs-lookup"><span data-stu-id="dff02-155">The default, **0**, applies no limit</span></span> | <span data-ttu-id="dff02-156">スキャン>スキャンするアーカイブ ファイルの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="dff02-156">Scan > Specify the maximum size of archive files to be scanned</span></span> | <span data-ttu-id="dff02-157">制限なし</span><span class="sxs-lookup"><span data-stu-id="dff02-157">No limit</span></span> | <span data-ttu-id="dff02-158">利用不可</span><span class="sxs-lookup"><span data-stu-id="dff02-158">Not available</span></span>
 <span data-ttu-id="dff02-159">スケジュールされたスキャンの CPU 優先度が低い構成</span><span class="sxs-lookup"><span data-stu-id="dff02-159">Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="dff02-160">スキャン >スケジュールされたスキャンの CPU 優先度が低いを構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-160">Scan > Configure low CPU priority for scheduled scans</span></span> | <span data-ttu-id="dff02-161">無効</span><span class="sxs-lookup"><span data-stu-id="dff02-161">Disabled</span></span> | <span data-ttu-id="dff02-162">利用不可</span><span class="sxs-lookup"><span data-stu-id="dff02-162">Not available</span></span>
 
> [!NOTE]
> <span data-ttu-id="dff02-163">リアルタイム保護が有効になっている場合、ファイルにアクセスして実行する前にファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="dff02-163">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="dff02-164">スキャンスコープには、マウントされたリムーバブル メディア上のファイル (USB ドライブなど) を含むすべてのファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dff02-164">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="dff02-165">スキャンを実行するデバイスでリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。</span><span class="sxs-lookup"><span data-stu-id="dff02-165">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="dff02-166">PowerShell を使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-166">Use PowerShell to configure scanning options</span></span>

<span data-ttu-id="dff02-167">[PowerShell コマンドレットMicrosoft Defender ウイルス対策 Defender コマンドレット](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用[](/powershell/module/defender/)して PowerShell を使用する方法の詳細については、「PowerShell コマンドレットと Defender コマンドレットを使用して管理する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="dff02-167">See [Manage Microsoft Defender Antivirus with PowerShell cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="dff02-168">WMI を使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-168">Use WMI to configure scanning options</span></span>

<span data-ttu-id="dff02-169">WMI クラスを使用する場合は[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="dff02-169">For using WMI classes, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a><span data-ttu-id="dff02-170">電子メールのスキャンの制限</span><span class="sxs-lookup"><span data-stu-id="dff02-170">Email scanning limitations</span></span>

<span data-ttu-id="dff02-171">メール スキャンを使用すると、オンデマンドおよびスケジュールされたスキャン中に、Outlook他のメール クライアントで使用される電子メール ファイルをスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="dff02-171">Email scanning enables scanning of  email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="dff02-172">電子メール ファイル内の埋め込みオブジェクト (添付ファイルやアーカイブ ファイルなど) もスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="dff02-172">Embedded objects within an email file (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="dff02-173">次のファイル形式の種類をスキャンして修復できます。</span><span class="sxs-lookup"><span data-stu-id="dff02-173">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="dff02-174">DBX</span><span class="sxs-lookup"><span data-stu-id="dff02-174">DBX</span></span>
- <span data-ttu-id="dff02-175">MBX</span><span class="sxs-lookup"><span data-stu-id="dff02-175">MBX</span></span>
- <span data-ttu-id="dff02-176">MIME</span><span class="sxs-lookup"><span data-stu-id="dff02-176">MIME</span></span>

<span data-ttu-id="dff02-177">Outlook 2003 以前 (アーカイブの種類が Unicode 以外に設定されている) で使用される PST ファイルもスキャンされますが、pst ファイル内で検出された脅威を Windows Defender で修復することはできません。</span><span class="sxs-lookup"><span data-stu-id="dff02-177">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) will also be scanned, but Windows Defender cannot remediate threats detected inside PST files.</span></span>

<span data-ttu-id="dff02-178">メールMicrosoft Defender ウイルス対策脅威を検出した場合は、侵害された電子メールを識別するために次の情報が表示されます。そのため、脅威を手動で修復できます。</span><span class="sxs-lookup"><span data-stu-id="dff02-178">If Microsoft Defender Antivirus detects a threat inside an email, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="dff02-179">メールの件名</span><span class="sxs-lookup"><span data-stu-id="dff02-179">Email subject</span></span>
- <span data-ttu-id="dff02-180">添付ファイル名</span><span class="sxs-lookup"><span data-stu-id="dff02-180">Attachment name</span></span>

## <a name="related-topics"></a><span data-ttu-id="dff02-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="dff02-181">Related topics</span></span>

- [<span data-ttu-id="dff02-182">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="dff02-182">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dff02-183">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="dff02-183">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dff02-184">スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="dff02-184">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dff02-185">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="dff02-185">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)