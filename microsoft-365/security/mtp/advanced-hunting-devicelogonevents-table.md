---
title: 高度な検索スキーマの DeviceLogonEvents テーブル
description: 高度な検索スキーマの DeviceLogonEvents テーブルの認証イベントまたはサインイン イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、logonevents、DeviceLogonEvents、認証、ログオン、サインイン
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
ms.openlocfilehash: 3a5666cc106365876956c8e313f9cd2f5a996e6f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931232"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



高度 `DeviceLogonEvents` な検索スキーマの [表には](advanced-hunting-overview.md) 、デバイス上のユーザー ログオンおよび他の認証イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用できる組み込みのスキーマ `ActionType` リファレンスを使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string |イベントをトリガーしたアクティビティの種類 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `LogonType` | string | ログオン セッションの種類。具体的には次の種類があります。<br><br> - **対話型** - ユーザーがローカルのキーボードと画面を使ってコンピューターと物理的に対話する<br><br> - **リモート 対話型 (RDP)** ログオン - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、その他の RDP クライアントを使用してリモートでコンピューターと対話します。<br><br> - **ネットワーク** - PsExec を使用してコンピューターにアクセスするか、プリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに開始されるセッション<br><br> - **Batch** - スケジュールされたタスクによって開始されるセッション<br><br> - **サービス** - サービスの開始時に開始されるセッション<br> |
| `LogonId` | string | ログオン セッションの識別子。 この識別子は、再起動の間にのみ同じコンピューター上で一意です。 |
| `RemoteDeviceName` | string | 影響を受けるコンピューターでリモート操作を実行したコンピューターの名前。 報告されるイベントに応じて、この名前は完全修飾ドメイン名 (FQDN)、NetBIOS 名、またはドメイン情報のないホスト名である場合があります。 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteIPType` | string | IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど) |
| `RemotePort` | int | 接続されているリモート デバイス上の TCP ポート |
| `AdditionalFields` | string | JSON 配列形式でのイベントに関する追加情報 |
| `InitiatingProcessAccountDomain` | string | イベントを処理するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを処理するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを処理するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネット ダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響します。 |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権の昇格の有無を示すトークンの種類 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは、通常は入力されません。使用可能な場合は SHA1 列を使用します。 |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | int | イベントを処理するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | ブラウザーの動作を分離するために Application Guard によって使用される仮想化コンテナーの識別子 |
| `IsLocalAdmin` | ブール値 | ユーザーがコンピューターのローカル管理者かどうかを示すブール値のインジケーター |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
