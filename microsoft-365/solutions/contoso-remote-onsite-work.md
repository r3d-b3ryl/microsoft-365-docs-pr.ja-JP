---
title: Contoso 社の COVID-19 応答とリモートおよびオンサイト作業のサポート
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation が COVID-19 パンデミックに対応し、リモートおよびオンサイト作業用のソフトウェア インストールと更新インフラストラクチャを設計した方法を理解します。
ms.openlocfilehash: 0bded43f03dd529ffdf463818a93af70e10eed89
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028982"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a><span data-ttu-id="88646-103">Contoso 社の COVID-19 応答とリモートおよびオンサイト作業のサポート</span><span class="sxs-lookup"><span data-stu-id="88646-103">Contoso's COVID-19 response and support for remote and onsite work</span></span>

<span data-ttu-id="88646-104">Contoso 社は、常にリモート ワーカーをサポートし、パリ本社の中央 VPN サーバーを介してオンプレミスのリソースにアクセスしました。</span><span class="sxs-lookup"><span data-stu-id="88646-104">Contoso had always supported its remote workers, who accessed on-premises resources through a central VPN server in the Paris headquarters.</span></span> <span data-ttu-id="88646-105">Contoso 社は、すべてのリモート ワーカーに管理対象ラップトップを発行しました。</span><span class="sxs-lookup"><span data-stu-id="88646-105">Contoso had issued all remote workers a managed laptop.</span></span> <span data-ttu-id="88646-106">オンプレミスのワーカーには、デスクトップ コンピューターとラップトップが混じり合っていた。</span><span class="sxs-lookup"><span data-stu-id="88646-106">On-premises workers had a mixture of desktop computers and laptops.</span></span>

## <a name="contosos-response-to-covid-19"></a><span data-ttu-id="88646-107">COVID-19 に対する Contoso の応答</span><span class="sxs-lookup"><span data-stu-id="88646-107">Contoso’s response to COVID-19</span></span>

<span data-ttu-id="88646-108">COVID-19 パンデミックが始め、突然、不可欠な労働者を含むすべてがリモート ワーカーでした。</span><span class="sxs-lookup"><span data-stu-id="88646-108">With the onset of the COVID-19 pandemic, suddenly all but essential workers were remote workers.</span></span> <span data-ttu-id="88646-109">Contoso 社は、従業員を自宅から仕事に移行し、Microsoft 365 クラウド サービスを使用してオンプレミスのリソースへのリモート アクセスとオンラインを通じて主要なアクティビティを実施することで対応しました。</span><span class="sxs-lookup"><span data-stu-id="88646-109">Contoso responded by shifting its workforce to work from home and conduct its primary activities through remote access to on-premises resources and online using Microsoft 365 cloud services.</span></span>

<span data-ttu-id="88646-110">Contoso 社は、既にリモートワークフォースの 25% をサポートするためにパリ本社オフィスにリモート アクセス VPN サーバーを持っていたが、従業員の 90% をサポートするリモート アクセス容量を拡大するために迅速に移行しました。</span><span class="sxs-lookup"><span data-stu-id="88646-110">Contoso had remote access VPN servers in the Paris headquarters office to support the 25% of its already remote workforce, but quickly moved to scale up it's remote access capacity to support 90% of its workforce.</span></span> <span data-ttu-id="88646-111">Contoso 社は、リモート ワーカーが Contoso イントラネットへのアクセスに地域的に近いエントリ ポイントを使用するために、各サテライト オフィスにリモート アクセス VPN サーバーを展開しました。</span><span class="sxs-lookup"><span data-stu-id="88646-111">Contoso deployed remote access VPN servers in each satellite office so that remote workers would use a regionally close entry point for access to the Contoso intranet.</span></span>

