---
title: ダウンロード可能な準備状況の評価チェック
description: 必要なエンドポイントを含む、デバイスとネットワークの設定を確認します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922021"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="73c29-104">ダウンロード可能な準備状況の評価チェック</span><span class="sxs-lookup"><span data-stu-id="73c29-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="73c29-105">Microsoft マネージド デスクトップで動作するには、デバイスがハードウェアと設定に関する特定の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="73c29-106">また、各デバイスが主要なエンドポイントに到達できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="73c29-107">このツールをダウンロードして実行し、HTML レポートを取得し、結果を表示して、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="73c29-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="73c29-108">ツールとサポート ファイルをダウンロードし、Microsoft マネージド デスクトップに登録する各デバイスで手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="73c29-109">チェックごとに、ツールは次の 3 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="73c29-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="73c29-110">結果</span><span class="sxs-lookup"><span data-stu-id="73c29-110">Result</span></span>  |<span data-ttu-id="73c29-111">意味</span><span class="sxs-lookup"><span data-stu-id="73c29-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="73c29-112">準備完了</span><span class="sxs-lookup"><span data-stu-id="73c29-112">Ready</span></span>     | <span data-ttu-id="73c29-113">登録を完了する前に、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="73c29-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="73c29-114">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="73c29-114">Advisory</span></span>    | <span data-ttu-id="73c29-115">登録とユーザーに最適なエクスペリエンスを得る場合は、ツールの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="73c29-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="73c29-116">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="73c29-117">使用不可能</span><span class="sxs-lookup"><span data-stu-id="73c29-117">Not ready</span></span> | <span data-ttu-id="73c29-118">*これらの問題を* 解決しない場合、登録は失敗します。</span><span class="sxs-lookup"><span data-stu-id="73c29-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="73c29-119">ツールの手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="73c29-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="73c29-120">チェッカーを取得する</span><span class="sxs-lookup"><span data-stu-id="73c29-120">Obtain the checker</span></span>

<span data-ttu-id="73c29-121">.zip ファイルをダウンロードします https://aka.ms/mmddratoolv0 。</span><span class="sxs-lookup"><span data-stu-id="73c29-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="73c29-122">ツールを実行するユーザーは、ツールを実行しているデバイスに対するローカル管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="73c29-123">次に、次の手順に従ってツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="73c29-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="73c29-124">ダウンロードした .zip ファイルを、確認する各デバイスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="73c29-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="73c29-125">圧縮ダウンロード内のすべてのファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="73c29-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="73c29-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="73c29-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="73c29-127">ユーザー アクセス制御のプロンプトが表示されたら、[はい] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="73c29-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="73c29-128">ツールが実行され、既定のブラウザーでレポートが開きます。</span><span class="sxs-lookup"><span data-stu-id="73c29-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="73c29-129">また、.zip アーカイブをダウンロードして共有の場所に抽出し、各 **デバイス** Microsoft.MMD.DeviceReadinessAssessmentTool.exeにアクセスして、ローカルで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="73c29-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="73c29-130">チェック</span><span class="sxs-lookup"><span data-stu-id="73c29-130">Checks</span></span>

<span data-ttu-id="73c29-131">ダウンロード可能なツールは、デバイスとネットワークに関連する次の項目をチェックします。</span><span class="sxs-lookup"><span data-stu-id="73c29-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="73c29-132">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="73c29-132">Hardware</span></span>

<span data-ttu-id="73c29-133">デバイスが Microsoft マネージド デスクトップで動作するには、特定のハードウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c29-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="73c29-134">現在、登録 [できるのは特定の](../service-description/device-list.md) 承認済みデバイスのみです。</span><span class="sxs-lookup"><span data-stu-id="73c29-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="73c29-135">デバイスがチェックに失敗した場合、Microsoft マネージド デスクトップと互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="73c29-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="73c29-136">ネットワーク エンドポイント</span><span class="sxs-lookup"><span data-stu-id="73c29-136">Network endpoints</span></span>

<span data-ttu-id="73c29-137">デバイスは、Microsoft マネージド デスクトップで [動作するために](network.md) 、いくつかの主要なエンドポイントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73c29-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="73c29-138">ツールで準備ができていない結果 **が** 報告された場合は、詳細なレポートを参照して、到達不能なエンドポイントを確認します。</span><span class="sxs-lookup"><span data-stu-id="73c29-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="73c29-139">次に、ファイアウォールまたは他のネットワーク設定を調整して、それらのエンドポイントに到達可能にします。</span><span class="sxs-lookup"><span data-stu-id="73c29-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="73c29-140">その他の設定</span><span class="sxs-lookup"><span data-stu-id="73c29-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="73c29-141">エンタープライズ Wi-Fi プロファイル</span><span class="sxs-lookup"><span data-stu-id="73c29-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="73c29-142">アドバイザリ **の結果** は、証明書とプロファイルが正常に動作する必要がある Wi-Fi プロファイルを使用しているという意味です。</span><span class="sxs-lookup"><span data-stu-id="73c29-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="73c29-143">詳細については、「証明書と [Wi-Fi/VPN プロファイルを展開する」を参照してください](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)。</span><span class="sxs-lookup"><span data-stu-id="73c29-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="73c29-144">LAN プロファイル</span><span class="sxs-lookup"><span data-stu-id="73c29-144">LAN profiles</span></span>

<span data-ttu-id="73c29-145">アドバイザリ **の結果** は、証明書とプロファイルが正常に動作する必要がある LAN を持っているという意味です。</span><span class="sxs-lookup"><span data-stu-id="73c29-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="73c29-146">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="73c29-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="73c29-147">VPN プロファイル</span><span class="sxs-lookup"><span data-stu-id="73c29-147">VPN profiles</span></span>

<span data-ttu-id="73c29-148">アドバイザリ **の結果** は、仮想プライベート ネットワーク (VPN) を使用しているという意味です。</span><span class="sxs-lookup"><span data-stu-id="73c29-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="73c29-149">Microsoft Intune と統合された証明書を展開する VPN プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="73c29-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="73c29-150">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="73c29-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="73c29-151">マップされたドライブ</span><span class="sxs-lookup"><span data-stu-id="73c29-151">Mapped drives</span></span>

<span data-ttu-id="73c29-152">アドバイザリ **の結果** は、マップされたドライブがいくつかあるという意味ですが、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="73c29-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="73c29-153">詳細については、「Microsoft マネージド デスクトップ用 [にマップされたドライブを準備する」を参照してください](mapped-drives.md)。</span><span class="sxs-lookup"><span data-stu-id="73c29-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="73c29-154">印刷キュー</span><span class="sxs-lookup"><span data-stu-id="73c29-154">Print queues</span></span>

<span data-ttu-id="73c29-155">アドバイザリ **の結果** は、未処理の印刷キューがいくつかあるという意味ですが、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="73c29-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="73c29-156">1 つのソリューションは、クラウド印刷を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="73c29-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="73c29-157">詳細については、「Microsoft マネージド [デスクトップの印刷リソースを準備する」を参照してください](printing.md)。</span><span class="sxs-lookup"><span data-stu-id="73c29-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="73c29-158">プロキシ</span><span class="sxs-lookup"><span data-stu-id="73c29-158">Proxies</span></span>

<span data-ttu-id="73c29-159">アドバイザリ **の結果** は、プロキシ サーバーが使用されているという意味です。</span><span class="sxs-lookup"><span data-stu-id="73c29-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="73c29-160">詳細については、「Microsoft マネージド [デスクトップのネットワーク構成」を参照してください](network.md)。</span><span class="sxs-lookup"><span data-stu-id="73c29-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

