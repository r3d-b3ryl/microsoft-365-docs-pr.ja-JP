---
title: ExpressRoute での BGP コミュニティの使用によるOffice 365シナリオ
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: Azure ExpressRoute で BGP コミュニティを使用して、複数のシナリオで必要な IP プレフィックスと必要な帯域幅の数を管理するOffice 365します。
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59177800"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>ExpressRoute での BGP コミュニティの使用によるOffice 365シナリオ

Azure ExpressRoute Office 365を使用したネットワークへの接続は、エンドポイントが展開されているネットワークを表す特定の IP サブネットの BGP アドバタイズOffice 365基づいて行います。 Office 365 のグローバルな性質と、Office 365 を構成するサービスの数により、顧客は多くの場合、ネットワーク上で受け入れる広告を管理する必要があります。 IP サブネットの数を減らす。この記事の残りの部分を通して IP プレフィックスと呼ばれる、BGP ネットワーク管理の用語に合わせて、お客様に次のエンド ゴールを提供します。
  
- アドバタイズされた IP プレフィックスの受け入れ数を管理する - 限られた数の **IP** プレフィックスのみをサポートする内部ネットワーク インフラストラクチャまたはネットワーク キャリアをお持ちのお客様と、限られた数を超えるプレフィックスを受け入れるネットワーク キャリアをお持ちのお客様は、ネットワークに既にアドバタイズされているプレフィックスの総数を評価し、ExpressRoute に最適な Office 365 アプリケーションを選択します。

- Azure ExpressRoute 回線で必要な帯域幅の量を管理する - お客様は **、ExpressRoute** パスとインターネット パスを使用して Office 365 サービスの帯域幅エンベロープを制御できます。 これにより、お客様は ExpressRoute 帯域幅を特定のアプリケーション (Skype for Businessなど) に予約し、Office 365アプリケーションをインターネット パス上にルーティングできます。

これらの目標を顧客に支援するために、ExpressRoute Office 365アドバタイズされる IP プレフィックスには、以下の例に示すように、サービス固有の BGP コミュニティ値がタグ付けされます。
  
> [!NOTE]
> 他のアプリケーションに関連付けられている一部のネットワーク トラフィックがコミュニティ値に含まれると予想する必要があります。 これは、共有サービスとデータセンターを備えたグローバル なソフトウェア as a Service オファリングに対して期待される動作です。 これは、上記の 2 つの目標で可能な限り最小限に抑え、プレフィックス数や帯域幅を管理します。

|**サービス**|**BGP Community値**|**メモ**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |サービスExchange EOP サービスを含む\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Businessオンライン & Microsoft Teams サービス  <br/> |
|その他Office 365サービス\*  <br/> |12076:5100  <br/> |ポータル Azure Active Directory (認証とディレクトリ同期のシナリオ) とポータル サービスOffice 365含まれます  <br/> |
|\*ExpressRoute に含まれるサービス シナリオの範囲については、「エンドポイントの[Office 365」に記載](./urls-and-ip-address-ranges.md)されています。  <br/> \*\*今後、追加のサービスと BGP コミュニティの値が追加される可能性があります。 [BGP コミュニティの現在のリストを参照してください](/azure/expressroute/expressroute-routing)。  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>BGP コミュニティを使用する最も一般的なシナリオは何ですか?

お客様は、BGP コミュニティを使用して、Azure ExpressRoute を通じてネットワークで受け入れられる IP プレフィックスのグループを調整し、特定の Office 365 サービスの総 IP プレフィックス数と予想帯域幅エンベロープに影響を与える可能性があります。 Azure ExpressRoute または BGP コミュニティOffice 365に関係なく、すべてのユーザーがインターネットにバインドされたトラフィックを必要としていることを理解することが重要です。 この機能の最も一般的な用途は、次の 3 つのシナリオです。
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>シナリオ 1: IP プレフィックスの数Office 365する

