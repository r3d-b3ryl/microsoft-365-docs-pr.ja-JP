---
title: Online でオブジェクト キャッシュをSharePointする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: この記事では、オンプレミスのサーバー 2013 および SharePoint Online でオブジェクト キャッシュを使用するSharePoint説明します。
ms.openlocfilehash: 669a68e949c5e83be794644e0d4b9ae117c69e6282f2d0ea15f96a0ad3e90461
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53894855"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>Online でオブジェクト キャッシュをSharePointする

この記事では、オンプレミスのサーバー 2013 および SharePoint Online でオブジェクト キャッシュを使用するSharePoint説明します。
  
オンライン展開のオブジェクト キャッシュに依存すると、重大な悪影響SharePointがあります。 オンラインでのオブジェクト キャッシュへのSharePointは、ページの信頼性を低下します。 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>SharePoint Server 2013 SharePoint キャッシュのしくみ

サーバー 2013 SharePointオンプレミスでホストされている場合、顧客はオブジェクト キャッシュをホストするプライベート フロントエンド Web サーバーを持っています。 つまり、キャッシュは 1 人の顧客専用であり、使用可能なメモリ量とオブジェクト キャッシュへの割り当て量によってのみ制限されます。 オンプレミスのシナリオでは、1 人の顧客だけがサービスを受け取るので、フロントエンド Web サーバーは通常、同じサイトに対して要求を行うユーザーを持っています。 つまり、キャッシュはすばやく完全に取得され、リスト クエリの結果と、ユーザーが定期的に要求しているSharePointオブジェクトの完全な状態を維持します。
  
![オンプレミスのフロントエンド Web サーバーへのトラフィックと負荷を示しています](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
その結果、ユーザーが 2 回目にページにアクセスすると、ページの読み込み時間が向上します。 同じページを少なくとも 4 回読み込むと、すべてのフロントエンド Web サーバーにページがキャッシュされます。
  
対照的に、オンラインではSharePointサーバーが多数あるだけでなく、サイトも多く用意されています。 各ユーザーは、キャッシュが設定された別のフロントエンド Web サーバーに接続できます。 または、おそらくキャッシュはサーバーに対して設定されますが、そのフロントエンド Web サーバーの次のユーザーが別のサイトからページを要求します。 または、次のユーザーが前回の訪問時と同じページを要求した場合でも、そのページをキャッシュに含めなかった別のフロントエンド Web サーバーに負荷分散されます。 この最後のケースでは、キャッシュはユーザーの助けにはなってこない。
  
次の図では、各ドットは、ユーザーが要求しているページと、そのページがキャッシュされた場所を表しています。 色が異なると、SaaS インフラストラクチャを共有して利用する顧客が異なります。
  
![SharePoint Online におけるオブジェクト キャッシュの結果を示します](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
図から分かっている通り、キャッシュされたバージョンのページでサーバーにアクセスする可能性は薄いです。 また、スループットが大きく、サーバーが多くのサイト間で共有されているという事実により、キャッシュに使用できる領域が非常に多いので、キャッシュは長持ちしません。
  
これらのすべての理由から、キャッシュされたオブジェクトを取得するユーザーに依存する方法は、SharePoint Online で高品質のユーザー エクスペリエンスとページ読み込み時間を確保する効果的な方法ではありません。
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>オブジェクト キャッシュを使用してオンラインのパフォーマンスを向上SharePoint場合、代わりに何を使用しますか?

SharePoint Online でのキャッシュに依存してはならないので、オブジェクト キャッシュを使用するカスタマイズのSharePoint設計方法を評価する必要があります。 つまり、ユーザーに良い結果を生み出すには、オブジェクト キャッシュに依存しないパフォーマンスの問題に対するアプローチを使用します。 これは、このシリーズの他の記事の一部で説明され、次のものが含まれます。
  
- [SharePoint Online のナビゲーション オプション](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online での縮小とバンドル](minification-and-bundling-in-sharepoint-online.md)
    
- [SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)
    
- [SharePoint Online での画像の読み込み遅延と JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

