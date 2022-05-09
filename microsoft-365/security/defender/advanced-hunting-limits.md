---
title: Microsoft 365 Defenderの高度なハンティング クォータと使用状況パラメーター
description: 高度なハンティング サービスの応答性を維持するさまざまなクォータと使用状況パラメーター (サービス制限) について理解する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ, kusto, CPU 制限, クエリ制限, リソース, 最大結果, クォータ, パラメーター, 割り当て
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
ms.openlocfilehash: fe0ad42ac0ebfc7f6816e412ab6ffb0ac9291b44
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643171"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高度なハンティング クォータと使用パラメーター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

サービスのパフォーマンスと応答性を維持するために、高度なハンティングでは、さまざまなクォータと使用パラメーター ("サービス制限" とも呼ばれます) を設定します。 これらのクォータとパラメーターは、手動で実行されるクエリと [、カスタム検出ルール](custom-detection-rules.md)を使用して実行されるクエリに個別に適用されます。 複数のクエリを定期的に実行する顧客は、これらの制限に留意し、中断を最小限に抑えるために [最適化のベスト プラクティスを適用](advanced-hunting-best-practices.md) する必要があります。

既存のクォータと使用状況パラメーターについては、次の表を参照してください。

| クォータまたはパラメーター | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去 30 日間までのデータを検索できます。 |
| 結果セット | 10,000 行 | すべてのクエリ | 各クエリは、最大 10,000 レコードを返すことができます。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは最大 10 分間実行できます。 10 分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | 15 分ごと | ポータルには、クエリが実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに [エラーが表示](advanced-hunting-errors.md) されます。 テナントが 100% に達した場合、次の 15 分のサイクル終了までクエリはブロックされます。 |

>[!NOTE] 
>API を使用して実行される高度なハンティング クエリには、別のクォータとパラメーターのセットが適用されます。 [高度なハンティング API について読む](./api-advanced-hunting.md)

## <a name="related-topics"></a>関連項目

- [高度なハンティングのベスト プラクティス](advanced-hunting-best-practices.md)
- [高度なハンティング エラーを処理する](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)