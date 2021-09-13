---
title: SharePoint Online での画像の読み込み遅延と JavaScript
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: JavaScript を使用してイメージの読み込みと重要でない JavaScript の読み込みを遅らせSharePointオンライン ページの読み込み時間を削減する方法について説明します。
ms.openlocfilehash: 7be256db8bce115b130322d1dd34131d845ef165
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218573"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>SharePoint Online での画像の読み込み遅延と JavaScript

この記事では、JavaScript を使用してイメージの読み込みを遅延し、ページの読み込み後まで重要でない JavaScript の読み込みを待機することで、SharePoint Online ページの読み込み時間を削減する方法について説明します。
  
画像は、オンラインのページ読み込み速度に悪影響SharePointがあります。 既定では、HTML ページの読み込み時に最新のほとんどのインターネット ブラウザーが画像をプリフェッチします。 これにより、ユーザーが下にスクロールするまで画像が画面に表示されない場合、ページの読み込み速度が不必要に遅くなる可能性があります。 画像は、ブラウザーがページの表示部分を読み込むのをブロックできます。 この問題を回避するには、JavaScript を使用して、最初にイメージの読み込みをスキップできます。 また、重要でない JavaScript を読み込むと、ページのダウンロード時間SharePoint遅くなる可能性があります。 このトピックでは、JavaScript のページ読み込み時間を改善するために使用できるいくつかの方法について説明します。SharePointします。
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>JavaScript を使用してオンライン ページでのイメージの読み込SharePointを遅らせ、ページの読み込み時間を短縮する

JavaScript を使用すると、Web ブラウザーによる画像の事前フェッチを防止できます。 これにより、ドキュメントの全体的なレンダリングが高速化されます。 これを行うには、タグから src 属性の値を削除し、それを data-src などのデータ属性内のファイルへのパスに \<img\> 置き換える必要があります。 例:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

このメソッドを使用すると、ブラウザーはイメージをすぐにダウンロードされません。 イメージが既にビューポート内にある場合、JavaScript はブラウザーに対して、データ属性から URL を取得し、src 属性の値として挿入します。 画像は、ユーザーがスクロールして表示される場合にのみ読み込まれます。
  
これをすべて実行するには、JavaScript を使用する必要があります。
  
テキスト ファイルで **isElementInViewport()** 関数を定義して、ユーザーに表示されるブラウザーの一部に要素が含されているかどうかを確認します。
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

次に **、loadItemsInView()** 関数で **isElementInViewport() を使用** します。 **loadItemsInView()** 関数は、ユーザーに表示されるブラウザーの一部にある場合、data-src 属性の値を持つすべてのイメージを読み込むようになります。 テキスト ファイルに次の関数を追加します。
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

最後に、次の例に示すように **、window.onscroll()** 内から **loadItemsInView()** を呼び出します。 これにより、ユーザーが必要とするとビューポート内のすべてのイメージが読み込まれますが、以前は読み込まれません。 テキスト ファイルに次の項目を追加します。
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

オンラインSharePoint、次の関数を、#s4-workspace タグのスクロール イベントに関連付ける必要 \<div\> があります。 これは、リボンがページの上部に接続されたままに維持するために、ウィンドウ イベントが上書きされるためです。
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

テキスト ファイルを JavaScript ファイルとして保存し、.jsなどの拡張子を持delayLoadImages.js。
  
ファイルの作成がdelayLoadImages.jsしたら、ファイルの内容を [オンライン] のマスター ページにSharePointできます。 これを行うには、マスター ページのヘッダーにスクリプト リンクを追加します。 マスター ページが作成されると、そのマスター ページ レイアウトを使用する SharePoint Online サイトのすべてのページに JavaScript が適用されます。 または、サイトの 1 ページでのみこれを使用する場合は、スクリプト エディター Web パーツを使用して JavaScript をページに埋め込む必要があります。 詳細については、次のトピックを参照してください。
  
- [[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>例: オンラインでマスター ページdelayLoadImages.js JavaScript ファイルを参照SharePointする
  
これを機能するには、マスター ページで jQuery も参照する必要があります。 次の例では、最初のページの読み込みで、読み込まれるイメージは 1 つのみですが、ページにはさらに複数のイメージが読み込まれているのを確認できます。
  
![ページに読み込まれた 1 つの画像を示すスクリーンショット。](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
次のスクリーンショットは、スクロールして表示した後にダウンロードされる残りのイメージを示しています。
  
![ページに読み込まれた複数の画像を示すスクリーンショット。](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
JavaScript を使用してイメージの読み込みを遅延させるのは、パフォーマンスを向上させる効果的な手法です。ただし、この手法がパブリック Web サイトに適用されている場合、検索エンジンは、定期的に形成されたイメージをクロールするのと同じ方法でイメージをクロールできます。 これは、ページが読み込まれるまで画像自体のメタデータが実際にはそこにないので、検索エンジンのランク付けに影響を与える可能性があります。 検索エンジン のクローラは HTML のみを読み取り、ページに画像をコンテンツとして表示しない。 画像は、検索結果のページのランク付けに使用される要素の 1 つです。 これを回避する 1 つの方法は、画像に入門テキストを使用する方法です。
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHubサンプル: JavaScript を挿入してパフォーマンスを向上させる

JavaScript インジェクションに関する記事とコード[](https://go.microsoft.com/fwlink/p/?LinkId=524759)サンプルをお見逃しなくGitHub。
  
## <a name="see-also"></a>関連項目

[2013 年および 2013 年OfficeでサポートされているMicrosoft 365 Apps for enterprise](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)