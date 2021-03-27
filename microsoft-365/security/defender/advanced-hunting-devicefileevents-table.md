---
title: 高度な検索スキーマの DeviceFileEvents テーブル
description: 高度なハンティング スキーマの DeviceFileEvents テーブルのファイル関連イベントについて説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、filecreationevents、DeviceFileEvents、ファイル、パス、ハッシュ、sha1、sha256、md5
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 62989eca2fd00757ea02d03bf24a0049135d97b0
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382867"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `DeviceFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ファイルの作成、変更、その他のファイル システム イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | コンピューターの一意識別子 |
| `DeviceName` | 文字列 | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MD5` | 文字列型 | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileOriginUrl` | 文字列 | ファイルがダウンロードされた URL |
| `FileOriginReferrerUrl` | 文字列 | ダウンロードしたファイルにリンクする Web ページの URL |
| `FileOriginIP` | 文字列 | ファイルがダウンロードされた IP アドレス |
| `PreviousFolderPath` | 文字列 | 記録されたアクションが適用される前のファイルを含む元のフォルダー |
| `PreviousFileName` | 文字列 | アクションの結果として名前が変更されたファイルの元の名前 |
| `FileSize` | long | ファイルのサイズ (バイト単位) |
| `InitiatingProcessAccountDomain` | 文字列 | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | 文字列 | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | 文字列 | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessAccountUpn` | 文字列 | イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN) |
| `InitiatingProcessAccountObjectId` | 文字列 | Azure ADを実行したユーザー アカウントのオブジェクト ID を指定します。 |
| `InitiatingProcessMD5` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessSHA1` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `InitiatingProcessFolderPath` | 文字列型 | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessFileName` | 文字列 | イベントを開始したプロセスの名前 |
| `InitiatingProcessFileSize` | long | イベントを開始したプロセス (イメージ ファイル) のサイズ |
| `InitiatingProcessVersionInfoCompanyName` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの会社名 |
| `InitiatingProcessVersionInfoProductName` | 文字列 | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの製品名 |
|` InitiatingProcessVersionInfoProductVersion` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの製品バージョン |
|` InitiatingProcessVersionInfoInternalFileName` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの内部ファイル名 |
| `InitiatingProcessVersionInfoOriginalFileName` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの元のファイル名 |
| `InitiatingProcessVersionInfoFileDescription` | 文字列 | イベントを担当するプロセス (イメージ ファイル) のバージョン情報の説明 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | 文字列 | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessIntegrityLevel` | 文字列 | イベントを開始したプロセスの整合性レベル。 Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | 文字列 | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | 文字列 | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `RequestProtocol` | 文字列 | ネットワーク プロトコル (該当する場合) を使用してアクティビティを開始します。不明、ローカル、SMB、または NFS |
| `RequestSourceIP` | 文字列 | アクティビティを開始したリモート デバイスの IPv4 または IPv6 アドレス |
| `RequestSourcePort` | 文字列 | アクティビティを開始したリモート デバイスの送信元ポート |
| `RequestAccountName` | 文字列 | アクティビティをリモートで開始するために使用されるアカウントのユーザー名 |
| `RequestAccountDomain` | 文字列 | アクティビティをリモートで開始するために使用されるアカウントのドメイン |
| `RequestAccountSid` | 文字列 | アクティビティをリモートで開始するために使用されるアカウントのセキュリティ識別子 (SID) |
| `ShareName` | 文字列 | ファイルを含む共有フォルダーの名前 |
| `InitiatingProcessFileSize` | long | イベントの処理を実行したファイルのサイズ |
| `SensitivityLabel` | 文字列 | 電子メール、ファイル、または他のコンテンツに適用されるラベルを情報保護のために分類する |
| `SensitivitySubLabel` | 文字列 | 電子メール、ファイル、または他のコンテンツに適用されるサブラベルを、情報保護のために分類します。感度サブラベルは、感度ラベルの下でグループ化されますが、個別に処理されます。 |
| `IsAzureInfoProtectionApplied` | boolean | ファイルが Azure Information Protection によって暗号化されているかどうかを示します。 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | 文字列 | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関する追加情報 |
>[!NOTE]
> ファイル ハッシュ情報は、利用可能なときに常に表示されます。 ただし、SHA1、SHA256、または MD5 を計算できない理由はいくつか考えられる。 たとえば、ファイルがリモート ストレージに置かれているか、別のプロセスによってロックされている、圧縮されている、または仮想としてマークされている可能性があります。 これらのシナリオでは、ファイル ハッシュ情報は空に表示されます。

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
