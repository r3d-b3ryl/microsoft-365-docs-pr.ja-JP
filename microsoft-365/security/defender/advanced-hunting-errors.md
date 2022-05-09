---
title: Microsoft 365 Defenderの高度な捜索でエラーを処理する
description: 高度なハンティングを使用するときに表示されるエラーを理解する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ, kusto, タイムアウト, リソース, エラー, 不明なエラー, 制限, クォータ, パラメーター, 割り当て
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8bd7d4b5191ff88fe2bd958c87e930b91f64dd5e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703635"
---
# <a name="handle-advanced-hunting-errors"></a>高度なハンティング エラーを処理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


高度な検索では、構文の間違いを通知するエラーが表示され、クエリが [定義済みのクォータと使用パラメーターに](advanced-hunting-limits.md)達するたびに表示されます。 エラーを解決または回避する方法のヒントについては、次の表を参照してください。

| エラーの種類 | 原因 | 解決策 | エラー メッセージの例 |
|--|--|--|--|
| 構文エラー | クエリには、存在しない演算子、列、関数、またはテーブルへの参照を含む、認識できない名前が含まれます。 | [Kusto演算子と関数](/azure/data-explorer/kusto/query/)への参照が正しいことを確認します。 正しい高度なハンティング列、関数、およびテーブルがないか [スキーマ](advanced-hunting-schema-tables.md) を確認します。 変数文字列が認識されるように、変数文字列を引用符で囲みます。 クエリを記述する場合は、IntelliSense からの自動入力候補を使用します。 | `A recognition error occurred.` |
| セマンティック エラー | クエリは有効な演算子、列、関数、またはテーブル名を使用していますが、その構造と結果のロジックにエラーがあります。 場合によっては、高度な追求で、エラーの原因となる特定の演算子が識別されることがあります。 | クエリの構造のエラーを確認します。 ガイダンスについては、[Kustoドキュメント](/azure/data-explorer/kusto/query/)を参照してください。 クエリを記述する場合は、IntelliSense からの自動入力候補を使用します。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| タイムアウト | クエリは、 [タイムアウトするまでの限られた期間内](advanced-hunting-limits.md)にのみ実行できます。このエラーは、複雑なクエリを実行するときに、より頻繁に発生する可能性があります。 | [クエリの最適化](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU の調整 | 同じテナント内のクエリが、テナント サイズに基づいて割り当てられた [CPU リソース](advanced-hunting-limits.md) を超えています。 | このサービスは、15 分ごとと毎日、CPU リソース使用率をチェックし、割り当てられたクォータの 10% を超えた使用状況に達したら警告を表示します。 使用率が 100% に達すると、サービスは次の 1 日、または 15 分のサイクルの後までクエリをブロックします。 [CPU クォータに達しないようにクエリを最適化する](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 結果のサイズ制限を超えた  | クエリの結果セットの集計サイズが最大サイズを超えました。 このエラーは、結果セットが大き過ぎるので、10,000 レコードの制限での切り捨てを行っても許容できるサイズに減らできない場合に発生する可能性があります。 大きなコンテンツを含む複数の列を含む結果は、このエラーの影響を受ける可能性が高くなります。 | [クエリの最適化](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| リソースの過剰な消費 | クエリで過剰な量のリソースが消費され、完了が停止されました。 高度な追求では、最適化が行えなかった特定の演算子が識別される場合があります。 | [クエリの最適化](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 不明なエラー | 不明な理由でクエリが失敗しました。 | クエリをもう一度実行してみてください。クエリが不明なエラーを引き続き返す場合は、ポータルから Microsoft にお問い合わせください。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>関連項目
- [高度なハンティングのベスト プラクティス](advanced-hunting-best-practices.md)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Kusto 照会言語の概要](/azure/data-explorer/kusto/query/)