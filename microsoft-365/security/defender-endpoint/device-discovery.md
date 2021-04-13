---
title: デバイス検出の概要
description: Microsoft 365 Defender のエンドポイント検出を活用してネットワーク内の管理されていないデバイスを検索する方法について説明します。
keywords: デバイスの検出、検出、パッシブ、プロアクティブ、ネットワーク、可視性、サーバー、ワークステーション、オンボード、管理されていないデバイス
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2e58b6048f9d815d759cd78ceb3316eb2ed6f66d
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698479"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="4dd78-104">デバイス検出の概要</span><span class="sxs-lookup"><span data-stu-id="4dd78-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4dd78-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4dd78-105">**Applies to:**</span></span>
- [<span data-ttu-id="4dd78-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4dd78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4dd78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4dd78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4dd78-108">環境を保護するには、ネットワーク内のデバイスのインベントリを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="4dd78-109">ただし、ネットワーク内のマッピング デバイスは、多くの場合、コストがかかり、困難で、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="4dd78-110">Microsoft Defender for Endpoint は、デバイス検出機能を提供し、追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="4dd78-111">デバイス検出機能を使用すると、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="4dd78-112">**企業ネットワークに接続されているエンタープライズ エンドポイントを検出する**</span><span class="sxs-lookup"><span data-stu-id="4dd78-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="4dd78-113">基本的な検出オプションまたは標準検出オプションを使用すると、Microsoft Defender for Endpoint にまだオンボードされていないワークステーション、サーバー、およびモバイル エンドポイントを検出できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="4dd78-114">**オンボードで検出されたエンドポイント**</span><span class="sxs-lookup"><span data-stu-id="4dd78-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="4dd78-115">ネットワーク内の管理されていないエンドポイントは、ネットワークに脆弱性とリスクを導入します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="4dd78-116">サービスにオンボーディングすると、セキュリティの可視性が向上します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="4dd78-117">この機能と組み合わせて、Microsoft Defender for Endpoint にデバイスをオンボードする新しいセキュリティ推奨事項は、既存の脅威と脆弱性管理エクスペリエンスの一環として利用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="4dd78-118">探索メソッド</span><span class="sxs-lookup"><span data-stu-id="4dd78-118">Discovery methods</span></span>
<span data-ttu-id="4dd78-119">検出には 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="4dd78-120">基本的な検出</span><span class="sxs-lookup"><span data-stu-id="4dd78-120">Basic discovery</span></span> 
-   <span data-ttu-id="4dd78-121">標準検出 (推奨)</span><span class="sxs-lookup"><span data-stu-id="4dd78-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="4dd78-122">検出は基本モードに設定されます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="4dd78-123">この構成は、[設定] ページから保持できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="4dd78-124">標準検出は、2021 年 5 月 10 日から始まるすべてのプレビューユーザーの既定のモードになります 。この日付より前の設定ページで変更しない限り。</span><span class="sxs-lookup"><span data-stu-id="4dd78-124">Standard discovery will be the default mode for all preview customers starting May 10, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="4dd78-125">基本的な検出</span><span class="sxs-lookup"><span data-stu-id="4dd78-125">Basic discovery</span></span> 

<span data-ttu-id="4dd78-126">このモードでは、エンドポイントはネットワーク内のイベントを受動的に収集し、そこからデバイス情報を抽出します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="4dd78-127">基本的な検出では、SenseNDR.exeネットワーク データ収集にバイナリを使用し、ネットワーク トラフィックは開始されません。</span><span class="sxs-lookup"><span data-stu-id="4dd78-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="4dd78-128">エンドポイントは、オンボードデバイスで見られるすべてのネットワーク トラフィックからデータを抽出するだけで構成されます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="4dd78-129">標準検出</span><span class="sxs-lookup"><span data-stu-id="4dd78-129">Standard discovery</span></span> 

<span data-ttu-id="4dd78-130">このモードにより、エンドポイントはネットワーク内の観測されたデバイスをアクティブにプローブして収集されたデータを強化し、信頼性の高い一貫性のあるデバイス インベントリを構築できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="4dd78-131">標準モードでは、スマートでアクティブなプロブを使用して、観測されたデバイスに関するさらに多くの情報を検出し、既存のデバイス情報を強化します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="4dd78-132">Standard モードを有効にすると、検出センサーによって生成される最小限のごくわずかのネットワーク アクティビティが、組織内のネットワーク監視ツールによって観察される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="4dd78-133">このモードを有効にしない場合は、ネットワーク内の管理されていないエンドポイントの表示が制限されます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="4dd78-134">標準検出では、さまざまな PowerShell スクリプトを使用して、ネットワーク内のデバイスをアクティブにプローブします。</span><span class="sxs-lookup"><span data-stu-id="4dd78-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="4dd78-135">これらの PowerShell スクリプトは Microsoft 署名済みで、次の場所から実行されます `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` 。</span><span class="sxs-lookup"><span data-stu-id="4dd78-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="4dd78-136">たとえば、`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1` などです。</span><span class="sxs-lookup"><span data-stu-id="4dd78-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="4dd78-137">詳細については、「デバイス検出の構成」を参照[してください。](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="4dd78-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4dd78-138">検出エンジンは、企業ネットワークで受信されるネットワーク イベントと企業ネットワーク外のネットワーク イベントを区別します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="4dd78-139">企業ネットワークに接続されていないデバイスは、デバイス インベントリで検出または一覧表示されません。</span><span class="sxs-lookup"><span data-stu-id="4dd78-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="4dd78-140">デバイス インベントリ</span><span class="sxs-lookup"><span data-stu-id="4dd78-140">Device Inventory</span></span> 
<span data-ttu-id="4dd78-141">Microsoft Defender for Endpoint によって検出されたが、まだオンボードおよびセキュリティ保護されていないデバイスは、[エンドポイント] タブの [デバイス インベントリ] に表示されます。これで、次の値を持つ可能性があるオンボード状態と呼ばれるデバイス インベントリ リストで新しいフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="4dd78-142">オンボード – エンドポイントは、Microsoft Defender for Endpoint にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="4dd78-143">オンボード可能 – ネットワークでエンドポイントが検出され、オペレーティング システムは Microsoft Defender for Endpoint でサポートされているエンドポイントとして識別されましたが、現在オンボードされていません。</span><span class="sxs-lookup"><span data-stu-id="4dd78-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="4dd78-144">これらのデバイスのオンボーディングを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4dd78-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="4dd78-145">サポートされていません– エンドポイントはネットワークで検出されましたが、Microsoft Defender for Endpoint ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4dd78-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="4dd78-146">不十分な情報 – システムがデバイスのサポート性を判断できない。</span><span class="sxs-lookup"><span data-stu-id="4dd78-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="4dd78-147">ネットワーク内のより多くのデバイスで標準検出を有効にすると、検出された属性を強化できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![デバイス インベントリ ダッシュボードのイメージ](images/2b62255cd3a9dd42f3219e437b956fb9.png)



## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="4dd78-149">検出されたデバイスの脆弱性評価</span><span class="sxs-lookup"><span data-stu-id="4dd78-149">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="4dd78-150">デバイスの脆弱性とリスク、およびネットワーク内で検出された他の管理されていないデバイスは、"セキュリティ推奨事項" の下にある現在の TVM フローの一部であり、ポータル全体のエンティティ ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-150">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="4dd78-151">"SSH" 関連のセキュリティ推奨事項を検索して、管理されていないデバイスと管理対象デバイスに関連する SSH の脆弱性を検索します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-151">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![セキュリティ推奨事項ダッシュボードのイメージ](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="4dd78-153">検出されたデバイスで高度なハンティングを使用する</span><span class="sxs-lookup"><span data-stu-id="4dd78-153">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="4dd78-154">高度な検索クエリを使用すると、検出されたデバイスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-154">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="4dd78-155">検出されたエンドポイントの詳細については、DeviceInfo テーブル、または DeviceNetworkInfo テーブルのこれらのデバイスに関するネットワーク関連の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4dd78-155">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![高度なハンティングの使用イメージ](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="4dd78-157">デバイス検出では、Microsoft Defender for Endpoint オンボード デバイスをネットワーク データ ソースとして活用して、オンボードされていないデバイスにアクティビティを属性付けします。</span><span class="sxs-lookup"><span data-stu-id="4dd78-157">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="4dd78-158">つまり、Microsoft Defender for Endpoint オンボード デバイスがオンボードされていないデバイスと通信した場合、オンボードされていないデバイス上のアクティビティは、タイムライン上および高度なハンティング DeviceNetworkEvents テーブルで確認できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-158">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="4dd78-159">新しいイベントは、伝送制御プロトコル (TCP) 接続ベースであり、現在の DeviceNetworkEvents スキームに適合します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-159">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="4dd78-160">エンドポイントが有効な Microsoft Defender 以外からの Microsoft Defender for Endpoint 対応デバイスへの TCP 入力。</span><span class="sxs-lookup"><span data-stu-id="4dd78-160">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="4dd78-161">次のアクションの種類も追加されています。</span><span class="sxs-lookup"><span data-stu-id="4dd78-161">The following action types have also been added:</span></span>  

- <span data-ttu-id="4dd78-162">ConnectionAttempt - TCP 接続を確立する試み (syn)</span><span class="sxs-lookup"><span data-stu-id="4dd78-162">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="4dd78-163">ConnectionAcknowledged - TCP 接続が受け入れられたという確認応答 (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="4dd78-163">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="4dd78-164">次のクエリ例を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="4dd78-164">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behaviour"></a><span data-ttu-id="4dd78-165">変更された動作</span><span class="sxs-lookup"><span data-stu-id="4dd78-165">Changed behaviour</span></span>
<span data-ttu-id="4dd78-166">次のセクションでは、この機能が有効になっているときに Microsoft Defender for Endpoint または Microsoft 365 セキュリティ センターで確認する変更点を示します。</span><span class="sxs-lookup"><span data-stu-id="4dd78-166">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="4dd78-167">Microsoft Defender to Endpoint にオンボードされていないデバイスは、デバイス インベントリ、高度なハンティング、API クエリに表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-167">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="4dd78-168">これにより、クエリ結果のサイズが大幅に増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-168">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="4dd78-169">Advanced Hunting の "DeviceInfo" テーブルと "DeviceNetworkInfo" テーブルには、検出されたデバイスが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-169">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="4dd78-170">"OnboardingStatus" 属性を使用して、これらのデバイスをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-170">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="4dd78-171">検出されたデバイスは、ストリーミング API クエリ結果に表示される予定です。</span><span class="sxs-lookup"><span data-stu-id="4dd78-171">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="4dd78-172">これらのデバイスは、クエリでフィルターを使用 `OnboardingStatus` してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-172">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="4dd78-173">管理されていないデバイスは、定義された条件に基づいて既存のデバイス グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-173">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="4dd78-174">まれに、標準検出によってネットワーク モニターやセキュリティ ツールでアラートがトリガーされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4dd78-174">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="4dd78-175">このようなイベントが発生した場合は、これらの問題が繰り返されるのを防ぐためのフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="4dd78-175">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="4dd78-176">特定のターゲットまたはサブネット全体が Standard Discovery によってアクティブにプローブされるのを明示的に除外できます。</span><span class="sxs-lookup"><span data-stu-id="4dd78-176">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="4dd78-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4dd78-177">Next steps</span></span>
- [<span data-ttu-id="4dd78-178">デバイスの検出を構成する</span><span class="sxs-lookup"><span data-stu-id="4dd78-178">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="4dd78-179">デバイスの検出に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="4dd78-179">Device discovery FAQs</span></span>](device-discovery-faq.md)
