---
title: レビュー セットからドキュメントをエクスポートする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: b6f467f938ce14aacb9553b11d51dc63431ab409
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862077"
---
# <a name="export-documents-from-a-review-set"></a>レビュー セットからドキュメントをエクスポートする

次のいずれかの方法で、プレゼンテーションまたは外部レビューのコンテンツをレビューセットからエクスポートできます。

- [ドキュメントのダウンロード](#download-documents-from-a-review-set)
 
- [ドキュメントのエクスポート](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a>校閲セットからドキュメントをダウンロードする

ダウンロードは、ネイティブ形式のレビューセットからコンテンツをダウンロードする簡単な方法を提供します。 ブラウザーのデータ転送機能を利用して、ダウンロードが完了するとブラウザーのプロンプトが表示されるようになります。 このメソッドを使用してダウンロードしたファイルは、コンテナーファイルに圧縮され、アイテムレベルのファイルになります。 これは、添付ファイルを選択すると、添付ファイルが含まれている電子メールを自動的に受信することを意味します。 同様に、word 文書に埋め込まれた excel スプレッドシートを選択すると、excel スプレッドシートが埋め込まれた word 文書が表示されます。 ダウンロードされたアイテムは、ファイルプロパティとして表示できる最終変更日を保持します。

レビューセットからコンテンツをダウンロードするには、ダウンロードするファイルを選択してから、[操作] メニューの [ダウンロード] を選択します。

![コンピューターの説明のスクリーンショットが自動的に生成される](media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a>レビュー セットからドキュメントをエクスポートする

[エクスポートすると、ユーザーはダウンロードパッケージに含まれるコンテンツをカスタマイズできます。 構成ページには、次の設定が用意されています。

### <a name="metadata-file"></a>メタデータファイル

これは、エクスポートするファイルに関連付けられたメタデータを含む "load file" と考えることができます。 メタデータファイルで使用できるエクスポートフィールドの一覧については、「 [Advanced 電子情報開示のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。 このファイルは、通常、サードパーティ製のツールによって取り込まれたできます。

### <a name="tag-data"></a>タグデータ

このコンテンツは、メタデータファイルのフィールドとして追加されます。 これには、校閲セットに適用されるすべてのタグ情報が含まれています。

### <a name="text-files"></a>テキスト ファイル

レビューセットからエクスポートされたファイルごとに、テキストファイルを生成できます。 これらのファイルは、多くの場合、サービスパートナーが取り込むデータの一部としてサードパーティ製ツールに必要とする場合があります。

### <a name="redacted-files"></a>がファイル

レビュー中にが PDF ファイルが生成された場合、これらのファイルはエクスポート中に利用できます。 ネイティブファイルのみをエクスポートするか、または校正を必要とするネイティブファイルを、実際の redactions を含む PDF ファイルに置き換えるかを決定できます。

### <a name="export-location"></a>エクスポート場所

エクスポートされたコンテンツは、Microsoft が提供する Azure blob またはお客様の blob のいずれかに配信されます。詳細については、export で提供されている場合があります。

### <a name="export-structure"></a>エクスポート構造

コンテンツが校閲セットからエクスポートされると、コンテンツは次のように構成されます。

  - ルートフォルダー–ダウンロード ID
    
      - Load\_\_ファイル .csv = メタデータファイルのエクスポート
    
      - Summary.txt = エクスポート統計情報を含む要約ファイル
    
      - 入力\_ファイルまた\_はネイティブファイル = すべてのネイティブファイルが含まれています。
    
      - エラー\_ファイル = エクスポートに含まれているエラーファイルが含まれています。
        
          - ExtractionError –親ファイルから正しく抽出されなかったファイルの利用可能なメタデータを含む csv。
        
          - ProcessingError-処理エラーがあるコンテンツ。 このコンテンツはアイテムレベルを意味する。添付ファイルに処理エラーが発生した場合、添付ファイルを含む電子メールはこのフォルダーに含まれます。
    
      - 抽出\_さ\_れたテキストファイル = 処理時に生成されたすべての抽出済みテキストファイルが含まれています。