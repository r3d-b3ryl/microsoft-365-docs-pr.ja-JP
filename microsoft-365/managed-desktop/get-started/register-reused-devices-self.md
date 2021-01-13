---
title: 既存のデバイスをj自分で登録する
description: Microsoft マネージド デスクトップで管理できるよう、既に自分が持っている可能性がある再利用可能なデバイスを登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840517"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="3c510-103">既存のデバイスをj自分で登録する</span><span class="sxs-lookup"><span data-stu-id="3c510-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="3c510-104">このトピックでは、既に持っているデバイスを再利用し、Microsoft マネージド デスクトップに登録する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c510-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3c510-105">新しいデバイスを使用している場合は [、「Microsoft マネージド](register-devices-self.md) デスクトップに新しいデバイスを自分で登録する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3c510-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="3c510-106">パートナーのプロセスについては、「パートナーがデバイスを登録するための [手順」を参照してください](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="3c510-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="3c510-107">Microsoft マネージド デスクトップは、新しいデバイスで動作するか、既に持っているデバイスを再利用できます (デバイスのイメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="3c510-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="3c510-108">Microsoft Endpoint Manager ポータルで、Microsoft マネージド デスクトップにデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="3c510-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="3c510-109">既存のデバイスの登録を準備する</span><span class="sxs-lookup"><span data-stu-id="3c510-109">Prepare to register existing devices</span></span>


<span data-ttu-id="3c510-110">既存のデバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="3c510-111">各デバイスのハードウェア ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="3c510-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="3c510-112">ハッシュ データをマージする</span><span class="sxs-lookup"><span data-stu-id="3c510-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="3c510-113">[Microsoft マネージド デスクトップにデバイスを登録します](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3c510-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="3c510-114">画像が正しいか、確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c510-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="3c510-115">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="3c510-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="3c510-116">ハードウェア ハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="3c510-116">Obtain the hardware hash</span></span>

<span data-ttu-id="3c510-117">Microsoft マネージド デスクトップでは、ハードウェア ハッシュを参照して各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="3c510-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="3c510-118">既に使用しているデバイスからこの情報を取得するには、次の 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3c510-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="3c510-119">ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM 供給者に問い合わせ、</span><span class="sxs-lookup"><span data-stu-id="3c510-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="3c510-120">[Microsoft Endpoint Configuration Manager で情報を収集します](#microsoft-endpoint-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="3c510-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="3c510-121">[Active](#active-directory-powershell-script-method) Directory Windows PowerShell手動でスクリプトを実行し、結果を[](#manual-powershell-script-method)ファイルに収集します。</span><span class="sxs-lookup"><span data-stu-id="3c510-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="3c510-122">各デバイスを起動します。ただし、Windows セットアップ エクスペリエンスを完了する必要があります。また、リムーバブル フラッシュ ドライブでハッシュ [を収集します](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="3c510-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3c510-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3c510-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="3c510-124">Microsoft Endpoint Configuration Manager を使用して、Microsoft マネージド デスクトップに登録する既存のデバイスからハードウェア ハッシュを収集できます。</span><span class="sxs-lookup"><span data-stu-id="3c510-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c510-125">この情報を取得するデバイスは、Windows 10 バージョン 1703 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="3c510-126">これらすべての前提条件を満たした場合は、次の手順に従って情報を収集する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="3c510-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="3c510-127">Configuration Manager コンソールで、[監視] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c510-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="3c510-128">[監視] ワークスペースで、[レポート] ノード **を展開し** 、[ **レポート**] を展開して、[ハードウェア - 全般] **ノードを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3c510-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="3c510-129">レポートの **Windows Autopilot Device Information を実行し**、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="3c510-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="3c510-130">レポート ビューアーでエクスポート アイコンを選択し **、CSV (コンマ区切り) オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3c510-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="3c510-131">ファイルを保存した後、Microsoft マネージド デスクトップに登録する予定のデバイスに対して結果をフィルター処理し、データを Microsoft マネージド デスクトップにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="3c510-132">Microsoft Endpoint Manager を開き、[デバイス] メニューに移動し、[Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3c510-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="3c510-133">[+ **デバイスの登録]** を選択すると、新しいデバイスを登録するフライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="3c510-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="3c510-134">詳細については [、「管理ポータルを使用してデバイスを登録する](#register-devices-by-using-the-admin-portal) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c510-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="3c510-135">Active Directory PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="3c510-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="3c510-136">Active Directory 環境では、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスからリモートで情報 `Get-WindowsAutoPilotInfo` を収集できます。</span><span class="sxs-lookup"><span data-stu-id="3c510-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="3c510-137">このコマンドレットを使用して、カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果 `Get-AD Computer` を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c510-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="3c510-138">続行する前に、まずこれらの前提条件を確認してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="3c510-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="3c510-139">WinRM が有効になっている。</span><span class="sxs-lookup"><span data-stu-id="3c510-139">WinRM is enabled.</span></span>
- <span data-ttu-id="3c510-140">登録するデバイスはネットワーク上でアクティブです (つまり、切断またはオフにされません)。</span><span class="sxs-lookup"><span data-stu-id="3c510-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="3c510-141">デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="3c510-142">Windows ファイアウォールで WMI へのアクセスが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="3c510-143">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="3c510-144">Windows Defender **ファイアウォール** のコントロール パネルを開き、ファイアウォールからアプリまたは機能 **を許可Windows Defenderします**。</span><span class="sxs-lookup"><span data-stu-id="3c510-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="3c510-145">一 **覧で Windows Management Instrumentation (WMI)** を見つけ **、Private** と Public の両方を有効にして **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c510-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="3c510-146">管理者権限で PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c510-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="3c510-147">次 *のいずれかのスクリプト* を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="3c510-148">デバイスのエントリがある可能性があるディレクトリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3c510-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="3c510-149">Windows Server Active Directoryドメイン サービスと Azure Active Directory を含むすべてのディレクトリから、各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="3c510-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="3c510-150">完全に処理するには、削除に数時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="3c510-151">デバイスのエントリがある可能性があるアクセス管理サービス。</span><span class="sxs-lookup"><span data-stu-id="3c510-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="3c510-152">Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows Autopilot など、すべての管理サービスから各デバイスのエントリを削除します。 </span><span class="sxs-lookup"><span data-stu-id="3c510-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="3c510-153">完全に処理するには、削除に数時間かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="3c510-154">これで、デバイスの登録に [進みます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3c510-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="3c510-155">手動 PowerShell スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="3c510-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="3c510-156">管理者権限で PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c510-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="3c510-157">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="3c510-158">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="3c510-159">ハッシュ データをマージします。</span><span class="sxs-lookup"><span data-stu-id="3c510-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="3c510-160">フラッシュ ドライブ方式</span><span class="sxs-lookup"><span data-stu-id="3c510-160">Flash drive method</span></span>

1. <span data-ttu-id="3c510-161">登録するデバイス以外のデバイスに USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3c510-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="3c510-162">管理者権限で PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c510-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="3c510-163">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="3c510-164">登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始してください*。</span><span class="sxs-lookup"><span data-stu-id="3c510-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="3c510-165">誤ってセットアップ エクスペリエンスを開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="3c510-166">USB ドライブを挿入し、Shift キーを押しながら F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3c510-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="3c510-167">管理者権限で PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="3c510-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="3c510-168">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="3c510-169">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="3c510-170">USB ドライブを取り外し、次に実行してデバイスをシャットダウンします。 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="3c510-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="3c510-171">ハッシュ データをマージします。</span><span class="sxs-lookup"><span data-stu-id="3c510-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="3c510-172">登録が完了するまで、登録するデバイスの電源を入れる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c510-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="3c510-173">ハッシュ データをマージする</span><span class="sxs-lookup"><span data-stu-id="3c510-173">Merge hash data</span></span>

<span data-ttu-id="3c510-174">手動の PowerShell またはフラッシュ ドライブの方法でハードウェア ハッシュ データを収集した場合、登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="3c510-175">簡単に実行できる PowerShell スクリプトのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3c510-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="3c510-176">ハッシュ データを 1 つの CSV ファイルにマージすると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3c510-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="3c510-177">管理ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="3c510-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="3c510-178">[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側のナビゲーション ウィンドウで [デバイス] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="3c510-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="3c510-179">メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="3c510-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="3c510-180">Microsoft マネージド デスクトップ デバイス ワークスペースで、デバイスの選択 **と** 登録を行います。このワークスペースでは、新しいデバイスを登録するフライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="3c510-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="3c510-181">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c510-181">Follow these steps:</span></span>

1. <span data-ttu-id="3c510-182">[ **ファイルのアップロード**] で、前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c510-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="3c510-183">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3c510-183">Select **Register devices**.</span></span> <span data-ttu-id="3c510-184">システムによって、[デバイス] ブレードのデバイスの一覧にデバイスが追加されます。登録が保留中 **としてマークされます**。</span><span class="sxs-lookup"><span data-stu-id="3c510-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="3c510-185">通常、登録に要する時間は 10 分未満です。正常に終了すると、デバイスは "準備完了" と表示されます。つまり、デバイスは準備が整い、ユーザーが使い始めるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="3c510-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="3c510-186">デバイス登録の進行状況は、メイン ページで監視できます。</span><span class="sxs-lookup"><span data-stu-id="3c510-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="3c510-187">報告される可能性がある状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3c510-187">Possible states reported there include:</span></span>

| <span data-ttu-id="3c510-188">状態</span><span class="sxs-lookup"><span data-stu-id="3c510-188">State</span></span> | <span data-ttu-id="3c510-189">説明</span><span class="sxs-lookup"><span data-stu-id="3c510-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="3c510-190">Registration Pending</span><span class="sxs-lookup"><span data-stu-id="3c510-190">Registration Pending</span></span> | <span data-ttu-id="3c510-191">登録はまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="3c510-191">Registration is not done yet.</span></span> <span data-ttu-id="3c510-192">後で確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c510-192">Check back later.</span></span> |
| <span data-ttu-id="3c510-193">登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="3c510-193">Registration failed</span></span> | <span data-ttu-id="3c510-194">登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-194">Registration could not be completed.</span></span> <span data-ttu-id="3c510-195">詳細については [、「デバイス登録のトラブルシューティング」](#troubleshooting-device-registration) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c510-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="3c510-196">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="3c510-196">Ready for user</span></span> | <span data-ttu-id="3c510-197">登録が成功し、デバイスをユーザーに配信する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="3c510-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="3c510-198">Microsoft マネージド デスクトップでは、初回セットアップについて説明します。そのため、追加の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c510-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="3c510-199">Active</span><span class="sxs-lookup"><span data-stu-id="3c510-199">Active</span></span> | <span data-ttu-id="3c510-200">デバイスがユーザーに配信され、テナントに登録されている。</span><span class="sxs-lookup"><span data-stu-id="3c510-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3c510-201">これは、デバイスを定期的に使用している場合も示します。</span><span class="sxs-lookup"><span data-stu-id="3c510-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="3c510-202">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="3c510-202">Inactive</span></span> | <span data-ttu-id="3c510-203">デバイスがユーザーに配信され、テナントに登録されている。</span><span class="sxs-lookup"><span data-stu-id="3c510-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3c510-204">ただし、最近 (過去 7 日間で) デバイスを使用していない。</span><span class="sxs-lookup"><span data-stu-id="3c510-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="3c510-205">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3c510-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="3c510-206">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="3c510-206">Error message</span></span> | <span data-ttu-id="3c510-207">詳細</span><span class="sxs-lookup"><span data-stu-id="3c510-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="3c510-208">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="3c510-208">Device not found</span></span> | <span data-ttu-id="3c510-209">提供された製造元、モデル、シリアル番号に一致するデバイスが見つからなかったため、このデバイスを登録できなかった。</span><span class="sxs-lookup"><span data-stu-id="3c510-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="3c510-210">デバイスの供給者にこれらの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="3c510-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="3c510-211">ハードウェア ハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="3c510-211">Hardware hash not valid</span></span> | <span data-ttu-id="3c510-212">このデバイスに指定したハードウェア ハッシュが正しくフォーマットされていません。</span><span class="sxs-lookup"><span data-stu-id="3c510-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="3c510-213">ハードウェア ハッシュを再確認し、再送信します。</span><span class="sxs-lookup"><span data-stu-id="3c510-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="3c510-214">デバイスが既に登録されている</span><span class="sxs-lookup"><span data-stu-id="3c510-214">Device already registered</span></span> | <span data-ttu-id="3c510-215">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="3c510-215">This device is already registered to your organization.</span></span> <span data-ttu-id="3c510-216">それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3c510-216">No further action required.</span></span> |
| <span data-ttu-id="3c510-217">別の組織によって要求されたデバイス</span><span class="sxs-lookup"><span data-stu-id="3c510-217">Device claimed by another organization</span></span> | <span data-ttu-id="3c510-218">このデバイスは、別の組織によって既に要求されています。</span><span class="sxs-lookup"><span data-stu-id="3c510-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="3c510-219">デバイスの供給者に確認します。</span><span class="sxs-lookup"><span data-stu-id="3c510-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="3c510-220">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="3c510-220">Unexpected error</span></span> | <span data-ttu-id="3c510-221">要求を自動的に処理する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="3c510-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="3c510-222">サポートに問い合わせ、要求 ID を入力します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="3c510-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="3c510-223">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="3c510-223">Check the image</span></span>

<span data-ttu-id="3c510-224">デバイスが Microsoft マネージド デスクトップ パートナーの供給者から提供されている場合は、イメージが正しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c510-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="3c510-225">必要に応じて、画像を自分で適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c510-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="3c510-226">To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="3c510-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="3c510-227">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="3c510-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c510-228">デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用してください](../get-ready/prerequisites.md) 。</span><span class="sxs-lookup"><span data-stu-id="3c510-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="3c510-229">すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)がデバイスを使用する準備を整え、ユーザーがデバイスを起動して Windows セットアップ エクスペリエンスを続行できます。</span><span class="sxs-lookup"><span data-stu-id="3c510-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









