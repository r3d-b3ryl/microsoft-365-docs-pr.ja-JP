---
title: Office 365 向け ExpressRoute のネットワーク計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: この記事では、Azure ExpressRoute for Office 365ネットワーク計画に利用する方法について説明します。
ms.openlocfilehash: e087afee52893b0be48e4024c619e3599f54338d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177065"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Office 365 向け ExpressRoute のネットワーク計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ExpressRoute for Office 365ネットワークと Microsoft のデータセンター間のレイヤー 3 接続を提供します。 回線は、クライアントのフロントエンド サーバーのボーダー ゲートウェイ プロトコル (BGP) Office 365アドバタイズを使用します。 オンプレミス デバイスの観点から、Office 365 への正しい TCP/IP パスを選択する必要がある場合、Azure ExpressRoute はインターネットの代替手段と見なされます。
  
Azure ExpressRoute は、Microsoft のデータセンター内のサーバーによって提供される、サポートされている機能とサービスの特定のセットOffice 365パスを追加します。 Azure ExpressRoute は、Microsoft データセンターへのインターネット接続や、ドメイン名解決などの基本的なインターネット サービスを置き換える必要はありません。 Azure ExpressRoute とインターネット回線をセキュリティで保護し、冗長化する必要があります。
  
次の表は、インターネット接続と Azure ExpressRoute 接続の違いを示しています。Office 365。

|**ネットワーク計画の違い**|**インターネット ネットワーク接続**|**ExpressRoute ネットワーク接続**|
|:-----|:-----|:-----|
| 必要なインターネット サービスへのアクセス(以下を含む)。  <br/>  DNS 名解決  <br/>  証明書失効の検証  <br/>  コンテンツ配信ネットワーク (CDN)  <br/> |はい  <br/> |Microsoft が所有する DNS および/またはインフラストラクチャへの要求CDN ExpressRoute ネットワークを使用する場合があります。  <br/> |
| 以下をOffice 365サービスへのアクセス。  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Officeで使用する  <br/>  Office 365ポータルと認証  <br/> |はい、すべてのアプリケーションと機能  <br/> |はい、 [特定のアプリケーションと機能](./urls-and-ip-address-ranges.md) <br/> |
|境界内のオンプレミス のセキュリティ。  <br/> |はい  <br/> |はい  <br/> |
|高可用性の計画。  <br/> |代替インターネット ネットワーク接続へのフェールオーバー  <br/> |代替 ExpressRoute 接続へのフェールオーバー  <br/> |
|予測可能なネットワーク プロファイルとの直接接続。  <br/> |いいえ  <br/> |はい  <br/> |
|IPv6 接続。  <br/> |はい  <br/> |はい  <br/> |

