---
title: Office 365 向け ExpressRoute のネットワーク計画
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: この記事では、Office 365用の Azure ExpressRoute と、それをネットワーク計画に利用する方法について説明します。
ms.openlocfilehash: a284472ad84139a5e76eeab38121d62cf3757829
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095644"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Office 365 向け ExpressRoute のネットワーク計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ExpressRoute for Office 365では、ネットワークと Microsoft のデータセンター間にレイヤー 3 接続が提供されます。 回線は、Office 365のフロントエンド サーバーの Border Gateway Protocol (BGP) ルートアドバタイズを使用します。 オンプレミス デバイスの観点から見ると、Office 365に正しい TCP/IP パスを選択する必要がある場合、Azure ExpressRoute はインターネットの代替手段と見なされます。
  
Azure ExpressRoute は、Microsoft のデータセンター内のOffice 365 サーバーによって提供される、サポートされている機能とサービスの特定のセットへの直接パスを追加します。 Azure ExpressRoute では、Microsoft データセンターへのインターネット接続や、ドメイン名解決などの基本的なインターネット サービスは置き換えられません。 Azure ExpressRoute とインターネット回線はセキュリティで保護され、冗長である必要があります。
  
次の表は、Office 365のコンテキストにおけるインターネット接続と Azure ExpressRoute 接続の違いをいくつか示しています。

|**ネットワーク計画の違い**|**インターネット ネットワーク接続**|**ExpressRoute ネットワーク接続**|
|:-----|:-----|:-----|
| 必要なインターネット サービスへのアクセス(以下を含む)。  <br/>  DNS 名解決  <br/>  証明書失効の検証  <br/>  コンテンツ配信ネットワーク (CDN)  <br/> |はい  <br/> |Microsoft 所有の DNS やCDN インフラストラクチャへの要求では、ExpressRoute ネットワークを使用できます。  <br/> |
| Office 365 サービスへのアクセス(以下を含む)  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  ブラウザーでのOffice  <br/>  Office 365 ポータルと認証  <br/> |はい。すべてのアプリケーションと機能  <br/> |はい、 [特定のアプリケーションと機能](./urls-and-ip-address-ranges.md) <br/> |
|境界でのオンプレミスのセキュリティ。  <br/> |はい  <br/> |はい  <br/> |
|高可用性の計画。  <br/> |代替インターネット ネットワーク接続にフェールオーバーする  <br/> |別の ExpressRoute 接続にフェールオーバーする  <br/> |
|予測可能なネットワーク プロファイルを使用した直接接続。  <br/> |いいえ  <br/> |はい  <br/> |
|IPv6 接続。  <br/> |はい  <br/> |はい  <br/> |

