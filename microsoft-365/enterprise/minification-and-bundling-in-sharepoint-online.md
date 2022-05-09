---
title: SharePoint Online での縮小とバンドル
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 1/18/2022
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
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Web Essentials で縮小とバンドルの手法を使用して HTTP 要求を減らし、SharePoint Online でページを読み込むのにかかる時間を短縮する方法について説明します。
ms.openlocfilehash: fabf690f523cabf67fe775bbd1a10251a477f633
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807118"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>SharePoint Online での縮小とバンドル

この記事では、Web Essentials で縮小とバンドルの手法を使用して HTTP 要求の数を減らし、SharePoint Online でページを読み込むのにかかる時間を短縮する方法について説明します。
  
Web サイトをカスタマイズすると、カスタマイズをサポートするために、サーバーに大量の追加ファイルを追加する可能性があります。 JavaScript、CSS、イメージを追加すると、サーバーへの HTTP 要求の数が増え、Web ページの表示にかかる時間が長くなります。 同じ種類の複数のファイルがある場合は、これらのファイルをバンドルして、これらのファイルのダウンロードを高速化できます。
  
JavaScript ファイルと CSS ファイルの場合は、縮小というアプローチを使用することもできます。ここでは、必要のない空白文字やその他の文字を削除することで、ファイルの合計サイズを縮小できます。
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Web Essentials を使用した JavaScript ファイルと CSS ファイルの縮小とバンドル

Web Essentials などのサード パーティ製ソフトウェアを使用して、CSS ファイルと JavaScript ファイルをバンドルできます。
  
> [!IMPORTANT]
> Web Essentials は、サードパーティのオープンソースのコミュニティ ベースのプロジェクトです。 このソフトウェアは、Visual Studio 2012 およびVisual Studio 2013の拡張機能であり、Microsoft ではサポートされていません。 Web Essentials をダウンロードするには、Web Essentials の Web サイトを [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629)参照してください。
  
Web Essentials には、次の 2 つの形式のバンドルが用意されています。
  
- .bundle: CSS ファイルと JavaScript ファイルの場合
- .sprite: イメージの場合 (Visual Studio 2013でのみ使用できます)

カスタム マスター ページ内で参照されるいくつかのブランド要素を持つ既存の機能がある場合は、Web Essentials を使用できます。
  
![カスタム マスター ページのブランド要素のスクリーンショット。](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
### <a name="to-create-a-te000127218-and-css-bundle-in-web-essentials"></a>Web Essentials で TE000127218 と CSS バンドルを作成するには
  
1. Visual Studioのソリューション エクスプローラーで、バンドルに含めるファイルを選択します。
2. 選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** **Create JavaScript bundle file] (Web** Essentials \> Create JavaScript バンドル ファイル) を選択します。 例:

    ![Web Essentials のメニュー オプションを示すスクリーンショット。](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>JavaScript ファイルと CSS ファイルをバンドルした結果を表示する

JavaScript と CSS バンドルを作成すると、Web Essentials は、JavaScript ファイルと CSS ファイル、およびその他の構成情報を識別するレシピ ファイルと呼ばれる XML ファイルを作成します。
  
![JavaScript と CSS のレシピ ファイルのスクリーンショット。](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
さらに、バンドル レシピで minify フラグが true に設定されている場合、ファイルのサイズが小さくなり、まとめてバンドルされます。 つまり、マスター ページで参照できる新しい縮小バージョンの JavaScript ファイルが作成されました。
  
![minify フラグが true に設定されているスクリーンショット。](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Web サイトからページを読み込むと、Internet Explorer 11 などの Web ブラウザーの開発者ツールを使用して、サーバーに送信された要求の数と各ファイルの読み込みにかかった時間を確認できます。
  
次の図は、縮小前に JavaScript ファイルと CSS ファイルを読み込む結果です。
  
![ダウンロード中の 80 個のアイテムを示すスクリーンショット。](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
CSS ファイルと JavaScript ファイルをバンドルした後、要求の数は 74 に減少し、各ファイルは個別にダウンロードするために元のファイルよりわずかに長く済みました。
  
![ダウンロード中の 74 個のアイテムを示すスクリーンショット。](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
バンドル後、JavaScript バンドル ファイルは 815 KB から 365 KB に大幅に削減されます。
  
![ダウンロード サイズの縮小を示すスクリーンショット。](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>画像スプライトを作成して画像をバンドルする

JavaScript ファイルと CSS ファイルをバンドルする方法と同様に、多くの小さなアイコンやその他の一般的な画像を大きなスプライト シートに結合し、CSS を使用して個々の画像を表示できます。 ユーザーの Web ブラウザーは、個々の画像をダウンロードする代わりに、スプライト シートを 1 回ダウンロードし、ローカル コンピューターにキャッシュします。 これにより、Web サーバーへのダウンロード数とラウンド トリップ数を減らすことで、ページ読み込みのパフォーマンスが向上します。
  
### <a name="to-create-an-image-sprite-in-web-essentials"></a>Web Essentials でイメージ スプライトを作成するには**
  
1. Visual Studioのソリューション エクスプローラーで、バンドルに含めるファイルを選択します。
2. 選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** Create image sprite] (Web Essentials \> **Create image sprite** ) を選択します。 例:

    ![イメージ スプライトを作成する方法を示すスクリーンショット。](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. スプライト ファイルを保存する場所を選択します。 .sprite ファイルは、スプライト内の設定とファイルを記述する XML ファイルです。 次の図は、スプライト PNG ファイルとそれに対応する .sprite XML ファイルの例を示しています。

    ![スプライト ファイルのスクリーンショット。](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![スプライト XML ファイルのスクリーンショット。](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
