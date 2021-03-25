---
title: 高度な検索スキーマの IdentityInfo テーブル
description: 高度なハンティング スキーマの IdentityInfo テーブルのユーザー アカウント情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft の脅威の保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、AccountInfo、IdentityInfo、アカウント
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e3e5410c868336308b1ecb34ba4326bf2dc5796f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064739"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `IdentityInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、Azure Active Directory を含むさまざまなサービスから取得したユーザー アカウントに関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!NOTE]
>このテーブルはから名前が変更されました `AccountInfo` 。 名前の変更中に、ポータルに保存されているクエリはすべて自動的に更新されます。 他の場所に保存したクエリを確認します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure アカウントのアカウントの一意AD |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `OnPremSid` | string | アカウントのオンプレミスセキュリティ識別子 (SID) |
| `CloudSid` | string | アカウントのクラウド セキュリティ識別子 |
| `GivenName` | string | アカウント ユーザーの名前または名を指定する |
| `Surname` | string | アカウント ユーザーの姓、ファミリ名、または姓 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `Department` | string | アカウント ユーザーが属する部署の名前 |
| `JobTitle` | string | アカウント ユーザーの役職 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `EmailAddress` | string | アカウントの SMTP アドレス |
| `SipProxyAddress` | string | アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス |
| `City` | string | アカウント ユーザーが保存されている都市 |
| `Country` | string | アカウント ユーザーが保存されている国/地域 |
| `IsAccountEnabled` | boolean | アカウントが有効になっているかどうかを示します。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
