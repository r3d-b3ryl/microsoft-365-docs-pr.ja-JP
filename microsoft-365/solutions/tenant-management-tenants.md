---
title: 手順 1. エンタープライズ テナントのMicrosoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 複数地域および移動場所のオプションを使用して、単一または複数のMicrosoft 365 テナントをデプロイおよび管理します。
ms.openlocfilehash: 305d7683413d5682c0dddda418e87de0a0a682b7
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524119"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>手順 1. エンタープライズ テナントのMicrosoft 365

最初のテナントの決定の 1 つは、持つ必要がある数です。 各Microsoft 365テナントは、個別で一意であり、他のすべてのMicrosoft 365テナントとは別です。 対応するAzure ADテナントは、他のすべてのMicrosoft 365 テナントとは異なり、一意です。

## <a name="single-tenant"></a>シングル テナント
1 つのテナントを持つことで、組織でのMicrosoft 365の使用の多くの側面が簡略化されます。 1 つのテナントとは、1 つのアカウント、グループ、ポリシーのセットを持つ 1 つのAzure AD テナントを意味します。 組織全体のリソースのアクセス許可と共有は、この中央 ID プロバイダーを使用して行うことができます。

1 つのテナントは、ユーザーに最も豊富でシンプルなコラボレーションと生産性のエクスペリエンスを提供します。

Microsoft 365 テナントの既定の場所とAzure ADテナントを示す例を次に示します。

