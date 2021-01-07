---
title: 高度な検索スキーマの DeviceFileEvents テーブル
description: 高度な検索スキーマの DeviceFileEvents テーブルのファイル関連イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、filecreationevents、DeviceFileEvents、ファイル、パス、ハッシュ、sha1、sha256、md5
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
ms.openlocfilehash: 9b48321693f883e40a100e29e5e1ec3c5203caa2
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771861"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `DeviceFileEvents` な検索スキーマ [の表には](advanced-hunting-overview.md) 、ファイルの作成、変更、その他のファイル システム イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MD5` | 文字列型 | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileOriginUrl` | string | ファイルのダウンロード先の URL |
| `FileOriginReferrerUrl` | string | ダウンロードしたファイルにリンクする Web ページの URL |
| `FileOriginIP` | string | ファイルのダウンロード先の IP アドレス |
| `InitiatingProcessAccountDomain` | string | イベントを処理するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを処理するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを処理するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `InitiatingProcessFolderPath` | 文字列型 | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネット ダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響します。 |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権の昇格の有無を示すトークンの種類 |
| `InitiatingProcessParentId` | int | イベントを処理するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `RequestProtocol` | string | ネットワーク プロトコル (該当する場合) は、不明、ローカル、SMB、または NFS のアクティビティを開始するために使用されます。 |
| `ShareName` | string | ファイルを含む共有フォルダーの名前 |
| `RequestSourceIP` | string | アクティビティを開始したリモート デバイスの IPv4 または IPv6 アドレス |
| `RequestSourcePort` | string | アクティビティを開始したリモート デバイス上の送信元ポート |
| `RequestAccountName` | string | リモートでアクティビティを開始するために使用されるアカウントのユーザー名 |
| `RequestAccountDomain` | string | リモートでアクティビティを開始するために使用されるアカウントのドメイン |
| `RequestAccountSid` | string | リモートでアクティビティを開始するために使用されるアカウントのセキュリティ識別子 (SID) |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | ブラウザーの動作を分離するために Application Guard によって使用される仮想化コンテナーの識別子 |
| `SensitivityLabel` | string | 電子メール、ファイル、その他のコンテンツに適用されたラベルを情報保護のために分類する |
| `SensitivitySubLabel` | string | 電子メール、ファイル、その他のコンテンツに適用されるサブラベル。情報保護のために分類されます。sensitivity サブラベルは、区別ラベルの下にグループ化されますが、個別に処理されます。 |
| `IsAzureInfoProtectionApplied` | ブール値 | ファイルが Azure Information Protection によって暗号化されているかどうかを示します |

>[!NOTE]
> ファイル ハッシュ情報は、利用可能な場合は常に表示されます。 ただし、SHA1、SHA256、または MD5 を計算できない理由はいくつか考えられる。 たとえば、ファイルがリモート ストレージに置かれているか、別のプロセスによってロックされている、圧縮されている、または仮想としてマークされている可能性があります。 これらのシナリオでは、ファイル ハッシュ情報は空のように表示されます。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
