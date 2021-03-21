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
description: JavaScript を使用してイメージの読み込みと非必須 JavaScript の読み込みを遅らせ、SharePoint Online ページの読み込み時間を削減する方法について説明します。
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919166"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="8965d-103">SharePoint Online での画像の読み込み遅延と JavaScript</span><span class="sxs-lookup"><span data-stu-id="8965d-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="8965d-104">この記事では、JavaScript を使用してイメージの読み込みを遅延し、ページの読み込み後まで重要でない JavaScript の読み込みを待機することで、SharePoint Online ページの読み込み時間を削減する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8965d-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="8965d-105">イメージは、SharePoint Online のページ読み込み速度に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="8965d-106">既定では、HTML ページの読み込み時に最新のほとんどのインターネット ブラウザーが画像をプリフェッチします。</span><span class="sxs-lookup"><span data-stu-id="8965d-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="8965d-107">これにより、ユーザーが下にスクロールするまで画像が画面に表示されない場合、ページの読み込み速度が不必要に遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="8965d-108">画像は、ブラウザーがページの表示部分を読み込むのをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="8965d-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="8965d-109">この問題を回避するには、JavaScript を使用して、最初にイメージの読み込みをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="8965d-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="8965d-110">また、重要でない JavaScript を読み込むと、SharePoint ページのダウンロード時間も遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="8965d-111">このトピックでは、SharePoint Online の JavaScript でページの読み込み時間を短縮するために使用できるいくつかの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8965d-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="8965d-112">JavaScript を使用して SharePoint Online ページでのイメージの読み込みを遅らせ、ページの読み込み時間を短縮する</span><span class="sxs-lookup"><span data-stu-id="8965d-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="8965d-113">JavaScript を使用すると、Web ブラウザーによる画像の事前フェッチを防止できます。</span><span class="sxs-lookup"><span data-stu-id="8965d-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="8965d-114">これにより、ドキュメントの全体的なレンダリングが高速化されます。</span><span class="sxs-lookup"><span data-stu-id="8965d-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="8965d-115">これを行うには、タグから src 属性の値を削除し、それを data-src などのデータ属性内のファイルへのパスに \<img\> 置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="8965d-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8965d-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="8965d-117">このメソッドを使用すると、ブラウザーはイメージをすぐにダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="8965d-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="8965d-118">イメージが既にビューポート内にある場合、JavaScript はブラウザーに対して、データ属性から URL を取得し、src 属性の値として挿入します。</span><span class="sxs-lookup"><span data-stu-id="8965d-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="8965d-119">画像は、ユーザーがスクロールして表示される場合にのみ読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8965d-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="8965d-120">これをすべて実行するには、JavaScript を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="8965d-121">テキスト ファイルで **isElementInViewport()** 関数を定義して、ユーザーに表示されるブラウザーの一部に要素が含されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8965d-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="8965d-122">次に **、loadItemsInView()** 関数で **isElementInViewport() を使用** します。</span><span class="sxs-lookup"><span data-stu-id="8965d-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="8965d-123">**loadItemsInView()** 関数は、ユーザーに表示されるブラウザーの一部にある場合、data-src 属性の値を持つすべてのイメージを読み込むようになります。</span><span class="sxs-lookup"><span data-stu-id="8965d-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="8965d-124">テキスト ファイルに次の関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="8965d-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="8965d-125">最後に、次の例に示すように **、window.onscroll()** 内から **loadItemsInView()** を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8965d-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="8965d-126">これにより、ユーザーが必要とするとビューポート内のすべてのイメージが読み込まれますが、以前は読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="8965d-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="8965d-127">テキスト ファイルに次の項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="8965d-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="8965d-128">SharePoint Online では、次の関数をワークスペース タグのスクロール イベントに#s4する必要 \<div\> があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="8965d-129">これは、リボンがページの上部に接続されたままに維持するために、ウィンドウ イベントが上書きされるためです。</span><span class="sxs-lookup"><span data-stu-id="8965d-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="8965d-130">テキスト ファイルを拡張子 .js を持つ JavaScript ファイルとして保存します (たとえば、delayLoadImages.js。</span><span class="sxs-lookup"><span data-stu-id="8965d-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="8965d-131">ファイルの作成がdelayLoadImages.jsしたら、SharePoint Online のマスター ページにファイルの内容を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8965d-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="8965d-132">これを行うには、マスター ページのヘッダーにスクリプト リンクを追加します。</span><span class="sxs-lookup"><span data-stu-id="8965d-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="8965d-133">マスター ページが作成されると、そのマスター ページ レイアウトを使用する SharePoint Online サイトのすべてのページに JavaScript が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8965d-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="8965d-134">または、サイトの 1 ページでのみこれを使用する場合は、スクリプト エディター Web パーツを使用して JavaScript をページに埋め込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="8965d-135">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8965d-135">See these topics for more information:</span></span>
  