<span data-ttu-id="88646-112">Contoso 社は、スプリット トンネリング用のラップトップ、タブレット、およびスマートフォンにインストールされている VPN クライアントの構成を更新し、Office 365 エンドポイントのオプティマイズ セットのトラフィックが VPN 接続をバイパスし、インターネット上で直接送信された。</span><span class="sxs-lookup"><span data-stu-id="88646-112">Contoso also updated the configuration of VPN clients installed on laptops, tablets, and smart phones for split tunneling so that traffic for the Optimize set of Office 365 endpoints bypassed the VPN connection and was sent directly over the internet.</span></span> <span data-ttu-id="88646-113">詳細については、「VPN スプリット トン [ネリングを使用Office 365](../enterprise/microsoft-365-vpn-split-tunnel.md)接続を最適化する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88646-113">For more information, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

<span data-ttu-id="88646-114">パリ本社と各サテライト オフィスに VPN デバイスをインストールした結果の構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="88646-114">Here is the resulting configuration with VPN devices installed in the Paris headquarters and each of the satellite offices.</span></span> 

![Contoso 社の VPN インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

<span data-ttu-id="88646-116">インストールされた VPN クライアントを持つリモート ワーカーは、DNS を使用して地域に最も近いオフィスを検索し、そこにインストールされている VPN デバイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="88646-116">A remote worker with the installed VPN client uses DNS to find the regionally closest office and connects to the VPN device installed there.</span></span> <span data-ttu-id="88646-117">分割トンネリングを使用すると、Microsoft 365 Optimize エンドポイントへのトラフィックは、地域的に最も近い Microsoft 365 ネットワークの場所に直接送信されます。</span><span class="sxs-lookup"><span data-stu-id="88646-117">With split tunneling, traffic to Microsoft 365 Optimize endpoints gets sent directly to the regionally closest Microsoft 365 network location.</span></span> <span data-ttu-id="88646-118">その他のすべてのトラフィックは、VPN 接続を通して VPN デバイスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="88646-118">All other traffic gets sent over the VPN connection to the VPN device.</span></span>

## <a name="contosos-support-for-remote-and-onsite-work"></a><span data-ttu-id="88646-119">Contoso のリモート作業とオンサイト作業のサポート</span><span class="sxs-lookup"><span data-stu-id="88646-119">Contoso’s support for remote and onsite work</span></span>

<span data-ttu-id="88646-120">地域ロックダウン時に主にリモート ワーカーをサポートするために最初の変更が行われた後、Contoso 社は、次のような、リモート作業とオンサイト作業をサポートするインフラストラクチャの変更を行いました。</span><span class="sxs-lookup"><span data-stu-id="88646-120">After the initial changes were made to support mostly remote workers during regional lockdowns, Contoso made infrastructure changes to support remote and onsite work in which a worker could be:</span></span>

- <span data-ttu-id="88646-121">常にリモート。</span><span class="sxs-lookup"><span data-stu-id="88646-121">Always remote.</span></span>
- <span data-ttu-id="88646-122">常にオンサイト。</span><span class="sxs-lookup"><span data-stu-id="88646-122">Always onsite.</span></span>
- <span data-ttu-id="88646-123">オンサイトとリモートの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="88646-123">A combination of onsite and remote.</span></span>

<span data-ttu-id="88646-124">Microsoft 365 ID、セキュリティ、コンプライアンス機能は、ゼロトラスト用に設計され、ユーザーとそのデバイスの場所に関係なく動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="88646-124">Microsoft 365 identity, security, and compliance features are designed for Zero Trust and to work regardless of the location of the user and their device.</span></span> <span data-ttu-id="88646-125">詳細については、「Zero [Trust」を参照してください](https://www.microsoft.com/security/business/zero-trust)。</span><span class="sxs-lookup"><span data-stu-id="88646-125">For more information, see [Zero Trust](https://www.microsoft.com/security/business/zero-trust).</span></span>

<span data-ttu-id="88646-126">ただし、ソフトウェアの新しいインストールと更新プログラムの管理は、インストールするソフトウェアがオンプレミスまたはインターネット ソースから提供される可能性があるため、デバイスの場所に依存します。</span><span class="sxs-lookup"><span data-stu-id="88646-126">However, managing new installs and updates of software is dependent on the location of the device because the software to install could come from an on-premises or an internet source.</span></span> <span data-ttu-id="88646-127">Contoso IT アーキテクトは、ワーカーではなく、デバイスの場所に基づいて新しいインストールと更新インフラストラクチャを設計しました。</span><span class="sxs-lookup"><span data-stu-id="88646-127">Contoso IT architects designed their new installs and updates infrastructure based on the location of the device, rather than the worker.</span></span>

<span data-ttu-id="88646-128">専用のオンプレミスとローミングの 2 種類のデバイスを指定しました。</span><span class="sxs-lookup"><span data-stu-id="88646-128">They designated two types of devices: dedicated on-premises and roaming.</span></span>

### <a name="dedicated-on-premises"></a><span data-ttu-id="88646-129">専用のオンプレミス</span><span class="sxs-lookup"><span data-stu-id="88646-129">Dedicated on-premises</span></span>

<span data-ttu-id="88646-130">専用のオンプレミス デバイスは、Contoso イントラネットから離れたことがないデスクトップまたはサーバー コンピューターであり、VPN クライアントがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="88646-130">A dedicated on-premises device is a desktop or server computer that never leaves the Contoso intranet and does not have a VPN client installed.</span></span> <span data-ttu-id="88646-131">これらのオンプレミス デバイスは、引き続き Microsoft Endpoint Configuration Manager とその配布ポイントを Windows 10、Microsoft 365 Apps for enterprise、Edge ブラウザーのインストールと更新に使用します。</span><span class="sxs-lookup"><span data-stu-id="88646-131">These on-premises devices continue to use Microsoft Endpoint Configuration Manager and its distribution points for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and the Edge browser.</span></span>

### <a name="roaming"></a><span data-ttu-id="88646-132">ローミング</span><span class="sxs-lookup"><span data-stu-id="88646-132">Roaming</span></span>

<span data-ttu-id="88646-133">ローミング デバイスは Contoso イントラネットから離れ、Contoso VPN クライアントがインストールされたスマートフォンやタブレットなど、多くのオフィス ワーカーとすべてのリモート ワーカー、その他の組織が所有するデバイスに発行されたラップトップを含む場合があります。</span><span class="sxs-lookup"><span data-stu-id="88646-133">A roaming device can leave the Contoso intranet and includes laptops issued to many office workers and all remote workers and other organization-owned devices such as smart phones and tablets with the Contoso VPN client installed.</span></span> 

<span data-ttu-id="88646-134">これらのデバイスは、いつでもインターネットに接続できるので、Windows 10、Microsoft 365 Apps for enterprise、および Edge のインストールと更新に Intune または他のクラウドベースのサービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="88646-134">Because these devices can be connected to the Internet at any given time, they use Intune or other cloud-based services for installs and updates of Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="88646-135">既存のオンプレミスの Configuration Manager 配布ポイントは使用しない。</span><span class="sxs-lookup"><span data-stu-id="88646-135">They do not use the existing on-premises Configuration Manager distribution points.</span></span>

<span data-ttu-id="88646-136">つまり、ローミング デバイスのインストールと更新の一部は、オンプレミスでイントラネットに接続されている間、インターネット上で行われます。</span><span class="sxs-lookup"><span data-stu-id="88646-136">This means some of the installs and updates for roaming device will be done over the internet while they are on-premises and connected to the intranet.</span></span> <span data-ttu-id="88646-137">しかし、Contoso IT アーキテクトは、特にほとんどのリモート ワーカーがイントラネットにほとんど接続されていない場合、インターネットへのイントラネット帯域幅の最適化よりも、構成の簡素化が重要だと決定しました。</span><span class="sxs-lookup"><span data-stu-id="88646-137">But Contoso IT architects decided that simplicity of configuration was more important than optimization of intranet bandwidth to the internet, especially when most remote workers are seldom connected to the intranet.</span></span>

<span data-ttu-id="88646-138">結果のインフラストラクチャを次に示します。</span><span class="sxs-lookup"><span data-stu-id="88646-138">Here is the resulting infrastructure.</span></span>

![Contoso 社のインストールと更新インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

<span data-ttu-id="88646-140">インストールと更新の動作は、デバイスのコンピューター アカウントを次のいずれかのグループのメンバーにすることで決まります。</span><span class="sxs-lookup"><span data-stu-id="88646-140">Install and update behavior is determined by making the computer accounts of devices a member of one of these groups:</span></span>

- <span data-ttu-id="88646-141">OnPremDevices</span><span class="sxs-lookup"><span data-stu-id="88646-141">OnPremDevices</span></span>

  <span data-ttu-id="88646-142">デバイス上の Configuration Manager クライアントは、インストールと更新に配布ポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="88646-142">The Configuration Manager client on the device uses distribution points for installs and updates.</span></span>

- <span data-ttu-id="88646-143">RoamingDevices</span><span class="sxs-lookup"><span data-stu-id="88646-143">RoamingDevices</span></span>

  <span data-ttu-id="88646-144">Intune およびデバイス上の他の設定では、インストールと更新に Microsoft 365 ネットワークを使用する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="88646-144">Intune and other settings on the device specify the use of the Microsoft 365 network for installs and updates.</span></span>

## <a name="new-onboarding-process"></a><span data-ttu-id="88646-145">新しいオンボーディング プロセス</span><span class="sxs-lookup"><span data-stu-id="88646-145">New onboarding process</span></span>

<span data-ttu-id="88646-146">新しいワーカーまたはデータセンター内の新しいサーバーに発行された新しい専用のオンプレミス デバイスの場合、ワーカーがサインインすると、OnPremDevices グループのデバイスのメンバーシップに基づいて Configuration Manager クライアントは、Windows 10、Microsoft 365 Apps for enterprise、および Edge の最新の更新プログラムをオンプレミス構成マネージャー配布ポイントからダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="88646-146">For a new dedicated on-premises device issued to a new worker or for a new server in a datacenter, when the worker signs in, the Configuration Manager client based on the device's membership in the OnPremDevices group downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge from on-premises Configuration Manager distribution points.</span></span> <span data-ttu-id="88646-147">完了すると、専用のオンプレミス デバイスを使用する準備が整い、これらの配布ポイントを継続的な更新に使用します。</span><span class="sxs-lookup"><span data-stu-id="88646-147">When complete, the dedicated on-premises device is ready for use and uses these distribution points for ongoing updates.</span></span>

<span data-ttu-id="88646-148">新しいワーカーに発行された新しいリモート デバイスの場合、ワーカーがサインインすると、デバイスは RoamingDevices グループのメンバーシップに基づいて Intune クラウド サービスや他のサービスに連絡し、Windows 10、Microsoft 365 Apps for enterprise、Edge の最新の更新プログラムをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="88646-148">For a new remote device issued to a new worker, when the worker signs in, the device, based on its membership in the RoamingDevices group, contacts the Intune cloud service and other services and downloads and installs the latest updates for Windows 10, Microsoft 365 Apps for enterprise, and Edge.</span></span> <span data-ttu-id="88646-149">完了すると、リモート デバイスを使用する準備が整い、インストールされた VPN クライアントを使用してオンプレミスのリソースにアクセスし、継続的な更新のために Microsoft 365 ネットワークを使用します。</span><span class="sxs-lookup"><span data-stu-id="88646-149">When complete, the remote device is ready for use and uses the installed VPN client for access to on-premises resources and the Microsoft 365 network for ongoing updates.</span></span>

## <a name="next-step"></a><span data-ttu-id="88646-150">次の手順</span><span class="sxs-lookup"><span data-stu-id="88646-150">Next step</span></span>

<span data-ttu-id="88646-151">[組織内のリモート ワーカーに](empower-people-to-work-remotely.md) 権限を与える。</span><span class="sxs-lookup"><span data-stu-id="88646-151">[Empower the remote workers](empower-people-to-work-remotely.md) in your organization.</span></span>
