---
title: IPs と URL/ドメインのインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、および除外を定義する、IPs および URL/ドメインのインジケーターを作成します。
keywords: IP、URL、ドメイン、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
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
ms.technology: mde
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198485"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="62bb8-104">IPs と URL/ドメインのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="62bb8-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="62bb8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="62bb8-105">**Applies to:**</span></span>
- [<span data-ttu-id="62bb8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="62bb8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="62bb8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="62bb8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="62bb8-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="62bb8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="62bb8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="62bb8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="62bb8-110">Defender for Endpoint は、Microsoft が悪意のある IPS/URL と見なす動作、Windows Defender SmartScreen for Microsoft ブラウザー、および Microsoft 以外のブラウザーやブラウザー外で行われた呼び出しに対するネットワーク保護を通じてブロックできます。</span><span class="sxs-lookup"><span data-stu-id="62bb8-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="62bb8-111">このための脅威インテリジェンス データ セットは、Microsoft によって管理されています。</span><span class="sxs-lookup"><span data-stu-id="62bb8-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="62bb8-112">IP と URL またはドメインのインジケーターを作成することで、独自の脅威インテリジェンスに基づいて、IPs、URL、またはドメインを許可またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="62bb8-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="62bb8-113">特定のグループが他のグループよりも多かれ少なかれ危険にさらされている場合は、設定ページまたはコンピューター グループを使用してこれを行えます。</span><span class="sxs-lookup"><span data-stu-id="62bb8-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="62bb8-114">IP アドレスInter-Domainクラスレス ルーティング (CIDR) 表記はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="62bb8-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="62bb8-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="62bb8-115">Before you begin</span></span>
<span data-ttu-id="62bb8-116">IPS、URL、またはドメインのインジケーターを作成する前に、次の前提条件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="62bb8-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="62bb8-117">URL/IP 許可とブロックは、Defender for Endpoint コンポーネントのネットワーク保護をブロック モードで有効にしています。</span><span class="sxs-lookup"><span data-stu-id="62bb8-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="62bb8-118">ネットワーク保護と構成手順の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="62bb8-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="62bb8-119">マルウェア対策クライアントのバージョンは、4.18.1906.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="62bb8-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="62bb8-120">Windows 10 バージョン 1709 以降のコンピューターでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="62bb8-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="62bb8-121">Microsoft Defender Security Center **の [設定] ページ** で[カスタム ネットワーク インジケーター] が有効 **>高度>確認します**。</span><span class="sxs-lookup"><span data-stu-id="62bb8-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="62bb8-122">詳細については、「高度な機能 [」を参照してください](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="62bb8-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="62bb8-123">iOS でのインジケーターのサポートについては、「カスタム インジケーターの [構成」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。</span><span class="sxs-lookup"><span data-stu-id="62bb8-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="62bb8-124">インジケーター リストに追加できるのは外部の AP のみです。</span><span class="sxs-lookup"><span data-stu-id="62bb8-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="62bb8-125">インジケーターは、内部の IPs に対して作成できません。</span><span class="sxs-lookup"><span data-stu-id="62bb8-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="62bb8-126">Web 保護のシナリオでは、Microsoft Edge の組み込み機能を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62bb8-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="62bb8-127">Microsoft Edge はネットワーク保護 [を利用して](network-protection.md) ネットワーク トラフィックを検査し、TCP、HTTP、HTTPS (TLS) のブロックを許可します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="62bb8-128">競合する URL インジケーター ポリシーがある場合は、長いパスが適用されます。</span><span class="sxs-lookup"><span data-stu-id="62bb8-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="62bb8-129">たとえば、URL インジケーター ポリシーは URL インジケーター `https:\\support.microsoft.com/en-us/office` ポリシーよりも優先されます `https:\\support.microsoft.com` 。</span><span class="sxs-lookup"><span data-stu-id="62bb8-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="62bb8-130">その他のすべてのプロセスでは、Web 保護シナリオでネットワーク保護を活用して検査と実施を行います。</span><span class="sxs-lookup"><span data-stu-id="62bb8-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="62bb8-131">IP は 3 つのプロトコルすべてでサポートされています</span><span class="sxs-lookup"><span data-stu-id="62bb8-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="62bb8-132">サポートされている IP アドレスは 1 つのみです (CIDR ブロックまたは IP 範囲なし)</span><span class="sxs-lookup"><span data-stu-id="62bb8-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="62bb8-133">暗号化された URL (フル パス) は、ファースト パーティのブラウザーでのみブロックできます (Internet Explorer エッジ)</span><span class="sxs-lookup"><span data-stu-id="62bb8-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="62bb8-134">暗号化された URL (FQDN のみ) は、ファースト パーティブラウザーの外部でブロックできます (Internet Explorer エッジ)</span><span class="sxs-lookup"><span data-stu-id="62bb8-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="62bb8-135">完全な URL パス ブロックは、ドメイン レベルと暗号化されていないすべての URL に適用できます。</span><span class="sxs-lookup"><span data-stu-id="62bb8-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="62bb8-136">アクションが実行され、URL と IP がブロックされる時間の間に最大 2 時間の待機時間 (通常は少ない) が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="62bb8-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="62bb8-137">設定ページから、IPs、URL、またはドメインのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="62bb8-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="62bb8-138">ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="62bb8-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="62bb8-139">[IP アドレス **] タブまたは [URL/ドメイン] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="62bb8-140">[アイテム **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="62bb8-140">Select **Add item**.</span></span>

4. <span data-ttu-id="62bb8-141">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-141">Specify the following details:</span></span>
   - <span data-ttu-id="62bb8-142">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="62bb8-143">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="62bb8-144">Scope - コンピューター グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="62bb8-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="62bb8-145">[概要] タブで詳細を確認し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="62bb8-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="62bb8-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="62bb8-146">Related topics</span></span>
- [<span data-ttu-id="62bb8-147">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="62bb8-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="62bb8-148">ファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="62bb8-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="62bb8-149">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="62bb8-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="62bb8-150">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="62bb8-150">Manage indicators</span></span>](indicator-manage.md)
