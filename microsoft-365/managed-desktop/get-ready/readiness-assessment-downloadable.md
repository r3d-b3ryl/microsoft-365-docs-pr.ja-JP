---
title: ダウンロード可能な準備状況の評価チェック
description: 必要なエンドポイントを含むデバイスとネットワークの設定を確認する
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581036"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="4262a-104">ダウンロード可能な準備状況の評価チェック</span><span class="sxs-lookup"><span data-stu-id="4262a-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="4262a-105">Microsoft Managed Desktop とうまく機能するには、デバイスがハードウェアと設定に関する特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="4262a-106">また、各デバイスが主要なエンドポイントに到達できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="4262a-107">このツールをダウンロードして実行して、HTML レポートを取得し、結果を表示し、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4262a-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="4262a-108">ツールとサポート ファイルをダウンロードし、Microsoft Managed Desktop に登録する各デバイスで手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4262a-109">チェックごとに、ツールは次の 3 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="4262a-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="4262a-110">結果</span><span class="sxs-lookup"><span data-stu-id="4262a-110">Result</span></span>  |<span data-ttu-id="4262a-111">意味</span><span class="sxs-lookup"><span data-stu-id="4262a-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4262a-112">準備完了</span><span class="sxs-lookup"><span data-stu-id="4262a-112">Ready</span></span>     | <span data-ttu-id="4262a-113">登録を完了する前に、アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4262a-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="4262a-114">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="4262a-114">Advisory</span></span>    | <span data-ttu-id="4262a-115">登録とユーザーの最適なエクスペリエンスを得るには、ツールの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4262a-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4262a-116">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4262a-117">使用不可能</span><span class="sxs-lookup"><span data-stu-id="4262a-117">Not ready</span></span> | <span data-ttu-id="4262a-118">*これらの問題を* 解決しない場合、登録は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4262a-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="4262a-119">ツールの手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="4262a-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="4262a-120">チェッカーを取得する</span><span class="sxs-lookup"><span data-stu-id="4262a-120">Obtain the checker</span></span>

<span data-ttu-id="4262a-121">から.zipファイルをダウンロードします https://aka.ms/mmddratoolv0 。</span><span class="sxs-lookup"><span data-stu-id="4262a-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="4262a-122">ツールを実行しているユーザーは、そのツールを実行しているデバイスに対するローカル管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="4262a-123">次に、次の手順に従ってツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="4262a-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="4262a-124">ダウンロードしたファイルを.zipする各デバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4262a-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="4262a-125">圧縮されたダウンロード内のすべてのファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="4262a-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="4262a-126">[実行 **Microsoft.MMD.DeviceReadinessAssessmentTool.exe] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4262a-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="4262a-127">[ユーザー アクセス制御] プロンプトが表示されたら、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4262a-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="4262a-128">ツールが実行され、既定のブラウザーでレポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="4262a-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="4262a-129">また、共有の場所に.zipアーカイブをダウンロードして抽出し、各Microsoft.MMD.DeviceReadinessAssessmentTool.exeからアクセスし、ローカルで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4262a-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="4262a-130">チェック</span><span class="sxs-lookup"><span data-stu-id="4262a-130">Checks</span></span>

<span data-ttu-id="4262a-131">ダウンロード可能なツールは、次のデバイスおよびネットワーク関連のアイテムをチェックします。</span><span class="sxs-lookup"><span data-stu-id="4262a-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="4262a-132">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="4262a-132">Hardware</span></span>

<span data-ttu-id="4262a-133">Microsoft Managed Desktop を使用するには、デバイスが特定のハードウェア要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4262a-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4262a-134">現時点では、特定 [の承認済みデバイス](../service-description/device-list.md) のみ登録が許可されています。</span><span class="sxs-lookup"><span data-stu-id="4262a-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="4262a-135">デバイスがチェックに失敗した場合、Microsoft Managed Desktop と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="4262a-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="4262a-136">ネットワーク エンドポイント</span><span class="sxs-lookup"><span data-stu-id="4262a-136">Network endpoints</span></span>

<span data-ttu-id="4262a-137">デバイスは、Microsoft Managed Desktop [で動作](network.md) するいくつかの主要なエンドポイントに多く到達できます。</span><span class="sxs-lookup"><span data-stu-id="4262a-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4262a-138">ツールが [準備完了] **の結果を** 報告する場合は、詳細なレポートを参照して、到達不能だったエンドポイントを確認します。</span><span class="sxs-lookup"><span data-stu-id="4262a-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="4262a-139">その後、ファイアウォールまたは他のネットワーク設定を調整して、それらのエンドポイントに到達可能にしてください。</span><span class="sxs-lookup"><span data-stu-id="4262a-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="4262a-140">その他の設定</span><span class="sxs-lookup"><span data-stu-id="4262a-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="4262a-141">エンタープライズ Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="4262a-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="4262a-142">アドバイザリ **の結果** は、証明書とプロファイルが適切に動作する必要があるいくつかの Wi-Fi プロファイルを使用しているという意味です。</span><span class="sxs-lookup"><span data-stu-id="4262a-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4262a-143">詳細については、「証明書の [展開」および「Wi-Fi/VPN プロファイル」を参照してください](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。</span><span class="sxs-lookup"><span data-stu-id="4262a-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="4262a-144">LAN プロファイル</span><span class="sxs-lookup"><span data-stu-id="4262a-144">LAN profiles</span></span>

<span data-ttu-id="4262a-145">アドバイザリ **の結果** は、証明書とプロファイルが適切に動作する必要がある LAN を持っているという意味です。</span><span class="sxs-lookup"><span data-stu-id="4262a-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="4262a-146">詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="4262a-147">VPN プロファイル</span><span class="sxs-lookup"><span data-stu-id="4262a-147">VPN profiles</span></span>

<span data-ttu-id="4262a-148">アドバイザリ **の結果** は、仮想プライベート ネットワーク (VPN) を使用しているという意味です。</span><span class="sxs-lookup"><span data-stu-id="4262a-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="4262a-149">Microsoft Intune と統合された証明書を展開する VPN プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4262a-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="4262a-150">詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="4262a-151">マップされたドライブ</span><span class="sxs-lookup"><span data-stu-id="4262a-151">Mapped drives</span></span>

<span data-ttu-id="4262a-152">アドバイザリ **の結果** は、マップされたドライブがいくつかあるという意味で、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="4262a-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="4262a-153">詳細については、「マップされたドライブ [を Microsoft Managed Desktop 用に準備する」を参照してください](mapped-drives.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="4262a-154">印刷キュー</span><span class="sxs-lookup"><span data-stu-id="4262a-154">Print queues</span></span>

<span data-ttu-id="4262a-155">アドバイザリ **の結果** は、未処理の印刷キューがいくつかあるという意味で、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="4262a-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="4262a-156">1 つの解決策は、クラウド印刷を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="4262a-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="4262a-157">詳細については [、「Microsoft Managed Desktop の印刷リソースを準備する」を参照してください](printing.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="4262a-158">プロキシ</span><span class="sxs-lookup"><span data-stu-id="4262a-158">Proxies</span></span>

<span data-ttu-id="4262a-159">アドバイザリ **の結果** は、プロキシ サーバーが使用されているという意味です。</span><span class="sxs-lookup"><span data-stu-id="4262a-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="4262a-160">詳細については [、「Microsoft Managed Desktop のネットワーク構成」を参照してください](network.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

