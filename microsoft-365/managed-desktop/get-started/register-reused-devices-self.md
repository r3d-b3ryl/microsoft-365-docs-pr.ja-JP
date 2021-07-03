---
title: 既存のデバイスをj自分で登録する
description: 再利用済みのデバイスを登録して、ユーザーが自分で管理Microsoft マネージド デスクトップ
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
ms.openlocfilehash: ed254234109bc5ff9865ff49ed3fa0fff8770ab0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286911"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="00822-103">既存のデバイスをj自分で登録する</span><span class="sxs-lookup"><span data-stu-id="00822-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="00822-104">このトピックでは、既に使用しているデバイスを再利用し、デバイスを既存のデバイスに登録する手順Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="00822-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="00822-105">新しいデバイスを操作する場合は、「新しいデバイスを自分で登録する」の手順に[Microsoft マネージド デスクトップ](register-devices-self.md)してください。</span><span class="sxs-lookup"><span data-stu-id="00822-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="00822-106">パートナーのプロセスについては、「デバイスを登録 [するパートナー向け手順」に記載されています](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="00822-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="00822-107">Microsoft マネージド デスクトップ新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用することもできます (再イメージ化が必要になります)。</span><span class="sxs-lookup"><span data-stu-id="00822-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="00822-108">デバイスの登録は、Microsoft マネージド デスクトップポータルMicrosoft エンドポイント マネージャーできます。</span><span class="sxs-lookup"><span data-stu-id="00822-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="00822-109">既存のデバイスを登録する準備</span><span class="sxs-lookup"><span data-stu-id="00822-109">Prepare to register existing devices</span></span>


<span data-ttu-id="00822-110">既存のデバイスを登録するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="00822-111">各デバイスのハードウェア ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="00822-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="00822-112">ハッシュ データを結合する</span><span class="sxs-lookup"><span data-stu-id="00822-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="00822-113">[デバイスを [デバイス] に登録Microsoft マネージド デスクトップ。](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="00822-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="00822-114">画像が正しいか確認してください。</span><span class="sxs-lookup"><span data-stu-id="00822-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="00822-115">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="00822-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="00822-116">ハードウェア ハッシュの取得</span><span class="sxs-lookup"><span data-stu-id="00822-116">Obtain the hardware hash</span></span>

<span data-ttu-id="00822-117">Microsoft マネージド デスクトップハードウェア ハッシュを参照して、各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="00822-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="00822-118">既に使用しているデバイスからこの情報を取得するには、次の 4 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="00822-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="00822-119">ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。</span><span class="sxs-lookup"><span data-stu-id="00822-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="00822-120">で情報を[収集Microsoft Endpoint Configuration Manager。](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="00822-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="00822-121">Active [Directory](#active-directory-powershell-script-method)をWindows PowerShell、または各デバイスで手動でスクリプト[](#manual-powershell-script-method)を実行し、結果をファイルに収集します。</span><span class="sxs-lookup"><span data-stu-id="00822-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="00822-122">各デバイスを起動しますが、セットアップ エクスペリエンスWindows完了して、リムーバブル フラッシュ ドライブでハッシュ[を収集する必要があります](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="00822-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="00822-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="00822-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="00822-124">ユーザーは、Microsoft Endpoint Configuration Managerを使用して、デバイスに登録する既存のデバイスからハードウェア ハッシュを収集Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="00822-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00822-125">この情報を取得するデバイスは、バージョン 1703 以降Windows 10実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="00822-126">これらすべての前提条件を満たしている場合は、次の手順に従って情報を収集する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="00822-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="00822-127">Configuration Manager コンソールで、[監視] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="00822-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="00822-128">[監視] ワークスペースで、[レポート] ノード **を展開し** 、[レポート] を **展開** し、[ハードウェア **- 全般] ノードを選択** します。</span><span class="sxs-lookup"><span data-stu-id="00822-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="00822-129">レポートを実行し **、[Windows情報] をクリックし**、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="00822-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="00822-130">レポート ビューアーで、[エクスポート] **アイコンを** 選択し、CSV (コンマ区切り **) オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="00822-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="00822-131">ファイルを保存した後は、データに登録する予定のデバイスに対して結果をフィルター処理し、Microsoft マネージド デスクトップにデータをアップロードするMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="00822-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="00822-132">[デバイスMicrosoft エンドポイント マネージャー開き、[デバイス]メニューに移動し、[デバイス] セクションMicrosoft マネージド デスクトップデバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="00822-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="00822-133">[+ **デバイスの登録]** を選択すると、フライインが開き、新しいデバイスが登録されます。</span><span class="sxs-lookup"><span data-stu-id="00822-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="00822-134">詳細については [、「管理ポータルを使用してデバイスを登録する](#register-devices-by-using-the-admin-portal) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00822-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="00822-135">Active Directory PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="00822-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="00822-136">Active Directory 環境では、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスから情報をリモート `Get-WindowsAutoPilotInfo` で収集できます。</span><span class="sxs-lookup"><span data-stu-id="00822-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="00822-137">コマンドレットを使用して、カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果 `Get-AD Computer` を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="00822-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="00822-138">続行する前に、まずこれらの前提条件を確認してから、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="00822-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="00822-139">WinRM が有効です。</span><span class="sxs-lookup"><span data-stu-id="00822-139">WinRM is enabled.</span></span>
- <span data-ttu-id="00822-140">登録するデバイスは、ネットワーク上でアクティブです (つまり、切断またはオフにされません)。</span><span class="sxs-lookup"><span data-stu-id="00822-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="00822-141">デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="00822-142">[ファイアウォール] でWindows WMI へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="00822-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="00822-143">そのためには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="00822-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="00822-144">[ファイアウォール] **Windows Defenderパネルを** 開き、[ファイアウォール経由でアプリまたは機能を許可 **する] Windows Defenderします**。</span><span class="sxs-lookup"><span data-stu-id="00822-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>

    2. <span data-ttu-id="00822-145">リスト **Windows管理インストルメンテーション (WMI)** を検索し、プライベートとパブリックの両方を有効にして **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="00822-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1. <span data-ttu-id="00822-146">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="00822-146">Open a PowerShell prompt with administrative rights.</span></span>

2. <span data-ttu-id="00822-147">次 *のいずれかのスクリプト* を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="00822-148">デバイスのエントリがある可能性があるディレクトリにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="00822-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="00822-149">ドメイン サービスとドメイン サービスを含むすべてのディレクトリから各Windows Server Active Directoryエントリを削除Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="00822-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="00822-150">完全に処理するには、削除に数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00822-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="00822-151">デバイスのエントリがある可能性がある管理サービスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="00822-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="00822-152">すべての管理サービスから各デバイスのエントリを削除します(Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows)。</span><span class="sxs-lookup"><span data-stu-id="00822-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="00822-153">完全に処理するには、削除に数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00822-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="00822-154">これで、デバイスの登録 [に進みます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="00822-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="00822-155">手動 PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="00822-155">Manual PowerShell script method</span></span>

1. <span data-ttu-id="00822-156">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="00822-156">Open a PowerShell prompt with administrative rights.</span></span>
2. <span data-ttu-id="00822-157">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3. <span data-ttu-id="00822-158">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="00822-159">ハッシュ データを結合します。</span><span class="sxs-lookup"><span data-stu-id="00822-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="00822-160">フラッシュ ドライブの方法</span><span class="sxs-lookup"><span data-stu-id="00822-160">Flash drive method</span></span>

1. <span data-ttu-id="00822-161">登録するデバイス以外のデバイスで、USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="00822-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="00822-162">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="00822-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="00822-163">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="00822-164">登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。</span><span class="sxs-lookup"><span data-stu-id="00822-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="00822-165">セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="00822-166">USB ドライブを挿入し、Shift + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="00822-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="00822-167">管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="00822-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="00822-168">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="00822-169">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="00822-170">USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="00822-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="00822-171">ハッシュ データを結合します。</span><span class="sxs-lookup"><span data-stu-id="00822-171">Merge the hash data.</span></span>](#merge-hash-data)

> [!IMPORTANT]
> <span data-ttu-id="00822-172">登録が完了するまで、登録するデバイスの電源を入れる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="00822-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 

### <a name="merge-hash-data"></a><span data-ttu-id="00822-173">ハッシュ データの結合</span><span class="sxs-lookup"><span data-stu-id="00822-173">Merge hash data</span></span>

<span data-ttu-id="00822-174">手動の PowerShell またはフラッシュ ドライブの方法でハードウェア ハッシュ データを収集した場合は、CSV ファイル内のデータを 1 つのファイルに結合して登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="00822-175">簡単に行う PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="00822-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="00822-176">ハッシュ データを 1 つの CSV ファイルにマージすると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="00822-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>

## <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="00822-177">管理者ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="00822-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="00822-178">[[Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00822-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="00822-179">メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="00822-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="00822-180">[デバイスのMicrosoft マネージド デスクトップ] ワークスペースで、[デバイスの登録]**を** 選択し、新しいデバイスを登録するフライインを開きます。</span><span class="sxs-lookup"><span data-stu-id="00822-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

<span data-ttu-id="00822-181">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="00822-181">Follow these steps:</span></span>

1. <span data-ttu-id="00822-182">[ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="00822-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="00822-183">ドロップダウン メニュー [でデバイス](../service-description/profiles.md) プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="00822-183">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="00822-184">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="00822-184">Select **Register devices**.</span></span> <span data-ttu-id="00822-185">システムは、[デバイス] ブレードのデバイスのリストにデバイスを追加します 。登録保留中 **とマークされます**。</span><span class="sxs-lookup"><span data-stu-id="00822-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="00822-186">登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="00822-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="00822-187">デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="00822-187">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="00822-188">デバイス登録の進行状況は、メイン ページで監視できます。</span><span class="sxs-lookup"><span data-stu-id="00822-188">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="00822-189">報告される可能性がある状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00822-189">Possible states reported there include:</span></span>

| <span data-ttu-id="00822-190">状態</span><span class="sxs-lookup"><span data-stu-id="00822-190">State</span></span> | <span data-ttu-id="00822-191">説明</span><span class="sxs-lookup"><span data-stu-id="00822-191">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="00822-192">登録保留中</span><span class="sxs-lookup"><span data-stu-id="00822-192">Registration Pending</span></span> | <span data-ttu-id="00822-193">登録はまだ行っていません。</span><span class="sxs-lookup"><span data-stu-id="00822-193">Registration is not done yet.</span></span> <span data-ttu-id="00822-194">後で確認してください。</span><span class="sxs-lookup"><span data-stu-id="00822-194">Check back later.</span></span> |
| <span data-ttu-id="00822-195">登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="00822-195">Registration failed</span></span> | <span data-ttu-id="00822-196">登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-196">Registration could not be completed.</span></span> <span data-ttu-id="00822-197">詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00822-197">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="00822-198">ユーザーの準備ができました</span><span class="sxs-lookup"><span data-stu-id="00822-198">Ready for user</span></span> | <span data-ttu-id="00822-199">登録が成功し、デバイスをユーザーに配信する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="00822-199">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="00822-200">Microsoft マネージド デスクトップセットアップをガイドしますので、それ以上の準備をする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="00822-200">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="00822-201">Active</span><span class="sxs-lookup"><span data-stu-id="00822-201">Active</span></span> | <span data-ttu-id="00822-202">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="00822-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="00822-203">これは、デバイスを定期的に使用している場合も示します。</span><span class="sxs-lookup"><span data-stu-id="00822-203">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="00822-204">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="00822-204">Inactive</span></span> | <span data-ttu-id="00822-205">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="00822-205">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="00822-206">ただし、最近デバイスを使用していない (過去 7 日間)。</span><span class="sxs-lookup"><span data-stu-id="00822-206">However, they have not used the device recently (in the last 7 days).</span></span>  | 

### <a name="troubleshooting-device-registration"></a><span data-ttu-id="00822-207">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="00822-207">Troubleshooting device registration</span></span>

| <span data-ttu-id="00822-208">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="00822-208">Error message</span></span> | <span data-ttu-id="00822-209">詳細</span><span class="sxs-lookup"><span data-stu-id="00822-209">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="00822-210">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="00822-210">Device not found</span></span> | <span data-ttu-id="00822-211">提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。</span><span class="sxs-lookup"><span data-stu-id="00822-211">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="00822-212">これらの値をデバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="00822-212">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="00822-213">ハードウェア ハッシュが無効</span><span class="sxs-lookup"><span data-stu-id="00822-213">Hardware hash not valid</span></span> | <span data-ttu-id="00822-214">このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。</span><span class="sxs-lookup"><span data-stu-id="00822-214">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="00822-215">ハードウェア ハッシュを再確認してから、再送信します。</span><span class="sxs-lookup"><span data-stu-id="00822-215">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="00822-216">デバイスが既に登録されている</span><span class="sxs-lookup"><span data-stu-id="00822-216">Device already registered</span></span> | <span data-ttu-id="00822-217">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="00822-217">This device is already registered to your organization.</span></span> <span data-ttu-id="00822-218">それ以上のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="00822-218">No further action required.</span></span> |
| <span data-ttu-id="00822-219">別の組織によって要求されたデバイス</span><span class="sxs-lookup"><span data-stu-id="00822-219">Device claimed by another organization</span></span> | <span data-ttu-id="00822-220">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="00822-220">This device has already been claimed by another organization.</span></span> <span data-ttu-id="00822-221">デバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="00822-221">Check with your device supplier.</span></span> |
| <span data-ttu-id="00822-222">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="00822-222">Unexpected error</span></span> | <span data-ttu-id="00822-223">要求を自動的に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-223">Your request could not be automatically processed.</span></span> <span data-ttu-id="00822-224">サポートに問い合わせ、要求 ID を入力します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="00822-224">Contact Support and provide the Request ID: <requestId></span></span> |

## <a name="check-the-image"></a><span data-ttu-id="00822-225">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="00822-225">Check the image</span></span>

<span data-ttu-id="00822-226">デバイスがパートナー サプライヤーからMicrosoft マネージド デスクトップ場合、イメージは正しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="00822-226">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="00822-227">必要に応じて、自分で画像を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="00822-227">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="00822-228">作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="00822-228">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

## <a name="deliver-the-device"></a><span data-ttu-id="00822-229">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="00822-229">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00822-230">デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。</span><span class="sxs-lookup"><span data-stu-id="00822-230">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="00822-231">すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動し、デバイスのセットアップ エクスペリエンスをWindowsできます。</span><span class="sxs-lookup"><span data-stu-id="00822-231">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>
