---
title: Microsoft Defender for Endpoint on Linux のパフォーマンスの問題のトラブルシューティング
description: Microsoft Defender for Endpoint on Linux のパフォーマンスの問題をトラブルシューティングします。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, linux, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9964b27f29654a7cc474dc4fb8f84334ddaf381c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933219"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="25953-104">Microsoft Defender for Endpoint on Linux のパフォーマンスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="25953-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25953-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="25953-105">**Applies to:**</span></span>
- [<span data-ttu-id="25953-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="25953-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="25953-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25953-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="25953-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="25953-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25953-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="25953-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="25953-110">この記事では、Defender for Endpoint on Linux に関連するパフォーマンスの問題を絞り込む一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="25953-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="25953-111">リアルタイム保護 (RTP) は、デバイスを継続的に監視し、脅威から保護する、Linux 上の Defender for Endpoint の機能です。</span><span class="sxs-lookup"><span data-stu-id="25953-111">Real-time protection (RTP) is a feature of Defender for Endpoint on Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="25953-112">ファイルとプロセスの監視、その他のヒューリスティックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="25953-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="25953-113">実行中のアプリケーションとデバイスの特性によっては、Defender for Endpoint on Linux を実行するときに最適でないパフォーマンスが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="25953-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint on Linux.</span></span> <span data-ttu-id="25953-114">特に、短時間で多くのリソースにアクセスするアプリケーションまたはシステム プロセスは、Defender for Endpoint on Linux のパフォーマンスの問題につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25953-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="25953-115">開始する前に、 **他のセキュリティ製品がデバイスで現在実行されていないか確認してください**。</span><span class="sxs-lookup"><span data-stu-id="25953-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="25953-116">複数のセキュリティ製品が競合し、ホストのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25953-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="25953-117">次の手順を使用して、これらの問題のトラブルシューティングと軽減を行います。</span><span class="sxs-lookup"><span data-stu-id="25953-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="25953-118">次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="25953-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="25953-119">この方法は、Defender for Endpoint on Linux がパフォーマンスの問題に貢献するかどうかを絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="25953-119">This approach helps narrow down whether Defender for Endpoint on Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="25953-120">デバイスが組織によって管理されていない場合は、コマンド ラインからリアルタイム保護を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="25953-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="25953-121">デバイスが組織によって管理されている場合は、「Defender for Endpoint on Linux の設定」の手順に従って、管理者がリアルタイム保護 [を無効にすることができます](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="25953-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint on Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="25953-122">リアルタイム保護がオフの間にパフォーマンスの問題が解決しない場合、問題の発生源はエンドポイント検出および応答コンポーネントである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25953-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="25953-123">この場合、詳細な手順と軽減策については、カスタマー サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="25953-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="25953-124">最も多くのスキャンをトリガーしているアプリケーションを見つけるには、Defender for Endpoint on Linux によって収集されたリアルタイム統計を使用できます。</span><span class="sxs-lookup"><span data-stu-id="25953-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25953-125">この機能は、バージョン 100.90.70 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="25953-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="25953-126">この機能は、既定で and チャネル `Dogfood` で有効 `InsiderFast` になっています。</span><span class="sxs-lookup"><span data-stu-id="25953-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="25953-127">別の更新チャネルを使用している場合は、コマンド ラインからこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="25953-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="25953-128">この機能では、リアルタイム保護を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="25953-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="25953-129">リアルタイム保護の状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25953-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="25953-130">エントリが `real_time_protection_enabled` . `true`</span><span class="sxs-lookup"><span data-stu-id="25953-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="25953-131">それ以外の場合は、次のコマンドを実行して有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="25953-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="25953-132">現在の統計情報を収集するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="25953-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="25953-133">使用 ```--output json``` (ダブル ダッシュに注意してください) を使用すると、出力形式が解析の準備ができていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="25953-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="25953-134">このコマンドの出力には、すべてのプロセスと関連するスキャン アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="25953-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="25953-135">Linux システムで、次のコマンドを使用して **python パーサー high_cpu_parser.py の** サンプルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="25953-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="25953-136">このコマンドの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="25953-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="25953-137">次に、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="25953-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="25953-138">上記の出力は、パフォーマンスの問題に対する上位の投稿者の一覧です。</span><span class="sxs-lookup"><span data-stu-id="25953-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="25953-139">最初の列はプロセス識別子 (PID)、2 番目の列は te プロセス名、最後の列はスキャンされたファイルの数で、影響順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="25953-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="25953-140">たとえば、コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="25953-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="25953-141">Defender for Endpoint on Linux のパフォーマンスを向上するには、行の下に数値が最も多いディフェンダーを見つけて除外 `Total files scanned` を追加します。</span><span class="sxs-lookup"><span data-stu-id="25953-141">To improve the performance of Defender for Endpoint on Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="25953-142">詳細については、「Linux での Defender for Endpoint の除外の構成と [検証」を参照してください](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="25953-142">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="25953-143">アプリケーションは、統計をメモリに格納し、ファイルのアクティビティが開始され、リアルタイム保護が有効にされた後にのみ追跡します。</span><span class="sxs-lookup"><span data-stu-id="25953-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="25953-144">リアルタイム保護がオフの前または期間中に起動されたプロセスはカウントされません。</span><span class="sxs-lookup"><span data-stu-id="25953-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="25953-145">さらに、トリガーされたスキャンがカウントされるイベントのみ。</span><span class="sxs-lookup"><span data-stu-id="25953-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="25953-146">パフォーマンスの問題に寄与するプロセスまたはディスクの場所を除外して、Microsoft Defender for Endpoint on Linux を構成し、リアルタイム保護を再び有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="25953-146">Configure Microsoft Defender for Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="25953-147">詳細については [、「Configure and validate exclusions for Microsoft Defender for Endpoint on Linux」を参照してください](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="25953-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint on Linux](linux-exclusions.md).</span></span>
