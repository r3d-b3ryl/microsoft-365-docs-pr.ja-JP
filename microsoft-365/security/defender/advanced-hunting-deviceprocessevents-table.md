---
title: 高度なハンティング スキーマの DeviceProcessEvents テーブル
description: 高度なハンティング スキーマの DeviceProcessEventstable で、プロセスの生成イベントまたは作成イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, processcreationevents, DeviceProcessEvents, プロセス ID, コマンド ライン, DeviceProcessEvents
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
ms.openlocfilehash: 5f250c18a8bacb728143ada220a09525f4f1f6b1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67476838"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



`DeviceProcessEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、プロセスの作成と関連イベントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType` 値) の詳細については、Defender for Cloud で使用できる組み込みのスキーマ参照を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `DeviceId` | `string` | コンピューターの一意識別子 |
| `DeviceName` | `string` | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください |
| `FileName` | `string` | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | `string` | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | `string` | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | `string` | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `MD5` | `string` | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileSize` | `long` | ファイルのサイズ (バイト単位) |
| `ProcessVersionInfoCompanyName` | `string` | 新しく作成されたプロセスのバージョン情報からの会社名 |
| `ProcessVersionInfoProductName` | `string` | 新しく作成されたプロセスのバージョン情報からの製品名 |
| `ProcessVersionInfoProductVersion` | `string` | 新しく作成されたプロセスのバージョン情報からの製品バージョン |
| `ProcessVersionInfoInternalFileName` | `string` | 新しく作成されたプロセスのバージョン情報からの内部ファイル名 |
| `ProcessVersionInfoOriginalFileName` | `string` | 新しく作成されたプロセスのバージョン情報からの元のファイル名 |
| `ProcessVersionInfoFileDescription` | `string` | 新しく作成されたプロセスのバージョン情報からの説明 |
| `ProcessId` | `int` | 新しく作成されたプロセスのプロセス ID (PID) |
| `ProcessCommandLine` | `string` | 新しいプロセスの作成に使用されるコマンド ライン |
| `ProcessIntegrityLevel` | `string` | 新しく作成されたプロセスの整合性レベル。 Windows では、ダウンロードされたインターネットから起動された場合など、特定の特性に基づいてプロセスに整合性レベルが割り当てられます。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `ProcessTokenElevation` | `string` | 新しく作成されたプロセスに適用されるトークン昇格の種類を示します。 使用可能な値: TokenElevationTypeLimited (restricted)、TokenElevationTypeDefault (standard)、TokenElevationTypeFull (管理者特権) |
| `ProcessCreationTime` | `datetime` | プロセスが作成された日時 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountObjectId` | `string` | Azure AD のアカウントの一意識別子 |
| `LogonId` | `string` | ログオン セッションの識別子。 この識別子は、再起動間でのみ同じマシンで一意です |
| `InitiatingProcessAccountDomain` | `string` | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | `string` | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | `string` | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessAccountUpn` | `string` | イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN) |
| `InitiatingProcessAccountObjectId` | `string` | イベントを担当するプロセスを実行したユーザー アカウントの Azure AD オブジェクト ID |
| `InitiatingProcessLogonId` | `string` | イベントを開始したプロセスのログオン セッションの識別子。 この識別子は、再起動間でのみ同じコンピューターで一意です。 |
| `InitiatingProcessIntegrityLevel` | `string` | イベントを開始したプロセスの整合性レベル。 Windows では、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルが割り当てられます。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | `string` | イベントを開始したプロセスに適用されたユーザー Access Control (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessSHA1` | `string` | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | `string` | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `InitiatingProcessMD5` | `string` | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | `string` | イベントを開始したプロセスの名前 |
| `InitiatingProcessFileSize` | `long` | イベントを担当するプロセスを実行したファイルのサイズ |
| `InitiatingProcessVersionInfoCompanyName` | `string` | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) の会社名 |
| `InitiatingProcessVersionInfoProductName` | `string` | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの製品名 |
| `InitiatingProcessVersionInfoProductVersion` | `string` | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの製品バージョン |
| `InitiatingProcessVersionInfoInternalFileName` | `string` | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの内部ファイル名 |
| `InitiatingProcessVersionInfoOriginalFileName` | `string` | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの元のファイル名 |
| `InitiatingProcessVersionInfoFileDescription` | `string` | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの説明 |
| `InitiatingProcessId` | `int` | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | `string` | イベントを開始したプロセスを実行するために使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | `datetime` | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | `string` | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | `int` | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | `string` | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | `datetime` | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessSignerType` | `string` | イベントを開始したプロセスのファイル署名者の種類 (イメージ ファイル) |
| `InitiatingProcessSignatureStatus` | `string` | イベントを開始したプロセス (イメージ ファイル) の署名の状態に関する情報 |
| `ReportId` | `long` | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | `string` | Application Guard がブラウザー アクティビティを分離するために使用する仮想化コンテナーの識別子 |
| `AdditionalFields` | `string` | JSON 配列形式のイベントに関する追加情報 |


## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
