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
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964899"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a><span data-ttu-id="5db73-104">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="5db73-104">Configure Microsoft Defender Antivirus scanning options</span></span>

<span data-ttu-id="5db73-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5db73-105">**Applies to:**</span></span>

- [<span data-ttu-id="5db73-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5db73-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a><span data-ttu-id="5db73-107">スキャン オプションMicrosoft Intune構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db73-107">Use Microsoft Intune to configure scanning options</span></span>

<span data-ttu-id="5db73-108">詳細については、「デバイス制限設定の[構成](/intune/device-restrictions-configure)」を参照Microsoft Intune Intune Microsoft Defender ウイルス対策デバイス制限設定Windows 10[参照してください](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5db73-108">For more information, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span> 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a><span data-ttu-id="5db73-109">スキャン オプションMicrosoft エンドポイント マネージャー構成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5db73-109">Use Microsoft Endpoint Manager to configure scanning options</span></span>

<span data-ttu-id="5db73-110">マルウェア対策ポリシー (現在のブランチMicrosoft エンドポイント マネージャー構成する方法の詳細については、「マルウェア対策ポリシーを作成して展開する方法: スキャン設定」[を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings)。</span><span class="sxs-lookup"><span data-stu-id="5db73-110">For details on configuring Microsoft Endpoint Manager (current branch), see [How to create and deploy antimalware policies: Scan settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).</span></span>

## <a name="use-group-policy-to-configure-scanning-options"></a><span data-ttu-id="5db73-111">グループ ポリシーを使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="5db73-111">Use Group Policy to configure scanning options</span></span>

1. <span data-ttu-id="5db73-112">グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開きます。</span><span class="sxs-lookup"><span data-stu-id="5db73-112">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="5db73-113">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5db73-113">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="5db73-114">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5db73-114">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

4. <span data-ttu-id="5db73-115">ツリーを展開してWindows **コンポーネント** Microsoft Defender ウイルス対策し、場所を選択します (この記事の「設定  >  [場所](#settings-and-locations)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5db73-115">Expand the tree to **Windows components** > **Microsoft Defender Antivirus**, and then select a location (refer to [Settings and locations](#settings-and-locations) in this article).</span></span>


5. <span data-ttu-id="5db73-116">ポリシー オブジェクトを編集します。</span><span class="sxs-lookup"><span data-stu-id="5db73-116">Edit the policy object.</span></span> 

6. <span data-ttu-id="5db73-117">**[OK] を** クリックし、他の設定を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5db73-117">Click **OK**, and repeat for any other settings.</span></span>

### <a name="settings-and-locations"></a><span data-ttu-id="5db73-118">設定場所</span><span class="sxs-lookup"><span data-stu-id="5db73-118">Settings and locations</span></span>

| <span data-ttu-id="5db73-119">ポリシー アイテムと場所</span><span class="sxs-lookup"><span data-stu-id="5db73-119">Policy item and location</span></span> | <span data-ttu-id="5db73-120">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="5db73-120">Default setting (if not configured)</span></span> | <span data-ttu-id="5db73-121">クラスの PowerShell `Set-MpPreference` パラメーターまたは WMI `MSFT_MpPreference` プロパティ</span><span class="sxs-lookup"><span data-stu-id="5db73-121">PowerShell `Set-MpPreference` parameter or WMI property for `MSFT_MpPreference` class</span></span> |
|---|---|---|
| <span data-ttu-id="5db73-122">電子メールのスキャン</span><span class="sxs-lookup"><span data-stu-id="5db73-122">Email scanning</span></span> <p> <span data-ttu-id="5db73-123">**スキャン**  > **電子メール スキャンを有効にする**</span><span class="sxs-lookup"><span data-stu-id="5db73-123">**Scan** > **Turn on e-mail scanning**</span></span><p><span data-ttu-id="5db73-124">「 [電子メールのスキャンの制限」を](#email-scanning-limitations) 参照してください (この記事で)</span><span class="sxs-lookup"><span data-stu-id="5db73-124">See [Email scanning limitations](#email-scanning-limitations) (in this article)</span></span> | <span data-ttu-id="5db73-125">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-125">Disabled</span></span> | `-DisableEmailScanning` |
|<span data-ttu-id="5db73-126">再 [解析ポイントのスキャン](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="5db73-126">Scan [reparse points](/windows/win32/fileio/reparse-points)</span></span> <p> <span data-ttu-id="5db73-127">**スキャン**  > **再解析ポイントスキャンを有効にする**</span><span class="sxs-lookup"><span data-stu-id="5db73-127">**Scan** > **Turn on reparse point scanning**</span></span> | <span data-ttu-id="5db73-128">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-128">Disabled</span></span> | <span data-ttu-id="5db73-129">利用不可</span><span class="sxs-lookup"><span data-stu-id="5db73-129">Not available</span></span> <p><span data-ttu-id="5db73-130">[「Reparse ポイント」を参照してください。](/windows/win32/fileio/reparse-points)</span><span class="sxs-lookup"><span data-stu-id="5db73-130">See [Reparse points](/windows/win32/fileio/reparse-points)</span></span>  |
| <span data-ttu-id="5db73-131">マップされたネットワーク ドライブをスキャンする</span><span class="sxs-lookup"><span data-stu-id="5db73-131">Scan mapped network drives</span></span> <p> <span data-ttu-id="5db73-132">**スキャン**  > **マップされたネットワーク ドライブでフル スキャンを実行する**</span><span class="sxs-lookup"><span data-stu-id="5db73-132">**Scan** > **Run full scan on mapped network drives**</span></span> | <span data-ttu-id="5db73-133">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-133">Disabled</span></span> | `-DisableScanningMappedNetworkDrivesForFullScan`|
| <span data-ttu-id="5db73-134">アーカイブ ファイルをスキャンする (.zipファイル.rarします。</span><span class="sxs-lookup"><span data-stu-id="5db73-134">Scan archive files (such as .zip or .rar files).</span></span>  <p> <span data-ttu-id="5db73-135">**スキャン**  > **アーカイブ ファイルのスキャン**</span><span class="sxs-lookup"><span data-stu-id="5db73-135">**Scan** > **Scan archive files**</span></span> | <span data-ttu-id="5db73-136">有効</span><span class="sxs-lookup"><span data-stu-id="5db73-136">Enabled</span></span> | `-DisableArchiveScanning` <p><span data-ttu-id="5db73-137">拡張機能 [の除外リストは、](configure-extension-file-exclusions-microsoft-defender-antivirus.md) この設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5db73-137">The [extensions exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md) will take precedence over this setting.</span></span>|
| <span data-ttu-id="5db73-138">ネットワーク上のファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="5db73-138">Scan files on the network</span></span> <p> <span data-ttu-id="5db73-139">**スキャン**  > **ネットワーク ファイルのスキャン**</span><span class="sxs-lookup"><span data-stu-id="5db73-139">**Scan** > **Scan network files**</span></span> | <span data-ttu-id="5db73-140">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-140">Disabled</span></span> | `-DisableScanningNetworkFiles` |
| <span data-ttu-id="5db73-141">パックされた実行可能ファイルをスキャンする</span><span class="sxs-lookup"><span data-stu-id="5db73-141">Scan packed executables</span></span> <p> <span data-ttu-id="5db73-142">**スキャン**  > **パックされた実行可能ファイルをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="5db73-142">**Scan** > **Scan packed executables**</span></span> | <span data-ttu-id="5db73-143">有効</span><span class="sxs-lookup"><span data-stu-id="5db73-143">Enabled</span></span> | <span data-ttu-id="5db73-144">利用不可</span><span class="sxs-lookup"><span data-stu-id="5db73-144">Not available</span></span> |
| <span data-ttu-id="5db73-145">フル スキャン時にのみリムーバブル ドライブをスキャンする</span><span class="sxs-lookup"><span data-stu-id="5db73-145">Scan removable drives during full scans only</span></span> <p> <span data-ttu-id="5db73-146">**スキャン**  > **リムーバブル ドライブのスキャン**</span><span class="sxs-lookup"><span data-stu-id="5db73-146">**Scan** > **Scan removable drives**</span></span> | <span data-ttu-id="5db73-147">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-147">Disabled</span></span> | `-DisableRemovableDriveScanning` |
| <span data-ttu-id="5db73-148">スキャンするアーカイブ フォルダー内のサブフォルダーのレベルを指定する</span><span class="sxs-lookup"><span data-stu-id="5db73-148">Specify the level of subfolders within an archive folder to scan</span></span> <p><span data-ttu-id="5db73-149">**スキャン**  > **アーカイブ ファイルをスキャンする最大深度を指定する**</span><span class="sxs-lookup"><span data-stu-id="5db73-149">**Scan** > **Specify the maximum depth to scan archive files**</span></span> | <span data-ttu-id="5db73-150">0</span><span class="sxs-lookup"><span data-stu-id="5db73-150">0</span></span> | <span data-ttu-id="5db73-151">利用不可</span><span class="sxs-lookup"><span data-stu-id="5db73-151">Not available</span></span> |
| <span data-ttu-id="5db73-152">スキャン中の CPU の最大負荷 (パーセンテージ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5db73-152">Specify the maximum CPU load (as a percentage) during a scan.</span></span> <p> <span data-ttu-id="5db73-153">**スキャン**  > **スキャン中の CPU 使用率の最大割合を指定する**</span><span class="sxs-lookup"><span data-stu-id="5db73-153">**Scan** > **Specify the maximum percentage of CPU utilization during a scan**</span></span> | <span data-ttu-id="5db73-154">50</span><span class="sxs-lookup"><span data-stu-id="5db73-154">50</span></span> |  `-ScanAvgCPULoadFactor` <p><span data-ttu-id="5db73-155">**注**: CPU の最大負荷はハード制限ではなく、スキャン エンジンが平均して最大値を超えないようにするガイダンスです。</span><span class="sxs-lookup"><span data-stu-id="5db73-155">**NOTE**: The maximum CPU load is not a hard limit, but is guidance for the scanning engine to not exceed the maximum on average.</span></span> <span data-ttu-id="5db73-156">手動でスキャンを実行すると、この設定は無視され、CPU 制限なしで実行されます。</span><span class="sxs-lookup"><span data-stu-id="5db73-156">Manually run scans will ignore this setting and run without any CPU limits.</span></span> |
| <span data-ttu-id="5db73-157">スキャンするアーカイブ ファイルの最大サイズ (キロバイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="5db73-157">Specify the maximum size (in kilobytes) of archive files that should be scanned.</span></span> <p> <span data-ttu-id="5db73-158">**スキャン**  > **スキャンするアーカイブ ファイルの最大サイズを指定する**</span><span class="sxs-lookup"><span data-stu-id="5db73-158">**Scan** > **Specify the maximum size of archive files to be scanned**</span></span> | <span data-ttu-id="5db73-159">制限なし</span><span class="sxs-lookup"><span data-stu-id="5db73-159">No limit</span></span> | <span data-ttu-id="5db73-160">利用不可</span><span class="sxs-lookup"><span data-stu-id="5db73-160">Not available</span></span> <p><span data-ttu-id="5db73-161">既定値 0 は制限なしを適用します</span><span class="sxs-lookup"><span data-stu-id="5db73-161">The default value of 0 applies no limit</span></span> |
| <span data-ttu-id="5db73-162">スケジュールされたスキャンの CPU 優先度が低い構成</span><span class="sxs-lookup"><span data-stu-id="5db73-162">Configure low CPU priority for scheduled scans</span></span> <p> <span data-ttu-id="5db73-163">**スキャン**  > **スケジュールされたスキャンの CPU 優先度が低い構成**</span><span class="sxs-lookup"><span data-stu-id="5db73-163">**Scan** > **Configure low CPU priority for scheduled scans**</span></span> | <span data-ttu-id="5db73-164">無効</span><span class="sxs-lookup"><span data-stu-id="5db73-164">Disabled</span></span> | <span data-ttu-id="5db73-165">利用不可</span><span class="sxs-lookup"><span data-stu-id="5db73-165">Not available</span></span> |

 
> [!NOTE]
> <span data-ttu-id="5db73-166">リアルタイム保護が有効になっている場合、ファイルにアクセスして実行する前にファイルがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="5db73-166">If real-time protection is turned on, files are scanned before they are accessed and executed.</span></span> <span data-ttu-id="5db73-167">スキャンスコープには、マウントされたリムーバブル メディア上のファイル (USB ドライブなど) を含むすべてのファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5db73-167">The scanning scope includes all files, including files on mounted removable media, such as USB drives.</span></span> <span data-ttu-id="5db73-168">スキャンを実行するデバイスでリアルタイム保護またはオンアクセス保護が有効になっている場合、スキャンにはネットワーク共有も含まれます。</span><span class="sxs-lookup"><span data-stu-id="5db73-168">If the device performing the scan has real-time protection or on-access protection turned on, the scan will also include network shares.</span></span>

## <a name="use-powershell-to-configure-scanning-options"></a><span data-ttu-id="5db73-169">PowerShell を使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="5db73-169">Use PowerShell to configure scanning options</span></span>


<span data-ttu-id="5db73-170">PowerShell を使用して PowerShell を使用する方法の詳細については、「Microsoft Defender ウイルス対策」</span><span class="sxs-lookup"><span data-stu-id="5db73-170">For more information on how to use PowerShell with Microsoft Defender Antivirus, see</span></span>

- [<span data-ttu-id="5db73-171">PowerShell コマンドレットMicrosoft Defender ウイルス対策の管理</span><span class="sxs-lookup"><span data-stu-id="5db73-171">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5db73-172">Defender コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5db73-172">Defender cmdlets</span></span>](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a><span data-ttu-id="5db73-173">WMI を使用してスキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="5db73-173">Use WMI to configure scanning options</span></span>

<span data-ttu-id="5db73-174">[「WMIv2 API Windows Defender」を参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="5db73-174">See [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="email-scanning-limitations"></a><span data-ttu-id="5db73-175">電子メールのスキャンの制限</span><span class="sxs-lookup"><span data-stu-id="5db73-175">Email scanning limitations</span></span>

<span data-ttu-id="5db73-176">メール スキャンを使用すると、オンデマンドおよびスケジュールされたスキャン中に、Outlook他のメール クライアントで使用される電子メール ファイルをスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="5db73-176">Email scanning enables scanning of email files used by Outlook and other mail clients during on-demand and scheduled scans.</span></span> <span data-ttu-id="5db73-177">電子メール内の埋め込みオブジェクト (添付ファイルやアーカイブ ファイルなど) もスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="5db73-177">Embedded objects within email (such as attachments and archived files) are also scanned.</span></span> <span data-ttu-id="5db73-178">次のファイル形式の種類をスキャンして修復できます。</span><span class="sxs-lookup"><span data-stu-id="5db73-178">The following file format types can be scanned and remediated:</span></span>

- <span data-ttu-id="5db73-179">DBX</span><span class="sxs-lookup"><span data-stu-id="5db73-179">DBX</span></span>
- <span data-ttu-id="5db73-180">MBX</span><span class="sxs-lookup"><span data-stu-id="5db73-180">MBX</span></span>
- <span data-ttu-id="5db73-181">MIME</span><span class="sxs-lookup"><span data-stu-id="5db73-181">MIME</span></span>

<span data-ttu-id="5db73-182">Outlook 2003 以前 (アーカイブの種類が Unicode 以外に設定されている) で使用される PST ファイルもスキャンされますが、Microsoft Defender ウイルス対策 は PST ファイル内で検出された脅威を修復できません。</span><span class="sxs-lookup"><span data-stu-id="5db73-182">PST files used by Outlook 2003 or older (where the archive type is set to non-unicode) are also scanned, but Microsoft Defender Antivirus cannot remediate threats that are detected inside PST files.</span></span>

<span data-ttu-id="5db73-183">電子Microsoft Defender ウイルス対策メッセージ内の脅威を検出した場合は、侵害された電子メールを識別するために次の情報が表示され、脅威を手動で修復できます。</span><span class="sxs-lookup"><span data-stu-id="5db73-183">If Microsoft Defender Antivirus detects a threat inside an email message, it will show you the following information to assist you in identifying the compromised email, so you can remediate the threat manually:</span></span>

- <span data-ttu-id="5db73-184">メールの件名</span><span class="sxs-lookup"><span data-stu-id="5db73-184">Email subject</span></span>
- <span data-ttu-id="5db73-185">添付ファイル名</span><span class="sxs-lookup"><span data-stu-id="5db73-185">Attachment name</span></span>


## <a name="scanning-mapped-network-drives"></a><span data-ttu-id="5db73-186">マップされたネットワーク ドライブのスキャン</span><span class="sxs-lookup"><span data-stu-id="5db73-186">Scanning mapped network drives</span></span>

<span data-ttu-id="5db73-187">どの OS でも、システム レベルでマップされているネットワーク ドライブだけがスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="5db73-187">On any OS, only the network drives that are mapped at system level, are scanned.</span></span> <span data-ttu-id="5db73-188">ユーザー レベルのマップされたネットワーク ドライブはスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="5db73-188">User-level mapped network drives aren't scanned.</span></span> <span data-ttu-id="5db73-189">ユーザー レベルのマップされたネットワーク ドライブは、ユーザーがセッション内で手動でマップし、自分の資格情報を使用するドライブです。</span><span class="sxs-lookup"><span data-stu-id="5db73-189">User-level mapped network drives are those that a user maps in their session manually and using their own credentials.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db73-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db73-190">See also</span></span>


- [<span data-ttu-id="5db73-191">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="5db73-191">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5db73-192">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="5db73-192">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5db73-193">スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="5db73-193">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5db73-194">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="5db73-194">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
