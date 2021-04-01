---
title: Microsoft Defender for Endpoint for Mac のパフォーマンスの問題のトラブルシューティング
description: Microsoft Defender for Endpoint for Mac のパフォーマンスの問題をトラブルシューティングします。
keywords: microsoft, defender, atp, mac, performance
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6ff93b44627cf876384522f0c4f25d22347c8661
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476257"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="908c2-104">Microsoft Defender for Endpoint for Mac のパフォーマンスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="908c2-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="908c2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="908c2-105">**Applies to:**</span></span>

- [<span data-ttu-id="908c2-106">Mac 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="908c2-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="908c2-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="908c2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="908c2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="908c2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="908c2-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="908c2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="908c2-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="908c2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="908c2-111">このトピックでは、Microsoft Defender for Endpoint for Mac に関連するパフォーマンスの問題を絞り込む一般的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="908c2-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="908c2-112">リアルタイム保護 (RTP) は、Microsoft Defender for Endpoint for Mac の機能であり、デバイスを継続的に監視し、脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="908c2-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="908c2-113">ファイルとプロセスの監視、その他のヒューリスティックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="908c2-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="908c2-114">実行中のアプリケーションとデバイスの特性によっては、Microsoft Defender for Endpoint for Mac を実行するときに最適でないパフォーマンスが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="908c2-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="908c2-115">特に、短時間で多くのリソースにアクセスするアプリケーションまたはシステム プロセスは、Microsoft Defender for Endpoint for Mac のパフォーマンスの問題につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="908c2-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="908c2-116">次の手順を使用して、これらの問題のトラブルシューティングと軽減を行います。</span><span class="sxs-lookup"><span data-stu-id="908c2-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="908c2-117">次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="908c2-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="908c2-118">この方法は、Microsoft Defender for Endpoint for Mac がパフォーマンスの問題に貢献するかどうかを絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="908c2-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

      <span data-ttu-id="908c2-119">デバイスが組織によって管理されていない場合は、次のいずれかのオプションを使用してリアルタイム保護を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="908c2-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="908c2-120">ユーザー インターフェイスから。</span><span class="sxs-lookup"><span data-stu-id="908c2-120">From the user interface.</span></span> <span data-ttu-id="908c2-121">Microsoft Defender for Endpoint for Mac を開き、[設定の管理] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="908c2-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![リアルタイム保護のスクリーンショットを管理する](images/mdatp-36-rtp.png)

    - <span data-ttu-id="908c2-123">ターミナルから。</span><span class="sxs-lookup"><span data-stu-id="908c2-123">From the Terminal.</span></span> <span data-ttu-id="908c2-124">セキュリティ上の目的で、この操作には昇格が必要です。</span><span class="sxs-lookup"><span data-stu-id="908c2-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="908c2-125">デバイスが組織によって管理されている場合は [、「Microsoft Defender for Endpoint for Mac](mac-preferences.md)の設定」の手順に従って、管理者がリアルタイム保護を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="908c2-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>
      
      <span data-ttu-id="908c2-126">リアルタイム保護がオフの間にパフォーマンスの問題が解決しない場合、問題の発生源はエンドポイント検出および応答コンポーネントである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="908c2-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="908c2-127">この場合、詳細な手順と軽減策については、カスタマー サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="908c2-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="908c2-128">Finder を開き、[アプリケーション ユーティリティ **]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="908c2-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="908c2-129">[ **アクティビティ モニター] を** 開き、システムでリソースを使用しているアプリケーションを分析します。</span><span class="sxs-lookup"><span data-stu-id="908c2-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="908c2-130">一般的な例としては、ソフトウェアアップデータとコンパイラが含まれます。</span><span class="sxs-lookup"><span data-stu-id="908c2-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="908c2-131">最も多くのスキャンをトリガーしているアプリケーションを見つけるには、Defender for Endpoint for Mac によって収集されたリアルタイム統計を使用できます。</span><span class="sxs-lookup"><span data-stu-id="908c2-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="908c2-132">この機能は、バージョン 100.90.70 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="908c2-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="908c2-133">この機能は **、Dogfood** チャネルと InsiderFast チャネルで既定 **で有効** になっています。</span><span class="sxs-lookup"><span data-stu-id="908c2-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="908c2-134">別の更新チャネルを使用している場合は、コマンド ラインからこの機能を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="908c2-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="908c2-135">この機能では、リアルタイム保護を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="908c2-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="908c2-136">リアルタイム保護の状態を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="908c2-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="908c2-137">このエントリが **true real_time_protection_enabled** 確認します。</span><span class="sxs-lookup"><span data-stu-id="908c2-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="908c2-138">それ以外の場合は、次のコマンドを実行して有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="908c2-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="908c2-139">現在の統計情報を収集するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="908c2-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > <span data-ttu-id="908c2-140">**--output json** (ダブル ダッシュ) を使用すると、出力形式が解析の準備ができていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="908c2-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="908c2-141">このコマンドの出力には、すべてのプロセスと関連するスキャン アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="908c2-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="908c2-142">Mac システムで、次のコマンドを使用して python パーサー high_cpu_parser.py のサンプルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="908c2-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="908c2-143">このコマンドの出力は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="908c2-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="908c2-144">次に、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="908c2-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="908c2-145">上記の出力は、パフォーマンスの問題に対する上位の投稿者の一覧です。</span><span class="sxs-lookup"><span data-stu-id="908c2-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="908c2-146">最初の列はプロセス識別子 (PID)、2 番目の列は te プロセス名、最後の列はスキャンされたファイルの数で、影響順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="908c2-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="908c2-147">たとえば、コマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="908c2-147">For example, the output of the command will be something like the below:</span></span>

      ```output
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

      <span data-ttu-id="908c2-148">Defender for Endpoint for Mac のパフォーマンスを向上するには、[ファイルの合計スキャン] 行の下で最も数が多いファイルを見つけて、除外を追加します。</span><span class="sxs-lookup"><span data-stu-id="908c2-148">To improve the performance of Defender for Endpoint for Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="908c2-149">詳細については、「Defender for Endpoint for Linux の除外の構成と検証 [」を参照してください](linux-exclusions.md)。</span><span class="sxs-lookup"><span data-stu-id="908c2-149">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="908c2-150">アプリケーションは、統計をメモリに格納し、ファイルのアクティビティが開始され、リアルタイム保護が有効にされた後にのみ追跡します。</span><span class="sxs-lookup"><span data-stu-id="908c2-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="908c2-151">リアルタイム保護がオフの前または期間中に起動されたプロセスはカウントされません。</span><span class="sxs-lookup"><span data-stu-id="908c2-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="908c2-152">さらに、トリガーされたスキャンがカウントされるイベントのみ。</span><span class="sxs-lookup"><span data-stu-id="908c2-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="908c2-153">パフォーマンスの問題に寄与するプロセスまたはディスクの場所の除外を使用して Microsoft Defender for Endpoint for Mac を構成し、リアルタイム保護を再び有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="908c2-153">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="908c2-154">詳細 [については、「Configure and validate exclusions for Microsoft Defender for Endpoint for Mac」](mac-exclusions.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="908c2-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
