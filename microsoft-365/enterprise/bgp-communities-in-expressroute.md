---
title: Office 365シナリオでの ExpressRoute での BGP コミュニティの使用
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Azure ExpressRoute で BGP コミュニティを使用して、IP プレフィックスの数と、Office 365シナリオに必要な帯域幅を管理する方法について説明します。
ms.openlocfilehash: 3e7ec6373299741cc1d34c18cc6be5b9366f3de6
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095776"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Office 365シナリオでの ExpressRoute での BGP コミュニティの使用

Azure ExpressRoute を使用してOffice 365に接続することは、Office 365 エンドポイントがデプロイされるネットワークを表す特定の IP サブネットの BGP アドバタイズに基づいています。 Office 365のグローバルな性質と、Office 365を構成するサービスの数のために、顧客は多くの場合、ネットワーク上で受け入れる広告を管理する必要があります。 IP サブネットの数を減らす。この記事の残りの部分を通じて IP プレフィックスと呼ばれる、BGP ネットワーク管理の用語に合わせて、お客様にとって次の最終目標を果たします。
  
- **承認済みのアドバタイズされた IP プレフィックスの数を管理** する - IP プレフィックスの数が制限されているだけの内部ネットワーク インフラストラクチャまたはネットワークキャリアをお持ちのお客様と、制限付き数を超えるプレフィックスを受け入れるために課金されるネットワーク通信事業者をお持ちのお客様は、ネットワークに既にアドバタイズされているプレフィックスの合計数を評価し、ExpressRoute に最適なOffice 365 アプリケーションを選択する必要があります。

- **Azure ExpressRoute 回線で必要な帯域幅の量を管理** する - お客様は、ExpressRoute パスとインターネット パスを介して、Office 365 サービスの帯域幅エンベロープを制御することができます。 これにより、お客様は、Skype for Businessなどの特定のアプリケーションに対して ExpressRoute 帯域幅を予約し、残りのOffice 365 アプリケーションをインターネット パス経由でルーティングできます。

これらの目標のお客様を支援するために、ExpressRoute 経由でアドバタイズされるOffice 365 IP プレフィックスには、次の例に示すように、サービス固有の BGP コミュニティ値がタグ付けされます。
  
> [!NOTE]
> 他のアプリケーションに関連付けられている一部のネットワーク トラフィックがコミュニティの価値に含まれることを期待する必要があります。 これは、共有サービスとデータセンターを使用するグローバル なサービスとしてのソフトウェアオファリングに対して想定される動作です。 これは、プレフィックス数や帯域幅を念頭に置いて管理する、上記の 2 つの目標で可能な限り最小限に抑えています。

|**サービス**|**BGP Community値**|**注**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Exchangeサービスと EOP サービスが含まれます\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business Online & Microsoft Teams サービス  <br/> |
|その他のOffice 365 サービス\*  <br/> |12076:5100  <br/> |Azure Active Directory (認証とディレクトリ同期のシナリオ) とポータル サービスOffice 365含まれています  <br/> |
|\*ExpressRoute に含まれるサービス シナリオの範囲については、[Office 365 エンドポイントに関する](./urls-and-ip-address-ranges.md)記事を参照してください。  <br/> \*\*今後、追加のサービスと BGP コミュニティの値が追加される可能性があります。 [BGP コミュニティの現在の一覧を参照してください](/azure/expressroute/expressroute-routing)。  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>BGP コミュニティを使用するための最も一般的なシナリオは何ですか?

お客様は BGP コミュニティを使用して、Azure ExpressRoute を介してネットワークによって受け入れられる IP プレフィックスのグループを規制し、特定のOffice 365 サービスの合計 IP プレフィックス数と予想される帯域幅エンベロープに影響を与える可能性があります。 Azure ExpressRoute または BGP コミュニティの使用に関係なく、すべてのOffice 365にインターネットにバインドされたトラフィックが必要であることを理解することが重要です。 この機能の最も一般的な用途は、次の 3 つのシナリオです。
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>シナリオ 1: Office 365 IP プレフィックスの数を最小限に抑える

