---
title: Microsoft の脅威保護での高度な検索の制限
description: 高度な検索サービスの応答性を維持するさまざまなサービス制限を理解する
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ、kusto、CPU 制限、クエリ制限、リソース、最大結果
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950951"
---
# <a name="advanced-hunting-service-limits"></a>高度な検索サービスの制限

**適用対象:**
- Microsoft Threat Protection

サービスのパフォーマンスと応答性を向上させるために、高度な検索は、クエリのさまざまな制限を手動で実行し、 [カスタムの検出ルール](custom-detection-rules.md)を設定します。 これらの制限事項については、次の表を参照してください。

| 極限 | Size | 更新サイクル | Description |
|--|--|--|--|
| データ範囲 | 30 日間 | すべてのクエリ | 各クエリは、過去30日間のデータを検索できます。 |
| 結果セット | 1万行 | すべてのクエリ | 各クエリは最大1万レコードを返すことができます。 |
| Timeout | 10 分 | すべてのクエリ | 各クエリは、最大10分間実行できます。 10分以内に完了しない場合、サービスはエラーを表示します。
| CPU リソース | テナントのサイズに基づく | -毎時、15分ごと<br>-毎日午前12時 | サービスによって、毎日および15分の制限が個別に適用されます。 各制限について、クエリが実行され、テナントが割り当てられたリソースの10% を超えた場合に、 [ポータルにエラーが表示され](advanced-hunting-errors.md) ます。 テナントが次の毎日または15分のサイクルの後に100% に達した場合、クエリはブロックされます。 |

>[!NOTE] 
>別の制限のセットは、API で実行される高度な検索クエリに適用されます。 [高度な検索 Api について確認する](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

複数のクエリを定期的に実行する場合は、使用量を追跡し、 [最適化のベストプラクティスを適用](advanced-hunting-best-practices.md) して、これらの制限を超えたことによる影響を最小限に抑えます。

## <a name="related-topics"></a>関連項目

- [高度な検索のベストプラクティス](advanced-hunting-best-practices.md)
- [詳細な検索エラーを処理する](advanced-hunting-errors.md)
- [高度な検出の概要](advanced-hunting-overview.md)
- [カスタム検出の概要](custom-detections-overview.md)
