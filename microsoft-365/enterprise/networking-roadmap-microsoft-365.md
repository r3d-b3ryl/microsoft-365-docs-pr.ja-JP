---
title: Microsoft 365 のネットワークロードマップ
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 ネットワークを実装するためのロードマップ。
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923554"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="fa505-103">Microsoft 365 のネットワークロードマップ</span><span class="sxs-lookup"><span data-stu-id="fa505-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="fa505-104">Microsoft 365 for enterprise には、コラボレーションと生産性のクラウド サービス、Microsoft Intune、Microsoft Azure の多くの ID およびセキュリティ サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa505-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="fa505-105">これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。</span><span class="sxs-lookup"><span data-stu-id="fa505-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="fa505-106">これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="fa505-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="fa505-107">Microsoft 365 オンボーディングの重要な部分は、ネットワークとインターネット接続が最適化されたアクセス用にセットアップされる点です。</span><span class="sxs-lookup"><span data-stu-id="fa505-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="fa505-108">グローバルに分散された Software-as-a-Service (SaaS) クラウドにアクセスするためのオンプレミス ネットワークの構成は、オンプレミスデータセンターへのトラフィックと中央インターネット接続用に最適化された従来のネットワークとは異なります。</span><span class="sxs-lookup"><span data-stu-id="fa505-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="fa505-109">以下の記事を活用して主な違いを理解し、エッジ デバイス、クライアント コンピューター、オンプレミス ネットワークを変更して、オンプレミス ユーザーの最高のパフォーマンスを引き出します。</span><span class="sxs-lookup"><span data-stu-id="fa505-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="fa505-110">計画</span><span class="sxs-lookup"><span data-stu-id="fa505-110">Plan</span></span>

<span data-ttu-id="fa505-111">ネットワーク実装の計画フェーズでは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="fa505-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="fa505-112">Microsoft 365 ネットワークのしくみを理解する</span><span class="sxs-lookup"><span data-stu-id="fa505-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="fa505-113">現在のネットワーク接続を評価する</span><span class="sxs-lookup"><span data-stu-id="fa505-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="fa505-114">ExpressRoute が組織に適切かどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="fa505-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="fa505-115">ネットワーク デバイスの計画</span><span class="sxs-lookup"><span data-stu-id="fa505-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="fa505-116">移行用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="fa505-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="fa505-117">展開</span><span class="sxs-lookup"><span data-stu-id="fa505-117">Deploy</span></span>

<span data-ttu-id="fa505-118">ネットワーク実装の展開フェーズでは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa505-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="fa505-119">エンタープライズ ネットワークが Microsoft 365 接続用に最適化されていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="fa505-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="fa505-120">組織の DNS ドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="fa505-120">Add the DNS domains for your organization</span></span>](../admin/setup/add-domain.md)
- [<span data-ttu-id="fa505-121">Microsoft 365 エンドポイントへの接続を最適化する</span><span class="sxs-lookup"><span data-stu-id="fa505-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="fa505-122">リモート ワーカーの接続を最適化する</span><span class="sxs-lookup"><span data-stu-id="fa505-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="fa505-123">必要に応じて [、ExpressRoute を構成する](azure-expressroute.md)</span><span class="sxs-lookup"><span data-stu-id="fa505-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="fa505-124">管理</span><span class="sxs-lookup"><span data-stu-id="fa505-124">Manage</span></span>

<span data-ttu-id="fa505-125">ネットワーク実装の管理フェーズでは、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="fa505-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="fa505-126">ネットワーク デバイスが最新のエンドポイント 365 エンドポイントOffice確認する</span><span class="sxs-lookup"><span data-stu-id="fa505-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="fa505-127">ネットワークパフォーマンスの監視と調整</span><span class="sxs-lookup"><span data-stu-id="fa505-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="fa505-128">ExpressRoute 接続を監視する</span><span class="sxs-lookup"><span data-stu-id="fa505-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="fa505-129">ネットワーク機器ベンダー</span><span class="sxs-lookup"><span data-stu-id="fa505-129">Network equipment vendors</span></span>

<span data-ttu-id="fa505-130">ネットワーク機器ベンダーの場合は [、Microsoft 365 Networking Partner Program に参加してください](microsoft-365-networking-partner-program.md)。</span><span class="sxs-lookup"><span data-stu-id="fa505-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="fa505-131">Microsoft 365 ネットワーク接続の原則を製品とソリューションに組み込むプログラムに登録します。</span><span class="sxs-lookup"><span data-stu-id="fa505-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="fa505-132">Contoso 社が Microsoft 365 のネットワークを行った方法</span><span class="sxs-lookup"><span data-stu-id="fa505-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="fa505-133">架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa505-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="fa505-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="fa505-135">Next step</span></span>

<span data-ttu-id="fa505-136">[Microsoft 365](microsoft-365-networking-overview.md)ネットワーク接続の概要を使用して、ネットワーク計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa505-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>