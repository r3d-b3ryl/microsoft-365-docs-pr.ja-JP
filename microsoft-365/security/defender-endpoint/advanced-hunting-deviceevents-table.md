---
title: 高度な検索スキーマの DeviceEvents テーブル
description: 高度なハンティング スキーマのその他のデバイス イベント (DeviceEvents) テーブルのウイルス対策、ファイアウォール、その他のイベントの種類について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、セキュリティ イベント、ウイルス対策、ファイアウォール、エクスプロイト ガード、MiscEvents
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
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064387"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

高度な検索スキーマのその他のデバイス イベントまたはテーブルには、Microsoft Defender Antivirus やエクスプロイト保護などのセキュリティ制御によってトリガーされるイベントなど、さまざまな種類のイベントに関する情報 `DeviceEvents` が含まれています。 [](advanced-hunting-overview.md) このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダー |
| `SHA1` | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | 文字列 | 記録されたアクションが適用されたファイルの SHA-256 このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。 |
| `MD5` | string | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountName` |string | アカウントのユーザー名 |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `RemoteUrl` | 文字列 | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `RemoteDeviceName` | 文字列 | 影響を受けるデバイスでリモート操作を実行したデバイスの名前。 報告されるイベントに応じて、この名前には完全修飾ドメイン名 (FQDN)、NetBIOS 名、またはドメイン情報のないホスト名を指定できます。 |
| `ProcessId` | int | 新しく作成されたプロセスのプロセス ID (PID) |
| `ProcessCommandLine` | string | 新しいプロセスの作成に使用するコマンド ライン |
| `ProcessCreationTime` | 日付型 | プロセスが作成された日時 |
| `ProcessTokenElevation` | string | 新しく作成されたプロセスに適用されるユーザー アクセス制御 (UAC) 特権昇格の有無を示すトークンの種類 |
| `LogonId` | string | ログオン セッションの識別子。 この識別子は、再起動の間にのみ同じデバイスで一意です |
| `RegistryKey` | string | 記録されたアクションが適用されたレジストリ キー |
| `RegistryValueName` | string | 記録されたアクションが適用されたレジストリ値の名前 |
| `RegistryValueData` | string | 記録されたアクションが適用されたレジストリ値のデータ |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemotePort` | int | 接続されているリモート デバイスの TCP ポート |
| `LocalIP` | string | 通信中に使用されるローカル デバイスに割り当てられた IP アドレス |
| `LocalPort` | int | 通信中に使用されるローカル デバイス上の TCP ポート |
| `FileOriginUrl` | string | ファイルがダウンロードされた URL |
| `FileOriginIP` | string | ファイルがダウンロードされた IP アドレス |
| `AdditionalFields` | string | JSON 配列形式のイベントに関する追加情報 |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-1 |
| `InitiatingProcessSHA256` | string | イベントを開始したプロセス (イメージ ファイル) の SHA-256。 このフィールドは、通常は設定されません。使用可能な場合は SHA1 列を使用します。 |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (イメージ ファイル) を含むフォルダー |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスの実行に使用されるコマンド ライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日時 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを生成した親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentFileName` | string | イベントを担当するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (イメージ ファイル) の MD5 ハッシュ |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessLogonId` | string | イベントを開始したプロセスのログオン セッションの識別子。 この識別子は、再起動の間にのみ同じデバイスで一意です |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を and 列と組み合わせて `DeviceName` 使用する必要 `Timestamp` があります。 |
| `AppGuardContainerId` | string | ブラウザーのアクティビティを分離するために Application Guard が使用する仮想化コンテナーの識別子 |


## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
