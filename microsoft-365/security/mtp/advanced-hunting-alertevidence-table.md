---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルで生成される警告に関連付けられているファイル、ネットワークアドレス、ユーザー、またはデバイスの情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、alert、entities、エビデンス、file、IP address、デバイス、コンピューター、ユーザー、アカウント
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
ms.openlocfilehash: 1a58d1e5db2ea8689d4909e6e9c47b08a6e94d34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929241"
---
# <a name="alertevidence"></a>AlertEvidence

**適用対象:**
- Microsoft Threat Protection

`AlertEvidence` [高度な](advanced-hunting-overview.md)検索スキーマの表には、さまざまなエンティティ (ファイル、IP アドレス、url、ユーザー、またはデバイス) に関する情報が含まれています。この情報には、Microsoft Defender ATP、Office 365 ATP、microsoft Cloud App SECURITY、および Azure ATP からのアラートに関連付けられています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | string | アラートの一意識別子 |
| `EntityType` | string | オブジェクトの種類 (ファイル、プロセス、デバイス、ユーザーなど) |
| `EvidenceRole` | string | エンティティが通知に関与する方法。そのエンティティが影響を受けているか、または単に関連しているかを示します。 |
| `SHA1` | string | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列型 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドには通常、値が設定されていません。使用可能な場合は SHA1 列を使用します。 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteUrl` | string | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD でのアカウントの一意識別子 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `ThreatFamily` | string | 疑わしいまたは悪意のあるファイルまたはプロセスが分類されたマルウェアファミリ |
| `EvidenceDirection` | string | エンティティがネットワーク接続のソースまたは宛先であるかどうかを示します |
| `AdditionalFields` | string | JSON 配列形式でのイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
