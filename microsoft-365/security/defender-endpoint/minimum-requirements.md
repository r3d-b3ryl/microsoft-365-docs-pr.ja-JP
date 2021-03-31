---
title: エンドポイント用 Microsoft Defender の最小要件
description: デバイスをサービスにオンボーディングする場合のライセンス要件と要件を理解する
keywords: 最小要件、ライセンス、比較表
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
ms.openlocfilehash: 1b203a29083aaa4a1f86abcd7e2c7b24bd63f186
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445746"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="6ef5d-104">エンドポイント用 Microsoft Defender の最小要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6ef5d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6ef5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ef5d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6ef5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6ef5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ef5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6ef5d-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6ef5d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ef5d-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="6ef5d-110">サービスへのデバイスのオンボーディングには、いくつかの最小要件があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="6ef5d-111">サービスにデバイスをオンボードするライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="6ef5d-112">Defender for Endpoint: Defender for Endpoint Tech Community の [最新の機能強化について説明します](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="6ef5d-113">Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="6ef5d-114">読み取り: [MITRE ATT および CK&評価からの分析情報](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6ef5d-115">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-115">Licensing requirements</span></span>
<span data-ttu-id="6ef5d-116">エンドポイント用 Microsoft Defender には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="6ef5d-117">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="6ef5d-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="6ef5d-118">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="6ef5d-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="6ef5d-119">Windows 10 Enterprise E5 を含む Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="6ef5d-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="6ef5d-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="6ef5d-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="6ef5d-121">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="6ef5d-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="6ef5d-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="6ef5d-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="6ef5d-123">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6ef5d-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-124">対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="6ef5d-125">Microsoft Defender for Endpoint は、クラウド ソリューション プロバイダー (CSP) から購入できます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="6ef5d-126">RDSH VM では、エンドポイント 用の個別の Defender ライセンスは必要とできません。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="6ef5d-127">Microsoft Defender for Endpoint for servers には、次のいずれかのライセンス オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="6ef5d-128">Azure Defender が有効になっている Azure セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="6ef5d-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="6ef5d-129">Microsoft Defender for Endpoint for Server (対象サーバーごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="6ef5d-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-130">お客様は、以下のユーザー ライセンスの 1 つ以上に対して最低 50 ライセンスを合計している場合、Microsoft Defender for Endpoint for Servers のサーバー ライセンス (対象サーバーのオペレーティング システム環境 (OSE) ごとに 1 つ) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="6ef5d-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6ef5d-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="6ef5d-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="6ef5d-132">Windows E5/A5</span></span>
> * <span data-ttu-id="6ef5d-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="6ef5d-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="6ef5d-134">Microsoft 365 E5/A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="6ef5d-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="6ef5d-135">ライセンスの詳細については、「 [製品](https://www.microsoft.com/licensing/terms/) 条項」サイトを参照し、アカウント チームと一緒に使用して、契約条件の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="6ef5d-136">Windows 10 エディションの機能の配列の詳細については [、「Compare Windows 10 editions」を参照してください](https://www.microsoft.com/windowsforbusiness/compare)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="6ef5d-137">Windows 10 商用エディションの比較の詳細な比較表については、比較 PDF を [参照してください](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="6ef5d-138">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-138">Browser requirements</span></span>
<span data-ttu-id="6ef5d-139">Defender for Endpoint へのアクセスはブラウザーを介して行われ、次のブラウザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="6ef5d-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6ef5d-140">Microsoft Edge</span></span>
- <span data-ttu-id="6ef5d-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="6ef5d-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-142">他のブラウザーが動作する場合は、前述のブラウザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="6ef5d-143">ハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="6ef5d-144">サポートされている Windows バージョン</span><span class="sxs-lookup"><span data-stu-id="6ef5d-144">Supported Windows versions</span></span>
- <span data-ttu-id="6ef5d-145">Windows 7 SP1エンタープライズ ([サポートには ESU が必要です](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。)</span><span class="sxs-lookup"><span data-stu-id="6ef5d-145">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="6ef5d-146">Windows 7 SP1 Pro ([サポートには ESU が必要](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)です。)</span><span class="sxs-lookup"><span data-stu-id="6ef5d-146">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="6ef5d-147">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6ef5d-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="6ef5d-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="6ef5d-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="6ef5d-149">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6ef5d-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="6ef5d-150">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="6ef5d-150">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="6ef5d-151">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="6ef5d-151">Windows 10 Education</span></span>
- <span data-ttu-id="6ef5d-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="6ef5d-152">Windows 10 Pro</span></span>
- <span data-ttu-id="6ef5d-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="6ef5d-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="6ef5d-154">Windows サーバー</span><span class="sxs-lookup"><span data-stu-id="6ef5d-154">Windows server</span></span>
  - <span data-ttu-id="6ef5d-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="6ef5d-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="6ef5d-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6ef5d-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="6ef5d-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6ef5d-157">Windows Server 2016</span></span>
  - <span data-ttu-id="6ef5d-158">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="6ef5d-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="6ef5d-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="6ef5d-159">Windows Server 2019</span></span>
- <span data-ttu-id="6ef5d-160">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="6ef5d-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="6ef5d-161">ネットワーク上のデバイスで、これらのエディションのいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="6ef5d-162">デバイス上の Defender for Endpoint のハードウェア要件は、サポートされているエディションで同じです。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-163">モバイル バージョンの Windows を実行しているコンピューター (Windows CE Windows 10 Mobile など) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="6ef5d-164">Windows 10 Enterprise 2016 LTSB を実行している仮想マシンは、Microsoft 以外の仮想化プラットフォームで実行すると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="6ef5d-165">仮想環境では、Windows 10 Enterprise LTSC 2019 以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="6ef5d-166">その他のサポートされているオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6ef5d-166">Other supported operating systems</span></span>
- <span data-ttu-id="6ef5d-167">Android</span><span class="sxs-lookup"><span data-stu-id="6ef5d-167">Android</span></span>
- <span data-ttu-id="6ef5d-168">iOS</span><span class="sxs-lookup"><span data-stu-id="6ef5d-168">iOS</span></span>
- <span data-ttu-id="6ef5d-169">Linux</span><span class="sxs-lookup"><span data-stu-id="6ef5d-169">Linux</span></span>
- <span data-ttu-id="6ef5d-170">macOS</span><span class="sxs-lookup"><span data-stu-id="6ef5d-170">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-171">統合が機能するには、Defender for Endpoint と互換性がある Android、iOS、macOS の Linux ディストリビューションとバージョンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-171">You'll need to confirm the Linux distributions and versions of Android, iOS and macOS you've are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="6ef5d-172">ネットワークとデータのストレージと構成の要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-172">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="6ef5d-173">オンボーディング ウィザードを初めて実行する場合は、Microsoft Defender for Endpoint 関連情報の保存場所 (欧州連合、英国、または米国のデータセンター) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="6ef5d-174">初回セットアップ後にデータストレージの場所を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="6ef5d-175">Microsoft が [データを保存する](data-storage-privacy.md) 場所と方法の詳細については、Microsoft Defender for Endpoint のデータ ストレージとプライバシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="6ef5d-176">診断データの設定</span><span class="sxs-lookup"><span data-stu-id="6ef5d-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-177">Microsoft Defender for Endpoint は、有効になっている限り、特定の診断レベルを必要としません。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="6ef5d-178">組織内のすべてのデバイスで診断データ サービスが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="6ef5d-179">既定では、このサービスは有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-179">By default, this service is enabled.</span></span> <span data-ttu-id="6ef5d-180">センサー データを取得する方法を確認する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="6ef5d-181">**コマンド ラインを使用して、Windows 10 診断データ サービスのスタートアップの種類を確認します**。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="6ef5d-182">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="6ef5d-183">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="6ef5d-184">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="6ef5d-185">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="6ef5d-186">サービスが有効になっている場合、結果は次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack の sc クエリ コマンドの結果](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="6ef5d-188">サービスが自動的に開始に設定されている場合は、START_TYPEに設定する **必要AUTO_START。**</span><span class="sxs-lookup"><span data-stu-id="6ef5d-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="6ef5d-189">**コマンド ラインを使用して、Windows 10 診断データ サービスを自動的に開始する設定を行います。**</span><span class="sxs-lookup"><span data-stu-id="6ef5d-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="6ef5d-190">エンドポイントで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="6ef5d-191">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="6ef5d-192">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="6ef5d-193">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="6ef5d-194">成功メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-194">A success message is displayed.</span></span> <span data-ttu-id="6ef5d-195">次のコマンドを入力して変更を確認し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="6ef5d-196">インターネット接続</span><span class="sxs-lookup"><span data-stu-id="6ef5d-196">Internet connectivity</span></span>
<span data-ttu-id="6ef5d-197">デバイス上のインターネット接続は、直接またはプロキシ経由で必要です。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="6ef5d-198">Defender for Endpoint センサーは、1 日の平均帯域幅 5 MB を使用して Defender for Endpoint クラウド サービスと通信し、サイバー データを報告できます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="6ef5d-199">ファイルのアップロードや調査パッケージ コレクションなどの 1 回限りでのアクティビティは、この 1 日の平均帯域幅には含まれません。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="6ef5d-200">追加のプロキシ構成設定の詳細については、「デバイス プロキシとインターネット接続の設定 [を構成する」を参照してください](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="6ef5d-201">デバイスをオンボードする前に、診断データ サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="6ef5d-202">このサービスは、Windows 10 で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="6ef5d-203">Microsoft Defender ウイルス対策の構成要件</span><span class="sxs-lookup"><span data-stu-id="6ef5d-203">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="6ef5d-204">Defender for Endpoint エージェントは、Microsoft Defender Antivirus がファイルをスキャンし、ファイルに関する情報を提供する機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="6ef5d-205">Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかを問う場合は、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="6ef5d-206">詳細については [、「Manage Microsoft Defender Antivirus updates and apply baselines」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="6ef5d-207">Microsoft Defender Antivirus が組織内のアクティブなマルウェア対策ではない場合、Defender for Endpoint サービスを使用すると、Microsoft Defender ウイルス対策はパッシブ モードになります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="6ef5d-208">組織でグループ ポリシーなどの方法で Microsoft Defender Antivirus を無効にしている場合は、オンボードされているデバイスをこのグループ ポリシーから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="6ef5d-209">サーバーをオンボーディングしている場合に、Microsoft Defender Antivirus がサーバー上のアクティブなマルウェア対策ではない場合は、パッシブ モードに切り替わるかアンインストールするように Microsoft Defender ウイルス対策を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="6ef5d-210">構成はサーバーのバージョンに依存します。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="6ef5d-211">詳細については [、「Microsoft Defender ウイルス対策の互換性」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-211">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6ef5d-212">通常のグループ ポリシーはタンパー プロテクションには適用されません。タンパー プロテクションがオンの場合、Microsoft Defender ウイルス対策設定の変更は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="6ef5d-213">Microsoft Defender ウイルス対策早期起動マルウェア対策 (ELAM) ドライバーが有効になっている</span><span class="sxs-lookup"><span data-stu-id="6ef5d-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="6ef5d-214">Microsoft Defender Antivirus をデバイスのプライマリマルウェア対策製品として実行している場合、Defender for Endpoint エージェントは正常にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="6ef5d-215">サードパーティのマルウェア対策クライアントを実行し、モバイル デバイス管理ソリューションまたは Microsoft Endpoint Manager (現在のブランチ) を使用する場合は、Microsoft Defender ウイルス対策 ELAM ドライバーが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="6ef5d-216">詳細については、「ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認 [する」を参照してください](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="6ef5d-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="6ef5d-217">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ef5d-217">Related topics</span></span>
- [<span data-ttu-id="6ef5d-218">Microsoft Defender for Endpoint の展開をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6ef5d-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="6ef5d-219">オンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="6ef5d-219">Onboard devices</span></span>](onboard-configure.md)
