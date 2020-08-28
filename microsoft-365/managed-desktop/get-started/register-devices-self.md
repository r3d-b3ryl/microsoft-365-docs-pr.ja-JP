---
title: 新しいデバイスを自分で登録する
description: Microsoft マネージドデスクトップで管理できるようにデバイスを自分で登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: e433b10b66b5e4f061227eae7e944c7fd19e2260
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289759"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="a9c28-103">新しいデバイスを自分で登録する</span><span class="sxs-lookup"><span data-stu-id="a9c28-103">Register new devices yourself</span></span>

<span data-ttu-id="a9c28-104">Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a9c28-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="a9c28-105">Microsoft Managed Desktop 管理ポータルを使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c28-106">パートナーと協力してデバイスを入手する方法</span><span class="sxs-lookup"><span data-stu-id="a9c28-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="a9c28-107">その場合は、ハードウェアハッシュの取得について心配する必要はありません。そのようにします。</span><span class="sxs-lookup"><span data-stu-id="a9c28-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="a9c28-108">パートナーが [パートナーセンター](https://partner.microsoft.com/dashboard)でお客様との関係を確立していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="a9c28-109">パートナーが詳細については、 [パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="a9c28-110">この関係が確立されると、パートナーは単にデバイスを登録するだけで済みます。これ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a9c28-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="a9c28-111">詳細を確認する場合、またはパートナーに質問がある場合は、「 [パートナーがデバイスを登録する手順](register-devices-partner.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="a9c28-112">デバイスが登録されたら、 [画像の確認](#check-the-image) とユーザーへ [のデバイスの配信](#deliver-the-device) を続行できます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="a9c28-113">ブランドを登録するために準備する-新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="a9c28-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="a9c28-114">新しいデバイスを用意したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="a9c28-115">各デバイスのハードウェアハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="a9c28-116">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="a9c28-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="a9c28-117">[Microsoft マネージドデスクトップにデバイスを登録](#register-devices-by-using-the-admin-portal)します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="a9c28-118">画像が正しいことをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="a9c28-119">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="a9c28-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="a9c28-120">ハードウェアハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="a9c28-120">Obtain the hardware hash</span></span>

