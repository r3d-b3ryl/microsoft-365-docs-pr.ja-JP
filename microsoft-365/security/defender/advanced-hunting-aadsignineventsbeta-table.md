---
title: 高度な検索スキーマの AADSignInEventsBeta テーブル
description: 高度な狩Azure Active Directoryスキーマの [サインイン イベント] テーブルについて説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、file、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.openlocfilehash: dad3ea9fe4297d93864032130e3f6d6b5f6e4e82
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074620"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> このテーブルは現在ベータ版で、Azure Active Directory (AAD) サインイン イベントをハントするために、短期的に `AADSignInEventsBeta` 提供されています。 このテーブルのアクティビティを収集Azure Active Directory Premium P2表示するには、ユーザーライセンスが必要です。 すべてのサインイン スキーマ情報は、最終的にテーブルに移動 `IdentityLogonEvents` します。

高度 `AADSignInEventsBeta` な検索スキーマの表には、対話型および非対話型Azure Active Directoryに関する情報が含まれている。詳細については、「サインイン アクティビティ レポート - プレビュー Azure Active Directory[サインイン」を参照してください](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。 高度な検索スキーマの他のテーブルの詳細については、高度な検索 [リファレンスを参照してください](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。

<br>

****

|列名|データ型|説明|
|---|---|---|
|`Timestamp`|`datetime`|レコードが作成された日付と時刻|
|`Application`|`string`|記録されたアクションを実行したアプリケーション|
|`ApplicationId`|`string`|アプリケーションの一意の識別子|
|`LogonType`|`string`|ログオン セッションの種類、対話型、リモート 対話型 (RDP)、ネットワーク、バッチ、およびサービス|
|`ErrorCode`|`int`|サインイン エラーが発生した場合のエラー コードを格納します。 特定のエラー コードの説明を見つけるには、 を参照してください <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|`string`|サインイン イベントの一意の識別子|
|`SessionId`|`string`|訪問またはセッション中に Web サイトのサーバーによってユーザーに割り当てられた一意の番号|
|`AccountDisplayName`|`string`|アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、ミドル イニシャル、姓または姓の組み合わせ。|
|`AccountObjectId`|`string`|アカウントの一意の識別子は、Azure AD|
|`AccountUpn`|`string`|アカウントのユーザー プリンシパル名 (UPN)|
|`IsExternalUser`|`int`|サインインしたユーザーが外部かどうかを示します。 指定できる値: -1 (設定されていない)、0 (外部ではない)、1 (外部)。|
|`IsGuestUser`|`boolean`|サインインしたユーザーがテナントのゲストかどうかを示します。|
|`AlternateSignInName`|`string`|ユーザーがユーザーにサインインするオンプレミスのユーザー プリンシパル名 (UPN) Azure AD|
|`LastPasswordChangeTimestamp`|`datetime`|最後にサインインしたユーザーがパスワードを変更した日時|
|`ResourceDisplayName`|`string`|アクセスされたリソースの表示名|
|`ResourceId`|`string`|アクセスされるリソースの一意の識別子|
|`ResourceTenantId`|`string`|アクセスされるリソースのテナントの一意の識別子|
|`DeviceName`|`string`|コンピューターの完全修飾ドメイン名 (FQDN)|
|`AadDeviceId`|`string`|ネットワーク内のデバイスの一意Azure AD|
|`OSPlatform`|`string`|コンピューターで実行されているオペレーティング システムのプラットフォームです。 11、Windows Windows 10、および 7 など、同じファミリ内Windows 10オペレーティング システムWindows示します。|
|`DeviceTrustType`|`string`|サインインしたデバイスの信頼の種類を示します。 管理対象デバイスのシナリオの場合のみ。 使用できる値は、Workplace、AzureAd、および ServerAd です。|
|`IsManaged`|`int`|サインインを開始したデバイスが管理対象デバイス (1) かどうか (0) を示します。|
|`IsCompliant`|`int`|サインインを開始したデバイスが準拠 (1) か非準拠 (0) かを示します。|
|`AuthenticationProcessingDetails`|`string`|認証プロセッサの詳細|
|`AuthenticationRequirement`|`string`|サインインに必要な認証の種類。 指定できる値: multiFactorAuthentication (MFA が必要でした) と singleFactorAuthentication (MFA は必要ありません)。|
|`TokenIssuerType`|`int`|トークン発行者が (0) Azure Active Directory Active Directory フェデレーション サービス (1) かどうかを示します。|
|`RiskLevelAggregated`|`int`|サインイン中の集計されたリスク レベル。 指定できる値: 0 (集計リスク レベルが設定されていない)、1 (なし)、10 (低)、50 (中程度)、または 100 (高) です。|
|`RiskDetails`|`int`|サインインしたユーザーの危険な状態の詳細|
|`RiskState`|`int`|危険なユーザー状態を示します。 指定できる値は、0 (なし)、1 (安全確認済み)、2 (修復済み)、3 (却下)、4 (危険にさらされている)、または 5 (確認済み侵害) です。|
|`UserAgent`|`string`|Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報|
|`ClientAppUsed`|`string`|使用するクライアント アプリを示します。|
|`Browser`|`string`|サインインに使用するブラウザーのバージョンの詳細|
|`ConditionalAccessPolicies`|`string`|サインイン イベントに適用される条件付きアクセス ポリシーの詳細|
|`ConditionalAccessStatus`|`int`|サインインに適用される条件付きアクセス ポリシーの状態。 指定できる値は、0 (適用されるポリシー)、1 (ポリシーの適用が失敗しました)、または 2 (ポリシーが適用されない) です。|
|`IPAddress`|`string`|エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス|
|`Country`|`string`|クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード|
|`State`|`string`|使用可能な場合は、サインインが発生した状態|
|`City`|`string`|アカウント ユーザーが保存されている都市|
|`Latitude`|`string`|サインイン場所の北から南の座標|
|`Longitude`|`string`|サインイン場所の東から西への座標|
|`NetworkLocationDetails`|`string`|サインイン イベントの認証プロセッサのネットワークの場所の詳細|
|`RequestId`|`string`|要求の一意の識別子|
|`ReportId`|`string`|イベントの一意識別子|

## <a name="related-articles"></a>関連記事

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
