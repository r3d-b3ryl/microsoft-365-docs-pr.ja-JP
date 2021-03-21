---
title: Office 365 サービスに接続するネットワーク デバイスの計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: '概要: ネットワーク容量、WAN アクセラレータ、および 365 への接続に使用される負荷分散デバイスに関する考慮事項Officeします。'
ms.openlocfilehash: e1209c13eb24d11a2cc9692957bc4ee5f6310f41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927502"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a><span data-ttu-id="ec2ca-103">Office 365 サービスに接続するネットワーク デバイスの計画</span><span class="sxs-lookup"><span data-stu-id="ec2ca-103">Plan for network devices that connect to Office 365 services</span></span>

<span data-ttu-id="ec2ca-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="ec2ca-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>
  
<span data-ttu-id="ec2ca-105">一部のネットワーク ハードウェアでは、サポートされている同時セッションの数に制限がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-105">Some network hardware may have limitations on the number of concurrent sessions that are supported.</span></span> <span data-ttu-id="ec2ca-106">2,000 人を超えるユーザーを持つ組織の場合は、ネットワーク デバイスを監視して、追加の 365 サービス トラフィックを処理Officeすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-106">For organizations having more than 2,000 users, we recommend that they monitor their network devices to ensure they are capable of handling the additional Office 365 service traffic.</span></span> <span data-ttu-id="ec2ca-107">簡易ネットワーク管理プロトコル (SNMP) 監視ソフトウェアは、これを行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-107">Simple Network Management Protocol (SNMP) monitoring software can help you do this.</span></span>

<span data-ttu-id="ec2ca-108">この記事は [、365](./network-planning-and-performance.md)のネットワーク計画とパフォーマンスの調整Officeです。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-108">This article is part of [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).</span></span>

<span data-ttu-id="ec2ca-109">オンプレミスの送信インターネット プロキシ設定は、クライアント アプリケーションOffice 365 サービスへの接続にも影響します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-109">On-premises outgoing Internet proxy settings also affect connectivity to Office 365 services for your client applications.</span></span> <span data-ttu-id="ec2ca-110">また、Microsoft クラウド サービスの URL とアプリケーションへの接続を許可するネットワーク プロキシ デバイスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-110">You must also configure your network proxy devices to allow connections for Microsoft cloud services URLs and applications.</span></span> <span data-ttu-id="ec2ca-111">すべての組織が異なります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-111">Every organization is different.</span></span> <span data-ttu-id="ec2ca-112">Microsoft がこのプロセスを管理する方法と、プロビジョニングする帯域幅の量を確認するには、ケース [スタディを参照してください](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-112">To get an idea for how Microsoft manages this process and the amount of bandwidth we provision, [read the case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365).</span></span>
  
<span data-ttu-id="ec2ca-113">次の Skype for Business ヘルプ記事には、Skype for Business 設定の詳細があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-113">The following Skype for Business Help articles have more information about Skype for Business settings:</span></span>
  
