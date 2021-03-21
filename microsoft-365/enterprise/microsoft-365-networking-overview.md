---
title: Microsoft 365 ネットワーク接続の概要
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: SaaS サービスにとってネットワークの最適化が重要である理由、Microsoft 365 ネットワークの目標、および SaaS が他のワークロードとは異なるネットワークを必要とする方法について説明します。
ms.openlocfilehash: d1a2b79f6e4042b97ec5a31d0ff92175baa1218e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923184"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 ネットワーク接続の概要

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 は、さまざまなマイクロ サービスとアプリケーションのセットを通じて生産性とコラボレーションシナリオを提供する、分散されたサービスとしてのソフトウェア (SaaS) クラウドです。 Outlook、Word、PowerPoint などの Microsoft 365 のクライアント コンポーネントは、ユーザー コンピューター上で実行され、Microsoft データセンターで実行される Microsoft 365 の他のコンポーネントに接続します。 Microsoft 365 エンド ユーザー エクスペリエンスの品質を決定する最も重要な要因は、Microsoft 365 クライアントと Microsoft 365 サービス フロント ドア間のネットワークの信頼性と低遅延です。

この記事では、Microsoft 365 ネットワークの目標と、Microsoft 365 ネットワークが一般的なインターネット トラフィックとは異なる最適化方法を必要とする理由について説明します。

## <a name="microsoft-365-networking-goals"></a>Microsoft 365 ネットワークの目標

Microsoft 365 ネットワークの最終的な目標は、クライアントと最も近い Microsoft 365 エンドポイント間の制限の少ないアクセスを有効にすることで、エンド ユーザー エクスペリエンスを最適化します。 エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。 たとえば、Microsoft Teams は低遅延に依存して、ユーザーの電話、会議、共有画面のコラボレーションがグリッチフリーであり、Outlook はサーバー側のインデックス作成機能と AI 機能を活用するインスタント検索機能のネットワーク接続に大きな依存しています。

ネットワーク設計の主な目標は、クライアント コンピューターから Microsoft Global Network への往復時間 (RTT) を短縮することで、待ち時間を最小限に抑え、Microsoft のすべてのデータセンターを低遅延で相互接続する Microsoft のパブリック ネットワーク バックボーンで、世界中に広がる高可用性クラウド アプリケーション エントリ ポイントです。 [Microsoft の高速で信頼性の高いグローバル ネットワーク構築方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) については、Microsoft のグローバル ネットワークの詳細を参照してください。

Microsoft 365 ネットワークパフォーマンスの最適化は複雑である必要はありません。 次の主要な原則に従って、可能な限り最高のパフォーマンスを得る方法があります。

- Microsoft 365 ネットワーク トラフィックの識別
- ユーザーが Microsoft 365 に接続する各場所からインターネットへの Microsoft 365 ネットワーク トラフィックのローカル ブランチ出力を許可する
- Microsoft 365 トラフィックによるプロキシとパケット検査デバイスのバイパスを許可する

Microsoft 365 ネットワーク接続の原則の詳細については [、「Microsoft 365 Network Connectivity Principles」を参照してください](microsoft-365-network-connectivity-principles.md)。

## <a name="traditional-network-architectures-and-saas"></a>従来のネットワーク アーキテクチャと SaaS

クライアント/サーバー ワークロードの従来のネットワーク アーキテクチャ原則は、クライアントとエンドポイント間のトラフィックが企業のネットワーク境界外に広がらないという前提に基づいて設計されています。 また、多くのエンタープライズ ネットワークでは、すべての送信インターネット接続が企業ネットワークを通過し、中央の場所から出力されます。

従来のネットワーク アーキテクチャでは、一般的なインターネット トラフィックの待機時間が長いほど、ネットワーク境界のセキュリティを維持するために必要なトレードオフであり、インターネット トラフィックのパフォーマンスの最適化には、通常、ネットワーク出力ポイントで機器をアップグレードまたはスケール アウトする必要があります。 ただし、この方法では、Microsoft 365 などの SaaS サービスの最適なネットワーク パフォーマンスに関する要件には対応していない。