<span data-ttu-id="a9c28-121">Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="a9c28-122">この情報を取得するには、次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a9c28-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="a9c28-123">ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="a9c28-124">各デバイスで [Windows PowerShell スクリプト](#powershell-script-method) を実行し、ファイルに結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="a9c28-125">各デバイスを開始しますが、Windows セットアップの動作を完了せず [に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="a9c28-126">PowerShell スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="a9c28-126">PowerShell script method</span></span>

<span data-ttu-id="a9c28-127">PowerShell Gallery web サイトで [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="a9c28-128">デバイス id とハードウェアハッシュの詳細については、「 [Windows 自動操縦にデバイスを追加する](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="a9c28-129">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="a9c28-130">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="a9c28-131">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="a9c28-132">Flash drive メソッド</span><span class="sxs-lookup"><span data-stu-id="a9c28-132">Flash drive method</span></span>

1. <span data-ttu-id="a9c28-133">登録している以外のデバイスに USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-133">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="a9c28-134">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-134">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="a9c28-135">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-135">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="a9c28-136">登録するデバイスを有効にしますが、 *セットアップの操作は開始*しないでください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-136">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="a9c28-137">セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9c28-137">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="a9c28-138">USB ドライブを挿入して、SHIFT + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-138">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="a9c28-139">管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-139">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="a9c28-140">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-140">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="a9c28-141">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-141">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="a9c28-142">USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。 `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="a9c28-142">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="a9c28-143">登録が完了するまでは、デバイスの電源を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-143">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="a9c28-144">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="a9c28-144">Merge hash data</span></span>

<span data-ttu-id="a9c28-145">登録を完了するには、CSV ファイル内のデータを1つのファイルに結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9c28-145">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="a9c28-146">これを簡単にするためのサンプル PowerShell スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-146">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="a9c28-147">管理ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="a9c28-147">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="a9c28-148">Microsoft Managed Desktop [管理ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウで [ **デバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-148">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="a9c28-149">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-149">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="a9c28-150">[![[デバイスの登録] を選択した後のフライイン、割り当てられたユーザーの列が含まれているデバイスを一覧表示する、シリアル番号、状態、最終確認日、および保存期間](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="a9c28-150">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="a9c28-151">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-151">Follow these steps:</span></span>

1. <span data-ttu-id="a9c28-152">[ **ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-152">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="a9c28-153">[ **デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-153">Select **Register devices**.</span></span> <span data-ttu-id="a9c28-154">デバイスは、 **AutopilotRegistrationRequested**としてマークされているデバイス**ブレード**上のデバイスの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-154">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="a9c28-155">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは **ユーザーのための** 準備完了として表示され、ユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-155">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="a9c28-156">メインの **Microsoft Managed Desktop-Devices** ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-156">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="a9c28-157">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9c28-157">Possible states reported there include:</span></span>

| <span data-ttu-id="a9c28-158">State</span><span class="sxs-lookup"><span data-stu-id="a9c28-158">State</span></span> | <span data-ttu-id="a9c28-159">説明</span><span class="sxs-lookup"><span data-stu-id="a9c28-159">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="a9c28-160">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="a9c28-160">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="a9c28-161">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="a9c28-161">Registration is not done yet.</span></span> <span data-ttu-id="a9c28-162">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-162">Check back later.</span></span> |
| <span data-ttu-id="a9c28-163">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="a9c28-163">Registration failed</span></span> | <span data-ttu-id="a9c28-164">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9c28-164">Registration could not be completed.</span></span> <span data-ttu-id="a9c28-165">詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-165">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="a9c28-166">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="a9c28-166">Ready for user</span></span> | <span data-ttu-id="a9c28-167">登録が成功し、デバイスをユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a9c28-167">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="a9c28-168">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a9c28-168">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="a9c28-169">Active</span><span class="sxs-lookup"><span data-stu-id="a9c28-169">Active</span></span> | <span data-ttu-id="a9c28-170">デバイスはユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-170">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="a9c28-171">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-171">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="a9c28-172">未使用</span><span class="sxs-lookup"><span data-stu-id="a9c28-172">Inactive</span></span> | <span data-ttu-id="a9c28-173">デバイスはユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-173">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="a9c28-174">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="a9c28-174">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="a9c28-175">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a9c28-175">Troubleshooting device registration</span></span>

| <span data-ttu-id="a9c28-176">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="a9c28-176">Error message</span></span> | <span data-ttu-id="a9c28-177">詳細</span><span class="sxs-lookup"><span data-stu-id="a9c28-177">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="a9c28-178">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="a9c28-178">Device not found</span></span> | <span data-ttu-id="a9c28-179">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9c28-179">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="a9c28-180">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-180">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="a9c28-181">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="a9c28-181">Hardware hash not valid</span></span> | <span data-ttu-id="a9c28-182">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9c28-182">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="a9c28-183">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-183">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="a9c28-184">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="a9c28-184">Device already registered</span></span> | <span data-ttu-id="a9c28-185">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-185">This device is already registered to your organization.</span></span> <span data-ttu-id="a9c28-186">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a9c28-186">No further action required.</span></span> |
| <span data-ttu-id="a9c28-187">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="a9c28-187">Device claimed by another organization</span></span> | <span data-ttu-id="a9c28-188">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-188">This device has already been claimed by another organization.</span></span> <span data-ttu-id="a9c28-189">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-189">Check with your device supplier.</span></span> |
| <span data-ttu-id="a9c28-190">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="a9c28-190">Unexpected error</span></span> | <span data-ttu-id="a9c28-191">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a9c28-191">Your request could not be automatically processed.</span></span> <span data-ttu-id="a9c28-192">サポートに連絡して、要求 ID を提供します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="a9c28-192">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="a9c28-193">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="a9c28-193">Check the image</span></span>

<span data-ttu-id="a9c28-194">デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-194">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="a9c28-195">また、必要に応じて、自分で画像を適用することも歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="a9c28-195">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="a9c28-196">開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9c28-196">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="a9c28-197">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="a9c28-197">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9c28-198">ユーザーにデバイスを渡す前に、そのユーザーの [適切なライセンス](../get-ready/prerequisites.md) を取得して適用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9c28-198">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="a9c28-199">すべてのライセンスが適用されている場合は、 [デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="a9c28-199">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






