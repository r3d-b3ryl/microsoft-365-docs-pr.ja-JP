---
title: SharePoint Online のパフォーマンス チューニングの概要
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: この記事では、SharePoint Online で最高のパフォーマンスを得るページを設計する際に考慮する必要がある特定の側面について説明します。
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909740"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>SharePoint Online のパフォーマンス チューニングの概要

この記事では、SharePoint Online で最高のパフォーマンスを得るページを設計する際に考慮する必要がある特定の側面について説明します。
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online の指標

SharePoint Online の次の広範な指標は、パフォーマンスに関する実際のデータを提供します。
  
- ページの読み込み速度
    
- ページごとに必要なラウンド トリップの数
    
- サービスに関する問題
    
- パフォーマンスの低下を引き起こすその他の問題
    
### <a name="conclusions-reached-because-of-the-data"></a>データのために達した結論

データには、次の情報が表示されます。
  
- ほとんどのページは SharePoint Online でうまく機能します。
    
- カスタマイズされていないページは非常に迅速に読み込まれます。
    
- OneDrive for Business、チーム サイト、システム ページ (_layoutsなど) は、すべてすばやく読み込まれます。
    
- SharePoint Online ページの最も遅い 1% の読み込みには 5,000 ミリ秒以上かかる。
    
使用できる簡単なベンチマーク テストの 1 つは、カスタマイズされた機能が少なく、独自のポータルの読み込み時間と OneDrive for Business ホーム ページの読み込み時間を比較してパフォーマンスを測定する方法です。 これは、多くの場合、ネットワーク パフォーマンスの問題のトラブルシューティング時に完了を求める最初の手順です。
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>パフォーマンスを確認するときに標準のユーザー アカウントを使用する

サイト コレクション管理者、サイト所有者、エディター、または共同作成者は、追加のセキュリティ グループに属し、追加のアクセス許可を持ち、SharePoint がページに読み込む追加の要素を持っています。
  
これは SharePoint オンプレミスと SharePoint Online に適用できますが、オンプレミスのシナリオでは、SharePoint Online のように簡単に違いを確認できません。
  
ユーザーに対するページのパフォーマンスを正しく評価するには、標準のユーザー アカウントを使用して、オーサリング コントロールやセキュリティ グループに関連する追加のトラフィックを読み込むのを避ける必要があります。
  
## <a name="connection-categories-for-performance-tuning"></a>パフォーマンス調整用の接続カテゴリ

サーバーとユーザーの間の接続を 3 つの主要なコンポーネントに分類できます。 読み込み時間に関する分析情報を得る SharePoint Online ページを設計する場合は、次の点を考慮してください。
  
- **サーバー** Microsoft がデータセンターでホストするサーバー。
    
- **ネットワーク** データセンターとユーザーの間の Microsoft ネットワーク、インターネット、オンプレミス ネットワーク。
    
- **ブラウザー** ページが読み込まれる場所。
    
これらの 3 つの接続内には、通常、低速ページの 95% が発生する 5 つの理由があります。 これらの理由のそれぞれについては、この記事で説明します。
  
- ナビゲーションの問題
    
- コンテンツのロールアップ
    
- 大きなファイル
    
- サーバーへの多くの要求
    
- Web パーツの処理
    
### <a name="server-connection"></a>サーバー接続

SharePoint オンプレミスのパフォーマンスに影響を与える問題の多くは、SharePoint Online にも適用されます。
  
予想通り、サーバーがオンプレミスの SharePoint で実行する方法をはるかに制御できます。 SharePoint Online では、少し異なります。 サーバーの作業が多くなると、ページのレンダリングにかかる時間が長くなります。 SharePoint では、この点で最大の原因は、複数の Web パーツを持つ複雑なページです。
  
オンプレミスの SharePoint Server
  
