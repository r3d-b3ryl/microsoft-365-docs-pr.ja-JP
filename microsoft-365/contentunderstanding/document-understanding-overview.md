---
title: ドキュメント理解の概要 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex におけるドキュメントの理解の概要について説明します。
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537402"
---
# <a name="document-understanding-overview-preview"></a>ドキュメント理解の概要 (プレビュー)
> [!Note] 
> Project Cortex は現在プレビュー段階です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

ドキュメントの概要 AI モデルを使用して、ファイルの分類と情報の抽出を自動化します。 これは、文字や契約書などの非構造化ドキュメントに最適です。 ドキュメントには、語句またはパターンに基づいて識別できるテキストが含まれている必要があります。 識別されたテキストでは、ファイルの種類 (分類) と抽出するもの (抽出器) の両方を指定できます。

ドキュメントのモデルについては、コンテンツセンターと呼ばれる種類の SharePoint サイトで作成および管理されます。 SharePoint ドキュメントライブラリに適用されると、モデルは、抽出された情報を格納する列を持つコンテンツタイプに関連付けられます。 作成したコンテンツタイプは、SharePoint コンテンツタイプギャラリーに格納されます。 スキーマを使用するために、既存のコンテンツタイプを使用するように選択することもできます。

*分類子**と抽出器をドキュメント*に追加するには、次の操作を実行するモデルを理解します。 

- 分類子は、ドキュメントライブラリにアップロードされたドキュメントを識別して分類するために使用されます。 たとえば、分類子は、ライブラリにアップロードされたすべての*契約更新*ドキュメントを識別するために、"トレーニング済み" にすることができます。 契約更新コンテンツタイプは、分類子を作成するときに定義されます。

- これらのドキュメントからの抽出情報を抽出します。 たとえば、ドキュメントライブラリで特定されたすべての契約書更新ドキュメントに対して、列がビューに表示され、各契約更新ドキュメントの*サービス開始日*と*クライアント*も表示されます。 

サンプルファイルを使用して、モデルで分類子と抽出器をトレーニングおよびテストします。 ファイルの例は、ファイルのデータを特定して抽出しようとしたときにどのような意味があるかをモデルの例で示しています。 たとえば、会社で作業している契約更新ドキュメントの例を使用して、契約の更新分類子と抽出器をトレーニングします。 また、サンプルファイルを使用して、モデルの有効性をテストすることもできます。

モデルを公開した後、コンテンツセンターを使用して、アクセスできる任意の SharePoint ドキュメントライブラリに適用します。  


## <a name="see-also"></a>関連項目
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[コンテンツセンター](create-a-content-center.md) 
 を作成する[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>
[モデルを適用する](apply-a-model.md)   
[ドキュメントの理解とフォーム処理モデルの違い](difference-between-document-understanding-and-form-processing-model.md)  
[フォーム処理の概要](form-processing-overview.md)




