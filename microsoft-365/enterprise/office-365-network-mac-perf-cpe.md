---
title: Microsoft 365 情報によるネットワークルーティング
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 情報によるネットワークルーティング
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611438"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="254d0-103">Microsoft 365 の情報ネットワークルーティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="254d0-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="254d0-104">情報としてのネットワークルーティングは、Microsoft サービスエンドポイントへのネットワーク接続を最適化および改善するために、さまざまな Microsoft 365 アプリケーションをサードパーティ製のソフトウェア定義ネットワーク (SD-WAN) ソリューションと統合する機能です。</span><span class="sxs-lookup"><span data-stu-id="254d0-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="254d0-105">最適化された SD-WAN 接続により、ユーザーエクスペリエンスとパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="254d0-106">Microsoft 365 では、現在、ネットワークルーティングがプレビュー状態になっています。</span><span class="sxs-lookup"><span data-stu-id="254d0-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="254d0-107">このプレビューの詳細については、「 [Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2151565)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254d0-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="254d0-108">概要</span><span class="sxs-lookup"><span data-stu-id="254d0-108">Overview</span></span>

<span data-ttu-id="254d0-109">得られたネットワークルーティングは、Microsoft と SD との間で双方向のデータ共有チャネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="254d0-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="254d0-110">構成するすべてのオフィスの場所とインターネット回線に対して、Microsoft は、特定のインターネット回路に関連付けられているネットワークトラフィック用に選択した Microsoft 365 アプリケーションエクスペリエンスの品質について、Microsoft が SD ソリューションとのフィードバックを定期的に共有します。</span><span class="sxs-lookup"><span data-stu-id="254d0-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="254d0-111">このフィードバックを使用すると、SD-WAN ソリューションは、Microsoft 365 アプリケーショントラフィックを別の利用可能なリンクからルーティングすることによって、smart 回復アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="254d0-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="254d0-112">遅延が増加したり、パケット損失が発生したりするなど、特定のインターネット回路のパスにおけるサービスの品質 degradations は、継続的に検出するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="254d0-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="254d0-113">これらの degradations は、Exchange Online、SharePoint、OneDrive、Microsoft Teams などのアプリケーションのユーザーエクスペリエンスに悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="254d0-114">一般的な現象としては、Exchange コンテンツの検索が遅くなる、SharePoint または OneDrive ドキュメントライブラリと対話する際の転送時間が長くなる、Microsoft Teams での通話や会議の品質が低下する、などがあります。</span><span class="sxs-lookup"><span data-stu-id="254d0-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="254d0-115">ネットワーク内のフィードバックと回復のメカニズムは、このような問題をほぼリアルタイムで動的に検出し、展開された SD ソリューションに自動の回復操作を実行するように通知します。</span><span class="sxs-lookup"><span data-stu-id="254d0-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="254d0-116">また、データ共有チャネルは、デバイスおよび接続された回路に関連する構成情報や使用状況の統計を含む、SD-WAN ソリューションからネットワークレベルの光学データを定期的に受信するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="254d0-117">個人情報は収集または保存されません。</span><span class="sxs-lookup"><span data-stu-id="254d0-117">No personal information is collected or stored.</span></span> <span data-ttu-id="254d0-118">収集されたすべての情報は、オフィスの場所と接続されたインターネット回線に集約されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="254d0-119">この情報は、microsoft 365 のサービスとアプリケーションを使用して、報告された問題をより効率的かつ効果的に解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="254d0-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="254d0-120">Microsoft 365 が示しているネットワークルーティングでは、WW 商用クラウドのテナントがサポートされていますが、GCC の中程度、GCC High、DoD、ドイツ、中国の各クラウドはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="254d0-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="254d0-121">要件</span><span class="sxs-lookup"><span data-stu-id="254d0-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="254d0-122">統合 SD-WAN ソリューション</span><span class="sxs-lookup"><span data-stu-id="254d0-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="254d0-123">Microsoft はさまざまなパートナーと協力して、Microsoft 365 の情報によるネットワークルーティングとの統合を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="254d0-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="254d0-124">現在有効になっているソリューションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="254d0-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="254d0-125">デバイスメーカー</span><span class="sxs-lookup"><span data-stu-id="254d0-125">Device Maker</span></span> | <span data-ttu-id="254d0-126">Solution Name</span><span class="sxs-lookup"><span data-stu-id="254d0-126">Solution Name</span></span> | <span data-ttu-id="254d0-127">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="254d0-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="254d0-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="254d0-128">Cisco</span></span> | [<span data-ttu-id="254d0-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="254d0-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="254d0-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="254d0-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="254d0-131">ネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="254d0-131">Network topology</span></span>

<span data-ttu-id="254d0-132">通知されたネットワークルーティングでは、Microsoft にネットワークトラフィックを送信するために使用されるパブリック IP アドレスに基づいて、特定のオフィスの場所とインターネットサーキットに関連付けられているトラフィックを特定します。</span><span class="sxs-lookup"><span data-stu-id="254d0-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="254d0-133">ブランチオフィスで直接インターネットアクセスを提供するネットワーク回線が少なくとも1つ存在しない場合は、ネットワークによってルーティングされたルーティングでは重要な価値が得られないことがあります。</span><span class="sxs-lookup"><span data-stu-id="254d0-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="254d0-134">アプリケーションの使用状況</span><span class="sxs-lookup"><span data-stu-id="254d0-134">Application usage</span></span>

<span data-ttu-id="254d0-135">アプリケーション環境のデータ (ネットワーク品質指標によって反映) は、Windows、Teams、SharePoint、OneDrive を実行しているデバイス上の Microsoft Outlook の使用によって収集されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-135">Application experience data (reflected through network quality metrics) is collected through usage of Microsoft Outlook on devices running Windows, Teams, SharePoint, and OneDrive.</span></span> <span data-ttu-id="254d0-136">ネットワーク回線の状態を評価するときは、他のアプリケーショントラフィックは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="254d0-136">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="254d0-137">情報に基づくネットワークルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="254d0-137">Enabling informed network routing</span></span>

<span data-ttu-id="254d0-138">情報に基づいたネットワークルーティングを有効にするには、複数の手順が必要になります。一部の手順は、SD ソリューションの構成インターフェイス内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-138">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="254d0-139">Sd-wan ソリューション内でネットワーク情報によるルーティングを有効にするプロセスを開始してから、Microsoft 365 管理センターでの構成に進む前に、SD-WAN ソリューションベンダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="254d0-139">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="254d0-140">Microsoft 365 管理センターで通知されたネットワークルーティングを有効にする準備が整ったら、必要なグローバル管理者アクセス許可を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="254d0-140">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="254d0-141">必要なテナントレベルのアプリケーションへのアクセス許可を選択した SD-WAN ソリューションに付与して、情報に基づいたネットワークルーティングデータ共有チャネルにアクセスするためには、全体管理者として次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-141">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="254d0-142">手順 1: SD を開く-WAN ソリューション構成オプション</span><span class="sxs-lookup"><span data-stu-id="254d0-142">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="254d0-143">[Microsoft 365 管理センター](https://admin.microsoft.com/)で、左側のナビゲーションウィンドウで [ **Health > ネットワーク接続**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-143">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="254d0-144">管理センターのこのセクションでは、組織のためのネットワーク接続性の集約指標と、接続を向上させる方法についてのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="254d0-144">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="254d0-145">管理センターで利用できるこれらの機能の詳細については [、「Microsoft 365 管理センター (プレビュー)」の「ネットワーク接続](office-365-network-mac-perf-overview.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254d0-145">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="254d0-146">[ **設定 > SD** ] を選択して、情報が表示されたネットワークルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="254d0-146">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="254d0-147">[ **設定** ] の下に表示されるその他のオプションは、管理センターの一般的なネットワーク接続のガイダンスに適用され、情報に基づいたネットワークルーティングを有効にするために必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="254d0-147">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="254d0-148">[構成] ウィンドウで、[ **SD を追加する-WAN ソリューション (プレビュー)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-148">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="254d0-149">手順 2: SD を選択する-WAN ソリューションとデータストレージの場所</span><span class="sxs-lookup"><span data-stu-id="254d0-149">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="254d0-150">ドロップダウンボックスで、展開した SD ソリューションと、ネットワークによって通知されたルーティングに関連付けられたデータを格納する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-150">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="254d0-151">詳細については、「 [データストレージ](#data-storage) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="254d0-151">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="254d0-152">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-152">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="254d0-153">手順 3: データ共有の条件に同意する</span><span class="sxs-lookup"><span data-stu-id="254d0-153">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="254d0-154">Microsoft と選択された SD-WAN ソリューションとの間でデータを共有するために関連付けられている用語を慎重に確認して確認し、次に [指定] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="254d0-154">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="254d0-155">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-155">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="254d0-156">手順 4: SD-WAN ソリューションへのアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="254d0-156">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="254d0-157">この手順では、Azure Active Directory (Azure AD) を使用したアクセス許可の付与要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="254d0-157">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="254d0-158">通知されたネットワークルーティングデータストレージ、およびテナントに関連付けられているサービス正常性情報へのアクセスを、選択した SD-WAN ソリューションに許可するテナントレベルのアクセス許可を付与するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-158">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="254d0-159">このアクションには、全体管理者役割のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="254d0-159">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="254d0-160">[ **このアプリケーションへのアクセス許可を付与する** ] リンクを選択して、Azure AD 要求に従います。</span><span class="sxs-lookup"><span data-stu-id="254d0-160">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="254d0-161">アクセス許可の付与が完了したら、[ **次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-161">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="254d0-162">手順 5: 構成設定を確認する</span><span class="sxs-lookup"><span data-stu-id="254d0-162">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="254d0-163">テナントのネットワーク情報のルーティングを有効にする最後の手順は、提供された設定を表示する確認ページです。</span><span class="sxs-lookup"><span data-stu-id="254d0-163">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="254d0-164">これで、テナントのネットワークルーティングが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="254d0-164">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="254d0-165">[ **完了** ] を選択して、[SD-WAN ソリューション構成] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="254d0-165">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="254d0-166">ネットワークの情報に基づいたルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="254d0-166">Configuring network informed routing</span></span>

<span data-ttu-id="254d0-167">通常の状況でのトラフィックのルーティング方法や、問題が検出された場合に使用する代替パスなど、SD-WAN ソリューション内で情報を得たネットワークルーティングに関する構成の大部分が実行されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-167">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="254d0-168">これらの構成手順の詳細については、「SD-WAN ソリューションプロバイダー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="254d0-168">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="254d0-169">各オフィスの場所は、Microsoft 365 管理センターで構成する必要があります。これにより、ネットワークルーティングで、これらの場所への接続を提供するネットワーク回線に関連付けられたトラフィックを正しく識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="254d0-169">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="254d0-170">Office の場所は、Microsoft のネットワークテレメトリの継続的なコレクションの一部として自動検出される場合があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-170">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="254d0-171">その結果、テナントの管理センターにいくつかの場所が事前に設定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-171">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="254d0-172">これらの場所が正確な場合は、必要な場所ごとに、情報に基づいたネットワークルーティング機能を有効にし、インターネット回線とそのパブリック IP アドレスを構成するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="254d0-172">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="254d0-173">自動検出された場所が正確でない場合、またはテナントに事前に設定された場所が存在しない場合は、組織の正確なトポロジを反映するために手動で場所を追加または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-173">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="254d0-174">場所を更新する</span><span class="sxs-lookup"><span data-stu-id="254d0-174">Updating locations</span></span>

<span data-ttu-id="254d0-175">テナントの場所は、[ **場所** ] タブにあります。場所は、リスト内で直接編集することも、CSV ファイルを使用して更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="254d0-175">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="254d0-176">情報が記載されたネットワークルーティングを有効にする各オフィスの場所が、この一覧に含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="254d0-176">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="254d0-177">収集されたサンプルおよびその他の評価関連の情報の **場所** の一覧にある列は、情報を得たネットワークルーティング機能に関連していません。</span><span class="sxs-lookup"><span data-stu-id="254d0-177">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="254d0-178">情報があるネットワークルーティングの場所を有効にする</span><span class="sxs-lookup"><span data-stu-id="254d0-178">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="254d0-179">[ **場所** ] の一覧で、[クイック操作] メニューから [ **編集** ] を選択して、[場所の構成] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="254d0-179">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="254d0-180">[ **Microsoft 365 により報告されたネットワークルーティングをこの場所で使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-180">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="254d0-181">[ **このオフィスの場所にある出口 IP アドレスの範囲** ] セクションで、このオフィスの場所へのインターネット接続を提供するすべてのネットワーク回線を追加します。</span><span class="sxs-lookup"><span data-stu-id="254d0-181">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="254d0-182">各回線が、ネットワークトラフィックを表す一意のパブリック IP アドレスサブネットに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="254d0-182">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="254d0-183">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="254d0-183">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="254d0-184">ネットワーク情報のルーティングを無効にする</span><span class="sxs-lookup"><span data-stu-id="254d0-184">Disabling network informed routing</span></span>

<span data-ttu-id="254d0-185">情報が含まれるネットワークルーティング機能は、SD をリセットすることで、テナント全体に対して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="254d0-185">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="254d0-186">これにより、Microsoft 365 内のデータのすべての処理が停止されますが、管理センター内のネットワーク情報によるルーティングも無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="254d0-186">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="254d0-187">手順 1: SD を開く-WAN ソリューション構成オプション</span><span class="sxs-lookup"><span data-stu-id="254d0-187">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="254d0-188">[Microsoft 365 管理センター](https://admin.microsoft.com/)で、左側のナビゲーションウィンドウで [ **Health > ネットワーク接続**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-188">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="254d0-189">[ **設定 > SD** ] を選択して、情報が表示されたネットワークルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="254d0-189">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="254d0-190">構成ウィンドウには、現在構成されている SD-WAN ソリューションの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-190">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="254d0-191">手順 2: 構成をリセットする</span><span class="sxs-lookup"><span data-stu-id="254d0-191">Step 2: Reset your configuration</span></span>

<span data-ttu-id="254d0-192">[構成] ウィンドウで、[ **SD をリセットする-WAN ソリューション設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="254d0-192">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="254d0-193">設定がリセットされ、ネットワークのルーティングが無効になったことが通知されました。</span><span class="sxs-lookup"><span data-stu-id="254d0-193">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="254d0-194">情報が表示された [ネットワークルーティングを有効](#enabling-informed-network-routing)にする手順に従って、いつでも再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="254d0-194">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="254d0-195">データ ストレージ</span><span class="sxs-lookup"><span data-stu-id="254d0-195">Data storage</span></span>

<span data-ttu-id="254d0-196">Microsoft と SD-WAN ソリューションプロバイダーとの間で交換されるデータは、ネットワーク通知されたルーティングを最初に有効にしたときに選択したデータストレージの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-196">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="254d0-197">データストレージの場所のオプションは、データが格納されている Microsoft Azure 地域を含む地理的領域を表します。</span><span class="sxs-lookup"><span data-stu-id="254d0-197">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="254d0-198">プレビューフェーズでは、使用可能なデータストレージの場所は **北アメリカ** のみです。</span><span class="sxs-lookup"><span data-stu-id="254d0-198">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="254d0-199">情報を入手したネットワークルーティングを使用できるようになる前に、追加のデータストレージの場所が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="254d0-199">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="254d0-200">データは、最大30日間、この場所に保持されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-200">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="254d0-201">無効にすると、残りのすべてのデータは、この30日の保持期間内で削除されます。</span><span class="sxs-lookup"><span data-stu-id="254d0-201">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="254d0-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="254d0-202">Related topics</span></span>

[<span data-ttu-id="254d0-203">Microsoft 365 管理センターでのネットワーク接続 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="254d0-203">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="254d0-204">Microsoft 365 ネットワーク接続ロケーションサービス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="254d0-204">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
