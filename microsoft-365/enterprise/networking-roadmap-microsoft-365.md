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
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365 のネットワークロードマップ

Microsoft 365 enterprise には、コラボレーションと生産性のクラウドサービス、Microsoft Intune、および Microsoft Azure の id およびセキュリティサービスが多数含まれています。 これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。 これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。 

Microsoft 365 オンボードの重要な部分は、ネットワークとインターネット接続が最適なアクセスのためにセットアップされていることを確認することです。 グローバルに分散されたソフトウェア (SaaS) クラウドにアクセスするようにオンプレミスネットワークを構成することは、社内データセンターへのトラフィック用に最適化された従来のネットワークや中央のインターネット接続とは異なります。 

以下の記事を活用して主な違いを理解し、エッジ デバイス、クライアント コンピューター、オンプレミス ネットワークを変更して、オンプレミス ユーザーの最高のパフォーマンスを引き出します。

## <a name="plan"></a>プラン

ネットワーク実装の計画段階で、次の手順を実行します。

- [Microsoft 365 ネットワークのしくみを理解する](microsoft-365-networking-overview.md)
- [現在のネットワーク接続を評価する](assessing-network-connectivity.md)
- [ExpressRoute が組織に適しているかどうかを判断する](network-planning-with-expressroute.md)
- [ネットワークデバイスの計画](plan-for-network-devices.md)
- [移行のためにネットワークをセットアップする](network-and-migration-planning.md)

## <a name="deploy"></a>展開

ネットワーク実装の展開フェーズで、次の手順を実行します。

- [エンタープライズネットワークが Microsoft 365 接続用に最適化されていることを確認する](set-up-network-for-microsoft-365.md)
- [組織の DNS ドメインを追加する](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
- [Microsoft 365 エンドポイントへの接続を最適化する](microsoft-365-ip-web-service.md)
- [リモートワーカーの接続を最適化する](microsoft-365-vpn-split-tunnel.md)
- 必要に応じて、 [ExpressRoute を構成](azure-expressroute.md)します。

## <a name="manage"></a>管理

ネットワーク実装の管理段階で、次の手順を実行します。

- [ネットワークデバイスが最新の Office 365 エンドポイントを使用していることを確認する](microsoft-365-endpoints.md)
- [ネットワークのパフォーマンスを監視および調整する](network-planning-and-performance.md)
- [ExpressRoute 接続を監視する](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>ネットワーク機器ベンダー

ネットワーク機器ベンダーの場合は、 [Microsoft 365 ネットワークパートナープログラム](microsoft-365-networking-partner-program.md)に参加してください。 Microsoft 365 ネットワーク接続の原則を製品とソリューションに構築するために、プログラムに登録します。 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso 社が Microsoft 365 に接続する方法

架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[Microsoft 365 ネットワーク接続の概要](microsoft-365-networking-overview.md)を使用して、ネットワークの計画を開始します。
