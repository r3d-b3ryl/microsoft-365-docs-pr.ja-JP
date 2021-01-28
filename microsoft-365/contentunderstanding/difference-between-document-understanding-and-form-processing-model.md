---
title: ドキュメント理解とフォーム処理モデルの違い
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
description: ドキュメント理解とフォーム処理モデルの主な違いについて説明します
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975879"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>ドキュメント理解とフォーム処理モデルの違い 


Microsoft SharePoint Syntex のコンテンツを理解すると、SharePoint ドキュメントライブラリにアップロードされたドキュメントを識別および分類し、各ファイルから関連情報を抽出できます。  たとえば、ファイルが SharePoint ドキュメントライブラリにアップロードされると、*発注書* として識別されたすべてのファイルがそのように分類され、カスタム ドキュメント ライブラリ ビューに表示されます。 さらに、各ファイルから特定の情報 (*PO番号* や *合計* など) を取得して、ドキュメントライブラリビューの列として表示できます。 

コンテンツの理解により、必要な情報を特定して抽出するための *モデル* を作成できます。 モデルは、検索、ビジネスプロセス、コンプライアンス、およびその他の多くのビジネス問題の解決を支援する上で価値があります。

使用できるモデルタイプは次の 2 つです。

- [ドキュメント理解モデル](document-understanding-overview.md)
- [フォーム処理モデル](form-processing-overview.md)

どちらのモデルも一般的に同じ目的で使用されますが、以下に示す主な違いは、どちらを使用できるかに影響します。

> [!NOTE]
> フォーム処理とドキュメント理解シナリオの例の詳細については、「[SharePoint Syntex の導入: 概要](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example)」を参照してください。


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>構造化コンテンツと非構造化コンテンツおよび半構造化コンテンツ

ドキュメント理解モデルを使用して、文字や契約書などの非構造化ドキュメントからデータを識別して抽出します。抽出するテキスト エンティティは、ドキュメントの文または特定の領域にあります。 たとえば、非構造化ドキュメントは、さまざまな方法で記述できる契約更新レターである可能性があります。 ただし、情報は各契約更新ドキュメントの本文に一貫して存在します。たとえば、*サービス開始日の* テキスト文字列の後に実際の日付が続きます。

フォーム処理モデルを使用してファイルを識別し、フォームや請求書などの構造化または半構造化されたドキュメントからデータを抽出します。 フォーム処理モデルは、サンプル ドキュメントからフォームのレイアウトを理解し、似ている場所から抽出する必要のあるデータを探すようにトレーニングされています。 フォームは通常、エンティティが同じ場所に配置されている、より構造化されたレイアウトを持っています (たとえば、納税申告での社会保障番号など)。

> [!NOTE]
> ドキュメント理解モデルを作成したり、SharePoint ドキュメントライブラリに適用したりするには、コンテンツ センター サイトへのアクセスが必要です。 


## <a name="where-models-are-created"></a>モデルが作成された場所

ドキュメント理解モデルは、SharePoint コンテンツ センター サイトで作成および管理されます。 

> [!NOTE]
> 入力ドキュメントの詳細については、[フォーム処理モデルの要件と制限](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)を参照してください。 

フォーム処理モデルは PowerApps [AI ビルダー](https://docs.microsoft.com/ai-builder/overview)で作成されますが、作成は SharePoint ドキュメント ライブラリから直接開始されます。 ドキュメント ライブラリでは、ユーザーがそのドキュメントのためにフォーム処理モデルを作成する前に、フォーム処理モデルの作成を有効にしておく必要があります。 管理者は、コンテンツの理解の管理設定でフォーム処理モデルの作成を有効にできます。 フォーム処理モデルは、ファイルがドキュメント ライブラリにアップロードされるときに、PowerAutomate フローを使用してファイルを処理します。

ドキュメント理解モデルを作成するときは、SharePoint コンテンツタイプギャラリーに保存される新しい [SharePoint コンテンツ タイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)を作成します。 または、必要に応じて、既存のコンテンツタイプを使用してモデルを定義できます。

フォーム処理モデルは、新しい [SharePoint コンテンツ タイプ](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)も作成し、SharePoint コンテンツ タイプ ギャラリーにも保存されます。

## <a name="where-they-can-be-applied"></a>適用可能な場所

アクセスできる SharePoint ドキュメント ライブラリにドキュメント理解モデルを適用できます。 コンテンツ センターを使用してドキュメント理解モデルを作成し、それをさまざまなドキュメント ライブラリに適用できます。 コンテンツ センターでは、ドキュメント理解モデルの使用方法と適用できる場所をより集中的に制御できます。 この情報はコンテンツセンターにもロールアップする必要があります。

現在、フォーム処理モデルは、モデルを作成した SharePoint ドキュメント ライブラリにのみ適用できます。 これにより、サイトにアクセスできるライセンス付与済みのユーザーは、フォーム処理モデルを作成できるようになります。 管理者は、SharePoint ドキュメントライブラリでフォーム処理を有効にして、ライセンス付与済みのユーザーが使用できるようにする必要があります。

 ## <a name="see-also"></a>関連項目
[トレーニング: AI ビルダーを使用してビジネスの実績を高める](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[ドキュメントの理解の概要](document-understanding-overview.md)

[フォーム処理の概要](form-processing-overview.md)

[SharePoint Syntex の概要](index.md)
