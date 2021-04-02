---
title: Microsoft 365 Defender の高度な検索クォータと使用状況パラメーター
description: 高度なハンティング サービスの応答性を維持するさまざまなクォータと使用状況パラメーター (サービス制限) を理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
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
ms.openlocfilehash: ca79abfa95feb65f98ec32ae8dbc0093e34d58e6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498429"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高度な検索クォータと使用状況パラメーター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

サービスのパフォーマンスと応答性を維持するために、高度なハンティングによってさまざまなクォータと使用状況パラメーター ("サービス制限" とも呼ばれる) が設定されます。 これらのクォータとパラメーターは、手動で、およびカスタム検出ルールによって実行 [されるクエリに適用されます](custom-detection-rules.md)。 複数のクエリを定期的に実行しているお客様は、消費を追跡し、中断を最小限に抑えるために最適化のベスト [プラクティス](advanced-hunting-best-practices.md) を適用する必要があります。

既存のクォータと使用状況パラメーターを理解するには、次の表を参照してください。

| クォータまたはパラメーター | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去 30 日間までのデータを検索できます。 |
| 結果セット | 10,000 行 | すべてのクエリ | 各クエリは、最大 10,000 レコードを返します。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは最大 10 分間実行できます。 10 分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | - 1 時間に 15 分ごとに<br>- 毎日午前 12 時 | サービスは、日次クォータと 15 分のクォータを個別に適用します。 クォータごとに [、クエリが](advanced-hunting-errors.md) 実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに、ポータルにエラーが表示されます。 テナントが次の 1 日または 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>API を介して実行される高度な検索クエリには、個別のクォータとパラメーターのセットが適用されます。 [高度な狩猟 API について読む](./api-advanced-hunting.md)

## <a name="related-topics"></a>関連項目

- [高度な狩猟のベスト プラクティス](advanced-hunting-best-practices.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)