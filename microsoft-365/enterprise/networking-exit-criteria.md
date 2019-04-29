---
title: 'フェーズ 1: ネットワーク インフラストラクチャの終了条件'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise のネットワーク インフラストラクチャの条件を満たしていることを確認します。
ms.openlocfilehash: 9ea601d66ef2df0d7a4efde188a70c51e3fb9f60
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400221"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="fce89-103">フェーズ 1: ネットワーク インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="fce89-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="fce89-104">ネットワーク インフラストラクチャが次の必須基準を満たすとともに、オプションの基準も考慮済みであることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="fce89-104">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="fce89-105">必須: Microsoft 365 Enterprise に必要なネットワーク環境が準備できていること</span><span class="sxs-lookup"><span data-stu-id="fce89-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="fce89-106">オフィスごとの、Office 365、Microsoft Intune、Windows 10 Enterprise のインストールと更新を含む、Microsoft 365 トラフィックに見合ったインターネット帯域幅の確保</span><span class="sxs-lookup"><span data-stu-id="fce89-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="fce89-107">Office 365 の参照アーキテクチャに関するネットワーク全体のマップ</span><span class="sxs-lookup"><span data-stu-id="fce89-107">Your overall network maps to an Office 365 reference architecture</span></span>
- <span data-ttu-id="fce89-108">ネットワークの変更のパイロット実行とテストが済んでおり、トラフィックの待機時間の要件が満たされていること</span><span class="sxs-lookup"><span data-stu-id="fce89-108">Your network changes have been piloted and tested and meet with your traffic latency requirements</span></span> 

<span data-ttu-id="fce89-109">必要に応じて、[手順 1](networking-provide-bandwidth-cloud-services.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fce89-109">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="fce89-110">必須: 支店のローカル インターネット接続と名前解決機能</span><span class="sxs-lookup"><span data-stu-id="fce89-110">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="fce89-p101">各支店に、ローカル ISP を使用したインターネット アクセスが構成され、そのローカル ISP の DNS サーバーがローカル パブリック IP を使用してインターネット上での自身の位置を識別するようになっていること。これにより、Office 365 と Intune にアクセスするユーザーのパフォーマンスを最大限に引き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fce89-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="fce89-113">各支店でローカル ISP を使用していない場合、ネットワーク トラフィックが組織のバックボーンを通過する必要があるか、またはデータ リクエストがリモートのフロントエンド サーバーにより処理されるため、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fce89-113">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="fce89-114">テスト方法</span><span class="sxs-lookup"><span data-stu-id="fce89-114">How to test</span></span>
<span data-ttu-id="fce89-p102">当該支社のデバイスからツールまたは Web サイトを使用して、プロキシ サーバーが使用しているパブリック IP アドレスを判別します。たとえば、[What Is My IP Address](https://www.whatismypublicip.com/) Web ページなどを使用します。ISP により割り当てられるパブリック IP アドレスは、地理的にローカルなはずです。これは、本社のパブリック IP アドレス範囲またはクラウドベース ネットワーク セキュリティ ベンダーの IP アドレスであってはなりません。</span><span class="sxs-lookup"><span data-stu-id="fce89-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="fce89-119">必要に応じて、[手順 2](networking-dns-resolution-same-location.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fce89-119">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="fce89-120">オプション: 不要なネットワーク ヘアピンの削除</span><span class="sxs-lookup"><span data-stu-id="fce89-120">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="fce89-p103">ネットワーク ヘアピンの調査と、オフィス全体のパフォーマンスに与える影響の確認がなされていること。削除できるヘアピンを削除するか、サード パーティのネットワーク プロバイダーやセキュリティ プロバイダーと協力し、ネットワークに最適な Microsoft 365 ピアリングが実装されていること。</span><span class="sxs-lookup"><span data-stu-id="fce89-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="fce89-123">必要に応じて、[手順 3](networking-avoid-network-hairpins.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fce89-123">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="fce89-124">オプション: インターネット ブラウザーとエッジ デバイスでのトラフィック バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="fce89-124">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="fce89-125">最新の PAC ファイルをオンプレミスのインターネット ブラウザーに展開し、Microsoft 365 の DNS ドメイン名へのトラフィックがプロキシ サーバーをバイパスするように構成されていること。</span><span class="sxs-lookup"><span data-stu-id="fce89-125">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="fce89-126">ネットワーク境界デバイス (ファイアウォール、SSL 中断/検査、パケット検査デバイスなど) が、トラフィック バイパスを使用するか、Microsoft 365 の "最適化" および "許可" カテゴリのエンドポイントへのトラフィック処理が最小限になるように構成されていること。</span><span class="sxs-lookup"><span data-stu-id="fce89-126">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="fce89-127">テスト方法</span><span class="sxs-lookup"><span data-stu-id="fce89-127">How to test</span></span>

<span data-ttu-id="fce89-128">ネットワーク境界デバイスでログ ツールを使用し、Microsoft 365 を宛先とするトラフィックが検査されたり、暗号化されたり、またはその他のことで阻害されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fce89-128">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="fce89-129">必要に応じて、[手順 4](networking-configure-proxies-firewalls.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fce89-129">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="fce89-130">オプション: クライアントと Office 365 アプリケーションが最適なパフォーマンスを実現できるように構成されている</span><span class="sxs-lookup"><span data-stu-id="fce89-130">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="fce89-131">クライアント デバイスと、Exchange Online、Skype for Business Online、SharePoint Online、Project Online の各サービスの Transmssion Control Protocol (TCP) 設定を最適化している。</span><span class="sxs-lookup"><span data-stu-id="fce89-131">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="fce89-132">必要に応じて、[手順 5](networking-optimize-tcp-performance.md) がこのオプション条件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fce89-132">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="fce89-133">結果と次のステップ</span><span class="sxs-lookup"><span data-stu-id="fce89-133">Results and next steps</span></span>

<span data-ttu-id="fce89-134">これで、イントラネット ユーザーは、効率的なネットワーク パスでインターネットに接続して、Microsoft 365 クラウド サービスを利用する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="fce89-134">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="fce89-135">Microsoft 365 Enterprise のエンド ツー エンド展開のフェーズを実行している場合、次の手順は [ID](identity-infrastructure.md) です。</span><span class="sxs-lookup"><span data-stu-id="fce89-135">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
