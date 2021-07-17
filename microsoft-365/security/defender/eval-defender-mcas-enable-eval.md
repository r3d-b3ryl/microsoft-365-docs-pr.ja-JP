---
title: ユーザーの評価環境を有効Microsoft Cloud App Security
description: Microsoft Defender 内の MCAS のアーキテクチャについて説明し、Office 365製品間の相互作用をMicrosoft 365 Defenderします。
keywords: Microsoft 365 Defender試し、Microsoft 365 Defender を試し、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボ、Microsoft 365 Defender パイロット、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度なハンティングを評価する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458051"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="5b388-104">ユーザーの評価環境を有効Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5b388-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="5b388-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5b388-105">**Applies to:**</span></span>

- <span data-ttu-id="5b388-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b388-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5b388-107">この記事は、ユーザーの評価環境をセットアップするプロセスの手順[2/2](eval-defender-mcas-overview.md) Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="5b388-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="5b388-108">このプロセスの詳細については、「概要」の記事を [参照してください](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5b388-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="5b388-109">この記事では、クラウド アプリのトラフィック データを収集するために、Cloud App Securityポータルにアクセスし、必要な統合を構成するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5b388-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="5b388-110">環境で使用されているクラウド アプリを検出するには、次の 1 つまたは両方を実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="5b388-111">Microsoft Defender for Endpoint と統合することで、クラウド探索を迅速に実行できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5b388-112">このネイティブ統合により、ネットワークのオンとオフを切り替えて、Windows 10トラフィックのデータ収集をすぐに開始できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="5b388-113">ネットワークに接続されているすべてのデバイスがアクセスしているすべてのクラウド アプリを検出するには、ファイアウォールや他のプロキシに Cloud App Security ログ コレクターを展開します。</span><span class="sxs-lookup"><span data-stu-id="5b388-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="5b388-114">これにより、エンドポイントからデータが収集され、分析Cloud App Security送信されます。</span><span class="sxs-lookup"><span data-stu-id="5b388-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="5b388-115">Cloud App Security機能を強化するために、一部のサード パーティ製プロキシとネイティブに統合できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="5b388-116">この記事には、両方の方法のガイダンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b388-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="5b388-117">次の手順を使用して、Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="5b388-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Microsoft Defender 評価環境で Microsoft Microsoft Cloud App Securityを有効にする手順](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="5b388-119">手順 1.ConnectポータルにCloud App Securityする</span><span class="sxs-lookup"><span data-stu-id="5b388-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="5b388-120">手順 2.エンドポイント向け Microsoft Defender との統合</span><span class="sxs-lookup"><span data-stu-id="5b388-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="5b388-121">手順 3.ファイアウォールやCloud App Securityプロキシにログ コレクターを展開する</span><span class="sxs-lookup"><span data-stu-id="5b388-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="5b388-122">手順 4.クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する</span><span class="sxs-lookup"><span data-stu-id="5b388-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="5b388-123">手順 1.</span><span class="sxs-lookup"><span data-stu-id="5b388-123">Step 1.</span></span> <span data-ttu-id="5b388-124">ConnectポータルにCloud App Securityする</span><span class="sxs-lookup"><span data-stu-id="5b388-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="5b388-125">ライセンスを確認し、Cloud App Security ポータルに接続するには[、「Quickstart: Get started with Microsoft Cloud App Security」 を参照してください](/cloud-app-security/getting-started-with-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="5b388-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="5b388-126">ポータルにすぐに接続できない場合は、ファイアウォールの許可リストに IP アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b388-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="5b388-127">詳細については[、「基本セットアップ」を参照Cloud App Security。](/cloud-app-security/general-setup)</span><span class="sxs-lookup"><span data-stu-id="5b388-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="5b388-128">それでも問題が発生する場合は、「ネットワーク要件 [」を確認してください](/cloud-app-security/network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="5b388-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="5b388-129">手順 2.</span><span class="sxs-lookup"><span data-stu-id="5b388-129">Step 2.</span></span> <span data-ttu-id="5b388-130">エンドポイント向け Microsoft Defender との統合</span><span class="sxs-lookup"><span data-stu-id="5b388-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="5b388-131">Microsoft Cloud App Security Microsoft Defender for Endpoint とネイティブに統合されます。</span><span class="sxs-lookup"><span data-stu-id="5b388-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="5b388-132">この統合により、クラウド探索のロールアウトが簡素化され、クラウド探索機能が企業ネットワークを超えて拡張され、デバイスベースの調査が可能です。</span><span class="sxs-lookup"><span data-stu-id="5b388-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="5b388-133">この統合により、IT 管理デバイスからアクセスされるクラウド アプリとサービスWindows 10されます。</span><span class="sxs-lookup"><span data-stu-id="5b388-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="5b388-134">Microsoft Defender for Endpoint を既にセットアップしている場合は、Cloud App Securityとの統合を構成Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="5b388-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="5b388-135">統合が有効になったら、ポータルに戻り、Cloud App Securityダッシュボードでリッチ データを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="5b388-136">これらのタスクを実行するには[、「Microsoft Defender for Endpoint と](/cloud-app-security/mde-integration)エンドポイントの統合」を参照Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="5b388-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="5b388-137">手順 3.</span><span class="sxs-lookup"><span data-stu-id="5b388-137">Step 3.</span></span> <span data-ttu-id="5b388-138">ファイアウォールやCloud App Securityプロキシにログ コレクターを展開する</span><span class="sxs-lookup"><span data-stu-id="5b388-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="5b388-139">ネットワークに接続されているすべてのデバイスでカバレッジを設定するには、ファイアウォールや他のプロキシに Cloud App Security ログ コレクターを展開して、エンドポイントからデータを収集し、分析のために Cloud App Security に送信します。</span><span class="sxs-lookup"><span data-stu-id="5b388-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="5b388-140">次のいずれかの Secure Web Gateway (SWG) を使用している場合は、Cloud App Securityの展開と統合が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5b388-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="5b388-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="5b388-141">Zscaler</span></span>
- <span data-ttu-id="5b388-142">iboss</span><span class="sxs-lookup"><span data-stu-id="5b388-142">iboss</span></span>
- <span data-ttu-id="5b388-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="5b388-143">Corrata</span></span>
- <span data-ttu-id="5b388-144">Menlo Security</span><span class="sxs-lookup"><span data-stu-id="5b388-144">Menlo Security</span></span>

<span data-ttu-id="5b388-145">これらのネットワーク デバイスとの統合の詳細については [、「Set up Cloud Discovery 」を参照してください](/cloud-app-security/set-up-cloud-discovery)。</span><span class="sxs-lookup"><span data-stu-id="5b388-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="5b388-146">手順 4.</span><span class="sxs-lookup"><span data-stu-id="5b388-146">Step 4.</span></span> <span data-ttu-id="5b388-147">クラウド探索ダッシュボードを表示して、組織内で使用されているアプリを確認する</span><span class="sxs-lookup"><span data-stu-id="5b388-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="5b388-148">クラウド検出ダッシュボードは、組織内でのクラウド アプリの使用方法に関する詳細な情報を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5b388-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="5b388-149">使用されているアプリの種類、開いているアラート、組織内のアプリのリスク レベルの概要を一目で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5b388-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="5b388-150">クラウド検出ダッシュボードの使用を開始するには、「検出されたアプリの操作 [」を参照してください](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="5b388-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b388-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="5b388-151">Next steps</span></span>

<span data-ttu-id="5b388-152">手順 3/ 3:[パイロット Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="5b388-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="5b388-153">[評価] の概要[に戻Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5b388-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="5b388-154">[評価とパイロット][の概要に戻Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5b388-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>