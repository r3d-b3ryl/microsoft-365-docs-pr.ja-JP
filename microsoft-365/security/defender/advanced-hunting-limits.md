---
title: Defender の高度な検索クォータとMicrosoft 365パラメーター
description: 高度なハンティング サービスの応答性を維持するさまざまなクォータと使用状況パラメーター (サービス制限) を理解する
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果、クォータ、パラメーター、割り当て
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245602"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>高度な検索クォータと使用状況パラメーター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

サービスのパフォーマンスと応答性を維持するために、高度なハンティングによってさまざまなクォータと使用状況パラメーター ("サービス制限" とも呼ばれる) が設定されます。 これらのクォータとパラメーターは、手動で実行されるクエリと、カスタム検出ルールを使用して実行されるクエリに [個別に適用されます](custom-detection-rules.md)。 複数のクエリを定期的に実行する顧客は、これらの制限に気を付け、最適化のベスト プラクティスを [適用](advanced-hunting-best-practices.md) して中断を最小限に抑える必要があります。

既存のクォータと使用状況パラメーターを理解するには、次の表を参照してください。

| クォータまたはパラメーター | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去 30 日間までのデータを検索できます。 |
| 結果セット | 10,000 行 | すべてのクエリ | 各クエリは、最大 10,000 レコードを返します。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは最大 10 分間実行できます。 10 分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | 15 分ごと | ポータル [は、クエリが実行](advanced-hunting-errors.md) され、テナントが割り当てられたリソースの 10% 以上を消費するたびにエラーを表示します。 テナントが次の 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>API を介して実行される高度な検索クエリには、個別のクォータとパラメーターのセットが適用されます。 [高度な狩猟 API について読む](./api-advanced-hunting.md)

## <a name="related-topics"></a>関連項目

- [高度な狩猟のベスト プラクティス](advanced-hunting-best-practices.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)