Contoso Corporation は、現在、Exchange OnlineおよびSharePoint Online にOffice 365を使用している 50,000 人の会社です。 ExpressRoute の要件を確認する際に、Contoso は、多くの地域の場所にあるネットワーク デバイスが、100 を超える追加ルート エントリを超えるルーティング テーブル サイズを処理できないと判断します。 Contoso は、ExpressRoute がOffice 365 サービスの完全なセットに対してアドバタイズする IP プレフィックスの合計数を確認し、100 を超えると結論付けました。 100 個の追加ルート エントリを維持するために、Contoso は ExpressRoute for Office 365の使用を、ExpressRoute Microsoft ピアリングを通じて受信した SharePoint Online BGP コミュニティ値 (12076:5020) のみに範囲を設定します。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネット ルート**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint オンライン &amp; OneDrive for Business  <br/> | DNS、CRL、 &amp; CDN要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべてのOffice 365 サービス  <br/>  その他すべての Microsoft クラウド サービス  <br/>  Office 365 ポータル、Office 365認証、 &amp; ブラウザーでのOffice  <br/>  Exchange Online、Exchange Online Protection、Skype for Business Online  <br/> |

> [!NOTE]
> 各サービスのプレフィックス数を減らすには、サービス間の重複が最小限に抑えられます。 この動作は仕様です。
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>シナリオ 2: 一部のOffice 365 サービスに対する ExpressRoute と内部帯域幅の使用をスコーピングする

分散異種ネットワークを備えた大規模な多国籍企業である Fabrikam Inc は、以下を含む多くのOffice 365サービスのサブスクライバーです。Exchange Online、オンラインSharePoint、およびオンラインSkype for Business。 Fabrikam の内部ルーティング インフラストラクチャは、そのルーティング テーブルで数千の IP プレフィックスを処理できます。ただし、Fabrikam では、ネットワーク パフォーマンスに最も影響を受けやすいOffice 365 アプリケーションに対してのみ ExpressRoute と内部帯域幅をプロビジョニングし、他のすべてのOffice 365 アプリケーションに対して既存のインターネット帯域幅を使用する必要があります。
  
そのため、Fabrikam は Azure ExpressRoute 帯域幅を、ExpressRoute Microsoft ピアリングを通じて受信したオンライン BGP Community値 (12076:5030) のみをSkype for Businessするようにスコープを設定します。 Office 365に関連付けられている残りのネットワーク トラフィックでは、引き続きインターネットエグレス ポイントが使用されます。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネット ルート**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |SKYPE SIP シグナリング、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> | DNS、CRL、 &amp; CDN要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべてのOffice 365 サービス  <br/>  その他すべての Microsoft クラウド サービス  <br/>  Office 365 ポータル、Office 365認証、 &amp; ブラウザーでのOffice  <br/>  Skype for Businessテレメトリ、Skype クライアントのクイック ヒント、パブリック IM 接続  <br/>  Exchange Online、Exchange Online Protection、SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>シナリオ 3: Office 365 サービスに対してのみ Azure ExpressRoute をスコーピングする

Woodgrove Bank は、Office 365を含むいくつかの Microsoft クラウド サービスの顧客です。 ネットワーク容量と使用量を評価した後、Woodgrove Bank は、サポートされているOffice 365 サービスの優先パスとして Azure ExpressRoute をデプロイすることにしました。 ルーティング テーブルでは、Office 365 IP プレフィックスの完全なセットと、プロビジョニング済みの Azure ExpressRoute 回線が、すべての予想される帯域幅と待機時間のニーズをサポートできます。
  
Office 365以外の Microsoft クラウド サービスに関連付けられているネットワーク トラフィックを確保するために、Woodgrove Bank では、Office 365用 ExpressRoute の使用を、Office 365特定の BGP コミュニティ値 (12076:5010、12076:5020、12076:5030、12076:5100) に適用します。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネット ルート**|
|:-----|:-----|:-----|
|Exchange、Skype for Business & Microsoft Teams、SharePoint、&amp;その他のサービス  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp; Exchange Online Exchange Online Protection  <br/> SharePoint オンライン &amp; OneDrive for Business  <br/> SKYPE SIP シグナリング、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> Office 365 ポータル、Office 365認証、 &amp; ブラウザーでのOffice  <br/> | DNS、CRL、 &amp; CDN要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべてのOffice 365 サービス  <br/>  その他すべての Microsoft クラウド サービス  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>BGP コミュニティの使用に関する主な計画に関する考慮事項

