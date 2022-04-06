---
title: Microsoft SharePoint Syntex での事前構築済みモデルの概要
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft SharePoint Syntex の事前構築済みモデルについて説明します。
ms.openlocfilehash: 1146e4947392ce0e0848632e55f22e5b8b8d2d91
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569050"
---
# <a name="prebuilt-models-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex での事前構築済みモデルの概要

ドキュメントの理解[モデルとフォーム](document-understanding-overview.md)処理[](form-processing-overview.md)モデルに加えて、SharePoint Syntex情報の抽出を自動化するための事前構築されたモデルが用意されています。

事前構築済みのモデルは、ドキュメントとドキュメント内の構造化された情報を認識するように事前にトレーニングされています。 新しいカスタム モデルを最初から作成する代わりに、既存の事前トレーニング済みモデルを反復処理して、組織のニーズに合った特定のフィールドを追加できます。 

事前構築済みのモデルでは、光学式文字認識 (OCR) とディープ ラーニング モデルを組み合わせて使用して、特定のドキュメントの種類に共通する定義済みのテキストフィールドとデータ フィールドを識別および抽出します。 まず、作成済みのモデルに対してファイルの 1 つを分析します。 次に、目的に合った検出されたフィールドを選択します。 モデルが必要なフィールドを検出しない場合は、別のファイルを使用してもう一度分析できます。

ドキュメントの理解モデルと同様に、事前構築済みのモデルはコンテンツ センターで [作成および管理されます](create-a-content-center.md)。 ドキュメント ライブラリに適用SharePoint、モデルはコンテンツ タイプに関連付けられるので、抽出される情報を格納する列があります。 

モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。  

## <a name="requirements"></a>Requirements

- サポートされているファイル形式: JPEG、PNG、BMP、TIFF、PDF (テキスト埋め込みまたはスキャン)。

- サポートされている言語: 現在サポートされている言語の米国英語の請求書のみです。 オーストラリア、カナダ、カナダ、米国、インドからの英語の販売領収書がサポートされています。

- テキスト埋め込み PDF は、文字の抽出と場所でエラーが発生する可能性を排除するために最適です。

- PDF および TIFF では、最大 2,000 ページまで処理できます。

- ファイル サイズは 50 MB 未満である必要があります。

- 画像のサイズは、50 x 50 ピクセルから 10,000 x 10,000 ピクセルの間である必要があります。

- PDF のサイズは、リーガルまたは A3 用紙サイズに対応する最大 17 x 17 インチ、または小さいサイズです。

- トレーニング データの合計サイズは 500 ページ以下です。

### <a name="file-limitations"></a>ファイルの制限事項

テキスト ベースのファイルと OCR スキャンMicrosoft Office (PDF、イメージ、または TIFF) に関する次の違いに注意してください。

- Officeファイル: 64,000 文字で切り捨て (ドキュメント ライブラリ内のファイルに対して実行する場合)。

- OCR スキャン ファイル: 20 ページの制限があります。  

## <a name="model-considerations"></a>モデルに関する考慮事項

- 2 つ以上の事前構築済みモデルを同じライブラリに適用すると、平均信頼度スコアが最も高いモデルを使用してファイルが分類されます。 抽出されたエンティティは、適用されたモデルからのみ取得されます。

- 事前構築済みモデルがドキュメント理解モデルを持つライブラリに適用される場合、ファイルはドキュメント理解モデルと、そのモデルのトレーニング済み抽出プログラムを使用して分類されます。 事前構築済みモデルに一致する空の列がある場合、それらの抽出された値を使用して列が設定されます。

- カスタム フォーム処理モデルを持つライブラリに事前構築済みモデルを適用する場合、ファイルは事前構築済みモデルと、そのモデルで検出された抽出器を使用して分類されます。 フォーム処理モデルに一致する空の列がある場合、それらの抽出された値を使用して列が設定されます。

- 複数のカスタム フォーム処理モデルをライブラリに適用する機能はサポートされていません。


## <a name="see-also"></a>関連項目

[事前構築済みモデルを使用して請求書または領収書から情報を抽出する](prebuilt-overview.md)
 

