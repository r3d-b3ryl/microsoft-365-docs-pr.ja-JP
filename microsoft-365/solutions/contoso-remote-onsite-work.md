---
title: Contoso 社の COVID-19 の応答と、リモートおよびオンサイト作業のサポート
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation が COVID-19 pandemic にどのように反応したかを理解し、リモートおよびオンサイト作業のためのインフラストラクチャをインストールおよび更新するインフラストラクチャを設計しました。
ms.openlocfilehash: d04b4efcdd4dd04315ad37311cdd2cfbc2e64e88
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580675"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="0c327-103">Contoso 社の COVID-19 の応答と、リモートおよびオンサイト作業のサポート</span><span class="sxs-lookup"><span data-stu-id="0c327-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="0c327-104">Contoso 社では、常にリモートワーカーをサポートしており、パリ本社の中央 VPN サーバーを介してオンプレミスのリソースにアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="0c327-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="0c327-105">Contoso 社は、すべてのリモートワーカーに管理されたラップトップを発行しました。</span><span class="sxs-lookup"><span data-stu-id="0c327-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="0c327-106">オンプレミスのワーカーは、デスクトップコンピューターとラップトップを混在させることができました。</span><span class="sxs-lookup"><span data-stu-id="0c327-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="0c327-107">COVID に対する Contoso の応答</span><span class="sxs-lookup"><span data-stu-id="0c327-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="0c327-108">COVID-19 pandemic が始まっている状態では、突然、重要なワーカーはリモートワーカーでした。</span><span class="sxs-lookup"><span data-stu-id="0c327-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="0c327-109">Contoso 社は、従業員を在宅勤務に移行させることによって反応し、Microsoft 365 cloud services を使用してオンプレミスのリソースへのリモートアクセスを通じて主な活動を実施しています。</span><span class="sxs-lookup"><span data-stu-id="0c327-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="0c327-110">Contoso 社では、既にリモートで作業している従業員の25% をサポートするために、パリ本社オフィスにリモートアクセス VPN サーバーがありましたが、迅速に移行することにより、そのリモートアクセスのキャパシティを拡大して、90% の人員をサポートしていました。</span><span class="sxs-lookup"><span data-stu-id="0c327-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="0c327-111">Contoso 社は、リモートアクセス VPN サーバーを各サテライトオフィスに展開して、リモートワーカーが Contoso イントラネットにアクセスするために地域的 close エントリポイントを使用するようにしました。</span><span class="sxs-lookup"><span data-stu-id="0c327-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="0c327-112">Contoso 社は、分割トンネリング用のラップトップ、タブレット、スマートフォンにインストールされている VPN クライアントの構成も更新して、Office 365 エンドポイントの最適化セットのトラフィックが VPN 接続をバイパスしてインターネット上で直接送信されるようにしました。</span><span class="sxs-lookup"><span data-stu-id="0c327-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="0c327-113">詳細については、「 [VPN 分割トンネリングを使用してリモートユーザー用に Office 365 接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c327-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="0c327-114">これは、パリ本社および各サテライトオフィスにインストールされた VPN デバイスを使用した構成の結果です。</span><span class="sxs-lookup"><span data-stu-id="0c327-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso 社の VPN インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="0c327-116">VPN クライアントがインストールされているリモートワーカーは、DNS を使用して地域的の最も近い office を検索し、そこにインストールされている VPN デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="0c327-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="0c327-117">分割トンネリングでは、Microsoft 365 の最適化エンドポイントへのトラフィックは、地域的に最も近い Microsoft 365 のネットワークの場所に直接送信されます。</span><span class="sxs-lookup"><span data-stu-id="0c327-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="0c327-118">他のすべてのトラフィックは、vpn デバイスへの VPN 接続を介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="0c327-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="0c327-119">Contoso 社のリモートおよびオンサイト作業のサポート</span><span class="sxs-lookup"><span data-stu-id="0c327-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="0c327-120">地域ロックダウン時にほとんどのリモートワーカーをサポートするように初期変更を行った後、Contoso 社は、次のような作業を行うことができる、リモートおよびオンサイトの作業をサポートするインフラストラクチャの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="0c327-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="0c327-121">常にリモート。</span><span class="sxs-lookup"><span data-stu-id="0c327-121">Always remote.</span></span>
- <span data-ttu-id="0c327-122">常にオンサイト。</span><span class="sxs-lookup"><span data-stu-id="0c327-122">Always onsite.</span></span>
- <span data-ttu-id="0c327-123">オンサイトとリモートの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="0c327-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="0c327-124">Microsoft 365 の id、セキュリティ、およびコンプライアンス機能は、信頼度がゼロになるように設計されており、ユーザーとデバイスの場所に関係なく動作します。</span><span class="sxs-lookup"><span data-stu-id="0c327-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="0c327-125">詳細については、「 [ゼロ信頼](https://www.microsoft.com/security/business/zero-trust)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c327-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="0c327-126">ただし、インストールするソフトウェアは社内またはインターネットソースから入手できるため、ソフトウェアの新規インストールと更新プログラムの管理はデバイスの場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c327-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="0c327-127">Contoso 社の IT アーキテクトは、新しいインストールを設計し、ワーカーではなくデバイスの場所に基づいてインフラストラクチャを更新します。</span><span class="sxs-lookup"><span data-stu-id="0c327-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="0c327-128">これらは、オンプレミスとローミングの2種類のデバイスを指定していました。</span><span class="sxs-lookup"><span data-stu-id="0c327-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="0c327-129">専用オンプレミス</span><span class="sxs-lookup"><span data-stu-id="0c327-129">Dedicated on-premises</span></span>

<span data-ttu-id="0c327-130">専用のオンプレミスデバイスは、Contoso イントラネットから離れたままで、VPN クライアントがインストールされていないデスクトップまたはサーバーコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="0c327-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="0c327-131">これらのオンプレミスデバイスは、Microsoft エンドポイント構成マネージャーとその配布ポイントを引き続き使用して、Windows 10、Microsoft 365 Apps for enterprise、エッジブラウザーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c327-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="0c327-132">節約</span><span class="sxs-lookup"><span data-stu-id="0c327-132">Roaming</span></span>

<span data-ttu-id="0c327-133">ローミングデバイスは Contoso イントラネットを離れることができ、多くの office ワーカーと、Contoso VPN クライアントがインストールされているスマートフォンやタブレットなどのすべてのリモートワーカーとその他の組織所有のデバイスに対して発行されたラップトップを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="0c327-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="0c327-134">これらのデバイスは、いつでもインターネットに接続できるため、Intune またはその他のクラウドベースのサービスを使用して、Windows 10、Microsoft 365 Apps for enterprise、および Edge をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c327-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="0c327-135">これらのユーザーは、既存のオンプレミス構成マネージャーの配布ポイントを使用しません。</span><span class="sxs-lookup"><span data-stu-id="0c327-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="0c327-136">これは、ローミングデバイスのインストールと更新が、オンプレミスの間にインターネット経由で行われ、イントラネットに接続されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="0c327-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="0c327-137">しかし、Contoso 社の IT アーキテクトは、イントラネットの帯域幅をインターネットに最適化するよりも構成の簡略化が重要であると判断しました。特に、ほとんどのリモートワーカーがほとんどの場合、イントラネットに接続されていない場合。</span><span class="sxs-lookup"><span data-stu-id="0c327-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="0c327-138">最終的なインフラストラクチャは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0c327-138">Here is the resulting infrastructure.</span></span>

![Contoso 社のインストールおよび更新インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="0c327-140">インストールと更新の動作は、デバイスのコンピューターアカウントをこれらのグループのいずれかのメンバーにすることによって決まります。</span><span class="sxs-lookup"><span data-stu-id="0c327-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="0c327-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="0c327-141">OnPremDevices</span></span>

  <span data-ttu-id="0c327-142">デバイス上の Configuration Manager クライアントは、配布ポイントを使用してインストールと更新を行います。</span><span class="sxs-lookup"><span data-stu-id="0c327-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="0c327-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="0c327-143">RoamingDevices</span></span>

  <span data-ttu-id="0c327-144">デバイス上の Intune およびその他の設定は、インストールと更新に Microsoft 365 ネットワークの使用を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c327-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="0c327-145">新しいオンボードプロセス</span><span class="sxs-lookup"><span data-stu-id="0c327-145">New onboarding process</span></span>

<span data-ttu-id="0c327-146">新しいワーカーまたはデータセンター内の新しいサーバーに対して発行された新しい専用オンプレミスのデバイスの場合、ワーカーがサインインすると、OnPremDevices グループ内のデバイスのメンバーシップに基づいた Configuration Manager クライアントは、Windows 10、Microsoft 365 Apps 用アプリ、およびオンプレミス構成マネージャー配布ポイントからのエッジに対する最新の更新プログラムをダウンロードし</span><span class="sxs-lookup"><span data-stu-id="0c327-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="0c327-147">完了すると、専用のオンプレミスデバイスが使用できるようになります。また、これらの配布ポイントを継続的に更新するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c327-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="0c327-148">新しいリモートデバイスが新しい作業者に対して発行されると、そのワーカーが RoamingDevices グループのメンバーシップに基づいてデバイスにサインインすると、Intune cloud service およびその他のサービスに接続し、Windows 10、Microsoft 365 Apps for enterprise、および Edge 用の最新の更新プログラムをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c327-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="0c327-149">完了すると、リモートデバイスは使用できる状態になります。また、インストールされている VPN クライアントを使用して、オンプレミスのリソースにアクセスし、Microsoft 365 ネットワークに更新を継続して実行します。</span><span class="sxs-lookup"><span data-stu-id="0c327-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="0c327-150">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0c327-150">Next step</span></span>

<span data-ttu-id="0c327-151">組織内の[リモートワーカーを](empower-people-to-work-remotely.md)強化します。</span><span class="sxs-lookup"><span data-stu-id="0c327-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
