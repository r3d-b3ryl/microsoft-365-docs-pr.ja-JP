---
title: デバイスを登録するためのパートナー向け手順
description: パートナーが Microsoft マネージドデスクトップで管理できるようにデバイスを登録する方法
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: eb7ff76ef51078e423201b41cf24780b822ba452
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572243"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="0f33b-103">デバイスを登録するためのパートナー向け手順</span><span class="sxs-lookup"><span data-stu-id="0f33b-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="0f33b-104">このトピックでは、パートナーがデバイスを登録するために従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="0f33b-105">自分でデバイスを登録するプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="0f33b-106">登録の準備</span><span class="sxs-lookup"><span data-stu-id="0f33b-106">Prepare for registration</span></span> 
<span data-ttu-id="0f33b-107">お客様の登録を完了する前に、[パートナーセンター](https://partner.microsoft.com/dashboard)で、お客様との関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f33b-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="0f33b-108">[ **Azure Active Directory および Office 365 の委任管理者特権を含める**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0f33b-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="0f33b-109">詳細については、[パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f33b-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="0f33b-110">お客様のために登録を完了するには、まず CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="0f33b-111">便宜上、この*パートナーバージョン*用の[サンプル CSV ファイル](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f33b-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv) for this *Partner version*.</span></span>

<span data-ttu-id="0f33b-112">ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f33b-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="0f33b-113">テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="0f33b-114">この形式は、パートナープロセスにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f33b-114">This format is only for the Partner process.</span></span> <span data-ttu-id="0f33b-115">自己登録のプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="0f33b-116">これらの値は、大文字と小文字を含めて、SMBIOS からの製造元の値と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f33b-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="0f33b-117">デバイスの製造元 (例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="0f33b-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="0f33b-118">デバイスモデル (例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="0f33b-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="0f33b-119">デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="0f33b-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="0f33b-120">Azure ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="0f33b-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="0f33b-121">Azure Portal を使用して登録することは、セルフサービスの場合と同じですが、ポータルには別の方法でアクセスする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="0f33b-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="0f33b-122">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-122">Follow these steps:</span></span>

1. <span data-ttu-id="0f33b-123">[パートナーセンター](https://partner.microsoft.com/dashboard)への移動</span><span class="sxs-lookup"><span data-stu-id="0f33b-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="0f33b-124">[**顧客**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-124">Select **Customers**.</span></span>
3. <span data-ttu-id="0f33b-125">管理する顧客を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="0f33b-126">[**サービスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="0f33b-127">[ **Intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-127">Select **Intune**.</span></span>
6. <span data-ttu-id="0f33b-128">Azure portal の上部の検索ボックスで「mmd」を検索します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="0f33b-129">[**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-129">Select **Devices**.</span></span>
8. <span data-ttu-id="0f33b-130">[**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="0f33b-131">必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f33b-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="0f33b-132">これらの値に書式の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="0f33b-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="0f33b-133">[**デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-133">Select **Register devices**.</span></span> <span data-ttu-id="0f33b-134">システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="0f33b-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="0f33b-135">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="0f33b-136">メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="0f33b-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="0f33b-137">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f33b-137">Possible states reported there include:</span></span>

| <span data-ttu-id="0f33b-138">State</span><span class="sxs-lookup"><span data-stu-id="0f33b-138">State</span></span> | <span data-ttu-id="0f33b-139">説明</span><span class="sxs-lookup"><span data-stu-id="0f33b-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="0f33b-140">登録保留中</span><span class="sxs-lookup"><span data-stu-id="0f33b-140">Registration pending</span></span> | <span data-ttu-id="0f33b-141">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="0f33b-141">Registration is not done yet.</span></span> <span data-ttu-id="0f33b-142">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f33b-142">Check back later.</span></span> |
| <span data-ttu-id="0f33b-143">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="0f33b-143">Registration failed</span></span> | <span data-ttu-id="0f33b-144">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0f33b-144">Registration could not be completed.</span></span> <span data-ttu-id="0f33b-145">詳細については、「 [device registration のトラブルシューティング](register-devices-self.md#troubleshooting-device-registration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f33b-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="0f33b-146">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="0f33b-146">Ready for user</span></span> | <span data-ttu-id="0f33b-147">登録が成功し、デバイスをエンドユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="0f33b-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="0f33b-148">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0f33b-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="0f33b-149">Active</span><span class="sxs-lookup"><span data-stu-id="0f33b-149">Active</span></span> | <span data-ttu-id="0f33b-150">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="0f33b-151">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="0f33b-152">未使用</span><span class="sxs-lookup"><span data-stu-id="0f33b-152">Inactive</span></span> | <span data-ttu-id="0f33b-153">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="0f33b-154">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="0f33b-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="0f33b-155">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0f33b-155">Troubleshooting</span></span>

| <span data-ttu-id="0f33b-156">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="0f33b-156">Error message</span></span> | <span data-ttu-id="0f33b-157">詳細</span><span class="sxs-lookup"><span data-stu-id="0f33b-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="0f33b-158">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="0f33b-158">Device not found</span></span> | <span data-ttu-id="0f33b-159">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0f33b-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="0f33b-160">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f33b-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="0f33b-161">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="0f33b-161">Hardware hash not valid</span></span> | <span data-ttu-id="0f33b-162">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="0f33b-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="0f33b-163">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="0f33b-164">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="0f33b-164">Device already registered</span></span> | <span data-ttu-id="0f33b-165">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-165">This device is already registered to your organization.</span></span> <span data-ttu-id="0f33b-166">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0f33b-166">No further action required.</span></span> |
| <span data-ttu-id="0f33b-167">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="0f33b-167">Device claimed by another organization</span></span> | <span data-ttu-id="0f33b-168">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="0f33b-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="0f33b-169">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="0f33b-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="0f33b-170">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="0f33b-170">Unexpected error</span></span> | <span data-ttu-id="0f33b-171">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="0f33b-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="0f33b-172">サポート<support link>に連絡して、要求 ID を提供します。<requestId></span><span class="sxs-lookup"><span data-stu-id="0f33b-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
