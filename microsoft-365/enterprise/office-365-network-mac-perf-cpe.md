---
title: Microsoft 365 の情報に基づいたネットワーク ルーティング
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 の情報に基づいたネットワーク ルーティング
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749553"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="21639-103">Microsoft 365 の情報に基づいたネットワーク ルーティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="21639-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="21639-104">情報に基づいたネットワーク ルーティングは、Microsoft サービス エンドポイントへのネットワーク接続を最適化および改善するために、さまざまな Microsoft 365 アプリケーションをサード パーティ製ソフトウェア定義ネットワーク (SD-WAN) ソリューションと統合する機能です。</span><span class="sxs-lookup"><span data-stu-id="21639-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="21639-105">SD-WAN 接続を最適化すると、ユーザー エクスペリエンスとパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21639-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="21639-106">Microsoft 365 の情報に基づいたネットワーク ルーティングは、現在プレビュー状態です。</span><span class="sxs-lookup"><span data-stu-id="21639-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="21639-107">サポートを受けるガイダンスなど、このプレビューの詳細については [、Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2151565)の情報に基づいたネットワーク ルーティングパブリック プレビューを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21639-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="21639-108">概要</span><span class="sxs-lookup"><span data-stu-id="21639-108">Overview</span></span>

<span data-ttu-id="21639-109">情報に基づいたネットワーク ルーティングは、Microsoft と SD-WAN ソリューション間の双方向データ共有チャネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="21639-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="21639-110">構成するオフィスの場所とインターネット回線ごとに、Microsoft は、特定のインターネット回線ごとに関連付けられたネットワーク トラフィックについて、選択した Microsoft 365 アプリケーション エクスペリエンスの品質に関するフィードバックを SD-WAN ソリューションと定期的に共有します。</span><span class="sxs-lookup"><span data-stu-id="21639-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="21639-111">このフィードバックを使用すると、SD-WAN ソリューションは、代替の利用可能なリンクを介して Microsoft 365 アプリケーション トラフィックをルーティングすることで、スマート回復アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="21639-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="21639-112">遅延の増加やパケット損失の大きなど、特定のインターネット回線のパスでのサービス品質の低下は、継続的に検出するのが困難です。</span><span class="sxs-lookup"><span data-stu-id="21639-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="21639-113">これらの低下は、Exchange Online、SharePoint、OneDrive、Microsoft Teams などのアプリケーションのユーザー エクスペリエンスに有害な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21639-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="21639-114">一般的な現象には、Exchange コンテンツの検索が遅い、SharePoint または OneDrive ドキュメント ライブラリを操作する場合の転送時間の短縮、Microsoft Teams での低品質な通話や会議の品質などです。</span><span class="sxs-lookup"><span data-stu-id="21639-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="21639-115">ネットワークに通知されたルーティング内のフィードバックと回復メカニズムは、ほぼリアルタイムでこのような問題を動的に検出し、展開された SD-WAN ソリューションに自動回復アクションを実行する通知を行います。</span><span class="sxs-lookup"><span data-stu-id="21639-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="21639-116">また、データ共有チャネルは、SD-WAN ソリューションからネットワーク レベルの光学データを定期的に受信するためにも使用されます。このソリューションには、デバイスと接続回線に関連する構成情報や使用状況統計が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21639-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="21639-117">個人情報は収集または保存されません。</span><span class="sxs-lookup"><span data-stu-id="21639-117">No personal information is collected or stored.</span></span> <span data-ttu-id="21639-118">収集された情報はすべて、オフィスの場所と接続されたインターネット回線に集約されます。</span><span class="sxs-lookup"><span data-stu-id="21639-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="21639-119">この情報は、Microsoft 365 サービスとアプリケーションの使用に関して報告された問題を Microsoft が効率的かつ効果的に解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21639-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="21639-120">Microsoft 365 の情報に基づいたネットワーク ルーティングは、WW 商用クラウドのテナントをサポートしますが、GCC Moderate、GCC High、DoD、ドイツ、中国のクラウドはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="21639-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="21639-121">要件</span><span class="sxs-lookup"><span data-stu-id="21639-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="21639-122">統合 SD-WAN ソリューション</span><span class="sxs-lookup"><span data-stu-id="21639-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="21639-123">Microsoft は、さまざまなパートナーと協力して、Microsoft 365 の情報に基づいたネットワーク ルーティングとの統合を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="21639-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="21639-124">現在有効になっているソリューションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21639-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="21639-125">Device Maker</span><span class="sxs-lookup"><span data-stu-id="21639-125">Device Maker</span></span> | <span data-ttu-id="21639-126">Solution Name</span><span class="sxs-lookup"><span data-stu-id="21639-126">Solution Name</span></span> | <span data-ttu-id="21639-127">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="21639-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="21639-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="21639-128">Cisco</span></span> | [<span data-ttu-id="21639-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="21639-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="21639-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="21639-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="21639-131">ネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="21639-131">Network topology</span></span>

