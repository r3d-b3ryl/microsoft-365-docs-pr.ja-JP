---
title: ドキュメントの理解とフォーム処理モデルの違い
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: ドキュメント理解とフォーム処理モデルの主要な違いについて説明します。
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294750"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>ドキュメントの理解とフォーム処理モデルの違い 

この記事の内容は、Project Cortex のプライベートプレビュー用です。 [詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。

「Project Cortex」では、SharePoint ドキュメントライブラリにアップロードされたドキュメントを識別して分類し、各ファイルから関連情報を抽出することができます。  たとえば、ファイルが SharePoint ドキュメントライブラリにアップロードされると、注文 *書* として識別されたすべてのファイルがそのように分類され、カスタムのドキュメントライブラリビューに表示されます。 さらに、各ファイル ( *PO 番号* や *合計*など) から特定の情報を取得して、それをドキュメントライブラリビューの列として表示することができます。 

コンテンツを理解することで、必要な情報を特定して抽出するための *モデル* を作成できます。 使用できる2つのモデルの種類を次に示します。

- [ドキュメントのモデルについて](document-understanding-overview.md)
- [フォーム処理モデル](form-processing-overview.md)

両方のモデルは基本的に同じ目的で使用されていますが、以下に示す主要な相違点は、使用できるものによって異なります。

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>構造化コンテンツと非構造化コンテンツおよび半構造化されたコンテンツ

ドキュメントについてのモデルを使用して、文字や契約書などの非構造化ドキュメントからデータを特定して抽出します。抽出するテキストエンティティは、ドキュメントのセンテンスまたは特定の領域に格納します。 たとえば、構造化されていないドキュメントは、さまざまな方法で記述できる契約更新レターの場合があります。 しかし、テキスト文字列「サービスの開始日」の後に実際の日付が続く、各契約更新ドキュメントの本文に、一貫して情報が存在します。   

フォーム処理モデルを使用して、構造化または半構造化されたドキュメント (フォーム、請求書など) からファイルを識別し、データを抽出します。 これらのドキュメントには、明確なキーと値のペア (たとえば、 *Date: 10/1/2020*) * または table data を指定する必要があります。 例として、フォーム処理の候補として、 *名前*、 *電話番号*、 *総コスト*など、ドキュメントレイアウトの同じ領域にある特定のフィールドに関する情報をクライアントが提供する必要がある会社の注文要求フォームが挙げられます。 構造化されたドキュメントの例として、税フォームがあります。 

## <a name="where-they-are-created"></a>作成された場所

ドキュメントのモデルについては、SharePoint コンテンツセンターサイトで作成および管理します。 

> [!NOTE]
> ドキュメントを認識するモデルを作成したり、SharePoint ドキュメントライブラリに適用したりするには、コンテンツセンターサイトにアクセスできる必要があります。 

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。 ユーザーがフォーム処理モデルを作成できるようにするには、ドキュメントライブラリでフォーム処理モデルの作成が有効になっている必要があります。管理者は、これをコンテンツの管理設定について理解する必要があります。 フォーム処理モデルは、PowerAutomate フローを使用して、ファイルをドキュメントライブラリにアップロードするときに処理します。

ドキュメントを理解するには、SharePoint コンテンツタイプギャラリーに保存される新しい [sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) を作成します。 または、必要に応じて、既存のコンテンツタイプを使用してモデルを定義できます。

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。 ユーザーがフォーム処理モデルを作成するには、ドキュメントライブラリでフォーム処理モデルの作成が有効になっている必要があります。 または、管理者が管理設定について理解している必要があります。 フォーム処理モデルは、PowerAutomate フローを使用して、ファイルをドキュメントライブラリにアップロードするときに処理します。

フォーム処理モデルは、新しい [sharepoint コンテンツタイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)も作成し、Sharepoint コンテンツタイプギャラリーにも保存されます。

## <a name="where-they-can-be-applied"></a>適用可能な場所

アクセスできる SharePoint ドキュメントライブラリについてのドキュメントを適用することができます。 コンテンツセンターを使用して、ドキュメントを認識するモデルを作成し、それを別のドキュメントライブラリに適用します。 コンテンツセンターを使用すると、ドキュメント理解モデルをどのように使用しているか、また、どのように適用されるかを、より集中管理できます。 メモこの情報は、コンテンツセンターにもロールアップする必要があります。

現在、フォーム処理モデルは、それを作成した SharePoint ドキュメントライブラリにのみ適用できます。 これにより、サイトへのアクセス権を持つライセンスを持つユーザーは、フォーム処理モデルを作成できるようになります。

 ## <a name="see-also"></a>関連項目
[トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[分類子を作成する](create-a-classifier.md)</br>
[抽出器を作成する](create-an-extractor.md)</br>
[ドキュメントを適用するモデルを理解する](apply-a-model.md)</br>
[フォーム処理モデルを作成する](create-a-form-processing-model.md)</br>
