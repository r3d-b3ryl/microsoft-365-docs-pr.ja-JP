---
title: 'Office 365 の URL と IP アドレスの範囲 '
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/01/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: '概要: Office 365 には、インターネットへの接続が必要です。Office 365 のプランを利用する予定のお客様は (政府機関コミュニティ クラウド (GCC) を含む)、次のエンドポイントに到達できる必要があります。'
hideEdit: true
ms.openlocfilehash: 8a878d9be63411d891f0f42e9c9a0df722317666
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66493766"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL および IP アドレス範囲

Office 365 には、インターネットへの接続が必要です。Office 365 のプランを利用する予定のお客様は (政府機関コミュニティ クラウド (GCC) を含む)、次のエンドポイントに到達できる必要があります。
  
*Office 365 ワールドワイド (+GCC)*\|[21 Vianetが運営するOffice 365](urls-and-ip-address-ranges-21vianet.md)\|[Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)\|[Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)\|

|備考|ダウンロード|使用|
|---|---|---|
|**最終更新日:** 2022 年 6 月 1 日 - ![RSS。](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [変更ログのサブスクリプション](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**ダウンロード:** 1 つの [JSON 形式](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)リスト内のすべての必須およびオプションの宛先。|**使用:** プロキシ [PAC ファイル](managing-office-365-endpoints.md#pacfiles)|
|

まずはじめに「[Office 365 エンドポイントを管理する](managing-office-365-endpoints.md)」を読み、以下のデータを使用してネットワーク接続を管理するための推奨事項を確認するようにしてください。エンドポイント データは毎月月初めに必要に応じて更新され、新しい IP アドレスと URL は、それらがアクティブになる 30 日前に公開されます。これにより、お客様がまだ自動更新の設定を行っていない場合でも、新しい接続が必要になる前にプロセスを完了していただけます。サポートのエスカレーション、セキュリティ インシデント、またはその他の即時の運用要件に対応するために、月の途中にエンドポイントが更新される場合があります。このページの下に表示されるデータは、すべて REST ベースの Web サービスから生成されたものです。スクリプトやネットワーク デバイスを使用してこのデータにアクセスする場合、[[Web サービス]](microsoft-365-ip-web-service.md) に直接移動する必要があります。

以下のエンドポイント データは、ユーザーのコンピューターから Office 365 への接続の要件を示しています。 Microsoft から顧客ネットワークへのネットワーク接続 (ハイブリッドまたは受信ネットワーク接続とも呼ばれる) に使用される IP アドレスの詳細については、「[追加エンドポイント](additional-office365-ip-addresses-and-urls.md)」を参照してください。

エンドポイントは、3 つのプライマリ ワークロードと一連の共通リソースを表す 4 つのサービス領域にグループ化されます。 これらのグループを使用してトラフィック フローを特定のアプリケーションに関連付けることができますが、機能が複数のワークロードにわたってエンドポイントを消費することがよくありますが、これらのグループを効果的に使用してアクセスを制限することはできません。

次のデータ列が表示されます。

- **ID**: エンドポイントのセットとして知られる、行の ID 番号です。この ID は、エンドポイントの Web サービスによって返されるものと同じです。

- **カテゴリ**: エンドポイントのセットが「**最適化**」、「**許可**」、「**既定**」のどれに分類されているかを示します。この列には、ネットワーク接続に必要なエンドポイントのセットが表示されます。ネットワーク接続が必要ないエンドポイントのセットの場合、このコラムには、エンドポイントのセットがブロックされた場合に使えなくなる機能に関する注意書きが書かれます。サービス領域全体を除外する場合は、ネットワーク接続が必要と記載されているエンドポイントのセットの接続は不要です。

   これらのカテゴリとその管理に関するガイダンスについては、「[新しい Office 365 エンドポイント カテゴリ](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)」をご覧いただけます。

- **ER**: 「**はい**」とある場合、エンドポイントのセットは Office 365 のルート プレフィックスを使用して Azure ExpressRoute でサポートされています。表示されているルートのプレフィックスを含む BGP コミュニティは、記載されているサービス領域と整合します。ER に「**いいえ**」とある場合、ExpressRoute はそのエンドポイントのセットでサポートされていないことを意味します。

   一部のルートは複数の BGP コミュニティでアドバタイズされる可能性があるため、特定の IP 範囲内のエンドポイントが ER 回線を通過することは可能ですが、それでもサポートの対象外です。 いずれの場合も、特定のエンドポイント セットの ER 列の値を尊重する必要があります。 BGP コミュニティの詳細については、「[Office 365 シナリオの ExpressRoute での BGP コミュニティの使用](bgp-communities-in-expressroute.md#key-planning-considerations-to-using-bgp-communities)」を参照してください。

- **アドレス**: FQDN またはワイルドカードを含むドメイン名と、エンドポイントのセットの IP アドレス範囲を一覧表示します。IP アドレスの範囲は CIDR 形式となり、指定されたネットワークの個別の IP アドレスが多数含まれる場合があることに注意してください。

- **ポート**: 記載された IP アドレスと組み合わさることによりネットワーク エンドポイントを形成する TCP または UDP ポートの一覧を表示します。異なるポートが記載されている場合、IP アドレス範囲が重複している場合があります。

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> Yammer の IP アドレスと URL に関する推奨事項については、Yammer ブログの「[Yammer でハードコードされた IP アドレスの使用が推奨される」を参照してください](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592)。

## <a name="related-topics"></a>関連項目

[Office 365 IP アドレスと URL Web サービスに含まれないその他のエンドポイント](additional-office365-ip-addresses-and-urls.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[一般的な Microsoft Stream エンドポイント](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Microsoft 365 の接続を監視する](./monitor-connectivity.md)

[ルート CA とサードパーティ製のアプリケーション システム上の中間 CA バンドル](../compliance/encryption-office-365-certificate-chains.md)
  
[クライアント接続](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[コンテンツ配信ネットワーク](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure の IP 範囲とサービス タグ – パブリック クラウド](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure の IP 範囲とサービス タグ – 米国政府機関向けクラウド](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure の IP 範囲とサービス タグ – 中国向けクラウド](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft パブリック IP スペース](https://www.microsoft.com/download/details.aspx?id=53602)

[サービス名およびトランスポート プロトコルのポート番号レジストリ](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
