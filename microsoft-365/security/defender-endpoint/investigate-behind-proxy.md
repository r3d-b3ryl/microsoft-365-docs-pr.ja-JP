---
title: 転送プロキシの背後で発生する接続イベントの調査
description: プロキシではなく、実際のターゲットを表面化する Microsoft Defender for Endpoint のネットワーク保護を通じて高度な HTTP レベルの監視を使用する方法について説明します。
keywords: プロキシ、ネットワーク保護、転送プロキシ、ネットワーク イベント、監査、ブロック、ドメイン名、ドメイン
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47be07759a72a080a3687ed3bb50cef9d0a959b7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904048"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="f611b-104">転送プロキシの背後で発生する接続イベントの調査</span><span class="sxs-lookup"><span data-stu-id="f611b-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f611b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f611b-105">**Applies to:**</span></span>
- [<span data-ttu-id="f611b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f611b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f611b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f611b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f611b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f611b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f611b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="f611b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="f611b-110">Defender for Endpoint は、ネットワーク スタックの異なるレベルからのネットワーク接続監視をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f611b-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="f611b-111">難しいケースは、ネットワークがインターネットへのゲートウェイとして転送プロキシを使用する場合です。</span><span class="sxs-lookup"><span data-stu-id="f611b-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="f611b-112">プロキシは、ターゲット エンドポイントである場合と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="f611b-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="f611b-113">このような場合、単純なネットワーク接続モニターはプロキシとの接続を監査します。これは正しいが調査値は低くなります。</span><span class="sxs-lookup"><span data-stu-id="f611b-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="f611b-114">Defender for Endpoint は、ネットワーク保護による高度な HTTP レベルの監視をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f611b-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="f611b-115">オンにすると、実際のターゲット ドメイン名を公開する新しい種類のイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f611b-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="f611b-116">ネットワーク保護を使用してファイアウォールの背後にあるネットワーク接続を監視する</span><span class="sxs-lookup"><span data-stu-id="f611b-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="f611b-117">転送プロキシの背後にあるネットワーク接続の監視は、ネットワーク保護から発生する追加のネットワーク イベントが原因で可能です。</span><span class="sxs-lookup"><span data-stu-id="f611b-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="f611b-118">デバイスのタイムラインで表示するには、ネットワーク保護を有効にします (最小監査モード)。</span><span class="sxs-lookup"><span data-stu-id="f611b-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="f611b-119">ネットワーク保護は、次のモードを使用して制御できます。</span><span class="sxs-lookup"><span data-stu-id="f611b-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="f611b-120">**Block**</span><span class="sxs-lookup"><span data-stu-id="f611b-120">**Block**</span></span> <br> <span data-ttu-id="f611b-121">ユーザーまたはアプリは、危険なドメインへの接続をブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f611b-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="f611b-122">このアクティビティは Microsoft Defender セキュリティ センターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f611b-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="f611b-123">**Audit**</span><span class="sxs-lookup"><span data-stu-id="f611b-123">**Audit**</span></span> <br> <span data-ttu-id="f611b-124">ユーザーまたはアプリは、危険なドメインへの接続をブロックされません。</span><span class="sxs-lookup"><span data-stu-id="f611b-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="f611b-125">ただし、このアクティビティは Microsoft Defender セキュリティ センターで引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="f611b-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="f611b-126">ネットワーク保護をオフにした場合、ユーザーまたはアプリは危険なドメインへの接続をブロックされません。</span><span class="sxs-lookup"><span data-stu-id="f611b-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="f611b-127">Microsoft Defender セキュリティ センターにネットワーク アクティビティは表示されない。</span><span class="sxs-lookup"><span data-stu-id="f611b-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="f611b-128">構成しない場合、ネットワークブロックは既定で無効になります。</span><span class="sxs-lookup"><span data-stu-id="f611b-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="f611b-129">詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f611b-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="f611b-130">調査への影響</span><span class="sxs-lookup"><span data-stu-id="f611b-130">Investigation impact</span></span>
<span data-ttu-id="f611b-131">ネットワーク保護を有効にすると、デバイスのタイムラインで IP アドレスがプロキシを表し続け、実際のターゲット アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f611b-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![デバイスのタイムライン上のネットワーク イベントのイメージ](images/atp-proxy-investigation.png)

<span data-ttu-id="f611b-133">ネットワーク保護層によってトリガーされる追加のイベントは、プロキシの背後でも実際のドメイン名を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f611b-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="f611b-134">イベントの情報:</span><span class="sxs-lookup"><span data-stu-id="f611b-134">Event's information:</span></span>

![単一のネットワーク イベントのイメージ](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="f611b-136">高度な検索を使用した接続イベントのハント</span><span class="sxs-lookup"><span data-stu-id="f611b-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="f611b-137">すべての新しい接続イベントは、高度な狩猟を通じて狩りを行うのにも利用できます。</span><span class="sxs-lookup"><span data-stu-id="f611b-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="f611b-138">これらのイベントは接続イベントですから、アクションの種類の下にある DeviceNetworkEvents テーブルの下に `ConnecionSuccess` イベントを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f611b-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="f611b-139">この単純なクエリを使用すると、関連するすべてのイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f611b-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![高度な検索クエリのイメージ](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="f611b-141">プロキシ自体への接続に関連するイベントをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f611b-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="f611b-142">プロキシへの接続をフィルター処理するには、次のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f611b-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="f611b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f611b-143">Related topics</span></span>
- [<span data-ttu-id="f611b-144">GP によるネットワーク保護の適用 - ポリシー CSP</span><span class="sxs-lookup"><span data-stu-id="f611b-144">Applying network protection with GP - policy CSP</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
