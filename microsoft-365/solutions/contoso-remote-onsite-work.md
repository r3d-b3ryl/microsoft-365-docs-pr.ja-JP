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
ms.openlocfilehash: 8e25b399d7acd2cb3486283623d29315eac9491e
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371759"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Contoso 社の COVID-19 の応答と、リモートおよびオンサイト作業のサポート

Contoso 社では、常にリモートワーカーをサポートしており、パリ本社の中央 VPN サーバーを介してオンプレミスのリソースにアクセスしました。 Contoso 社は、すべてのリモートワーカーに管理されたラップトップを発行しました。 オンプレミスのワーカーは、デスクトップコンピューターとラップトップを混在させることができました。

## <a name="contosos-response-to-covid-19"></a>COVID に対する Contoso の応答

COVID-19 pandemic が始まっている状態では、突然、重要なワーカーはリモートワーカーでした。 Contoso 社は、従業員を在宅勤務に移行させることによって反応し、Microsoft 365 cloud services を使用してオンプレミスのリソースへのリモートアクセスを通じて主な活動を実施しています。

Contoso 社では、既にリモートで作業している従業員の25% をサポートするために、パリ本社オフィスにリモートアクセス VPN サーバーがありましたが、迅速に移行することにより、そのリモートアクセスのキャパシティを拡大して、90% の人員をサポートしていました。 Contoso 社は、リモートアクセス VPN サーバーを各サテライトオフィスに展開して、リモートワーカーが Contoso イントラネットにアクセスするために地域的 close エントリポイントを使用するようにしました。

Contoso 社は、分割トンネリング用のラップトップ、タブレット、スマートフォンにインストールされている VPN クライアントの構成も更新して、Office 365 エンドポイントの最適化セットのトラフィックが VPN 接続をバイパスしてインターネット上で直接送信されるようにしました。 詳細については、「 [VPN 分割トンネリングを使用してリモートユーザー用に Office 365 接続を最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」を参照してください。

これは、パリ本社および各サテライトオフィスにインストールされた VPN デバイスを使用した構成の結果です。 

![Contoso 社の VPN インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

VPN クライアントがインストールされているリモートワーカーは、DNS を使用して地域的の最も近い office を検索し、そこにインストールされている VPN デバイスに接続します。 分割トンネリングでは、Microsoft 365 の最適化エンドポイントへのトラフィックは、地域的に最も近い Microsoft 365 のネットワークの場所に直接送信されます。 他のすべてのトラフィックは、vpn デバイスへの VPN 接続を介して送信されます。

## <a name="contosos-support-for-remote-and-onsite-work"></a>Contoso 社のリモートおよびオンサイト作業のサポート

地域ロックダウン時にほとんどのリモートワーカーをサポートするように初期変更を行った後、Contoso 社は、次のような作業を行うことができる、リモートおよびオンサイトの作業をサポートするインフラストラクチャの変更を行いました。

- 常にリモート。
- 常にオンプレミス。
- リモートとオンプレミスの組み合わせ。

Microsoft 365 の id、セキュリティ、およびコンプライアンス機能は、信頼度がゼロになるように設計されており、ユーザーとデバイスの場所に関係なく動作します。 詳細については、「 [ゼロ信頼](https://www.microsoft.com/security/business/zero-trust)」を参照してください。

ただし、インストールするソフトウェアは社内またはインターネットソースから入手できるため、ソフトウェアの新規インストールと更新プログラムの管理はデバイスの場所によって異なります。 Contoso 社の IT アーキテクトは、新しいインストールを設計し、ワーカーではなくデバイスの場所に基づいてインフラストラクチャを更新します。

これらは、オンプレミスとローミングの2種類のデバイスを指定していました。

### <a name="dedicated-on-premises"></a>専用オンプレミス

専用のオンプレミスデバイスは、Contoso イントラネットから離れたままで、VPN クライアントがインストールされていないデスクトップまたはサーバーコンピューターです。 これらのオンプレミスデバイスは、Microsoft エンドポイント構成マネージャーとその配布ポイントを引き続き使用して、Windows 10、Microsoft 365 Apps for enterprise、エッジブラウザーをインストールします。

### <a name="roaming"></a>節約

ローミングデバイスは Contoso イントラネットを離れることができ、多くの office ワーカーと、Contoso VPN クライアントがインストールされているスマートフォンやタブレットなどのすべてのリモートワーカーとその他の組織所有のデバイスに対して発行されたラップトップを含んでいます。 

これらのデバイスは、いつでもインターネットに接続できるため、Intune またはその他のクラウドベースのサービスを使用して、Windows 10、Microsoft 365 Apps for enterprise、および Edge をインストールします。 これらのユーザーは、既存のオンプレミス構成マネージャーの配布ポイントを使用しません。

これは、ローミングデバイスのインストールと更新が、オンプレミスの間にインターネット経由で行われ、イントラネットに接続されることを意味します。 しかし、Contoso 社の IT アーキテクトは、イントラネットの帯域幅をインターネットに最適化するよりも構成の簡略化が重要であると判断しました。特に、ほとんどのリモートワーカーがほとんどの場合、イントラネットに接続されていない場合。

最終的なインフラストラクチャは次のとおりです。

![Contoso 社のインストールおよび更新インフラストラクチャ](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

インストールと更新の動作は、デバイスのコンピューターアカウントをこれらのグループのいずれかのメンバーにすることによって決まります。

- OnPremDevices

  デバイス上の Configuration Manager クライアントは、配布ポイントを使用してインストールと更新を行います。

- RoamingDevices

  デバイス上の Intune およびその他の設定は、インストールと更新に Microsoft 365 ネットワークの使用を指定します。

## <a name="new-onboarding-process"></a>新しいオンボードプロセス

新しいワーカーまたはデータセンター内の新しいサーバーに対して発行された新しい専用オンプレミスのデバイスの場合、ワーカーがサインインすると、OnPremDevices グループ内のデバイスのメンバーシップに基づいた Configuration Manager クライアントは、Windows 10、Microsoft 365 Apps 用アプリ、およびオンプレミス構成マネージャー配布ポイントからのエッジに対する最新の更新プログラムをダウンロードし 完了すると、専用のオンプレミスデバイスが使用できるようになります。また、これらの配布ポイントを継続的に更新するために使用します。

新しいリモートデバイスが新しい作業者に対して発行されると、そのワーカーが RoamingDevices グループのメンバーシップに基づいてデバイスにサインインすると、Intune cloud service およびその他のサービスに接続し、Windows 10、Microsoft 365 Apps for enterprise、および Edge 用の最新の更新プログラムをダウンロードしてインストールします。 完了すると、リモートデバイスは使用できる状態になります。また、インストールされている VPN クライアントを使用して、オンプレミスのリソースにアクセスし、Microsoft 365 ネットワークに更新を継続して実行します。

## <a name="next-step"></a>次の手順

組織内の[リモートワーカーを](empower-people-to-work-remotely.md)強化します。