BGP コミュニティを利用して、ExpressRoute のアドバタイズ方法と顧客ネットワーク経由での伝達方法に影響を与えるお客様は、次の考慮事項を考慮する必要があります。
  
- ネットワーク設計で BGP コミュニティを使用する場合は、ルートの対称性を維持することが重要です。 場合によっては、BGP コミュニティを追加または削除すると、対称ルーティングが切断され、対称ルーティングを再確立するためにルーティング構成を更新する必要がある状況が発生することがあります。

- BGP コミュニティ値を使用した Azure ExpressRoute のスコーピングは、お客様のアクションです。 Microsoft は、お客様が構成したスコープに関係なく、ピアリング関係に関連付けられているすべての IP プレフィックスをアドバタイズします。

- Azure ExpressRoute では、お客様が割り当てた BGP コミュニティに基づいて、Microsoft のネットワーク上のアクションはサポートされません。

- Office 365によって使用される IP プレフィックスは、サービス固有の BGP コミュニティ値でのみマークされ、場所固有の BGP コミュニティはサポートされません。 Office 365 サービスは本質的にグローバルであり、テナントの場所またはOffice 365 クラウド内のデータに基づくプレフィックスのフィルター処理はサポートされていません。 推奨される方法は、要求するOffice 365 サービスの IP アドレスの物理的な場所に関係なく、ユーザーのネットワークの場所から Microsoft グローバル ネットワークへの最短または最も優先されるネットワーク パスを調整するようにネットワークを構成することです。

- 各 BGP コミュニティ値に含まれる IP プレフィックスは、値に関連付けられたOffice 365 アプリケーションの IP アドレスを含むサブネットを表します。 場合によっては、複数のOffice 365 アプリケーションがサブネット内に IP アドレスを持ち、その結果、複数のコミュニティ値に存在する IP プレフィックスが生成される場合があります。 これは、割り当ての断片化による動作はまれですが、プレフィックス数や帯域幅管理の目標には影響しません。 お客様は、BGP コミュニティを利用して効果を最小限に抑えるために、"必要なものを拒否する" のではなく、"必要なものを許可する" アプローチ Office 365を使用することをお勧めします。

- BGP コミュニティを使用しても、基になるネットワーク接続の要件や、Office 365を使用するために必要な構成は変更されません。 Office 365にアクセスしたいお客様は、引き続きインターネットにアクセスできる必要があります。

- BGP コミュニティを使用した Azure ExpressRoute のスコーピングは、内部ネットワークが Microsoft ピアリング関係を介して表示できるルートにのみ影響します。 スコープ付きルーティングと組み合わせて PAC または WPAD 構成を使用するなど、追加のアプリケーション レベルの構成を行う必要がある場合があります。

- Microsoft によって割り当てられた BGP コミュニティを使用することに加えて、お客様は、内部ルーティングに影響を与えるために Azure ExpressRoute を通じて学習Office 365 IP プレフィックスに独自の BGP コミュニティを割り当てることを選択できます。 一般的なユース ケースでは、特定の ExpressRoute ピアリングの各場所を通じて学習したすべてのルートに場所ベースの BGP コミュニティを割り当て、その情報を顧客ネットワークの下流で使用して、Microsoft のネットワークへの最短または最も優先されるネットワーク パスを調整します。 お客様が割り当てた BGP コミュニティを ExpressRoute でOffice 365シナリオに使用することは、Microsoft の制御または可視性の範囲外です。

戻ってくるのに使用できる短いリンクを次に示します [https://aka.ms/bgpexpressroute365]()。
  
## <a name="related-topics"></a>関連項目

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)
  
[Office 365 向け Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)
  
[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)
  
[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)
  
[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online での ExpressRoute および QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute を使用したコール フロー](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)
  
[BGP コミュニティのサポート](/azure/expressroute/expressroute-routing)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute for Office 365 のトレーニング](https://channel9.msdn.com/series/aer)