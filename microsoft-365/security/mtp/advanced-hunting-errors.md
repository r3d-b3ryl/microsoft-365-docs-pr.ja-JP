---
title: Microsoft Threat Protection の高度な検索でエラーを処理する
description: 高度な検索を使用したときに表示されるエラーを理解する
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、timeout、resources、errors、不明なエラー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 939f235a5168766e1ab6982eb9fb554a749ad041
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413820"
---
# <a name="handle-advanced-hunting-errors"></a>詳細な検索エラーを処理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


高度な検索構文ミスを通知するエラーと、クエリが [定義済みの制限](advanced-hunting-limits.md)をヒットしたときに表示されるエラーを表示します。 エラーを解決または回避する方法に関するヒントについては、以下の表を参照してください。 

| エラーの種類 | 原因 | 解決策 | エラーメッセージの例 |
|--|--|--|--|
| 構文エラー | クエリに、存在しない演算子、列、関数、またはテーブルへの参照を含む、認識できない名前が含まれています。 | [Kusto 演算子と関数](https://docs.microsoft.com/azure/data-explorer/kusto/query/)への参照が正しいことを確認してください。 正しい高度な検索列、関数、およびテーブルの [スキーマ](advanced-hunting-schema-tables.md) を確認してください。 変数文字列は、引用符で囲まれ、認識されるようにしてください。 クエリの作成時に、IntelliSense からのオートコンプリート候補を使用します。 | `A recognition error occurred.` |
| セマンティックエラー | クエリで有効な演算子、列、関数、またはテーブル名が使用されていますが、構造にエラーがあり、結果として得られるロジックがあります。 場合によっては、高度な検索でエラーの原因となる特定の演算子が識別されます。 | クエリの構造にエラーがあるかどうかを確認します。 ガイダンスについては、 [Kusto ドキュメント](https://docs.microsoft.com/azure/data-explorer/kusto/query/) を参照してください。 クエリの作成時に、IntelliSense からのオートコンプリート候補を使用します。 |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| アウト | クエリは、タイムアウト [になるまで、限ら](advanced-hunting-limits.md)れた期間内でのみ実行できます。このエラーは、複雑なクエリを実行すると、より頻繁に発生することがあります。 | [クエリを最適化する](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| CPU 調整 | 同じテナント内のクエリは、テナントサイズに基づいて割り当てられた [CPU リソース](advanced-hunting-limits.md) を超過しました。 | サービスは、15分および毎日、CPU リソース使用率をチェックし、使用率が割り当てられた制限の10% を超えると警告を表示します。 100% の使用率に達した場合、サービスは次の毎日または15分のサイクルが終わるまでクエリをブロックします。 [CPU の制限のヒットを回避するためにクエリを最適化する](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| 結果のサイズ制限を超過しました  | クエリの結果セットの集計サイズが上限を超えています。 このエラーは、結果セットが大きすぎて、1万レコードの制限で切り捨てられても許容可能なサイズに減少しない場合に発生する可能性があります。 予測可能なコンテンツを持つ複数の列を持つ結果は、このエラーによって影響を受ける可能性が高くなります。 | [クエリを最適化する](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| 過剰なリソース消費 | クエリで大量のリソースが消費されており、完了を停止しています。 場合によっては、高度な検索は最適化されていない特定の演算子を識別します。 | [クエリを最適化する](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| 不明なエラー | 不明な理由によりクエリが失敗しました。 | クエリを再実行してみてください。 クエリを続行しても不明なエラーが返される場合は、ポータル経由で Microsoft に連絡してください。 | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>関連項目
- [高度な検索のベストプラクティス](advanced-hunting-best-practices.md)
- [サービスの制限](advanced-hunting-limits.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [Kusto クエリ言語の概要](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
