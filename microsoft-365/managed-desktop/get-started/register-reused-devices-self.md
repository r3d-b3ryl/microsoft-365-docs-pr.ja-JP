---
title: 既存のデバイスをj自分で登録する
description: 再利用されたデバイスを既に持っている可能性があるデバイスを登録して、Microsoft Managed Desktop で管理できます
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445568"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="3cf62-104">既存のデバイスをj自分で登録する</span><span class="sxs-lookup"><span data-stu-id="3cf62-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="3cf62-105">このトピックでは、既に持っているデバイスを再利用し、Microsoft Managed Desktop に登録する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="3cf62-106">新しいデバイスを操作する場合は [、「Microsoft Managed Desktop](register-devices-self.md) で新しいデバイスを自分で登録する」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="3cf62-107">パートナーのプロセスについては、「デバイスを登録 [するパートナー向け手順」に記載されています](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="3cf62-108">Microsoft Managed Desktop は、新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用できます (再イメージ化が必要になります)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="3cf62-109">Microsoft Endpoint Manager ポータルで、Microsoft Managed Desktop にデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="3cf62-110">既存のデバイスを登録する準備</span><span class="sxs-lookup"><span data-stu-id="3cf62-110">Prepare to register existing devices</span></span>


<span data-ttu-id="3cf62-111">既存のデバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="3cf62-112">各デバイスのハードウェア ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="3cf62-113">ハッシュ データを結合する</span><span class="sxs-lookup"><span data-stu-id="3cf62-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="3cf62-114">[Microsoft Managed Desktop にデバイスを登録します](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="3cf62-115">画像が正しいか確認してください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="3cf62-116">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="3cf62-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="3cf62-117">ハードウェア ハッシュの取得</span><span class="sxs-lookup"><span data-stu-id="3cf62-117">Obtain the hardware hash</span></span>

<span data-ttu-id="3cf62-118">Microsoft Managed Desktop は、ハードウェア ハッシュを参照することによって、各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="3cf62-119">既に使用しているデバイスからこの情報を取得するには、次の 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="3cf62-120">ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。</span><span class="sxs-lookup"><span data-stu-id="3cf62-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="3cf62-121">Microsoft Endpoint [Configuration Manager で情報を収集します](#microsoft-endpoint-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="3cf62-122">Active [Directory](#active-directory-powershell-script-method)をWindows PowerShell、または各デバイスで手動でスクリプト[](#manual-powershell-script-method)を実行し、結果をファイルに収集します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="3cf62-123">各デバイスを起動しますが、Windows セットアップ エクスペリエンスを完了し、リムーバブル フラッシュ ドライブのハッシュ [を収集する必要があります](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3cf62-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3cf62-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="3cf62-125">Microsoft Endpoint Configuration Manager を使用して、Microsoft Managed Desktop に登録する既存のデバイスからハードウェア ハッシュを収集できます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf62-126">この情報を取得するデバイスは、Windows 10 バージョン 1703 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="3cf62-127">これらすべての前提条件を満たしている場合は、次の手順に従って情報を収集する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="3cf62-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="3cf62-128">Configuration Manager コンソールで、[監視] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="3cf62-129">[監視] ワークスペースで、[レポート] ノード **を展開し** 、[レポート] を **展開** し、[ハードウェア **- 全般] ノードを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="3cf62-130">レポートの **Windows Autopilot デバイス情報を実行し**、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="3cf62-131">レポート ビューアーで、[エクスポート] **アイコンを** 選択し、CSV (コンマ区切り **) オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="3cf62-132">ファイルを保存した後、Microsoft Managed Desktop に登録し、データを Microsoft Managed Desktop にアップロードする予定のデバイスに対して結果をフィルター処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="3cf62-133">Microsoft Endpoint Manager を開き、[デバイス] メニューに移動し、[Microsoft Managed Desktop] セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="3cf62-134">[+ **デバイスの登録]** を選択すると、フライインが開き、新しいデバイスが登録されます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="3cf62-135">詳細については [、「管理ポータルを使用してデバイスを登録する](#register-devices-by-using-the-admin-portal) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="3cf62-136">Active Directory PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="3cf62-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="3cf62-137">Active Directory 環境では、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスから情報をリモート `Get-WindowsAutoPilotInfo` で収集できます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="3cf62-138">コマンドレットを使用して、カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果 `Get-AD Computer` を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="3cf62-139">続行する前に、まずこれらの前提条件を確認してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="3cf62-140">WinRM が有効です。</span><span class="sxs-lookup"><span data-stu-id="3cf62-140">WinRM is enabled.</span></span>
- <span data-ttu-id="3cf62-141">登録するデバイスは、ネットワーク上でアクティブです (つまり、切断またはオフにされません)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="3cf62-142">デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="3cf62-143">Windows ファイアウォールで WMI へのアクセスが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="3cf62-144">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="3cf62-145">[ファイアウォール] **Windows Defenderパネルを** 開き、[ファイアウォール経由でアプリまたは機能を許可 **する] をWindows Defenderします**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="3cf62-146">一 **覧で Windows 管理インス** トルメンテーション (WMI) を検索し、プライベートとパブリックの両方を有効にし **、[OK] を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="3cf62-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="3cf62-147">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="3cf62-148">次 *のいずれかのスクリプト* を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="3cf62-149">デバイスのエントリがある可能性があるディレクトリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3cf62-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="3cf62-150">Windows Server Active Directoryドメイン サービスや Azure Active Directory など、すべてのディレクトリから各デバイスのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="3cf62-151">完全に処理するには、削除に数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="3cf62-152">デバイスのエントリがある可能性がある管理サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="3cf62-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="3cf62-153">Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows Autopilot など、すべての管理サービスから各デバイスのエントリを削除します。 </span><span class="sxs-lookup"><span data-stu-id="3cf62-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="3cf62-154">完全に処理するには、削除に数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="3cf62-155">これで、デバイスの登録 [に進みます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="3cf62-156">手動 PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="3cf62-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="3cf62-157">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="3cf62-158">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="3cf62-159">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="3cf62-160">ハッシュ データを結合します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="3cf62-161">フラッシュ ドライブの方法</span><span class="sxs-lookup"><span data-stu-id="3cf62-161">Flash drive method</span></span>

1. <span data-ttu-id="3cf62-162">登録するデバイス以外のデバイスで、USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="3cf62-163">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="3cf62-164">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="3cf62-165">登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。</span><span class="sxs-lookup"><span data-stu-id="3cf62-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="3cf62-166">セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="3cf62-167">USB ドライブを挿入し、Shift + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="3cf62-168">管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="3cf62-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="3cf62-169">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="3cf62-170">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="3cf62-171">USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="3cf62-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="3cf62-172">ハッシュ データを結合します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="3cf62-173">登録が完了するまで、登録するデバイスの電源を入れる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="3cf62-174">ハッシュ データの結合</span><span class="sxs-lookup"><span data-stu-id="3cf62-174">Merge hash data</span></span>

<span data-ttu-id="3cf62-175">手動の PowerShell またはフラッシュ ドライブの方法でハードウェア ハッシュ データを収集した場合は、CSV ファイル内のデータを 1 つのファイルに結合して登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="3cf62-176">簡単に行う PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="3cf62-177">ハッシュ データを 1 つの CSV ファイルにマージすると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="3cf62-178">管理者ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="3cf62-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="3cf62-179">[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側 **のナビゲーション ウィンドウで**[デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="3cf62-180">メニューの [Microsoft Managed Desktop] セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="3cf62-181">[Microsoft Managed Desktop Devices] ワークスペースで、[デバイスの登録] **を** 選択し、新しいデバイスを登録するフライインを開きます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="3cf62-182">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-182">Follow these steps:</span></span>

1. <span data-ttu-id="3cf62-183">[ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="3cf62-184">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-184">Select **Register devices**.</span></span> <span data-ttu-id="3cf62-185">システムは、[デバイス] ブレードのデバイスのリストにデバイスを追加します 。登録保留中 **とマークされます**。</span><span class="sxs-lookup"><span data-stu-id="3cf62-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="3cf62-186">登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="3cf62-187">デバイス登録の進行状況は、メイン ページで監視できます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="3cf62-188">報告される可能性がある状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3cf62-188">Possible states reported there include:</span></span>

| <span data-ttu-id="3cf62-189">状態</span><span class="sxs-lookup"><span data-stu-id="3cf62-189">State</span></span> | <span data-ttu-id="3cf62-190">説明</span><span class="sxs-lookup"><span data-stu-id="3cf62-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="3cf62-191">登録保留中</span><span class="sxs-lookup"><span data-stu-id="3cf62-191">Registration Pending</span></span> | <span data-ttu-id="3cf62-192">登録はまだ行っていません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-192">Registration is not done yet.</span></span> <span data-ttu-id="3cf62-193">後で確認してください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-193">Check back later.</span></span> |
| <span data-ttu-id="3cf62-194">登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="3cf62-194">Registration failed</span></span> | <span data-ttu-id="3cf62-195">登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-195">Registration could not be completed.</span></span> <span data-ttu-id="3cf62-196">詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="3cf62-197">ユーザーの準備ができました</span><span class="sxs-lookup"><span data-stu-id="3cf62-197">Ready for user</span></span> | <span data-ttu-id="3cf62-198">登録が成功し、デバイスをユーザーに配信する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="3cf62-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="3cf62-199">Microsoft Managed Desktop では、初回セットアップをガイドしますので、それ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="3cf62-200">Active</span><span class="sxs-lookup"><span data-stu-id="3cf62-200">Active</span></span> | <span data-ttu-id="3cf62-201">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="3cf62-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3cf62-202">これは、デバイスを定期的に使用している場合も示します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="3cf62-203">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="3cf62-203">Inactive</span></span> | <span data-ttu-id="3cf62-204">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="3cf62-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="3cf62-205">ただし、最近デバイスを使用していない (過去 7 日間)。</span><span class="sxs-lookup"><span data-stu-id="3cf62-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="3cf62-206">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3cf62-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="3cf62-207">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="3cf62-207">Error message</span></span> | <span data-ttu-id="3cf62-208">詳細</span><span class="sxs-lookup"><span data-stu-id="3cf62-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="3cf62-209">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="3cf62-209">Device not found</span></span> | <span data-ttu-id="3cf62-210">提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。</span><span class="sxs-lookup"><span data-stu-id="3cf62-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="3cf62-211">これらの値をデバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="3cf62-212">ハードウェア ハッシュが無効</span><span class="sxs-lookup"><span data-stu-id="3cf62-212">Hardware hash not valid</span></span> | <span data-ttu-id="3cf62-213">このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="3cf62-214">ハードウェア ハッシュを再確認してから、再送信します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="3cf62-215">デバイスが既に登録されている</span><span class="sxs-lookup"><span data-stu-id="3cf62-215">Device already registered</span></span> | <span data-ttu-id="3cf62-216">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="3cf62-216">This device is already registered to your organization.</span></span> <span data-ttu-id="3cf62-217">それ以上のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3cf62-217">No further action required.</span></span> |
| <span data-ttu-id="3cf62-218">別の組織によって要求されたデバイス</span><span class="sxs-lookup"><span data-stu-id="3cf62-218">Device claimed by another organization</span></span> | <span data-ttu-id="3cf62-219">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="3cf62-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="3cf62-220">デバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="3cf62-221">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="3cf62-221">Unexpected error</span></span> | <span data-ttu-id="3cf62-222">要求を自動的に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="3cf62-223">サポートに問い合わせ、要求 ID を入力します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="3cf62-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="3cf62-224">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="3cf62-224">Check the image</span></span>

<span data-ttu-id="3cf62-225">デバイスが Microsoft Managed Desktop パートナー サプライヤーから提供されている場合は、イメージが正しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf62-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="3cf62-226">必要に応じて、自分で画像を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="3cf62-227">作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="3cf62-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="3cf62-228">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="3cf62-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf62-229">デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。</span><span class="sxs-lookup"><span data-stu-id="3cf62-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="3cf62-230">すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動して Windows セットアップ エクスペリエンスを続行できます。</span><span class="sxs-lookup"><span data-stu-id="3cf62-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









