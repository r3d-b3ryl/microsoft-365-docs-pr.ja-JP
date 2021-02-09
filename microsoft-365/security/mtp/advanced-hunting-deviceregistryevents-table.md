---
title: 高度な検索スキーマの DeviceRegistryEvents テーブル
description: 高度な検索スキーマの DeviceRegistryEvents テーブルからクエリできるレジストリ イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、レジストリ イベント、レジストリ、DeviceRegistryEvents、キー、サブキー、値
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6bd0e4fe3173fa899b0b9c86d6f85d724b52be3a
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145009"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `DeviceRegistryEvents` な検索スキーマ [の表](advanced-hunting-overview.md) には、レジストリ エントリの作成と変更に関する情報が含されています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `RegistryKey` | string | 記録されたアクションが適用されたレジストリ キー |
| `RegistryValueType` | string | 記録されたアクションが適用されたレジストリ値のデータ型 (バイナリ、文字列など) |
| `RegistryValueName` | string | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` | string | 記録されたアクションが適用されたレジストリ値のデータ |
| `PreviousRegistryKey` | string | 変更前のレジストリ値の元のレジストリ キー |
| `PreviousRegistryValueName` | string | 変更前のレジストリ値の元の名前 |
| `PreviousRegistryValueData` | string | 変更前のレジストリ値の元のデータ |
| `InitiatingProcessAccountDomain` | string | イベントを処理するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを処理するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを処理するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessAccountUpn` | string | イベントを処理するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN) |
| `InitiatingProcessAccountObjectId` | string | Azure ADイベントを処理するプロセスを実行したユーザー アカウントのオブジェクト ID を取得します。 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは通常は入力されません。使用可能な場合は、SHA1 列を使用します。 |
| `InitiatingProcessMD5` | 文字列型 | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessFileSize` | long | イベントを処理するプロセスを実行したファイルのサイズ |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | int | イベントを処理するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネット ダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響します。 |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権の昇格の有無を示すトークンの種類 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | ブラウザーの動作を分離するために Application Guard によって使用される仮想化コンテナーの識別子 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
