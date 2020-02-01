---
title: 高度な検索スキーマの DeviceFileEvents テーブル
description: 高度な検索スキーマの DeviceFileEvents テーブルにあるファイル関連イベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検出、microsoft の脅威の防止、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、filecreationevents、DeviceFileEvents、files、path、hash、sha1、sha256、md5
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
ms.openlocfilehash: 035efb5b2404708010f5fbfd4c419d59df088393
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600474"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

`DeviceFileEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、ファイルの作成、変更、およびその他のファイルシステムイベントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `FileName` | string | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列型 | 記録されたアクションが適用されたファイルを含むフォルダ |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 通常、このフィールドは入力されません。使用可能な場合は SHA1 列を使用します。 |
| `MD5` | string | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileOriginUrl` | string | ファイルのダウンロード元の URL |
| `FileOriginReferrerUrl` | string | ダウンロードしたファイルにリンクする web ページの URL |
| `FileOriginIP` | string | ファイルのダウンロード元の IP アドレス |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (画像ファイル) の SHA-1 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (画像ファイル) を含むフォルダー |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスを実行するために使用されるコマンドライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日付と時刻 |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。 これらの整合性レベルは、リソースへのアクセス許可に影響します。 |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子 |
| `SensitivityLabel` | string | 情報保護のためにメール、ファイル、その他のコンテンツに適用されるラベル |
| `SensitivitySubLabel` | string | Sublabel は、電子メール、ファイル、またはその他のコンテンツに適用され、情報保護のために分類します。機密サブラベルは、機密ラベルの下にグループ化されますが、個別に処理されます。 |
| `IsAzureInfoProtectionApplied` | boolean | ファイルが Azure Information Protection によって暗号化されているかどうかを示します |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
