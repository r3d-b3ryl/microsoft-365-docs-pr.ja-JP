---
title: 高度な検索スキーマの AADSignInEventsBeta テーブル
description: 高度な検索スキーマの Azure Active Directory サインイン イベント テーブルに関連する情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 174db150920d2d95c043bb5d6e5a4593ea1ea39d
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145429"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

>[!IMPORTANT]
> この `AADSignInEventsBeta` テーブルは現在ベータ版であり、Azure Active Directory (AAD) サインイン イベントをハントするために短期で提供されています。 最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。<br><br>
> Azure Security Center の統合 Microsoft Defender for Endpoint ソリューションを通じて Microsoft 365 Defender にアクセスできるが、Office 用 Microsoft Defender、Id 用 Microsoft Defender、または Microsoft Cloud App Security のライセンスを持ってないお客様は、このスキーマを表示できません。 

 

高度 `AADSignInEventsBeta` な検索スキーマの表には、Azure Active Directory 対話型サインインと非対話型サインインに関する情報が含まれます。Azure Active Directory サインイン アクティビティ レポートのサインインの詳細については [、「プレビュー」を参照してください](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。
高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。

 

 

| 列名                 | データ型 | 説明          |
|---------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Timestamp`                       | datetime      | レコードが作成された日付と時刻                                                                                                                                         |
| `Application`                     | 文字列        | 記録されたアクションを実行したアプリケーション                                                                                                                                       |
| `ApplicationId`                   | string        | アプリケーションの一意識別子                                                                                                                                               |
| `LogonType`                       | string        | ログオン セッションの種類(具体的には対話型、リモート 対話型 (RDP)、ネットワーク、バッチ、およびサービス                                                                              |
| `ErrorCode`                       | int        | サインイン エラーが発生した場合のエラー コードを含む。 特定のエラー コードの説明を見つけるには、次のページを参照してください <https://aka.ms/AADsigninsErrorCodes> 。                                     |
| `CorrelationId`                   | string        | サインイン イベントの一意識別子                                                                                                                                              |
| `SessionId`                       | string        | 訪問またはセッション中に Web サイトのサーバーによってユーザーに割り当てられた一意の番号                                                                                     |
| `AccountDisplayName`              | string        | アドレス帳に表示されるアカウント ユーザーの名前。 通常は、名、ミドル ネームのイニシャル、姓または姓の組み合わせです。                             |
| `AccountObjectId`                 | string        | Azure AD のアカウントの一意の識別子                                                                                                                                       |
| `AccountUpn`                      | string        | アカウントのユーザー プリンシパル名 (UPN)                                                                                                                                            |
| `IsExternalUser`                  | int        | サインインしたユーザーが外部ユーザーかどうかを示します。 指定可能な値: -1 (設定しない)、0 (外部ではない)、1 (外部)。                                                                   |
| `IsGuestUser`                     | boolean       | サインインしたユーザーがテナントのゲストかどうかを示します                                                                                                                  |
| `AlternateSignInName`             | string        | Azure アカウントにサインインするユーザーのオンプレミスのユーザー プリンシパル名 (UPN) AD                                                                                                            |
| `LastPasswordChangeTimestamp`     | 日付型        | 最後にサインインしたユーザーがパスワードを変更した日時                                                                                                              |
| `ResourceDisplayName`             | string        | アクセスされたリソースの表示名                                                                                                                                               |
| `ResourceId`                      | string        | アクセスされたリソースの一意の識別子                                                                                                                                          |
| `ResourceTenantId`                | string        | アクセスされたリソースのテナントの一意の識別子                                                                                                                            |
| `DeviceName`                      | string        | コンピューターの完全修飾ドメイン名 (FQDN)                                                                                                                                   |
| `AadDeviceId`                     | string   |      Azure AD のデバイスの一意の識別子                                                                                                                                                                               |
| `OSPlatform`                      | string        | コンピューターで実行されているオペレーティング システムのプラットフォームです。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。  |
| `DeviceTrustType`                 | string        | サインインしたデバイスの信頼の種類を示します。 管理対象デバイスのシナリオの場合のみ。 有効な値は、Workplace、AzureAd、ServerAd です。                                     |
| `IsManaged`                       | int       | サインインを開始したデバイスが管理対象デバイス (1) か、管理対象デバイスではないかを示します (0)                                                                         |
| `IsCompliant`                     | int       | サインインを開始したデバイスが準拠 (1) か非準拠 (0) かを示します。                                                                                       |
| `AuthenticationProcessingDetails` | string        | 認証プロセッサの詳細                                                                                                                                          |
| `AuthenticationRequirement`       | string        | サインインに必要な認証の種類。 可能な値: multiFactorAuthentication (MFA が必要でした) と singleFactorAuthentication (MFA は必要ありません)。                |
| `TokenIssuerType`                 | int        | トークン発行者が Azure Active Directory (0) または Active Directory フェデレーション サービス (1) かどうかを示します。                                                                             |
| `RiskLevelAggregated`                       | int        | サインイン中の集計されたリスク レベル。 指定できる値は、0 (集計リスク レベルが設定されていない)、1 (なし)、10 (低)、50 (中)、または 100 (高) です。                               |
| `RiskDetails`                      | int        | サインインしたユーザーの危険な状態に関する詳細                                                                                                                            |
| `RiskState`                       | int        | 危険なユーザー状態を示します。 指定可能な値は、0 (なし)、1 (安全確認済み)、2 (修復済み)、3 (却下)、4 (危険な場合)、または 5 (侵害が確認済み) です。                                |
| `UserAgent`                       | string        | Web ブラウザーまたは他のクライアント アプリケーションからのユーザー エージェント情報                                                                                                             |
| `ClientAppUsed`                   | string        | 使用されているクライアント アプリを示します。                                                                                                                                                       |
| `Browser`                         | string        | サインインに使用されるブラウザーのバージョンに関する詳細                                                                                                                            |
| `ConditionalAccessPolicies`       | string        | サインイン イベントに適用される条件付きアクセス ポリシーの詳細                                                                                                             |
| `ConditionalAccessStatus`         | int        | サインインに適用される条件付きアクセス ポリシーの状態。 指定できる値は、0 (ポリシーが適用)、1 (ポリシーの適用が失敗)、または 2 (ポリシーが適用されない) です。      |
| `IPAddress`                       | string        | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス                                                                                                  |
| `Country`                     | string        | クライアント IP アドレスが地理的に位置する国を示す 2 文字のコード                                                                                                    |
| `State`                           | string        | サインインが発生した状態 (使用可能な場合)                                                                                                                                      |
| `City`                            | string        | アカウント ユーザーが位置する市区町町ラ                                                                                                                                              |
| `Latitude`                        | string        | サインイン位置の北から南の座標                                                                                                                              |
| `Longitude`                       | string        | サインイン位置の東から西の座標                                                                                                                                |
| `NetworkLocationDetails`          | string        | サインイン イベントの認証プロセッサのネットワークの場所の詳細                                                                                                       |
| `RequestId`                       | string        |  要求の一意識別子                                                                                                                                                   |
|`ReportId` | string | イベントの一意識別子 |

 

 

## <a name="related-articles"></a>関連記事

-   [AADSpnSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadspnsignineventsbeta-table)
-   [高度な検出の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [クエリ言語の説明](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [スキーマを理解する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

 
