---
title: 高度な検索スキーマの [イベント] テーブル
description: 高度な検索スキーマのイベントテーブルの Active Directory によって記録された認証イベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、identity Logonevents、Azure AD、Active Directory、Azure ATP、id
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 176f131ad020d001b72b97332d54be71feef5548
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847418"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityLogonEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft の Cloud App Security で取得した microsoft online services に関連した id と認証アクティビティについて microsoft Defender がキャプチャした認証アクティビティに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

>[!NOTE]
>次の表は、クラウドアプリのセキュリティによって追跡された Azure Active Directory (AD) ログオンアクティビティ、具体的には、ActiveSync やその他の従来のプロトコルを使用した対話的なサインインと認証アクティビティについて説明しています。 この表に記載されていない非対話型のログオンは、Azure AD 監査ログに表示できます。 [クラウドアプリのセキュリティを Microsoft 365 に接続する方法について説明します。](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | string | イベントをトリガーしたアクティビティの種類。 詳細については、 [ポータル内のスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を参照してください。 |
| `LogonType` | string | ログオンセッションの種類。具体的には次のとおりです。<br><br> - **Interactive** -ユーザーがローカルのキーボードと画面を使用してコンピューターと物理的に対話する<br><br> - **リモート対話 (RDP) ログオン** -ユーザーがリモートデスクトップ、ターミナルサービス、リモートアシスタンス、またはその他の RDP クライアントを使用してリモートでコンピューターと対話する<br><br> - PsExec を使用してコンピューターにアクセスするとき、またはプリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに、 **ネットワーク** セッションが開始されます。<br><br> - スケジュールされたタスクによって開始された **バッチ** セッション<br><br> - **サービス** -開始時にサービスによって開始されたセッション |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `Protocol` | string | 使用されるネットワークプロトコル |
| `FailureReason` | string | 記録された操作が失敗した理由を説明する情報 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountUpn` | string | アカウントのユーザープリンシパル名 (UPN) |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD でのアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | string | デバイスの種類 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `DestinationDeviceName` | string | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの名前 |
| `DestinationIPAddress` | string | 記録されたアクションを処理したサーバーアプリケーションを実行しているデバイスの IP アドレス |
| `TargetDeviceName` | string | 記録されたアクションが適用されたデバイスの完全修飾ドメイン名 (FQDN) |
| `TargetAccountDisplayName` | string | 記録済みのアクションが適用されたアカウントの名前を表示します。 |
| `Location` | string | イベントに関連付けられている市区町村、国、またはその他の地理的な場所 |
| `Isp` | string | エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP) |
| `ReportId` | long | イベントの一意識別子 |
| `AdditionalFields` | string | エンティティまたはイベントに関するその他の情報 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
