---
title: 高度な狩猟スキーマの中の IdLogon イベント テーブル
description: 高度な検索スキーマの IdentityLogonEvents テーブルに Active Directory によって記録された認証イベントについて
keywords: 高度な狩猟, 脅威の狩猟, サイバー脅威の狩猟, Microsoft 365 ディフェンダー, Microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データタイプ, 説明, IdentityLogonEvents, Azure AD, アクティブディレクトリ, アイデンティティのためのマイクロソフトディフェンダー, アイデンティティ
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3cd0c0f371c73a515704791e829be7266d400580
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572755"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityLogonEvents`[高度な検索](advanced-hunting-overview.md)スキーマのテーブルには、Microsoft Cloud App Securityによってキャプチャされた Microsoft オンライン サービスに関連する Id と認証アクティビティの Microsoft Defender によってキャプチャされた、オンプレミスの Active Directory を介して行われた認証アクティビティに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 ( `ActionType` 値) の詳細については、セキュリティ センターで利用できる組み込みのスキーマ リファレンスを使用してください。

>[!NOTE]
>次の表は、Cloud App Securityによって追跡されるAzure Active Directory (Azure AD) ログオン アクティビティ、特に ActiveSync およびその他の従来のプロトコルを使用した対話型サインインと認証アクティビティについて説明します。 この表に記載されていない非対話型ログオンは、Azure AD 監査ログに表示できます。 [Cloud App SecurityをMicrosoft 365に接続する方法の詳細](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティのタイプ。 詳細については、 [ポータル内スキーマ リファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `LogonType` | string | ログオン セッションの種類、具体的には次の操作を行います。<br><br> - **対話 -** ユーザーはローカルキーボードと画面を使用してマシンと物理的に対話します<br><br> - **リモート 対話型 (RDP) ログオン** - ユーザーはリモート デスクトップ、ターミナル サービス、リモート アシスタンス、または他の RDP クライアントを使用してリモートでコンピュータと対話します。<br><br> - **ネットワーク** - PsExec を使用してマシンにアクセスするとき、またはマシン上の共有リソース (プリンターや共有フォルダなど) にアクセスした場合に開始されるセッション<br><br> - **バッチ** - スケジュールされたタスクによって開始されたセッション<br><br> - **サービス** - サービスが開始する時点で開始されるセッション |
| `Protocol` | string | 使用されるネットワーク プロトコル |
| `FailureReason` | string | 記録されたアクションが失敗した理由を説明する情報 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD のアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定された名前または名、ミドル ネームの開始、姓または姓の組み合わせ。 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | string | デバイスの種類 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `Port` | string | 通信中に使用される TCP ポート |
| `DestinationDeviceName` | string | 記録されたアクションを処理したサーバー・アプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | string | 記録されたアクションを処理したサーバー・アプリケーションを実行しているデバイスの IP アドレス |
| `DestinationPort` | string | 関連ネットワーク通信の宛先ポート |
| `TargetDeviceName` | string | 記録された操作が適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountDisplayName` | string | 記録されたアクションが適用された取引先企業の表示名 |
| `Location` | string | イベントに関連付けられている都市、国、またはその他の地理的位置 |
| `Isp` | string | エンドポイント IP アドレスに関連付けられているインターネット サービス プロバイダ (ISP) |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | string | エンティティまたはイベントに関する追加情報 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)