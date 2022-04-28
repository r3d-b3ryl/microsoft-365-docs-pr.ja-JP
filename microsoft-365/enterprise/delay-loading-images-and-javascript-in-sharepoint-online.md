---
title: SharePoint Online での画像の読み込み遅延と JavaScript
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: JavaScript を使用してイメージの読み込みを遅延し、必須ではない JavaScript を使用して、SharePoint Online ページの読み込み時間を短縮する方法について説明します。
ms.openlocfilehash: af75b3ede1136894bea0a7f4c00cc9498d194fe3
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101295"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>SharePoint Online での画像の読み込み遅延と JavaScript

この記事では、JavaScript を使用してイメージの読み込みを遅延し、ページの読み込み後まで重要でない JavaScript の読み込みを待機することで、SharePoint Online ページの読み込み時間を短縮する方法について説明します。
  
イメージは、SharePoint Online のページ読み込み速度に悪影響を及ぼす可能性があります。 既定では、ほとんどの最新のインターネット ブラウザーは、HTML ページの読み込み時に画像をプリフェッチします。 これにより、ユーザーが下にスクロールするまで画像が画面に表示されないと、ページの読み込みが不必要に遅くなる可能性があります。 イメージは、ブラウザーがページの表示部分を読み込むのをブロックできます。 この問題を回避するには、JavaScript を使用して最初にイメージの読み込みをスキップします。 また、重要でない JavaScript を読み込むと、SharePoint ページのダウンロード時間も遅くなる可能性があります。 このトピックでは、SharePoint Online で JavaScript を使用してページの読み込み時間を短縮するために使用できるいくつかの方法について説明します。
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>JavaScript を使用してSharePoint Online ページでの画像読み込みを遅らせることでページの読み込み時間を短縮する

JavaScript を使用すると、Web ブラウザーがイメージを事前にフェッチできないようにすることができます。 これにより、ドキュメントの全体的なレンダリングが高速化されます。 これを行うには、タグから src 属性の値を \<img\> 削除し、data-src などのデータ属性内のファイルへのパスに置き換えます。 次に例を示します。
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

このメソッドを使用すると、ブラウザーはイメージをすぐにダウンロードしません。 イメージがビューポートに既にある場合、JavaScript はブラウザーに対して、データ属性から URL を取得し、src 属性の値として挿入するように指示します。 イメージは、ユーザーがスクロールして表示されるときにのみ読み込まれます。
  
このすべてを実現するには、JavaScript を使用する必要があります。
  
テキスト ファイルで **isElementInViewport()** 関数を定義し、要素がユーザーに表示されるブラウザーの一部にあるかどうかを確認します。
  
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

次に、**loadItemsInView() 関数で isElementInViewport(****)** を使用します。 **loadItemsInView()** 関数は、ユーザーに表示されるブラウザーの一部にある場合、data-src 属性の値を持つすべてのイメージを読み込みます。 テキスト ファイルに次の関数を追加します。
  
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

最後に、次の例に示すように、**window.onscroll()** 内から **loadItemsInView**() を呼び出します。 これにより、ビューポート内のイメージはすべて、ユーザーが必要とするが、以前は読み込まれないようにします。 テキスト ファイルに次を追加します。
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

SharePoint Online の場合は、#s4 ワークスペース タグのスクロール イベントに次の関数をアタッチする必要があります\<div\>。 これは、リボンがページの上部にアタッチされたままになるように、ウィンドウ イベントがオーバーライドされるためです。
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

テキスト ファイルを JavaScript ファイルとして、拡張子.js (delayLoadImages.js など) で保存します。
  
delayLoadImages.jsの作成が完了したら、SharePoint Online のマスター ページにファイルの内容を追加できます。 これを行うには、マスター ページのヘッダーにスクリプト リンクを追加します。 マスター ページになると、そのマスター ページ レイアウトを使用するSharePoint Online サイトのすべてのページに JavaScript が適用されます。 または、サイトの 1 つのページでのみこれを使用する場合は、スクリプト エディター Web パーツを使用して JavaScript をページに埋め込みます。 詳細については、次のトピックを参照してください。
  
- [[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>例: SharePoint Online のマスター ページから JavaScript delayLoadImages.js ファイルを参照する
  
これを機能させるには、マスター ページで jQuery も参照する必要があります。 次の例では、最初のページ読み込みで、読み込まれたイメージは 1 つだけですが、ページにはさらに複数あることがわかります。
  
![ページに読み込まれた 1 つの画像を示すスクリーンショット。](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
次のスクリーンショットは、ビューにスクロールした後にダウンロードされた残りのイメージを示しています。
  
![ページに読み込まれたいくつかの画像を示すスクリーンショット。](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
JavaScript を使用してイメージの読み込みを遅らせることは、パフォーマンスを向上させる効果的な手法です。ただし、この手法がパブリック Web サイトに適用されている場合、検索エンジンは、定期的に形成されたイメージをクロールするのと同じ方法で画像をクロールできません。 これは、ページが読み込まれるまで画像自体のメタデータが実際には存在しないため、検索エンジンのランク付けに影響を与える可能性があります。 検索エンジン のクローラーは HTML のみを読み取るため、画像はページのコンテンツとして表示されません。 画像は、検索結果のページのランク付けに使用される要因の 1 つです。 これを回避する 1 つの方法は、画像に入門テキストを使用する方法です。
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHubコード サンプル: JavaScript を挿入してパフォーマンスを向上させる

GitHubで提供される [JavaScript インジェクション](https://go.microsoft.com/fwlink/p/?LinkId=524759)に関する記事とコード サンプルをお見逃しなく。
  
## <a name="see-also"></a>関連項目

[Office 2013 および Microsoft 365 Apps for enterprise でサポートされているブラウザー](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)