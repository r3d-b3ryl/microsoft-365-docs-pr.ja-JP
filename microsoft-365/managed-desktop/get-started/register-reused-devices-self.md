---
title: 既存のデバイスをj自分で登録する
description: 再利用されたデバイスを登録します。これにより、Microsoft マネージドデスクトップで管理できるようになります。
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289141"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="60f65-103">既存のデバイスをj自分で登録する</span><span class="sxs-lookup"><span data-stu-id="60f65-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="60f65-104">このトピックでは、既に所有しているデバイスを再利用して、Microsoft マネージドデスクトップで登録する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="60f65-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="60f65-105">新しいデバイスを使用している場合は、代わりに「 [Microsoft Managed Desktop で新しいデバイスを登録](register-devices-self.md) する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="60f65-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="60f65-106">パートナーのプロセスは、パートナーが [デバイスを登録する手順](register-devices-partner.md)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="60f65-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="60f65-107">Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="60f65-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="60f65-108">Microsoft Managed Desktop 管理ポータルを使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="60f65-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="60f65-109">既存のデバイスを登録するための準備</span><span class="sxs-lookup"><span data-stu-id="60f65-109">Prepare to register existing devices</span></span>


<span data-ttu-id="60f65-110">既存のデバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="60f65-111">各デバイスのハードウェアハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="60f65-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="60f65-112">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="60f65-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="60f65-113">[Microsoft マネージドデスクトップにデバイスを登録](#register-devices-by-using-the-admin-portal)します。</span><span class="sxs-lookup"><span data-stu-id="60f65-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="60f65-114">画像が正しいことをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="60f65-115">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="60f65-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="60f65-116">ハードウェアハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="60f65-116">Obtain the hardware hash</span></span>

<span data-ttu-id="60f65-117">Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="60f65-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="60f65-118">既に使用しているデバイスからこの情報を取得するには、次の4つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="60f65-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="60f65-119">ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="60f65-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="60f65-120">[Microsoft エンドポイント構成マネージャー](#microsoft-endpoint-configuration-manager)で情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="60f65-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="60f65-121">[Active Directory](#active-directory-powershell-script-method)を使用するか、または各デバイスで[手動](#manual-powershell-script-method)で Windows PowerShell スクリプトを実行して、ファイルに結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="60f65-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="60f65-122">各デバイスを開始しますが、Windows セットアップの動作を完了せず [に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。</span><span class="sxs-lookup"><span data-stu-id="60f65-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="60f65-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="60f65-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="60f65-124">Microsoft エンドポイント構成マネージャーを使用して、Microsoft マネージドデスクトップに登録する既存のデバイスからハードウェアハッシュを収集できます。</span><span class="sxs-lookup"><span data-stu-id="60f65-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60f65-125">この情報を取得するデバイスには、Windows 10、バージョン1703以降が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60f65-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="60f65-126">これらの前提条件をすべて満たしている場合は、次の手順を実行して情報を収集する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="60f65-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="60f65-127">構成マネージャーコンソールで、[ **監視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="60f65-128">[監視] ワークスペースで、[ **レポート** ] ノードを展開し、[ **レポート**] を展開して、[ **ハードウェア-全般** ] ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="60f65-129">レポート、 **Windows 自動操縦デバイス情報**を実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="60f65-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="60f65-130">レポートビューアーで [ **エクスポート** ] アイコンを選択し、[ **CSV (コンマ区切り)** ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="60f65-131">ファイルを保存した後は、Microsoft マネージドデスクトップに登録する予定のデバイスのみに結果をフィルター処理し、そのデータを Microsoft Managed Desktop [管理ポータル](https://aka.ms/mmdportal)にアップロードする必要があります。左側のナビゲーションウィンドウで [ **デバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="60f65-132">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="60f65-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="60f65-133">詳細については [、「管理者ポータルを使用してデバイスを登録](#register-devices-by-using-the-admin-portal) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="60f65-134">Active Directory PowerShell スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="60f65-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="60f65-135">Active Directory 環境では、PowerShell コマンドレットを使用して、 `Get-WindowsAutoPilotInfo` WinRM を使用して Active Directory グループ内のデバイスから情報をリモートで収集できます。</span><span class="sxs-lookup"><span data-stu-id="60f65-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="60f65-136">また、この `Get-AD Computer` コマンドレットを使用して、カタログに含まれている特定のハードウェアモデル名のフィルター結果を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="60f65-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="60f65-137">これを行うには、まずこれらの前提条件を確認してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="60f65-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="60f65-138">WinRM は有効になっています。</span><span class="sxs-lookup"><span data-stu-id="60f65-138">WinRM is enabled.</span></span>
- <span data-ttu-id="60f65-139">登録するデバイスがネットワーク上でアクティブになっている (つまり、切断されていないかオフになっている)。</span><span class="sxs-lookup"><span data-stu-id="60f65-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="60f65-140">デバイス上でリモートで実行するためのアクセス許可を持つ domain credential パラメーターがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="60f65-141">Windows ファイアウォールが WMI へのアクセスを許可していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60f65-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="60f65-142">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="60f65-143">**Windows Defender ファイアウォール**コントロールパネルを開き、[ **Windows defender ファイアウォール経由でアプリまたは機能を許可**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="60f65-144">一覧で [ **Windows Management Instrumentation (WMI)** ] を見つけ、[ **プライベートとパブリック**] の両方で有効にして、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="60f65-145">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="60f65-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="60f65-146">次 *のいずれかのスクリプトを実行* します。</span><span class="sxs-lookup"><span data-stu-id="60f65-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="60f65-147">デバイスのエントリが存在する可能性があるディレクトリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="60f65-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="60f65-148">Windows Server Active Directory ドメインサービスと Azure Active Directory を含む、 *すべて* のディレクトリから各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="60f65-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="60f65-149">この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="60f65-150">デバイスのエントリが存在する可能性があるアクセス管理サービス。</span><span class="sxs-lookup"><span data-stu-id="60f65-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="60f65-151">Microsoft エンドポイント構成マネージャー、Microsoft Intune、Windows 自動操縦など、 *すべて* の管理サービスから各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="60f65-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="60f65-152">この削除は、完全に処理されるまで数時間かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="60f65-153">これで、デバイスの [登録](#register-devices-by-using-the-admin-portal)に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="60f65-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="60f65-154">PowerShell スクリプトの手動メソッド</span><span class="sxs-lookup"><span data-stu-id="60f65-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="60f65-155">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="60f65-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="60f65-156">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="60f65-157">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="60f65-158">ハッシュデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="60f65-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="60f65-159">Flash drive メソッド</span><span class="sxs-lookup"><span data-stu-id="60f65-159">Flash drive method</span></span>

1. <span data-ttu-id="60f65-160">登録している以外のデバイスに USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="60f65-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="60f65-161">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="60f65-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="60f65-162">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="60f65-163">登録するデバイスを有効にしますが、 *セットアップの操作は開始*しないでください。</span><span class="sxs-lookup"><span data-stu-id="60f65-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="60f65-164">セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60f65-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="60f65-165">USB ドライブを挿入して、SHIFT + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="60f65-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="60f65-166">管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。</span><span class="sxs-lookup"><span data-stu-id="60f65-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="60f65-167">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="60f65-168">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="60f65-169">USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="60f65-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="60f65-170">ハッシュデータを結合します。</span><span class="sxs-lookup"><span data-stu-id="60f65-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="60f65-171">登録が完了するまでは、デバイスの電源を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="60f65-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="60f65-172">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="60f65-172">Merge hash data</span></span>

<span data-ttu-id="60f65-173">手動の PowerShell または flash drive メソッドによってハードウェアハッシュデータを収集した場合は、CSV ファイル内のデータを1つのファイルにまとめて登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60f65-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="60f65-174">これを簡単にするためのサンプル PowerShell スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="60f65-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="60f65-175">ハッシュデータを1つの CSV ファイルに結合すると、 [デバイスの登録](#register-devices-by-using-the-admin-portal)に進むことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="60f65-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="60f65-176">管理ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="60f65-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="60f65-177">Microsoft Managed Desktop [管理ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウで [ **デバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="60f65-178">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="60f65-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="60f65-179">[![[デバイスの登録] を選択した後のフライイン、割り当てられたユーザーの列が含まれているデバイスを一覧表示する、シリアル番号、状態、最終確認日、および保存期間](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="60f65-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="60f65-180">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f65-180">Follow these steps:</span></span>

1. <span data-ttu-id="60f65-181">[ **ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="60f65-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="60f65-182">[ **デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60f65-182">Select **Register devices**.</span></span> <span data-ttu-id="60f65-183">デバイスは、 **AutopilotRegistrationRequested**としてマークされているデバイス**ブレード**上のデバイスの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="60f65-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="60f65-184">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは **ユーザーのための** 準備完了として表示され、ユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="60f65-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="60f65-185">メインの **Microsoft Managed Desktop-Devices** ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="60f65-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="60f65-186">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60f65-186">Possible states reported there include:</span></span>

| <span data-ttu-id="60f65-187">State</span><span class="sxs-lookup"><span data-stu-id="60f65-187">State</span></span> | <span data-ttu-id="60f65-188">説明</span><span class="sxs-lookup"><span data-stu-id="60f65-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="60f65-189">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="60f65-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="60f65-190">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="60f65-190">Registration is not done yet.</span></span> <span data-ttu-id="60f65-191">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-191">Check back later.</span></span> |
| <span data-ttu-id="60f65-192">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="60f65-192">Registration failed</span></span> | <span data-ttu-id="60f65-193">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="60f65-193">Registration could not be completed.</span></span> <span data-ttu-id="60f65-194">詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="60f65-195">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="60f65-195">Ready for user</span></span> | <span data-ttu-id="60f65-196">登録が成功し、デバイスをユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="60f65-196">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="60f65-197">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60f65-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="60f65-198">Active</span><span class="sxs-lookup"><span data-stu-id="60f65-198">Active</span></span> | <span data-ttu-id="60f65-199">デバイスはユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="60f65-199">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="60f65-200">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="60f65-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="60f65-201">未使用</span><span class="sxs-lookup"><span data-stu-id="60f65-201">Inactive</span></span> | <span data-ttu-id="60f65-202">デバイスはユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="60f65-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="60f65-203">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="60f65-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="60f65-204">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="60f65-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="60f65-205">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="60f65-205">Error message</span></span> | <span data-ttu-id="60f65-206">詳細</span><span class="sxs-lookup"><span data-stu-id="60f65-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="60f65-207">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="60f65-207">Device not found</span></span> | <span data-ttu-id="60f65-208">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="60f65-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="60f65-209">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="60f65-210">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="60f65-210">Hardware hash not valid</span></span> | <span data-ttu-id="60f65-211">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="60f65-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="60f65-212">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="60f65-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="60f65-213">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="60f65-213">Device already registered</span></span> | <span data-ttu-id="60f65-214">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="60f65-214">This device is already registered to your organization.</span></span> <span data-ttu-id="60f65-215">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="60f65-215">No further action required.</span></span> |
| <span data-ttu-id="60f65-216">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="60f65-216">Device claimed by another organization</span></span> | <span data-ttu-id="60f65-217">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="60f65-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="60f65-218">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="60f65-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="60f65-219">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="60f65-219">Unexpected error</span></span> | <span data-ttu-id="60f65-220">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="60f65-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="60f65-221">サポートに連絡して、要求 ID を提供します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="60f65-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="60f65-222">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="60f65-222">Check the image</span></span>

<span data-ttu-id="60f65-223">デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="60f65-224">また、必要に応じて、自分で画像を適用することも歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="60f65-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="60f65-225">開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="60f65-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="60f65-226">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="60f65-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60f65-227">ユーザーにデバイスを渡す前に、そのユーザーの [適切なライセンス](../get-ready/prerequisites.md) を取得して適用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="60f65-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="60f65-228">すべてのライセンスが適用されている場合は、 [デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="60f65-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









