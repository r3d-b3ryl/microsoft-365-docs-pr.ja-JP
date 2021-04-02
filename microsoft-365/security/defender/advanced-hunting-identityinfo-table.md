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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498209"
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
| `AccountUpn` | 文字列 | アカウントのユーザー プリンシパル名 (UPN) |
| `OnPremSid` | 文字列 | アカウントのオンプレミスセキュリティ識別子 (SID) |
| `CloudSid` | 文字列 | アカウントのクラウド セキュリティ識別子 |
| `GivenName` | 文字列 | アカウント ユーザーの名前または名を指定する |
| `Surname` | 文字列 | アカウント ユーザーの姓、ファミリ名、または姓 |
| `AccountDisplayName` | 文字列 | アドレス帳に表示されるアカウント ユーザーの名前。 通常、指定または名、ミドル イニシエーション、姓または姓の組み合わせ。 |
| `Department` | 文字列 | アカウント ユーザーが属する部署の名前 |
| `JobTitle` | 文字列 | アカウント ユーザーの役職 |
| `AccountName` | 文字列 | アカウントのユーザー名 |
| `AccountDomain` | 文字列 | アカウントのドメイン |
| `EmailAddress` | 文字列 | アカウントの SMTP アドレス |
| `SipProxyAddress` | 文字列 | アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス |
| `City` | 文字列 | アカウント ユーザーが保存されている都市 |
| `Country` | 文字列 | アカウント ユーザーが保存されている国/地域 |
| `IsAccountEnabled` | boolean | アカウントが有効になっているかどうかを示します。 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
