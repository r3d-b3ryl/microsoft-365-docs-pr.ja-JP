---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルのアラート生成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、列、データ型、説明、AlertInfo、アラート、重大度、カテゴリ、MITRE、ATT&CK、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、MCAS、Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211983"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `AlertInfo` な検索スキーマの[表](advanced-hunting-overview.md)には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | string | アラートの一意識別子 |
| `Title` | 文字列 | アラートのタイトル |
| `Category` | 文字列 | アラートで識別された脅威インジケーターまたは侵害アクティビティの種類 |
| `Severity` | 文字列 | アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。 |
| `ServiceSource` | 文字列 | アラート情報を提供した製品またはサービス |
| `DetectionSource` | string | 重要なコンポーネントまたはアクティビティを識別した検出テクノロジまたはセンサー |
| `AttackTechniques` | string | MITRE ATT&をトリガーしたアクティビティに関連付けられた CK テクニックを使用します。 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
