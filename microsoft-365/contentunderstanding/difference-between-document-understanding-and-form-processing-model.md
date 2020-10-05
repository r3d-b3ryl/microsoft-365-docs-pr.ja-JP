---
title: ドキュメント理解とフォーム処理モデルの違い
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: ドキュメント理解とフォーム処理モデルの主な違いについて説明します
ms.openlocfilehash: c5d60753e84cb55dc088b79f90fe841b50da1836
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338598"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>ドキュメント理解とフォーム処理モデルの違い 


Microsoft SharePoint Syntex のコンテンツを理解すると、SharePoint ドキュメントライブラリにアップロードされたドキュメントを識別および分類したり、各ファイルから関連情報を抽出したりできます。  たとえば、ファイルが SharePoint ドキュメントライブラリにアップロードされると、*発注書*として識別されたすべてのファイルがそのように分類され、カスタム ドキュメント ライブラリ ビューに表示されます。 さらに、各ファイルから特定の情報 (*PO番号*や*合計*など) を取得して、ドキュメントライブラリビューの列として表示できます。 

コンテンツの理解により、必要な情報を特定して抽出するための*モデル*を作成できます。 モデルは、検索、ビジネスプロセス、コンプライアンス、およびその他の多くのビジネス問題の解決を支援する上で価値があります。

使用できるモデルタイプは次の 2 つです。

- [ドキュメント理解モデル](document-understanding-overview.md)
- [フォーム処理モデル](form-processing-overview.md)

どちらのモデルも一般的に同じ目的で使用されますが、以下に示す主な違いは、どちらを使用できるかに影響します。

> [!NOTE]
> フォーム処理とドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)」を参照してください。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>構造化コンテンツと非構造化コンテンツおよび半構造化コンテンツ

ドキュメント理解モデルを使用して、文字や契約書などの非構造化ドキュメントからデータを識別して抽出します。抽出するテキスト エンティティは、ドキュメントの文または特定の領域にあります。 たとえば、非構造化ドキュメントは、さまざまな方法で記述できる契約更新レターである可能性があります。 ただし、情報は各契約更新ドキュメントの本文に一貫して存在します。たとえば、*サービス開始日の*テキスト文字列の後に実際の日付が続きます。   

フォーム処理モデルを使用してファイルを識別し、フォームや請求書などの構造化または半構造化されたドキュメントからデータを抽出します。 フォームは、エンティティが同じ場所にあるより構造化されたレイアウトを持っているため、フォーム処理モデルは、サンプル ドキュメントからフォームのレイアウトを理解し、同様の場所から抽出する必要のあるデータ (たとえば、 税務フォームの社会保障番号) を探すようにトレーニングされています。 

> [!NOTE]
> ドキュメント理解モデルを作成したり、SharePoint ドキュメントライブラリに適用したりするには、コンテンツ センター サイトへのアクセスが必要です。 


## <a name="where-they-are-created"></a>それらが作成された場所

ドキュメント理解モデルは、SharePoint コンテンツ センター サイトで作成および管理されます。 

> [!NOTE]
> 入力ドキュメントの詳細については、[フォーム処理モデルの要件と制限](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)を参照してください。 

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。 ユーザーがフォーム処理モデルを作成するには、ドキュメント ライブラリでフォーム処理モデルの作成を有効にする必要があります。管理者は、コンテンツ理解管理者設定で有効にできます。 フォーム処理モデルは、ファイルがドキュメントライブラリにアップロードされるときに、PowerAutomate フローを使用してファイルを処理します。

ドキュメント理解モデルを作成するときは、SharePoint コンテンツタイプギャラリーに保存される新しい [SharePoint コンテンツ タイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。 または、必要に応じて、既存のコンテンツタイプを使用してモデルを定義できます。

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメントライブラリから直接開始されます。 ユーザーがフォーム処理モデルを作成するには、ドキュメント ライブラリでフォーム処理モデルの作成を有効にする必要があります。 または、管理者は、管理者設定理解のコンテンツでこれを行うことができます。 フォーム処理モデルは、ファイルがドキュメントライブラリにアップロードされるときに、PowerAutomate フローを使用してファイルを処理します。

フォーム処理モデルは、新しい [SharePoint コンテンツ タイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)も作成し、SharePoint コンテンツ タイプ ギャラリーにも保存されます。

## <a name="where-they-can-be-applied"></a>適用可能な場所

アクセスできる SharePoint ドキュメント ライブラリにドキュメント理解モデルを適用できます。 コンテンツ センターを使用してドキュメント理解モデルを作成し、それをさまざまなドキュメント ライブラリに適用できます。 コンテンツセンターでは、ドキュメント理解モデルの使用方法と適用できる場所をより集中的に制御できます。 この情報はコンテンツセンターにもロールアップする必要があります。

現在、フォーム処理モデルは、モデルを作成した SharePoint ドキュメント ライブラリにのみ適用できます。 これにより、サイトにアクセスできるライセンス ユーザーは、フォーム処理モデルを作成できます。 管理者は、SharePoint ドキュメントライブラリでフォーム処理を有効にして、ライセンスユーザーが使用できるようにする必要があります。

 ## <a name="see-also"></a>関連項目
[トレーニング: AI ビルダーを使用してビジネスの実績を高める](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[ドキュメントの理解の概要](document-understanding-overview.md)

[フォーム処理の概要](form-processing-overview.md)

[SharePoint Syntex の概要](index.md)
