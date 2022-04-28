---
title: SharePoint Online でのオブジェクト キャッシュの使用
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、SharePoint Server 2013 オンプレミスと SharePoint Online でのオブジェクト キャッシュの使用の違いについて説明します。
ms.openlocfilehash: db0a150927bc3a2078d4dc0ca7491471b7973f2d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077791"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>SharePoint Online でのオブジェクト キャッシュの使用

この記事では、SharePoint Server 2013 オンプレミスと SharePoint Online でのオブジェクト キャッシュの使用の違いについて説明します。
  
SharePoint Online デプロイのオブジェクト キャッシュに依存すると、大きな悪影響が生じます。 SharePoint Online のオブジェクト キャッシュに対する依存関係により、ページの信頼性が低下します。 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>SharePoint Online および SharePoint Server 2013 オブジェクト キャッシュのしくみ

SharePoint Server 2013 がオンプレミスでホストされている場合、顧客はオブジェクト キャッシュをホストするプライベート フロントエンド Web サーバーを持ちます。 つまり、キャッシュは 1 人の顧客専用であり、使用可能なメモリの量とオブジェクト キャッシュへの割り当て量によってのみ制限されます。 オンプレミスのシナリオでは 1 人の顧客のみが提供されるため、フロントエンド Web サーバーには通常、同じサイトに対して何度も要求を行うユーザーがいます。 つまり、キャッシュはすばやく完全になり、ユーザーが定期的に要求しているリスト クエリの結果とSharePoint オブジェクトがいっぱいになります。
  
![オンプレミスのフロントエンド Web サーバーへのトラフィックと読み込みを表示します。](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
その結果、ユーザーが 2 回目にページにアクセスすると、ページの読み込み時間が向上します。 同じページを少なくとも 4 回読み込んだ後、ページはすべてのフロントエンド Web サーバーにキャッシュされます。
  
これに対し、SharePoint Online には、より多くのサーバーが存在しますが、サイトも多数あります。 各ユーザーは、キャッシュが設定されていない別のフロントエンド Web サーバーに接続できます。 または、サーバーに対してキャッシュが設定される場合もありますが、そのフロントエンド Web サーバーの次のユーザーは別のサイトからページを要求します。 または、次のユーザーが以前のアクセス時と同じページを要求した場合でも、そのページをキャッシュに含まない別のフロントエンド Web サーバーに負荷分散されます。 この最後のケースでは、キャッシュはユーザーにはまったく役立ちません。
  
次の図では、各ドットは、ユーザーが要求しているページとキャッシュされた場所を表しています。 色が異なると、SaaS インフラストラクチャを共有して使用している顧客が異なります。
  
![SharePoint Online でのオブジェクト キャッシュの結果を表示します。](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
図からわかるように、特定のユーザーがキャッシュされたバージョンのページでサーバーにアクセスする可能性は薄いです。 また、スループットが大きく、サーバーが多くのサイト間で共有されているため、キャッシュの使用可能な領域が非常に多いため、キャッシュは長続きしません。
  
これらのすべての理由から、キャッシュされたオブジェクトを取得するユーザーに依存することは、SharePoint Online で品質の高いユーザー エクスペリエンスとページ読み込み時間を確保するための効果的な方法ではありません。
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>SharePoint Online のパフォーマンスを向上させるためにオブジェクト キャッシュに依存できない場合は、代わりに何を使用しますか?

SharePoint Online でのキャッシュに依存しないようにする必要があるため、オブジェクト キャッシュを使用するSharePointカスタマイズの代替設計方法を評価する必要があります。 これは、パフォーマンスの問題に対するアプローチを使用することを意味します。これは、ユーザーに適切な結果を生成するためにオブジェクト キャッシュに依存しません。 これは、このシリーズの他のいくつかの記事で説明され、次のものが含まれます。
  
- [SharePoint Online のナビゲーション オプション](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online での縮小とバンドル](minification-and-bundling-in-sharepoint-online.md)
    
- [SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)
    
- [SharePoint Online での画像の読み込み遅延と JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    