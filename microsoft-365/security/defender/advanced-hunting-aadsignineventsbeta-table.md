---
title: 高度な検索スキーマの AADSignInEventsBeta テーブル
description: 高度なハンティング スキーマAzure Active Directoryサインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、Microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.openlocfilehash: 7fc5e0a37f57928b2ee1318d01e2a10b95a36108
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341666"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> この表は現在ベータ版で、短期的に提供され、Azure Active Directory (AAD) サインイン イベントを `AADSignInEventsBeta` ハントできます。 最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。

高度 `AADSignInEventsBeta` な検索スキーマの表には、対話型および非対話型Azure Active Directoryに関する情報が含まれている。詳細については、「サインイン アクティビティ レポート - プレビュー Azure Active Directory[サインイン」を参照してください](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。 高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。

<br>

****

|列名|データ型|説明|
|---|---|---|
|`Timestamp`|datetime|レコードが作成された日付と時刻|
|`Application`|文字列|記録されたアクションを実行したアプリケーション|
|`ApplicationId`|文字列|アプリケーションの一意の識別子|
|`LogonType`|文字列|ログオン セッションの種類 (特に対話型、リモート 対話型 (RDP)、ネットワーク、バッチ、およびサービス|
|`ErrorCode`|整数|サインイン エラーが発生した場合のエラー コードを格納します。 特定のエラー コードの説明を見つけるには、 を参照してください <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|文字列|サインイン イベントの一意の識別子|
|`SessionId`|文字列|訪問またはセッションの期間中、Web サイトのサーバーによってユーザーに割り当てられた一意の番号|
|`AccountDisplayName`|文字列|アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、ミドル イニシャル、姓または姓の組み合わせ。|
|`AccountObjectId`|文字列|Azure アカウントのアカウントの一意AD|
|`AccountUpn`|文字列|アカウントのユーザー プリンシパル名 (UPN)|
|`IsExternalUser`|整数|サインインしたユーザーが外部かどうかを示します。 指定できる値: -1 (設定されていない)、0 (外部ではない)、1 (外部)。|
|`IsGuestUser`|ブール値|サインインしたユーザーがテナントのゲストかどうかを示します。|
|`AlternateSignInName`|文字列|Azure サーバーにサインインするユーザーのオンプレミス ユーザー プリンシパル名 (UPN) AD|
|`LastPasswordChangeTimestamp`|日付型|最後にサインインしたユーザーがパスワードを変更した日時|
|`ResourceDisplayName`|文字列|アクセスされたリソースの表示名|
|`ResourceId`|文字列|アクセスされるリソースの一意の識別子|
|`ResourceTenantId`|文字列|アクセスされるリソースのテナントの一意の識別子|
|`DeviceName`|文字列|コンピューターの完全修飾ドメイン名 (FQDN)|
|`AadDeviceId`|文字列|Azure のデバイスの一意の識別子AD|
|`OSPlatform`|文字列|コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。|
|`DeviceTrustType`|string|サインインしたデバイスの信頼の種類を示します。 管理対象デバイスのシナリオの場合のみ。 使用できる値は、Workplace、AzureAd、および ServerAd です。|
|`IsManaged`|整数|サインインを開始したデバイスが管理対象デバイス (1) かどうか (0) を示します。|
|`IsCompliant`|整数|サインインを開始したデバイスが準拠 (1) か非準拠 (0) かを示します。|
|`AuthenticationProcessingDetails`|文字列|認証プロセッサの詳細|
|`AuthenticationRequirement`|文字列|サインインに必要な認証の種類。 指定できる値: multiFactorAuthentication (MFA が必要でした) と singleFactorAuthentication (MFA は必要ありません)。|
|`TokenIssuerType`|整数|トークン発行者が (0) Azure Active Directory Active Directory フェデレーション サービス (1) かどうかを示します。|
|`RiskLevelAggregated`|整数|サインイン中の集計されたリスク レベル。 指定できる値: 0 (集計リスク レベルが設定されていない)、1 (なし)、10 (低)、50 (中程度)、または 100 (高) です。|
|`RiskDetails`|整数|サインインしたユーザーの危険な状態の詳細|
|`RiskState`|整数|危険なユーザー状態を示します。 指定できる値は、0 (なし)、1 (安全確認済み)、2 (修復済み)、3 (却下)、4 (危険にさらされている)、または 5 (確認済み侵害) です。|
|`UserAgent`|文字列|Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報|
|`ClientAppUsed`|文字列|使用するクライアント アプリを示します。|
|`Browser`|文字列|サインインに使用するブラウザーのバージョンの詳細|
|`ConditionalAccessPolicies`|文字列|サインイン イベントに適用される条件付きアクセス ポリシーの詳細|
|`ConditionalAccessStatus`|整数|サインインに適用される条件付きアクセス ポリシーの状態。 指定できる値は、0 (適用されるポリシー)、1 (ポリシーの適用が失敗しました)、または 2 (ポリシーが適用されない) です。|
|`IPAddress`|文字列|エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス|
|`Country`|文字列|クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード|
|`State`|文字列|使用可能な場合は、サインインが発生した状態|
|`City`|文字列|アカウント ユーザーが保存されている都市|
|`Latitude`|文字列|サインイン場所の北から南の座標|
|`Longitude`|文字列|サインイン場所の東から西への座標|
|`NetworkLocationDetails`|文字列|サインイン イベントの認証プロセッサのネットワークの場所の詳細|
|`RequestId`|文字列|要求の一意の識別子|
|`ReportId`|文字列|イベントの一意識別子|

## <a name="related-articles"></a>関連記事

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