Contoso Corporation は 50,000 人の会社で、現在はオンラインおよびオンラインOffice 365にExchange OnlineをSharePointしています。 ExpressRoute 要件を確認する場合、Contoso 社は、多くの地域の場所にあるネットワーク デバイスが、100 を超える追加のルート エントリのルーティング テーブル サイズを処理できないと判断します。 Contoso 社は、ExpressRoute が一連の Office 365 サービスに対してアドバタイズする IP プレフィックスの総数を確認し、100 を超えると結論付けしました。 100 の追加のルート エントリの下に滞在するために、Contoso は Office 365 の ExpressRoute の使用を、ExpressRoute Microsoft ピアリングを通じて受信した SharePoint Online BGP コミュニティ値 12076:5020 に範囲を設定します。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute でルーティング可能な機能**|**インターネット ルートが必要**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePointオンライン &amp; OneDrive for Business  <br/> | &amp;DNS、CRL、CDN要求  <br/>  Azure ExpressRoute でOffice 365サポートされていない他のすべてのサービス  <br/>  その他のすべての Microsoft クラウド サービス  <br/>  Office 365ポータル、Office 365認証、Office &amp; ブラウザーでの認証  <br/>  Exchange Online、Exchange Online Protection、および Skype for Business Online  <br/> |

> [!NOTE]
> 各サービスのプレフィックス数を削減するために、サービス間の重複は最小限に抑えられます。 これは想定された動作です。
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>シナリオ 2: ExpressRoute と内部帯域幅の使用を一部のサービスにOffice 365する

Fabrikam Inc,分散異種ネットワークを持つ大規模な多国籍企業は、以下を含む多くのOffice 365加入者です。Exchange Online、SharePointオンライン、およびオンラインSkype for Businessします。 Fabrikam の内部ルーティング インフラストラクチャは、ルーティング テーブルで何千もの IP プレフィックスを処理できます。ただし、Fabrikam は、ネットワーク パフォーマンスに最も敏感な Office 365 アプリケーションに ExpressRoute と内部帯域幅をプロビジョニングし、他のすべての Office 365 アプリケーションに対して既存のインターネット帯域幅を使用する必要があります。
  
このため、Fabrikam は Azure ExpressRoute 帯域幅を、ExpressRoute Microsoft ピアリングを通じて受信した Skype for Business Online BGP Community 値 12076:5030 にスコープを設定します。 ネットワーク に関連付けられている残りのネットワーク Office 365は、引き続きインターネット出力ポイントを使用します。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute でルーティング可能な機能**|**インターネット ルートが必要**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |SkypeSIP シグナリング、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> | &amp;DNS、CRL、CDN要求  <br/>  Azure ExpressRoute でOffice 365サポートされていない他のすべてのサービス  <br/>  その他のすべての Microsoft クラウド サービス  <br/>  Office 365ポータル、Office 365認証、Office &amp; ブラウザーでの認証  <br/>  Skype for Business利用統計情報、Skypeクイック ヒント、パブリック IM 接続  <br/>  Exchange Online、Exchange Online Protection、およびオンラインSharePointする  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>シナリオ 3: Azure ExpressRoute のスコープOffice 365サービスのみ

Woodgrove Bank は、複数の Microsoft クラウド サービスの顧客Office 365。 ネットワーク容量と使用量を評価した Woodgrove Bank は、サポートされるサービスの優先パスとして Azure ExpressRoute を展開Office 365します。 ルーティング テーブルは、一連の Office 365 IP プレフィックスをサポートし、プロビジョニングした Azure ExpressRoute 回線は、すべての投影帯域幅と待機時間のニーズをサポートします。
  
Office 365 以外の Microsoft クラウド サービスに関連付けられたネットワーク トラフィックを確保するために、Woodgrove Bank は Office 365 用 ExpressRoute の使用を、Office 365 固有の BGP コミュニティ値 12076:5010、12076:5020、12076:5030、120776:5100 でタグ付けされたすべての IP プレフィックスに適用します。

