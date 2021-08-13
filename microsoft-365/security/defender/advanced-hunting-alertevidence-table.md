---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルのアラートに関連付けられている情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント
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
ms.openlocfilehash: eb5358e3751ab10fcad0f4a162fc3e43c0dba61427f710632732893413b6ea7e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53833353"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な検索スキーマの表には `AlertEvidence` 、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、および Microsoft Defender for Identity からのアラートに関連付けられたさまざまなエンティティ (ファイル[](advanced-hunting-overview.md)、IP アドレス、URL、ユーザー、またはデバイス) に関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | string | アラートの一意識別子 |
| `ServiceSource` | string | アラート情報を提供した製品またはサービス |
| `EntityType` | string | ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類 |
| `EvidenceRole` | string | エンティティがアラートに関与する方法 (影響を受け取ったのか、単に関連付けなのかを示す) |
| `EvidenceDirection` | string | エンティティがネットワーク接続の送信元か宛先かを示します。 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは、通常は入力されません。使用可能な場合は SHA1 列を使用します。 |
| `FileSize` | 整数 | ファイルのサイズ (バイト単位) |
| `ThreatFamily` | string | 疑わしいファイルまたは悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリは、 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | アカウントの一意の識別子は、Azure Active Directory |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `LocalIP` | string | 通信中に使用されるローカル デバイスに割り当てられた IP アドレス |
| `NetworkMessageId` | string | Office 365 により生成されたメールの一意の識別子 |
| `EmailSubject` | string | メールの件名 |
| `ApplicationId` | string | アプリケーションの一意の識別子 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `ProcessCommandLine` | string | 新しいプロセスの作成に使用するコマンド ライン |
| `AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |
| `RegistryKey` |string | 記録されたアクションが適用されたレジストリ キー |
| `RegistryValueName` |string | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` |string | 記録されたアクションが適用されたレジストリ値のデータ |

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
