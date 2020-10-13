---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルで通知に関連付けられている情報について説明します。
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7f6a4f7592e6a8fde0b7ae6269f07ce7f76a5730
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430165"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

`AlertEvidence`[高度な](advanced-hunting-overview.md)検索スキーマの表には、さまざまなエンティティ (ファイル、IP アドレス、url、ユーザー、またはデバイス) に関する情報が含まれています。この情報には、microsoft Defender ATP、Office 365 ATP、Microsoft Cloud App Security、および Azure ATP からのアラートに関連付けられています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | string | アラートの一意識別子 |
| `ServiceSource` | string | 通知情報を提供した製品またはサービス |
| `EntityType` | string | オブジェクトの種類 (ファイル、プロセス、デバイス、ユーザーなど) |
| `EvidenceRole` | string | エンティティが通知に関与する方法。そのエンティティが影響を受けているか、または単に関連しているかを示します。 |
| `EvidenceDirection` | string | エンティティがネットワーク接続のソースまたは宛先であるかどうかを示します |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダ |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドには通常、値が設定されていません。使用可能な場合は SHA1 列を使用します。 |
| `FileSize` | int | ファイルのサイズ (バイト数) |
| `ThreatFamily` | string | 疑わしいまたは悪意のあるファイルまたはプロセスが分類されたマルウェアファミリ |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure Active Directory のアカウントの一意識別子 |
| `DeviceId` | string | サービス内のデバイスの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `LocalIP` | string | 通信時に使用されるローカルデバイスに割り当てられた IP アドレス |
| `NetworkMessageId` | string | Office 365 により生成されたメールの一意の識別子 |
| `EmailSubject` | string | メールの件名 |
| `ApplicationId` | string | アプリケーションの一意識別子 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `ProcessCommandLine` | string | 新しいプロセスを作成するために使用されるコマンドライン |
| `AdditionalFields` | string | JSON 配列形式でのイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
