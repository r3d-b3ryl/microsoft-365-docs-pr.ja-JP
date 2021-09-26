---
title: SharePoint Syntex ドキュメント理解モデル REST API
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: SharePoint Syntex ドキュメント理解モデル REST API の概要。
ms.openlocfilehash: b77e882163810a389e734f63b45418a4e682dd88
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775686"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>SharePoint Syntex ドキュメント理解モデル REST API

SharePoint REST インターフェイスを使用して、ドキュメント理解モデルの作成、1 つ以上のライブラリへのモデルの適用または削除、モデルに関する情報の取得または更新を行うことができます。 

SharePoint Online (および SharePoint 2016 以降のオンプレミス) REST サービスでは、OData $batch クエリ オプションを使って、サービスに対する複数の要求を 1 つの呼び出しに統合できます。 

詳細とコード サンプルへのリンクについては、[「REST API によりバッチ要求を発行する」](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)を参照してください。

## <a name="prerequisites"></a>前提条件

作業の開始前に、次に示す事項について十分に理解しておいてください。

- [SharePoint REST サービスの概要](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [SharePoint REST エンドポイントを使用して基本的な操作を完了する](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST コマンド

Syntex ドキュメント理解モデルを操作するには、次の REST コマンドを使用できます。

- [モデルの作成](rest-createmodel-method.md) – モデルとそれに関連付けられたコンテンツ タイプを作成します。
- [GetByUniqueId](rest-getbyuniqueid-method.md) – SharePoint Syntex ドキュメント理解モデルに関する情報を取得または更新します。
- [GetByTitle](rest-getbytitle-method.md) – モデル タイトルを使用して SharePoint Syntex ドキュメント理解モデルに関する情報を取得または更新します。
- [モデルの適用](rest-applymodel-method.md) –トレーニング済みのドキュメント理解モデルを 1 つ以上のライブラリに適用 (または同期) します。
- [モデルとライブラリの情報を取得](rest-getmodelandlibraryinfo.md) – モデルと、それが適用されているライブラリに関する情報を取得します。
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – SharePoint Syntex ドキュメント理解モデルの使用可能なモデル設定 (関連する保持ラベルとモデルの説明) を更新します。
- [BatchDelete](rest-batchdelete-method.md) – 適用されたドキュメント理解モデルを 1 つ以上のライブラリから削除します。
- [ファイル分類要求の作成](rest-createclassificationrequest.md) – 適用されたモデルを使用して、指定したファイルを分類する要求を作成します。
- [フォルダー分類要求の作成](rest-createclassificationrequest.md) – 適用されたモデルを使用して、フォルダー全体を分類する要求を作成します。

## <a name="scenarios"></a>シナリオ

メソッドの名前からは直感的に理解できないような、次に示すシナリオ例にご注意ください。 詳細については、各手順を参照してください。

[モデル作成] メソッドは、モデル オブジェクトとそれに関連付けられたコンテンツ タイプのみを作成します。 ライブラリに適用する前に、まずコンテンツ センターでモデルをトレーニングする必要があります。

[モデル適用] メソッドを使用して、ドキュメントを分類し、必要に応じて追加情報を抽出するようにターゲット ライブラリのモデルを構成します。 この API では、モデルを複数のライブラリにバッチ適用することもできます。

[モデル削除] メソッドは、以前に適用された 1 つ以上のライブラリからモデルを削除するだけです。 モデルを削除する場合は、まず、モデルが適用されたすべてのライブラリから削除する必要があります。


## <a name="see-also"></a>関連項目

[ドキュメント理解の概要](../document-understanding-overview.md)

