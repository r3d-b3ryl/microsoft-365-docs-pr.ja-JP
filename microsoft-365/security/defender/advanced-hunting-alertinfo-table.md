---
title: 高度なハンティング スキーマの AlertInfo テーブル
description: 高度なハンティング スキーマの AlertInfo テーブルでアラート生成イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, AlertInfo, アラート, 重大度, カテゴリ, MITRE, ATT&CK, Microsoft Defender for Endpoint,Microsoft Defender for Office 365、Microsoft Cloud App Security、MCAS、Microsoft Defender for Identity
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
ms.openlocfilehash: 0298b4f83ac748048215af4f5b1f8261a2a8c67c
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530789"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



`AlertInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびMicrosoft Defender for Identity。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `AlertId` | `string` | アラートの一意識別子 |
| `Title` | `string` | アラートのタイトル |
| `Category` | `string` | アラートで識別された脅威インジケーターまたは侵害アクティビティの種類 |
| `Severity` | `string` | アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。 |
| `ServiceSource` | `string` | アラート情報を提供した製品またはサービス |
| `DetectionSource` | `string` | 注目すべきコンポーネントまたはアクティビティを識別した検出テクノロジまたはセンサー |
| `AttackTechniques` | `string` | MITRE ATT&アラートをトリガーしたアクティビティに関連付けられた CK 手法 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
