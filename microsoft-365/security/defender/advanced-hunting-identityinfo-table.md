---
title: 高度なハンティング スキーマの IdentityInfo テーブル
description: 高度なハンティング スキーマの IdentityInfo テーブルでユーザー アカウント情報について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, AccountInfo, IdentityInfo, account
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b09d1774ab35dbca9119deb98864d6c6f78051a9
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531437"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

`IdentityInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Azure Active Directoryを含むさまざまなサービスから取得されたユーザー アカウントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!NOTE]
>このテーブルの名前が .`AccountInfo` 名前の変更中に、ポータルに保存されたすべてのクエリが自動的に更新されます。 他の場所に保存したクエリを確認します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `AccountObjectId` | `string` | Azure ADのアカウントの一意識別子 |
| `AccountUpn` | `string` | アカウントのユーザー プリンシパル名 (UPN) |
| `OnPremSid` | `string` | アカウントのオンプレミス セキュリティ識別子 (SID) |
| `CloudSid` | `string` | アカウントのクラウド セキュリティ識別子 |
| `GivenName` | `string` | アカウント ユーザーの指定された名前または名 |
| `Surname` | `string` | アカウント ユーザーの姓、姓、または姓 |
| `AccountDisplayName` | `string` | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の開始、姓または姓の組み合わせ。 |
| `Department` | `string` | アカウント ユーザーが属している部署の名前 |
| `JobTitle` | `string` | アカウント ユーザーの役職 |
| `AccountName` | `string` | アカウントのユーザー名 |
| `AccountDomain` | `string` | アカウントのドメイン |
| `EmailAddress` | `string` | アカウントの SMTP アドレス |
| `SipProxyAddress` | `string` | アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス |
| `City` | `string` | アカウント ユーザーが配置されている市区町村 |
| `Country` | `string` | アカウント ユーザーが配置されている国/地域 |
| `IsAccountEnabled` | `boolean` | アカウントが有効かどうかを示します |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
