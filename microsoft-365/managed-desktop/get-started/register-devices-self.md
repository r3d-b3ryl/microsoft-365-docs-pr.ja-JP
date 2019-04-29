---
title: Microsoft マネージドデスクトップのデバイスを自分で登録する
description: Microsoft マネージドデスクトップで管理できるようにデバイスを自分で登録する
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 02b3b7ab32ff92304ab27ca8e8c805ade803c971
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400078"
---
# <a name="register-devices-in-microsoft-managed-desktop"></a><span data-ttu-id="56a82-103">Microsoft マネージドデスクトップでのデバイスの登録</span><span class="sxs-lookup"><span data-stu-id="56a82-103">Register devices in Microsoft Managed Desktop</span></span>

>[!NOTE]
><span data-ttu-id="56a82-104">このトピックでは、自分でデバイスを登録する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="56a82-104">This topic describes the steps for you to register devices on your own.</span></span> <span data-ttu-id="56a82-105">パートナー向けのプロセスについては、「 [Register devices in Microsoft Managed Desktop in a パートナー](register-devices-partner.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-105">The process for Partners is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="56a82-106">Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="56a82-106">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="56a82-107">Azure Portal で Microsoft Managed Desktop を使用してデバイスを登録するか、API を使用して柔軟性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="56a82-107">You can register devices by using Microsoft Managed Desktop on the Azure Portal or gain flexibility by using an API.</span></span>

## <a name="prepare-to-register-devices"></a><span data-ttu-id="56a82-108">デバイスを登録するための準備</span><span class="sxs-lookup"><span data-stu-id="56a82-108">Prepare to register devices</span></span>

<span data-ttu-id="56a82-109">使用するデバイスをまだ入手していない場合は、 [Microsoft Managed Desktop devices](../service-description/device-list.md)をチェックし、デバイスパートナーと連携して、サポートされているデバイスを調達してください。</span><span class="sxs-lookup"><span data-stu-id="56a82-109">If you haven't already obtained the devices you want to use, check [Microsoft Managed Desktop devices](../service-description/device-list.md) and work with a device partner to procure supported devices.</span></span>

<span data-ttu-id="56a82-110">完全に新しいデバイスで作業しているか、または既存のデバイスを再利用しているかにかかわらず、Microsoft マネージドデスクトップに登録するには、**コンマ区切り (CSV) ファイル**を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56a82-110">Whether you're working with completely new devices or re-using existing ones, to register them with Microsoft Managed Desktop, you'll need to prepare a **comma-delimited (CSV) file**.</span></span> <span data-ttu-id="56a82-111">このファイルには、各デバイスの以下の情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="56a82-111">This file should include the following information for each device:</span></span>

>[!NOTE]
><span data-ttu-id="56a82-112">この形式は、セルフサービスの登録にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="56a82-112">This format is for self-service registration only.</span></span> <span data-ttu-id="56a82-113">パートナーを使用するための形式は、「 [Microsoft Managed Desktop の Register devices](register-devices-partner.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-113">The format Partners should use is documented in [Register devices in Microsoft Managed Desktop for Partners](register-devices-partner.md).</span></span>

<span data-ttu-id="56a82-114">これらの値は表示のために使用され、デバイスのプロパティを正確に照合する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="56a82-114">These values are used for display purposes, and don't need to match properties from the device exactly.</span></span>
- <span data-ttu-id="56a82-115">デバイスの製造元 (例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="56a82-115">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="56a82-116">デバイスモデル (例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="56a82-116">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="56a82-117">デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="56a82-117">Device serial number</span></span>

<span data-ttu-id="56a82-118">ハードウェアハッシュは、完全に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="56a82-118">The hardware hash must be an exact match.</span></span>
- <span data-ttu-id="56a82-119">ハードウェアハッシュ</span><span class="sxs-lookup"><span data-stu-id="56a82-119">Hardware hash</span></span>

<span data-ttu-id="56a82-120">ハードウェアハッシュを取得するには、OEM またはパートナーからサポートを依頼するか、デバイスごとに次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-120">To obtain the hardware hash you can ask for help from your OEM or Partner, or follow these steps for each device:</span></span>

1.  <span data-ttu-id="56a82-121">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="56a82-121">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="56a82-122">`Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-122">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="56a82-123">`powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-123">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutopilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>


<span data-ttu-id="56a82-124">または、次の手順を新しいデバイスで実行することもできます (OOBE を初めて実行する前に)。</span><span class="sxs-lookup"><span data-stu-id="56a82-124">Alternately, you can follow these steps on a brand-new device (before going through OOBE for the first time):</span></span>

1. <span data-ttu-id="56a82-125">別のデバイスで、USB ドライブを挿入します。</span><span class="sxs-lookup"><span data-stu-id="56a82-125">On a different device, insert a USB drive.</span></span>
2. <span data-ttu-id="56a82-126">管理者権限を持つ PowerShell プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="56a82-126">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="56a82-127">`Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-127">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="56a82-128">ターゲットデバイスをオンにします。ただし、セットアップの操作は開始しません。</span><span class="sxs-lookup"><span data-stu-id="56a82-128">Turn on the target device, but do not start the setup experience.</span></span> <span data-ttu-id="56a82-129">セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="56a82-129">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="56a82-130">USB ドライブを挿入して、SHIFT + F10 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="56a82-130">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="56a82-131">管理者権限で PowerShell プロンプトを開き、を実行`cd <pathToUsb>`します。</span><span class="sxs-lookup"><span data-stu-id="56a82-131">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="56a82-132">`Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-132">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="56a82-133">`.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-133">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
3. <span data-ttu-id="56a82-134">USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="56a82-134">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="56a82-135">ターゲットデバイスの登録が完了するまで、もう一度電源を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="56a82-135">Do not power on the target device again until you've completed registration for it.</span></span> 

>[!NOTE]
><span data-ttu-id="56a82-136">便宜上、この CSV ファイルの[テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="56a82-136">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="56a82-137">ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="56a82-137">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="56a82-138">テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。</span><span class="sxs-lookup"><span data-stu-id="56a82-138">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="56a82-139">サンプルデータの変更を忘れると、登録は失敗します。</span><span class="sxs-lookup"><span data-stu-id="56a82-139">If you forget to change any of the sample data, registration will fail.</span></span>   


## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="56a82-140">Azure ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="56a82-140">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="56a82-141">Microsoft マネージドデスクトップの[Azure ポータル](https://aka.ms/mmdportal)で、左側のナビゲーションウィンドウの [**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56a82-141">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="56a82-142">[ **+ デバイスの登録**] を選択します。フライインが開きます。</span><span class="sxs-lookup"><span data-stu-id="56a82-142">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="56a82-143">[![[デバイスの登録] を選択した後のフライイン](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="56a82-143">[![Fly-in after selecting Register devices](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (残念ながら、これは当てはまりません。このメモを削除することはできますが、それについてお客様がチャットできるようになるまで、そのままにしておきます。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="56a82-145">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="56a82-145">Follow these steps:</span></span>

1. <span data-ttu-id="56a82-146">[**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="56a82-146">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="56a82-147">必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="56a82-147">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="56a82-148">これらの値に書式の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="56a82-148">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="56a82-149">[**デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="56a82-149">Select **Register devices**.</span></span> <span data-ttu-id="56a82-150">システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="56a82-150">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="56a82-151">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="56a82-151">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="56a82-152">メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="56a82-152">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="56a82-153">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56a82-153">Possible states reported there include:</span></span>

| <span data-ttu-id="56a82-154">State</span><span class="sxs-lookup"><span data-stu-id="56a82-154">State</span></span> | <span data-ttu-id="56a82-155">説明</span><span class="sxs-lookup"><span data-stu-id="56a82-155">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="56a82-156">登録保留中</span><span class="sxs-lookup"><span data-stu-id="56a82-156">Registration pending</span></span> | <span data-ttu-id="56a82-157">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="56a82-157">Registration is not done yet.</span></span> <span data-ttu-id="56a82-158">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="56a82-158">Check back later.</span></span> |
| <span data-ttu-id="56a82-159">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="56a82-159">Registration failed</span></span> | <span data-ttu-id="56a82-160">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="56a82-160">Registration could not be completed.</span></span> <span data-ttu-id="56a82-161">詳細については、「[トラブルシューティング](register-devices-self.md#troubleshooting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56a82-161">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="56a82-162">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="56a82-162">Ready for user</span></span> | <span data-ttu-id="56a82-163">登録が成功し、デバイスをエンドユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="56a82-163">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="56a82-164">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="56a82-164">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="56a82-165">Active</span><span class="sxs-lookup"><span data-stu-id="56a82-165">Active</span></span> | <span data-ttu-id="56a82-166">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-166">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="56a82-167">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="56a82-167">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="56a82-168">未使用</span><span class="sxs-lookup"><span data-stu-id="56a82-168">Inactive</span></span> | <span data-ttu-id="56a82-169">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-169">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="56a82-170">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="56a82-170">However, they have not used the device recently (in the last 7 days).</span></span>  | 


## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="56a82-171">API を使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="56a82-171">Register devices by using an API</span></span>

<span data-ttu-id="56a82-172">REST API を使用すると、頻繁に独立したデバイスの登録により柔軟性と再現性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="56a82-172">A REST API is available to allow you greater flexibility and repeatability with frequent separate device registrations.</span></span> <span data-ttu-id="56a82-173">現時点では、この API を使用するには、Microsoft 連絡先からサポートを依頼して、この機能のプレビューに参加してください。</span><span class="sxs-lookup"><span data-stu-id="56a82-173">Currently, to use the API, ask for help from your Microsoft contact to join a preview of this capability.</span></span>



## <a name="troubleshooting"></a><span data-ttu-id="56a82-174">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="56a82-174">Troubleshooting</span></span>

| <span data-ttu-id="56a82-175">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="56a82-175">Error message</span></span> | <span data-ttu-id="56a82-176">詳細</span><span class="sxs-lookup"><span data-stu-id="56a82-176">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="56a82-177">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="56a82-177">Device not found</span></span> | <span data-ttu-id="56a82-178">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="56a82-178">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="56a82-179">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="56a82-179">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="56a82-180">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="56a82-180">Device not found</span></span> | <span data-ttu-id="56a82-181">このデバイスは組織内に存在しないため、登録を解除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="56a82-181">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="56a82-182">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="56a82-182">No further action required.</span></span> |
| <span data-ttu-id="56a82-183">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="56a82-183">Hardware hash not valid</span></span> | <span data-ttu-id="56a82-184">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="56a82-184">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="56a82-185">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="56a82-185">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="56a82-186">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="56a82-186">Device already registered</span></span> | <span data-ttu-id="56a82-187">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-187">This device is already registered to your organization.</span></span> <span data-ttu-id="56a82-188">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="56a82-188">No further action required.</span></span> |
| <span data-ttu-id="56a82-189">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="56a82-189">Device claimed by another organization</span></span> | <span data-ttu-id="56a82-190">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="56a82-190">This device has already been claimed by another organization.</span></span> <span data-ttu-id="56a82-191">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="56a82-191">Check with your device supplier.</span></span> |
| <span data-ttu-id="56a82-192">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="56a82-192">Unexpected error</span></span> | <span data-ttu-id="56a82-193">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="56a82-193">Your request could not be automatically processed.</span></span> <span data-ttu-id="56a82-194">サポートに連絡して、要求 ID を提供します。<requestId></span><span class="sxs-lookup"><span data-stu-id="56a82-194">Contact Support and provide the Request ID: <requestId></span></span> |




