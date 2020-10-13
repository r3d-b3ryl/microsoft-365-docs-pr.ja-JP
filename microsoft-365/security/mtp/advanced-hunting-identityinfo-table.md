---
title: 高度な検索スキーマの [情報] テーブル
description: 高度な検索スキーマの id 情報の表にあるユーザーアカウント情報について説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検出、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AccountInfo、identity Info、account
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
ms.openlocfilehash: 38a7e6600c682b1edef5320ef4de296b5943952d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430481"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection

`IdentityInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Azure Active Directory などのさまざまなサービスから取得したユーザーアカウントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!NOTE]
>このテーブルはから名前が変更されました `AccountInfo` 。 名前を変更すると、ポータルに保存されているすべてのクエリが自動的に更新されます。 他の場所に保存されたクエリをチェックします。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure AD でのアカウントの一意識別子 |
| `AccountUpn` | string | アカウントのユーザープリンシパル名 (UPN) |
| `OnPremSid` | string | アカウントの社内セキュリティ識別子 (SID) |
| `CloudSid` | string | アカウントのクラウドセキュリティ識別子 |
| `GivenName` | string | アカウントユーザーの名前または名を指定します。 |
| `Surname` | string | アカウントユーザーの姓、家族名、または姓 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウントユーザーの名前。 通常、指定された名前または名、ミドルネーム、姓の組み合わせです。 |
| `Department` | string | アカウントユーザーが属する部署の名前 |
| `JobTitle` | string | アカウントユーザーの役職 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `EmailAddress` | string | アカウントの SMTP アドレス |
| `SipProxyAddress` | string | アカウントのボイスオーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス |
| `City` | string | アカウントユーザーが配置されている市区町村 |
| `Country` | string | アカウントユーザーが配置されている国/地域 |
| `IsAccountEnabled` | ブール値 | アカウントが有効であるかどうかを示します |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
