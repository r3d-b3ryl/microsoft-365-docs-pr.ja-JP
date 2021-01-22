---
title: 高度な検索スキーマの IdentityInfo テーブル
description: 高度な検索スキーマの IdentityInfo テーブルのユーザー アカウント情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AccountInfo、IdentityInfo、アカウント
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
ms.openlocfilehash: 6604e6d48e277e840b87ddc461580bcb69dd1bc7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929912"
---
# <a name="identityinfo"></a>IdentityInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度 `IdentityInfo` な検索スキーマの [表](advanced-hunting-overview.md) には、Azure Active Directory など、さまざまなサービスから取得したユーザー アカウントに関する情報が含まれます。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

>[!NOTE]
>このテーブルの名前は、 `AccountInfo` . 名前を変更すると、ポータルに保存されたクエリはすべて自動的に更新されます。 別の場所に保存したクエリを確認します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `AccountObjectId` | string | Azure AD のアカウントの一意の識別子 |
| `AccountUpn` | string | アカウントのユーザー プリンシパル名 (UPN) |
| `OnPremSid` | string | アカウントのオンプレミス セキュリティ識別子 (SID) |
| `CloudSid` | string | アカウントのクラウド セキュリティ識別子 |
| `GivenName` | string | アカウント ユーザーの名前または名 |
| `Surname` | string | アカウント ユーザーの姓、ファミリ名、または姓 |
| `AccountDisplayName` | string | アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、ミドル ネームの開始、姓または姓の組み合わせ。 |
| `Department` | string | アカウント ユーザーが属する部署の名前 |
| `JobTitle` | string | アカウント ユーザーの役職 |
| `AccountName` | string | アカウントのユーザー名 |
| `AccountDomain` | string | アカウントのドメイン |
| `EmailAddress` | string | アカウントの SMTP アドレス |
| `SipProxyAddress` | string | アカウントのボイス オーバー IP (VOIP) セッション開始プロトコル (SIP) アドレス |
| `City` | string | アカウント ユーザーが位置する都市 |
| `Country` | string | アカウント ユーザーが位置する国/地域 |
| `IsAccountEnabled` | ブール値 | アカウントが有効かどうかを示します。 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
