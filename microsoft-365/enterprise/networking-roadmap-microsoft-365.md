---
title: Microsoft 365のネットワーク ロードマップ
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 03/03/2022
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ネットワークの計画、実装、および管理に関するロードマップMicrosoft 365。
ms.openlocfilehash: cfefd668f91eb074259d056b3b573b9c0f636bb6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325195"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Microsoft 365のネットワーク ロードマップ

企業向けのMicrosoft 365には、コラボレーションと生産性の高いクラウド サービス、Microsoft Intune、Microsoft Azureの多くの ID およびセキュリティ サービスが含まれます。 これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。 これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。

Microsoft 365オンボードの重要な部分は、ネットワークとインターネット接続が最適化されたアクセス用に設定されていることを確認することです。 グローバルに分散されたサービスとしてのソフトウェア (SaaS) クラウドにアクセスするようにオンプレミス ネットワークを構成することは、オンプレミスデータセンターへのトラフィックと中央インターネット接続用に最適化された従来のネットワークとは異なります。

以下の記事を活用して主な違いを理解し、エッジ デバイス、クライアント コンピューター、オンプレミス ネットワークを変更して、オンプレミス ユーザーの最高のパフォーマンスを引き出します。

## <a name="plan"></a>計画

ネットワーク実装の計画フェーズでは、次の手順を実行します。

- [Microsoft 365ネットワークのしくみを理解する](microsoft-365-networking-overview.md)
- [ネットワーク接続の原則について学習する](microsoft-365-network-connectivity-principles.md)
- [現在のネットワーク接続を評価する](assessing-network-connectivity.md)
- [ExpressRoute が組織に適しているかどうかを判断する](network-planning-with-expressroute.md)
- [ネットワーク デバイスの計画](plan-for-network-devices.md)
- [移行用にネットワークを設定する](network-and-migration-planning.md)

## <a name="deploy"></a>展開

ネットワーク実装のデプロイ フェーズでは、次の手順を実行します。

- [エンタープライズ ネットワークがMicrosoft 365接続用に最適化されていることを確認する](set-up-network-for-microsoft-365.md)
- [組織の DNS ドメインを追加する](../admin/setup/add-domain.md)
- [VPN 分割トンネリングを使用してリモート ワーカーの接続を最適化する](microsoft-365-vpn-split-tunnel.md)
- [ネットワーク パフォーマンスを向上させるためにCDNを構成する](office-365-cdn-quickstart.md)
- [Microsoft 365 エンドポイントへの接続を最適化する](microsoft-365-ip-web-service.md)
- 必要に応じて [、ExpressRoute を構成する](azure-expressroute.md)

## <a name="manage"></a>管理

ネットワーク実装の管理フェーズでは、次の手順を実行します。

- [Microsoft 365ネットワーク接続テスト ツールを使用したテストと最適化](office-365-network-mac-perf-onboarding-tool.md)
- [ネットワーク デバイスが最新のOffice 365 エンドポイントを使用していることを確認する](microsoft-365-endpoints.md)
- [ネットワークのパフォーマンスを監視して調整する](network-planning-and-performance.md)
- [Microsoft 365接続を監視する](monitor-connectivity.md)

## <a name="network-equipment-vendors"></a>ネットワーク機器ベンダー

ネットワーク機器ベンダーの場合は、Microsoft 365 ネットワーク パートナー プログラムに参加[します](microsoft-365-networking-partner-program.md)。 プログラムに登録して、Microsoft 365ネットワーク接続の原則を製品とソリューションに組み込む。

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Contoso がMicrosoft 365のネットワークをどのように行ったか

架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。

![Contoso Corporation。](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

[ネットワーク接続の概要をMicrosoft 365して、ネットワーク計画を](microsoft-365-networking-overview.md)開始します。
