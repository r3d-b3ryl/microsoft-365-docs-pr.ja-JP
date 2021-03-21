---
title: 高度なハンティング スキーマの AADSpnSignInEventsBeta テーブル
description: 高度なハンティング スキーマの Azure Active Directory サービス プリンシパルとマネージ ID サインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、description、Description、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.openlocfilehash: 5050f4f91d61369e927eae15ca7c156a17792c24
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924542"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

>[!IMPORTANT]
> この表は現在ベータ版で `AADSpnSignInEventsBeta` 、Azure Active Directory (AAD) サービス プリンシパルおよびマネージ ID サインイン イベントをハントするために、短期的に提供されています。 最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。<br><br>
> Azure Security Center の統合された Microsoft Defender for Endpoint ソリューションを通じて Microsoft 365 Defender にアクセスできますが、microsoft Defender for Office、Microsoft Defender for Identity、または Microsoft Cloud App Security のライセンスを持ってないお客様は、このスキーマを表示できません。 



高度 `AADSpnSignInEventsBeta` な検索スキーマの表には、Azure Active Directory サービス プリンシパルとマネージ ID サインインに関する情報が含まれます。さまざまな種類のサインインの詳細については、「Azure Active Directory サインイン アクティビティ レポート - プレビュー」 [を参照してください](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。





| 列名     | データ型 | 説明   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | レコードが作成された日付と時刻                                                                                                     |
| `Application`          | 文字列        | 記録されたアクションを実行したアプリケーション                                                                                                   |
| `ApplicationId`        | string        | アプリケーションの一意の識別子                                                                                                           |
| `IsManagedIdentity`    | boolean       | マネージ ID によってサインインが開始されたかどうかを示します。                                                                               |
| `ErrorCode`            | int        | サインイン エラーが発生した場合のエラー コードを格納します。 特定のエラー コードの説明を見つけるには、 を参照してください <https://aka.ms/AADsigninsErrorCodes> 。 |
| `CorrelationId`        | string        | サインイン イベントの一意の識別子                                                                                                          |
| `ServicePrincipalName` | string        | サインインを開始したサービス プリンシパルの名前                                                                                        |
| `ServicePrincipalId`   | string        | サインインを開始したサービス プリンシパルの一意の識別子                                                                           |
| `ResourceDisplayName`  | string        | アクセスされたリソースの表示名                                                                                                           |
| `ResourceId`           | string        | アクセスされるリソースの一意の識別子                                                                                                      |
| `ResourceTenantId`     | string        | アクセスされるリソースのテナントの一意の識別子                                                                                        |
| `IPAddress`            | string        | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス                                                              |
| `Country`          | string        | クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード                                                                |
| `State`                | string        | 使用可能な場合は、サインインが発生した状態                                                                                                  |
| `City`                 | string        | アカウント ユーザーが保存されている都市                                                                                                          |
| `Latitude`             | string        | サインイン場所の北から南の座標                                                                                          |
| `Longitude`            | string        | サインイン場所の東から西への座標                                                                                            |
| `RequestId`            | string        | 要求の一意の識別子                                                                                                                |
|`ReportId` | string | イベントの一意識別子 | 

 

## <a name="related-articles"></a>関連記事

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [高度な検出の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)