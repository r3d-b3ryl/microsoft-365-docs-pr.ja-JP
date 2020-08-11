---
title: ドキュメントの理解とフォーム処理モデルの相違点 (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: ドキュメント理解とフォーム処理モデルの主要な違いについて説明します。
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612740"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a>ドキュメントの理解とフォーム処理モデルの相違点 (プレビュー)

> [!Note] 
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

「Project Cortex」では、SharePoint ドキュメントライブラリにアップロードされたドキュメントを識別して分類し、各ファイルから関連情報を抽出することができます。  たとえば、ファイルが SharePoint ドキュメントライブラリにアップロードされると、注文*書*として識別されたすべてのファイルは、そのように分類され、表示されるカスタムのドキュメントライブラリビューに表示されます。 さらに、各ファイル ( *PO 番号*や*合計*など) から特定の情報を取得し、ドキュメントライブラリビューの列に表示することができます。 


コンテンツを理解することで、必要な情報を特定して抽出するための*モデル*を作成できます。  使用できるモデルには、次の2種類があります。

- [ドキュメントのモデルについて](document-understanding-overview.md)
- [フォーム処理モデル](form-processing-overview.md)

両方のモデルは一般的に同じ目的で使用されていますが、どちらを使用するかに影響する主な違いがあります。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>構造化コンテンツと非構造化コンテンツおよび半構造化されたコンテンツ

ドキュメントについてのモデルを使用して、文字や契約書などの非構造化ドキュメントからデータを特定して抽出します。抽出するテキストエンティティは、ドキュメントのセンテンスまたは特定の領域に格納します。 たとえば、構造化されていないドキュメントは、さまざまな方法で記述できる契約更新レターの場合があります。 ただし、各契約更新文書の本文に一貫した情報があります。たとえば、テキスト文字列「サービスの開始日」の後に実際の日付が続きます。   

フォーム処理モデルを使用して、ファイルを特定し、構造化または半構造化されたドキュメント (たとえば、*日付: 10/1/2020*) * またはテーブルデータなど、キーと値のペアが明確であるフォームや請求書からデータを抽出します。 例として、フォーム処理の候補として、*名前*、*電話番号*、*総コスト*など、ドキュメントレイアウトの同じ領域にある特定のフィールドについて、クライアントが情報を提供する必要がある会社の注文要求フォームが挙げられます。 構造化されたドキュメントの例として、税フォームがあります。 

## <a name="where-they-are-created"></a>作成された場所

ドキュメントのモデルについては、SharePoint コンテンツセンターサイトで作成および管理します。 ドキュメントを認識するモデルを作成したり、SharePoint ドキュメントライブラリに適用したりするには、コンテンツセンターサイトにアクセスできる必要があります。 

ドキュメントを理解するには、SharePoint コンテンツタイプギャラリーに保存される新しい[sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。 必要に応じて、既存のコンテンツタイプを使用してモデルを定義することもできます。

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。 ユーザーがフォーム処理モデルを作成できるようにするには、ドキュメントライブラリでフォーム処理モデルの作成が有効になっている必要があります。管理者は、これをコンテンツの管理設定について理解する必要があります。 フォーム処理モデルは、PowerAutomate フローを使用して、ファイルをドキュメントライブラリにアップロードするときに処理します。

フォーム処理モデルでも、sharepoint コンテンツタイプギャラリーに格納されている新しい[sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。

## <a name="where-they-can-be-applied"></a>適用可能な場所

ドキュメントのモデルについては、アクセスできるさまざまな SharePoint ドキュメントライブラリに適用できます。 コンテンツセンターを使用して、ドキュメントを理解するだけでなく、別のドキュメントライブラリに適用することもできます。 コンテンツセンターでは、コンテンツセンターにロールアップする必要があるので、ドキュメントを理解するモデルをどのように使用し、どのように適用するかについて、より集中管理できます。

現在、フォーム処理モデルは、作成元の SharePoint ドキュメントライブラリにのみ適用できます。 これにより、サイトにアクセスできる任意のライセンスユーザーがフォーム処理モデルを作成できるようになります。




 ## <a name="see-also"></a>関連項目
[トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[ドキュメントを適用するモデルを理解する](apply-a-model.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>



  
  



