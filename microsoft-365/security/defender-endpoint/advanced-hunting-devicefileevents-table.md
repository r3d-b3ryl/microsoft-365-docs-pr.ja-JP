---
title: 高度な検索スキーマの DeviceFileEvents テーブル
description: 高度なハンティング スキーマの DeviceFileEvents テーブルのファイル関連イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、devicefileevents、ファイル、パス、ハッシュ、sha1、sha256、md5、FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 323cc8e809b81f937a29e41f24c2976c3d5c175b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500853"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度 `DeviceFileEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ファイルの作成、変更、その他のファイル システム イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング  [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | 文字列 | サービス内のデバイスの一意の識別子 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。 |
| `MD5` | 文字列 | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileOriginUrl` | 文字列 | ファイルがダウンロードされた URL |
| `FileOriginReferrerUrl` | 文字列 | ダウンロードしたファイルにリンクする Web ページの URL |
| `FileOriginIP` | 文字列 | ファイルがダウンロードされた IP アドレス |
| `InitiatingProcessAccountDomain` | 文字列 | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | 文字列 | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | 文字列 | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessMD5` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessSHA1` | 文字列 | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessFolderPath` | 文字列 | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessFileName` | 文字列 | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | 文字列 | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessIntegrityLevel` | 文字列 | イベントを開始したプロセスの整合性レベルを指定します。 Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | 文字列 | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | 文字列 | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `RequestProtocol` | 文字列 | ネットワーク プロトコル (該当する場合) を使用してアクティビティを開始します。不明、ローカル、SMB、または NFS |
| `ShareName` | 文字列 | ファイルを含む共有フォルダーの名前 |
| `RequestSourceIP` | 文字列 | アクティビティを開始したリモート デバイスの IPv4 または IPv6 アドレス |
| `RequestSourcePort` | 文字列 | アクティビティを開始したリモート デバイスの送信元ポート |
| `RequestAccountName` | 文字列 | アクティビティをリモートで開始するために使用されるアカウントのユーザー名 |
| `RequestAccountDomain` | 文字列 | アクティビティをリモートで開始するために使用されるアカウントのドメイン |
| `RequestAccountSid` | 文字列 | アクティビティをリモートで開始するアカウントのセキュリティ識別子 (SID) |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | 文字列 | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |
| `SensitivityLabel` | 文字列 | 電子メール、ファイル、または他のコンテンツに適用されるラベルを情報保護のために分類する |
| `SensitivitySubLabel` | 文字列 | 電子メール、ファイル、または他のコンテンツに適用されるサブラベルを、情報保護のために分類します。感度サブラベルは、感度ラベルの下でグループ化されますが、個別に処理されます。 |
| `IsAzureInfoProtectionApplied` | boolean | ファイルが Azure Information Protection によって暗号化されているかどうかを示します。 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