![Azure AD テナントを持つ単一のMicrosoft 365 テナント。](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>複数のテナント

組織に複数のテナントが存在する可能性がある理由は次のとおりです。

- 管理上の分離
- 分散型 IT
- 履歴に関する決定
- 合併、買収、または分権
- 複合組織のブランド化の明確な分離
- 運用前、テスト、またはサンドボックス テナント

同じ既定のデータセンター geo に 2 つのテナント (テナント A とテナント B) を持つ組織の例を次に示します。 各テナントを個別のAzure AD テナントとして使用します。

![独自のAzure AD テナントを持つ複数のMicrosoft 365 テナント。](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

複数のテナントがある場合、テナントを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。

### <a name="inter-tenant-collaboration"></a>テナント間コラボレーション

ユーザーがさまざまなMicrosoft 365 テナント間で安全な方法で効率的に共同作業できるようにする場合、テナント間コラボレーション オプションには、ファイルと会話の一元的な場所の使用、予定表の共有、IM の使用、通信のためのオーディオ/ビデオ通話、リソースとアプリケーションへのアクセスのセキュリティ保護などがあります。

詳細については、「[テナント間コラボレーションのMicrosoft 365](../enterprise/microsoft-365-inter-tenant-collaboration.md)」を参照してください。

### <a name="cross-tenant-mailbox-migration-preview"></a>テナント間メールボックス移行 (プレビュー)

テナント間メールボックス移行 (プレビュー段階) の前に、テナント間でメールボックスExchange Online移動する場合は、ユーザー メールボックスを現在のテナント (ソース テナント) からオンプレミスに完全にオフボードし、新しいテナント (ターゲット テナント) にオンボードする必要があります。 新しいテナント間メールボックス移行機能を使用すると、ソース テナントとターゲット テナントの両方のテナント管理者は、オンプレミス システムのインフラストラクチャ依存関係を最小限に抑えて、テナント間でメールボックスを移動できます。 これにより、メールボックスをオフボードおよびオンボードする必要が解消されます。

テナント間メールボックス移行前の 2 つのテナントとそのメールボックスの例を次に示します。

![複数のMicrosoft 365 テナントとそのメールボックス。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

この図では、2 つの独立したテナントに独自のドメインとExchangeメールボックスのセットがあります。

クロステナント メールボックス移行後のターゲット テナント (テナント A) を次に示します。

![テナント間メールボックス移行後のターゲット テナント。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

この図では、1 つのテナントにドメインとExchangeメールボックスの両方のセットがあります。

詳細については、「 [テナント間メールボックスの移行](../enterprise/cross-tenant-mailbox-migration.md)」を参照してください。

### <a name="tenant-to-tenant-migrations"></a>テナントからテナントへの移行

既存のMicrosoft 365 テナントを新しいテナントに移行する可能性がある、合併、買収、詳細、その他のシナリオには、いくつかのアーキテクチャアプローチがあります。 

詳細なガイダンスについては、「[テナント間の移行Microsoft 365」を](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)参照してください。

## <a name="multi-geo-for-a-tenant"></a>テナントの複数地域

Microsoft 365 Multi-Geo を使用すると、データ所在地の要件を満たすために選択した他のデータセンターの地理的な場所に保存データをプロビジョニングして保存すると同時に、最新の生産性エクスペリエンスのグローバルロールアウトをワーカーに公開できます。

複数地域環境では、Microsoft 365 テナントは、Microsoft 365 サブスクリプションが最初に作成された既定または中央の場所と、1 つ以上のサテライトの場所で構成されます。 複数地域テナントでは、地理的な場所、グループ、およびユーザー情報に関する情報は、グローバル Azure AD テナントでマスターされます。 テナント情報は一元的にマスターされ、各地域の場所に同期されるため、会社の誰もが関与するコラボレーション エクスペリエンスが場所間で共有されます。

ヨーロッパの既定の場所と北米のサテライトの場所を持つ組織の例を次に示します。 どちらの場所も、単一のMicrosoft 365 テナントに対して同じグローバル Azure AD テナントを共有します。

![複数地域のMicrosoft 365テナントの例。](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>コア データを新しいデータセンター geo に移動する

Microsoft は、Microsoft 365 サービスの新しいデータセンター geo を引き続き開いています。 こうした新しいデータセンター geo により、現在続いているお客様の需要と使用量の拡大をサポートするための容量と計算リソースが増加されます。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

新しいデータセンター geo を開く場合、既存のデータセンター geo に格納されているコア データには影響しませんが、Microsoft では、組織のコア顧客データを新しいデータセンター geo に早期に移行することを要求できます。

ここでは、Microsoft 365 テナントが欧州連合 (EU) データセンター geo から英国 (英国) にあるデータセンターに移動された例を示します。

![データセンター geo 間でMicrosoft 365テナントを移動する例。](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

詳細については、「[新しいMicrosoft 365データセンター geo へのコア データの移動](../enterprise/moving-data-to-new-datacenter-geos.md)」を参照してください。

## <a name="products-and-licenses-for-a-tenant"></a>テナントの製品とライセンス

Microsoft 365 E3など、最初の製品を購入すると、Microsoft 365 テナントが作成されます。 製品と共にライセンスは、毎月または年間の料金が請求されます。 その後、管理者は、製品の 1 つの使用可能なライセンスを、直接またはグループ メンバーシップを使用してユーザー アカウントに割り当てます。 組織のビジネス ニーズによっては、それぞれ独自のライセンス プールを備えた一連の製品が用意されている場合があります。 

製品のセットと各ライセンスの数を決定するには、次の計画が必要です。

- 高度な機能を必要とするユーザー アカウントに十分なライセンスがあることを確認します。
- 組織でのスタッフの変更に基づいて、ライセンスが不足したり、割り当てられていないライセンスが多すぎたりすることを防ぎます。


## <a name="results-of-step-1"></a>手順 1 の結果

エンタープライズ テナントのMicrosoft 365については、次のことを決定しました。

- 必要なテナントの数。
- テナントごとに、どの製品とライセンスを購入する必要があります。
- データ所在地の要件に準拠するためにテナントを複数地域にする必要があるかどうか。
- テナント間コラボレーションを設定する必要があるかどうか。
- テナントを別のテナントに移行する必要があるかどうか。
- コア データを 1 つのデータセンター geo から新しいデータセンターに移動する必要があるかどうか。

新しいテナントの例を次に示します。

![新しいテナントの例。](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

この図では、テナントには次のものがあります。

- Microsoft 365 データセンター geo に対応する既定の場所。
- 製品とライセンスのセット。
- クラウド生産性アプリのセット。一部は製品に固有です。
- グローバル管理者アカウントと初期 DNS ドメイン名を含むAzure AD テナント。

このソリューションの追加の手順を進め、この図を作成します。

## <a name="ongoing-maintenance-for-tenants"></a>テナントの継続的なメンテナンス

継続的に、次の操作が必要になる場合があります。

- 新しいテナントを追加します。
- 最初のライセンス数を持つ新しい製品をテナントに追加します。
- テナント内の製品の一連のライセンスを変更して、スタッフの要件を変更するように調整します。
- テナントから新しいデータセンターの地理的な場所にコア データを移動します。
- データ常駐要件に複数地域を追加します。
- テナント間コラボレーションを設定します。

## <a name="next-step"></a>次の手順

[![手順 2.アクセス用にテナントをネットワーク用に最適化します。](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

[ネットワーク](tenant-management-networking.md)を続行して、ワーカーからクラウド サービスMicrosoft 365最適なネットワークを提供します。
