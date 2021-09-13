---
title: 高度なハンティング スキーマの DeviceProcessEvents テーブル
description: 高度なハンティング スキーマの DeviceProcessEventstable でのプロセスの生成イベントまたは作成イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、processcreationevents、DeviceProcessEvents、process id、コマンドライン、DeviceProcessEvents
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
ms.openlocfilehash: b5e57fec83217c8df00d333bb4c71f375cac23bb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164719"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高度 `DeviceProcessEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、プロセスの作成と関連イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MD5` | 文字列型 | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileSize` | long | ファイルのサイズ (バイト単位) |
| `ProcessVersionInfoCompanyName` | string | 新しく作成されたプロセスのバージョン情報からの会社名 |
| `ProcessVersionInfoProductName` | string | 新しく作成されたプロセスのバージョン情報からの製品名 |
| `ProcessVersionInfoProductVersion` | string | 新しく作成されたプロセスのバージョン情報からの製品バージョン |
| `ProcessVersionInfoInternalFileName` | string | 新しく作成されたプロセスのバージョン情報からの内部ファイル名 |
| `ProcessVersionInfoOriginalFileName` | string | 新しく作成されたプロセスのバージョン情報からの元のファイル名 |
| `ProcessVersionInfoFileDescription` | 文字列 | 新しく作成されたプロセスのバージョン情報からの説明 |
| `ProcessId` | int | 新しく作成されたプロセスのプロセス ID (PID) |
| `ProcessCommandLine` | string | 新しいプロセスの作成に使用するコマンド ライン |
| `ProcessIntegrityLevel` | string | 新しく作成されたプロセスの整合性レベル。 Windows、ダウンロードしたインターネットから起動した場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる必要があります。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `ProcessTokenElevation` | string | 新しく作成されたプロセスに適用されるトークン昇格の種類を示します。 指定できる値: TokenElevationTypeLimited (制限あり)、TokenElevationTypeDefault (standard)、TokenElevationTypeFull (昇格) |
| `ProcessCreationTime` | 日付型 | プロセスが作成された日時 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountObjectId` | 文字列 | Azure アカウントのアカウントの一意AD |
| `LogonId` | string | ログオン セッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessAccountUpn` | string | イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN) |
| `InitiatingProcessAccountObjectId` | string | Azure ADを実行したユーザー アカウントのオブジェクト ID を指定します。 |
| `InitiatingProcessLogonId` | string | イベントを開始したプロセスのログオン セッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `InitiatingProcessIntegrityLevel` | 文字列 | イベントを開始したプロセスの整合性レベル。 Windows、インターネットダウンロードから起動した場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる必要があります。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `InitiatingProcessMD5` | 文字列型 | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessFileSize` | long | イベントの処理を実行したファイルのサイズ |
| `InitiatingProcessVersionInfoCompanyName` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの会社名 |
| `InitiatingProcessVersionInfoProductName` | 文字列 | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの製品名 |
| `InitiatingProcessVersionInfoProductVersion` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの製品バージョン |
| `InitiatingProcessVersionInfoInternalFileName` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの内部ファイル名 |
| `InitiatingProcessVersionInfoOriginalFileName` | 文字列 | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの元のファイル名 |
| `InitiatingProcessVersionInfoFileDescription` | 文字列 | イベントを担当するプロセス (イメージ ファイル) のバージョン情報の説明 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | 文字列 | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessSignerType` | string | イベントを開始したプロセス (イメージ ファイル) のファイル 署名者の種類 |
| `InitiatingProcessSignatureStatus` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の署名状態に関する情報 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | 文字列 | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |
| `AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
