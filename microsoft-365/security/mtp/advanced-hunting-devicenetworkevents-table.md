---
title: 高度な検索スキーマの DeviceNetworkEvents 孔テーブル
description: 高度な検索スキーマの DeviceNetworkEvents 孔テーブルからクエリできるネットワーク接続イベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、devicenetworkevents 孔、NetworkCommunicationEvents、network接続、リモート ip、ローカル ip
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2e7999fef43adb372947d9edf92b84ac67f347fe
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235006"
---
# <a name="devicenetworkevents"></a>DeviceNetworkEvents 孔

**適用対象:**
- Microsoft Threat Protection



`DeviceNetworkEvents` [高度な](advanced-hunting-overview.md)検索スキーマの表には、ネットワーク接続と関連イベントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `DeviceId` | string | コンピューターの一意識別子 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類 |
| `RemoteIP` | 文字列 | に接続されていた IP アドレス |
| `RemotePort` | int | 接続先のリモートデバイスの TCP ポート |
| `RemoteUrl` | string | に接続されていた URL または完全修飾ドメイン名 (FQDN) |
| `LocalIP` | 文字列 | 通信時に使用されるローカルコンピューターに割り当てられた IP アドレス |
| `LocalPort` | int | 通信時に使用されるローカルコンピューターの TCP ポート |
| `Protocol` | string | 使用されている IP プロトコル (TCP または UDP) |
| `LocalIPType` | string | IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト) |
| `RemoteIPType` | string | IP アドレスの種類 (例: Public、Private、Reserved、Loopback、Teredo、FourToSixMapping、ブロードキャスト) |
| `InitiatingProcessSHA1` | string | イベントを開始したプロセス (画像ファイル) の SHA-1 |
| `InitiatingProcessMD5` | string | イベントを開始したプロセス (画像ファイル) の MD5 ハッシュ |
| `InitiatingProcessFileName` | string | イベントを開始したプロセスの名前 |
| `InitiatingProcessId` | int | イベントを開始したプロセスのプロセス ID (PID) |
| `InitiatingProcessCommandLine` | string | イベントを開始したプロセスを実行するために使用されるコマンドライン |
| `InitiatingProcessCreationTime` | 日付型 | イベントを開始したプロセスが開始された日付と時刻 |
| `InitiatingProcessFolderPath` | string | イベントを開始したプロセス (画像ファイル) を含むフォルダー |
| `InitiatingProcessParentFileName` | string | イベントを処理するプロセスを生成した親プロセスの名前 |
| `InitiatingProcessParentId` | int | イベントを担当するプロセスを発生させる親プロセスのプロセス ID (PID) |
| `InitiatingProcessParentCreationTime` | 日付型 | イベントを担当するプロセスの親が開始された日時 |
| `InitiatingProcessAccountDomain` | string | イベントを担当するプロセスを実行したアカウントのドメイン |
| `InitiatingProcessAccountName` | string | イベントを担当するプロセスを実行したアカウントのユーザー名 |
| `InitiatingProcessAccountSid` | string | イベントを担当するプロセスを実行したアカウントのセキュリティ識別子 (SID) |
| `InitiatingProcessIntegrityLevel` | string | イベントを開始したプロセスの整合性レベル。 Windows は、インターネットダウンロードから起動されたかどうかなど、特定の特性に基づいてプロセスに整合性レベルを割り当てます。 これらの整合性レベルは、リソースへのアクセス許可に影響します。 |
| `InitiatingProcessTokenElevation` | string | イベントを開始したプロセスに適用されたユーザーアクセス制御 (UAC) 特権昇格が存在するかどうかを示すトークンの種類 |
| `ReportId` | long | 繰り返しカウンターに基づくイベント識別子。 一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。 |
| `AppGuardContainerId` | string | Application Guard がブラウザーのアクティビティを分離するために使用する仮想化されたコンテナーの識別子 |

## <a name="related-topics"></a>関連項目
- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