- [<span data-ttu-id="ec2ca-114">管理者向け Skype for Business Online サインイン エラーのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ec2ca-114">Troubleshooting Skype for Business Online sign-in errors for administrators</span></span>](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [<span data-ttu-id="ec2ca-115">オンプレミスのファイアウォールが接続をブロックするために、Skype for Business に接続できないか、特定の機能が機能しない</span><span class="sxs-lookup"><span data-stu-id="ec2ca-115">You cannot connect to Skype for Business, or certain features do not work, because an on-premises firewall blocks the connection</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> <span data-ttu-id="ec2ca-116">これらの設定の多くは Skype for Business 固有ですが、ネットワーク構成に関する一般的なガイダンスは、すべての 365 サービスOffice役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-116">While many of these settings are Skype for Business-specific, the general guidance on network configuration is useful for all Office 365 services.</span></span>
  
## <a name="determining-network-capacity"></a><span data-ttu-id="ec2ca-117">ネットワーク容量の決定</span><span class="sxs-lookup"><span data-stu-id="ec2ca-117">Determining Network Capacity</span></span>

<span data-ttu-id="ec2ca-118">接続に存在するネットワーク デバイスには、容量制限があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-118">Every network device that exists on a connection has its capacity limit.</span></span> <span data-ttu-id="ec2ca-119">これらのデバイスには、クライアントとサーバーのネットワーク アダプター、ルーター、スイッチ、およびそれらを相互接続するハブが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-119">These devices include the client and server network adapters, routers, switches, and hubs that interconnect them.</span></span> <span data-ttu-id="ec2ca-120">適切なネットワーク容量は、どのネットワーク容量も飽和状態でいなかっているという意味です。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-120">Adequate network capacity means that none of them are saturated.</span></span> <span data-ttu-id="ec2ca-121">ネットワーク アクティビティの監視は、すべてのネットワーク デバイスの実際の負荷が最大容量より小さい状態を確保するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-121">Monitoring network activity is essential to help ensure that the actual loads on all network devices are less than their maximum capacity.</span></span> <span data-ttu-id="ec2ca-122">ネットワーク容量は、プロキシ デバイスのパフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-122">Network capacity affects proxy device performance.</span></span>
  
<span data-ttu-id="ec2ca-123">ほとんどの場合、インターネット接続帯域幅はトラフィック量の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-123">In most situations, the Internet connection bandwidth sets the limit for the amount of traffic.</span></span> <span data-ttu-id="ec2ca-124">トラフィックのピーク時のパフォーマンスが低下する原因は、インターネット リンクが過剰に使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-124">Weak performance during peak traffic hours is probably caused by excessive use of the Internet link.</span></span> <span data-ttu-id="ec2ca-125">この状況は、ブランチ オフィス のプロキシ サーバー コンピューターが低速のワイド エリア ネットワーク (WAN) リンクを使用してブランチの本社のプロキシ デバイスに接続されるブランチ オフィスのシナリオにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-125">This situation also applies to a branch office scenario, where branch office proxy server computers are connected to the proxy device at the branch's headquarters over a slow Wide Area Network (WAN) link.</span></span>
  
<span data-ttu-id="ec2ca-126">ネットワーク容量をテストするには、プロキシ ネットワーク インターフェイスでネットワーク アクティビティを監視します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-126">To test network capacity, monitor the network activity on the proxy network interface.</span></span> <span data-ttu-id="ec2ca-127">ネットワーク インターフェイスの最大帯域幅の 75% を超える場合は、不十分なネットワーク インフラストラクチャの帯域幅を増やしてください。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-127">If it's more than 75 percent of the maximum bandwidth of any network interface, consider increasing the bandwidth of the network infrastructure that's inadequate.</span></span> <span data-ttu-id="ec2ca-128">または、HTTP 圧縮などの高度な機能の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-128">Or, consider using advanced features, such as HTTP compression.</span></span>
  
## <a name="wan-accelerators"></a><span data-ttu-id="ec2ca-129">WAN アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="ec2ca-129">WAN Accelerators</span></span>

<span data-ttu-id="ec2ca-130">組織でワイド エリア ネットワーク (WAN) アクセラレーション プロキシ アプライアンスを使用している場合は、365 サービスにアクセスするときにOffice発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-130">If your organization uses wide area network (WAN) acceleration proxy appliances, you may encounter issues when you access the Office 365 services.</span></span> <span data-ttu-id="ec2ca-131">ネットワーク デバイスまたはデバイスを最適化して、ユーザーが 365 から 365 にアクセスするときに一貫性のあるエクスペリエンスをOffice場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-131">You may need to optimize your network device or devices to ensure that your users have a consistent experience when accessing Office 365.</span></span> <span data-ttu-id="ec2ca-132">たとえば、365 Office 365 サービスは、365 コンテンツOffice TCP ヘッダーを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-132">For example, Office 365 services encrypt some Office 365 content and the TCP header.</span></span> <span data-ttu-id="ec2ca-133">デバイスでこの種類のトラフィックを処理できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-133">Your device may not be able to handle this kind of traffic.</span></span>
  
<span data-ttu-id="ec2ca-134">WAN 最適化コントローラーまたはトラフィック/検査デバイスを [365](https://support.microsoft.com/kb/2690045)で使用する方法に関するOffice参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-134">Read our support statement about [Using WAN Optimization Controller or Traffic/Inspection devices with Office 365](https://support.microsoft.com/kb/2690045).</span></span>
  
## <a name="hardware-and-software-load-balancing-devices"></a><span data-ttu-id="ec2ca-135">ハードウェアおよびソフトウェア負荷分散デバイス</span><span class="sxs-lookup"><span data-stu-id="ec2ca-135">Hardware and Software Load-balancing Devices</span></span>

<span data-ttu-id="ec2ca-136">組織では、ハードウェア ロード バランサー (HLB) またはネットワーク負荷分散 (NLB) ソリューションを使用して、Active Directory フェデレーション サービス (AD FS) サーバーや Exchange ハイブリッド サーバーに要求を配布する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-136">Your organization needs to use a hardware load balancer (HLB) or a Network Load Balancing (NLB) solution to distribute requests to your Active Directory Federation Services (AD FS) servers and/or your Exchange hybrid servers.</span></span> <span data-ttu-id="ec2ca-137">負荷分散デバイスは、オンプレミス サーバーへのネットワーク トラフィックを制御します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-137">Load-balancing devices control the network traffic to the on-premises servers.</span></span> <span data-ttu-id="ec2ca-138">これらのサーバーは、シングル サインオンと Exchange ハイブリッド展開の可用性を確保する上で重要です。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-138">These servers are crucial in helping to ensure the availability of single sign-on and Exchange hybrid deployment.</span></span>
  
<span data-ttu-id="ec2ca-139">Windows Server に組み込むソフトウェア ベースの NLB ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-139">We provide a software-based NLB solution built into Windows Server.</span></span> <span data-ttu-id="ec2ca-140">Office 365 は、このソリューションをサポートすることによって負荷分散を実現します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-140">Office 365 supports this solution to achieve load balancing.</span></span>
  
## <a name="firewalls-and-proxies"></a><span data-ttu-id="ec2ca-141">ファイアウォールとプロキシ</span><span class="sxs-lookup"><span data-stu-id="ec2ca-141">Firewalls and proxies</span></span>

<span data-ttu-id="ec2ca-142">Office 365 に接続するためのファイアウォールとプロキシの構成の詳細については [、「Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)エンドポイントの管理」、Office [365](assessing-network-connectivity.md)ネットワーク接続の評価、および [Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) エンドポイントの FAQ を参照して、デバイスと回線の選択の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec2ca-142">For more details on configuring firewalls and proxies to connect to Office 365, read [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), [Assessing Office 365 network connectivity](assessing-network-connectivity.md), and [Office 365 endpoints FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) to learn more about devices and circuit selection.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec2ca-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec2ca-143">See also</span></span>

[<span data-ttu-id="ec2ca-144">365 サービスのOfficeガイド</span><span class="sxs-lookup"><span data-stu-id="ec2ca-144">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)

[<span data-ttu-id="ec2ca-145">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="ec2ca-145">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)