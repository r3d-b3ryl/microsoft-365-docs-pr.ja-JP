---
title: Microsoft 365 Defender の高度な検索でエラーを処理する
description: 高度な検索を使用するときに表示されるエラーを理解する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ、kusto、タイムアウト、リソース、エラー、不明なエラー、制限、クォータ、パラメーター、割り当て
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929648"
---
# <a name="handle-advanced-hunting-errors"></a>高度なハンティング エラーの処理

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


高度な検索では、構文の間違いや、クエリが定義済みのクォータと使用パラメーターにヒットするたびに通知する [エラーが表示されます](advanced-hunting-limits.md)。 エラーを解決または回避する方法のヒントについては、次の表を参照してください。

| エラーの種類 | 原因 | 解決策 | エラー メッセージの例 |
|--|--|--|--|
| 構文エラー | クエリには、存在しない演算子、列、関数、またはテーブルへの参照など、認識できない名前が含まれます。 | [Kusto 演算子と関数への参照が正しいか](https://docs.microsoft.com/azure/data-explorer/kusto/query/)確認します。 スキーマ [で、適切](advanced-hunting-schema-tables.md) な高度なハンティング列、関数、およびテーブルを確認します。 変数文字列を二重引用符で囲み、認識します。 クエリを記述する場合は、クエリのオートコンプリート候補を使用IntelliSense。 | `A recognition error occurred.` |
| セマンティック エラー | クエリは有効な演算子、列、関数、またはテーブル名を使用しますが、その構造と結果のロジックにエラーがあります。 場合によっては、高度な検索によって、エラーの原因を引き起こした特定の演算子が識別されます。 | クエリの構造のエラーを確認します。 ガイダンスについては [、Kusto のドキュメント](https://docs.microsoft.com/azure/data-explorer/kusto/query/) を参照してください。 クエリを記述する場合は、クエリのオートコンプリート候補を使用IntelliSense。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| タイムアウト | クエリは、タイム アウトする前 [に限られた時間内にのみ実行できます](advanced-hunting-limits.md)。このエラーは、複雑なクエリを実行するときに発生する頻度が高い可能性があります。 | [クエリを最適化する](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 調整 | 同じテナント内のクエリが、テナントのサイズに基づいて割り当てられた [CPU](advanced-hunting-limits.md) リソースを超えました。 | このサービスは、15 分ごとに 1 日ごとに CPU リソース使用量をチェックし、割り当てられたクォータの 10% を超える使用率を超えた後に警告を表示します。 使用率が 100% に達すると、サービスは次の 1 日または 15 分のサイクルの後までクエリをブロックします。 [CPU クォータに達しないようにクエリを最適化する](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 結果のサイズ制限を超えました  | クエリの結果セットの集計サイズが最大サイズを超えました。 このエラーは、結果セットが非常に大きいので、10,000 レコードの制限で切り捨てられても許容できるサイズに減らすことができない場合に発生する可能性があります。 コンテンツの大きな大きな列が複数含まれる結果は、このエラーの影響を受け可能性が高い。 | [クエリを最適化する](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| リソースの過剰消費 | クエリが大量のリソースを消費し、完了を停止しています。 場合によっては、高度な検索によって、最適化されたのではない特定の演算子が識別される場合があります。 | [クエリを最適化する](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 不明なエラー | 不明な理由のためにクエリが失敗しました。 | クエリを再度実行してみてください。 クエリが不明なエラーを引き続き返す場合は、ポータルから Microsoft にお問い合わせください。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>関連項目
- [高度な検索のベスト プラクティス](advanced-hunting-best-practices.md)
- [クォータと使用パラメータ](advanced-hunting-limits.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Kusto クエリ言語の概要](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
