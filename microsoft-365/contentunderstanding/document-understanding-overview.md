---
title: ドキュメント理解の概要
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint の同期に関するドキュメントの概要について説明します。
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294762"
---
# <a name="document-understanding-overview"></a>ドキュメント理解の概要


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

ドキュメントの概要は、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。 これは、文字や契約書などの非構造化ドキュメントに最適に機能します。 これらのドキュメントには、語句やパターンに基づいて識別できるテキストが含まれている必要があります。 識別されたテキストは、そのファイルの種類 (分類) と抽出するもの (抽出器) の両方を指定します。

ドキュメントのモデルについては、 *コンテンツセンター*と呼ばれる種類の SharePoint サイトで作成および管理されます。 SharePoint ドキュメントライブラリに適用されると、モデルには、抽出される情報を格納する列があるコンテンツタイプに関連付けられます。 作成したコンテンツタイプは、SharePoint コンテンツタイプギャラリーに格納されます。 既存のコンテンツタイプを使用してスキーマを使用することもできます。

*分類子*と抽出器をドキュメントに追加する次の操作を実行するモデルについて*説明します*。 

- 分類子は、ドキュメントライブラリにアップロードされたドキュメントを識別して分類するために使用されます。 たとえば、分類子は、ライブラリにアップロードされたすべての *契約更新* ドキュメントを識別するために、"トレーニング済み" にすることができます。 契約更新コンテンツタイプは、分類子を作成するときに定義されます。

- これらのドキュメントからの抽出情報を抽出します。 たとえば、ドキュメントライブラリで特定されたすべての契約書の更新ドキュメントについては、ビューに列が表示されます。このドキュメントには、 *サービスの開始日* と  *クライアント* も表示されます。 

サンプルファイルを使用すると、モデルで分類子と抽出器をトレーニングし、テストすることができます。 サンプルファイルには、ファイルのデータを特定して抽出しようとしたときに検索する内容のモデル例が記載されています。 たとえば、会社で作業している契約更新文書のサンプルを使用して、契約の更新分類子と抽出器をトレーニングします。 サンプルファイルを使用して、モデルの有効性をテストすることもできます。

モデルを公開した後、コンテンツセンターを使用して、アクセスできる任意の SharePoint ドキュメントライブラリに適用します。  


## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[コンテンツセンター](create-a-content-center.md) 
 を作成する[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>
[モデルを適用する](apply-a-model.md)   
[ドキュメントの理解とフォーム処理モデルの違い](difference-between-document-understanding-and-form-processing-model.md)  
[フォーム処理の概要](form-processing-overview.md)
