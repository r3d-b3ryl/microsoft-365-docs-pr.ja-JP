---
title: Microsoft Defender for Endpoint で不健康なセンサーを修正する
description: サービスがデバイスからデータを受信するために、構成が正しく設定されていないか非アクティブとして報告されているデバイス センサーを修正します。
keywords: 誤構成、非アクティブ、センサーの修正、センサーの正常性、センサー データなし、センサー データ、通信障害、通信障害
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935367"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="1638f-104">Microsoft Defender for Endpoint で不健康なセンサーを修正する</span><span class="sxs-lookup"><span data-stu-id="1638f-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1638f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1638f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1638f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1638f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1638f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1638f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="1638f-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="1638f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1638f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="1638f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="1638f-110">構成ミスまたは非アクティブとして分類されたデバイスは、さまざまな原因によりフラグが設定される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1638f-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="1638f-111">このセクションでは、デバイスが非アクティブまたは正しく構成されていないと分類された原因について説明します。</span><span class="sxs-lookup"><span data-stu-id="1638f-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="1638f-112">非アクティブ デバイス</span><span class="sxs-lookup"><span data-stu-id="1638f-112">Inactive devices</span></span>

<span data-ttu-id="1638f-113">非アクティブなデバイスは、問題が原因でフラグが設定されているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1638f-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="1638f-114">デバイスで実行される次のアクションにより、デバイスが非アクティブとして分類される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1638f-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="1638f-115">デバイスが使用されていない</span><span class="sxs-lookup"><span data-stu-id="1638f-115">Device is not in use</span></span>

<span data-ttu-id="1638f-116">何らかの理由でデバイスが 7 日間以上使用されていない場合は、ポータルの [非アクティブ] 状態のままです。</span><span class="sxs-lookup"><span data-stu-id="1638f-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="1638f-117">デバイスが再インストールまたは名前の変更された</span><span class="sxs-lookup"><span data-stu-id="1638f-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="1638f-118">再インストールまたは名前の変更されたデバイスは、新しいデバイス エンティティを新しいデバイス エンティティMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="1638f-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="1638f-119">前のデバイス エンティティは、ポータルの "非アクティブ" 状態のままです。</span><span class="sxs-lookup"><span data-stu-id="1638f-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="1638f-120">デバイスを再インストールして Defender for Endpoint パッケージを展開した場合は、新しいデバイス名を検索して、デバイスが正常に報告されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="1638f-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="1638f-121">デバイスがオフボードされた</span><span class="sxs-lookup"><span data-stu-id="1638f-121">Device was offboarded</span></span>
<span data-ttu-id="1638f-122">デバイスがオフボードされている場合は、デバイスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1638f-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="1638f-123">7 日後、デバイスの正常性状態は非アクティブに変更されます。</span><span class="sxs-lookup"><span data-stu-id="1638f-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="1638f-124">デバイスが信号を送信していない</span><span class="sxs-lookup"><span data-stu-id="1638f-124">Device is not sending signals</span></span>
<span data-ttu-id="1638f-125">デバイスが、構成が正しく設定されていないデバイス分類に該当する条件を含む何らかの理由で、Microsoft Defender for Endpoint チャネルに 7 日間以上信号を送信していない場合、デバイスは非アクティブと見なされます。</span><span class="sxs-lookup"><span data-stu-id="1638f-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="1638f-126">デバイスが 'Active' 状態にあると思いますか?</span><span class="sxs-lookup"><span data-stu-id="1638f-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="1638f-127">[サポート チケットを開きます](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。</span><span class="sxs-lookup"><span data-stu-id="1638f-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="1638f-128">誤って構成されたデバイス</span><span class="sxs-lookup"><span data-stu-id="1638f-128">Misconfigured devices</span></span>
<span data-ttu-id="1638f-129">構成が正しく設定されていないデバイスは、さらに次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="1638f-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="1638f-130">通信障害</span><span class="sxs-lookup"><span data-stu-id="1638f-130">Impaired communications</span></span>
- <span data-ttu-id="1638f-131">センサー データなし</span><span class="sxs-lookup"><span data-stu-id="1638f-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="1638f-132">通信障害</span><span class="sxs-lookup"><span data-stu-id="1638f-132">Impaired communications</span></span>
<span data-ttu-id="1638f-133">この状態は、デバイスとサービス間の通信が制限されている状態を示します。</span><span class="sxs-lookup"><span data-stu-id="1638f-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="1638f-134">次の推奨されるアクションは、通信障害のある誤った構成済みデバイスに関連する問題を解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1638f-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="1638f-135">デバイスにインターネット接続が確立されている</span><span class="sxs-lookup"><span data-stu-id="1638f-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="1638f-136">Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1638f-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="1638f-137">エンドポイント サービス URL 用 Microsoft Defender へのクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="1638f-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="1638f-138">プロキシ構成が正常に完了し、WinHTTP が環境内のプロキシ サーバーを介して検出して通信し、プロキシ サーバーが Microsoft Defender for Endpoint サービス URL へのトラフィックを許可することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1638f-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="1638f-139">修正アクションを実行してもデバイスの状態が正しく構成されていない場合は、サポート [チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="1638f-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="1638f-140">センサー データなし</span><span class="sxs-lookup"><span data-stu-id="1638f-140">No sensor data</span></span>
<span data-ttu-id="1638f-141">"センサー データなし" の状態の誤った構成済みデバイスは、サービスとの通信を持っていますが、部分的なセンサー データのみを報告できます。</span><span class="sxs-lookup"><span data-stu-id="1638f-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="1638f-142">これらのアクションに従って、誤って構成されたデバイスに関連する既知の問題を修正し、状態が "センサー データなし" になります。</span><span class="sxs-lookup"><span data-stu-id="1638f-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="1638f-143">デバイスにインターネット接続が確立されている</span><span class="sxs-lookup"><span data-stu-id="1638f-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="1638f-144">Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1638f-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="1638f-145">エンドポイント サービス URL 用 Microsoft Defender へのクライアント接続を確認する</span><span class="sxs-lookup"><span data-stu-id="1638f-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="1638f-146">プロキシ構成が正常に完了し、WinHTTP が環境内のプロキシ サーバーを介して検出して通信し、プロキシ サーバーが Microsoft Defender for Endpoint サービス URL へのトラフィックを許可することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1638f-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="1638f-147">診断データ サービスが有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="1638f-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="1638f-148">デバイスが正しく報告されていない場合は、Windows 10 診断データ サービスが自動的に開始するように設定され、エンドポイントで実行されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1638f-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="1638f-149">ポリシーによってMicrosoft Defender ウイルス対策が無効にされていないか確認する</span><span class="sxs-lookup"><span data-stu-id="1638f-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="1638f-150">デバイスでサードパーティのマルウェア対策クライアントを実行している場合、Defender for Endpoint エージェントは Microsoft Defender ウイルス対策 早期起動マルウェア対策 (ELAM) ドライバーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1638f-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="1638f-151">修正アクションを実行してもデバイスの状態が正しく構成されていない場合は、サポート [チケットを開きます](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="1638f-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="1638f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="1638f-152">See also</span></span>
- [<span data-ttu-id="1638f-153">Microsoft Defender for Endpoint のセンサーの正常性状態を確認する</span><span class="sxs-lookup"><span data-stu-id="1638f-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
