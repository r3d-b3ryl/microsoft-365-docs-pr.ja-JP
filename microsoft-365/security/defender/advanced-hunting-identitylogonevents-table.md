---
title: 高度なハンティング スキーマの IdentityLogonEvents テーブル
description: 高度なハンティング スキーマの IdentityLogonEvents テーブルで Active Directory によって記録された認証イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, IdentityLogonEvents, Azure AD, Active Directory, Microsoft Defender for Identity, ID
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
ms.openlocfilehash: 177710ef709d6c9d3f40882a370620f908671114
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481440"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityLogonEvents` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Identityによってキャプチャされたオンプレミスの Active Directoryを介して行われた認証アクティビティと、Microsoft オンライン サービスに関連する認証アクティビティによってキャプチャされた認証アクティビティに関する情報が含まれています。Microsoft Defender for Cloud Apps。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (`ActionType` 値) の詳細については、Defender for Cloud で使用できる組み込みのスキーマ参照を使用します。

>[!NOTE]
>次の表では、Defender for Cloud Apps によって追跡される Azure Active Directory (Azure AD) ログオン アクティビティ、特に ActiveSync やその他のレガシ プロトコルを使用した対話型サインインと認証アクティビティについて説明します。 この表では使用できない非対話型ログオンは、Azure AD 監査ログに表示できます。 [Defender for Cloud Apps を Microsoft 365 に接続する方法の詳細](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `ActionType` | `string` | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内スキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください |
| `Application` | `string` | 記録されたアクションを実行したアプリケーション |
| `LogonType` | `string` | ログオン セッションの種類。具体的には次のとおりです。<br><br> - **対話型** - ユーザーがローカル キーボードと画面を使用してコンピューターと物理的に対話する<br><br> - **リモート 対話型 (RDP) ログオン** - ユーザーは、リモート デスクトップ、ターミナル サービス、リモート アシスタンス、またはその他の RDP クライアントを使用してリモートでコンピューターと対話します。<br><br> - **ネットワーク** - PsExec を使用してマシンにアクセスしたとき、またはコンピューター上の共有リソース (プリンターや共有フォルダーなど) にアクセスしたときに開始されるセッション<br><br> - **Batch** - スケジュールされたタスクによって開始されるセッション<br><br> - **サービス** - 開始時にサービスによって開始されるセッション |
| `Protocol` | `string` | 使用されるネットワーク プロトコル |
| `FailureReason` | `string` | 記録されたアクションが失敗した理由を説明する情報 |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | `string` | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | `string` | Azure AD のアカウントの一意識別子 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の開始、姓または姓の組み合わせ。 |
| `DeviceName` | `string` | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | `string` | デバイスの種類 |
| `OSPlatform` | `string` | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 |
| `IPAddress` | `string` | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | `string` | 通信中に使用される TCP ポート |
| `DestinationDeviceName` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | `string` | 記録されたアクションを処理したサーバー アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | `string` | 関連するネットワーク通信の宛先ポート |
| `TargetDeviceName` | `string` | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountDisplayName` | `string` | 記録されたアクションが適用されたアカウントの表示名 |
| `Location` | `string` | イベントに関連付けられている都市、国、またはその他の地理的な場所 |
| `Isp` | `string` | エンドポイント IP アドレスに関連付けられたインターネット サービス プロバイダー (ISP) |
| `ReportId` | `long` | イベントの一意識別子 |
| `AdditionalFields` | `string` | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
