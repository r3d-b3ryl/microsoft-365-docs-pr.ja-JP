---
title: Microsoft 365 のネットワークロードマップ
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 93d0f253e098815139b431a826f7e5e7a0410b37
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691914"
---
# <a name="networking-roadmap-for-microsoft-365"></a><span data-ttu-id="982d3-103">Microsoft 365 のネットワークロードマップ</span><span class="sxs-lookup"><span data-stu-id="982d3-103">Networking roadmap for Microsoft 365</span></span>

<span data-ttu-id="982d3-104">Microsoft 365 enterprise には、コラボレーションと生産性のクラウドサービス、Microsoft Intune、および Microsoft Azure の id およびセキュリティサービスが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="982d3-104">Microsoft 365 for enterprise includes collaboration and productivity cloud services, Microsoft Intune, and many identity and security services of Microsoft Azure.</span></span> <span data-ttu-id="982d3-105">これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。</span><span class="sxs-lookup"><span data-stu-id="982d3-105">All of these cloud-based services rely on the security, performance, and reliability of connections from client devices over the Internet or dedicated circuits.</span></span> <span data-ttu-id="982d3-106">これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="982d3-106">To host these services and make them available to customers all over the world, Microsoft has designed a networking infrastructure that emphasizes performance and integration.</span></span> 

<span data-ttu-id="982d3-107">Microsoft 365 オンボードの重要な部分は、ネットワークとインターネット接続が最適なアクセスのためにセットアップされていることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="982d3-107">A crucial part of your Microsoft 365 onboarding is to ensure that your network and Internet connections are set up for optimized access.</span></span> <span data-ttu-id="982d3-108">グローバルに分散されたソフトウェア (SaaS) クラウドにアクセスするようにオンプレミスネットワークを構成することは、社内データセンターへのトラフィック用に最適化された従来のネットワークや中央のインターネット接続とは異なります。</span><span class="sxs-lookup"><span data-stu-id="982d3-108">Configuring your on-premises network to access a globally distributed Software-as-a-Service (SaaS) cloud is different from a traditional network that is optimized for traffic to on-premises datacenters and a central Internet connection.</span></span> 

<span data-ttu-id="982d3-109">以下の記事を活用して主な違いを理解し、エッジ デバイス、クライアント コンピューター、オンプレミス ネットワークを変更して、オンプレミス ユーザーの最高のパフォーマンスを引き出します。</span><span class="sxs-lookup"><span data-stu-id="982d3-109">Use these articles to understand the key differences and to modify your edge devices, client computers, and on-premises network to get the best performance for your on-premises users.</span></span>

## <a name="plan"></a><span data-ttu-id="982d3-110">プラン</span><span class="sxs-lookup"><span data-stu-id="982d3-110">Plan</span></span>

<span data-ttu-id="982d3-111">ネットワーク実装の計画段階で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="982d3-111">In the planning phase of your networking implementation:</span></span>

- [<span data-ttu-id="982d3-112">Microsoft 365 ネットワークのしくみを理解する</span><span class="sxs-lookup"><span data-stu-id="982d3-112">Understand how Microsoft 365 networking works</span></span>](microsoft-365-networking-overview.md)
- [<span data-ttu-id="982d3-113">現在のネットワーク接続を評価する</span><span class="sxs-lookup"><span data-stu-id="982d3-113">Assess your current network connectivity</span></span>](assessing-network-connectivity.md)
- [<span data-ttu-id="982d3-114">ExpressRoute が組織に適しているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="982d3-114">Determine if ExpressRoute is right for your organization</span></span>](network-planning-with-expressroute.md)
- [<span data-ttu-id="982d3-115">ネットワークデバイスの計画</span><span class="sxs-lookup"><span data-stu-id="982d3-115">Plan for your network devices</span></span>](plan-for-network-devices.md)
- [<span data-ttu-id="982d3-116">移行のためにネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="982d3-116">Get your network set up for migration</span></span>](network-and-migration-planning.md)

## <a name="deploy"></a><span data-ttu-id="982d3-117">展開</span><span class="sxs-lookup"><span data-stu-id="982d3-117">Deploy</span></span>

