---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルのアラート生成イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、重大度、カテゴリ、MITRE、ATT&CK、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS、Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929972"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `AlertInfo` な検索スキーマ[](advanced-hunting-overview.md)の表には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

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
| `AttackTechniques` | string | MITRE ATT&アラートをトリガーしたアクティビティに関連付けられた CK の手法を使用します。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
