---
title: オンラインクラシック発行サイトSharePointの画像の最適化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
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
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Renditions とスプライトを使用して、オンライン の従来の発行サイトでの画像SharePoint向上させる方法について学習します。
ms.openlocfilehash: 15885f1d8803332e24e2656a48b796dab28c665f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924577"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a><span data-ttu-id="8d1c5-103">オンラインクラシック発行サイトSharePointの画像の最適化</span><span class="sxs-lookup"><span data-stu-id="8d1c5-103">Image optimization for SharePoint Online classic publishing sites</span></span>

<span data-ttu-id="8d1c5-104">Web ページの読み込み速度は、画像、HTML、JavaScript、CSS など、ページのレンダリングに必要なすべてのコンポーネントの合計サイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-104">The loading speed of a webpage depends on the combined size of all the components required to render the page including images, HTML, JavaScript, and CSS.</span></span> <span data-ttu-id="8d1c5-105">画像は、サイトをより魅力的にする最適な方法ですが、サイズがパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-105">Images are a great way to make your site more appealing, but their size can affect performance.</span></span> <span data-ttu-id="8d1c5-106">圧縮とサイズ変更を使用して画像を最適化し、スプライトを使用すると、非常に大きな画像の効果を相殺できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-106">By optimizing your images with compression and resizing, and using sprites, you can offset the effects of very large images.</span></span> <span data-ttu-id="8d1c5-107">画像SharePointを使用すると、1 つの大きな画像をアップロードし、画像のセクションを表示して、再読み込みではなく再利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-107">Using SharePoint image renditions, you can upload a single large image, and display sections of the image allowing it to be reused rather than reloaded.</span></span>

>[!NOTE]
><span data-ttu-id="8d1c5-108">このトピックは、最新のSharePointサイトではなく、オンラインクラシック発行サイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-108">This topic applies to SharePoint Online classic publishing sites, not modern portal sites.</span></span> <span data-ttu-id="8d1c5-109">SharePoint Online モダン ポータル サイトでの画像の最適化の詳細については、「SharePoint Online モダン ポータル ページの[画像を最適化する」を参照してください](modern-image-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-109">For information about image optimization in SharePoint Online modern portal sites, see [Optimize images in SharePoint Online modern portal pages](modern-image-optimization.md).</span></span>
  
## <a name="using-sprites-to-speed-up-image-loading"></a><span data-ttu-id="8d1c5-110">スプライトを使用して画像の読み込みを高速化する</span><span class="sxs-lookup"><span data-stu-id="8d1c5-110">Using sprites to speed up image loading</span></span>

![spcommon のスクリーンショット](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)

<span data-ttu-id="8d1c5-112">イメージ スプライトには、小さい画像が多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-112">An image sprite contains many smaller images.</span></span> <span data-ttu-id="8d1c5-113">CSS を使用して、ページの特定の部分に表示する合成イメージの一部を絶対位置付けで選択します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-113">Using CSS you select a part of the composite image to display on a particular part of the page with absolute positioning.</span></span> <span data-ttu-id="8d1c5-114">基本的には、複数のイメージを読み込む代わりに、ページの周りに 1 つのイメージを移動し、そのイメージの小さな部分を、スプライト イメージの必要な部分がエンド ユーザーに表示される小さなウィンドウから表示します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-114">Basically, you move a single image around the page instead of loading multiple images, and make a small part of that image visible through a small window where the required part of the sprite image is shown to the end user.</span></span> <span data-ttu-id="8d1c5-115">SharePointOnline では、スプライトを使用して、スプライト ファイル内のさまざまなアイコンspcommon.pngします。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-115">SharePoint Online uses sprites to display its various icons in the sprite spcommon.png file.</span></span>

