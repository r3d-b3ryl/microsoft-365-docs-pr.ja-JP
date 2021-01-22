---
title: Microsoft 365 Defender の高度な検索クォータと使用パラメーター
description: 高度な検索サービスの応答性を維持するさまざまなクォータと使用パラメーター (サービス制限) を理解する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
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
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929792"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高度な検索クォータと使用パラメーター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

サービスのパフォーマンスと応答性を維持するために、高度な検索では、さまざまなクォータと使用パラメーター ("サービス制限" とも呼ばれる) が設定されます。 これらのクォータとパラメーターは、クエリが手動で実行され、カスタム検出ルール [によって実行される場合に適用されます](custom-detection-rules.md)。 複数のクエリを定期的に実行する顧客は、[](advanced-hunting-best-practices.md)消費を追跡し、最適化のベスト プラクティスを適用して、中断を最小限に抑える必要があります。

既存のクォータと使用パラメーターを理解するには、次の表を参照してください。

| クォータまたはパラメーター | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、最大 30 日間のデータを検索できます。 |
| 結果セット | 10,000 行 | すべてのクエリ | 各クエリは最大 10,000 レコードを返します。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは最大 10 分間実行できます。 10 分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントサイズに基づく | - 1 時間後 15 分ごとに<br>- 毎日午前 0 時 12 分 | サービスは、日次クォータと 15 分のクォータを個別に適用します。 クォータごとに、クエリが[](advanced-hunting-errors.md)実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに、ポータルにエラーが表示されます。 テナントが 1 日または 15 分のサイクル後まで 100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>別のクォータとパラメーターのセットは、API を介して実行される高度な検索クエリに適用されます。 [高度なハンティング API について読む](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>関連項目

- [高度な検索のベスト プラクティス](advanced-hunting-best-practices.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)