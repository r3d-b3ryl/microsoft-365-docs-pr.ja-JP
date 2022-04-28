---
title: SharePoint Online のパフォーマンス チューニングの概要
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: この記事では、SharePoint Online で最適なパフォーマンスを得るためにページを設計する際に考慮する必要がある特定の側面について説明します。
ms.openlocfilehash: b31696766d3201b6677bf0c63108fad72c3ed49d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100745"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>SharePoint Online のパフォーマンス チューニングの概要

この記事では、SharePoint Online で最適なパフォーマンスを得るためにページを設計する際に考慮する必要がある特定の側面について説明します。
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online メトリック

SharePoint Online の次の広範なメトリックは、パフォーマンスに関する実際のデータを提供します。
  
- ページの読み込み速度
    
- ページごとに必要なラウンド トリップの数
    
- サービスに関する問題
    
- パフォーマンスの低下の原因となるその他のもの
    
### <a name="conclusions-reached-because-of-the-data"></a>データが原因で到達した結論

データは次の情報を示します。
  
- ほとんどのページは、SharePoint Online で優れたパフォーマンスを発揮します。
    
- カスタマイズされていないページはすぐに読み込まれます。
    
- OneDrive for Business、チーム サイト、システム ページ (_layoutsなど) はすべて、すばやく読み込むことができます。
    
- SharePoint Online ページの最も遅い 1% の読み込みには 5,000 ミリ秒以上かかります。
    
使用できる簡単なベンチマーク テストの 1 つは、カスタマイズされた機能をいくつか使用するため、独自のポータルの読み込み時間とOneDrive for Businessホーム ページの読み込み時間を比較することで、パフォーマンスを測定することです。 これは多くの場合、ネットワーク パフォーマンスの問題のトラブルシューティング時にサポートから完了を求める最初の手順になります。
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>パフォーマンスを確認するときに標準ユーザー アカウントを使用する

サイト コレクション管理者、サイト所有者、エディター、または共同作成者は別のセキュリティ グループに属しており、より多くのアクセス許可を持ち、ページに読み込SharePoint追加の要素を持ちます。
  
これは、オンプレミスと SharePoint Online のSharePointに適用できますが、オンプレミスのシナリオでは、SharePoint Online のように簡単に違いが認識されることはありません。
  
ユーザーに対するページの動作を正しく評価するには、標準ユーザー アカウントを使用して、作成コントロールとセキュリティ グループに関連する追加のトラフィックの読み込みを回避する必要があります。
  
## <a name="connection-categories-for-performance-tuning"></a>パフォーマンスチューニングの接続カテゴリ

サーバーとユーザー間の接続は、主に 3 つのコンポーネントに分類できます。 読み込み時間に関する分析情報をSharePointオンライン ページを設計する場合は、これらを考慮してください。
  
- **サーバー** Microsoft がデータセンターでホストするサーバー。
    
- **ネットワーク** Microsoft ネットワーク、インターネット、およびデータセンターとユーザー間のオンプレミス ネットワーク。
    
- **ブラウザー** ページが読み込まれる場所。
    
これら 3 つの接続内には、通常、95% の低速ページの原因となる 5 つの理由があります。 これらの各理由については、この記事で説明します。
  
- ナビゲーションの問題
    
- コンテンツのロールアップ
    
- 大きなファイル
    
- サーバーに対する多くの要求
    
- Web パーツの処理
    
### <a name="server-connection"></a>サーバー接続

SharePointオンプレミスのパフォーマンスに影響する問題の多くは、SharePoint Online にも適用されます。
  
想定どおりに、オンプレミスのSharePointでサーバーがどのように実行されるかをはるかに制御できます。 SharePoint Online では、物事は少し異なります。 サーバーを実行する作業が多いほど、ページのレンダリングにかかる時間が長くなります。 SharePointでは、この点で最大の原因は、複数の Web パーツを含む複雑なページです。
  
オンプレミスの SharePoint Server
  