![オンプレミスのサーバーのスクリーンショット](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![オンラインのサーバーのスクリーンショット](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
SharePoint Online では、特定のページ要求が実際に複数のサーバーを呼び出す可能性があります。 個々の要求に対するサーバー間の要求のマトリックスで終わる可能性があります。 これらの操作は、ページ読み込みの観点からコストがかかるので、動作が遅くなります。
  
これらのサーバー間の対話の例を次に示します。
  
- Web to SQL サーバー
    
- Web からアプリケーション サーバーへ
    
サーバーの操作が遅くなる可能性があるもう 1 つの問題は、キャッシュ ミスです。 オンプレミスの SharePoint とは異なり、以前にアクセスしたページに対して同じサーバーをヒットする可能性は非常に低いです。これにより、オブジェクトのキャッシュは使用されなくなりました。
  
### <a name="network-connection"></a>ネットワーク接続

WAN を使用しないオンプレミスの SharePoint では、データセンターとエンド ユーザーの間で高速接続を使用できます。 一般に、ネットワークの観点から簡単に管理できます。
  
SharePoint Online では、考慮すべきいくつかの要因があります。例えば：
  
- Microsoft ネットワーク
    
- インターネット
    
- The ISP
    
使用している SharePoint (およびどのネットワーク) のバージョンに関係なく、通常、ネットワークがビジー状態になる原因となるものは次のとおりです。
  
- 大きなペイロード
    
- 多くのファイル
    
- サーバーへの物理的な距離が大きい
    
SharePoint Online で利用できる機能の 1 つは、Microsoft CDN (コンテンツ配信ネットワーク) です。 CDN は基本的に、複数のデータセンターに展開されるサーバーの分散コレクションです。 CDN を使用すると、クライアントが元の SharePoint Server から遠く離れた場合でも、ページ上のコンテンツをクライアントに近いサーバーでホストできます。 Microsoft は今後、これを使用して、カスタマイズできないページのローカル インスタンス (SharePoint Online 管理ホーム ページなど) を格納する予定です。 CDN の詳細については、「コンテンツ配信 [ネットワーク」を参照してください](content-delivery-networks.md)。
  
注意する必要がありますが、あまり実行できない可能性がある点は、ISP の接続速度です。 簡単な速度テスト ツールは、接続速度を示します。
  
### <a name="browser-connection"></a>ブラウザー接続

パフォーマンスの観点から Web ブラウザーで考慮すべきいくつかの要因があります。
  
複雑なページにアクセスすると、パフォーマンスに影響します。 ほとんどのブラウザーはキャッシュが小さい (約 90 MB) ですが、平均的な Web ページは通常約 1.6 MB です。 これは使い慣れるのに時間はかからない。
  
帯域幅も問題になる可能性があります。 たとえば、ユーザーが別のセッションでビデオを視聴している場合、これは SharePoint ページのパフォーマンスに影響します。 ユーザーがメディアをストリーミングするのを防ぐことはできないが、ページがユーザーに対して読み込む方法を制御できます。
  
最適なパフォーマンスを実現するために役立つさまざまな SharePoint Online ページカスタマイズ手法や他のベスト プラクティスについては、次の記事を参照してください。
  
- [SharePoint Online のナビゲーション オプション](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online のページ診断ツールを使用する](page-diagnostics-for-spo.md)
    
- [SharePoint Online のイメージの最適化](image-optimization-for-sharepoint-online.md)
    
- [SharePoint Online での画像の読み込み遅延と JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [SharePoint Online での縮小とバンドル](minification-and-bundling-in-sharepoint-online.md)
    
- [SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)
    
- [コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して SharePoint Online のパフォーマンスを向上させる](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [SharePoint Online のキャパシティ プランニングとロード テスト](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [SharePoint Online のパフォーマンスの問題の診断](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [SharePoint Online でのオブジェクト キャッシュの使用](using-the-object-cache-with-sharepoint-online.md)
    
- [方法:SharePoint Online で調整またはブロックを回避する](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
