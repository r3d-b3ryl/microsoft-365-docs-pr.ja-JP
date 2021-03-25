---
title: 高度な検索スキーマの DeviceLogonEvents テーブル
description: 高度なハンティング スキーマの DeviceLogonEvents テーブルの認証イベントまたはサインイン イベントについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、devicelogonevents、認証、ログオン、サインイン、LogonEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7bc6e655d3a423b45f70210e53fca9713427355a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067060"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度 `DeviceLogonEvents` な検索スキーマの [表](advanced-hunting-overview.md) には、ユーザー ログオンや他の認証イベントに関する情報が含まれている。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

> [!NOTE]
> DeviceLogonEvents のコレクションは、Windows 7 または Windows 7 ではサポートWindows Server 2008 R2。
> ユーザー ログオン アクティビティを最適に表示するために、Windows 10 または Windows Server 2019 にアップグレードすることをお勧めします。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string |イベントをトリガーしたアクティビティの種類 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `LogonType` | string | ログオン セッションの種類(具体的には次の場合):<br><br> - **対話型** - ユーザーがローカル キーボードと画面を使用してデバイスを物理的に操作する<br><br> - **リモート 対話型 (RDP) ログオン** - ユーザーがリモート デスクトップ、ターミナル サービス、リモート アシスタンス、または他の RDP クライアントを使用してデバイスをリモートで操作する<br><br> - **ネットワーク** - PsExec を使用してデバイスにアクセスした場合、またはデバイス上の共有リソース (プリンターや共有フォルダーなど) にアクセスするときに開始されるセッション<br><br> - **Batch** - スケジュールされたタスクによって開始されるセッション<br><br> - **サービス** - サービスが開始するセッション<br> |
| `LogonId` | string | ログオン セッションの識別子。 この識別子は、再起動の間にのみ同じデバイスで一意です |
| `RemoteDeviceName` | string | 影響を受けるデバイスでリモート操作を実行したデバイスの名前。 報告されるイベントに応じて、この名前には完全修飾ドメイン名 (FQDN)、NetBIOS 名、またはドメイン情報のないホスト名を指定できます。 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemoteIPType` | string | IP アドレスの種類 (パブリック、プライベート、予約済み、ループバック、Teredo、FourToSixMapping、ブロードキャストなど) |
| `RemotePort` | int | 接続されているリモート デバイスの TCP ポート |
| `AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネットダウンロードから起動された場合など、特定の特性に基づいてプロセスに整合性レベルを割り当てる。 これらの整合性レベルは、リソースへのアクセス許可に影響を与えます |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。 |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。 |
| `AppGuardContainerId` | string | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |
| `IsLocalAdmin` | boolean | ユーザーがデバイスのローカル管理者であるかどうかを示すブール値インジケーター |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