<span data-ttu-id="8d1c5-116">ここで説明する情報:</span><span class="sxs-lookup"><span data-stu-id="8d1c5-116">What's covered here:</span></span>
- <span data-ttu-id="8d1c5-117">画像の圧縮</span><span class="sxs-lookup"><span data-stu-id="8d1c5-117">Image compression</span></span>
- <span data-ttu-id="8d1c5-118">画像の最適化</span><span class="sxs-lookup"><span data-stu-id="8d1c5-118">Image optimization</span></span>
- <span data-ttu-id="8d1c5-119">SharePoint表示</span><span class="sxs-lookup"><span data-stu-id="8d1c5-119">SharePoint image renditions</span></span>
   
<span data-ttu-id="8d1c5-120">これは、複数のイメージではなく 1 つのイメージのみをダウンロードし、そのイメージをキャッシュして再利用するためにパフォーマンスを向上させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-120">This can increase performance because you download only one image instead of several and then cache and reuse that image.</span></span> <span data-ttu-id="8d1c5-121">イメージがキャッシュされたままでなくても、複数のイメージではなく 1 つのイメージを持つことで、このメソッドは HTTP 要求の総数をサーバーに削減し、ページの読み込み時間を短縮します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-121">Even if the image does not remain cached, by having a single image instead of multiple images, this method reduces the total number of HTTP requests to the server which will reduce page loading times.</span></span> <span data-ttu-id="8d1c5-122">これは、実際にはイメージのバンドルの形式です。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-122">This is really a form of image bundling.</span></span> <span data-ttu-id="8d1c5-123">これは、上記の例の例に示すように、アイコンなど、画像が頻繁に変更されない場合にSharePoint便利です。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-123">This is a very useful technique if the images are not changing very often, for example, icons, as shown in the SharePoint example provided above.</span></span> <span data-ttu-id="8d1c5-124">サードパーティのオープンソースのコミュニティベースのプロジェクトである[Web Essentials](https://vswebessentials.com/)を使用して、これを簡単に実現する方法をMicrosoft Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-124">You can how to use [Web Essentials](https://vswebessentials.com/), a third-party, open-source, community-based project to achieve this easily in Microsoft Visual Studio.</span></span> <span data-ttu-id="8d1c5-125">詳細については、「Minification and bundling in SharePoint [Online」を参照してください](./minification-and-bundling-in-sharepoint-online.md)。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-125">For more information, see [Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).</span></span>
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a><span data-ttu-id="8d1c5-126">画像の圧縮と最適化を使用してページの読み込みを高速化する</span><span class="sxs-lookup"><span data-stu-id="8d1c5-126">Using image compression and optimization to speed up page loading</span></span>

<span data-ttu-id="8d1c5-127">画像の圧縮と最適化は、サイトで使用する画像のファイル サイズを小さくすることです。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-127">Image compression and optimization is about reducing the file size of the images you use on your site.</span></span> <span data-ttu-id="8d1c5-128">多くの場合、画像のサイズを小さくする最善の方法は、サイトで表示される最大サイズにイメージのサイズを変更することです。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-128">Often, the best technique to reduce the size of an image is to resize the image to the maximum dimensions that it will be viewed on the site.</span></span> <span data-ttu-id="8d1c5-129">画像が表示されるよりも大きいイメージを持つことは意味がありません。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-129">There is no sense in having an image larger than it will ever be viewed.</span></span> <span data-ttu-id="8d1c5-130">イメージ エディターを使用して画像が正しいサイズに設定されていることを確認すると、ページのサイズを簡単かつ簡単に削減できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-130">Making sure images are of the correct dimensions using an image editor is a quick and easy way to reduce the size of your page.</span></span>
  
<span data-ttu-id="8d1c5-131">画像のサイズが適切な場合は、次に、これらの画像の圧縮を最適化します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-131">Once images are the right size, the next step is to optimize the compression of these images.</span></span> <span data-ttu-id="8d1c5-132">フォト ギャラリーやサード パーティ製のツールなど、圧縮と最適化に使用できるさまざまなツールがあります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-132">There are various tools available to use for compression and optimization, including Photo Gallery and third-party tools.</span></span> <span data-ttu-id="8d1c5-133">圧縮の鍵は、エンド ユーザーの識別可能な品質を失わずに、ファイル サイズを可能な限り小さくすることです。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-133">The key to compression is to reduce the file size as much as possible without losing any discernible quality for end users.</span></span> <span data-ttu-id="8d1c5-134">圧縮ファイルが引き続き良好に表示される場合は、高解像度ディスプレイでテストしてください。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-134">Make sure you test your compressed files on a high-definition display to ensure they will still look good.</span></span>
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a><span data-ttu-id="8d1c5-135">イメージ表示を使用してページのダウンロードSharePoint高速化する</span><span class="sxs-lookup"><span data-stu-id="8d1c5-135">Speed up page downloads by using SharePoint image renditions</span></span>

<span data-ttu-id="8d1c5-136">画像表示は、SharePoint Online の機能で、定義済みの画像サイズに基づいてさまざまなバージョンの画像を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-136">Image renditions are a feature in SharePoint Online that allows you to serve up different versions of images based on pre-defined image dimensions.</span></span> <span data-ttu-id="8d1c5-137">これは、ユーザーが生成した画像コンテンツがある場合や、サイト上の CSS によって幅や高さなどの画像のサイズが固定されている場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-137">This is especially important when there is user-generated image content or the image dimensions such as width and height are fixed by the CSS on the site.</span></span> <span data-ttu-id="8d1c5-138">イメージが CSS によって固定されている場合でも、完全な解像度のイメージは読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-138">Even if an image is fixed by CSS, the full resolution image is still loaded.</span></span> <span data-ttu-id="8d1c5-139">この場合、イメージ表示を使用してファイル サイズを縮小できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-139">In this case the file size can be reduced by using image renditions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d1c5-140">Renditions は、発行が有効になっているSharePointに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-140">Renditions are only available for SharePoint when publishing is enabled.</span></span> <span data-ttu-id="8d1c5-141">[サイトの公開] の下設定を有効設定サーバー発行のサイト機能SharePoint \> \> \> 管理します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-141">You can enable publishing under Settings \> Site Settings \> Manage site features \> SharePoint Server Publishing.</span></span> <span data-ttu-id="8d1c5-142">それ以外の場合は、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-142">The option will not appear otherwise.</span></span>
  
<span data-ttu-id="8d1c5-143">イメージ表示のサイズ変更は、定義した最小のサイズ (幅または高さ) を取得してから、ロックされた縦横比に基づいて他のディメンションのサイズが自動的に変更されるイメージのサイズを変更することで機能します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-143">The image rendition resizing works by taking the smallest dimension you define, either width or height, and then resizing the image so that the other dimension is automatically resized based on the locked aspect ratio.</span></span> <span data-ttu-id="8d1c5-144">既定では、画像は中央から残りの寸法でトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-144">By default, it will crop the image from the center by the remaining dimensions.</span></span> <span data-ttu-id="8d1c5-145">たとえば、幅 100 ピクセル、高さ 50px の表示を定義し、元のイメージの幅が 1000px、高さ 800px の場合、800px ディメンションが 50px、1000px ディメンション (現在は 62.5px) がイメージの中央からトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-145">For example, if you define a rendition of 100px wide and 50px high and your original image is 1000px wide and 800px high, it will be resized so that the 800px dimension is now 50px and the 1000px dimension (now 62.5px) is cropped from the center of the image.</span></span>
  
<span data-ttu-id="8d1c5-146">手順は比較的簡単ですが、イメージが表示を使用するには、イメージを追加する前に、SharePoint サイト上に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-146">The steps are relatively simple but for images to use the renditions, the renditions need to be on the SharePoint site before you add the images.</span></span> <span data-ttu-id="8d1c5-147">さらに、SharePoint サーバー発行インフラストラクチャ (サイト コレクション レベル) と SharePoint サーバー発行 (サイト レベル) 機能を有効にしている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-147">In addition, you also need to have the SharePoint Server Publishing Infrastructure (Site Collection Level) and SharePoint Server Publishing (Site Level) features turned on.</span></span>
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a><span data-ttu-id="8d1c5-148">ページの読み込みを高速化するイメージ表示を追加する</span><span class="sxs-lookup"><span data-stu-id="8d1c5-148">Add an image rendition to speed up page loading</span></span>
  
1. <span data-ttu-id="8d1c5-149">この手順を実行しているユーザー アカウントに、少なくともサイト コレクションのトップ レベル サイトに対するデザインアクセス許可が付与され、サイトが Web ページに公開されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-149">Verify that the user account that is performing this procedure has, at minimum, Design permissions to the top-level site of the site collection, and that the site is being published to a webpage.</span></span>

2. <span data-ttu-id="8d1c5-150">Web ブラウザーで、発行サイト コレクションのトップ レベル のサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-150">In a web browser, go to the top-level site of the publishing site collection.</span></span>

3. <span data-ttu-id="8d1c5-151">[ **設定**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-151">Choose the **Settings** icon.</span></span>

4. <span data-ttu-id="8d1c5-152">[サイト **の設定]** ページの [外観] セクションに、組み込みのイメージ表示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-152">On the **Site Settings** page, in the **Look and Feel** section, you will see the built-in image renditions.</span></span>

    <span data-ttu-id="8d1c5-153">ボックスの表示を使用するか、[ **イメージ** 表示] を選択して新しい表示を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-153">You can use the out of the box renditions or choose **Image Renditions** to create a new one.</span></span>

    ![Image Rendition のスクリーンショット](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. <span data-ttu-id="8d1c5-155">**[イメージ表示]** ページで **[新しいアイテムの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-155">On the **Image Renditions** page, choose **Add new item**.</span></span>

    ![[新しい項目の追加] のスクリーンショット](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. <span data-ttu-id="8d1c5-157">[ **新しいイメージ表示**] ページの [ **名前**] ボックスに、表示の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-157">On the **New Image Rendition** page, in the **Name** box, enter a name for the rendition.</span></span>

7. <span data-ttu-id="8d1c5-158">[ **幅**] ボックスおよび [ **高さ**] ボックスに、ピクセル単位で表示の幅と高さを入力して、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-158">In the **Width** and **Height** text boxes, enter the width and height, in pixels, of the rendition, and then choose **Save**.</span></span>

    ![イメージ表示名のスクリーンショット](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a><span data-ttu-id="8d1c5-160">イメージ表示を使用したカスタム トリミング</span><span class="sxs-lookup"><span data-stu-id="8d1c5-160">Custom cropping with image renditions</span></span>

<span data-ttu-id="8d1c5-161">既定では、イメージ表示はイメージの中央から生成されます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-161">By default, an image rendition is generated from the center of the image.</span></span> <span data-ttu-id="8d1c5-162">イメージの使用する部分をトリミングすることにより、個別のイメージのイメージ表示を調整できます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-162">You can adjust the image rendition for individual images by cropping the portion of the image that you want to use.</span></span> <span data-ttu-id="8d1c5-163">画像は、表示ごとに個別にトリミングできます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-163">You can crop the images on an individual basis, per rendition.</span></span> <span data-ttu-id="8d1c5-164">イメージをトリミングすると、SharePoint BLOB キャッシュを使用して各表示のイメージのバージョンを作成することで、ページの読み込みが高速化されます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-164">Cropping the images speeds up page loading by using SharePoint's blob cache to create a version of the image for each rendition.</span></span> <span data-ttu-id="8d1c5-165">この方法では、イメージのサイズが 1 回だけ変更され、エンド ユーザーに複数回サービスを提供する準備ができているため、サーバーの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-165">This way the server load is reduced because the image is only resized once and is then ready to serve to end users multiple times.</span></span> <span data-ttu-id="8d1c5-166">イメージ表示をトリミングする方法の詳細については、「Crop an [image rendition 」を参照してください](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)。</span><span class="sxs-lookup"><span data-stu-id="8d1c5-166">For more information on how to crop an image rendition, see [Crop an image rendition](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels).</span></span>
