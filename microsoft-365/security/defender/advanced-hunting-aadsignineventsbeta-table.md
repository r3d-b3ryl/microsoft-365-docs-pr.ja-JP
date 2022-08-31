---
title: 高度なハンティング スキーマの AADSignInEventsBeta テーブル
description: 高度なハンティング スキーマの Azure Active Directory サインイン イベント の表について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, ファイル, IP アドレス, デバイス, マシン, ユーザー, アカウント, ID, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: 90d275264c93736e1219488ecd4ae03e66a62af1
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67469143"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> この `AADSignInEventsBeta` テーブルは現在ベータ版であり、Azure Active Directory (AAD) のサインイン イベントを探索できるように、短期的に提供されています。 このテーブルのアクティビティを収集して表示するには、Azure Active Directory Premium P2 ライセンスが必要です。 すべてのサインイン スキーマ情報は、最終的にテーブルに `IdentityLogonEvents` 移動します。

`AADSignInEventsBeta`高度なハンティング スキーマの表には、Azure Active Directory の対話型サインインと非対話型サインインに関する情報が含まれています。[Azure Active Directory サインイン アクティビティ レポート - プレビューのサインイン](/azure/active-directory/reports-monitoring/concept-all-sign-ins)の詳細について説明します。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。 高度なハンティング スキーマの他のテーブルについては、 [高度なハンティング リファレンスを参照してください](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)。

<br>

****

|列名|データ型|説明|
|---|---|---|
|`Timestamp`|`datetime`|レコードが作成された日付と時刻|
|`Application`|`string`|記録されたアクションを実行したアプリケーション|
|`ApplicationId`|`string`|アプリケーションの一意の識別子|
|`LogonType`|`string`|ログオン セッションの種類、対話型、リモート 対話型 (RDP)、ネットワーク、バッチ、およびサービス|
|`ErrorCode`|`int`|サインイン エラーが発生した場合のエラー コードを含みます。 特定のエラー コードの説明を見つけるには、次のページを参照してください <https://aka.ms/AADsigninsErrorCodes>。|
|`CorrelationId`|`string`|サインイン イベントの一意識別子|
|`SessionId`|`string`|アクセスまたはセッション中に Web サイトのサーバーによってユーザーに割り当てられた一意の番号|
|`AccountDisplayName`|`string`|アドレス帳に表示されるアカウント ユーザーの名前。 通常、特定の名前または名、中間の頭文字、姓または姓の組み合わせ。|
|`AccountObjectId`|`string`|Azure AD のアカウントの一意識別子|
|`AccountUpn`|`string`|アカウントのユーザー プリンシパル名 (UPN)|
|`IsExternalUser`|`int`|サインインしたユーザーが外部かどうかを示します。 指定できる値: -1 (未設定)、0 (外部ではない)、1 (外部)。|
|`IsGuestUser`|`boolean`|サインインしたユーザーがテナント内のゲストであるかどうかを示します|
|`AlternateSignInName`|`string`|Azure AD にサインインするユーザーのオンプレミス ユーザー プリンシパル名 (UPN)|
|`LastPasswordChangeTimestamp`|`datetime`|サインインしたユーザーが最後にパスワードを変更した日時|
|`ResourceDisplayName`|`string`|アクセスされたリソースの表示名|
|`ResourceId`|`string`|アクセスされたリソースの一意の識別子|
|`ResourceTenantId`|`string`|アクセスされたリソースのテナントの一意の識別子|
|`DeviceName`|`string`|コンピューターの完全修飾ドメイン名 (FQDN)|
|`AadDeviceId`|`string`|Azure AD のデバイスの一意の識別子|
|`OSPlatform`|`string`|コンピューターで実行されているオペレーティング システムのプラットフォームです。 Windows 11、Windows 10、Windows 7 など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。|
|`DeviceTrustType`|`string`|サインインしたデバイスの信頼の種類を示します。 マネージド デバイスのシナリオの場合のみ。 使用可能な値は Workplace、AzureAd、ServerAd です。|
|`IsManaged`|`int`|サインインを開始したデバイスがマネージド デバイス (1) であるかどうかを示します。マネージド デバイス (0)|
|`IsCompliant`|`int`|サインインを開始したデバイスが準拠 (1) か非準拠 (0) かを示します。|
|`AuthenticationProcessingDetails`|`string`|認証プロセッサの詳細|
|`AuthenticationRequirement`|`string`|サインインに必要な認証の種類。 可能な値: multiFactorAuthentication (MFA が必要でした) と singleFactorAuthentication (MFA は必要ありませんでした)。|
|`TokenIssuerType`|`int`|トークン発行者が Azure Active Directory (0) であるか、Active Directory フェデレーション サービス (AD FS) (1) であるかどうかを示します。|
|`RiskLevelAggregated`|`int`|サインイン中の集計されたリスク レベル。 可能な値: 0 (集計されたリスク レベルは設定されていません)、1 (なし)、10 (低)、50 (中)、または 100 (高)。|
|`RiskDetails`|`int`|サインインしたユーザーの危険な状態に関する詳細|
|`RiskState`|`int`|危険なユーザー状態を示します。 可能な値: 0 (なし)、1 (安全であることが確認済み)、2 (修復済み)、3 (却下)、4 (リスクあり)、または 5 (侵害が確認されました)。|
|`UserAgent`|`string`|Web ブラウザーまたはその他のクライアント アプリケーションからのユーザー エージェント情報|
|`ClientAppUsed`|`string`|使用されているクライアント アプリを示します|
|`Browser`|`string`|サインインに使用されるブラウザーのバージョンに関する詳細|
|`ConditionalAccessPolicies`|`string`|サインイン イベントに適用される条件付きアクセス ポリシーの詳細|
|`ConditionalAccessStatus`|`int`|サインインに適用される条件付きアクセス ポリシーの状態。 指定できる値は 0 (適用されたポリシー)、1 (ポリシーの適用に失敗しました)、または 2 (ポリシーが適用されていません) です。|
|`IPAddress`|`string`|エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス|
|`Country`|`string`|クライアント IP アドレスが地理的に割り当てられた国を示す 2 文字のコード|
|`State`|`string`|サインインが発生した状態 (使用可能な場合)|
|`City`|`string`|アカウント ユーザーが配置されている市区町村|
|`Latitude`|`string`|サインイン場所の北から南の座標|
|`Longitude`|`string`|サインイン場所の東から西の座標|
|`NetworkLocationDetails`|`string`|サインイン イベントの認証プロセッサのネットワークの場所の詳細|
|`RequestId`|`string`|要求の一意の識別子|
|`ReportId`|`string`|イベントの一意識別子|

## <a name="related-articles"></a>関連記事

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