![オンプレミスのサーバーのスクリーンショット。](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![オンライン サーバーのスクリーンショット。](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
SharePoint Online では、特定のページ要求が実際に複数のサーバーを呼び出す可能性があります。 個々の要求に対するサーバー間の要求のマトリックスで終わる可能性があります。 これらの相互作用は、ページ読み込みの観点から見るとコストがかかり、処理が遅くなります。
  
これらのサーバー間の対話の例を次に示します。
  
- Web から SQL サーバーへ
    
- Web からアプリケーション サーバーへ
    
サーバーの操作を遅らせるもう 1 つの点は、キャッシュ ミスです。 オンプレミスのSharePointとは異なり、以前にアクセスしたページで同じサーバーにアクセスする可能性は低くなります。これにより、オブジェクトキャッシュが廃止されます。
  
### <a name="network-connection"></a>ネットワーク接続

WAN を利用しないオンプレミスのSharePointでは、データセンターとエンド ユーザー間の高速接続を使用できます。 一般に、ネットワークの観点から物事を簡単に管理できます。
  
SharePoint Online では、次のようないくつかの要因を考慮する必要があります。
  
- Microsoft ネットワーク
    
- インターネット
    
- The ISP
    
使用しているSharePoint (およびネットワーク) のバージョンに関係なく、通常、ネットワークがビジー状態になる原因となるものは次のとおりです。
  
- 大きなペイロード
    
- 多くのファイル
    
- サーバーへの物理的な距離が大きい
    
SharePoint Online で使用できる機能の 1 つは、Microsoft CDN (Content Delivery Network) です。 CDNは、基本的に、複数のデータセンターにデプロイされたサーバーの分散コレクションです。 CDNを使用すると、クライアントが元のSharePoint サーバーから離れている場合でも、ページ上のコンテンツをクライアントに近いサーバーでホストできます。 Microsoft では、今後、これを使用して、カスタマイズできないページのローカル インスタンス (SharePoint Online 管理者ホーム ページなど) を格納する予定です。 CDN の詳細については、「 [コンテンツ配信ネットワーク](content-delivery-networks.md)」を参照してください。
  
注意する必要がありますが、あまりできない可能性があるのは、ISP の接続速度です。 簡単な速度テスト ツールによって、接続速度が示されます。
  
### <a name="browser-connection"></a>ブラウザー接続

Web ブラウザーには、パフォーマンスの観点から考慮すべきいくつかの要素があります。
  
複雑なページにアクセスすると、パフォーマンスに影響します。 ほとんどのブラウザーには小さなキャッシュ (約 90 MB) しか用意されていませんが、平均的な Web ページは通常約 1.6 MB です。 これは、使い慣れるのに時間はかからず。
  
帯域幅も問題になる可能性があります。 たとえば、ユーザーが別のセッションでビデオを視聴している場合、これはSharePoint ページのパフォーマンスに影響します。 ユーザーがメディアをストリーミングできないようにすることはできませんが、ユーザーのページの読み込み方法を制御できます。
  
最適なパフォーマンスを実現するために役立つさまざまなSharePoint Online ページのカスタマイズ手法とその他のベスト プラクティスについては、次の記事を参照してください。
  
- [SharePoint Online のナビゲーション オプション](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online のページ診断ツールを使用する](page-diagnostics-for-spo.md)
    
- [SharePoint Online のイメージの最適化](image-optimization-for-sharepoint-online.md)
    
- [SharePoint Online での画像の読み込み遅延と JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [SharePoint Online での縮小とバンドル](minification-and-bundling-in-sharepoint-online.md)
    
- [SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)
    
- [コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して、SharePoint Online のパフォーマンスを向上させる](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [SharePoint Online のキャパシティ プランニングとロード テスト](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [SharePoint Online のパフォーマンスの問題の診断](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [SharePoint Online でのオブジェクト キャッシュの使用](using-the-object-cache-with-sharepoint-online.md)
    
- [方法:SharePoint Online で調整またはブロックを回避する](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
