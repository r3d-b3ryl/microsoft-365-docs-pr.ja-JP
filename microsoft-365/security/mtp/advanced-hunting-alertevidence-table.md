---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルで生成される警告に関連付けられているファイル、ネットワークアドレス、ユーザー、またはデバイスの情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、alert、entities、エビデンス、file、IP address、device、machine、user、account
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
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649513"
---
# <a name="alertevidence"></a>AlertEvidence

**適用対象:**
- Microsoft Threat Protection

`AlertEvidence`[高度な](advanced-hunting-overview.md)検索スキーマの表には、さまざまなエンティティ (ファイル、IP アドレス、url、ユーザー、またはデバイス) に関する情報が含まれています。この情報には、microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのアラートに関連付けられています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | string | アラートの一意識別子 |
| `EntityType` | string | オブジェクトの種類 (ファイル、プロセス、デバイス、ユーザーなど) |
| `EvidenceRole` | string | エンティティが通知に関与する方法。そのエンティティが影響を受けているか、または単に関連しているかを示します。 |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD でのアカウントの一意識別子 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `ThreatFamily` | string | 疑わしいまたは悪意のあるファイルまたはプロセスが分類されたマルウェアファミリ |
| `EvidenceDirection` | string | エンティティがネットワーク接続のソースまたは宛先であるかどうかを示します |
| `AdditionalFields` | string | JSON 配列形式でのイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、および id の間でのハント](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
