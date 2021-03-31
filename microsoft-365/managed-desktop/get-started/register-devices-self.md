---
title: 新しいデバイスを自分で登録する
description: デバイスを自分で登録して、Microsoft Managed Desktop で管理できるよう
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
ms.openlocfilehash: 3aff3bdc1260e9aa2a23760020aeabd71d6b28fd
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445580"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="42cdc-104">新しいデバイスを自分で登録する</span><span class="sxs-lookup"><span data-stu-id="42cdc-104">Register new devices yourself</span></span>

<span data-ttu-id="42cdc-105">Microsoft Managed Desktop は、新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用できます (再イメージ化が必要になります)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-105">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="42cdc-106">Microsoft Endpoint Manager ポータルで、Microsoft Managed Desktop にデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-106">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="42cdc-107">パートナーと一緒にデバイスを入手する</span><span class="sxs-lookup"><span data-stu-id="42cdc-107">Working with a partner to obtain devices?</span></span> <span data-ttu-id="42cdc-108">その場合は、ハードウェア ハッシュの取得について心配する必要はありません。彼らはその世話をします。</span><span class="sxs-lookup"><span data-stu-id="42cdc-108">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="42cdc-109">パートナーがパートナー センターでユーザーとの関係を確立する [必要があります](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-109">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="42cdc-110">パートナーは、パートナー センターのヘルプ [で詳細を確認できます](/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-110">Your partner can learn more at [Partner Center help](/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="42cdc-111">この関係が確立されると、パートナーはユーザーに代わってデバイスを登録するだけで、それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-111">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="42cdc-112">詳細を確認する場合、またはパートナーに質問がある場合は、「デバイスを登録するパートナー向け [手順」を参照してください](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-112">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="42cdc-113">デバイスが登録された後、イメージの [確認と](#check-the-image) ユーザーへのデバイスの [配信](#deliver-the-device) を続行できます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-113">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="42cdc-114">新しいデバイスを登録する準備をする</span><span class="sxs-lookup"><span data-stu-id="42cdc-114">Prepare to register brand-new devices</span></span>


<span data-ttu-id="42cdc-115">新しいデバイスを手に入したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-115">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="42cdc-116">各デバイスのハードウェア ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-116">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="42cdc-117">ハッシュ データを結合する</span><span class="sxs-lookup"><span data-stu-id="42cdc-117">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="42cdc-118">[Microsoft Managed Desktop にデバイスを登録します](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-118">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="42cdc-119">画像が正しいか確認してください。</span><span class="sxs-lookup"><span data-stu-id="42cdc-119">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="42cdc-120">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="42cdc-120">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="42cdc-121">ハードウェア ハッシュの取得</span><span class="sxs-lookup"><span data-stu-id="42cdc-121">Obtain the hardware hash</span></span>

<span data-ttu-id="42cdc-122">Microsoft Managed Desktop は、ハードウェア ハッシュを参照することによって、各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-122">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="42cdc-123">この情報を取得するには、次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-123">You have three options for getting this information:</span></span>

- <span data-ttu-id="42cdc-124">ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。</span><span class="sxs-lookup"><span data-stu-id="42cdc-124">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="42cdc-125">各デバイスで [Windows PowerShellスクリプト](#powershell-script-method) を実行し、結果をファイルに収集します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-125">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="42cdc-126">各デバイスを起動しますが、Windows セットアップ エクスペリエンスを完了し、リムーバブル フラッシュ ドライブのハッシュ [を収集する必要があります](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-126">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="42cdc-127">PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="42cdc-127">PowerShell script method</span></span>

<span data-ttu-id="42cdc-128">PowerShell ギャラリー web [ サイトGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-128">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="42cdc-129">デバイス ID とハードウェア ハッシュの詳細については [、「Windows Autopilot へのデバイスの追加」を参照してください](/mem/autopilot/add-devices#device-identification)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-129">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="42cdc-130">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-130">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="42cdc-131">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-131">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="42cdc-132">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-132">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4.  <span data-ttu-id="42cdc-133">後続 `powershell -ExecutionPolicy restricted` の制限されていないスクリプトが実行されるのを防ぐために実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-133">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>


#### <a name="flash-drive-method"></a><span data-ttu-id="42cdc-134">フラッシュ ドライブの方法</span><span class="sxs-lookup"><span data-stu-id="42cdc-134">Flash drive method</span></span>

1. <span data-ttu-id="42cdc-135">登録するデバイス以外のデバイスで、USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-135">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="42cdc-136">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-136">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="42cdc-137">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-137">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="42cdc-138">登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。</span><span class="sxs-lookup"><span data-stu-id="42cdc-138">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="42cdc-139">セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-139">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="42cdc-140">USB ドライブを挿入し、Shift + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-140">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="42cdc-141">管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="42cdc-141">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="42cdc-142">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-142">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="42cdc-143">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-143">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="42cdc-144">USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="42cdc-144">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="42cdc-145">登録が完了するまで、登録するデバイスの電源を入れる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-145">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="42cdc-146">ハッシュ データの結合</span><span class="sxs-lookup"><span data-stu-id="42cdc-146">Merge hash data</span></span>

<span data-ttu-id="42cdc-147">登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-147">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="42cdc-148">簡単に行う PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-148">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="42cdc-149">管理者ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="42cdc-149">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="42cdc-150">[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側 **のナビゲーション ウィンドウで**[デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-150">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="42cdc-151">メニューの [Microsoft Managed Desktop] セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="42cdc-151">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="42cdc-152">[Microsoft Managed Desktop Devices] ワークスペースで、[デバイスの登録] **を** 選択し、新しいデバイスを登録するフライインを開きます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-152">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="42cdc-153">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-153">Follow these steps:</span></span>

1. <span data-ttu-id="42cdc-154">[ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-154">In **File upload**, provide a path to the CSV file you created previously.</span></span>
3. <span data-ttu-id="42cdc-155">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="42cdc-155">Select **Register devices**.</span></span> <span data-ttu-id="42cdc-156">システムは、デバイスのリストにデバイスを追加します。 **登録** 保留として **マークされます**。</span><span class="sxs-lookup"><span data-stu-id="42cdc-156">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="42cdc-157">登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-157">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="42cdc-158">デバイス登録の進行状況は、メイン ページで監視できます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-158">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="42cdc-159">報告される可能性がある状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42cdc-159">Possible states reported there include:</span></span>

| <span data-ttu-id="42cdc-160">状態</span><span class="sxs-lookup"><span data-stu-id="42cdc-160">State</span></span> | <span data-ttu-id="42cdc-161">説明</span><span class="sxs-lookup"><span data-stu-id="42cdc-161">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="42cdc-162">登録保留中</span><span class="sxs-lookup"><span data-stu-id="42cdc-162">Registration Pending</span></span> | <span data-ttu-id="42cdc-163">登録はまだ行っていません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-163">Registration is not done yet.</span></span> <span data-ttu-id="42cdc-164">後で確認してください。</span><span class="sxs-lookup"><span data-stu-id="42cdc-164">Check back later.</span></span> |
| <span data-ttu-id="42cdc-165">登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="42cdc-165">Registration failed</span></span> | <span data-ttu-id="42cdc-166">登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-166">Registration could not be completed.</span></span> <span data-ttu-id="42cdc-167">詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42cdc-167">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="42cdc-168">ユーザーの準備ができました</span><span class="sxs-lookup"><span data-stu-id="42cdc-168">Ready for user</span></span> | <span data-ttu-id="42cdc-169">登録が成功し、デバイスをユーザーに配信する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="42cdc-169">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="42cdc-170">Microsoft Managed Desktop では、初回セットアップをガイドしますので、それ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-170">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="42cdc-171">Active</span><span class="sxs-lookup"><span data-stu-id="42cdc-171">Active</span></span> | <span data-ttu-id="42cdc-172">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="42cdc-172">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="42cdc-173">この状態は、デバイスを定期的に使用している場合も示します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-173">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="42cdc-174">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="42cdc-174">Inactive</span></span> | <span data-ttu-id="42cdc-175">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="42cdc-175">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="42cdc-176">ただし、最近デバイスを使用していない (過去 7 日間)。</span><span class="sxs-lookup"><span data-stu-id="42cdc-176">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="42cdc-177">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="42cdc-177">Troubleshooting device registration</span></span>

| <span data-ttu-id="42cdc-178">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="42cdc-178">Error message</span></span> | <span data-ttu-id="42cdc-179">詳細</span><span class="sxs-lookup"><span data-stu-id="42cdc-179">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="42cdc-180">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="42cdc-180">Device not found</span></span> | <span data-ttu-id="42cdc-181">提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。</span><span class="sxs-lookup"><span data-stu-id="42cdc-181">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="42cdc-182">これらの値をデバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-182">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="42cdc-183">ハードウェア ハッシュが無効</span><span class="sxs-lookup"><span data-stu-id="42cdc-183">Hardware hash not valid</span></span> | <span data-ttu-id="42cdc-184">このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="42cdc-185">ハードウェア ハッシュを再確認してから、再送信します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="42cdc-186">デバイスが既に登録されている</span><span class="sxs-lookup"><span data-stu-id="42cdc-186">Device already registered</span></span> | <span data-ttu-id="42cdc-187">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="42cdc-187">This device is already registered to your organization.</span></span> <span data-ttu-id="42cdc-188">それ以上のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="42cdc-188">No further action required.</span></span> |
| <span data-ttu-id="42cdc-189">別の組織によって要求されたデバイス</span><span class="sxs-lookup"><span data-stu-id="42cdc-189">Device claimed by another organization</span></span> | <span data-ttu-id="42cdc-190">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="42cdc-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="42cdc-191">デバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="42cdc-192">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="42cdc-192">Unexpected error</span></span> | <span data-ttu-id="42cdc-193">要求を自動的に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="42cdc-194">サポートに問い合わせ、要求 ID を入力します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="42cdc-194">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="42cdc-195">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="42cdc-195">Check the image</span></span>

<span data-ttu-id="42cdc-196">デバイスが Microsoft Managed Desktop パートナー サプライヤーから提供されている場合は、イメージが正しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="42cdc-196">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="42cdc-197">必要に応じて、自分で画像を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-197">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="42cdc-198">作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="42cdc-198">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="42cdc-199">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="42cdc-199">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42cdc-200">デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。</span><span class="sxs-lookup"><span data-stu-id="42cdc-200">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="42cdc-201">すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動して Windows セットアップ エクスペリエンスを続行できます。</span><span class="sxs-lookup"><span data-stu-id="42cdc-201">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>