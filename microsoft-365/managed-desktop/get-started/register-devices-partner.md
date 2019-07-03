---
title: パートナー用の Microsoft マネージドデスクトップのデバイスを登録する
description: パートナーが Microsoft マネージドデスクトップで管理できるようにデバイスを登録する方法
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 06ec98ebc7ea44a1bf3d8039e3a3ab7102521d3e
ms.sourcegitcommit: ef749c44d72b5258706be86a4af1aeca4154ead2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35447529"
---
# <a name="register-devices-in-microsoft-managed-desktop-for-partners"></a><span data-ttu-id="52789-103">パートナー用の Microsoft マネージドデスクトップのデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="52789-103">Register devices in Microsoft Managed Desktop for Partners</span></span>


<span data-ttu-id="52789-104">このトピックでは、パートナーがデバイスを登録するために従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="52789-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="52789-105">自分でデバイスを登録するプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="52789-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="52789-106">登録の準備</span><span class="sxs-lookup"><span data-stu-id="52789-106">Prepare for registration</span></span> 
<span data-ttu-id="52789-107">お客様の登録を完了する前に、[パートナーセンター](https://partner.microsoft.com/dashboard)で、お客様との関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52789-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="52789-108">[ **Azure Active Directory および Office 365 の委任管理者特権を含める**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="52789-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="52789-109">詳細については、[パートナーセンターのヘルプ](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52789-109">Learn more at [Partner Center help](https://docs.microsoft.com/en-us/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="52789-110">お客様のために登録を完了するには、まず CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="52789-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="52789-111">便宜上、この*パートナーバージョン*の CSV ファイルの[テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx)をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="52789-111">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.xlsx) for this *Partner version* of the CSV file.</span></span>

<span data-ttu-id="52789-112">ファイルには、サンプル 1 (製造元、モデルなど) と**まったく同じ列見出し**を含める必要がありますが、その他の行については独自のデータを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="52789-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="52789-113">テンプレートを使用している場合は、メモ帳などのテキスト編集ツールでそのテンプレートを開き、行1のみにデータを入力し、2行以下にデータを入力することを検討します。</span><span class="sxs-lookup"><span data-stu-id="52789-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```


>[!NOTE]
><span data-ttu-id="52789-114">この形式は、パートナープロセスにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="52789-114">This format is only for the Partner process.</span></span> <span data-ttu-id="52789-115">自己登録のプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="52789-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="52789-116">これらの値は、SMBIOS からの製造元の値と正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="52789-116">These values must match the manufacturer values from SMBIOS exactly.</span></span> <span data-ttu-id="52789-117">最初の行に*ハードウェアハッシュ*を含める必要があります (ただし、2行目にはその値を指定しません)。2行目の*シリアル番号*の後に続くコンマを指定します。</span><span class="sxs-lookup"><span data-stu-id="52789-117">You must also include *Hardware Hash* in the first row (but no value for it in the second row) the trailing comma after the *Serial Number* value in the second row.</span></span>

- <span data-ttu-id="52789-118">デバイスの製造元 (例: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="52789-118">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="52789-119">デバイスモデル (例: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="52789-119">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="52789-120">デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="52789-120">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="52789-121">Azure ポータルを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="52789-121">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="52789-122">Azure Portal を使用して登録することは、セルフサービスの場合と同じですが、ポータルには別の方法でアクセスする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="52789-122">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="52789-123">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="52789-123">Follow these steps:</span></span>

1. <span data-ttu-id="52789-124">[パートナーセンター](https://partner.microsoft.com/dashboard)への移動</span><span class="sxs-lookup"><span data-stu-id="52789-124">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="52789-125">[**顧客**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-125">Select **Customers**.</span></span>
3. <span data-ttu-id="52789-126">管理する顧客を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-126">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="52789-127">[**サービスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-127">Select **Service Administration**.</span></span>
5. <span data-ttu-id="52789-128">[ **Intune**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-128">Select **Intune**.</span></span>
6. <span data-ttu-id="52789-129">Azure portal の上部の検索ボックスで「mmd」を検索します。</span><span class="sxs-lookup"><span data-stu-id="52789-129">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="52789-130">[**デバイス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-130">Select **Devices**.</span></span>
8. <span data-ttu-id="52789-131">[**ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="52789-131">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="52789-132">必要に応じて、独自の追跡目的のために、**注文 id**または**購買 id**を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="52789-132">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="52789-133">これらの値に書式の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="52789-133">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="52789-134">[**デバイスの登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="52789-134">Select **Register devices**.</span></span> <span data-ttu-id="52789-135">システムによってデバイス**ブレード**上のデバイスの一覧にデバイスが追加され、[**登録保留中**] としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="52789-135">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="52789-136">通常、登録にかかる時間は10分未満で、成功した場合、デバイスは**ユーザーのための準備**完了として表示され、エンドユーザーが使用を開始するのを待っています。</span><span class="sxs-lookup"><span data-stu-id="52789-136">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="52789-137">メインの**Microsoft Managed Desktop-Devices**ページでのデバイス登録の進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="52789-137">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="52789-138">報告される状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="52789-138">Possible states reported there include:</span></span>

| <span data-ttu-id="52789-139">State</span><span class="sxs-lookup"><span data-stu-id="52789-139">State</span></span> | <span data-ttu-id="52789-140">説明</span><span class="sxs-lookup"><span data-stu-id="52789-140">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="52789-141">登録保留中</span><span class="sxs-lookup"><span data-stu-id="52789-141">Registration pending</span></span> | <span data-ttu-id="52789-142">登録はまだ行われていません。</span><span class="sxs-lookup"><span data-stu-id="52789-142">Registration is not done yet.</span></span> <span data-ttu-id="52789-143">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="52789-143">Check back later.</span></span> |
| <span data-ttu-id="52789-144">登録の失敗</span><span class="sxs-lookup"><span data-stu-id="52789-144">Registration failed</span></span> | <span data-ttu-id="52789-145">登録を完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="52789-145">Registration could not be completed.</span></span> <span data-ttu-id="52789-146">詳細については、「[トラブルシューティング](register-devices-self.md#troubleshooting)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52789-146">Refer to [Troubleshooting](register-devices-self.md#troubleshooting) for more information.</span></span> |
| <span data-ttu-id="52789-147">ユーザーの準備完了</span><span class="sxs-lookup"><span data-stu-id="52789-147">Ready for user</span></span> | <span data-ttu-id="52789-148">登録が成功し、デバイスをエンドユーザーに配信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="52789-148">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="52789-149">Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="52789-149">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="52789-150">Active</span><span class="sxs-lookup"><span data-stu-id="52789-150">Active</span></span> | <span data-ttu-id="52789-151">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="52789-151">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="52789-152">これは、デバイスを定期的に使用していることも示しています。</span><span class="sxs-lookup"><span data-stu-id="52789-152">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="52789-153">未使用</span><span class="sxs-lookup"><span data-stu-id="52789-153">Inactive</span></span> | <span data-ttu-id="52789-154">デバイスはエンドユーザーに配信され、テナントに登録されています。</span><span class="sxs-lookup"><span data-stu-id="52789-154">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="52789-155">しかし、最近7日間ではデバイスを使用していません。</span><span class="sxs-lookup"><span data-stu-id="52789-155">However, they have not used the device recently (in the last 7 days).</span></span>  |

## <a name="register-devices-by-using-an-api"></a><span data-ttu-id="52789-156">API を使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="52789-156">Register devices by using an API</span></span>

<span data-ttu-id="52789-157">API による登録は自己サービスと同じですが、CSV セクションで説明するように、デバイスコレクションのハードウェアハッシュプロパティがオプションである点が異なります。</span><span class="sxs-lookup"><span data-stu-id="52789-157">Registering by API is the same as self-service, except that the hardware hash property of the device collection is optional as described in the CSV section.</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="52789-158">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="52789-158">Troubleshooting</span></span>

| <span data-ttu-id="52789-159">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="52789-159">Error message</span></span> | <span data-ttu-id="52789-160">詳細</span><span class="sxs-lookup"><span data-stu-id="52789-160">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="52789-161">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="52789-161">Device not found</span></span> | <span data-ttu-id="52789-162">提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。</span><span class="sxs-lookup"><span data-stu-id="52789-162">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="52789-163">これらの値は、デバイスの提供元に確認してください。</span><span class="sxs-lookup"><span data-stu-id="52789-163">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="52789-164">デバイスが見つかりません</span><span class="sxs-lookup"><span data-stu-id="52789-164">Device not found</span></span> | <span data-ttu-id="52789-165">このデバイスは組織内に存在しないため、登録を解除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="52789-165">We couldn’t de-register this device because it does not exist in your organization.</span></span> <span data-ttu-id="52789-166">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="52789-166">No further action required.</span></span> |
| <span data-ttu-id="52789-167">ハードウェアハッシュが無効です</span><span class="sxs-lookup"><span data-stu-id="52789-167">Hardware hash not valid</span></span> | <span data-ttu-id="52789-168">このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。</span><span class="sxs-lookup"><span data-stu-id="52789-168">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="52789-169">ハードウェアハッシュをもう一度確認してから再送信します。</span><span class="sxs-lookup"><span data-stu-id="52789-169">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="52789-170">デバイスは既に登録されています</span><span class="sxs-lookup"><span data-stu-id="52789-170">Device already registered</span></span> | <span data-ttu-id="52789-171">このデバイスは既に組織に登録されています。</span><span class="sxs-lookup"><span data-stu-id="52789-171">This device is already registered to your organization.</span></span> <span data-ttu-id="52789-172">その他のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="52789-172">No further action required.</span></span> |
| <span data-ttu-id="52789-173">別の組織によって要求されるデバイス</span><span class="sxs-lookup"><span data-stu-id="52789-173">Device claimed by another organization</span></span> | <span data-ttu-id="52789-174">このデバイスは、既に別の組織によって要求されています。</span><span class="sxs-lookup"><span data-stu-id="52789-174">This device has already been claimed by another organization.</span></span> <span data-ttu-id="52789-175">デバイスサプライヤーに確認します。</span><span class="sxs-lookup"><span data-stu-id="52789-175">Check with your device supplier.</span></span> |
| <span data-ttu-id="52789-176">予期しないエラーです</span><span class="sxs-lookup"><span data-stu-id="52789-176">Unexpected error</span></span> | <span data-ttu-id="52789-177">要求は自動的に処理されませんでした。</span><span class="sxs-lookup"><span data-stu-id="52789-177">Your request could not be automatically processed.</span></span> <span data-ttu-id="52789-178">サポート<support link>に連絡して、要求 ID を提供します。<requestId></span><span class="sxs-lookup"><span data-stu-id="52789-178">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
