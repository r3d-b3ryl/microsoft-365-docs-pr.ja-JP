---
title: Microsoft Defender ATP の高度な狩猟制限
description: 高度なハンティング サービスの応答性を維持するさまざまなサービス制限を理解する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp、検索、クエリ、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499535"
---
# <a name="advanced-hunting-service-limits"></a>高度なハンティング サービスの制限

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

サービスのパフォーマンスと応答性を維持するために、高度な検索では、クエリを手動で、カスタム検出ルールによって実行するためのさまざまな [制限を設定します](custom-detection-rules.md)。 これらの制限を理解するには、次の表を参照してください。

| 制限 | Size | 更新サイクル | 説明 |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去 30 日間までのデータを検索できます。 |
| 結果セット | 10,000 行 | すべてのクエリ | 各クエリは、最大 10,000 レコードを返します。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは最大 10 分間実行できます。 10 分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | - 1 時間に 15 分ごとに<br>- 毎日午前 12 時 | サービスは、日次制限と 15 分の制限を個別に適用します。 制限ごとに [、クエリが](advanced-hunting-errors.md) 実行され、テナントが割り当てられたリソースの 10% 以上を消費するたびに、ポータルにエラーが表示されます。 テナントが次の 1 日または 15 分のサイクルの後まで 100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>API を介して実行される高度な検索クエリには、個別の制限セットが適用されます。 [高度な狩猟 API について読む](run-advanced-query-api.md)

複数のクエリを定期的に実行しているお客様は[](advanced-hunting-best-practices.md)、消費を追跡し、最適化のベスト プラクティスを適用して、これらの制限を超えた結果の中断を最小限に抑える必要があります。

## <a name="related-topics"></a>関連項目

- [高度な狩猟のベスト プラクティス](advanced-hunting-best-practices.md)
- [高度なハンティング エラーの処理](advanced-hunting-errors.md)
- [高度な追求の概要](advanced-hunting-overview.md)
- [カスタム検出ルール](custom-detection-rules.md)
