---
title: 高度な検索スキーマの DeviceLogonEvents テーブル
description: 高度なハンティング スキーマの DeviceLogonEvents テーブルの認証イベントまたはサインイン イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、logonevents、DeviceLogonEvents、認証、ログオン、サインイン
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: eec17d9c9605e6ee731c4ff518de029e2ecd3c03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207657"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



高度 `DeviceLogonEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、デバイス上のユーザー ログオンや他の認証イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされるイベントの種類 (値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ参照 `ActionType` を使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string |イベントをトリガーしたアクティビティの種類 |
| `LogonType` | string | ログオン セッションの種類(具体的には次の場合):<br><br> - **対話型** - ユーザーがローカル キーボードと画面を使用してコンピューターと物理的に対話する<br><br> - **リモート 対話型 (RDP) ログオン** - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、または他の RDP クライアントを使用してコンピューターをリモート操作します。<br><br> - **ネットワーク** - PsExec を使用してコンピューターにアクセスした場合、またはコンピューター上の共有リソース (プリンターや共有フォルダーなど) にアクセスするときに開始されるセッション<br><br> - **Batch** - スケジュールされたタスクによって開始されるセッション<br><br> - **サービス** - サービスが開始するセッション<br> |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `Protocol` | string | 通信中に使用されるプロトコル |
| `FailureReason` | string | 記録されたアクションが失敗した理由を説明する情報 |
| `IsLocalAdmin` | ブール値 | ユーザーがコンピューターのローカル管理者であるかどうかを示すブール値インジケーター |
| `LogonId` | string | ログオン セッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `RemoteDeviceName` | string | 影響を受けるコンピューターでリモート操作を実行したコンピューターの名前。 報告されるイベントに応じて、この名前には完全修飾ドメイン名 (FQDN)、NetBIOS 名、またはドメイン情報のないホスト名を指定できます。 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteIPType` | string | IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど) |
| `RemotePort` | 整数 | 接続されているリモート デバイスの TCP ポート |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessAccountUpn` | string | イベントを担当するプロセスを実行したアカウントのユーザー プリンシパル名 (UPN) |
| ` InitiatingProcessAccountObjectId` | string | Azure ADを実行したユーザー アカウントのオブジェクト ID を指定します。 |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows、インターネットダウンロードから起動した場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる必要があります。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。 |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessFileSize` | long | イベントの処理を実行したファイルのサイズ |
| `InitiatingProcessVersionInfoCompanyName` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの会社名 |
| `InitiatingProcessVersionInfoProductName` | string | イベントを担当するプロセス (イメージ ファイル) のバージョン情報からの製品名 |
| `InitiatingProcessVersionInfoProductVersion` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの製品バージョン |
| `InitiatingProcessVersionInfoInternalFileName` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの内部ファイル名 |
| `InitiatingProcessVersionInfoOriginalFileName` | string | イベントを担当するプロセスのバージョン情報 (イメージ ファイル) からの元のファイル名 |
| `InitiatingProcessVersionInfoFileDescription` | string | イベントを担当するプロセス (イメージ ファイル) のバージョン情報の説明 |
| `InitiatingProcessId` | 整数 | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | 整数 | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |
| `AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |

## <a name="related-topics"></a>関連トピック
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
