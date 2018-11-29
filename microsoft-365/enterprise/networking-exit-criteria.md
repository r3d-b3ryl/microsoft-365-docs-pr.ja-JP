---
title: 'フェーズ 1: ネットワーク インフラストラクチャの終了条件'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 構成が Microsoft 365 Enterprise のネットワーク インフラストラクチャの条件を満たしていることを確認します。
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868988"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="242c8-103">フェーズ 1: ネットワーク インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="242c8-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="242c8-104">ネットワーク インフラストラクチャが次の条件を満たしている場合は、フェーズ 2 に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="242c8-104">If your networking infrastructure meets the following conditions, you’re ready to move to Phase 2.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="242c8-105">必須: Microsoft 365 Enterprise に必要なネットワーク環境が準備できていること</span><span class="sxs-lookup"><span data-stu-id="242c8-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="242c8-106">オフィスごとの、Office 365、Microsoft Intune、Windows 10 Enterprise のインストールと更新を含む、Microsoft 365 トラフィックに見合ったインターネット帯域幅の確保</span><span class="sxs-lookup"><span data-stu-id="242c8-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="242c8-107">一般的なインターネット トラフィックすべてを処理する本社</span><span class="sxs-lookup"><span data-stu-id="242c8-107">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="242c8-108">最適化カテゴリのエンドポイント トラフィックを処理する支店</span><span class="sxs-lookup"><span data-stu-id="242c8-108">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="242c8-109">Office 365 の参照アーキテクチャに関するネットワーク全体のマップ</span><span class="sxs-lookup"><span data-stu-id="242c8-109">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="242c8-110">必要に応じて、[手順 1](networking-provide-bandwidth-cloud-services.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="242c8-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="242c8-111">必須: 支店のローカル インターネット接続と名前解決機能</span><span class="sxs-lookup"><span data-stu-id="242c8-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="242c8-p101">各支店に、ローカル ISP を使用したインターネット アクセスが構成され、そのローカル ISP の DNS サーバーがローカル パブリック IP を使用してインターネット上での自身の位置を識別するようになっていること。これにより、Office 365 と Intune にアクセスするユーザーのパフォーマンスを最大限に引き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="242c8-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="242c8-114">各支店でローカル ISP を使用していない場合、ネットワーク トラフィックが組織のバックボーンを通過する必要があるか、またはデータ リクエストがリモートのフロントエンド サーバーにより処理されるため、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="242c8-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="242c8-115">テスト方法</span><span class="sxs-lookup"><span data-stu-id="242c8-115">How to test</span></span>
<span data-ttu-id="242c8-p102">当該支社のデバイスからツールまたは Web サイトを使用して、プロキシ サーバーが使用しているパブリック IP アドレスを判別します。たとえば、[What Is My IP Address](https://www.whatismypublicip.com/) Web ページなどを使用します。ISP により割り当てられるパブリック IP アドレスは、地理的にローカルなはずです。これは、本社のパブリック IP アドレス範囲またはクラウドベース ネットワーク セキュリティ ベンダーの IP アドレスであってはなりません。</span><span class="sxs-lookup"><span data-stu-id="242c8-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="242c8-120">必要に応じて、[手順 2](networking-dns-resolution-same-location.md) がこの必須条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="242c8-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="242c8-121">オプション: 不要なネットワーク ヘアピンの削除</span><span class="sxs-lookup"><span data-stu-id="242c8-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="242c8-p103">ネットワーク ヘアピンの調査と、オフィス全体のパフォーマンスに与える影響の確認がなされていること。削除できるヘアピンを削除するか、サード パーティのネットワーク プロバイダーやセキュリティ プロバイダーと協力し、ネットワークに最適な Microsoft 365 ピアリングが実装されていること。</span><span class="sxs-lookup"><span data-stu-id="242c8-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="242c8-124">必要に応じて、[手順 3](networking-avoid-network-hairpins.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="242c8-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="242c8-125">オプション: インターネット ブラウザーとエッジ デバイスでのトラフィック バイパスの構成</span><span class="sxs-lookup"><span data-stu-id="242c8-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="242c8-126">最新の PAC ファイルをオンプレミスのインターネット ブラウザーに展開し、Microsoft 365 の DNS ドメイン名へのトラフィックがプロキシ サーバーをバイパスするように構成されていること。</span><span class="sxs-lookup"><span data-stu-id="242c8-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="242c8-127">ネットワーク境界デバイス (ファイアウォール、SSL 中断/検査、パケット検査デバイスなど) が、トラフィック バイパスを使用するか、Microsoft 365 の "最適化" および "許可" カテゴリのエンドポイントへのトラフィック処理が最小限になるように構成されていること。</span><span class="sxs-lookup"><span data-stu-id="242c8-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="242c8-128">テスト方法</span><span class="sxs-lookup"><span data-stu-id="242c8-128">How to test</span></span>

<span data-ttu-id="242c8-129">ネットワーク境界デバイスでログ ツールを使用し、Microsoft 365 を宛先とするトラフィックが検査されたり、暗号化されたり、またはその他のことで阻害されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="242c8-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="242c8-130">必要に応じて、[手順 4](networking-configure-proxies-firewalls.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="242c8-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="242c8-131">オプション: クライアントと Office 365 アプリケーションが最適なパフォーマンスを実現できるように構成されている</span><span class="sxs-lookup"><span data-stu-id="242c8-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="242c8-132">クライアント デバイスと、Exchange Online、Skype for Business Online、SharePoint Online、Project Online の各サービスの Transmssion Control Protocol (TCP) 設定を最適化している。</span><span class="sxs-lookup"><span data-stu-id="242c8-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="242c8-133">必要に応じて、[手順 5](networking-optimize-tcp-performance.md) がこのオプション条件を満たす上で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="242c8-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="next-phase"></a><span data-ttu-id="242c8-134">次のフェーズ</span><span class="sxs-lookup"><span data-stu-id="242c8-134">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="242c8-135">Microsoft 365 Enterprise のエンドツーエンド展開プロセスの次のフェーズは、[ID](identity-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="242c8-135">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [identity](identity-infrastructure.md).</span></span> |
