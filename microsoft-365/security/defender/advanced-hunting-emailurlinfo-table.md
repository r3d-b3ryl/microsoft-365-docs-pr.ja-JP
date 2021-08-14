---
title: 高度な捜索スキーマの EmailUrlInfo テーブル
description: 高度な捜索スキーマの EmailUrlInfo テーブルで URL またはリンクの情報について学習する
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、EmailUrlInfo、ネットワーク メッセージ ID、URL、リンク
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
ms.openlocfilehash: d57de219daca5fd8a6eb3762014496262f7f0b6409b5ae5c4f222808afcb48d6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53810848"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `EmailUrlInfo` な検索スキーマの[表](advanced-hunting-overview.md)には、Microsoft Defender によって処理された電子メールと添付ファイルの URL に関する情報が含Office 365。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。 

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `NetworkMessageId` | string | ユーザーが生成する電子メールの一意Microsoft 365 |
| `Url` | 文字列型 | メールの件名、本文、または添付ファイル内の完全な URL |
| `UrlDomain` | string | URL のドメイン名またはホスト名 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
