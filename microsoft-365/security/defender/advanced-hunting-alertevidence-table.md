---
title: 高度な検索スキーマの AlertEvidence テーブル
description: 高度な検索スキーマの AlertEvidence テーブルのアラートに関連付けられている情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント
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
ms.openlocfilehash: 7b1f581e1cfc8345df6e7b8053621cf46110c355
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499890"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な検索スキーマの表には `AlertEvidence` 、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security、Microsoft Defender for Identity からのアラートに関連付けられたさまざまなエンティティ (ファイル、IP アドレス、URL、[](advanced-hunting-overview.md)ユーザー、またはデバイス) に関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `AlertId` | 文字列 | アラートの一意識別子 |
| `ServiceSource` | 文字列 | アラート情報を提供した製品またはサービス |
| `EntityType` | 文字列 | ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類 |
| `EvidenceRole` | 文字列 | エンティティがアラートに関与する方法 (影響を受け取ったのか、単に関連付けなのかを示す) |
| `EvidenceDirection` | 文字列 | エンティティがネットワーク接続の送信元か宛先かを示します。 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは、通常は入力されません。使用可能な場合は SHA1 列を使用します。 |
| `FileSize` | int | ファイルのサイズ (バイト単位) |
| `ThreatFamily` | 文字列 | 疑わしいファイルまたは悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリは、 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `AccountSid` | 文字列 | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | 文字列 | Azure Active Directory のアカウントの一意識別子 |
| `AccountUpn` | 文字列 | アカウントのユーザー プリンシパル名 (UPN) |
| `DeviceId` | 文字列 | サービス内のデバイスの一意の識別子 |
| `DeviceName` | 文字列 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `LocalIP` | 文字列 | 通信中に使用されるローカル デバイスに割り当てられた IP アドレス |
| `NetworkMessageId` | string | Office 365 により生成されたメールの一意の識別子 |
| `EmailSubject` | string | メールの件名 |
| `ApplicationId` | string | アプリケーションの一意の識別子 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `ProcessCommandLine` | 文字列 | 新しいプロセスの作成に使用するコマンド ライン |
| `AdditionalFields` | 文字列 | JSON 配列形式のイベントに関する追加情報 |
| `RegistryKey` |文字列 | 記録されたアクションが適用されたレジストリ キー |
| `RegistryValueName` |文字列 | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` |文字列 | 記録されたアクションが適用されたレジストリ値のデータ |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
