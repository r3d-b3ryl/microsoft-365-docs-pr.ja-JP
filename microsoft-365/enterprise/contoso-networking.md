---
title: Contoso Corporation のネットワーク
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社のネットワークインフラストラクチャと、企業が Microsoft 365 for enterprise cloud services に最適なネットワークパフォーマンスを得るために、その SD テクノロジをどのように使用するかについて説明します。
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637189"
---
# <a name="networking-for-the-contoso-corporation"></a>Contoso Corporation のネットワーク

クラウドを含むインフラストラクチャを採用するために、Contoso 社はクラウドサービスへのネットワークトラフィックの移動方法について基本的な説明を考案しています。ネットワーク接続と、office 階層の次のレベルのトラフィックを中心とする内部ハブアンドスポークモデルの代わりに、ユーザーの場所を、インターネット上の最も近い Microsoft 365 ネットワークの場所へのローカルインターネット出口およびローカル接続にマップしていました。

## <a name="networking-infrastructure"></a>ネットワークインフラストラクチャ

以下は、世界中で Contoso 支社をリンクするネットワーク要素です。

- Multiprotocol Label Switching (MPLS) WAN ネットワーク

  MPLS WAN ネットワークは、パリ本社を地域のオフィスや地域のオフィスに、スポークとハブの構成のサテライトオフィスに接続します。ネットワークによって、ユーザーは、パリ本社で基幹業務アプリケーションを構成するオンプレミスサーバーにアクセスできます。また、すべての一般的なインターネットトラフィックをパリのオフィスにルーティングします。これにより、ネットワークセキュリティデバイスが要求をスクラブできます。各オフィスで、ルーターは、プライベート IP アドレス空間を使用して、有線ホストまたはサブネット上のワイヤレスアクセスポイントにトラフィックを配信します。

- Microsoft 365 トラフィック用のローカル直接インターネットアクセス

  各オフィスには、プロキシサーバー経由の独自のインターネット接続を備えた1つ以上のローカルインターネット ISP ネットワーク回線を備えた、ソフトウェア定義の WAN (SD) デバイスがあります。これは、通常、パブリック IP アドレスとローカル DNS サーバーも提供するローカル ISP への WAN リンクとして実装されます。

- インターネット プレゼンス

  Contoso は contoso \. com パブリックドメイン名を所有しています。製品を注文するための Contoso 社のパブリック web サイトは、パリキャンパスのインターネット接続されたデータセンター内のサーバーのセットです。Contoso 社では、インターネット上のパブリック IP アドレスの範囲として24個を使用しています。

図1は、Contoso 社のネットワークインフラストラクチャと、そのインターネットに対する接続を示しています。

![Contoso ネットワーク](../media/contoso-networking/contoso-networking-fig1.png)
 
**図 1: Contoso ネットワーク**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Microsoft への最適なネットワーク接続のための SD-WAN の使用

Contoso 社は次の [Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)に従いました。

- Microsoft 365 ネットワーク トラフィックを識別して区別する
- ネットワーク接続のローカルの出口を提供する
- ネットワーク ヘアピンを回避する
- 重複するネットワーク セキュリティ デバイスをバイパスする

Microsoft 365 のネットワークトラフィックには、 *Optimize*、 *Allow*、および *Default*の3つのカテゴリがあります。 トラフィックの最適化と許可は、エンドポイントで暗号化およびセキュリティ保護され、Microsoft 365 ネットワークに向けられている信頼されたネットワークトラフィックです。

Contoso は次のように決定しました。

- 直接インターネット出口を使用してカテゴリトラフィックを最適化および許可し、すべての既定のカテゴリトラフィックをパリベースの中央インターネット接続に転送します。

- これらの原則に従って、Microsoft 365 のクラウドベースのサービスで最適なネットワークパフォーマンスを実現するための簡単な方法として、各オフィスの SD を展開します。

  SD-WAN デバイスには、ローカル オフィス ネットワーク用の LAN ポートと複数の WAN ポートがあります。 1つの WAN ポートが MPLS ネットワークに接続します。 別の方法として、ローカルの ISP サーキットに接続します。 SD-WAN デバイスは、ISP リンクを介してカテゴリ ネットワーク トラフィックを最適化および許可します。