ネットワーク計画の詳細については、以下のタイトルを展開してください。 さらに、10 部構成の Azure [ExpressRoute](https://channel9.msdn.com/series/aer)を、より深く掘り下Office 365トレーニング シリーズ用に記録しました。

## <a name="existing-azure-expressroute-customers"></a>既存の Azure ExpressRoute のお客様

既存の Azure ExpressRoute 回線を使用し、この回線に Office 365 接続を追加する場合は、回線の数、出力場所、およびサイズを確認して、Office 365 使用法のニーズを満たすことができます。 ほとんどのお客様は追加の帯域幅を必要とします。多くは追加の回線を必要とします。
  
既存の Azure ExpressRoute 回線Office 365アクセスを有効にするには、ルート フィルター[](/azure/expressroute/how-to-routefilter-portal)を構成して、サービスにアクセスOffice 365確認します。
  
Azure ExpressRoute サブスクリプションは顧客中心で、サブスクリプションは顧客に関連付けされます。 お客様は、複数の Azure ExpressRoute 回線を使用して、それらの回線を通して多くの Microsoft クラウド リソースにアクセスできます。 たとえば、Azure ホスト型仮想マシン、Office 365 テスト テナント、および 2 組の冗長 Azure ExpressRoute 回線を使用して Office 365 実稼働テナントにアクセスできます。
  
次の表に、回線上で実装できるピアリング関係の 2 種類の概要を示します。

|**ピアリング関係**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**サービス** <br/> |IaaS: Azure 仮想マシン  <br/> |PaaS: Azure パブリック サービス  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|接続の開始**** <br/> |顧客から Microsoft へのアクセス  <br/> Microsoft-to-Customer  <br/> |顧客から Microsoft へのアクセス  <br/> Microsoft-to-Customer  <br/> |
|**QoS のサポート** <br/> |QoS なし  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup>QoS では、Skype for Businessのみサポートされます。
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Azure ExpressRoute の帯域幅計画

すべての Office 365 顧客は、各場所の人数、各 Office 365 アプリケーションでのアクティブな状態、オンプレミスまたはハイブリッド機器の使用、ネットワーク セキュリティ構成などの他の要因に応じて、固有の帯域幅ニーズを持っています。
  
帯域幅が少なすぎると、輻輳、データの再送信、予期しない遅延が発生します。 帯域幅が多すぎると、不必要なコストが発生します。 既存のネットワークでは、回線で利用可能なヘッドルームの量をパーセンテージで表す場合が多い。 10% のヘッドルームを使用すると、混雑が発生する可能性が高く、80% のヘッドルームを持つことは、通常、不要なコストを意味します。 一般的なヘッドルームターゲットの割り当ては、20% ~ 50% です。
  
適切なレベルの帯域幅を見つけるには、既存のネットワーク使用量をテストする方法が最適です。 これは、すべてのネットワーク構成とアプリケーションがいくつかの点で一意であるので、実際の使用状況と必要性を得る唯一の方法です。 測定する場合は、ネットワークのニーズを理解するために、帯域幅の総消費、待機時間、および TCP 輻輳に細心の注意を払う必要があります。
  
すべてのネットワーク アプリケーションを含む推定基準計画を作成したら、組織内のユーザーの異なるプロファイルを構成する小さなグループを持つパイロット Office 365 を使用して実際の使用状況を判断し、2 つの測定値を使用して、各オフィスの場所に必要な帯域幅の量を推定します。 テストで遅延や TCP 輻輳の問題が見つかった場合は、Office 365 を使用しているユーザーの近くに出力を移動するか、SSL 復号化/検査などの集中的なネットワーク スキャンを削除する必要があります。
  
推奨されるネットワーク処理の種類に関する推奨事項はすべて、ExpressRoute 回線とインターネット回線の両方に適用されます。 パフォーマンス チューニング サイトのガイダンスの残りの部分でも [同様です](./network-planning-and-performance.md)。
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Azure ExpressRoute にセキュリティ制御を適用して、シナリオOffice 365する

Azure ExpressRoute 接続のセキュリティ保護は、インターネット接続のセキュリティ保護と同じ原則から始まります。 多くのお客様は、オンプレミス ネットワークをネットワークと他の Microsoft クラウドに接続する ExpressRoute パスに沿ってネットワークと境界Office 365展開します。 これらのコントロールには、ファイアウォール、アプリケーション プロキシ、データ漏洩防止、侵入検知、侵入防止システムなどがあります。 多くの場合、お客様は、Microsoft に行くオンプレミスから開始されるトラフィックと、Microsoft から顧客のオンプレミス ネットワークに行くトラフィックと、一般的なインターネット接続先へのオンプレミスから開始されるトラフィックに対して、さまざまなレベルのコントロールを適用します。
  
展開する [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) 接続モデルとセキュリティを統合する例を次に示します。

|**ExpressRoute 統合オプション**|**ネットワーク セキュリティ境界モデル**|
|:-----|:-----|
|Cloud Exchange でのコロケーション  <br/> |ExpressRoute 接続が確立されているコロケーション機能に、新しいセキュリティ/境界インフラストラクチャをインストールするか、既存のセキュリティ/境界インフラストラクチャを活用します。  <br/> 同じ場所の施設を、ルーティング/相互接続の目的と、同じ場所の施設からオンプレミスのセキュリティ/境界インフラストラクチャへのバックホール接続のために、純粋に活用します。  <br/> |
|ポイント間イーサネット  <br/> |既存のオンプレミスのセキュリティ/境界インフラストラクチャの場所で、ポイント間 ExpressRoute 接続を終了します。  <br/> ExpressRoute パスに固有の新しいセキュリティ/境界インフラストラクチャをインストールし、ポイント間接続を終了します。  <br/> |
|Any-to-Any IPVPN  <br/> |ExpressRoute の接続に使用される IPVPN に出力する、すべての場所にある既存のオンプレミスのセキュリティ/境界インフラストラクチャOffice 365活用します。  <br/> ExpressRoute に使用する IPVPN を、セキュリティOffice 365として指定された特定のオンプレミスの場所にヘアピンします。  <br/> |

一部のサービス プロバイダーは、Azure ExpressRoute との統合ソリューションの一部として、マネージ セキュリティ/境界機能も提供します。
  
ExpressRoute に使用するネットワーク/セキュリティ境界オプションのトポロジの配置を検討する場合は、Office 365の考慮事項を次に示します。
  
- ネットワーク/セキュリティコントロールの深度と種類は、ユーザー エクスペリエンスのパフォーマンスとスケーラビリティに影響を与Office 365があります。

- 送信 (オンプレミス- \> Microsoft) と受信 (Microsoft- オンプレミス) [有効な場合] フローの要件が \> 異なる場合があります。 これらは、一般的なインターネットの宛先への送信とは異なる可能性があります。

- Office 365/プロトコルおよび必要な IP サブネットに関する要件は、トラフィックが ExpressRoute 経由でルーティングされる場合とインターネット経由でルーティングOffice 365同じです。

- お客様のネットワーク/セキュリティ制御のトポロジ的な配置は、ユーザーと Office 365 サービスの間の最終的なエンド to エンド ネットワークを決定し、ネットワークの遅延と輻輳に大きな影響を与える可能性があります。

- お客様は、冗長性、高可用性、および障害復旧のベスト プラクティスに従って、Office 365 用 ExpressRoute で使用するセキュリティ/境界トポロジを設計してください。

ここでは、さまざまな Azure ExpressRoute 接続オプションと、上記で説明した境界セキュリティ モデルを比較する Woodgrove Bank の例を示します。
  
### <a name="example-1-securing-azure-expressroute"></a>例 1: Azure ExpressRoute のセキュリティ保護
  
Woodgrove Bank は Azure ExpressRoute の実装を検討し、Office 365 の[ExpressRoute](routing-with-expressroute.md)によるルーティングに最適なアーキテクチャを計画した後、帯域幅要件を理解するために上記のガイダンスを使用した後、境界を保護するための最適な方法を決定しています。
  
複数の大陸に複数の場所を持つ複数の国の組織である Woodgrove では、セキュリティがすべての境界にまたがる必要があります。 Woodgrove の最適な接続オプションは、世界中の複数のピアリング場所との複数ポイント接続で、各大陸の従業員のニーズに対応します。 各大陸には、大陸内の冗長な Azure ExpressRoute 回線が含まれています。セキュリティはこれらすべてにまたがる必要があります。
  
Woodgrove の既存のインフラストラクチャは信頼性が高く、追加作業を処理できます。その結果、Woodgrove Bank は Azure ExpressRoute およびインターネット境界セキュリティにインフラストラクチャを使用できます。 そうでなかった場合、Woodgrove は既存の機器を補う、または別の種類の接続を処理するために追加の機器を購入することができます。
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Azure ExpressRoute を使用した高可用性とフェールオーバー
<a name="BKMK_high-availability"> </a>

ExpressRoute を使用して、各出力から ExpressRoute プロバイダーに少なくとも 2 つのアクティブ回線をプロビジョニングすることをお勧めします。 これは、お客様にエラーが発生する最も一般的な場所であり、アクティブ/アクティブな ExpressRoute 回線のペアをプロビジョニングすることで簡単に回避できます。 また、多くのサービスがインターネット上でのみ利用Office 365、少なくとも 2 つのアクティブ/アクティブ なインターネット回線を使用することをお勧めします。
  
ネットワークの出力ポイントの内部には、他の多くのデバイスや回線が含め、ユーザーが可用性を認識する方法において重要な役割を果たします。 接続シナリオのこれらの部分は、ExpressRoute または Office 365 SLA ではカバーされませんが、組織内のユーザーが認識するサービスの可用性をエンド エンドで重要な役割を果たします。
  
Office 365 を使用して操作しているユーザーに焦点を当て、1 つのコンポーネントに障害が発生すると、サービスを使用するユーザーのエクスペリエンスに影響を与える場合は、影響を受けるユーザーの合計割合を制限する方法を探します。 フェールオーバー モードが運用上複雑な場合は、復旧に長い時間の人々の経験を考慮し、操作上単純で自動化されたフェールオーバー モードを探します。
  
ネットワークの外部では、Office 365 ExpressRoute プロバイダー、および ExpressRoute プロバイダーは、すべて異なるレベルの可用性を持ちます。
  
### <a name="service-availability"></a>サービスの可用性
  
- Office 365サービスは、個々のサービスのアップタイム[](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)と可用性の指標を含む、よく定義されたサービス レベル契約によってカバーされます。 このような高Office 365を維持できる理由の 1 つは、グローバル Microsoft ネットワークを使用して、多数の Microsoft データセンター間で個々のコンポーネントがシームレスにフェールオーバーできる機能です。 このフェールオーバーは、データセンターとネットワークから複数のインターネット出力ポイントに拡張され、サービスを使用しているユーザーの観点からシームレスにフェールオーバーできます。

- ExpressRoute は、Microsoft ネットワーク エッジと ExpressRoute プロバイダーまたはパートナー インフラストラクチャの間の個別の専用回線に [99.9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) の可用性 SLA を提供します。 これらのサービス レベルは ExpressRoute 回線レベルで適用されます。これは[](/azure/expressroute/expressroute-introduction)、冗長な Microsoft 機器と各ピアリング場所のネットワーク プロバイダー機器との間の 2 つの独立した相互接続で構成されます。

### <a name="provider-availability"></a>プロバイダーの可用性
  
- Microsoft のサービス レベルの取り決めは、ExpressRoute プロバイダーまたはパートナーで停止します。 また、可用性レベルに影響を与える選択肢を選び出す最初の場所です。 ネットワーク境界と各 Microsoft ピアリングの場所でのプロバイダー接続の間で ExpressRoute プロバイダーが提供するアーキテクチャ、可用性、および復元特性を詳細に評価する必要があります。 冗長性、ピアリング機器、キャリア提供の WAN 回線、NAT サービスや管理ファイアウォールなどの追加の付加価値サービスの論理的側面と物理的側面の両方に細心の注意を払います。

### <a name="designing-your-availability-plan"></a>可用性計画の設計
  
可用性と復元性を計画し、設計し、エンド to エンドの接続シナリオに合Office 365。 デザインには、次のものが含まれる必要があります。
  
- インターネット回線と ExpressRoute 回線の両方を含む単一障害点はありません。

- 最も予想されるエラー モードに対して、影響を受けるユーザーの数と影響期間を最小限に抑えます。

- 最も予想される障害モードからの単純、反復可能、および自動回復プロセスの最適化。

- 冗長パスを通じてネットワーク トラフィックと機能の完全な要求をサポートします。大幅な低下は発生しません。

接続シナリオには、複数の独立したアクティブなネットワーク パスに最適化されたネットワーク トポロジを含Office 365。 これにより、個々のデバイスまたは機器レベルでの冗長性のみを最適化するトポロジよりも、エンドツーエンドの可用性が向上します。
  
> [!TIP]
> ユーザーが複数の大陸または地理的地域に分散され、それらの各場所が冗長 WAN 回線を越えて単一の ExpressRoute 回線がある単一のオンプレミスの場所に接続する場合、ユーザーは、異なる地域を最も近いピアリング場所に接続する独立した ExpressRoute 回線を含むネットワーク トポロジ設計よりもエンド ツー エンドのサービス可用性が少なくなっています。
  
異なる地理的ピアリングの場所に接続する各回線で、少なくとも 2 つの ExpressRoute 回線をプロビジョニングすることをお勧めします。 このアクティブ/アクティブな回線のペアは、ユーザーが ExpressRoute 接続を使用してサービスを構成する地域ごとにOffice 365必要があります。 これにより、データセンターやピアリングの場所などの主要な場所に影響を与える災害時に、各地域が接続された状態を維持できます。 アクティブ/アクティブとして構成すると、エンド ユーザー トラフィックを複数のネットワーク パスに分散できます。 これにより、デバイスまたはネットワーク機器の停止中に影響を受けるユーザーの範囲が減少します。
  
インターネットをバックアップとして 1 つの ExpressRoute 回線を使用することをお勧めしません。
  
### <a name="example-2-failover-and-high-availability"></a>例 2: フェールオーバーと高可用性
  
Woodgrove Bank の複数地域設計では、ルーティング、帯域幅、セキュリティのレビューが行なえ、高可用性のレビューを行う必要があります。 Woodgrove では、高可用性は 3 つのカテゴリをカバーすると考えています。復元性、信頼性、冗長性を実現します。
  
復元により、Woodgrove は障害から迅速に回復できます。 信頼性により、Woodgrove はシステム内で一貫した結果を提供できます。 冗長性により、Woodgrove は 1 つ以上のミラーリングされたインフラストラクチャ インスタンス間を移動できます。
  
各エッジ構成内で、Woodgrove には冗長ファイアウォール、プロキシ、IDS があります。 北アメリカでは、Woodgrove はダラスのデータセンターにエッジ構成を 1 つ、バージニア データセンターに別のエッジ構成を持ちます。 各場所の冗長な機器は、その場所に対する回復性を提供します。
  
Woodgrove Bank のネットワーク構成は、いくつかの主要な原則に基づいて構築されています。
  
- 各地域内には、複数の Azure ExpressRoute 回線があります。

- 領域内の各回線は、その地域内のすべてのネットワーク トラフィックをサポートできます。

- ルーティングは、可用性、場所などによって、一方または他のパスを明確に優先します。

- Azure ExpressRoute 回線間のフェールオーバーは、Woodgrove で必要な追加の構成やアクションなしで自動的に行われます。

- インターネット回線間のフェールオーバーは、Woodgrove で必要な追加の構成やアクションなしで自動的に行われます。

この構成では、物理レベルと仮想レベルでの冗長性を備え、Woodgrove Bank はローカルの復元力、地域の回復力、およびグローバルな復元性を信頼性の高い方法で提供できます。 Woodgrove は、地域ごとに 1 つの Azure ExpressRoute 回線を評価し、インターネットにフェールオーバーする可能性を評価した後、この構成を選択しました。
  
Woodgrove がリージョンごとに複数の Azure ExpressRoute 回線を持てない場合、北米からアジア太平洋の Azure ExpressRoute 回線へのルーティング トラフィックは許容できないレベルの待機時間を追加し、必要な DNS 転送側の構成は複雑さを追加します。
  
バックアップ構成としてインターネットを活用する方法は推奨されません。 これにより、Woodgrove の信頼性の原則が破られるので、接続を使用したエクスペリエンスが一貫性がありません。 さらに、構成済みの BGP アドバタイズメント、NAT 構成、DNS 構成、およびプロキシ構成を考慮してフェールオーバーするには、手動構成が必要になります。 これにより、フェールオーバーの複雑性が増し、回復時間が増加し、関連する手順を診断およびトラブルシューティングする能力が低下します。
  
トラフィック管理または Azure ExpressRoute を計画して実装する方法について、まだ質問がありますか? ネットワークとパフォーマンスのガイダンスの残りの [部分、](./network-planning-and-performance.md) または Azure ExpressRoute に関する [FAQ をお読みください](/azure/expressroute/expressroute-faqs)。
  
## <a name="working-with-azure-expressroute-providers"></a>Azure ExpressRoute プロバイダーの操作
<a name="BKMK_high-availability"> </a>

帯域幅、待機時間、セキュリティ、高可用性の計画に基づいて回線の場所を選択します。 最適な場所がわかったら、回線を配置する場合は、地域別のプロバイダーの現在のリスト [を確認します](/azure/expressroute/expressroute-locations)。
  
プロバイダーまたはプロバイダーと一緒に、最適な接続オプション、ポイント対ポイント、マルチポイント、またはホスト型を選択します。 帯域幅や他の冗長コンポーネントがルーティングと高可用性の設計をサポートしている限り、接続オプションを混在して一致できます。
  
ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>関連項目
<a name="BKMK_high-availability"> </a>

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)
  
[Office 365 向け Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)
  
[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)
  
[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)
  
[ExpressRoute での BGP コミュニティの使用によるOffice 365シナリオ](bgp-communities-in-expressroute.md)
  
[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online 向けのネットワークの最適化](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online での ExpressRoute および QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute を使用したコール フロー](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Office 365 の URL および IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 のネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)
  
[Office 365 エンドポイントの FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)