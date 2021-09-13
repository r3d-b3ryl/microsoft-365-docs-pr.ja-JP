---
title: Office 365 向け ExpressRoute の接続を管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: プレフィックス フィルター、セキュリティ、コンプライアンスOffice 365構成する共通領域など、ExpressRoute for Office 365を管理する方法について学習します。
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213853"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Office 365 向け ExpressRoute の接続を管理する

ExpressRoute for Office 365は、インターネットへのすべてのトラフィックを必要とせずに、Office 365サービスに到達する代替ルーティング パスを提供します。 Office 365 へのインターネット接続は依然として必要ですが、ネットワークに他の構成がない限り、Microsoft が BGP を介してネットワークにアドバタイズする特定のルートによって、直接 ExpressRoute 回線が優先されます。 このルーティングを管理するために構成する 3 つの共通領域には、プレフィックス フィルター、セキュリティ、コンプライアンスが含まれます。
  
> [!NOTE]
> Microsoft は、Azure ExpressRoute の Microsoft ピアリング ルーティング ドメインのレビュー方法を変更しました。 2017 年 7 月 31 日から、すべての Azure ExpressRoute のお客様は、Azure 管理コンソールまたは PowerShell 経由で Microsoft Peering を直接有効にできます。 Microsoft Peering を有効にすると、すべてのお客様がルート フィルターを作成して、Dynamics 365 Customer Engagement アプリケーション (以前は CRM Online と呼ばれる) の BGP ルート アドバタイズを受信できます。 Azure ExpressRoute を必要とするお客様Office 365、Microsoft からレビューを受け取る必要があります。その前に、ユーザーが Microsoft のルート フィルターを作成Office 365。 ExpressRoute を有効にするためのレビューを要求する方法については、Microsoft アカウント チームOffice 365してください。 ユーザーのルート フィルターを作成しようとする未承認Office 365エラー メッセージが[表示される](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>プレフィックス フィルター

Microsoft は、お客様が Microsoft からアドバタイズされたすべての BGP ルートを受け入れ、提供されるルートは厳格なレビューと検証プロセスを経て、追加の精査に対する利点を取り除くことをお勧めします。 ExpressRoute は、IP プレフィックスの所有権、整合性、スケールなどの推奨されるコントロールをネイティブに提供し、顧客側では受信ルート フィルターを使用しません。
  
ExpressRoute パブリック ピアリング全体でルート所有権の追加検証が必要な場合は、Microsoft のパブリック [IP](https://www.microsoft.com/download/details.aspx?id=53602)範囲を表すすべての IPv4 および IPv6 IP プレフィックスのリストに対してアドバタイズされたルートを確認できます。 これらの範囲は、Microsoft のアドレス空間全体をカバーし、頻繁に変更を加え、環境に漏洩する Microsoft 以外の所有ルートを懸念しているお客様にも保護を提供します。 変更が行われた場合は、月の 1 日に行い、ファイルが更新されるごとにページの詳細セクションのバージョン番号が変更されます。
  
プレフィックス フィルター リストを生成するための URL および[IP](./urls-and-ip-address-ranges.md)アドレスOffice 365使用しないようにするには、いくつかの理由があります。 以下を含む:
  
- IP プレフィックスOffice 365頻繁に多くの変更が行われます。

- URL Office 365 IP アドレス範囲は、ルーティングではなく、ファイアウォール許可リストとプロキシ インフラストラクチャを管理するために設計されています。

- このOffice 365 URL と IP アドレス範囲は、ExpressRoute 接続のスコープMicrosoft サービス他のデータをカバーしません。

|**オプション**|**複雑さ**|**変更コントロール**|
|:-----|:-----|:-----|
|すべての Microsoft ルートを受け入れる  <br/> |**低:** お客様は、すべてのルートが適切に所有されていることを確認するために、Microsoft のコントロールに依存しています。  <br/> |なし  <br/> |
|Microsoft 所有のスーパーネットをフィルター処理する  <br/> |**中:** お客様は、Microsoft が所有するルートのみを許可する要約プレフィックス フィルター リストを実装します。  <br/> |お客様は、まれな更新プログラムがルート フィルターに反映される必要があります。  <br/> |
|IP Office 365フィルター  <br/> [!CAUTION] Not-Recommended |**高:** 顧客は、定義された IP プレフィックスに基Office 365をフィルター処理します。  <br/> |お客様は、毎月の更新プログラムに対して堅牢な変更管理プロセスを実装する必要があります。  <br/> [!CAUTION] このソリューションには、重要な変更が必要です。 時間内に実装されていない変更は、サービスが停止する可能性があります。   |

Azure ExpressRoute Office 365を使用したネットワークへの接続は、エンドポイントが展開されているネットワークを表す特定の IP サブネットの BGP アドバタイズOffice 365基づいて行います。 Office 365 のグローバルな性質と Office 365 を構成するサービスの数により、顧客は多くの場合、ネットワーク上で受け入れる広告を管理する必要があります。 環境にアドバタイズされるプレフィックスの数が気になる場合は[、BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099)コミュニティ機能を使用して、特定の一連のサービスにアドバタイズOffice 365できます。 この機能はプレビュー中です。
  
Microsoft から送信される BGP ルート アドバタイズメントの管理方法に関係なく、インターネット回線だけで Office 365 に接続する場合と比較して、Office 365 サービスに特別な露出を得る必要はありません。 Microsoft は、お客様がデバイスに接続するために使用する回線の種類に関係なく、同じセキュリティ、コンプライアンス、およびパフォーマンス レベルOffice 365。
  
### <a name="security"></a>セキュリティ

Microsoft では、ExpressRoute パブリックと Microsoft ピアリングを行き帰する接続に対して、ネットワークとセキュリティ境界の制御を独自に維持Office 365勧めします。 ネットワークから Microsoft のネットワークへの送信、および Microsoft のネットワークからネットワークへの受信を行うネットワーク要求に対して、セキュリティ制御を行う必要があります。
  
#### <a name="outbound-from-customer-to-microsoft"></a>顧客から Microsoft への送信
  
コンピューターが Office 365接続すると、インターネット回線または ExpressRoute 回線を使用して接続が行われたかどうかに関係なく、同じエンドポイントセットに接続します。 使用する回線に関係なく、Microsoft では、一般的なインターネット接続先よりも信頼できるOffice 365サービスを扱う必要があります。 送信セキュリティ制御は、ポートとプロトコルに重点を置いて、露出を低減し、継続的なメンテナンスを最小限に抑える必要があります。 必要なポート情報は、エンドポイントリファレンスのOffice 365[参照](./urls-and-ip-address-ranges.md)してください。
  
追加されたコントロールの場合は、プロキシ インフラストラクチャ内で FQDN レベル フィルターを使用して、インターネットまたはサーバーに送信される一部またはすべてのネットワーク要求を制限または検査Office 365。 機能がリリースされ、Office 365 製品が進化するにつれて FQDN のリストを維持するには、公開されたエンドポイントに対する変更のより堅牢な変更管理と追跡Office 365[必要です](./urls-and-ip-address-ranges.md)。
  
> [!CAUTION]
> Microsoft では、IP プレフィックスのみに依存して、送信セキュリティを管理してセキュリティを管理Office 365。

|**オプション**|**複雑さ**|**変更コントロール**|
|:-----|:-----|:-----|
|制限なし  <br/> |**低:** お客様は、Microsoft への無制限の送信アクセスを許可します。  <br/> |なし  <br/> |
|ポートの制限  <br/> |**低:** お客様は、予期されるポートによって Microsoft への送信アクセスを制限します。  <br/> |まれです。  <br/> |
|FQDN の制限  <br/> |**高:** 顧客は、発行された FQDN に基づいてOffice 365への送信アクセスを制限します。  <br/> |毎月の変更。  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Microsoft から顧客への受信
  
Microsoft がネットワークへの接続を開始する必要があるいくつかのオプションのシナリオがあります。
  
- サインインのパスワード検証中の ADFS。

- [Exchange Serverハイブリッド展開](/exchange/exchange-hybrid).

- テナントからExchange Onlineオンプレミス ホストへのメール。

- SharePointオンライン メールは、SharePointからオンプレミス のホストに送信されます。

- [SharePointハイブリッド検索を実行します](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)。

- [SharePointハイブリッド BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype for Businessおよび](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)/またはハイブリッド[フェデレーションSkype for Businessします](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

- [Skype for Business クラウド コネクタ .](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)

複雑さを軽減するために、ExpressRoute 回線の代わりにインターネット回線を通してこれらの接続を受け入れる必要があります。 コンプライアンスまたはパフォーマンスのニーズに応じて、これらの受信接続を ExpressRoute 回線で受け入れる必要がある場合は、ファイアウォールまたはリバース プロキシを使用して、受け入れられる接続の範囲を指定することを推奨します。 エンドポイントを使用[Office 365、](./urls-and-ip-address-ranges.md)適切な FQDN と IP プレフィックスを把握できます。
  
### <a name="compliance"></a>コンプライアンス

コンプライアンスコントロールに使用するルーティング パスには依存しない。 ExpressRoute またはインターネット回線を通Office 365サービスに接続しても、コンプライアンス制御は変更されません。 組織のニーズを満たす最適な選択肢を把握するには、Office 365のコンプライアンスとセキュリティの認定レベルを確認する必要があります。
  
ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>関連項目

[コンテンツ配信ネットワーク](content-delivery-networks.md)
  
[Office 365 の URL と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute for Office 365 のトレーニング](https://channel9.msdn.com/series/aer)