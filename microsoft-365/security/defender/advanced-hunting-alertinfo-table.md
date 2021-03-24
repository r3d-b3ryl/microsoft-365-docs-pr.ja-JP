---
title: 高度な検索スキーマの AlertInfo テーブル
description: 高度な検索スキーマの AlertInfo テーブルのアラート生成イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、重大度、カテゴリ、MITRE、ATT&CK、Microsoft Defender ATP、MDATP、Office 365 ATP、Microsoft Cloud App Security、MCAS、Azure ATP
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bc81c9c8406a6e70df6ec38e3896ef9977a120e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063604"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `AlertInfo` な検索スキーマ[](advanced-hunting-overview.md)の表には、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity のアラートに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

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
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
