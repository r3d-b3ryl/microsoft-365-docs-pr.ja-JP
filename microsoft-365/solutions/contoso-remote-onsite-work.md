---
title: Contoso の COVID-19 応答とハイブリッド作業のサポート
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso Corporation が COVID-19 のパンデミックにどのように対応し、ハイブリッド作業のためにソフトウェアのインストールと更新インフラストラクチャを設計したかを理解します。
ms.openlocfilehash: 8b3829b7d3361c3a29ee495dd5a335a28a08c0b4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325727"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contoso の COVID-19 応答とハイブリッド作業のサポート

Contoso は、パリ本社の中央 VPN サーバーを介してオンプレミスリソースにアクセスするリモート ワーカーを常にサポートしていました。 Contoso は、すべてのリモート ワーカーにマネージド ノート PC を発行していました。 オンプレミスのワーカーには、デスクトップ コンピューターとノート PC が混在していました。

## <a name="contosos-response-to-covid-19"></a>COVID-19 に対する Contoso の応答

COVID-19 パンデミックが発生すると、突然、不可欠なワーカー以外はすべてリモート ワーカーでした。 Contoso は、従業員を自宅から仕事に移行し、オンプレミスのリソースにリモート アクセスし、クラウド サービスを使用してオンラインで主要なアクティビティMicrosoft 365実施することで対応しました。

Contoso は、既にリモートワークフォースの 25% をサポートするために、パリ本社オフィスにリモート アクセス VPN サーバーを持っていましたが、すぐに移動してリモート アクセス容量をスケールアップし、従業員の 90% をサポートしました。 Contoso は、リモート ワーカーが Contoso イントラネットへのアクセスに地域的に近いエントリ ポイントを使用できるように、各サテライト オフィスにリモート アクセス VPN サーバーをデプロイしました。

Contoso はまた、分割トンネリング用にラップトップ、タブレット、スマートフォンにインストールされている VPN クライアントの構成を更新し、Office 365 エンドポイントの最適化セットのトラフィックが VPN 接続をバイパスし、インターネット経由で直接送信されるようにしました。 詳細については、「[VPN 分割トンネリングを使用してリモート ユーザーの接続Office 365最適化する](../enterprise/microsoft-365-vpn-split-tunnel.md)」を参照してください。

パリ本社と各サテライト オフィスに VPN デバイスがインストールされた構成を次に示します。 

![Contoso の VPN インフラストラクチャ。](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

インストールされている VPN クライアントを持つリモート ワーカーは、DNS を使用して、地域に最も近いオフィスを検索し、そこにインストールされている VPN デバイスに接続します。 分割トンネリングでは、Microsoft 365最適化エンドポイントへのトラフィックは、リージョン内で最も近いMicrosoft 365ネットワークの場所に直接送信されます。 その他のすべてのトラフィックは、VPN 接続経由で VPN デバイスに送信されます。

## <a name="contosos-support-for-hybrid-work"></a>ハイブリッド作業に対する Contoso のサポート

地域のロックダウン中に主にリモート ワーカーをサポートするように最初の変更が加えられた後、Contoso は、ワーカーが次の可能性があるハイブリッド作業をサポートするためにインフラストラクチャを変更しました。

- 常にリモート。
- 常にオンサイト。
- オンサイトとリモートの組み合わせ。

Microsoft 365 ID、セキュリティ、およびコンプライアンス機能は、ユーザーとそのデバイスの場所に関係なく、ゼロ トラストおよび動作するように設計されています。 詳細については、「[ゼロ トラスト](https://www.microsoft.com/security/business/zero-trust)」を参照してください。

ただし、ソフトウェアの新しいインストールと更新プログラムの管理は、インストールするソフトウェアがオンプレミスまたはインターネット ソースから提供される可能性があるため、デバイスの場所によって異なります。 Contoso IT アーキテクトは、ワーカーではなく、デバイスの場所に基づいて新しいインストールと更新インフラストラクチャを設計しました。

専用のオンプレミスとローミングの 2 種類のデバイスを指定しました。

### <a name="dedicated-on-premises"></a>オンプレミス専用

専用のオンプレミス デバイスは、Contoso イントラネットから離れることがなく、VPN クライアントがインストールされていないデスクトップまたはサーバー コンピューターです。 これらのオンプレミス デバイスは、Windows 10、Microsoft 365 Apps for enterprise、および Edge ブラウザーのインストールと更新にMicrosoft Endpoint Configuration Managerとその配布ポイントを引き続き使用します。

### <a name="roaming"></a>ローミング

ローミング デバイスは Contoso イントラネットから離れることができ、Contoso VPN クライアントがインストールされたスマートフォンやタブレットなどの、多くのオフィス ワーカーやすべてのリモート ワーカー、その他の組織所有のデバイスに発行されたノート PC が含まれます。 

これらのデバイスは任意の時点でインターネットに接続できるため、Windows 10、Microsoft 365 Apps for enterprise、および Edge のインストールと更新には、Intuneまたはその他のクラウドベースのサービスが使用されます。 既存のオンプレミスConfiguration Manager配布ポイントは使用しません。

つまり、ローミング デバイスのインストールと更新の一部は、オンプレミスでイントラネットに接続されている間にインターネット経由で行われます。 しかし、Contoso IT アーキテクトは、インターネットへのイントラネット帯域幅の最適化よりも構成のシンプルさが重要であると判断しました。特に、ほとんどのリモート ワーカーがイントラネットに接続されにくい場合です。

結果として得られるインフラストラクチャを次に示します。

![Contoso のインフラストラクチャのインストールと更新。](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

インストールと更新の動作は、デバイスのコンピューター アカウントを次のいずれかのグループのメンバーにすることで決定されます。

- OnPremDevices

  デバイス上のConfiguration Manager クライアントは、インストールと更新に配布ポイントを使用します。

- RoamingDevices

  デバイス上のIntuneおよびその他の設定では、インストールと更新にMicrosoft 365 ネットワークの使用を指定します。

## <a name="new-onboarding-process"></a>新しいオンボード プロセス

新しいワーカーまたはデータセンター内の新しいサーバーに対して発行された新しい専用オンプレミス デバイスの場合、ワーカーがサインインすると、OnPremDevices グループのデバイスのメンバーシップに基づいてConfiguration Manager クライアントがダウンロードされ、Windows 10用の最新の更新プログラムがインストールMicrosoft 365 Apps for enterprise、およびオンプレミスのConfiguration Manager配布ポイントからのエッジ。 完了すると、専用のオンプレミス デバイスを使用する準備が整い、これらの配布ポイントを継続的な更新に使用します。

新しいワーカーに発行された新しいリモート デバイスの場合、ワーカーがサインインすると、RoamingDevices グループのメンバーシップに基づいてデバイスがIntuneクラウド サービスやその他のサービスに接続し、Windows 10、Microsoft 365 Apps for enterprise、および Edge の最新の更新プログラムをダウンロードしてインストールします。 完了すると、リモート デバイスを使用する準備が整い、インストールされている VPN クライアントを使用して、オンプレミス のリソースとMicrosoft 365 ネットワークにアクセスし、継続的な更新を行います。

## <a name="next-step"></a>次の手順

組織内[でハイブリッド作業用のインフラストラクチャを設定](empower-people-to-work-remotely.md)します。
