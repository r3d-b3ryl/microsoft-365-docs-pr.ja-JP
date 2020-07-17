---
title: 新しいデバイスを自分で登録する
description: Microsoft マネージドデスクトップで管理できるようにデバイスを自分で登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101661"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="9d3fb-103">新しいデバイスを自分で登録する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-103">Register new devices yourself</span></span>

<span data-ttu-id="9d3fb-104">Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="9d3fb-105">Microsoft Managed Desktop 管理ポータルを使用してデバイスを登録できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="9d3fb-106">パートナーと協力してデバイスを入手する方法</span><span class="sxs-lookup"><span data-stu-id="9d3fb-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="9d3fb-107">その場合は、ハードウェアハッシュの取得について心配する必要はありません。そのようにします。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="9d3fb-108">パートナーが [パートナーセンター](https://partner.microsoft.com/dashboard)でお客様との関係を確立していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="9d3fb-109">パートナーが詳細については、 [パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="9d3fb-110">この関係が確立されると、パートナーは単にデバイスを登録するだけで済みます。これ以上の操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="9d3fb-111">詳細を確認する場合、またはパートナーに質問がある場合は、「[パートナーがデバイスを登録する手順](register-devices-partner.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="9d3fb-112">デバイスが登録されたら、[画像の確認](#check-the-image)とユーザーへ[のデバイスの配信](#deliver-the-device)を続行できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="9d3fb-113">ブランドを登録するために準備する-新しいデバイス</span><span class="sxs-lookup"><span data-stu-id="9d3fb-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="9d3fb-114">新しいデバイスを用意したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="9d3fb-115">各デバイスのハードウェアハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="9d3fb-116">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="9d3fb-117">[Microsoft マネージドデスクトップにデバイスを登録](#register-devices)します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="9d3fb-118">画像が正しいことをもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="9d3fb-119">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="9d3fb-120">ハードウェアハッシュを取得する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-120">Obtain the hardware hash</span></span>

<span data-ttu-id="9d3fb-121">Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="9d3fb-122">この情報を取得するには、次の3つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="9d3fb-123">ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="9d3fb-124">各デバイスで[Windows PowerShell スクリプト](#powershell-script-method)を実行し、ファイルに結果を収集します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="9d3fb-125">各デバイスを開始しますが、Windows セットアップの動作を完了せず[に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="9d3fb-126">PowerShell スクリプトメソッド</span><span class="sxs-lookup"><span data-stu-id="9d3fb-126">PowerShell script method</span></span>

1.  <span data-ttu-id="9d3fb-127">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="9d3fb-128">`Install-Script -Name Get-MMDRegistrationInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="9d3fb-129">`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="9d3fb-130">Flash drive メソッド</span><span class="sxs-lookup"><span data-stu-id="9d3fb-130">Flash drive method</span></span>

1. <span data-ttu-id="9d3fb-131">登録している以外のデバイスに USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="9d3fb-132">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="9d3fb-133">`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="9d3fb-134">登録するデバイスを有効にしますが、*セットアップの操作は開始*しないでください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="9d3fb-135">セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="9d3fb-136">USB ドライブを挿入して、SHIFT + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="9d3fb-137">管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="9d3fb-138">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="9d3fb-139">`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="9d3fb-140">USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="9d3fb-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="9d3fb-141">登録が完了するまでは、デバイスの電源を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="9d3fb-142">ハッシュデータを結合する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-142">Merge hash data</span></span>

<span data-ttu-id="9d3fb-143">登録を完了するには、CSV ファイル内のデータを1つのファイルに結合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="9d3fb-144">これを簡単にするためのサンプル PowerShell スクリプトを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="9d3fb-145">デバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-145">Register devices</span></span>

<span data-ttu-id="9d3fb-146">CSV ファイルは、登録用に特定の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="9d3fb-147">前の手順でデータを自分で収集した場合は、ファイルが正しい形式になっている必要があります。業者からファイルを取得する場合は、形式を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="9d3fb-148">便宜上、[サンプルの CSV ファイル](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="9d3fb-149">ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="9d3fb-150">テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="9d3fb-151">サンプルデータの変更を忘れると、登録は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="9d3fb-152">管理ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-152">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="9d3fb-153">Microsoft Managed Desktop[管理ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウで [**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-153">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="9d3fb-154">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="9d3fb-155">[![[デバイスの登録] を選択した後のフライイン、割り当てられたユーザーの列が含まれているデバイスを一覧表示する、シリアル番号、状態、最終確認日、および保存期間](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="9d3fb-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (残念ながら、これは当てはまりません。このメモを削除することはできますが、それについてお客様がチャットできるようになるまで、そのままにしておきます。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="9d3fb-157">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-157">Follow these steps:</span></span>

1. <span data-ttu-id="9d3fb-158">[**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="9d3fb-159">必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="9d3fb-160">これらの値に書式の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="9d3fb-161">[**デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-161">Select **Register devices**.</span></span> <span data-ttu-id="9d3fb-162">システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="9d3fb-163">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="9d3fb-164">メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="9d3fb-165">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-165">Possible states reported there include:</span></span>

| <span data-ttu-id="9d3fb-166">State</span><span class="sxs-lookup"><span data-stu-id="9d3fb-166">State</span></span> | <span data-ttu-id="9d3fb-167">説明</span><span class="sxs-lookup"><span data-stu-id="9d3fb-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="9d3fb-168">登録保留中</span><span class="sxs-lookup"><span data-stu-id="9d3fb-168">Registration pending</span></span> | <span data-ttu-id="9d3fb-169">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-169">Registration is not done yet.</span></span> <span data-ttu-id="9d3fb-170">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-170">Check back later.</span></span> |
| <span data-ttu-id="9d3fb-171">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="9d3fb-171">Registration failed</span></span> | <span data-ttu-id="9d3fb-172">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-172">Registration could not be completed.</span></span> <span data-ttu-id="9d3fb-173">詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="9d3fb-174">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="9d3fb-174">Ready for user</span></span> | <span data-ttu-id="9d3fb-175">登録が成功し、デバイスをエンドユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="9d3fb-176">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="9d3fb-177">Active</span><span class="sxs-lookup"><span data-stu-id="9d3fb-177">Active</span></span> | <span data-ttu-id="9d3fb-178">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="9d3fb-179">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="9d3fb-180">未使用</span><span class="sxs-lookup"><span data-stu-id="9d3fb-180">Inactive</span></span> | <span data-ttu-id="9d3fb-181">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="9d3fb-182">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="9d3fb-183">デバイス登録のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9d3fb-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="9d3fb-184">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="9d3fb-184">Error message</span></span> | <span data-ttu-id="9d3fb-185">詳細</span><span class="sxs-lookup"><span data-stu-id="9d3fb-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="9d3fb-186">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="9d3fb-186">Device not found</span></span> | <span data-ttu-id="9d3fb-187">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="9d3fb-188">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="9d3fb-189">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="9d3fb-189">Hardware hash not valid</span></span> | <span data-ttu-id="9d3fb-190">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="9d3fb-191">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="9d3fb-192">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="9d3fb-192">Device already registered</span></span> | <span data-ttu-id="9d3fb-193">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-193">This device is already registered to your organization.</span></span> <span data-ttu-id="9d3fb-194">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-194">No further action required.</span></span> |
| <span data-ttu-id="9d3fb-195">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="9d3fb-195">Device claimed by another organization</span></span> | <span data-ttu-id="9d3fb-196">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="9d3fb-197">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="9d3fb-198">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="9d3fb-198">Unexpected error</span></span> | <span data-ttu-id="9d3fb-199">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="9d3fb-200">サポートに連絡して、要求 ID を提供します。<requestId></span><span class="sxs-lookup"><span data-stu-id="9d3fb-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="9d3fb-201">画像を確認する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-201">Check the image</span></span>

<span data-ttu-id="9d3fb-202">デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="9d3fb-203">また、必要に応じて、自分で画像を適用することも歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="9d3fb-204">開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="9d3fb-205">デバイスを配信する</span><span class="sxs-lookup"><span data-stu-id="9d3fb-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d3fb-206">ユーザーにデバイスを渡す前に、そのユーザーの[適切なライセンス](../get-ready/prerequisites.md)を取得して適用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="9d3fb-207">すべてのライセンスが適用されている場合は、[デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。</span><span class="sxs-lookup"><span data-stu-id="9d3fb-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