<span data-ttu-id="21639-132">現在、情報に基づくネットワーク ルーティングは、ネットワーク トラフィックを Microsoft に送信するために使用されるパブリック IP アドレスに基づいて、特定のオフィスの場所とインターネット回線に関連付けられているトラフィックを識別します。</span><span class="sxs-lookup"><span data-stu-id="21639-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="21639-133">ブランチの場所に直接インターネット アクセスを提供するネットワーク回線が少なくとも 1 つない場合、ネットワーク情報に基づいたルーティングでは重要な値が提供されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21639-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="21639-134">アプリケーションの使用状況</span><span class="sxs-lookup"><span data-stu-id="21639-134">Application usage</span></span>

<span data-ttu-id="21639-135">(ネットワーク品質メトリックによって反映される) アプリケーション エクスペリエンス データは、Windows、Teams、SharePoint、OneDrive を実行しているデバイスで Microsoft Outlook を使用して収集されます。</span><span class="sxs-lookup"><span data-stu-id="21639-135">Application experience data (reflected through network quality metrics) is collected through usage of Microsoft Outlook on devices running Windows, Teams, SharePoint, and OneDrive.</span></span> <span data-ttu-id="21639-136">ネットワーク回線の正常性を評価する際には、他のアプリケーション トラフィックは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="21639-136">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="21639-137">情報に基づいたネットワーク ルーティングの有効化</span><span class="sxs-lookup"><span data-stu-id="21639-137">Enabling informed network routing</span></span>