|**使用される BGP コミュニティ タグ**|**Azure ExpressRoute でルーティング可能な機能**|**インターネット ルートが必要**|
|:-----|:-----|:-----|
|Exchange、Skype for Business & Microsoft Teams、SharePoint、その他 &amp; のサービス  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp;Exchange OnlineExchange Online Protection  <br/> SharePointオンライン &amp; OneDrive for Business  <br/> SkypeSIP シグナリング、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> Office 365ポータル、Office 365認証、Office &amp; ブラウザーでの認証  <br/> | &amp;DNS、CRL、CDN要求  <br/>  Azure ExpressRoute でOffice 365サポートされていない他のすべてのサービス  <br/>  その他のすべての Microsoft クラウド サービス  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>BGP コミュニティの使用に関する主な計画上の考慮事項

BGP コミュニティを利用して、ExpressRoute のアドバタイズ方法と顧客ネットワーク経由での伝達方法に影響を与える場合は、次の点を考慮する必要があります。
  
- ネットワーク設計で BGP コミュニティを使用する場合は、ルートの対称性を維持することが重要です。 場合によっては、BGP コミュニティを追加または削除すると、対称ルーティングが壊れ、対称ルーティングを再確立するためにルーティング構成を更新する必要がある場合があります。

- BGP コミュニティ値を使用して Azure ExpressRoute をスコープ化する方法は、お客様の操作です。 Microsoft は、お客様が構成したスコープに関係なく、ピアリング関係に関連付けられているすべての IP プレフィックスをアドバタイズします。

- Azure ExpressRoute は、お客様に割り当てられた BGP コミュニティに基づく Microsoft のネットワーク上のアクションをサポートしています。

- サービスによって使用される IP プレフィックスOffice 365サービス固有の BGP コミュニティ値でのみマークされ、場所固有の BGP コミュニティはサポートされません。 Office 365サービスはグローバルな性質上、テナントの場所やクラウド内のデータに基づいてプレフィックスをフィルター処理Office 365サポートされていません。 推奨される方法は、要求する Office 365 サービスの IP アドレスの物理的な場所に関係なく、ユーザーのネットワークの場所から Microsoft グローバル ネットワークへの最短または最も優先されるネットワーク パスを調整するためにネットワークを構成します。

- 各 BGP コミュニティ値に含まれる IP プレフィックスは、その値に関連付けられているアプリケーションの IP Office 365を含むサブネットを表します。 場合によっては、複数のアプリケーションOffice 365 IP アドレスがサブネット内に含まれます。その結果、複数のコミュニティ値に IP プレフィックスが含まれます。 これは、割り当ての断片化による動作はめったにありませんが、プレフィックス数や帯域幅管理の目標には影響しません。 Office 365 の BGP コミュニティを利用して効果を最小限に抑える場合は、「不要な情報を拒否する」のではなく、「必要な操作を許可する」方法を使用してください。

- BGP コミュニティを使用しても、ネットワーク接続の使用に必要な基になるネットワーク接続要件や構成Office 365。 インターネットにアクセスするOffice 365ユーザーは、引き続きインターネットにアクセスできる必要があります。

- AZURE ExpressRoute を BGP コミュニティでスコープ設定すると、内部ネットワークが Microsoft ピアリング関係を通して確認できるルートにのみ影響します。 スコープ付きルーティングと組み合わせて PAC または WPAD 構成の使用など、アプリケーション レベルの構成を追加する必要がある場合があります。

- Microsoft に割り当てられた BGP コミュニティの使用に加えて、Azure ExpressRoute で学習した Office 365 IP プレフィックスに独自の BGP コミュニティを割り当て、内部ルーティングに影響を与える場合があります。 一般的な使用例は、場所ベースの BGP コミュニティを、特定の ExpressRoute ピアリングの各場所で学習したすべてのルートに割り当て、その情報を顧客ネットワークの下流で使用して、Microsoft のネットワークへの最短または最も優先されるネットワーク パスを調整します。 お客様が割り当てられた BGP コミュニティを ExpressRoute で使用Office 365、Microsoft の制御や可視性の範囲を外しています。

戻って来るのに使用できる短いリンクを次に示します [https://aka.ms/bgpexpressroute365]() 。
  
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