## <a name="identifying-microsoft-365-network-traffic"></a>Microsoft 365 ネットワーク トラフィックの識別

Microsoft 365 ネットワーク トラフィックの識別を容易にし、ネットワーク ID の管理を簡単にします。

- 高度に重要なネットワーク トラフィックとインターネット遅延の影響を受けないネットワーク トラフィックを区別する新しいカテゴリのネットワーク エンドポイント。 最も重要な "最適化" カテゴリには、ほんの一握りの URL とサポート IP アドレスがあります。
- スクリプトの使用、または Microsoft 365 ネットワーク識別の直接デバイス構成および変更管理のための Web サービス。 変更は、Web サービス、RSS 形式、または Microsoft Flow テンプレートを使用した電子メールから利用できます。
- [Office 365 ネットワーク](./microsoft-365-networking-partner-program.md) 接続の原則に従い、簡単な構成を持つデバイスまたはサービスを提供する Microsoft パートナーと 365 ネットワーク パートナー プログラムを提供します。

## <a name="securing-microsoft-365-connections"></a>Microsoft 365 接続のセキュリティ保護

従来のネットワーク セキュリティの目標は、侵入および悪意のある脅威に対して企業のネットワーク境界を強化することです。 ほとんどのエンタープライズ ネットワークでは、プロキシ サーバー、ファイアウォール、SSL ブレーク アンド インスペクション、ディープ パケット インスペクション、データ損失防止システムなどのテクノロジを使用して、インターネット トラフィックのネットワーク セキュリティを適用します。 これらのテクノロジは、一般的なインターネット要求の重要なリスクを軽減しますが、Microsoft 365 のエンドポイントに適用すると、パフォーマンス、スケーラビリティ、エンドユーザー エクスペリエンスの品質が大幅に落ちることがあります。