ネットワーク計画の詳細については、以下のタイトルを展開してください。 さらに詳しく説明する 10 部構成の [Azure ExpressRoute for Office 365 トレーニング](https://channel9.msdn.com/series/aer) シリーズも記録しました。

## <a name="existing-azure-expressroute-customers"></a>既存の Azure ExpressRoute のお客様

既存の Azure ExpressRoute 回線を使用していて、この回線にOffice 365接続を追加する場合は、回線の数、エグレスの場所、および回線のサイズを調べて、Office 365の使用状況のニーズを満たしていることを確認する必要があります。 ほとんどのお客様は余分な帯域幅を必要とし、多くのお客様にはより多くの回線が必要です。
  
既存の Azure ExpressRoute 回線経由でOffice 365にアクセスできるようにするには、Office 365 サービスにアクセスできるように[ルート フィルターを構成](/azure/expressroute/how-to-routefilter-portal)します。
  
Azure ExpressRoute サブスクリプションは顧客中心であり、サブスクリプションは顧客に関連付けられています。 お客様は、複数の Azure ExpressRoute 回線を使用でき、それらの回線を介して多くの Microsoft クラウド リソースにアクセスできます。 たとえば、Azure ホスト型仮想マシン、Office 365 テスト テナント、およびOffice 365運用テナントに、冗長な Azure ExpressRoute 回線のペア経由でアクセスすることを選択できます。
  
次の表では、回線経由で実装するために選択できる 2 種類のピアリング関係の概要を示します。

|**ピアリングリレーションシップ**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**サービス** <br/> |IaaS: Azure Virtual Machines  <br/> |PaaS: Azure パブリック サービス  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|接続の開始**** <br/> |Customer-to-Microsoft  <br/> Microsoft から顧客へ  <br/> |Customer-to-Microsoft  <br/> Microsoft から顧客へ  <br/> |
|**QoS サポート** <br/> |QoS なし  <br/> |<sup>QoS1</sup> <br/> |

<sup>1 </sup>QoS では、現時点でのみSkype for Businessがサポートされています。
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Azure ExpressRoute の帯域幅計画

すべてのOffice 365顧客は、各場所の人数、各Office 365アプリケーションでのアクティブな状況、オンプレミスやハイブリッド機器の使用、ネットワーク セキュリティ構成などのその他の要因に応じて、固有の帯域幅ニーズを持っています。
  
帯域幅が少なすぎると、混雑、データの再送信、予期しない遅延が発生します。 帯域幅が多すぎると、不要なコストが発生します。 既存のネットワークでは、帯域幅は多くの場合、回線で使用可能なヘッドルームの量をパーセンテージと呼びます。 ヘッドルームが 10% の場合、混雑が発生する可能性があります。通常、ヘッドルームが 80% の場合は不要なコストが発生します。 一般的なヘッドルーム ターゲット割り当ては 20% から 50% です。
  
適切なレベルの帯域幅を見つけるには、既存のネットワーク使用量をテストするのが最適なメカニズムです。 これは、すべてのネットワーク構成とアプリケーションがいくつかの点で一意であるため、実際の使用状況とニーズを測定する唯一の方法です。 測定する場合は、ネットワークのニーズを理解するために、帯域幅の消費量、待機時間、および TCP の混雑の合計に注意を払う必要があります。
  
すべてのネットワーク アプリケーションを含むベースラインの見積もりが完了したら、組織内のさまざまなプロファイルを構成する小規模なグループでパイロット Office 365して実際の使用状況を決定し、2 つの測定値を使用して、各オフィスの場所に必要な帯域幅の量を見積もります。 テストで待機時間や TCP 混雑の問題が見つかった場合は、Office 365を使用しているユーザーにエグレスを近付けるか、SSL 復号化や検査などの集中的なネットワーク スキャンを削除する必要があります。
  
推奨されるネットワーク処理の種類に関するすべての推奨事項は、ExpressRoute とインターネット回線の両方に適用されます。 [パフォーマンス チューニング サイト](./network-planning-and-performance.md)の残りのガイダンスでも同様です。
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Office 365シナリオに対する Azure ExpressRoute へのセキュリティ制御の適用

Azure ExpressRoute 接続のセキュリティ保護は、インターネット接続のセキュリティ保護と同じ原則から始まります。 多くのお客様は、オンプレミス ネットワークをOffice 365およびその他の Microsoft クラウドに接続する ExpressRoute パスに沿ってネットワークと境界の制御をデプロイすることを選択しています。 これらの制御には、ファイアウォール、アプリケーション プロキシ、データ漏えい防止、侵入検出、侵入防止システムなどが含まれます。 多くの場合、お客様は、Microsoft に向かうオンプレミスから開始されたトラフィックに対して、Microsoft から顧客のオンプレミス ネットワークに向かうトラフィックと、オンプレミスから一般的なインターネット宛先に向かうトラフィックに対して、さまざまなレベルの制御を適用します。
  
デプロイする [ExpressRoute 接続モデル](/azure/expressroute/expressroute-connectivity-models) とセキュリティを統合する例をいくつか次に示します。

|**ExpressRoute 統合オプション**|**ネットワーク セキュリティ境界モデル**|
|:-----|:-----|
|クラウド エクスチェンジで併置  <br/> |ExpressRoute 接続が確立されているコロケーション機能に新しいセキュリティ/境界インフラストラクチャをインストールするか、既存のセキュリティ/境界インフラストラクチャを使用します。  <br/> コロケーション機能は、単にルーティング/相互接続の目的で使用し、コロケーション機能からオンプレミスのセキュリティ/境界インフラストラクチャへのバックホール接続に使用します。  <br/> |
|ポイント対ポイント イーサネット  <br/> |既存のオンプレミスのセキュリティ/境界インフラストラクチャの場所でポイント対ポイント ExpressRoute 接続を終了します。  <br/> ExpressRoute パスに固有の新しいセキュリティ/境界インフラストラクチャをインストールし、そこでポイント対ポイント接続を終了します。  <br/> |
|Any-to-Any IPVPN  <br/> |ExpressRoute でOffice 365接続に使用される IPVPN に送信されるすべての場所で、既存のオンプレミスのセキュリティ/境界インフラストラクチャを使用します。  <br/> ExpressRoute で使用される IPVPN を、セキュリティ/境界として機能するように指定された特定のオンプレミスの場所にOffice 365します。  <br/> |

一部のサービス プロバイダーでは、Azure ExpressRoute との統合ソリューションの一部として、マネージド セキュリティ/境界機能も提供されています。
  
expressRoute でOffice 365接続に使用されるネットワーク/セキュリティ境界オプションのトポロジの配置を検討する場合は、次の追加の考慮事項を参照してください。
  
- 深度と種類のネットワーク/セキュリティ制御は、Office 365ユーザー エクスペリエンスのパフォーマンスとスケーラビリティに影響を与える可能性があります。

- 送信 (オンプレミス -\>Microsoft) フローと受信 (Microsoft\> オンプレミス) [有効な場合] フローの要件は異なる場合があります。 これらは、一般的なインターネット宛先への送信とは異なる可能性があります。

- ポート/プロトコルと必要な IP サブネットのOffice 365要件は同じです。トラフィックは、Office 365またはインターネット経由で ExpressRoute 経由でルーティングされるかどうかが同じです。

- 顧客ネットワーク/セキュリティ制御のトポロジ的な配置によって、ユーザーとOffice 365 サービスの間の最終的なエンドツーエンド ネットワークが決定され、ネットワークの待機時間と混雑に大きな影響を与える可能性があります。

- お客様は、冗長性、高可用性、ディザスター リカバリーのベスト プラクティスに従って、Office 365用に ExpressRoute で使用するセキュリティ/境界トポロジを設計することをお勧めします。

さまざまな Azure ExpressRoute 接続オプションと、上で説明した境界セキュリティ モデルを比較する Woodgrove Bank の例を次に示します。
  
### <a name="example-1-securing-azure-expressroute"></a>例 1: Azure ExpressRoute のセキュリティ保護
  
Woodgrove Bank は Azure ExpressRoute の実装を検討しており、[Office 365に対して ExpressRoute を](routing-with-expressroute.md)使用したルーティングに最適なアーキテクチャを計画した後、上記のガイダンスを使用して帯域幅要件を理解した後、境界をセキュリティで保護するための最適な方法を決定しています。
  
複数の大陸に場所を持つ複数の国家組織である Woodgrove の場合、セキュリティはすべての境界にまたがる必要があります。 Woodgrove の最適な接続オプションは、世界中の複数のピアリング場所とのマルチポイント接続であり、各大陸の従業員のニーズに対応します。 各大陸には、大陸内に冗長な Azure ExpressRoute 回線が含まれており、セキュリティはこれらのすべてにまたがっている必要があります。
  
Woodgrove の既存のインフラストラクチャは信頼性が高く、余分な作業を処理できるため、Woodgrove Bank は Azure ExpressRoute とインターネット境界のセキュリティにインフラストラクチャを使用できます。 これが該当しない場合、Woodgrove は、既存の機器を補完するために、または別の種類の接続を処理するために、より多くの機器を購入することを選択できます。
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Azure ExpressRoute を使用した高可用性とフェールオーバー
<a name="BKMK_high-availability"> </a>

ExpressRoute を使用して各エグレスから ExpressRoute プロバイダーに少なくとも 2 つのアクティブ回線をプロビジョニングすることをお勧めします。 これは、お客様に障害が発生する最も一般的な場所であり、アクティブ/アクティブな ExpressRoute 回線のペアをプロビジョニングすることで簡単に回避できます。 また、多くのOffice 365 サービスはインターネット経由でのみ利用できるため、少なくとも 2 つのアクティブ/アクティブ インターネット回線をお勧めします。
  
ネットワークのエグレス ポイント内には、他の多くのデバイスや回線があり、ユーザーが可用性を認識する方法に重要な役割を果たします。 接続シナリオのこれらの部分は、ExpressRoute または Office 365 SLA ではカバーされませんが、組織内のユーザーが認識するエンド ツー エンドのサービス可用性において重要な役割を果たします。
  
1 つのコンポーネントの障害がサービスを使用するユーザーのエクスペリエンスに影響を与える場合は、Office 365を使用して操作するユーザーに焦点を当て、影響を受けるユーザーの合計数を制限する方法を探します。 フェールオーバー モードが運用上複雑な場合は、復旧に長い時間を要するユーザーの経験を考慮し、運用上単純で自動化されたフェールオーバー モードを探します。
  
ネットワーク、Office 365、ExpressRoute、および ExpressRoute プロバイダーの外部では、すべて異なるレベルの可用性があります。
  
### <a name="service-availability"></a>サービスの可用性
  
- Office 365サービスは、個々のサービスのアップタイムと可用性メトリックを含む、明確に定義されたサービス [レベル アグリーメント](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)によってカバーされます。 このような高いサービス可用性レベルOffice 365維持できる理由の 1 つは、グローバル Microsoft ネットワークを使用して、個々のコンポーネントが多数の Microsoft データセンター間でシームレスにフェールオーバーできる点です。 このフェールオーバーは、データセンターとネットワークから複数のインターネット エグレス ポイントに拡張され、サービスを使用しているユーザーの観点からシームレスにフェールオーバーを可能にします。

- ExpressRoute は、Microsoft Network Edge と ExpressRoute プロバイダーまたはパートナー インフラストラクチャ間の個々の専用回線に対して [99.9% の可用性 SLA を提供](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) します。 これらのサービス レベルは ExpressRoute 回線レベルで適用されます。これは、各ピアリングの場所にある冗長な Microsoft 機器とネットワーク プロバイダー機器の間の [2 つの独立した相互接続](/azure/expressroute/expressroute-introduction) で構成されます。

### <a name="provider-availability"></a>プロバイダーの可用性
  
- Microsoft のサービス レベルの取り決めは、ExpressRoute プロバイダーまたはパートナーで停止します。 これは、可用性レベルに影響を与える選択を行うことができる最初の場所でもあります。 ExpressRoute プロバイダーが提供するアーキテクチャ、可用性、回復性の特性は、各 Microsoft ピアリングの場所でネットワーク境界とプロバイダー接続の間で厳密に評価する必要があります。 冗長性、ピアリング機器、キャリア提供の WAN 回線、その他の付加価値により、NAT サービスやマネージド ファイアウォールなどのサービスが追加されるため、論理的および物理的な側面の両方に注意を払います。

### <a name="designing-your-availability-plan"></a>可用性プランの設計
  
Office 365のエンドツーエンド接続シナリオに対して高可用性と回復性を計画し、設計することを強くお勧めします。 デザインには次のものが含まれている必要があります。
  
- インターネット回線と ExpressRoute 回線の両方を含め、単一障害点はありません。

- 最も予想される障害モードの影響を受けるユーザーの数とその影響の期間を最小限に抑えます。

- 最も予想される障害モードからの単純で繰り返し可能な自動復旧プロセスを最適化します。

- 大幅に低下することなく、冗長パスを介してネットワーク トラフィックと機能の完全な要求をサポートします。

接続シナリオには、Office 365への複数の独立したアクティブなネットワーク パス用に最適化されたネットワーク トポロジが含まれている必要があります。 これにより、個々のデバイスまたは機器レベルの冗長性のみに最適化されたトポロジよりも、エンド ツー エンドの可用性が向上します。
  
> [!TIP]
> ユーザーが複数の大陸または地理的リージョンに分散されていて、それらの各場所が冗長 WAN 回線を介して単一の ExpressRoute 回線がある 1 つのオンプレミスの場所に接続する場合、ユーザーは、異なるリージョンを最も近いピアリングの場所に接続する独立した ExpressRoute 回線を含むネットワーク トポロジ設計よりも、エンド ツー エンドのサービスの可用性が低くなります。
  
各回線が異なる地理的ピアリングの場所に接続する ExpressRoute 回線を少なくとも 2 つプロビジョニングすることをお勧めします。 ユーザーが Office 365 サービスに ExpressRoute 接続を使用するすべてのリージョンに対して、このアクティブ/アクティブな回線ペアをプロビジョニングする必要があります。 これにより、データセンターやピアリングの場所などの主要な場所に影響を与える障害発生時に、各リージョンを接続したままにできます。 アクティブ/アクティブとして構成すると、エンド ユーザー トラフィックを複数のネットワーク パスに分散できます。 これにより、デバイスまたはネットワーク機器の停止中に影響を受けるユーザーの範囲が減少します。
  
インターネットで単一の ExpressRoute 回線をバックアップとして使用することはお勧めしません。
  
### <a name="example-2-failover-and-high-availability"></a>例 2: フェールオーバーと高可用性
  
Woodgrove Bank のマルチ地理的設計では、ルーティング、帯域幅、セキュリティのレビューが行われ、高可用性のレビューを行う必要があります。 Woodgrove では、高可用性は 3 つのカテゴリをカバーしていると考えています。回復性、信頼性、冗長性。
  
回復性により、Woodgrove は障害から迅速に回復できます。 信頼性により、Woodgrove はシステム内で一貫した結果を提供できます。 冗長性により、Woodgrove はインフラストラクチャの 1 つ以上のミラー化されたインスタンス間を移動できます。
  
各エッジ構成内で、Woodgrove には冗長なファイアウォール、プロキシ、IDS があります。 北米の場合、Woodgrove にはダラス データセンターに 1 つのエッジ構成があり、バージニア データセンターには別のエッジ構成があります。 各場所の冗長機器は、その場所に対する回復性を提供します。
  
Woodgrove Bank のネットワーク構成は、いくつかの重要な原則に基づいて構築されています。
  
- 各地理的リージョン内には、複数の Azure ExpressRoute 回線があります。

- リージョン内の各回線は、そのリージョン内のすべてのネットワーク トラフィックをサポートできます。

- ルーティングは、可用性、場所などに応じて、どちらか一方のパスを明確に優先します。

- Azure ExpressRoute 回線間のフェールオーバーは、Woodgrove で必要な追加の構成やアクションなしで自動的に行われます。

- インターネット回線間のフェールオーバーは、Woodgrove で必要な追加の構成やアクションなしで自動的に行われます。

この構成では、物理レベルと仮想レベルの冗長性を備えた Woodgrove Bank は、ローカルの回復性、リージョンの回復性、およびグローバルな回復性を信頼性の高い方法で提供できます。 Woodgrove は、リージョンごとに 1 つの Azure ExpressRoute 回線とインターネットにフェールオーバーする可能性を評価した後、この構成を選択しました。
  
Woodgrove がリージョンごとに複数の Azure ExpressRoute 回線を持つことができなかった場合、北米に発信されたトラフィックをアジア太平洋の Azure ExpressRoute 回線にルーティングすると、許容できないレベルの待機時間が追加され、必要な DNS フォワーダー構成が複雑になります。
  
バックアップ構成としてインターネットを使用することはお勧めしません。 これにより、Woodgrove の信頼性の原則が壊れ、接続を使用して一貫性のないエクスペリエンスが得られます。 また、構成されている BGP アドバタイズメント、NAT 構成、DNS 構成、プロキシ構成を考慮してフェールオーバーするには、手動構成が必要になります。 これにより、フェールオーバーの複雑さが増し、復旧にかかる時間が長くなり、関連する手順を診断およびトラブルシューティングする機能が低下します。
  
トラフィック管理または Azure ExpressRoute を計画して実装する方法については、まだ質問がありますか? [ネットワークとパフォーマンスに関するガイダンス](./network-planning-and-performance.md)の残りの部分または [Azure ExpressRoute に関する FAQ を参照してください](/azure/expressroute/expressroute-faqs)。
  
## <a name="working-with-azure-expressroute-providers"></a>Azure ExpressRoute プロバイダーの操作
<a name="BKMK_high-availability"> </a>

帯域幅、待機時間、セキュリティ、高可用性の計画に基づいて回線の場所を選択します。 最適な場所がわかったら、回線を配置して、 [リージョン別のプロバイダーの現在の一覧を確認](/azure/expressroute/expressroute-locations)します。
  
プロバイダーまたはプロバイダーと連携して、最適な接続オプション、ポイント対ポイント、マルチポイント、ホストを選択します。 帯域幅やその他の冗長コンポーネントがルーティングと高可用性の設計をサポートしている限り、接続オプションを組み合わせて一致させることができます。
  
ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>関連項目
<a name="BKMK_high-availability"> </a>

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)
  
[Office 365 向け Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)
  
[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)
  
[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)
  
[Office 365シナリオでの ExpressRoute での BGP コミュニティの使用](bgp-communities-in-expressroute.md)
  
[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online での ExpressRoute および QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute を使用したコール フロー](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Office 365 の URL および IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)
  
[Office 365 エンドポイントの FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)