<span data-ttu-id="982d3-118">ネットワーク実装の展開フェーズで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="982d3-118">In the deployment phase of your networking implementation:</span></span>

- [<span data-ttu-id="982d3-119">エンタープライズネットワークが Microsoft 365 接続用に最適化されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="982d3-119">Ensure your enterprise network is optimized for Microsoft 365 connectivity</span></span>](set-up-network-for-microsoft-365.md)
- [<span data-ttu-id="982d3-120">組織の DNS ドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="982d3-120">Add the DNS domains for your organization</span></span>](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [<span data-ttu-id="982d3-121">Microsoft 365 エンドポイントへの接続を最適化する</span><span class="sxs-lookup"><span data-stu-id="982d3-121">Optimize your connectivity to Microsoft 365 endpoints</span></span>](microsoft-365-ip-web-service.md)
- [<span data-ttu-id="982d3-122">リモートワーカーの接続を最適化する</span><span class="sxs-lookup"><span data-stu-id="982d3-122">Optimize connectivity for remote workers</span></span>](microsoft-365-vpn-split-tunnel.md)
- <span data-ttu-id="982d3-123">必要に応じて、 [ExpressRoute を構成](azure-expressroute.md)します。</span><span class="sxs-lookup"><span data-stu-id="982d3-123">If needed, [configure ExpressRoute](azure-expressroute.md)</span></span>

## <a name="manage"></a><span data-ttu-id="982d3-124">管理</span><span class="sxs-lookup"><span data-stu-id="982d3-124">Manage</span></span>

<span data-ttu-id="982d3-125">ネットワーク実装の管理段階で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="982d3-125">In the management phase of your networking implementation:</span></span>

- [<span data-ttu-id="982d3-126">ネットワークデバイスが最新の Office 365 エンドポイントを使用していることを確認する</span><span class="sxs-lookup"><span data-stu-id="982d3-126">Ensure that your network devices are using the latest Office 365 endpoints</span></span>](microsoft-365-endpoints.md)
- [<span data-ttu-id="982d3-127">ネットワークのパフォーマンスを監視および調整する</span><span class="sxs-lookup"><span data-stu-id="982d3-127">Monitor and tune your networking performance</span></span>](network-planning-and-performance.md)
- [<span data-ttu-id="982d3-128">ExpressRoute 接続を監視する</span><span class="sxs-lookup"><span data-stu-id="982d3-128">Monitor your ExpressRoute connections</span></span>](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a><span data-ttu-id="982d3-129">ネットワーク機器ベンダー</span><span class="sxs-lookup"><span data-stu-id="982d3-129">Network equipment vendors</span></span>

<span data-ttu-id="982d3-130">ネットワーク機器ベンダーの場合は、 [Microsoft 365 ネットワークパートナープログラム](microsoft-365-networking-partner-program.md)に参加してください。</span><span class="sxs-lookup"><span data-stu-id="982d3-130">If you are a network equipment vendor, join the [Microsoft 365 Networking Partner Program](microsoft-365-networking-partner-program.md).</span></span> <span data-ttu-id="982d3-131">Microsoft 365 ネットワーク接続の原則を製品とソリューションに構築するために、プログラムに登録します。</span><span class="sxs-lookup"><span data-stu-id="982d3-131">Enroll in the program to build Microsoft 365 network connectivity principles into your products and solutions.</span></span> 

## <a name="how-contoso-did-networking-for-microsoft-365"></a><span data-ttu-id="982d3-132">Contoso 社が Microsoft 365 に接続する方法</span><span class="sxs-lookup"><span data-stu-id="982d3-132">How Contoso did networking for Microsoft 365</span></span>

<span data-ttu-id="982d3-133">架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="982d3-133">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network devices and Internet connections](contoso-networking.md) for Microsoft 365 cloud services.</span></span>

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="982d3-135">次の手順</span><span class="sxs-lookup"><span data-stu-id="982d3-135">Next step</span></span>

<span data-ttu-id="982d3-136">[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)を使用して、ネットワークの計画を開始します。</span><span class="sxs-lookup"><span data-stu-id="982d3-136">Start your networking planning with the [Microsoft 365 networking connectivity overview](microsoft-365-networking-overview.md).</span></span>
