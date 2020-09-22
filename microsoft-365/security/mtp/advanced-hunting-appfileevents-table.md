---
title: 高度な検索スキーマの AppFileEvents テーブル
description: 高度な検索スキーマの AppFileEvents テーブルでクラウドアプリおよびサービスに関連付けられているファイル関連イベントについて説明します。
keywords: 高度な検索、脅威の探し、サイバーの脅威の検出、microsoft の脅威の防止、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AppFileEvents、Cloud App Security、MCAS
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
ms.openlocfilehash: 385011382d20919b219cf84e13cda4993826691b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197063"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

`AppFileEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、クラウドアプリと Microsoft cloud App Security によって監視されるサービスのファイル関連アクティビティに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | 文字列 | 記録されたアクションを実行したアプリケーション |
| `FileName` | 文字列 | 記録されたアクションが適用されたファイルの名前 |
| `FolderPath` | 文字列 | 記録されたアクションが適用されたファイルを含むフォルダ |
| `PreviousFileName` | 文字列 | アクションの結果として名前が変更されたファイルの元の名前 |
| `PreviousFolderPath` | 文字列 | 記録されたアクションが適用される前のファイルが含まれている元のフォルダー |
| `Protocol` | 文字列 | 使用されるネットワークプロトコル |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `AccountUpn` | 文字列 | アカウントのユーザープリンシパル名 (UPN) |
| `AccountObjectId` | 文字列 | Azure AD でのアカウントの一意識別子 |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `DeviceName` | 文字列 | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | 文字列 | デバイスの種類 | 
| `OSPlatform` | 文字列 | デバイス上で実行されているオペレーティングシステムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `DestinationDeviceName` | 文字列 | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | 文字列 | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス |
| `Location` | 文字列 | イベントに関連付けられている市区町村、国、またはその他の地理的な場所 |
| `Isp` | 文字列 | エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP) |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | 文字列 | エンティティまたはイベントに関するその他の情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
