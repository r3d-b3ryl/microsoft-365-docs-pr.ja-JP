---
title: コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用してオンラインでのパフォーマンスSharePointする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えてパフォーマンスを向上させる方法について説明します。
ms.openlocfilehash: 270019b59666c3f52d67648a88c453278149fccd
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58566746"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用してオンラインでのパフォーマンスSharePointする

この記事では、コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えてパフォーマンスを向上させる方法について説明します。
  
SharePoint Server 2013 および SharePoint の最も強力な新機能の 1 つは、コンテンツ検索 Web パーツ (CSWP) です。 この Web パーツは、検索インデックスを使用して、ユーザーに表示される結果をすばやく取得します。 ユーザーのパフォーマンスを向上させるために、ページ内のコンテンツ クエリ Web パーツ (CQWP) の代わりにコンテンツ検索 Web パーツを使用します。
  
コンテンツ クエリ Web パーツに対してコンテンツ検索 Web パーツを使用すると、ほとんどの場合、オンラインでのページ読み込みパフォーマンスがSharePointになります。 適切なクエリを取得するために少し追加の構成がありますが、報酬はパフォーマンスが向上し、ユーザーが幸せです。
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して得られるパフォーマンスの向上を比較する

次の例は、コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用するときに受け取る可能性がある相対的なパフォーマンス向上を示しています。 複雑なサイト構造と非常に広範なコンテンツ クエリにより、効果が明らかになります。
  
このサイトの例には、次の特性があります。
  
- 8 レベルのサブサイト。
    
- カスタムの "フルーツ" コンテンツ タイプを使用するリスト。
    
- Web パーツでは、コンテンツ クエリは広範で、コンテンツ タイプが "fruit" のすべてのアイテムを返します。
    
- この例では、8 つのサイト全体で 50 アイテムのみを使用します。 コンテンツが多いサイトでは、さらに効果が顕著に表示されます。
    
コンテンツ クエリ Web パーツの結果のスクリーン ショットを次に示します。
  
![Web パーツのコンテンツ クエリを示すグラフィック。](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
このInternet Explorer、F12開発者ツールの [ネットワーク] タブを使用して、応答ヘッダーの詳細を確認します。 次のスクリーン ショットでは、このページ読み込み時の **SPRequestDuration** の値は 924 ミリ秒です。 
  
![924 の要求期間を示すスクリーンショット。](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration は** 、ページを準備するためにサーバーで実行される作業量を示します。 クエリによってコンテンツを切りWeb パーツ検索でコンテンツを切りWeb パーツ、ページのレンダリングにかかる時間が大幅に短縮されます。 対照的に、同等のコンテンツ検索 Web パーツを持つページで、同じ数の結果を返す場合、このスクリーン ショットに示すように **SPRequestDuration** 値は 106 ミリ秒です。 
  
![要求期間 106 を示すスクリーン ショット。](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>オンラインでのコンテンツ検索 Web パーツSharePointする

コンテンツ検索 Web パーツの追加は、通常のコンテンツ クエリ Web パーツと非常に似ています。 「コンテンツ検索 *Web パーツを構成する*」のセクション「コンテンツ検索 [Web](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)パーツの追加」を参照SharePoint。
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>コンテンツ検索 Web パーツの適切な検索クエリを作成する

コンテンツ検索 Web パーツを追加したら、検索を絞り込んで、必要なアイテムを返します。 これを行う方法の詳細については、「SharePoint でコンテンツ検索 Webパーツを構成する」のセクション「コンテンツ検索 Web パーツで高度なクエリを構成してコンテンツを表示する[」を参照してください](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)。
  
## <a name="query-building-and-testing-tool"></a>クエリの作成とテスト ツール

複雑なクエリをビルドしてテストするツールについては、「Codeplex の [検索クエリ ツール」](https://sp2013searchtool.codeplex.com/) を参照してください。 
  

