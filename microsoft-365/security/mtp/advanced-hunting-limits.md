---
title: Microsoft 365 Defender の高度な検索クォータと使用法のパラメーター
description: 高度な検索サービスの応答性を維持するさまざまなクォータおよび使用法のパラメーター (サービス制限) について理解します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847370"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高度な検索クォータと使用法のパラメーター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

サービスのパフォーマンスと応答性を向上させるために、高度な検索はさまざまなクォータと使用状況パラメーター ("サービス制限" とも呼ばれます) を設定します。 これらのクォータとパラメーターは、手動で実行されるクエリ、および [カスタムの検出ルール](custom-detection-rules.md)に適用されます。 複数のクエリを定期的に実行する場合は、使用量を追跡し、 [最適化のベストプラクティスを適用](advanced-hunting-best-practices.md) して、中断を最小限に抑える必要があります。

既存のクォータと使用法のパラメーターについては、次の表を参照してください。

| Quota または parameter | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去30日間のデータを検索できます。 |
| 結果セット | 1万行 | すべてのクエリ | 各クエリは最大1万レコードを返すことができます。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは、最大10分間実行できます。 10分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | -毎時、15分ごと<br>-毎日午前12時 | サービスは、毎日および15分のクォータを個別に適用します。 クォータごとに、クエリが実行され、テナントが割り当てられたリソースの10% 以上を消費した場合は常に [エラーが表示され](advanced-hunting-errors.md) ます。 テナントが次の毎日または15分のサイクルの後に100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>クォータとパラメーターの別のセットは、API を通じて実行される高度な検索クエリに適用されます。 [高度な検索 Api について確認する](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>関連項目

- [高度な検索のベストプラクティス](advanced-hunting-best-practices.md)
- [詳細な検索エラーを処理する](advanced-hunting-errors.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)