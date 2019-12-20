---
title: 高度な捜索スキーマの EmailUrlInfo テーブル
description: 高度な捜索スキーマの EmailUrlInfo テーブルで URL またはリンクの情報について学習する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、EmailUrlInfo、ネットワーク メッセージ ID、URL、リンク
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
ms.openlocfilehash: da9712d1f3465c28d2ba880997a52434723a297d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808672"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[高度な捜索](advanced-hunting-overview.md)スキーマの `EmailUrlInfo` テーブルには、Office 365 ATP によって処理されるメールおよび添付ファイルの URL に関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `UrlId` | 文字列型 | メールの件名、本文、または添付ファイル内の URL の一意の識別子 |
| `NetworkMessageId` | 文字列型 | Office 365 により生成されたメールの一意の識別子 |
| `Url` | 文字列型 | メールの件名、本文、または添付ファイル内の完全な URL |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)