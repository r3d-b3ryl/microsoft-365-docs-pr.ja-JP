---
title: ドキュメント理解の概要
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex でのドキュメント理解の概要を説明します。
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222757"
---
# <a name="document-understanding-overview"></a>ドキュメント理解の概要


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

ドキュメント理解では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。 手紙や契約書などの非構造化ドキュメントで最適に機能します。 これらのドキュメントには、フレーズやパターンに基づいて識別できるテキストが含まれている必要があります。 識別されたテキストは、ファイルのタイプ (分類) および抽出するもの (抽出プログラム) の両方を指定します。

> [!NOTE]
> ドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](./adoption-getstarted.md)」を参照してください。

ドキュメント理解モデルは、*コンテンツ センター* と呼ばれる一種の SharePoint サイトで作成および管理されます。 SharePoint ドキュメント ライブラリに適用した場合、モデルはコンテンツタイプに関連付けられ、抽出される情報を格納するための列が含まれます。 作成したコンテンツタイプは、SharePoint コンテンツタイプ ギャラリーに保存されます。 既存のコンテンツ タイプを使用してスキーマを使用することもできます。

> [!NOTE]
> 読み取り専用、またはシールされたコンテンツ タイプは更新できないため、モデルに使用することはできません。

*分類子* と *抽出子* をドキュメント理解モデルに追加して、以下を実行します。 

- 分類子は、ドキュメント ライブラリにアップロードされたドキュメントを識別および分類するために使用されます。 たとえば、分類子を "トレーニング" して、ライブラリにアップロードされているすべての契約 *更新ドキュメント* を識別させることができます。 契約更新コンテンツ タイプは、分類子を作成するときにユーザーが定義します。

- 抽出子は、これらのドキュメントから情報を引き出します。 たとえば、ドキュメント ライブラリで識別されたすべての契約更新ドキュメントについて、各契約更新ドキュメントの *サービス開始日* と *クライアント* を示す列がビューに表示されます。 

サンプルファイルを使用して、モデル内の分類子と抽出子をトレーニングおよびテストできます。 サンプルファイルは、ファイルからデータを識別して抽出しようとするときに何を探すべきかについてのモデル例を提供します。 たとえば、会社が使用している契約更新ドキュメントの例を使用して、契約更新の分類子と抽出子をトレーニングします。 サンプルファイルを使用して、モデルの有効性をテストすることもできます。

モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。  

### <a name="file-limitations"></a>ファイルの制限事項

ドキュメント理解モデルは、光学式文字認識 (OCR) テクノロジーを使用して、PDF、画像、および TIFF ファイルをスキャンします。これは、サンプル ファイルを使用してモデルをトレーニングする場合と、ドキュメント ライブラリ内のファイルに対してモデルを実行する場合の両方です。

Microsoft Office のテキストベース ファイルと OCR スキャン ファイル (PDF、画像、または TIFF) に関して、次の違いに注意してください。

- Office ファイル: 64K 文字を切り捨てます (トレーニング時およびドキュメント ライブラリ内のファイルに対して実行する場合)。
- OCR スキャン ファイル: 20 ページの制限があります。  

#### <a name="supported-file-types"></a>サポートされているファイルの種類

ドキュメント理解モデルでは、次のファイルの種類がサポートされます。

- doc
- docx
- eml
- heic
- heic
- htm
- html
- jpeg
- jpg
- markdown
- md
- msg
- pdf
- png
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[抽出子を作成する](create-an-extractor.md)

[コンテンツ センターを作成する](create-a-content-center.md)

[フォーム処理モデルを作成する](create-a-form-processing-model.md)

[モデルを適用する](apply-a-model.md)   

[ドキュメント理解とフォーム処理モデルの違い](difference-between-document-understanding-and-form-processing-model.md)
  
[フォーム処理の概要](form-processing-overview.md)

[SharePoint Syntex アクセシビリティ モード](accessibility-mode.md)