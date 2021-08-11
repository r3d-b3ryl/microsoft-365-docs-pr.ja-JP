---
title: ネットワークのロードマップ (Microsoft 365
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
description: ネットワークを実装するためのロードマップMicrosoft 365です。
ms.openlocfilehash: 7c8c67305ef67e9e7a20b2d341f339b8bdbab4090426861e37b5b5277bb249e7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800983"
---
# <a name="networking-roadmap-for-microsoft-365"></a>ネットワークのロードマップ (Microsoft 365

Microsoft 365には、コラボレーションと生産性のクラウド サービス、Microsoft Intune、多数の ID およびセキュリティ サービスが含Microsoft Azure。 これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。 これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。 

オンボーディングの重要なMicrosoft 365は、ネットワークとインターネット接続が最適化されたアクセス用にセットアップされている必要があります。 グローバルに分散された Software-as-a-Service (SaaS) クラウドにアクセスするためのオンプレミス ネットワークの構成は、オンプレミスデータセンターへのトラフィックと中央インターネット接続用に最適化された従来のネットワークとは異なります。 

以下の記事を活用して主な違いを理解し、エッジ デバイス、クライアント コンピューター、オンプレミス ネットワークを変更して、オンプレミス ユーザーの最高のパフォーマンスを引き出します。

## <a name="plan"></a>計画

ネットワーク実装の計画フェーズでは、次の処理を行います。

- [ネットワークのしくみMicrosoft 365理解する](microsoft-365-networking-overview.md)
- [現在のネットワーク接続を評価する](assessing-network-connectivity.md)
- [ExpressRoute が組織に適切かどうかを判断する](network-planning-with-expressroute.md)
- [ネットワーク デバイスの計画](plan-for-network-devices.md)
- [移行用にネットワークをセットアップする](network-and-migration-planning.md)

## <a name="deploy"></a>展開

ネットワーク実装の展開フェーズでは、次の手順を実行します。

- [エンタープライズ ネットワークがネットワーク接続用に最適化Microsoft 365確認する](set-up-network-for-microsoft-365.md)
- [組織の DNS ドメインを追加する](../admin/setup/add-domain.md)
- [エンドポイントへの接続をMicrosoft 365する](microsoft-365-ip-web-service.md)
- [リモート ワーカーの接続を最適化する](microsoft-365-vpn-split-tunnel.md)
- 必要に応じて [、ExpressRoute を構成する](azure-expressroute.md)

## <a name="manage"></a>管理

ネットワーク実装の管理フェーズでは、次の処理を行います。

- [ネットワーク デバイスが最新のエンドポイントを使用Office 365する](microsoft-365-endpoints.md)
- [ネットワークパフォーマンスの監視と調整](network-planning-and-performance.md)
- [ExpressRoute 接続を監視する](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>ネットワーク機器ベンダー

ネットワーク機器ベンダーの場合は、ネットワーク機器ベンダーに[Microsoft 365 ネットワーク パートナー プログラム。](microsoft-365-networking-partner-program.md) プログラムに登録して、ネットワークMicrosoft 365原則を製品とソリューションに組み込みます。 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso 社がネットワークを使用してネットワークをMicrosoft 365

架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

ネットワーク接続の概要を使用して[、Microsoft 365計画を開始します](microsoft-365-networking-overview.md)。