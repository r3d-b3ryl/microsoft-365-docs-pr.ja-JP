---
title: 新しいデバイスを自分で登録する
description: デバイスを自分で登録して、デバイスをユーザーが管理Microsoft マネージド デスクトップ
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
ms.openlocfilehash: 850d7e6692d3ccbfda6e15c8d5ca95301bd4d094
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245614"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="6914d-103">新しいデバイスを自分で登録する</span><span class="sxs-lookup"><span data-stu-id="6914d-103">Register new devices yourself</span></span>

<span data-ttu-id="6914d-104">Microsoft マネージド デスクトップ新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用することもできます (再イメージ化が必要になります)。</span><span class="sxs-lookup"><span data-stu-id="6914d-104">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="6914d-105">デバイスの登録は、Microsoft マネージド デスクトップポータルMicrosoft エンドポイント マネージャーできます。</span><span class="sxs-lookup"><span data-stu-id="6914d-105">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

> [!NOTE]
> <span data-ttu-id="6914d-106">パートナーと一緒にデバイスを入手する</span><span class="sxs-lookup"><span data-stu-id="6914d-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="6914d-107">その場合は、ハードウェア ハッシュの取得について心配する必要はありません。彼らはその世話をします。</span><span class="sxs-lookup"><span data-stu-id="6914d-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="6914d-108">パートナーがパートナー センターでユーザーとの関係を確立する [必要があります](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="6914d-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="6914d-109">パートナーは、パートナー センターのヘルプ [で詳細を確認できます](/partner-center/request-a-relationship-with-a-customer)。</span><span class="sxs-lookup"><span data-stu-id="6914d-109">Your partner can learn more at [Partner Center help](/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="6914d-110">この関係が確立されると、パートナーはユーザーに代わってデバイスを登録するだけで、それ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6914d-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="6914d-111">詳細を確認する場合、またはパートナーに質問がある場合は、「デバイスを登録するパートナー向け [手順」を参照してください](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="6914d-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="6914d-112">デバイスが登録された後、イメージの [確認と](#check-the-image) ユーザーへのデバイスの [配信](#deliver-the-device) を続行できます。</span><span class="sxs-lookup"><span data-stu-id="6914d-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>



## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="6914d-113">新しいデバイスを登録する準備をする</span><span class="sxs-lookup"><span data-stu-id="6914d-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="6914d-114">新しいデバイスを手に入したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="6914d-115">各デバイスのハードウェア ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="6914d-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="6914d-116">ハッシュ データを結合する</span><span class="sxs-lookup"><span data-stu-id="6914d-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="6914d-117">[デバイスを [デバイス] に登録Microsoft マネージド デスクトップ。](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="6914d-117">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="6914d-118">画像が正しいか確認してください。</span><span class="sxs-lookup"><span data-stu-id="6914d-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="6914d-119">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="6914d-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="6914d-120">ハードウェア ハッシュの取得</span><span class="sxs-lookup"><span data-stu-id="6914d-120">Obtain the hardware hash</span></span>

<span data-ttu-id="6914d-121">Microsoft マネージド デスクトップハードウェア ハッシュを参照して、各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="6914d-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="6914d-122">この情報を取得するには、次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6914d-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="6914d-123">ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。</span><span class="sxs-lookup"><span data-stu-id="6914d-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="6914d-124">各デバイス[Windows PowerShellスクリプト](#powershell-script-method)を実行し、結果をファイルに収集します。</span><span class="sxs-lookup"><span data-stu-id="6914d-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="6914d-125">各デバイスを起動しますが、セットアップ エクスペリエンスWindows完了して、リムーバブル フラッシュ ドライブでハッシュ[を収集する必要があります](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="6914d-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="6914d-126">PowerShell スクリプト メソッド</span><span class="sxs-lookup"><span data-stu-id="6914d-126">PowerShell script method</span></span>

<span data-ttu-id="6914d-127">PowerShell ギャラリー web [ サイトGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell スクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6914d-127">You can use the [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell script on the PowerShell Gallery website.</span></span> <span data-ttu-id="6914d-128">デバイス ID とハードウェア ハッシュの詳細については、「デバイスを[Autopilot に追加Windows参照してください](/mem/autopilot/add-devices#device-identification)。</span><span class="sxs-lookup"><span data-stu-id="6914d-128">For more information about device identification and hardware hash, see [Adding devices to Windows Autopilot](/mem/autopilot/add-devices#device-identification).</span></span>

1.  <span data-ttu-id="6914d-129">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6914d-129">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="6914d-130">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-130">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="6914d-131">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-131">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4.  <span data-ttu-id="6914d-132">後続 `powershell -ExecutionPolicy restricted` の制限されていないスクリプトが実行されるのを防ぐために実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-132">Run `powershell -ExecutionPolicy restricted` to prevent subsequent unrestricted scripts from running.</span></span>


#### <a name="flash-drive-method"></a><span data-ttu-id="6914d-133">フラッシュ ドライブの方法</span><span class="sxs-lookup"><span data-stu-id="6914d-133">Flash drive method</span></span>

1. <span data-ttu-id="6914d-134">登録するデバイス以外のデバイスで、USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6914d-134">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="6914d-135">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6914d-135">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="6914d-136">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-136">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="6914d-137">登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。</span><span class="sxs-lookup"><span data-stu-id="6914d-137">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="6914d-138">セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6914d-138">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="6914d-139">USB ドライブを挿入し、Shift + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6914d-139">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="6914d-140">管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。</span><span class="sxs-lookup"><span data-stu-id="6914d-140">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="6914d-141">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-141">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="6914d-142">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-142">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="6914d-143">USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="6914d-143">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="6914d-144">登録が完了するまで、登録するデバイスの電源を入れる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6914d-144">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="6914d-145">ハッシュ データの結合</span><span class="sxs-lookup"><span data-stu-id="6914d-145">Merge hash data</span></span>

<span data-ttu-id="6914d-146">登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6914d-146">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="6914d-147">簡単に行う PowerShell スクリプトの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6914d-147">Here's a sample PowerShell script to make it easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="6914d-148">管理者ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="6914d-148">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="6914d-149">[[Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6914d-149">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="6914d-150">メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="6914d-150">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="6914d-151">[デバイスのMicrosoft マネージド デスクトップ] ワークスペースで、[デバイスの登録]**を** 選択し、新しいデバイスを登録するフライインを開きます。</span><span class="sxs-lookup"><span data-stu-id="6914d-151">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="6914d-152">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6914d-152">Follow these steps:</span></span>

1. <span data-ttu-id="6914d-153">[ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6914d-153">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="6914d-154">ドロップダウン メニュー [でデバイス](../service-description/profiles.md) プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="6914d-154">Select a [device profile](../service-description/profiles.md) in the drop-down menu.</span></span>
3. <span data-ttu-id="6914d-155">[デバイス **の登録] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="6914d-155">Select **Register devices**.</span></span> <span data-ttu-id="6914d-156">システムは、デバイスのリストにデバイスを追加します。 **登録** 保留として **マークされます**。</span><span class="sxs-lookup"><span data-stu-id="6914d-156">The system will add the devices to your list of devices on **Devices**, marked as **Registration Pending**.</span></span> <span data-ttu-id="6914d-157">登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6914d-157">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>

> [!NOTE]
> <span data-ttu-id="6914d-158">デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6914d-158">If you manually change the Azure Active Directory (AAD) group membership of a device, it will be automatically reassigned to the group for its device profile and removed from any conflicting groups.</span></span>

<span data-ttu-id="6914d-159">デバイス登録の進行状況は、メイン ページで監視できます。</span><span class="sxs-lookup"><span data-stu-id="6914d-159">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="6914d-160">報告される可能性がある状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6914d-160">Possible states reported there include:</span></span>

| <span data-ttu-id="6914d-161">状態</span><span class="sxs-lookup"><span data-stu-id="6914d-161">State</span></span> | <span data-ttu-id="6914d-162">説明</span><span class="sxs-lookup"><span data-stu-id="6914d-162">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="6914d-163">登録保留中</span><span class="sxs-lookup"><span data-stu-id="6914d-163">Registration Pending</span></span> | <span data-ttu-id="6914d-164">登録はまだ行っていません。</span><span class="sxs-lookup"><span data-stu-id="6914d-164">Registration is not done yet.</span></span> <span data-ttu-id="6914d-165">後で確認してください。</span><span class="sxs-lookup"><span data-stu-id="6914d-165">Check back later.</span></span> |
| <span data-ttu-id="6914d-166">登録に失敗しました</span><span class="sxs-lookup"><span data-stu-id="6914d-166">Registration failed</span></span> | <span data-ttu-id="6914d-167">登録を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6914d-167">Registration could not be completed.</span></span> <span data-ttu-id="6914d-168">詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6914d-168">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="6914d-169">ユーザーの準備ができました</span><span class="sxs-lookup"><span data-stu-id="6914d-169">Ready for user</span></span> | <span data-ttu-id="6914d-170">登録が成功し、デバイスをユーザーに配信する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="6914d-170">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="6914d-171">Microsoft マネージド デスクトップセットアップをガイドしますので、それ以上の準備をする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6914d-171">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="6914d-172">Active</span><span class="sxs-lookup"><span data-stu-id="6914d-172">Active</span></span> | <span data-ttu-id="6914d-173">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="6914d-173">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="6914d-174">この状態は、デバイスを定期的に使用している場合も示します。</span><span class="sxs-lookup"><span data-stu-id="6914d-174">This state also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="6914d-175">非アクティブ</span><span class="sxs-lookup"><span data-stu-id="6914d-175">Inactive</span></span> | <span data-ttu-id="6914d-176">デバイスがユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="6914d-176">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="6914d-177">ただし、最近デバイスを使用していない (過去 7 日間)。</span><span class="sxs-lookup"><span data-stu-id="6914d-177">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="6914d-178">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6914d-178">Troubleshooting device registration</span></span>

| <span data-ttu-id="6914d-179">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="6914d-179">Error message</span></span> | <span data-ttu-id="6914d-180">詳細</span><span class="sxs-lookup"><span data-stu-id="6914d-180">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="6914d-181">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="6914d-181">Device not found</span></span> | <span data-ttu-id="6914d-182">提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。</span><span class="sxs-lookup"><span data-stu-id="6914d-182">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="6914d-183">これらの値をデバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="6914d-183">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="6914d-184">ハードウェア ハッシュが無効</span><span class="sxs-lookup"><span data-stu-id="6914d-184">Hardware hash not valid</span></span> | <span data-ttu-id="6914d-185">このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。</span><span class="sxs-lookup"><span data-stu-id="6914d-185">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="6914d-186">ハードウェア ハッシュを再確認してから、再送信します。</span><span class="sxs-lookup"><span data-stu-id="6914d-186">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="6914d-187">デバイスが既に登録されている</span><span class="sxs-lookup"><span data-stu-id="6914d-187">Device already registered</span></span> | <span data-ttu-id="6914d-188">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="6914d-188">This device is already registered to your organization.</span></span> <span data-ttu-id="6914d-189">それ以上のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6914d-189">No further action required.</span></span> |
| <span data-ttu-id="6914d-190">別の組織によって要求されたデバイス</span><span class="sxs-lookup"><span data-stu-id="6914d-190">Device claimed by another organization</span></span> | <span data-ttu-id="6914d-191">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="6914d-191">This device has already been claimed by another organization.</span></span> <span data-ttu-id="6914d-192">デバイスのサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="6914d-192">Check with your device supplier.</span></span> |
| <span data-ttu-id="6914d-193">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="6914d-193">Unexpected error</span></span> | <span data-ttu-id="6914d-194">要求を自動的に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6914d-194">Your request could not be automatically processed.</span></span> <span data-ttu-id="6914d-195">サポートに問い合わせ、要求 ID を入力します。 <requestId></span><span class="sxs-lookup"><span data-stu-id="6914d-195">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="6914d-196">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="6914d-196">Check the image</span></span>

<span data-ttu-id="6914d-197">デバイスがパートナー サプライヤーからMicrosoft マネージド デスクトップ場合、イメージは正しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="6914d-197">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="6914d-198">必要に応じて、自分で画像を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6914d-198">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="6914d-199">作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="6914d-199">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="autopilot-group-tag"></a><span data-ttu-id="6914d-200">Autopilot グループ タグ</span><span class="sxs-lookup"><span data-stu-id="6914d-200">Autopilot group tag</span></span>

<span data-ttu-id="6914d-201">管理者ポータルを使用してデバイスを登録すると、自動パイロット **グループ タグ** Microsoft365Managed_Autopilot自動的に割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="6914d-201">When you use the Admin portal to register devices, we automatically assign the **Microsoft365Managed_Autopilot** Autopilot Group Tag.</span></span>
<span data-ttu-id="6914d-202">サービスは、すべてのデバイスMicrosoft マネージド デスクトップ毎日監視し、グループ タグをまだ持ってないデバイスに割り当てします。</span><span class="sxs-lookup"><span data-stu-id="6914d-202">The service monitors all Microsoft Managed Desktop devices daily and assigns the group tag to any that don't already have it.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="6914d-203">デバイスの配信</span><span class="sxs-lookup"><span data-stu-id="6914d-203">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6914d-204">デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。</span><span class="sxs-lookup"><span data-stu-id="6914d-204">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="6914d-205">すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動し、デバイスのセットアップ エクスペリエンスをWindowsできます。</span><span class="sxs-lookup"><span data-stu-id="6914d-205">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>
