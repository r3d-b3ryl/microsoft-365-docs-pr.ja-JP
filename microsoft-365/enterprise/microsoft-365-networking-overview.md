---
title: Microsoft 365 ネットワーク接続の概要
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 08/27/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: SaaS サービスにとってネットワークの最適化が重要な理由、Microsoft 365ネットワークの目的、SaaS で他のワークロードとは異なるネットワークを必要とする方法について説明します。
ms.openlocfilehash: 64af558653ff57e91068d2e028235b73c165376b
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096768"
---
# <a name="microsoft-365-network-connectivity-overview"></a>Microsoft 365 ネットワーク接続の概要

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、さまざまなマイクロ サービスとアプリケーションを通じて生産性とコラボレーションのシナリオを提供する、サービスとしての分散型ソフトウェア (SaaS) クラウドです。 Outlook、Word、PowerPointなどのMicrosoft 365のクライアント コンポーネントは、ユーザー コンピューターで実行され、Microsoft データセンターで実行されるMicrosoft 365の他のコンポーネントに接続します。 Microsoft 365エンド ユーザー エクスペリエンスの品質を決定する最も重要な要因は、ネットワークの信頼性と、Microsoft 365 クライアントとMicrosoft 365サービス フロント ドア間の待機時間の短さです。

この記事では、Microsoft 365 ネットワークの目的と、Microsoft 365 ネットワークで一般的なインターネット トラフィックとは異なる最適化アプローチが必要な理由について説明します。

## <a name="microsoft-365-networking-goals"></a>Microsoft 365ネットワークの目標

Microsoft 365 ネットワークの最終的な目標は、クライアントと最も近いMicrosoft 365 エンドポイント間のアクセスを最小限に制限できるようにすることで、エンド ユーザー エクスペリエンスを最適化することです。 エンド ユーザー エクスペリエンスの品質は、ユーザーが使用しているアプリケーションのパフォーマンスと応答性に直接関係します。 たとえば、Microsoft Teamsは低待機時間に依存しているため、ユーザーの電話、会議、共有画面のコラボレーションは問題なく、Outlookはサーバー側のインデックス作成と AI 機能を適用するインスタント検索機能の優れたネットワーク接続に依存しています。

ネットワーク設計の主な目標は、クライアント マシンから Microsoft Global Network (Microsoft のパブリック ネットワーク バックボーン) へのラウンドトリップ時間 (RTT) を短縮し、待機時間が短く高可用性クラウド アプリケーションのエントリ ポイントが世界中に広がる Microsoft のすべてのデータセンターを相互接続することで、待機時間を最小限に抑える必要があります。 [Microsoft の高速で信頼性の高いグローバル ネットワーク構築方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) については、Microsoft のグローバル ネットワークの詳細を参照してください。

ネットワーク パフォーマンスMicrosoft 365最適化することは複雑である必要はありません。 いくつかの重要な原則に従って、可能な限り最高のパフォーマンスを得ることができます。

- ネットワーク トラフィックMicrosoft 365識別する
- ユーザーがMicrosoft 365に接続する各場所からインターネットへのMicrosoft 365ネットワーク トラフィックのローカル ブランチエグレスを許可する
- トラフィックMicrosoft 365プロキシとパケット検査デバイスのバイパスを許可する

Microsoft 365ネットワーク接続の原則の詳細については、「[Microsoft 365ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)」を参照してください。

## <a name="traditional-network-architectures-and-saas"></a>従来のネットワーク アーキテクチャと SaaS

クライアント/サーバー ワークロードの従来のネットワーク アーキテクチャ原則は、クライアントとエンドポイント間のトラフィックが企業ネットワーク境界の外部に及ばないことを前提として設計されています。 また、多くのエンタープライズ ネットワークでは、すべての送信インターネット接続が企業ネットワークを経由し、中央の場所から送信されます。

従来のネットワーク アーキテクチャでは、ネットワーク境界のセキュリティを維持するために一般的なインターネット トラフィックの待機時間を長くすることが必要であり、インターネット トラフィックのパフォーマンスの最適化には通常、ネットワークエグレス ポイントで機器をアップグレードまたはスケールアウトする必要があります。 ただし、この方法では、Microsoft 365などの SaaS サービスの最適なネットワーク パフォーマンスに関する要件には対応していません。

## <a name="identifying-microsoft-365-network-traffic"></a>ネットワーク トラフィックMicrosoft 365識別する

ネットワーク トラフィックMicrosoft 365識別しやすくし、ネットワーク識別を簡単に管理できるようになりました。

- 非常に重要なネットワーク トラフィックと、インターネット待機時間の影響を受けないネットワーク トラフィックを区別するための新しいカテゴリのネットワーク エンドポイント。 最も重要な "最適化" カテゴリには、少数の URL とサポートされている IP アドレスがあります。
- スクリプトの使用やダイレクト デバイスの構成、Microsoft 365ネットワーク識別の変更管理のための Web サービス。 変更は、Web サービス、RSS 形式、またはMicrosoft Flow テンプレートを使用して電子メールで利用できます。
- [Office 365 ネットワーク接続](./microsoft-365-networking-partner-program.md)の原則に従い、簡単な構成を持つデバイスまたはサービスを提供する Microsoft パートナーとネットワーク パートナー プログラムMicrosoft 365。

## <a name="securing-microsoft-365-connections"></a>Microsoft 365接続のセキュリティ保護

