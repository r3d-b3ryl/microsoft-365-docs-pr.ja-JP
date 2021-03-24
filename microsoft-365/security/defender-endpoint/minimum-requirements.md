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
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061396"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="36107-104">エンドポイント用 Microsoft Defender の最小要件</span><span class="sxs-lookup"><span data-stu-id="36107-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="36107-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="36107-105">**Applies to:**</span></span>
- [<span data-ttu-id="36107-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36107-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="36107-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36107-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="36107-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="36107-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="36107-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="36107-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="36107-110">サービスへのデバイスのオンボーディングには、いくつかの最小要件があります。</span><span class="sxs-lookup"><span data-stu-id="36107-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="36107-111">サービスにデバイスをオンボードするライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="36107-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="36107-112">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="36107-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="36107-113">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="36107-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="36107-114">Defender for Endpoint: Defender for Endpoint Tech Community の [最新の機能強化について説明します](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)。</span><span class="sxs-lookup"><span data-stu-id="36107-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="36107-115">Defender for Endpoint は、最近の MITRE 評価で業界をリードする光学機能と検出機能を実証しました。</span><span class="sxs-lookup"><span data-stu-id="36107-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="36107-116">読み取り: [MITRE ATT および CK&評価からの分析情報](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。</span><span class="sxs-lookup"><span data-stu-id="36107-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="36107-117">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="36107-117">Licensing requirements</span></span>
<span data-ttu-id="36107-118">エンドポイント用 Microsoft Defender には、次のいずれかの Microsoft ボリューム ライセンスオファーが必要です。</span><span class="sxs-lookup"><span data-stu-id="36107-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="36107-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="36107-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="36107-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="36107-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="36107-121">Windows 10 Enterprise E5 を含む Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="36107-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="36107-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="36107-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="36107-123">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="36107-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="36107-124">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="36107-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="36107-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36107-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="36107-126">対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。</span><span class="sxs-lookup"><span data-stu-id="36107-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="36107-127">Microsoft Defender for Endpoint は、クラウド ソリューション プロバイダー (CSP) から購入できます。</span><span class="sxs-lookup"><span data-stu-id="36107-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="36107-128">Microsoft Defender for Endpoint for servers には、次のいずれかのライセンス オプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="36107-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="36107-129">Azure Defender が有効になっている Azure セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="36107-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="36107-130">Microsoft Defender for Endpoint for Server (対象サーバーごとに 1 つ)</span><span class="sxs-lookup"><span data-stu-id="36107-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="36107-131">お客様は、以下のユーザー ライセンスの 1 つ以上に対して最低 50 ライセンスを合計している場合、Microsoft Defender for Endpoint for Servers のサーバー ライセンス (対象サーバーのオペレーティング システム環境 (OSE) ごとに 1 つ) を取得できます。</span><span class="sxs-lookup"><span data-stu-id="36107-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="36107-132">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="36107-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="36107-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="36107-133">Windows E5/A5</span></span>
> * <span data-ttu-id="36107-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="36107-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="36107-135">Microsoft 365 E5/A5 セキュリティ</span><span class="sxs-lookup"><span data-stu-id="36107-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="36107-136">ライセンスの詳細については、「 [製品](https://www.microsoft.com/licensing/terms/) 条項」サイトを参照し、アカウント チームと一緒に使用して、契約条件の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="36107-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="36107-137">Windows 10 エディションの機能の配列の詳細については [、「Compare Windows 10 editions」を参照してください](https://www.microsoft.com/windowsforbusiness/compare)。</span><span class="sxs-lookup"><span data-stu-id="36107-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="36107-138">Windows 10 商用エディションの比較の詳細な比較表については、比較 PDF を [参照してください](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)。</span><span class="sxs-lookup"><span data-stu-id="36107-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="36107-139">ブラウザー要件</span><span class="sxs-lookup"><span data-stu-id="36107-139">Browser requirements</span></span>
<span data-ttu-id="36107-140">Defender for Endpoint へのアクセスはブラウザーを介して行われ、次のブラウザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="36107-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="36107-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36107-141">Microsoft Edge</span></span>
- <span data-ttu-id="36107-142">Internet Explorerバージョン 11</span><span class="sxs-lookup"><span data-stu-id="36107-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="36107-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="36107-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="36107-144">他のブラウザーが動作する場合は、前述のブラウザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="36107-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="36107-145">ハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="36107-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="36107-146">サポートされている Windows バージョン</span><span class="sxs-lookup"><span data-stu-id="36107-146">Supported Windows versions</span></span>
- <span data-ttu-id="36107-147">Windows 7 SP1エンタープライズ ([サポートには ESU が必要です](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)。)</span><span class="sxs-lookup"><span data-stu-id="36107-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="36107-148">Windows 7 SP1 Pro ([サポートには ESU が必要](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)です。)</span><span class="sxs-lookup"><span data-stu-id="36107-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="36107-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36107-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="36107-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="36107-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="36107-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36107-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="36107-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="36107-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="36107-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="36107-153">Windows 10 Education</span></span>
- <span data-ttu-id="36107-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="36107-154">Windows 10 Pro</span></span>
- <span data-ttu-id="36107-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="36107-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="36107-156">Windows サーバー</span><span class="sxs-lookup"><span data-stu-id="36107-156">Windows server</span></span>
  - <span data-ttu-id="36107-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="36107-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="36107-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="36107-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="36107-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="36107-159">Windows Server 2016</span></span>
  - <span data-ttu-id="36107-160">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="36107-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="36107-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="36107-161">Windows Server 2019</span></span>
- <span data-ttu-id="36107-162">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="36107-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="36107-163">ネットワーク上のデバイスで、これらのエディションのいずれかを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="36107-164">デバイス上の Defender for Endpoint のハードウェア要件は、サポートされているエディションで同じです。</span><span class="sxs-lookup"><span data-stu-id="36107-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="36107-165">モバイル バージョンの Windows を実行しているコンピューター (Windows CE Windows 10 Mobile など) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="36107-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="36107-166">Windows 10 Enterprise 2016 LTSB を実行している仮想マシンは、Microsoft 以外の仮想化プラットフォームで実行すると、パフォーマンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36107-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="36107-167">仮想環境では、Windows 10 Enterprise LTSC 2019 以降を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36107-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="36107-168">その他のサポートされているオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="36107-168">Other supported operating systems</span></span>
- <span data-ttu-id="36107-169">Android</span><span class="sxs-lookup"><span data-stu-id="36107-169">Android</span></span>
- <span data-ttu-id="36107-170">Linux</span><span class="sxs-lookup"><span data-stu-id="36107-170">Linux</span></span>
- <span data-ttu-id="36107-171">macOS</span><span class="sxs-lookup"><span data-stu-id="36107-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="36107-172">統合を機能するには、Defender for Endpoint と互換性のある Android と macOS の Linux ディストリビューションとバージョンを正確に知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="36107-173">ネットワークとデータのストレージと構成の要件</span><span class="sxs-lookup"><span data-stu-id="36107-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="36107-174">オンボーディング ウィザードを初めて実行する場合は、Microsoft Defender for Endpoint 関連情報の保存場所 (欧州連合、英国、または米国のデータセンター) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="36107-175">初回セットアップ後にデータストレージの場所を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="36107-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="36107-176">Microsoft が [データを保存する](data-storage-privacy.md) 場所と方法の詳細については、Microsoft Defender for Endpoint のデータ ストレージとプライバシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36107-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="36107-177">診断データの設定</span><span class="sxs-lookup"><span data-stu-id="36107-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="36107-178">Microsoft Defender for Endpoint は、有効になっている限り、特定の診断レベルを必要としません。</span><span class="sxs-lookup"><span data-stu-id="36107-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="36107-179">組織内のすべてのデバイスで診断データ サービスが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="36107-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="36107-180">既定では、このサービスは有効になっています。</span><span class="sxs-lookup"><span data-stu-id="36107-180">By default, this service is enabled.</span></span> <span data-ttu-id="36107-181">センサー データを取得する方法を確認する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="36107-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="36107-182">**コマンド ラインを使用して、Windows 10 診断データ サービスのスタートアップの種類を確認します**。</span><span class="sxs-lookup"><span data-stu-id="36107-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="36107-183">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="36107-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="36107-184">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="36107-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="36107-185">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36107-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="36107-186">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="36107-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="36107-187">サービスが有効になっている場合、結果は次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="36107-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack の sc クエリ コマンドの結果](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="36107-189">サービスが自動的に開始に設定されている場合は、START_TYPEに設定する必要 **AUTO_START。**</span><span class="sxs-lookup"><span data-stu-id="36107-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="36107-190">**コマンド ラインを使用して、Windows 10 診断データ サービスを自動的に開始する設定を行います。**</span><span class="sxs-lookup"><span data-stu-id="36107-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="36107-191">エンドポイントで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="36107-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="36107-192">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="36107-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="36107-193">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="36107-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="36107-194">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="36107-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="36107-195">成功メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36107-195">A success message is displayed.</span></span> <span data-ttu-id="36107-196">次のコマンドを入力して変更を確認し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="36107-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="36107-197">インターネット接続</span><span class="sxs-lookup"><span data-stu-id="36107-197">Internet connectivity</span></span>
<span data-ttu-id="36107-198">デバイス上のインターネット接続は、直接またはプロキシ経由で必要です。</span><span class="sxs-lookup"><span data-stu-id="36107-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="36107-199">Defender for Endpoint センサーは、1 日の平均帯域幅 5 MB を使用して Defender for Endpoint クラウド サービスと通信し、サイバー データを報告できます。</span><span class="sxs-lookup"><span data-stu-id="36107-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="36107-200">ファイルのアップロードや調査パッケージ コレクションなどの 1 回限りでのアクティビティは、この 1 日の平均帯域幅には含まれません。</span><span class="sxs-lookup"><span data-stu-id="36107-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="36107-201">追加のプロキシ構成設定の詳細については、「デバイス プロキシとインターネット接続の設定 [を構成する」を参照してください](configure-proxy-internet.md)。</span><span class="sxs-lookup"><span data-stu-id="36107-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="36107-202">デバイスをオンボードする前に、診断データ サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="36107-203">このサービスは、Windows 10 で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="36107-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="36107-204">Microsoft Defender ウイルス対策の構成要件</span><span class="sxs-lookup"><span data-stu-id="36107-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="36107-205">Defender for Endpoint エージェントは、Microsoft Defender Antivirus がファイルをスキャンし、ファイルに関する情報を提供する機能に依存します。</span><span class="sxs-lookup"><span data-stu-id="36107-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="36107-206">Microsoft Defender ウイルス対策がアクティブなマルウェア対策であるかどうかを問う場合は、Defender for Endpoint デバイスでセキュリティ インテリジェンス更新プログラムを構成します。</span><span class="sxs-lookup"><span data-stu-id="36107-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="36107-207">詳細については [、「Manage Microsoft Defender Antivirus updates and apply baselines」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="36107-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="36107-208">Microsoft Defender Antivirus が組織内のアクティブなマルウェア対策ではなく、Defender for Endpoint サービスを使用している場合、Microsoft Defender ウイルス対策はパッシブ モードになります。</span><span class="sxs-lookup"><span data-stu-id="36107-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="36107-209">組織でグループ ポリシーなどの方法で Microsoft Defender Antivirus を無効にしている場合は、オンボードされているデバイスをこのグループ ポリシーから除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="36107-210">サーバーをオンボーディングしている場合、Microsoft Defender Antivirus がサーバー上のアクティブなマルウェア対策ではない場合、Microsoft Defender Antivirus はパッシブ モードで動作するように構成するか、アンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="36107-211">構成はサーバーのバージョンに依存します。</span><span class="sxs-lookup"><span data-stu-id="36107-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="36107-212">詳細については [、「Microsoft Defender ウイルス対策の互換性」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="36107-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36107-213">通常のグループ ポリシーはタンパー プロテクションには適用されません。タンパー プロテクションがオンの場合、Microsoft Defender ウイルス対策設定の変更は無視されます。</span><span class="sxs-lookup"><span data-stu-id="36107-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="36107-214">Microsoft Defender ウイルス対策早期起動マルウェア対策 (ELAM) ドライバーが有効になっている</span><span class="sxs-lookup"><span data-stu-id="36107-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="36107-215">Microsoft Defender Antivirus をデバイスのプライマリマルウェア対策製品として実行している場合、Defender for Endpoint エージェントは正常にオンボードされます。</span><span class="sxs-lookup"><span data-stu-id="36107-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="36107-216">サードパーティのマルウェア対策クライアントを実行し、モバイル デバイス管理ソリューションまたは Microsoft Endpoint Manager (現在のブランチ) を使用する場合は、Microsoft Defender ウイルス対策 ELAM ドライバーが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="36107-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="36107-217">詳細については、「ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認 [する」を参照してください](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。</span><span class="sxs-lookup"><span data-stu-id="36107-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="36107-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="36107-218">Related topics</span></span>
- [<span data-ttu-id="36107-219">Microsoft Defender for Endpoint の展開をセットアップする</span><span class="sxs-lookup"><span data-stu-id="36107-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="36107-220">オンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="36107-220">Onboard devices</span></span>](onboard-configure.md)
