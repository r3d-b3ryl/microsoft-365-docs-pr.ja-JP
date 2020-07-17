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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2116d8f6f1006f5acf9d468006fa07a04e13087b
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046030"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**適用対象:**
- Microsoft Threat Protection

`IdentityLogonEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft Cloud App Security で取得した microsoft online services に関連する Azure ATP と認証アクティビティによってキャプチャされた、オンプレミスの Active Directory によって行われた認証アクティビティに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `ActionType` | 文字列 | イベントをトリガーしたアクティビティの種類 |
| `LogonType` | string | ログオンセッションの種類。具体的には次のとおりです。<br><br> - **Interactive** -ユーザーがローカルのキーボードと画面を使用してコンピューターと物理的に対話する<br><br> - **リモート対話 (RDP) ログオン**-ユーザーがリモートデスクトップ、ターミナルサービス、リモートアシスタンス、またはその他の RDP クライアントを使用してリモートでコンピューターと対話する<br><br> - PsExec を使用してコンピューターにアクセスするとき、またはプリンターや共有フォルダーなどのコンピューター上の共有リソースにアクセスするときに、**ネットワーク**セッションが開始されます。<br><br> - スケジュールされたタスクによって開始された**バッチ**セッション<br><br> - **サービス**-開始時にサービスによって開始されたセッション |
| `Application` | string | 記録されたアクションを実行したアプリケーション |
| `Protocol` | string | 通信中に使用されるプロトコル |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `AccountUpn` | string | アカウントのユーザープリンシパル名 (UPN) |
| `AccountSid` | string | アカウントのセキュリティ識別子 (SID) |
| `AccountObjectId` | string | Azure AD でのアカウントの一意識別子 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `DeviceName` | string | コンピューターの完全修飾ドメイン名 (FQDN) |
| `DeviceType` | string | デバイスの種類 |
| `OSPlatform` | string | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 |
| `IPAddress` | string | エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス |
| `Location` | string | イベントに関連付けられている市区町村、国、またはその他の地理的な場所 |
| `Isp` | string | エンドポイントの IP アドレスに関連付けられているインターネットサービスプロバイダー (ISP) |

## <a name="related-topics"></a>関連トピック
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を捜索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
