---
title: 高度な検索でエラーを処理Microsoft 365 Defender
description: 高度な検索を使用する場合に表示されるエラーを理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ、kusto、タイムアウト、リソース、エラー、不明なエラー、制限、クォータ、パラメーター、割り当て
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 32d50103c6476a89f24568edeea75a206e37e227
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211924"
---
# <a name="handle-advanced-hunting-errors"></a>高度なハンティング エラーの処理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


高度な検索では、構文の間違いを通知するエラーと、クエリが定義済みのクォータと使用状況パラメーターに達するたびに [エラーが表示されます](advanced-hunting-limits.md)。 エラーを解決または回避する方法のヒントについては、以下の表を参照してください。

| エラーの種類 | 原因 | 解決策 | エラー メッセージの例 |
|--|--|--|--|
| 構文エラー | クエリには、存在しない演算子、列、関数、またはテーブルへの参照を含む、認識できない名前が含まれます。 | [Kusto 演算子と関数への参照が正しいか](/azure/data-explorer/kusto/query/)確認します。 スキーマ [で、適切](advanced-hunting-schema-tables.md) な高度な検索列、関数、およびテーブルを確認します。 変数文字列を引用符で囲み、認識します。 クエリを記述する場合は、IntelliSense からの自動入力候補を使用します。 | `A recognition error occurred.` |
| セマンティック エラー | クエリは有効な演算子、列、関数、またはテーブル名を使用していますが、その構造と結果のロジックにエラーがあります。 場合によっては、高度な追求で、エラーの原因となる特定の演算子が識別されることがあります。 | クエリの構造のエラーを確認します。 ガイダンスについては [、Kusto のドキュメント](/azure/data-explorer/kusto/query/) を参照してください。 クエリを記述する場合は、IntelliSense からの自動入力候補を使用します。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| タイムアウト | クエリは、限られた期間内 [にしか実行されず、タイミングアウトが発生します](advanced-hunting-limits.md)。このエラーは、複雑なクエリを実行するときにより頻繁に発生する可能性があります。 | [クエリの最適化](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU の調整 | 同じテナント内のクエリが、テナントのサイズに基づいて割り当てられた [CPU](advanced-hunting-limits.md) リソースを超えました。 | このサービスは、15 分ごとと毎日、CPU リソース使用率をチェックし、割り当てられたクォータの 10% を超えた使用状況に達したら警告を表示します。 使用率が 100% に達すると、サービスは次の 1 日、または 15 分のサイクルの後までクエリをブロックします。 [CPU クォータに達しないようにクエリを最適化する](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 結果のサイズ制限を超えた  | クエリの結果セットの集計サイズが最大サイズを超えました。 このエラーは、結果セットが大き過ぎるので、10,000 レコードの制限での切り捨てを行っても許容できるサイズに減らできない場合に発生する可能性があります。 大きなコンテンツを含む複数の列を含む結果は、このエラーの影響を受ける可能性が高くなります。 | [クエリの最適化](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| リソースの過剰な消費 | クエリで過剰な量のリソースが消費され、完了が停止されました。 高度な追求では、最適化が行えなかった特定の演算子が識別される場合があります。 | [クエリの最適化](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 不明なエラー | 不明な理由でクエリが失敗しました。 | もう一度クエリを実行してください。 クエリが不明なエラーを引き続き返す場合は、ポータルから Microsoft にお問い合わせください。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`



## <a name="related-topics"></a>関連項目
- [高度な狩猟のベスト プラクティス](advanced-hunting-best-practices.md)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Kusto クエリ言語の概要](/azure/data-explorer/kusto/query/)