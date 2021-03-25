---
title: デバイスを Microsoft Defender ATP サービスにオンボードする
description: Windows 10 デバイス、サーバー、Windows 以外のデバイスをオンボードし、検出テストを実行する方法について学習します。
keywords: オンボーディング、エンドポイントオンボーディング用 Microsoft Defender、Windows atp オンボーディング、sccm、グループ ポリシー、mdm、ローカル スクリプト、検出テスト
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9b7a225e29b4b79b2e6caf95332cb91da3dade7f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186955"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="64d69-104">デバイスを Microsoft Defender for Endpoint サービスにオンボードする</span><span class="sxs-lookup"><span data-stu-id="64d69-104">Onboard devices to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64d69-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="64d69-105">**Applies to:**</span></span>
- [<span data-ttu-id="64d69-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64d69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64d69-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64d69-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="64d69-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="64d69-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64d69-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="64d69-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="64d69-110">Defender for Endpoint ポータルのオンボーディング セクションに移動して、サポートされているデバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d69-110">You'll need to go the onboarding section of the Defender for Endpoint portal to onboard any of the supported devices.</span></span> <span data-ttu-id="64d69-111">デバイスに応じて、適切な手順と、デバイスに適した管理および展開ツールのオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="64d69-111">Depending on the device, you'll be guided with appropriate steps and provided management and deployment tool options suitable for the device.</span></span> 

<span data-ttu-id="64d69-112">一般に、デバイスをサービスにオンボードするには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="64d69-112">In general, to onboard devices to the service:</span></span>

- <span data-ttu-id="64d69-113">デバイスが最小要件を満 [たしていることを確認する](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="64d69-113">Verify that the device fulfills the [minimum requirements](minimum-requirements.md)</span></span>
- <span data-ttu-id="64d69-114">デバイスに応じて、Defender for Endpoint ポータルのオンボーディング セクションに示されている構成手順に従います。</span><span class="sxs-lookup"><span data-stu-id="64d69-114">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal</span></span>
- <span data-ttu-id="64d69-115">デバイスに適切な管理ツールと展開方法を使用する</span><span class="sxs-lookup"><span data-stu-id="64d69-115">Use the appropriate management tool and deployment method for your devices</span></span>
- <span data-ttu-id="64d69-116">検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="64d69-116">Run a detection test to verify that the devices are properly onboarded and reporting to the service</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a><span data-ttu-id="64d69-117">オンボーディング ツールのオプション</span><span class="sxs-lookup"><span data-stu-id="64d69-117">Onboarding tool options</span></span>
<span data-ttu-id="64d69-118">次の表に、オンボードする必要があるエンドポイントに基づいて使用可能なツールを示します。</span><span class="sxs-lookup"><span data-stu-id="64d69-118">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="64d69-119">Endpoint</span><span class="sxs-lookup"><span data-stu-id="64d69-119">Endpoint</span></span>     | <span data-ttu-id="64d69-120">ツール オプション</span><span class="sxs-lookup"><span data-stu-id="64d69-120">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="64d69-121">**Windows**</span><span class="sxs-lookup"><span data-stu-id="64d69-121">**Windows**</span></span>  |  [<span data-ttu-id="64d69-122">ローカル スクリプト (最大 10 台のデバイス)</span><span class="sxs-lookup"><span data-stu-id="64d69-122">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="64d69-123">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="64d69-123">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="64d69-124">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="64d69-124">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="64d69-125">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64d69-125">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="64d69-126">VDI スクリプト</span><span class="sxs-lookup"><span data-stu-id="64d69-126">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="64d69-127">**macOS**</span><span class="sxs-lookup"><span data-stu-id="64d69-127">**macOS**</span></span>    | [<span data-ttu-id="64d69-128">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="64d69-128">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="64d69-129">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="64d69-129">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="64d69-130">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="64d69-130">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="64d69-131">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="64d69-131">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="64d69-132">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="64d69-132">**Linux Server**</span></span> | [<span data-ttu-id="64d69-133">ローカル スクリプト</span><span class="sxs-lookup"><span data-stu-id="64d69-133">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="64d69-134">Puppet</span><span class="sxs-lookup"><span data-stu-id="64d69-134">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="64d69-135">Ansible</span><span class="sxs-lookup"><span data-stu-id="64d69-135">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="64d69-136">**iOS**</span><span class="sxs-lookup"><span data-stu-id="64d69-136">**iOS**</span></span>      | [<span data-ttu-id="64d69-137">アプリベース</span><span class="sxs-lookup"><span data-stu-id="64d69-137">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="64d69-138">**Android**</span><span class="sxs-lookup"><span data-stu-id="64d69-138">**Android**</span></span>  | [<span data-ttu-id="64d69-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="64d69-139">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




## <a name="in-this-section"></a><span data-ttu-id="64d69-140">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="64d69-140">In this section</span></span>
<span data-ttu-id="64d69-141">トピック</span><span class="sxs-lookup"><span data-stu-id="64d69-141">Topic</span></span> | <span data-ttu-id="64d69-142">説明</span><span class="sxs-lookup"><span data-stu-id="64d69-142">Description</span></span>
:---|:---
[<span data-ttu-id="64d69-143">以前のバージョンの Windows のオンボード</span><span class="sxs-lookup"><span data-stu-id="64d69-143">Onboard previous versions of Windows</span></span>](onboard-downlevel.md)| <span data-ttu-id="64d69-144">Windows 7 および Windows 8.1 デバイスを Defender for Endpoint にオンボードします。</span><span class="sxs-lookup"><span data-stu-id="64d69-144">Onboard Windows 7 and Windows 8.1 devices to Defender for Endpoint.</span></span> 
[<span data-ttu-id="64d69-145">オンボード Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="64d69-145">Onboard Windows 10 devices</span></span>](configure-endpoints.md) | <span data-ttu-id="64d69-146">Defender for Endpoint サービスに報告するには、デバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64d69-146">You'll need to onboard devices for it to report to the Defender for Endpoint service.</span></span> <span data-ttu-id="64d69-147">エンタープライズでデバイスを構成するために使用できるツールと方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64d69-147">Learn about the tools and methods you can use to configure devices in your enterprise.</span></span>
[<span data-ttu-id="64d69-148">オンボード サーバー</span><span class="sxs-lookup"><span data-stu-id="64d69-148">Onboard servers</span></span>](configure-server-endpoints.md) |  <span data-ttu-id="64d69-149">オンボード Windows Server 2008 R2 SP1、Windows Server 2012 R2、Windows Server 2016、Windows Server (SAC) バージョン 1803 以降、Windows Server 2019 以降、および Windows Server 2019 Core Edition to Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="64d69-149">Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) version 1803 and later, Windows Server 2019 and later, and Windows Server 2019 core edition to Defender for Endpoint.</span></span>
[<span data-ttu-id="64d69-150">Windows 以外のデバイスをオンボードする</span><span class="sxs-lookup"><span data-stu-id="64d69-150">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md) | <span data-ttu-id="64d69-151">Defender for Endpoint は、Windows および Windows 以外のプラットフォームに対して一元的なセキュリティ操作エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="64d69-151">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="64d69-152">Microsoft Defender Security Center でサポートされているさまざまなオペレーティング システム (OS) からのアラートを確認し、組織のネットワークをより保護することができます。</span><span class="sxs-lookup"><span data-stu-id="64d69-152">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> <span data-ttu-id="64d69-153">このエクスペリエンスは、サードパーティのセキュリティ製品のセンサー データを活用します。</span><span class="sxs-lookup"><span data-stu-id="64d69-153">This experience leverages on a third-party security products' sensor data.</span></span> 
[<span data-ttu-id="64d69-154">新しくオンボードされたデバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="64d69-154">Run a detection test on a newly onboarded device</span></span>](run-detection-test.md) | <span data-ttu-id="64d69-155">新しくオンボードされたデバイスでスクリプトを実行して、Defender for Endpoint サービスに適切に報告されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64d69-155">Run a script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>
[<span data-ttu-id="64d69-156">プロキシとインターネットの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="64d69-156">Configure proxy and Internet settings</span></span>](configure-proxy-internet.md)| <span data-ttu-id="64d69-157">プロキシとインターネット接続の設定を構成して、Defender for Endpoint クラウド サービスとの通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="64d69-157">Enable communication with the Defender for Endpoint cloud service by configuring the proxy and Internet connectivity settings.</span></span>
[<span data-ttu-id="64d69-158">オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="64d69-158">Troubleshoot onboarding issues</span></span>](troubleshoot-onboarding.md) | <span data-ttu-id="64d69-159">オンボーディング中に発生する可能性のある問題の解決について説明します。</span><span class="sxs-lookup"><span data-stu-id="64d69-159">Learn about resolving issues that might arise during onboarding.</span></span>

><span data-ttu-id="64d69-160">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="64d69-160">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64d69-161">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="64d69-161">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
