---
title: 高度な検索スキーマの AlertEvents テーブル
description: 高度な検索スキーマの AlertEvents テーブル内のアラート発生イベントについて
keywords: 高度な検索、脅威ハンティング、サイバー脅威ハンティング、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、alertevents、アラート、重要度、カテゴリ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911333"
---
# <a name="alertevents"></a>AlertEvents

**適用対象:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

[高度な検索](advanced-hunting-overview.md) スキーマの `AlertEvents` テーブルには、Microsoft Defender ATP アラートに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な検索スキーマのその他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `AlertId` | string | アラートの一意識別子 |
| `EventTime` | datetime | イベントが記録された日付と時刻 |
| `MachineId` | 文字列 | コンピューターの一意識別子 |
| `ComputerName` | 文字列 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `Severity` | 文字列 | アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。 |
| `Category` | 文字列 | アラートで識別された脅威インジケーターまたは侵害アクティビティの種類 |
| `Title` | 文字列 | アラートのタイトル |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを特定するには、この列を ComputerName 列と EventTime 列と共に使用する必要があります。 |
| `Table` | 文字列 | イベントの詳細を含むテーブル |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を検索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使う](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を検索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
