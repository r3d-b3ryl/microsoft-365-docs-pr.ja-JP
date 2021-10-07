---
title: 手順 1. エンタープライズ Microsoft 365のユーザー 情報
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 複数地域および移動場所のオプションMicrosoft 365単一または複数のテナントを展開および管理します。
ms.openlocfilehash: 149dd4274e43d085f2c454774c4499a12561b766
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206435"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>手順 1. エンタープライズ Microsoft 365のユーザー 情報

テナントの最初の決定の 1 つは、必要な数です。 各Microsoft 365は、個別、一意、および他のすべてのテナントMicrosoft 365します。 対応する Azure ADは、他のすべてのテナントとは異なる、一意Microsoft 365です。

## <a name="single-tenant"></a>シングル テナント
1 つのテナントを使用すると、組織による組織のアプリケーションの使用の多くの側面がMicrosoft 365。 1 つのテナントとは、単一の Azure ADアカウント、グループ、およびポリシーのセットを持つテナントを意味します。 組織全体のリソースのアクセス許可と共有は、この一元的な ID プロバイダーを通じて行えます。

1 つのテナントは、ユーザーに最も機能が豊富で簡略化されたコラボレーションと生産性のエクスペリエンスを提供します。

次に、テナントの既定の場所と Azure ADテナントをMicrosoft 365します。

