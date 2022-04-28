---
title: コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して、SharePoint Online のパフォーマンスを向上させる
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えることで、パフォーマンスを向上させる方法について説明します。
ms.openlocfilehash: 77c2c6e48beb05b6d371734f0eeeb48881339156
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65098166"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して、SharePoint Online のパフォーマンスを向上させる

この記事では、コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えることで、パフォーマンスを向上させる方法について説明します。
  
SharePoint Server 2013 および SharePoint Online の最も強力な新機能の 1 つは、コンテンツ検索 Web パーツ (CSWP) です。 この Web パーツでは、検索インデックスを使用して、ユーザーに表示される結果をすばやく取得します。 ページ内のコンテンツ クエリ Web パーツ (CQWP) の代わりにコンテンツ検索 Web パーツを使用して、ユーザーのパフォーマンスを向上させます。
  
コンテンツ クエリ Web パーツでコンテンツ検索 Web パーツを使用すると、ほとんどの場合、SharePoint Online でのページ読み込みパフォーマンスが大幅に向上します。 適切なクエリを取得するための追加の構成が少しありますが、報酬はパフォーマンスが向上し、ユーザーの満足度が向上します。
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して得られるパフォーマンスの向上を比較する

次の例は、コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用するときに得る相対的なパフォーマンス向上を示しています。 複雑なサイト構造と非常に広範なコンテンツ クエリでは、効果がより明確になります。
  
このサンプル サイトには、次の特性があります。
  
- 8 レベルのサブサイト。
    
- カスタム "果樹" コンテンツ タイプを使用するリスト。
    
- Web パーツでは、コンテンツ クエリは広範であり、コンテンツ タイプが "fruit" のすべての項目を返します。
    
- この例では、8 つのサイト全体で 50 個のアイテムのみを使用します。 コンテンツが多いサイトでは、効果がさらに顕著になります。
    
コンテンツ クエリ Web パーツの結果のスクリーン ショットを次に示します。
  
![Web パーツのコンテンツ クエリを示すグラフィック。](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
Internet Explorer で、F12 開発者ツールの [ **ネットワーク** ] タブを使用して、応答ヘッダーの詳細を確認します。 次のスクリーン ショットでは、このページ読み込みの **SPRequestDuration** の値は 924 ミリ秒です。 
  
![要求期間 924 を示すスクリーンショット。](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** は、ページを準備するためにサーバーで実行される作業量を示します。 Content by Search Web パーツを使用してクエリ Web パーツでコンテンツを切り替えると、ページのレンダリングにかかる時間が大幅に短縮されます。 これに対し、同じ数の結果を返すコンテンツ検索 Web パーツを持つページでは、このスクリーン ショットに示すように **SPRequestDuration** の値は 106 ミリ秒です。 
  
![要求期間 106 を示すスクリーン ショット。](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>SharePoint Online でのコンテンツ検索 Web パーツの追加

コンテンツ検索 Web パーツの追加は、通常のコンテンツ クエリ Web パーツとよく似ています。 *「SharePointでコンテンツ検索 Web パーツを* 構成する」の「[コンテンツ検索 Web パーツの](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)追加」セクションを参照してください。
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>コンテンツ検索 Web パーツの適切な検索クエリを作成する

コンテンツ検索 Web パーツを追加したら、検索を絞り込んで目的のアイテムを返すことができます。 これを行う方法の詳細については、「*SharePointでコンテンツ検索 Web パーツを構成する」の「コンテンツ検索 Web パーツで高度なクエリを構成して*[コンテンツを](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)表示する」セクションを参照してください。
  
## <a name="query-building-and-testing-tool"></a>クエリのビルドとテスト ツール

複雑なクエリをビルドしてテストするツールについては、Codeplex の [検索クエリ ツール](https://sp2013searchtool.codeplex.com/) を参照してください。 
  