<span data-ttu-id="21639-138">情報に基づいたネットワーク ルーティングを有効にする場合は複数の手順が必要ですが、その一部は SD-WAN ソリューションの構成インターフェイス内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-138">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="21639-139">Microsoft 365 管理センターで構成に進む前に、SD-WAN ソリューション内でネットワーク情報に基づいたルーティングを有効にするプロセスを開始する方法のガイダンスについては、SD-WAN ソリューション ベンダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="21639-139">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="21639-140">Microsoft 365 管理センターで情報に基づいたネットワーク ルーティングを有効にする準備ができたら、必要なグローバル管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-140">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="21639-141">選択した SD-WAN ソリューションが、情報に基づいたネットワーク ルーティング データ共有チャネルにアクセスするために必要なテナント レベルアプリケーションのアクセス許可の同意を提供するには、グローバル管理者として次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-141">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="21639-142">手順 1: SD-WAN ソリューション構成オプションを開く</span><span class="sxs-lookup"><span data-stu-id="21639-142">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="21639-143">Microsoft [365](https://admin.microsoft.com/)管理センターで、左側のナビゲーション ウィンドウ>の [正常性とネットワーク接続] を選択します。</span><span class="sxs-lookup"><span data-stu-id="21639-143">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="21639-144">管理センターのこのセクションでは、組織のネットワーク接続に関する集計された指標と、接続性を向上させる方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="21639-144">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="21639-145">管理 [センターで利用可能なこれらの機能の詳細については、Microsoft 365](office-365-network-mac-perf-overview.md) 管理センター (プレビュー) のネットワーク接続を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21639-145">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="21639-146">**SD-WAN >設定] を選択して**、情報に基づいたネットワーク ルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="21639-146">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="21639-147">[設定] に表示されるその他のオプションは、管理センターの一般的なネットワーク接続ガイダンスに適用され、情報に基づいたネットワーク ルーティングを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="21639-147">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="21639-148">構成ウィンドウで **、SD-WAN ソリューションの追加 (プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="21639-148">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="21639-149">手順 2: SD-WAN ソリューションとデータストレージの場所を選択する</span><span class="sxs-lookup"><span data-stu-id="21639-149">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="21639-150">ドロップダウン ボックスで、展開した SD-WAN ソリューションと、ネットワーク情報に基づいたルーティングに関連付けられたデータを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="21639-150">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="21639-151">詳細については [、データ ストレージの](#data-storage) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21639-151">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="21639-152">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="21639-152">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="21639-153">手順 3: データ共有の条件を承諾する</span><span class="sxs-lookup"><span data-stu-id="21639-153">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="21639-154">Microsoft と選択した SD-WAN ソリューションとの間でデータを共有する場合に関連する用語を注意深く読んで確認し、示されているチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="21639-154">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="21639-155">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="21639-155">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="21639-156">手順 4: SD-WAN ソリューションにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="21639-156">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="21639-157">この手順では、Azure Active Directory (Azure AD) を使用してアクセス許可付与要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="21639-157">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="21639-158">選択した SD-WAN ソリューションが、情報に基づいたネットワーク ルーティング データ ストレージおよびテナントに関連付けられているサービス正常性情報にアクセスできるテナント レベルのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-158">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="21639-159">このアクションには、グローバル管理者ロールのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="21639-159">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="21639-160">[このアプリケーション **へのアクセス許可を付与する** ] リンクを選択し、Azure の要求ADします。</span><span class="sxs-lookup"><span data-stu-id="21639-160">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="21639-161">アクセス許可の付与が完了したら、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="21639-161">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="21639-162">手順 5: 構成設定を確認する</span><span class="sxs-lookup"><span data-stu-id="21639-162">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="21639-163">テナントのネットワーク情報に基づいたルーティングを有効にする最後の手順は、指定した設定を表示する確認ページです。</span><span class="sxs-lookup"><span data-stu-id="21639-163">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="21639-164">情報に基づいたネットワーク ルーティングがテナントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="21639-164">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="21639-165">[ **完了] を** 選択し、SD-WAN ソリューション構成ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="21639-165">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="21639-166">ネットワーク情報に基づいたルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="21639-166">Configuring network informed routing</span></span>

<span data-ttu-id="21639-167">SD-WAN ソリューション内で情報に基づいたネットワーク ルーティングの構成の多くを実行します。たとえば、通常の状況でトラフィックをルーティングする方法や、問題が検出された場合に使用する代替パスを構成します。</span><span class="sxs-lookup"><span data-stu-id="21639-167">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="21639-168">これらの構成手順の詳細については、SD-WAN ソリューション プロバイダーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21639-168">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="21639-169">情報に基づいたネットワーク ルーティングが、これらの場所への接続を提供するネットワーク回線に関連付けられているトラフィックを適切に識別できるよう、各オフィスの場所を Microsoft 365 管理センターで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-169">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="21639-170">Officeは、Microsoft の継続的なネットワーク 利用統計情報の収集の一環として自動検出される場合があります。</span><span class="sxs-lookup"><span data-stu-id="21639-170">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="21639-171">その結果、テナントの管理センターに一部の場所が事前に入力されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21639-171">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="21639-172">これらの場所が正確な場合は、必要な場所ごとに情報に基づいたネットワーク ルーティング機能を有効にし、インターネット回線とそのパブリック IP アドレスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-172">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="21639-173">自動検出された場所が正確ではない場合、またはテナントに事前に入力されている場所がない場合は、組織の正確なトポロジを反映するために場所を手動で追加または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-173">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="21639-174">場所の更新</span><span class="sxs-lookup"><span data-stu-id="21639-174">Updating locations</span></span>

<span data-ttu-id="21639-175">テナントの場所は、[場所] タブ **にあります** 。場所は、リスト内で直接編集するか、CSV ファイルを使用して更新できます。</span><span class="sxs-lookup"><span data-stu-id="21639-175">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="21639-176">情報に基づいたネットワーク ルーティングを有効にする各オフィスの場所が、この一覧に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-176">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="21639-177">収集されたサンプルの **場所リスト内** の列、および他の評価に関連する情報は、情報に基づいたネットワーク ルーティング機能には関連付けされません。</span><span class="sxs-lookup"><span data-stu-id="21639-177">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="21639-178">情報に基づいたネットワーク ルーティングの場所の有効化</span><span class="sxs-lookup"><span data-stu-id="21639-178">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="21639-179">[場所 **] ボックスの** 一覧でクイック アクション **メニューから** [編集] を選択し、場所の構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="21639-179">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="21639-180">[ **この場所で Microsoft 365 の情報に基づいたネットワーク ルーティングを使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="21639-180">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="21639-181">このオフィスの場所の [出力 IP アドレス] の範囲に、インターネット接続を提供しているすべてのネットワーク回線 **を追加** します。</span><span class="sxs-lookup"><span data-stu-id="21639-181">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="21639-182">各回線が、ネットワーク トラフィックを表す一意のパブリック IP アドレス サブネットに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-182">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="21639-183">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="21639-183">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="21639-184">ネットワーク情報に基づいたルーティングを無効にする</span><span class="sxs-lookup"><span data-stu-id="21639-184">Disabling network informed routing</span></span>

<span data-ttu-id="21639-185">SD-WAN ソリューション設定をリセットすると、情報に基づいたネットワーク ルーティング機能がテナント全体で無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="21639-185">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="21639-186">これにより、Microsoft 365 内のすべてのデータ処理が停止しますが、管理センター内のネットワーク情報に基づいたルーティングも無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21639-186">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="21639-187">手順 1: SD-WAN ソリューション構成オプションを開く</span><span class="sxs-lookup"><span data-stu-id="21639-187">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="21639-188">Microsoft [365](https://admin.microsoft.com/)管理センターで、左側>ウィンドウで [正常性とネットワーク接続] を選択します。</span><span class="sxs-lookup"><span data-stu-id="21639-188">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="21639-189">**SD-WAN >設定] を選択して**、情報に基づいたネットワーク ルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="21639-189">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="21639-190">構成ウィンドウには、現在構成されている SD-WAN ソリューションの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21639-190">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="21639-191">手順 2: 構成をリセットする</span><span class="sxs-lookup"><span data-stu-id="21639-191">Step 2: Reset your configuration</span></span>

<span data-ttu-id="21639-192">構成ウィンドウで **、[SD-WAN ソリューション設定のリセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="21639-192">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="21639-193">設定がリセットされ、通知されたネットワーク ルーティングが無効になりました。</span><span class="sxs-lookup"><span data-stu-id="21639-193">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="21639-194">情報に基づいたネットワーク ルーティングを有効にする手順に従って、いつでも再び [有効にできます](#enabling-informed-network-routing)。</span><span class="sxs-lookup"><span data-stu-id="21639-194">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="21639-195">データ ストレージ</span><span class="sxs-lookup"><span data-stu-id="21639-195">Data storage</span></span>

<span data-ttu-id="21639-196">Microsoft と SD-WAN ソリューション プロバイダー間で交換されるデータは、ネットワーク情報ルーティングの初期有効化時に選択されたデータ格納場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="21639-196">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="21639-197">データ ストレージの場所のオプションは、データが保存されている Microsoft Azure 地域を含む地理的な領域を表します。</span><span class="sxs-lookup"><span data-stu-id="21639-197">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="21639-198">プレビュー フェーズでは、使用可能なデータストレージの場所は **北米のみです**。</span><span class="sxs-lookup"><span data-stu-id="21639-198">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="21639-199">情報に基づいたネットワーク ルーティングが一般提供される前に、追加のデータストレージの場所が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="21639-199">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="21639-200">データは、この場所に最大 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="21639-200">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="21639-201">無効にした場合、残りのすべてのデータは、この 30 日間の保持期間内に削除されます。</span><span class="sxs-lookup"><span data-stu-id="21639-201">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="21639-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="21639-202">Related topics</span></span>

[<span data-ttu-id="21639-203">Microsoft 365 管理センターでのネットワーク接続 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="21639-203">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="21639-204">Microsoft 365 Network Connectivity Location Services (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="21639-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
