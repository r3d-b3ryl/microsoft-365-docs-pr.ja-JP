---
title: SharePoint Online での縮小とバンドル
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
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
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Web Essentials でミニフィケーションとバンドルの手法を使用して HTTP 要求を削減する方法と、Web オンラインでページを読み込むのにかかる時間SharePointします。
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691659"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="f34cf-103">SharePoint Online での縮小とバンドル</span><span class="sxs-lookup"><span data-stu-id="f34cf-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="f34cf-104">この記事では、Web Essentials でミニフィケーションとバンドルの手法を使用して HTTP 要求の数を減らし、SharePoint Online のページの読み込みにかかる時間を短縮する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="f34cf-105">Web サイトをカスタマイズすると、カスタマイズをサポートするためにサーバーに多数の追加ファイルを追加する結果になります。</span><span class="sxs-lookup"><span data-stu-id="f34cf-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="f34cf-106">JavaScript、CSS、およびイメージを追加すると、サーバーへの HTTP 要求の数が増え、Web ページの表示にかかる時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="f34cf-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="f34cf-107">同じ種類のファイルが複数の場合は、これらのファイルをバンドルして、これらのファイルのダウンロードを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="f34cf-108">JavaScript ファイルと CSS ファイルの場合は、ミニフィケーションと呼ばれるアプローチを使用して、空白文字や不要な文字を削除してファイルの合計サイズを小さくすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="f34cf-109">Web Essentials を使用した JavaScript ファイルと CSS ファイルのマイニングとバンドル</span><span class="sxs-lookup"><span data-stu-id="f34cf-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="f34cf-110">Web Essentials などのサード パーティ製ソフトウェアを使用して、CSS ファイルと JavaScript ファイルをバンドルできます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f34cf-111">Web Essentials は、サードパーティのオープンソースのコミュニティ ベースのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f34cf-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="f34cf-112">このソフトウェアは、2012 年および 2012 年Visual Studioの拡張機能Visual Studio 2013 Microsoft ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f34cf-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="f34cf-113">Web Essentials をダウンロードするには、以下の Web サイトを参照してください [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 。</span><span class="sxs-lookup"><span data-stu-id="f34cf-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="f34cf-114">Web Essentials には、次の 2 つの形式のバンドルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f34cf-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="f34cf-115">.bundle: CSS および JavaScript ファイルの場合</span><span class="sxs-lookup"><span data-stu-id="f34cf-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="f34cf-116">.sprite: イメージの場合 (Visual Studio 2013 でのみ使用可能)</span><span class="sxs-lookup"><span data-stu-id="f34cf-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="f34cf-117">カスタム マスター ページ内で参照されるブランド要素を持つ既存の機能がある場合は、Web Essentials を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![ユーザー設定のマスター ページ内のブランド要素のスクリーンショット](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="f34cf-119">**Web Essentials で TE000127218 と CSS バンドルを作成するには**</span><span class="sxs-lookup"><span data-stu-id="f34cf-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="f34cf-120">[Visual Studio エクスプローラーで、バンドルに含めるファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="f34cf-121">選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** \> **Create JavaScript バンドル ファイル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="f34cf-122">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-122">For example:</span></span> 
    
    ![Web Essentials のメニュー オプションが表示されているスクリーンショット](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="f34cf-124">JavaScript ファイルと CSS ファイルのバンドル結果の表示</span><span class="sxs-lookup"><span data-stu-id="f34cf-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="f34cf-125">JavaScript および CSS バンドルを作成すると、Web Essentials は、JavaScript ファイルと CSS ファイル、および他のいくつかの構成情報を識別するレシピ ファイルと呼ばれる XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![JavaScript と CSS レシピ ファイルのスクリーンショット](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="f34cf-127">さらに、バンドル レシピで minify フラグが true に設定されている場合は、ファイルのサイズが縮小され、バンドルされます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="f34cf-128">つまり、マスター ページで参照できる JavaScript ファイルの新しいバージョンが作成されました。</span><span class="sxs-lookup"><span data-stu-id="f34cf-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![true に設定された minify フラグのスクリーンショット](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="f34cf-130">Web サイトからページを読み込む場合は、Internet Explorer 11 などの Web ブラウザーの開発者ツールを使用して、サーバーに送信された要求の数と各ファイルの読み込み時間を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="f34cf-131">次の図は、Minification の前に JavaScript ファイルと CSS ファイルを読み込む結果です。</span><span class="sxs-lookup"><span data-stu-id="f34cf-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![ダウンロードされている 80 のアイテムが表示されているスクリーンショット](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="f34cf-133">CSS ファイルと JavaScript ファイルをバンドルした後、要求の数は 74 に減少し、各ファイルは個別にダウンロードするために元のファイルよりわずかに長くしかかからなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f34cf-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![ダウンロードされている 74 のアイテムが表示されているスクリーンショット](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="f34cf-135">バンドル後、JavaScript バンドル ファイルは 815 KB から 365 KB に大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![削減されたダウンロード サイズを示すスクリーンショット](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="f34cf-137">イメージ スプライトを作成してイメージをバンドルする</span><span class="sxs-lookup"><span data-stu-id="f34cf-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="f34cf-138">JavaScript ファイルと CSS ファイルをバンドルする方法と同様に、多くの小さなアイコンやその他の一般的な画像を大きなスプライト シートに結合し、CSS を使用して個々の画像を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f34cf-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="f34cf-139">個々のイメージをダウンロードする代わりに、ユーザーの Web ブラウザーはスプライト シートを 1 回ダウンロードし、ローカル コンピューターにキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="f34cf-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="f34cf-140">これにより、Web サーバーへのダウンロード数とラウンド トリップ数を削減することで、ページの読み込みパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="f34cf-141">**Web Essentials でイメージ スプライトを作成するには**</span><span class="sxs-lookup"><span data-stu-id="f34cf-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="f34cf-142">[Visual Studio エクスプローラーで、バンドルに含めるファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="f34cf-143">選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** \> **Create image sprite]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="f34cf-144">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-144">For example:</span></span> 
    
    ![画像のスプライトを作成する方法を示したスクリーンショット](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="f34cf-146">スプライト ファイルを保存する場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="f34cf-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="f34cf-147">.sprite ファイルは、スプライト内の設定とファイルを記述する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f34cf-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="f34cf-148">次の図は、スプライト PNG ファイルとその対応する .sprite XML ファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="f34cf-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![スプライト ファイルのスクリーンショット](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![スプライト XML ファイルのスクリーンショット](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

