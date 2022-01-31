---
title: Microsoft ドキュメントのサンプル ドキュメント理解モデルをインポートSharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.custom: intro-get-started
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: サンプル モデルを使用したドキュメント理解モデルについて説明します。
ms.openlocfilehash: 6e7c680bcb136b52e0b3c9821471d922d43b614b
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281172"
---
# <a name="import-a-sample-document-understanding-model-for-microsoft-sharepoint-syntex"></a>Microsoft ドキュメントのサンプル ドキュメント理解モデルをインポートSharePoint Syntex

SharePoint Syntexを確認するために使用できるサンプル モデルを提供し、独自のモデルを作成する方法をよりよく理解できます。 サンプルモデルでは、分類子、抽出子、説明などのモデル コンポーネントを調べることもできます。 サンプル ファイルを使用して、モデルをトレーニングすることもできます。

## <a name="import-the-sample-model"></a>サンプルモ デルをインポートする

サンプルモデルにアクセスするには、最初にモデルをコンテンツ センターにインポートする必要があります。

1. コンテンツ センターから[**モデル**]を選択して、モデルリストを表示します。</br>
2. [**モデル**]ページで、[**サンプルモデルのインポート**]を選択します。</br>

    ![サンプル モデルのインポート。](../media/content-understanding/import-sample-model.png) </br>

3. インポートが完了すると、**BenefitsChangeNotice** モデルのホーム ページが開きます。 今後サンプル モデルを開く必要がある場合は、コンテンツ センターのモデル リストから開くことができます。 </br>

     ![サンプル ホーム ページ。](../media/content-understanding/sample-home-page.png)</br>

サンプル モデルを分析してモデルがどのように構築されているかをよりよく理解するだけでなく、作業モデルとしてさらに進んで、次のようなことを行うことができます。

- 別の抽出子を追加します。 たとえば、*割引料金* を抽出するものを追加します。
- モデルをドキュメント ライブラリに適用し、トレーニング ファイルの一部をアップロードして、モデルがファイルを分類し、ファイルからデータを抽出する方法を確認します。

## <a name="get-sample-models"></a>サンプル モデルの取得

ドキュメント理解モデルの[異SharePoint Syntex](https://github.com/pnp/syntex-samples)使用パターンを示すコミュニティ サンプルを含むサンプル リポジトリにアクセスできます。 このリポジトリのサンプルには、ドキュメント理解モデル ファイルと、モデルのトレーニングに使用されるファイルの両方が含まれています。 インポートしたら、これらのモデルを使用してファイルを処理し、分類子と抽出器を表示および編集できます。

## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[エクストラクターを作成する](create-an-extractor.md)

[ドキュメント理解の概要](document-understanding-overview.md)

[フォーム処理モデルを作成する](create-a-form-processing-model.md)  
