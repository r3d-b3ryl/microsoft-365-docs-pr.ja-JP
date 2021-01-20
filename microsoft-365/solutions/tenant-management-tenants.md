---
title: 手順 1. エンタープライズ向け Microsoft 365 テナント
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: 複数地域および移動場所のオプションを使用して、単一または複数の Microsoft 365 テナントを展開および管理します。
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908593"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>手順 1. エンタープライズ向け Microsoft 365 テナント

最初のテナント決定の 1 つは、必要な数です。 各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。 対応する Azure AD、他のすべての Microsoft 365 テナントとは異なる、一意のテナントです。

## <a name="single-tenant"></a>シングル テナント
1 つのテナントを使用すると、組織で Microsoft 365 を使用する多くの側面が簡素化されます。 単一のテナントとは、単一のアカウントADポリシーのセットを持つ単一の Azure テナントを意味します。 組織全体のリソースのアクセス許可と共有は、この中央 ID プロバイダーを通じて行えます。

1 つのテナントは、ユーザーにとって最も機能が豊富で簡素化されたコラボレーションと生産性のエクスペリエンスを提供します。

Microsoft 365 テナントの既定の場所と Azure ADテナントを示す例を次に示します。

![単一の Microsoft 365 テナントと Azure AD テナント](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>複数のテナント

組織が複数のテナントを持つ理由は多数あるので、次のとおりです。

- 管理上の分離
- IT の分散化
- 過去の決定
- 合併、買収、または合併
- 複合組織向けブランドの明確な分離
- 実稼働前テナント、テスト テナント、またはサンドボックス テナント

同じ既定のデータセンター geo に 2 つのテナント (テナント A とテナント B) がある組織の例を次に示します。 各テナントを個別の Azure ADテナントとして使用します。

![独自の Azure テナントを持つ複数の Microsoft 365 ADテナント](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

複数のテナントがある場合、テナントを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。

### <a name="inter-tenant-collaboration"></a>テナント間コラボレーション

ユーザーがさまざまな Microsoft 365 テナント間で安全な方法でより効果的に共同作業を行う場合、テナント間コラボレーション オプションには、ファイルと会話の中心的な場所の使用、予定表の共有、通信のための IM、音声/ビデオ通話の使用、リソースとアプリケーションへのアクセスのセキュリティ保護が含まれます。

詳細については [、「Microsoft 365 テナント間コラボレーション」を参照してください](../enterprise/microsoft-365-inter-tenant-collaboration.md)。

### <a name="cross-tenant-mailbox-migration-preview"></a>テナント間メールボックスの移行 (プレビュー)

テナント間のメールボックス移行 (プレビュー) の前に、Exchange Online メールボックスをテナント間で移動する場合は、ユーザー メールボックスを現在のテナント (ソース テナント) からオンプレミスに完全にオフボードし、新しいテナント (ターゲット テナント) にオンボードする必要があります。 新しいテナント間メールボックス移行機能により、移行元テナントと移行先テナントの両方のテナント管理者は、オンプレミス システムで最小限のインフラストラクチャ依存関係を持つテナント間でメールボックスを移動できます。 これにより、メールボックスをオフボードおよびオンボードする必要が削除されます。

テナント間のメールボックス移行前の 2 つのテナントとそのメールボックスの例を次に示します。

![複数の Microsoft 365 テナントとそのメールボックス](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

この図では、2 つの異なるテナントが独自のドメインと Exchange メールボックスのセットを持っています。

テナント間メールボックスの移行後のターゲット テナント (テナント A) を次に示します。

![テナント間メールボックスの移行後のターゲット テナント](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

この図では、1 つのテナントに両方のドメインと Exchange メールボックスの両方のセットがあります。

詳細については、「テナント間メールボックス [の移行」を参照してください](../enterprise/cross-tenant-mailbox-migration.md)。

### <a name="tenant-to-tenant-migrations"></a>テナントからテナントへの移行

合併、買収、買収、その他のシナリオには、既存の Microsoft 365 テナントを新しいテナントに移行するためのいくつかのアーキテクチャアプローチがあります。 

詳細なガイダンスについては [、Microsoft 365 テナント間の移行に関するページを参照してください](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。

## <a name="multi-geo-for-a-tenant"></a>テナントの複数地域

Microsoft 365 Multi-Geo を使用すると、データ所在地の要件を満たすために選択した他のデータセンターの地理的な場所に保存されたデータをプロビジョニングして保存すると同時に、最新の生産性エクスペリエンスのグローバル ロールアウトを作業者に提供できます。

複数地域環境では、Microsoft 365 テナントは、Microsoft 365 サブスクリプションが最初に作成された既定または中央の場所と、1 つ以上のサテライトの場所で構成されます。 複数地域テナントでは、地域の場所、グループ、およびユーザー情報に関する情報は、グローバル Azure AD テナントでマスター化されます。 テナント情報は一元的にマスター化され、各地域の場所に同期されるので、会社の誰かが関与するコラボレーション エクスペリエンスは場所間で共有されます。

ヨーロッパに既定の場所を持ち、北米にサテライトの場所がある組織の例を次に示します。 どちらの場所も、単一の Microsoft 365 AD同じグローバル Azure テナントを共有します。

![複数地域の Microsoft 365 テナントの例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>コア データを新しいデータセンター geo に移動する

Microsoft は、Microsoft 365 サービスの新しいデータセンター geo を引き続き開きます。 こうした新しいデータセンター geo により、現在続いているお客様の需要と使用量の拡大をサポートするための容量と計算リソースが増加されます。 さらに、新しいデータセンター geo では、コア カスタマー データを geo 内に常駐できます。

新しいデータセンター geo を開くことには、既存のデータセンター geo に保存されているお客様やコア データには影響を与え得ないが、Microsoft では、組織のコア カスタマー データの保存中の新しいデータセンター geo への早期移行を要求することができます。

Microsoft 365 テナントが欧州連合 (EU) データセンター geo から英国 (英国) に配置されたデータセンター geo に移行された例を次に示します。

![データセンター geo 間で Microsoft 365 テナントを移動する例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

詳細については、「コア データを [新しい Microsoft 365 データセンター geo に移動する」を参照してください](../enterprise/moving-data-to-new-datacenter-geos.md)。

## <a name="products-and-licenses-for-a-tenant"></a>テナントの製品とライセンス

Microsoft 365 E3 などの最初の製品を購入すると、Microsoft 365 テナントが作成されます。 製品と共にライセンスは、月次または年会費が課金されます。 その後、管理者は、製品の 1 つから使用可能なライセンスをユーザー アカウントに直接割り当てるか、グループ メンバーシップを通じて割り当てる必要があります。 組織のビジネス ニーズに応じて、製品のセットが用意されている場合があります。各製品には、独自のライセンス プールがあります。 

製品のセットとそれぞれのライセンス数を決定するには、次の計画が必要です。

- 高度な機能を必要とするユーザー アカウント用の十分なライセンスを持っている必要があります。
- 組織でのスタッフの変更に基づいて、ライセンスが使い切れたり、割り当てられていないライセンスが多すぎたりするのを防ぐ。


## <a name="results-of-step-1"></a>手順 1 の結果

エンタープライズ向け Microsoft 365 テナントの場合、次の点を決定しました。

- 使用しているテナントまたは必要なテナントの数。
- テナントごとに、購入する必要がある製品とライセンス。
- データ常駐の要件に準拠するためにテナントが複数地域である必要があるかどうか。
- テナント間コラボレーションを設定する必要があるかどうか。
- テナントを別のテナントに移行する必要があるかどうか。
- コア データを 1 つのデータセンター geo から新しいデータセンター geo に移動する必要があるかどうか。

新しいテナントの例を次に示します。

![新しいテナントの例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

この図では、テナントには次の機能があります。

- Microsoft 365 データセンター geo に対応する既定の場所。
- 製品とライセンスのセット。
- 一連のクラウド生産性向上アプリ。その一部は製品に固有です。
- Azure AD、グローバル管理者アカウントと最初のアカウント名をDNS ドメインします。

このソリューションの追加の手順を進め、この図を構築します。

## <a name="ongoing-maintenance-for-tenants"></a>テナントの継続的なメンテナンス

継続的に、次の必要が生じ得る場合があります。

- 新しいテナントを追加します。
- 初期数のライセンスを持つテナントに新しい製品を追加します。
- テナント内の製品のライセンスのセットを変更して、スタッフの要件の変更に合わせて調整します。
- コア データをテナントから新しいデータセンターの地理的位置に移動します。
- データ常駐の要件に複数地域を追加します。
- テナント間コラボレーションを設定します。

## <a name="next-step"></a>次の手順

[![手順 2.アクセスのためにネットワーク用にテナントを最適化する](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

ネットワークを [続行して](tenant-management-networking.md) 、ワーカーから Microsoft 365 クラウド サービスへの最適なネットワークを提供します。