- <span data-ttu-id="8965d-136">[[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="8965d-136">[How to: Apply a master page to a site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)</span></span>

- <span data-ttu-id="8965d-137">[[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="8965d-137">[How to: Create a page layout in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)</span></span>

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="8965d-138">例: SharePoint Online delayLoadImages.jsページから JavaScript ファイルを参照する</span><span class="sxs-lookup"><span data-stu-id="8965d-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="8965d-139">これを機能するには、マスター ページで jQuery も参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="8965d-140">次の例では、最初のページの読み込みで、読み込まれるイメージは 1 つのみですが、ページにはさらに複数のイメージが読み込まれているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8965d-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![ページ上に読み込まれる 1 つのイメージが表示されたスクリーンショット](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="8965d-142">次のスクリーンショットは、スクロールして表示した後にダウンロードされる残りのイメージを示しています。</span><span class="sxs-lookup"><span data-stu-id="8965d-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![ページ上に読み込まれる複数のイメージが表示されたスクリーンショット](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="8965d-144">JavaScript を使用してイメージの読み込みを遅延させるのは、パフォーマンスを向上させる効果的な手法です。ただし、この手法がパブリック Web サイトに適用されている場合、検索エンジンは、定期的に形成されたイメージをクロールするのと同じ方法でイメージをクロールできます。</span><span class="sxs-lookup"><span data-stu-id="8965d-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="8965d-145">これは、ページが読み込まれるまで画像自体のメタデータが実際にはそこにないので、検索エンジンのランク付けに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8965d-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="8965d-146">検索エンジン のクローラは HTML のみを読み取り、ページに画像をコンテンツとして表示しない。</span><span class="sxs-lookup"><span data-stu-id="8965d-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="8965d-147">画像は、検索結果のページのランク付けに使用される要素の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8965d-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="8965d-148">これを回避する 1 つの方法は、画像に入門テキストを使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="8965d-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="8965d-149">GitHub コード サンプル: JavaScript を挿入してパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="8965d-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="8965d-150">GitHub で提供される [JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) インジェクションに関する記事とコード サンプルをお見逃しなく。</span><span class="sxs-lookup"><span data-stu-id="8965d-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8965d-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="8965d-151">See also</span></span>

[<span data-ttu-id="8965d-152">エンタープライズ向け Office 2013 Microsoft 365 Apps でサポートされるブラウザー</span><span class="sxs-lookup"><span data-stu-id="8965d-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
<span data-ttu-id="8965d-153">[[方法]: SharePoint Server 2013 のサイトにマスター ページを適用する](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="8965d-153">[How to: Apply a master page to a site in SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)</span></span>
  
<span data-ttu-id="8965d-154">[[方法]: SharePoint 2013 でページ レイアウトを作成する方法](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)</span><span class="sxs-lookup"><span data-stu-id="8965d-154">[How to: Create a page layout in SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)</span></span>