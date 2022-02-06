---
title: Microsoft SharePoint Syntex のドキュメント理解の概要
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.customer: intro-overview
ms.prod: microsoft-365-enterprise
search.appverid: null
ms.collection:
  - enabler-strategic
  - m365initiative-syntex
ms.localizationpriority: medium
description: Microsoft SharePoint Syntex のドキュメント理解について説明します。
---

# <a name="document-understanding-overview-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex のドキュメント理解の概要


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

ドキュメント理解では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。 手紙や契約書などの非構造化ドキュメントで最適に機能します。 これらのドキュメントには、フレーズやパターンに基づいて識別できるテキストが含まれている必要があります。 識別されたテキストは、ファイルのタイプ (分類) および抽出するもの (抽出プログラム) の両方を指定します。

> [!NOTE]
> ドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](./adoption-getstarted.md)」を参照してください。

ドキュメント理解モデルは、*コンテンツ センター* と呼ばれる一種の SharePoint サイトで作成および管理されます。 SharePoint ドキュメント ライブラリに適用した場合、モデルはコンテンツタイプに関連付けられ、抽出される情報を格納するための列が含まれます。 作成したコンテンツタイプは、SharePoint コンテンツタイプ ギャラリーに保存されます。 既存のコンテンツ タイプを使用してスキーマを使用することもできます。

> [!NOTE]
> 読み取り専用、またはシールされたコンテンツ タイプは更新できないため、モデルに使用することはできません。

次 *のアクションを実行するには**、分類* 子と抽出器をドキュメント理解モデルに追加します。 

- 分類子は、ドキュメント ライブラリにアップロードされたドキュメントを識別および分類するために使用されます。 たとえば、分類子を "トレーニング" して、ライブラリにアップロードされているすべての契約 *更新ドキュメント* を識別させることができます。 契約更新コンテンツ タイプは、分類子を作成するときにユーザーが定義します。

- 抽出子は、これらのドキュメントから情報を引き出します。 たとえば、ドキュメント ライブラリで識別された契約更新ドキュメントごとに、各ドキュメントのサービス開始日と *クライアント* を示す列が表示されます。 

サンプルファイルを使用して、モデル内の分類子と抽出子をトレーニングおよびテストできます。 サンプルファイルは、ファイルからデータを識別して抽出しようとするときに何を探すべきかについてのモデル例を提供します。 たとえば、会社が使用している契約更新ドキュメントの例を使用して、契約更新の分類子と抽出子をトレーニングします。 サンプルファイルを使用して、モデルの有効性をテストすることもできます。

モデルを公開したら、コンテンツセンターを使用して、アクセスできる SharePoint ドキュメントライブラリにモデルを適用します。  

## <a name="file-limitations"></a>ファイルの制限事項

ドキュメント理解モデルでは、光学式文字認識 (OCR) テクノロジを使用して PDF、画像、TIFF ファイルをスキャンします。 ファイルは、サンプル ファイルを含むモデルをトレーニングするときに、およびドキュメント ライブラリ内のファイルに対してモデルを実行するときにスキャンされます。

テキスト ベースのファイルと OCR スキャンMicrosoft Office (PDF、イメージ、または TIFF) に関する次の違いに注意してください。

- Office ファイル: 64,000 文字を切り捨てます (トレーニング時およびドキュメント ライブラリ内のファイルに対して実行する場合)。

- OCR スキャン ファイル: 20 ページの制限があります。  

### <a name="requirements"></a>要件

OCR 処理は、次の要件を満たすドキュメントで最適に機能します。

- JPG、PNG、または PDF 形式 (テキストまたはスキャン)。 文字の抽出と場所にエラーが発生しないため、テキストが埋め込まれた PDF の方が優れています。

- PDF がパスワードでロックされている場合は、送信する前にロックを解除する必要があります。

- コレクションごとのトレーニングに使用されるドキュメントの合計ファイル サイズは 50 MB を超えてはならず、PDF ドキュメントは 500 ページを超えてはなりません。

- 画像の場合、サイズは 50×50 ピクセルと 10,000×10,000 ピクセルの間である必要があります。
   > [!NOTE]
   > 非常に幅が広い画像やサイズが奇数の画像 (平面図など) は、OCR プロセスで切り捨てられ、精度が低下する可能性があります。
 
- PDF ファイルの場合、サイズは最大 17 x 17 インチで、リーガルまたは A3 の用紙サイズ以下に対応する必要があります。

- 紙の文書からスキャンする場合、スキャンは高品質の画像である必要があります。

- ラテン アルファベット (英語の文字) を使用する必要があります。

> [!NOTE]
> AI ビルダーは現在、次の種類のフォーム処理入力データをサポートしていません。<br>- チェック ボックスまたはラジオ ボタン<br>- 署名<br>- 入力可能な PDF

### <a name="supported-file-types"></a>サポートされているファイルの種類

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

### <a name="supported-languages"></a>サポートされている言語

ドキュメント理解モデルでは、次の言語がサポートされています。
- フランス語
- ドイツ語
- イタリア語
- スペイン語


## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)

[抽出子を作成する](create-an-extractor.md)

[コンテンツ センターを作成する](create-a-content-center.md)

[フォーム処理モデルを作成する](create-a-form-processing-model.md)

[モデルを適用する](apply-a-model.md)   

[ドキュメント理解とフォーム処理モデルの違い](difference-between-document-understanding-and-form-processing-model.md)
  
[フォーム処理の概要](form-processing-overview.md)

[SharePoint Syntex アクセシビリティ モード](accessibility-mode.md)