従来のネットワーク セキュリティの目標は、侵入および悪意のある脅威に対して企業のネットワーク境界を強化することです。 ほとんどのエンタープライズ ネットワークでは、プロキシ サーバー、ファイアウォール、SSL の中断と検査、ディープ パケット検査、データ損失防止システムなどのテクノロジを使用して、インターネット トラフィックのネットワーク セキュリティを適用します。 これらのテクノロジは、一般的なインターネット要求の重要なリスクを軽減しますが、Microsoft 365 のエンドポイントに適用すると、パフォーマンス、スケーラビリティ、エンドユーザー エクスペリエンスの品質が大幅に落ちることがあります。

Microsoft 365は、Microsoft 365機能とワークロード向けに特別に設計された組み込みのセキュリティとガバナンス機能を使用して、コンテンツ のセキュリティとデータ使用状況のコンプライアンスに対する組織のニーズを満たすのに役立ちます。 Microsoft 365セキュリティとコンプライアンスの詳細については、[Office 365セキュリティロードマップ](/office365/securitycompliance/security-roadmap)を参照してください。 Microsoft 365 トラフィックに対して高度なレベルの処理を実行する高度なネットワーク ソリューションに関する Microsoft の推奨事項とサポートの位置の詳細については、「Office 365 [トラフィックでのサード パーティのネットワーク デバイスまたはソリューションの使用](https://support.microsoft.com/help/2690045)」を参照してください。

## <a name="why-is-microsoft-365-networking-different"></a>Microsoft 365ネットワークが異なるのはなぜですか?

Microsoft 365は、エンドポイント セキュリティと暗号化されたネットワーク接続を使用して最適なパフォーマンスを実現するように設計されており、境界セキュリティの適用の必要性を減らします。 Microsoft 365データセンターは世界中に存在し、サービスはクライアントを利用可能な最高のサービス エンドポイントに接続するためのさまざまな方法を使用するように設計されています。 ユーザー データと処理は多くの Microsoft データセンター間で分散されるため、クライアント マシンが接続できる単一のネットワーク エンドポイントはありません。 実際、Microsoft 365 テナント内のデータとサービスは、エンド ユーザーがアクセスする地理的な場所に合わせて Microsoft Global Network によって動的に最適化されます。

一般的なパフォーマンスの問題は、トラフィックMicrosoft 365パケット検査と一元化されたエグレスの対象となる場合に発生します。

- 待機時間が長いと、ビデオストリームとオーディオ ストリームのパフォーマンスが低下し、データの取得、検索、リアルタイムコラボレーション、予定表の空き時間情報、製品内コンテンツ、その他のサービスの応答が遅くなる可能性があります
- 中央の場所からのエグレス接続は、Microsoft 365グローバル ネットワークの動的ルーティング機能を打ち負かし、待機時間とラウンドトリップ時間を追加します
- ネットワーク トラフィックMicrosoft 365 SSL セキュリティで保護された暗号化を解除し、再暗号化すると、プロトコル エラーが発生し、セキュリティ 上のリスクが発生する可能性があります

クライアント トラフィックを地理的な場所にできるだけ近い場所に送信できるようにすることで、Microsoft 365エントリ ポイントへのネットワーク パスを短縮すると、Microsoft 365での接続パフォーマンスとエンド ユーザー エクスペリエンスが向上します。 また、ネットワーク アーキテクチャに対する今後の変更がMicrosoft 365パフォーマンスと信頼性に与える影響を軽減することもできます。 最適な接続モデルは、企業ネットワーク上にあるか、自宅、ホテル、コーヒー ショップ、空港などの遠隔地にあるかに関係なく、常にユーザーの場所でネットワーク エグレスを提供することです。 汎用インターネット トラフィックと WAN ベースの企業ネットワーク トラフィックは個別にルーティングされ、ローカルのダイレクト エグレス モデルは使用されません。 このローカルの直接の出口モデルを示したものが下の図です。

![ローカル出口ネットワーク アーキテクチャ。](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)

ローカル出口アーキテクチャには、従来のモデルよりも Microsoft 365 ネットワーク トラフィックに次のような利点があります。
  
- ルートの長さを最適化することにより、Microsoft 365 の最適なパフォーマンスを提供します。 エンド ユーザー接続は、Microsoft Global Network の _分散サービス フロント ドア_ インフラストラクチャによって最も近いMicrosoft 365エントリ ポイントに動的にルーティングされ、トラフィックは Microsoft の超低待機時間高可用性ファイバーを介してデータエンドポイントとサービス エンドポイントに内部的にルーティングされます。
- プロキシとトラフィック検査デバイスをバイパスして、Microsoft 365 トラフィックのローカル エグレスを許可することで、企業ネットワーク インフラストラクチャの負荷を軽減します。
- クライアント エンドポイントのセキュリティ機能とクラウド セキュリティ機能を適用することで、冗長なネットワーク セキュリティ テクノロジの適用を回避することで、両端の接続をセキュリティで保護します。

> [!NOTE]
> _分散サービス フロント ドア_ インフラストラクチャは、地理的に分散された場所を備えた Microsoft Global Network の高可用性でスケーラブルなネットワーク エッジです。 エンド ユーザー接続を終了し、Microsoft Global Network 内で効率的にルーティングします。 [Microsoft の高速で信頼性の高いグローバル ネットワーク構築方法](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/) については、Microsoft のグローバル ネットワークの詳細を参照してください。

ネットワーク接続の原則Microsoft 365理解して適用する方法の詳細については、「[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)」を参照してください。

## <a name="conclusion"></a>まとめ

ネットワーク パフォーマンスMicrosoft 365最適化することは、不要な障害を取り除くことにつながります。 Microsoft 365接続を信頼されたトラフィックとして扱うことで、パケット検査とプロキシ帯域幅の競合によって遅延が発生するのを防ぐことができます。 クライアント マシンとOffice 365 エンドポイント間のローカル接続を許可すると、トラフィックを Microsoft Global Network 経由で動的にルーティングできます。

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
