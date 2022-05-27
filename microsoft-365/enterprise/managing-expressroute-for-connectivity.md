---
title: Office 365 向け ExpressRoute の接続を管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: プレフィックス のフィルター処理、セキュリティ、コンプライアンスなどの構成に共通する領域を含む、Office 365用の ExpressRoute を管理する方法について説明します。
ms.openlocfilehash: 493a7c0ca14d05a2b84763b9e9485f828574a930
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65753872"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Office 365 向け ExpressRoute の接続を管理する

ExpressRoute for Office 365は、インターネットに送信するすべてのトラフィックを必要とせずに、多くのOffice 365 サービスに到達するための代替ルーティング パスを提供します。 Office 365へのインターネット接続は引き続き必要ですが、ネットワークに他の構成がない限り、ネットワークへの BGP 経由で Microsoft がアドバタイズする特定のルートにより、ExpressRoute 回線が優先されます。 このルーティングを管理するために構成する 3 つの一般的な領域には、プレフィックスのフィルター処理、セキュリティ、およびコンプライアンスが含まれます。
  
> [!NOTE]
> Microsoft は、Azure ExpressRoute の Microsoft ピアリング ルーティング ドメインのレビュー方法を変更しました。 2017 年 7 月 31 日から、すべての Azure ExpressRoute のお客様は、Azure 管理コンソールまたは PowerShell から直接 Microsoft ピアリングを有効にすることができます。 Microsoft ピアリングを有効にした後、すべてのお客様は、Dynamics 365 Customer Engagement アプリケーション (旧称 CRM Online) の BGP ルートアドバタイズを受信するルート フィルターを作成できます。 Office 365用に Azure ExpressRoute を必要とするお客様は、Office 365のルート フィルターを作成する前に、Microsoft からレビューを取得する必要があります。 ExpressRoute を有効にするためのレビューを要求する方法については、Microsoft アカウント チームOffice 365問い合わせてください。 Office 365のルート フィルターを作成しようとしている未承認のサブスクリプションに[エラー メッセージが表示](https://support.microsoft.com/kb/3181709)される
  
## <a name="prefix-filtering"></a>プレフィックス のフィルター処理

Microsoft は、お客様が Microsoft からアドバタイズされたすべての BGP ルートを受け入れることをお勧めします。提供されるルートは厳格なレビューと検証プロセスを受け、追加された精査に対する利点を排除します。 ExpressRoute では、IP プレフィックスの所有権、整合性、スケールなどの推奨される制御がネイティブに提供され、顧客側では受信ルートのフィルター処理は行われません。
  
ExpressRoute パブリック ピアリング全体のルート所有権の追加検証が必要な場合は、 [Microsoft のパブリック IP 範囲](https://www.microsoft.com/download/details.aspx?id=53602)を表すすべての IPv4 および IPv6 IP プレフィックスの一覧に対してアドバタイズされたルートを確認できます。 これらの範囲は、Microsoft の完全なアドレス空間をカバーし、頻繁に変更されることが少なく、信頼性の高い一連の範囲を提供し、それに対してフィルターを適用することで、Microsoft 以外の所有ルートが環境に漏えいすることを懸念しているお客様に対する追加の保護も提供します。 変更が発生した場合は、月の 1 日に行われ、ファイルが更新されるたびにページの **詳細** セクションのバージョン番号が変更されます。
  
プレフィックス フィルター リストを生成するために[、Office 365 URL と IP アドレス範囲](./urls-and-ip-address-ranges.md)を使用しないようにするには、多くの理由があります。 次を含めます。
  
- Office 365 IP プレフィックスは、頻繁に多くの変更を受けます。

- Office 365 URL と IP アドレス範囲は、ルーティングではなく、ファイアウォール許可リストとプロキシ インフラストラクチャを管理するように設計されています。

- Office 365 URL と IP アドレス範囲には、ExpressRoute 接続のスコープ内にある可能性がある他のMicrosoft サービスは含まれません。

|**オプション**|**複雑さ**|**コントロールの変更**|
|:-----|:-----|:-----|
|すべての Microsoft ルートを受け入れる  <br/> |**低：** お客様は、すべてのルートが適切に所有されていることを確認するために、Microsoft コントロールに依存しています。  <br/> |なし  <br/> |
|Microsoft 所有のスーパーネットをフィルター処理する  <br/> |**媒体：** お客様は、Microsoft 所有のルートのみを許可するように、要約されたプレフィックス フィルター リストを実装しています。  <br/> |お客様は、頻度の低い更新プログラムがルート フィルターに反映されていることを確認する必要があります。  <br/> |
|Office 365 IP 範囲をフィルター処理する  <br/> [!CAUTION] Not-Recommended |**高：** お客様は、定義済みのOffice 365 IP プレフィックスに基づいてルートをフィルター処理します。  <br/> |お客様は、毎月の更新に対して堅牢な変更管理プロセスを実装する必要があります。  <br/> [!CAUTION] このソリューションには、継続的な大幅な変更が必要です。 時間内に実装されていない変更により、サービスが停止する可能性があります。   |

Azure ExpressRoute を使用してOffice 365に接続することは、Office 365 エンドポイントがデプロイされるネットワークを表す特定の IP サブネットの BGP アドバタイズに基づいています。 Office 365のグローバルな性質と、Office 365を構成するサービスの数のために、顧客は多くの場合、ネットワーク上で受け入れる広告を管理する必要があります。 環境にアドバタイズされるプレフィックスの数に関心がある場合は、[BGP コミュニティ](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099)機能を使用して、特定の一連のOffice 365 サービスにアドバタイズをフィルター処理できます。 この機能はプレビュー段階です。
  
Microsoft からの BGP ルートアドバタイズメントを管理する方法に関係なく、インターネット回線経由でOffice 365に接続する場合と比較して、Office 365 サービスに特別な影響を受けることはありません。 Microsoft は、お客様がOffice 365に接続するために使用する回線の種類に関係なく、同じセキュリティ、コンプライアンス、およびパフォーマンス レベルを維持します。
  
### <a name="security"></a>セキュリティ

ExpressRoute のパブリックおよび Microsoft ピアリングとの間の接続には、Office 365 サービスとの間の接続を含む独自のネットワークおよびセキュリティ境界制御を維持することをお勧めします。 セキュリティ制御は、ネットワークから Microsoft のネットワークに送信され、Microsoft のネットワークからネットワークに受信されるネットワーク要求に対して行われる必要があります。
  
#### <a name="outbound-from-customer-to-microsoft"></a>お客様から Microsoft への送信
  
コンピューターがOffice 365に接続すると、インターネット回線または ExpressRoute 回線経由で接続されるかどうかに関係なく、コンピューターは同じエンドポイント セットに接続します。 使用されている回線に関係なく、Microsoft では、Office 365 サービスを一般的なインターネットの宛先よりも信頼できるものとして扱うようにお勧めします。 送信セキュリティ制御は、露出を減らし、継続的なメンテナンスを最小限に抑えるために、ポートとプロトコルに焦点を当てる必要があります。 必要なポート情報については、[Office 365 エンドポイントの](./urls-and-ip-address-ranges.md)リファレンス記事を参照してください。
  
追加されたコントロールについては、プロキシ インフラストラクチャ内で FQDN レベルのフィルター処理を使用して、インターネットまたはOffice 365宛ての一部またはすべてのネットワーク要求を制限または検査できます。 機能がリリースされ、Office 365オファリングの進化に伴って FQDN の一覧を維持するには、より堅牢な変更管理と、公開された[Office 365 エンドポイント](./urls-and-ip-address-ranges.md)への変更の追跡が必要です。
  
> [!CAUTION]
> microsoft では、Office 365への送信セキュリティを管理するために IP プレフィックスのみに依存しないことをお勧めします。

|**オプション**|**複雑さ**|**コントロールの変更**|
|:-----|:-----|:-----|
|制限なし  <br/> |**低：** お客様は、Microsoft への無制限のアウトバウンド アクセスを許可します。  <br/> |なし  <br/> |
|ポートの制限  <br/> |**低：** お客様は、予想されるポートによって Microsoft への送信アクセスを制限します。  <br/> |まれ。  <br/> |
|FQDN の制限  <br/> |**高：** お客様は、発行された FQDN に基づいてOffice 365への送信アクセスを制限します。  <br/> |毎月の変更。  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Microsoft から顧客への受信
  
Microsoft がネットワークへの接続を開始する必要があるオプションのシナリオがいくつかあります。
  
- サインインのパスワード検証中の ADFS。

- [ハイブリッド展開をExchange Serverします](/exchange/exchange-hybrid)。

- Exchange Online テナントからオンプレミス ホストにメールを送信します。

- SharePoint Online からオンプレミス ホストに送信されたオンライン メールをSharePointします。

- [フェデレーション ハイブリッド検索をSharePoint](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)します。

- [ハイブリッド BCSをSharePoint](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)します。

- [ハイブリッド](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)フェデレーションまたは[Skype for BusinessフェデレーションをSkype for Business](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)します。

- [クラウド コネクタSkype for Business](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)。

複雑さを軽減するために、ExpressRoute 回線の代わりにインターネット回線経由でこれらの接続を受け入れることをお勧めします。 コンプライアンスまたはパフォーマンスのニーズに応じて、これらの受信接続を ExpressRoute 回線経由で受け入れる必要がある場合は、ファイアウォールまたはリバース プロキシを使用して、受け入れられた接続の範囲を指定することをお勧めします。 [Office 365 エンドポイント](./urls-and-ip-address-ranges.md)を使用して、適切な FQDN と IP プレフィックスを把握できます。
  
### <a name="compliance"></a>コンプライアンス

Microsoft では、コンプライアンス管理のいずれにも使用するルーティング パスに依存しません。 ExpressRoute またはインターネット回線経由でOffice 365 サービスに接続するかどうかにかかわらず、Microsoft のコンプライアンス制御は変更されません。 組織のニーズを満たすための最適な選択肢を見つけるには、Office 365のさまざまなコンプライアンスとセキュリティの認定レベルを確認する必要があります。
  
ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>関連項目

[コンテンツ配信ネットワーク](content-delivery-networks.md)
  
[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute for Office 365 のトレーニング](https://channel9.msdn.com/series/aer)