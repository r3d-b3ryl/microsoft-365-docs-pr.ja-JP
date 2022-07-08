---
title: Microsoft SharePoint Syntex の事前構築済みモデルの概要
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
description: Microsoft SharePoint Syntexの事前構築済みモデルについて説明します。
ms.openlocfilehash: 47579f640e02874545177946534d81f1350104cd
ms.sourcegitcommit: ebaa70d0da4a600efe52b5008eaddb511d36df8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2022
ms.locfileid: "66687676"
---
# <a name="prebuilt-models-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex の事前構築済みモデルの概要

SharePoint Syntexは、[理解モデル](document-understanding-overview.md)と[フォーム処理モデル](form-processing-overview.md)を文書化するだけでなく、情報の抽出を自動化するための事前構築済みのモデルを提供します。

事前構築済みモデルは、ドキュメントとドキュメント内の構造化された情報を認識するように事前トレーニングされています。 新しいカスタム モデルを最初から作成する代わりに、既存の事前トレーニング済みモデルを反復処理して、組織のニーズに合った特定のフィールドを追加できます。 

事前構築済みモデルでは、光学式文字認識 (OCR) とディープ ラーニング モデルを組み合わせて使用し、特定のドキュメントの種類に共通する定義済みのテキストフィールドとデータ フィールドを識別して抽出します。 まず、事前構築済みモデルに対してファイルの 1 つを分析します。 次に、目的に合った検出されたフィールドを選択します。 モデルで必要なフィールドが検出されない場合は、別のファイルを使用して再度分析できます。

ドキュメント理解モデルと同様に、事前構築済みモデルは [コンテンツ センター](create-a-content-center.md)で作成および管理されます。 SharePoint ドキュメント ライブラリに適用すると、モデルはコンテンツ タイプに関連付け、抽出される情報を格納する列を持ちます。 

モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。  

## <a name="requirements"></a>要件

- サポートされているファイル形式: JPEG、PNG、BMP、TIFF、PDF (テキスト埋め込みまたはスキャン)。

- サポートされている言語: 現在、米国からの英語の請求書のみがサポートされています。 オーストラリア、カナダ、米国、英国、インドからの英語の販売レシートがサポートされています。

- テキスト埋め込み PDF は、文字の抽出と場所にエラーが発生する可能性を排除することをお勧めします。

- PDF と TIFF の場合、最大 2,000 ページを処理できます。

- ファイル サイズは 50 MB 未満である必要があります。

- 画像のサイズは、50 x 50 ピクセルから 10,000 x 10,000 ピクセルの間である必要があります。

- PDF サイズは最大 17 x 17 インチで、Legal または A3 用紙サイズに対応するか、小さくなります。

- トレーニング データの合計サイズは 500 ページ以下です。

### <a name="file-limitations"></a>ファイルの制限事項

Microsoft Office テキスト ベースのファイルと OCR スキャンされたファイル (PDF、画像、TIFF) については、次の違いに注意してください。

- Office ファイル: 64,000 文字で切り捨てられます (ドキュメント ライブラリ内のファイルに対して実行する場合)。

- OCR スキャン ファイル: 20 ページの制限があります。  

## <a name="model-considerations"></a>モデルに関する考慮事項

- 2 つ以上の事前構築済みモデルが同じライブラリに適用されている場合、ファイルは平均信頼度スコアが最も高いモデルを使用して分類されます。 抽出されたエンティティは、適用されたモデルからのみ取得されます。

- カスタム フォーム処理モデルを持つライブラリに事前構築済みモデルが適用されている場合、ファイルは事前構築済みモデルとそのモデルで検出されたすべての抽出器を使用して分類されます。 フォーム処理モデルに一致する空の列がある場合は、抽出された値を使用して列が設定されます。

- 複数のカスタム フォーム処理モデルをライブラリに適用することはサポートされていません。

## <a name="see-also"></a>関連項目

[事前構築済みモデルを使用して、請求書または領収書から情報を抽出する](prebuilt-overview.md)
 

