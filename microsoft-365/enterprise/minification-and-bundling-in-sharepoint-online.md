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
ms.openlocfilehash: 5ba1e174cbb016bdf88a1d4006a0b8aafd5ec042
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58567390"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>SharePoint Online での縮小とバンドル

この記事では、Web Essentials でミニフィケーションとバンドルの手法を使用して HTTP 要求の数を減らし、SharePoint Online のページの読み込みにかかる時間を短縮する方法について説明します。
  
Web サイトをカスタマイズすると、カスタマイズをサポートするためにサーバーに多数の追加ファイルを追加する結果になります。 JavaScript、CSS、およびイメージを追加すると、サーバーへの HTTP 要求の数が増え、Web ページの表示にかかる時間が長くなります。 同じ種類のファイルが複数の場合は、これらのファイルをバンドルして、これらのファイルのダウンロードを高速化できます。
  
JavaScript ファイルと CSS ファイルの場合は、ミニフィケーションと呼ばれるアプローチを使用して、空白文字や不要な文字を削除してファイルの合計サイズを小さくすることもできます。
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Web Essentials を使用した JavaScript ファイルと CSS ファイルのマイニングとバンドル

Web Essentials などのサード パーティ製ソフトウェアを使用して、CSS ファイルと JavaScript ファイルをバンドルできます。
  
> [!IMPORTANT]
> Web Essentials は、サードパーティのオープンソースのコミュニティ ベースのプロジェクトです。 このソフトウェアは、2012 年および 2012 年Visual Studioの拡張機能Visual Studio 2013 Microsoft ではサポートされていません。 Web Essentials をダウンロードするには、以下の Web サイトを参照してください [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 。 
  
Web Essentials には、次の 2 つの形式のバンドルが用意されています。
  
- .bundle: CSS および JavaScript ファイルの場合
    
- .sprite: イメージの場合 (Visual Studio 2013 でのみ使用可能)
    
カスタム マスター ページ内で参照されるブランド要素を持つ既存の機能がある場合は、Web Essentials を使用できます。
  
![カスタム マスター ページの brand 要素のスクリーンショット。](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Web Essentials で TE000127218 と CSS バンドルを作成するには**
  
1. [Visual Studio エクスプローラーで、バンドルに含めるファイルを選択します。
    
2. 選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** \> **Create JavaScript バンドル ファイル** ] を選択します。 次に例を示します。 
    
    ![Web Essentials メニュー オプションを示すスクリーンショット。](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>JavaScript ファイルと CSS ファイルのバンドル結果の表示

JavaScript および CSS バンドルを作成すると、Web Essentials は、JavaScript ファイルと CSS ファイル、および他のいくつかの構成情報を識別するレシピ ファイルと呼ばれる XML ファイルを作成します。 
  
![JavaScript および CSS レシピ ファイルのスクリーンショット。](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
さらに、バンドル レシピで minify フラグが true に設定されている場合は、ファイルのサイズが縮小され、バンドルされます。 つまり、マスター ページで参照できる JavaScript ファイルの新しいバージョンが作成されました。
  
![minify フラグが true に設定されているスクリーンショット。](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Web サイトからページを読み込む場合は、Internet Explorer 11 などの Web ブラウザーの開発者ツールを使用して、サーバーに送信された要求の数と各ファイルの読み込み時間を確認できます。
  
次の図は、Minification の前に JavaScript ファイルと CSS ファイルを読み込む結果です。
  
![ダウンロード中の 80 アイテムを示すスクリーンショット。](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
CSS ファイルと JavaScript ファイルをバンドルした後、要求の数は 74 に減少し、各ファイルは個別にダウンロードするために元のファイルよりわずかに長くしかかからなくなりました。
  
![ダウンロード中の 74 アイテムを示すスクリーンショット。](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
バンドル後、JavaScript バンドル ファイルは 815 KB から 365 KB に大幅に減少します。
  
![ダウンロード サイズの縮小を示すスクリーンショット。](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>イメージ スプライトを作成してイメージをバンドルする

JavaScript ファイルと CSS ファイルをバンドルする方法と同様に、多くの小さなアイコンやその他の一般的な画像を大きなスプライト シートに結合し、CSS を使用して個々の画像を表示できます。 個々のイメージをダウンロードする代わりに、ユーザーの Web ブラウザーはスプライト シートを 1 回ダウンロードし、ローカル コンピューターにキャッシュします。 これにより、Web サーバーへのダウンロード数とラウンド トリップ数を削減することで、ページの読み込みパフォーマンスが向上します。
  
 **Web Essentials でイメージ スプライトを作成するには**
  
1. [Visual Studio エクスプローラーで、バンドルに含めるファイルを選択します。
    
2. 選択したファイルを右クリックし、コンテキスト メニューから **[Web Essentials** \> **Create image sprite]** を選択します。 次に例を示します。 
    
    ![イメージ スプライトを作成する方法を示すスクリーンショット。](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. スプライト ファイルを保存する場所を選択します。 .sprite ファイルは、スプライト内の設定とファイルを記述する XML ファイルです。 次の図は、スプライト PNG ファイルとその対応する .sprite XML ファイルの例を示しています。
    
    ![スプライト ファイルのスクリーンショット。](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![スプライト XML ファイルのスクリーンショット。](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

