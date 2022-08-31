---
title: 高度なハンティング スキーマの AlertEvidence テーブル
description: 高度なハンティング スキーマの AlertEvidence テーブルで、アラートに関連付けられている情報について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, AlertInfo, アラート, エンティティ, 証拠, ファイル, IP アドレス, デバイス, マシン, ユーザー, アカウント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 3e1e0dcbf88063dd4338b48e6bb2fe3dd2e87e64
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482849"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`AlertEvidence` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびからのアラートに関連付けられたさまざまなエンティティ (ファイル、IP アドレス、URL、ユーザー、またはデバイス) に関する情報が含まれています。Microsoft Defender for Identity。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `AlertId` | `string` | アラートの一意識別子 |
| `ServiceSource` | `string` | アラート情報を提供した製品またはサービス |
| `EntityType` | `string` | ファイル、プロセス、デバイス、ユーザーなどのオブジェクトの種類 |
| `EvidenceRole` | `string` | エンティティがアラートに関与する方法。影響を受けるか、単に関連しているだけかを示します |
| `EvidenceDirection` | `string` | エンティティがネットワーク接続の送信元か宛先かを示します。 |
| `FileName` | `string` | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | `string` | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | `string` | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | `string` | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常設定されません。使用可能な場合は SHA1 列を使用します。 |
| `FileSize` | `int` | ファイルのサイズ (バイト単位) |
| `ThreatFamily` | `string` | 疑わしい、または悪意のあるファイルまたはプロセスが分類されたマルウェア ファミリ |
| `RemoteIP` | `string` | に接続されていた IP アドレス |
| `RemoteUrl` | `string` | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | `string` | Azure Active Directory のアカウントの一意識別子 |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `DeviceId` | `string` | サービス内のデバイスの一意の識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `LocalIP` | `string` | 通信中に使用されるローカル デバイスに割り当てられた IP アドレス |
| `NetworkMessageId` | `string` | Office 365 により生成されたメールの一意の識別子 |
| `EmailSubject` | `string` | メールの件名 |
| `ApplicationId` | `string` | アプリケーションの一意の識別子 |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `ProcessCommandLine` | `string` | 新しいプロセスの作成に使用されるコマンド ライン |
| `AdditionalFields` | `string` | JSON 配列形式のイベントに関する追加情報 |
| `RegistryKey` |`string` | 記録されたアクションが適用されたレジストリ キー |
| `RegistryValueName` |`string` | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` |`string` | 記録されたアクションが適用されたレジストリ値のデータ |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