## <a name="the-contoso-line-of-business-app-infrastructure"></a>Contoso の基幹業務アプリインフラストラクチャ

Contoso 社は、次のような基幹業務アプリケーションとサーバーのイントラネットインフラストラクチャを構築しています。

- サテライト オフィスは、ローカル キャッシュ サーバーを使用して、アクセス頻度の高いドキュメントおよび内部 Web サイトを格納します。
- 地域ハブは、地域オフィスおよびサテライト オフィスに地域アプリケーション サーバーを使用します。これらのサーバーは、パリ本社のサーバーと同期します。
- パリキャンパスデータセンターには、組織全体にサービスを提供する集中管理アプリケーションサーバーが含まれています。

図2は、Contoso イントラネット経由でサーバーにアクセスする際に使用されるネットワークトラフィック容量の割合を示しています。

![内部アプリケーションの Contoso インフラストラクチャ](../media/contoso-networking/contoso-networking-fig2.png)
 
**図 2: 内部アプリケーションの Contoso インフラストラクチャ**

サテライトまたは地域ハブのオフィスの場合、従業員が必要とするリソースの60% は、サテライトおよび地域のハブオフィスサーバーによって提供されます。 リソース要求の40% は、パリキャンパスへの WAN リンクを介して追加する必要があります。

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Microsoft 365 for enterprise のネットワーク分析と準備

Contoso ユーザーによるエンタープライズサービスへの Microsoft 365 の導入を成功させるには、インターネットまたは Microsoft クラウドサービスに直接接続できる高可用性とパフォーマンスを備えています。 Contoso 社は次の手順を実行して、エンタープライズクラウドサービス用に Microsoft 365 への接続を最適化して計画および実装しました。

1. 計画に役立てるために会社の WAN ネットワーク図を作成する

   ネットワーク計画を開始するために、Contoso 社は、オフィスの場所、既存のネットワーク接続、既存のネットワーク境界デバイス、およびネットワーク上で管理されているサービスのクラスを示す図を作成しました。 この図は、「ネットワーク接続の計画と実装」に記載されている以降の手順で使用します。

2. エンタープライズネットワーク接続用の Microsoft 365 の計画を作成する

   Contoso 社は、microsoft [365 のネットワーク接続の原則](microsoft-365-network-connectivity-principles.md) とサンプルの参照ネットワークアーキテクチャを使用して、microsoft 365 接続の優先トポロジとして SD WAN を識別していました。

3. 各オフィスでインターネット接続の使用率と MPLS-WAN の帯域幅を分析し、必要に応じて帯域幅を増やす

   各 office の現在の使用状況が分析され、回路が増加したため、Microsoft 365 のクラウドベースのトラフィックは、平均で20% の未使用容量を使用して動作するようになりました。

4. Microsoft ネットワークサービスに対するパフォーマンスを最適化する

   Contoso 社は、最適なパフォーマンスを得るために、Office 365、Intune、および Azure エンドポイントのセット、および構成されているファイアウォール、セキュリティデバイス、およびその他のシステムをインターネットパスに決定しました。 Office 365 のエンドポイント [最適化] および [許可] カテゴリトラフィックは、ISP 回線経由でルーティングするために SD デバイスに構成されました。

5. 内部 DNS を構成する

   DNS が機能し、Microsoft 365 トラフィックのためにローカルで検索対象になる必要があります。

6. ネットワークエンドポイントとポート接続を検証する

   Contoso 社は Microsoft ネットワーク接続テストツールを実行して、エンタープライズクラウドサービスの Microsoft 365 への接続を検証しました。

7. ネットワーク接続のために従業員のコンピューターを最適化する

   各コンピューターは、最新のオペレーティングシステムの更新プログラムがインストールされていて、エンドポイントのセキュリティ監視がすべてのクライアントでアクティブであったことを確認するためにチェックされました。

## <a name="next-step"></a>次の手順

Contoso 社が、どのようにクラウド内のオンプレミスの Active Directory ドメイン サービス (AD DS) を従業員向けに利用し、どのように顧客やビジネス パートナー向けのフェデレーション認証を活用しているかについて[説明](contoso-identity.md)します。

## <a name="see-also"></a>関連項目

[Microsoft 365 のネットワークロードマップ](networking-roadmap-microsoft-365.md)

[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