Microsoft 365 は、Microsoft 365 の機能とワークロード専用に設計された組み込みのセキュリティ機能とガバナンス機能を使用して、コンテンツ セキュリティとデータ使用コンプライアンスに関する組織のニーズを満たすのに役立ちます。 Microsoft 365 のセキュリティとコンプライアンスの詳細については、「Office [365](/office365/securitycompliance/security-roadmap)セキュリティ ロードマップ」を参照してください。 Microsoft 365 トラフィックで高度なレベルの処理を実行する高度なネットワーク ソリューションに関する Microsoft の推奨事項とサポートの位置の詳細については [、「36 Office 5](https://support.microsoft.com/help/2690045)トラフィックでサード パーティ製のネットワーク デバイスまたはソリューションを使用する」を参照してください。

## <a name="why-is-microsoft-365-networking-different"></a>Microsoft 365 ネットワークが異なる理由

Microsoft 365 は、エンドポイント セキュリティと暗号化されたネットワーク接続を使用して最適なパフォーマンスを実現するように設計され、境界セキュリティの適用の必要性を軽減します。 Microsoft 365 データセンターは世界中にあり、このサービスは、クライアントを最適なサービス エンドポイントに接続するためにさまざまな方法を使用するように設計されています。 ユーザー データと処理は多くの Microsoft データセンター間で分散されますので、クライアント コンピューターが接続できる単一のネットワーク エンドポイントはありません。 実際、Microsoft 365 テナントのデータとサービスは、エンド ユーザーがアクセスする地理的な場所に合わせて、Microsoft グローバル ネットワークによって動的に最適化されています。

Microsoft 365 トラフィックがパケットインスペクションと集中出力の対象となる場合、一般的なパフォーマンスに関する一般的な問題が発生します。

- 待ち時間が長い場合、ビデオおよびオーディオ ストリームのパフォーマンスが非常に低下し、データ取得、検索、リアルタイムコラボレーション、予定表の空き時間情報、製品内コンテンツ、その他のサービスの応答が遅くなる可能性があります。
- 中央の場所からの接続を出力すると、Microsoft 365 グローバル ネットワークの動的ルーティング機能が強化され、待機時間とラウンドトリップ時間が増加します。
- SSL セキュリティで保護された Microsoft 365 ネットワーク トラフィックを復号化して再暗号化すると、プロトコル エラーが発生し、セキュリティ リスクが発生する可能性があります。

クライアント トラフィックが地理的な場所に可能な限り近い位置に送信できるようにして、ネットワーク パスを Microsoft 365 エントリ ポイントに短縮すると、Microsoft 365 の接続パフォーマンスとエンド ユーザー エクスペリエンスが向上します。 また、Microsoft 365 のパフォーマンスと信頼性に対するネットワーク アーキテクチャの将来の変更による影響を軽減するのにも役立ちます。 最適な接続モデルは、企業ネットワークまたは自宅、ホテル、コーヒーショップ、空港などのリモートの場所に関係なく、常にユーザーの場所にネットワーク出力を提供します。 一般的なインターネット トラフィックと WAN ベースの企業ネットワーク トラフィックは個別にルーティングされ、ローカルの直接出力モデルは使用されません。 このローカルの直接の出口モデルを示したものが下の図です。

![ローカル出口ネットワーク アーキテクチャ](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

ローカル出力アーキテクチャには、従来のモデル上の Microsoft 365 ネットワーク トラフィックに対して次のような利点があります。
  
- ルートの長さを最適化することにより、Microsoft 365 の最適なパフォーマンスを提供します。 エンド ユーザー接続は、Microsoft Global Network の分散サービス フロント ドア インフラストラクチャによって最も近いMicrosoft 365 エントリ ポイントに動的にルーティングされ、トラフィックは Microsoft の超低遅延高可用性ファイバーを使用して内部的にデータおよびサービス エンドポイントにルーティングされます。
- Microsoft 365 トラフィックのローカル出力を許可し、プロキシとトラフィック検査デバイスをバイパスすることで、企業のネットワーク インフラストラクチャへの負荷を軽減します。
- クライアント エンドポイントのセキュリティ機能とクラウド セキュリティ機能を活用して、両端の接続をセキュリティで保護し、冗長なネットワーク セキュリティ テクノロジの適用を回避します。

> [!NOTE]
> 分散 _サービス フロント ドア インフラストラクチャ_ は、地理的に分散した場所を持つ Microsoft Global Network の高可用性と拡張性の高いネットワーク エッジです。 エンド ユーザー接続を終了し、Microsoft グローバル ネットワーク内で効率的にルーティングします。 [Microsoft の高速で信頼性の高いグローバル ネットワーク構築方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) については、Microsoft のグローバル ネットワークの詳細を参照してください。

Microsoft 365 ネットワーク接続の原則の理解と適用の詳細については [、「Microsoft 365 Network Connectivity Principles」を参照してください](microsoft-365-network-connectivity-principles.md)。

## <a name="conclusion"></a>まとめ

Microsoft 365 ネットワークのパフォーマンスを最適化すると、不要な障害が取り除かされます。 Microsoft 365 接続を信頼できるトラフィックとして扱う場合、パケット検査やプロキシ帯域幅の競合によって遅延が発生するのを防ぐことが可能です。 クライアント コンピューターと 365 Office間のローカル接続を許可すると、トラフィックを Microsoft グローバル ネットワーク経由で動的にルーティングできます。

## <a name="related-topics"></a>関連項目

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](urls-and-ip-address-ranges.md)

[Office 365 IP アドレスと URL の Web サービス ](microsoft-365-ip-web-service.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)

[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)

[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)

[Content Delivery Network](content-delivery-networks.md)

[Microsoft 365 の接続テスト](https://aka.ms/netonboard)

[Microsoft がそのファースト・信頼性の高いグローバルネットワークを構築する方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 ネットワークのしくみ](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)