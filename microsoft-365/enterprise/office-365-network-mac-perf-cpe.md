---
title: Microsoft 365 の情報に基づいたネットワーク ルーティング
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
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
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717592"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="e8603-103">Microsoft 365 の情報に基づいたネットワーク ルーティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8603-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="e8603-104">情報に基づいたネットワーク ルーティングは、Microsoft サービス エンドポイントへのネットワーク接続を最適化および改善するために、さまざまな Microsoft 365 アプリケーションとサード パーティ製ソフトウェア定義ネットワーク (SD-WAN) ソリューションを統合する機能です。</span><span class="sxs-lookup"><span data-stu-id="e8603-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="e8603-105">最適化された SD-WAN 接続により、ユーザー エクスペリエンスとパフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e8603-106">Microsoft 365 の情報に基づいたネットワーク ルーティングは現在プレビュー状態です。</span><span class="sxs-lookup"><span data-stu-id="e8603-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="e8603-107">サポートを受けるガイダンスを含むこのプレビューの詳細については [、「Microsoft 365 の](https://go.microsoft.com/fwlink/?linkid=2151565)情報に基づいたネットワーク ルーティングパブリック プレビュー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8603-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="e8603-108">概要</span><span class="sxs-lookup"><span data-stu-id="e8603-108">Overview</span></span>

<span data-ttu-id="e8603-109">情報に基づいたネットワーク ルーティングは、Microsoft と SD-WAN ソリューション間の双方向データ共有チャネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8603-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="e8603-110">構成するオフィスの場所とインターネット回線ごとに、Microsoft は、特定のインターネット回線ごとに関連付けられたネットワーク トラフィックに対して、選択した Microsoft 365 アプリケーション エクスペリエンスの品質に関するフィードバックを SD-WAN ソリューションと定期的に共有します。</span><span class="sxs-lookup"><span data-stu-id="e8603-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="e8603-111">このフィードバックを使用して、SD-WAN ソリューションは、代替利用可能なリンクを介して Microsoft 365 アプリケーション トラフィックをルーティングすることで、スマート 回復アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8603-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="e8603-112">遅延の増加やパケット損失の増加など、特定のインターネット回線のパスにおけるサービス品質の低下は、継続的に検出することは困難です。</span><span class="sxs-lookup"><span data-stu-id="e8603-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="e8603-113">これらの低下は、Exchange Online、SharePoint、OneDrive、Microsoft Teams などのアプリケーションのユーザー エクスペリエンスに有害な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="e8603-114">一般的な現象としては、Exchange コンテンツの検索が遅い、SharePoint または OneDrive ドキュメント ライブラリを操作する場合の転送時間が多い、Microsoft Teams での通話や会議の品質の低下などです。</span><span class="sxs-lookup"><span data-stu-id="e8603-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="e8603-115">ネットワークに通知されたルーティング内のフィードバックと回復メカニズムは、このような問題をほぼリアルタイムで動的に検出し、展開された SD-WAN ソリューションに自動回復アクションを実行する通知を求める。</span><span class="sxs-lookup"><span data-stu-id="e8603-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="e8603-116">また、データ共有チャネルは、SD-WAN ソリューションからネットワーク レベルの光学データを定期的に受信するためにも使用されます。デバイスおよび接続回線に関連する構成情報や使用状況の統計情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8603-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="e8603-117">個人情報は収集または保存されません。</span><span class="sxs-lookup"><span data-stu-id="e8603-117">No personal information is collected or stored.</span></span> <span data-ttu-id="e8603-118">収集された情報はすべて、オフィスの場所と接続されたインターネット回線に集約されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="e8603-119">この情報は、Microsoft 365 サービスとアプリケーションの使用に関する報告された問題を、Microsoft のより効率的かつ効果的に解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8603-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="e8603-120">Microsoft 365 の情報に基づいたネットワーク ルーティングは、WW 商用クラウドのテナントをサポートしますが、GCC モデレート、GCC High、DoD、ドイツ、中国のクラウドはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e8603-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8603-121">要件</span><span class="sxs-lookup"><span data-stu-id="e8603-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="e8603-122">統合 SD-WAN ソリューション</span><span class="sxs-lookup"><span data-stu-id="e8603-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="e8603-123">Microsoft は、さまざまなパートナーと協力して、Microsoft 365 の情報に基づいたネットワーク ルーティングとの統合を可能にしています。</span><span class="sxs-lookup"><span data-stu-id="e8603-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="e8603-124">現在有効になっているソリューションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8603-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="e8603-125">デバイス メーカー</span><span class="sxs-lookup"><span data-stu-id="e8603-125">Device Maker</span></span> | <span data-ttu-id="e8603-126">Solution Name</span><span class="sxs-lookup"><span data-stu-id="e8603-126">Solution Name</span></span> | <span data-ttu-id="e8603-127">最小バージョン</span><span class="sxs-lookup"><span data-stu-id="e8603-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e8603-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="e8603-128">Cisco</span></span> | [<span data-ttu-id="e8603-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="e8603-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="e8603-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="e8603-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="e8603-131">ネットワーク トポロジ</span><span class="sxs-lookup"><span data-stu-id="e8603-131">Network topology</span></span>

<span data-ttu-id="e8603-132">情報に基づくネットワーク ルーティングは、現在、Microsoft にネットワーク トラフィックを送信するために使用されるパブリック IP アドレスに基づいて、特定のオフィスの場所とインターネット回線に関連付けられているトラフィックを識別します。</span><span class="sxs-lookup"><span data-stu-id="e8603-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="e8603-133">ブランチの場所にインターネットへの直接アクセスを提供するネットワーク回線が少なくとも 1 つない場合、ネットワーク情報に基づいたルーティングでは大きな価値が得されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="e8603-134">アプリケーションの使用状況</span><span class="sxs-lookup"><span data-stu-id="e8603-134">Application usage</span></span>

<span data-ttu-id="e8603-135">アプリケーション エクスペリエンス データ (ネットワーク品質メトリックスによって反映) は、特定の Microsoft クライアント アプリケーションを使用して収集されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-135">Application experience data (reflected through network quality metrics) is collected through usage of specific Microsoft client applications.</span></span> <span data-ttu-id="e8603-136">Exchange の指標は、Outlook クライアントの使用状況と一部の使用状況をOutlook Web Appします。</span><span class="sxs-lookup"><span data-stu-id="e8603-136">Exchange metrics reflect usage of the Outlook client as well as some Outlook Web App usage.</span></span> <span data-ttu-id="e8603-137">SharePoint と OneDrive のメトリックは、クライアント アプリケーションに関係なく、テナント固有の SharePoint エンドポイントの使用状況を反映します。</span><span class="sxs-lookup"><span data-stu-id="e8603-137">SharePoint and OneDrive metrics reflect usage of the tenant-specific SharePoint endpoints, regardless of client application.</span></span> <span data-ttu-id="e8603-138">Teams のメトリックは、Teams デスクトップ クライアントの使用状況を反映します。</span><span class="sxs-lookup"><span data-stu-id="e8603-138">Teams metrics reflect usage of the Teams desktop client.</span></span> <span data-ttu-id="e8603-139">ネットワーク回線の正常性を評価する場合、他のアプリケーション トラフィックは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="e8603-139">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="e8603-140">情報に基づいたネットワーク ルーティングの有効化</span><span class="sxs-lookup"><span data-stu-id="e8603-140">Enabling informed network routing</span></span>

<span data-ttu-id="e8603-141">情報に基づいたネットワーク ルーティングを有効にするには、複数の手順が必要です。その一部は、SD-WAN ソリューションの構成インターフェイス内で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-141">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="e8603-142">Microsoft 365 管理センターで構成を進む前に、SD-WAN ソリューション内でネットワークに関する情報に基づいたルーティングを有効にするプロセスを開始する方法のガイダンスについては、SD-WAN ソリューション ベンダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e8603-142">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e8603-143">Microsoft 365 管理センターで情報に基づいたネットワーク ルーティングを有効にする準備ができたら、必要なグローバル管理者のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-143">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e8603-144">選択した SD-WAN ソリューションが情報に基づいたネットワーク ルーティング データ共有チャネルにアクセスするために必要なテナント レベルのアプリケーションアクセス許可の同意を提供するには、グローバル管理者として次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-144">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="e8603-145">手順 1: SD-WAN ソリューション構成オプションを開く</span><span class="sxs-lookup"><span data-stu-id="e8603-145">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="e8603-146">Microsoft [365 管理](https://admin.microsoft.com/)センターで、左側 **のナビゲーション** ウィンドウ> [正常性とネットワーク接続] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8603-146">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="e8603-147">管理センターのこのセクションでは、組織の集約されたネットワーク接続の指標と、接続性を向上させる方法に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e8603-147">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="e8603-148">管理 [センターで使用できるこれらの機能の詳細については、「Microsoft 365 管理センターの](office-365-network-mac-perf-overview.md) ネットワーク接続 (プレビュー)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8603-148">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="e8603-149">**[SD-WAN >設定] を選択** して、情報に基づいたネットワーク ルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8603-149">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="e8603-150">[設定] に表示されるその他のオプションは、管理センターの一般的なネットワーク接続ガイダンスに適用され、情報に基づいたネットワーク ルーティングを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e8603-150">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="e8603-151">構成ウィンドウで **、[SD-WAN ソリューションの追加 (プレビュー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8603-151">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="e8603-152">手順 2: SD-WAN ソリューションとデータストレージの場所を選択する</span><span class="sxs-lookup"><span data-stu-id="e8603-152">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="e8603-153">ドロップダウン ボックスで、展開した SD-WAN ソリューションと、ネットワーク情報に基づいたルーティングに関連付けられたデータを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8603-153">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="e8603-154">詳細については [、「データストレージ」](#data-storage) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8603-154">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="e8603-155">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8603-155">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="e8603-156">手順 3: データの共有に関する用語を受け入れる</span><span class="sxs-lookup"><span data-stu-id="e8603-156">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="e8603-157">Microsoft と選択した SD-WAN ソリューション間のデータ共有に関連する指定された用語を注意深く読み、確認し、指定されたチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e8603-157">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="e8603-158">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8603-158">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="e8603-159">手順 4: SD-WAN ソリューションにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="e8603-159">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="e8603-160">この手順では、Azure Active Directory (Azure Active Directory) を使用してアクセス許可付与要求をAD。</span><span class="sxs-lookup"><span data-stu-id="e8603-160">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="e8603-161">選択した SD-WAN ソリューションに、情報に基づいたネットワーク ルーティング データ ストレージとテナントに関連付けられたサービス正常性情報へのアクセスを許可するテナント レベルのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-161">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="e8603-162">このアクションには、グローバル管理者ロールのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e8603-162">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="e8603-163">[この **アプリケーションにアクセス許可を付与する** ] リンクを選択し、Azure の要求にADします。</span><span class="sxs-lookup"><span data-stu-id="e8603-163">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="e8603-164">アクセス許可の付与が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8603-164">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="e8603-165">手順 5: 構成設定を確認する</span><span class="sxs-lookup"><span data-stu-id="e8603-165">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="e8603-166">テナントのネットワーク情報ルーティングを有効にする最後の手順は、指定した設定を表示する確認ページです。</span><span class="sxs-lookup"><span data-stu-id="e8603-166">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="e8603-167">テナントに対して、情報に基づいたネットワーク ルーティングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e8603-167">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="e8603-168">[ **完了] を** 選択し、SD-WAN ソリューション構成ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e8603-168">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="e8603-169">ネットワークに関する情報に基づいたルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="e8603-169">Configuring network informed routing</span></span>

<span data-ttu-id="e8603-170">SD-WAN ソリューション内の情報に基づいたネットワーク ルーティングの構成の多くを実行します。たとえば、通常の状況下でのトラフィックのルーティング方法や、問題が検出された場合に使用する代替パスの構成などです。</span><span class="sxs-lookup"><span data-stu-id="e8603-170">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="e8603-171">これらの構成手順の詳細については、SD-WAN ソリューション プロバイダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e8603-171">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="e8603-172">情報に基づいたネットワーク ルーティングが、これらの場所への接続を提供するネットワーク回線に関連付けられたトラフィックを適切に識別できるよう、各オフィスの場所を Microsoft 365 管理センターで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-172">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="e8603-173">Officeのネットワーク テレメトリの継続的なコレクションの一部として、場所が自動的に検出される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-173">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="e8603-174">その結果、テナントの管理センターに一部の場所が事前に設定されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-174">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="e8603-175">これらの場所が正確な場合は、必要な場所ごとに情報に基づいたネットワーク ルーティング機能を有効にし、インターネット回線とそのパブリック IP アドレスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-175">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="e8603-176">自動検出された場所が正確ではない場合、またはテナントに事前に設定されている場所がない場合は、組織の正確なトポロジを反映するために手動で場所を追加または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-176">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="e8603-177">場所の更新</span><span class="sxs-lookup"><span data-stu-id="e8603-177">Updating locations</span></span>

<span data-ttu-id="e8603-178">テナントの場所は、[場所] タブ **にあります** 。場所は、リスト内で直接編集するか、CSV ファイルを使用して更新できます。</span><span class="sxs-lookup"><span data-stu-id="e8603-178">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="e8603-179">情報に基づいたネットワーク ルーティングを有効にする各オフィスの場所が、このリストに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-179">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="e8603-180">収集されたサンプルの **[場所] リスト** の列と、その他の評価に関連する情報は、情報に基づいたネットワーク ルーティング機能には関連付けされません。</span><span class="sxs-lookup"><span data-stu-id="e8603-180">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="e8603-181">情報に基づいたネットワーク ルーティングの場所を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8603-181">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="e8603-182">[場所] **リストで** 、[クイック **アクション]** メニューから [編集] を選択して、場所の構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8603-182">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="e8603-183">[この **場所で Microsoft 365 の情報に基づいたネットワーク ルーティングを使用する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8603-183">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="e8603-184">[このオフィスの場所] セクションの [出力 IP アドレス範囲] で、インターネット接続を提供するネットワーク回線をこのオフィスの場所 **に追加** します。</span><span class="sxs-lookup"><span data-stu-id="e8603-184">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="e8603-185">各回線が、ネットワーク トラフィックを表す一意のパブリック IP アドレス サブネットに関連付けられているか確認します。</span><span class="sxs-lookup"><span data-stu-id="e8603-185">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="e8603-186">**[保存]** を選択し、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e8603-186">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="e8603-187">ネットワークに関する情報に基づいたルーティングを無効にする</span><span class="sxs-lookup"><span data-stu-id="e8603-187">Disabling network informed routing</span></span>

<span data-ttu-id="e8603-188">SD-WAN ソリューション設定をリセットすると、テナント全体で情報に基づいたネットワーク ルーティング機能が無効になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-188">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="e8603-189">これにより、Microsoft 365 内のすべてのデータ処理が停止しますが、管理センター内のネットワーク情報に基づいたルーティングも無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8603-189">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="e8603-190">手順 1: SD-WAN ソリューション構成オプションを開く</span><span class="sxs-lookup"><span data-stu-id="e8603-190">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="e8603-191">Microsoft [365 管理](https://admin.microsoft.com/) センターで、左側のナビゲーション ウィンドウ> **[** 正常性] [ネットワーク接続] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e8603-191">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="e8603-192">**[SD-WAN >設定] を選択** して、情報に基づいたネットワーク ルーティング構成ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="e8603-192">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="e8603-193">構成ウィンドウには、現在構成されている SD-WAN ソリューションの概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-193">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="e8603-194">手順 2: 構成をリセットする</span><span class="sxs-lookup"><span data-stu-id="e8603-194">Step 2: Reset your configuration</span></span>

<span data-ttu-id="e8603-195">構成ウィンドウで **、[SD-WAN ソリューション設定のリセット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e8603-195">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="e8603-196">設定がリセットされ、通知されたネットワーク ルーティングが無効になりました。</span><span class="sxs-lookup"><span data-stu-id="e8603-196">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="e8603-197">「情報に基づいたネットワーク ルーティングを有効にする」の手順に従って、いつでも再び [有効にできます](#enabling-informed-network-routing)。</span><span class="sxs-lookup"><span data-stu-id="e8603-197">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="e8603-198">データ ストレージ</span><span class="sxs-lookup"><span data-stu-id="e8603-198">Data storage</span></span>

<span data-ttu-id="e8603-199">Microsoft と SD-WAN ソリューション プロバイダーの間で交換されるデータは、ネットワーク情報に基づいたルーティングの初期有効化時に選択されたデータストレージの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-199">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="e8603-200">データ格納場所オプションは、データが格納されている Microsoft Azure 地域を含む地理的領域を表します。</span><span class="sxs-lookup"><span data-stu-id="e8603-200">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="e8603-201">プレビュー フェーズでは、使用可能なデータストレージの場所は北米 **のみです**。</span><span class="sxs-lookup"><span data-stu-id="e8603-201">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="e8603-202">情報に基づいたネットワーク ルーティングの一般的な可用性の前に、追加のデータストレージの場所が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e8603-202">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="e8603-203">データは、この場所に最大 30 日間保持されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-203">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="e8603-204">無効にすると、残りのすべてのデータは、この 30 日間の保持ウィンドウ内で削除されます。</span><span class="sxs-lookup"><span data-stu-id="e8603-204">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8603-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8603-205">Related topics</span></span>

[<span data-ttu-id="e8603-206">Microsoft 365 管理センターのネットワーク接続 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8603-206">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="e8603-207">Microsoft 365 Network Connectivity Location Services (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8603-207">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