![Azure Microsoft 365テナントを持つ単一のADテナント。](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>複数のテナント

組織が複数のテナントを持つ理由は、次のとおりです。

- 管理上の分離
- 分散 IT
- 過去の決定
- 合併、買収、または売却
- 複合企業組織のブランド化の明確な分離
- プレプロダクション、テスト、またはサンドボックス テナント

同じ既定のデータセンター geo に 2 つのテナント (テナント A とテナント B) がある組織の例を次に示します。 各テナントは、個別の Azure ADテナントとして使用されます。

![独自Microsoft 365 Azure テナントを持つ複数のADテナント。](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

複数のテナントがある場合は、それらを管理し、ユーザーにサービスを提供する際に、制限と追加の考慮事項があります。

### <a name="inter-tenant-collaboration"></a>テナント間コラボレーション

ユーザーが異なる Microsoft 365 テナント間で安全な方法で共同作業を行う場合、テナント間のコラボレーション オプションには、ファイルと会話の中心的な場所の使用、予定表の共有、IM の使用、通信のための音声/ビデオ通話、リソースとアプリケーションへのアクセスのセキュリティ保護が含まれます。

詳細については、「テナント間[Microsoft 365」を参照してください](../enterprise/microsoft-365-inter-tenant-collaboration.md)。

### <a name="cross-tenant-mailbox-migration-preview"></a>テナント間メールボックスの移行 (プレビュー)

テナント間メールボックスの移行 (プレビュー) の前に、Exchange Online メールボックスをテナント間で移動する場合は、ユーザー メールボックスを現在のテナント (ソース テナント) からオンプレミスに完全にオフボードし、新しいテナント (ターゲット テナント) にオンボードする必要があります。 新しいクロステナント メールボックス移行機能により、移行元テナントとターゲット テナントの両方のテナント管理者は、オンプレミス システムでのインフラストラクチャの依存関係を最小限に抑えたテナント間でメールボックスを移動できます。 これにより、オフボードメールボックスとオンボードメールボックスが不要になります。

クロステナント メールボックス移行前の 2 つのテナントとそのメールボックスの例を次に示します。

![複数Microsoft 365テナントとそのメールボックス。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

この図では、2 つの独立したテナントに独自のドメインと一連のメールボックスExchangeがあります。

クロステナント メールボックスの移行後のターゲット テナント (テナント A) を次に示します。

![テナント間メールボックスの移行後のターゲット テナント。](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

この図では、1 つのテナントにドメインとメールボックスの両方のセットExchangeしています。

詳細については、「クロステナント [メールボックスの移行」を参照してください](../enterprise/cross-tenant-mailbox-migration.md)。

### <a name="tenant-to-tenant-migrations"></a>テナントからテナントへの移行

合併、買収、売却、その他のシナリオには、既存の Microsoft 365 テナントを新しいテナントに移行するためのいくつかのアーキテクチャアプローチがあります。 

詳細なガイダンスについては、「テナント[間Microsoft 365移行」を参照してください](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。

## <a name="multi-geo-for-a-tenant"></a>テナントの複数地域

Microsoft 365 Multi-Geo を使用すると、データ常駐要件を満たすために選択した他のデータセンターの地理的な場所にデータをプロビジョニングして保存し、同時に、最新の生産性エクスペリエンスのグローバルロールアウトをワーカーにロック解除できます。

複数地域環境では、Microsoft 365 テナントは、Microsoft 365 サブスクリプションが最初に作成された既定または中央の場所と、1 つ以上のサテライトの場所で構成されます。 複数地域のテナントでは、地域の場所、グループ、およびユーザー情報に関する情報は、グローバル Azure ADテナントでADされます。 テナント情報は一元的にマスターされ、各地域の場所に同期されますので、会社の誰もが関与するコラボレーション エクスペリエンスが場所全体で共有されます。

ヨーロッパに既定の場所を持ち、北アメリカのサテライトの場所を持つ組織の例を次に示します。 どちらの場所も、単一のテナントAD同じグローバル Azure Microsoft 365共有します。

![複数地域のテナントのMicrosoft 365します。](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>コア データを新しいデータセンター geo に移動する

Microsoft は、引き続き新しいデータセンター geos を開き、Microsoft 365します。 こうした新しいデータセンター geo により、現在続いているお客様の需要と使用量の拡大をサポートするための容量と計算リソースが増加されます。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

新しいデータセンター geo を開いても、既存のデータセンター geo に格納されているコア データには影響を及ぼすとは言え、Microsoft では、組織の主要な顧客データの早期移行を新しいデータセンター geo に要求できます。

次に示すのは、Microsoft 365テナントが欧州連合 (EU) データセンター geo から英国 (英国) に移動された例です。

![データセンター geo 間でMicrosoft 365テナントを移動する例。](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

詳細については、「コア データを新しいデータセンター geos[にMicrosoft 365する」を参照してください](../enterprise/moving-data-to-new-datacenter-geos.md)。

## <a name="products-and-licenses-for-a-tenant"></a>テナントの製品とライセンス

最初Microsoft 365を購入すると、テナントが作成されます (Microsoft 365 E3)。 製品と共にライセンスは、月次または年会費が課金されます。 その後、管理者は、いずれかの製品の利用可能なライセンスを、直接またはグループ メンバーシップを通じてユーザー アカウントに割り当てる。 組織のビジネス ニーズに応じて、それぞれ独自のライセンス プールを持つ一連の製品が用意されている場合があります。 

製品のセットと各ライセンスの数を決定するには、次の計画が必要です。

- 高度な機能を必要とするユーザー アカウントのライセンスが十分に確保されている必要があります。
- 組織でのスタッフの変更に基づいて、ライセンスが使い切れたり、割り当てられていないライセンスが多すぎたりするのを防ぐ。


## <a name="results-of-step-1"></a>手順 1 の結果

エンタープライズ テナントMicrosoft 365、次の条件を決定しました。

- 必要なテナントの数。
- テナントごとに、購入する必要がある製品とライセンス。
- データ常駐要件に準拠するためにテナントが複数地域である必要があるかどうか。
- テナント間のコラボレーションをセットアップする必要があるかどうか。
- テナントを別のテナントに移行する必要があるかどうか。
- コア データを 1 つのデータセンター geo から新しいデータセンター geo に移動する必要があるかどうか。

新しいテナントの例を次に示します。

![新しいテナントの例。](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

この図では、テナントには次の機能があります。

- データ センター geo に対応する既定Microsoft 365場所です。
- 製品とライセンスのセット。
- 一連のクラウド生産性アプリは、製品に固有の一部です。
- グローバル管理者ADアカウントと初期管理者名を含む Azure DNS ドメインテナント。

このソリューションの追加の手順を進め、この図を作成します。

## <a name="ongoing-maintenance-for-tenants"></a>テナントの継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- 新しいテナントを追加します。
- ライセンスの初期数を持つテナントに新しい製品を追加します。
- テナント内の製品のライセンスセットを変更して、スタッフの要件の変更に合わせて調整します。
- コア データをテナントから新しいデータセンターの地理的な場所に移動します。
- データ常駐要件に複数地域を追加します。
- テナント間のコラボレーションを設定します。

## <a name="next-step"></a>次の手順

[![手順 2.アクセスのためにネットワーク用にテナントを最適化します。](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

ネットワークを[続行して、](tenant-management-networking.md)ワーカーからクラウド サービスへの最適なネットワークMicrosoft 365提供します。
