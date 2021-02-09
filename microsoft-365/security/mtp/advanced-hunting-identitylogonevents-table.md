---
title: 高度な検索スキーマの IdentityLogonEvents テーブル
description: 高度な検索スキーマの IdentityLogonEvents テーブルに Active Directory によって記録される認証イベントについて説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、IdentityLogonEvents、Azure AD、Active Directory、Azure ATP、ID
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
ms.openlocfilehash: 87ac6194374e8e042cf9d00271b17dd8bb785d64
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145357"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度な検索スキーマの表には、Id 用に Microsoft Defender によってキャプチャされたオンプレミスの Active Directory を介して行われた認証アクティビティと、Microsoft Cloud App Security によってキャプチャされた Microsoft オンライン サービスに関連する認証アクティビティに関する情報が含まれます。 `IdentityLogonEvents` [](advanced-hunting-overview.md) このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( 値) の詳細については、セキュリティ センターで使用可能な組み込みのスキーマ `ActionType` 参照を使用してください。 [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

>[!NOTE]
>次の表では、Cloud App Security によって追跡される Azure Active Directory (AD) ログオン アクティビティ、特に ActiveSync や他のレガシ プロトコルを使用した対話型サインインと認証アクティビティについて説明します。 この表では使用できない非対話型ログオンは、Azure 監査ログADできます。 [Cloud App Security を Microsoft 365 に接続する方法の詳細](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類。 詳細については [、ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `LogonType` | string | ログオン セッションの種類。具体的には次の種類があります。<br><br> - **対話型** - ユーザーがローカルのキーボードと画面を使ってコンピューターと物理的に対話する<br><br> - **リモート 対話型 (RDP)** ログオン - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、その他の RDP クライアントを使用してリモートでコンピューターと対話します。<br><br> - **ネットワーク** - PsExec を使用してコンピューターにアクセスするか、プリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに開始されるセッション<br><br> - **Batch** - スケジュールされたタスクによって開始されるセッション<br><br> - **サービス** - サービスが開始すると開始されるセッション |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `Protocol` | string | 使用されるネットワーク プロトコル |
| `FailureReason` | string | 記録されたアクションが失敗した理由を説明する情報 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD のアカウントの一意の識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウント ユーザーの名前。 通常、名、ミドル ネーム、姓または姓の組み合わせ。 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | string | デバイスの種類 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | string | 通信中に使用される TCP ポート |
| `DestinationDeviceName` | string | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | string | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | string | 関連するネットワーク通信の宛先ポート |
| `TargetDeviceName` | string | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountDisplayName` | string | 記録されたアクションが適用されたアカウントの表示名 |
| `Location` | string | イベントに関連付けられている都市、国、その他の地理的な場所 |
| `Isp` | string | エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | string | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
