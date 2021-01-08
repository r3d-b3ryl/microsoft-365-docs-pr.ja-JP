---
title: 高度な検索スキーマの AADSpnSignInEventsBeta テーブル
description: 高度な検索スキーマの Azure Active Directory サービス プリンシパルと管理対象 ID サインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、列、データ型、説明、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 42acf24ce9b941fffb1ce0ed4b67216bd8c1de47
ms.sourcegitcommit: 4482c174e0e68e0fbbc7ad9ef6b0e78dc34ac85a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2021
ms.locfileid: "49784301"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**適用対象:**

- Microsoft 365 Defender

>[!IMPORTANT]
> このテーブルは現在ベータ版であり `AADSpnSignInEventsBeta` 、Azure Active Directory (AAD) サービス プリンシパルとマネージ ID サインイン イベントをハントするために、短期的に提供されています。 最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。<br><br>
> Azure Security Center の統合 Microsoft Defender for Endpoint ソリューションを通じて Microsoft 365 Defender にアクセスできるが、Office 用 Microsoft Defender、Id 用 Microsoft Defender、または Microsoft Cloud App Security のライセンスを持ってないお客様は、このスキーマを表示できません。 



高度 `AADSpnSignInEventsBeta` な検索スキーマの表には、Azure Active Directory サービス プリンシパルとマネージ ID サインインに関する情報が含まれます。さまざまな種類のサインインの詳細については、Azure Active Directory サインイン アクティビティ [レポートのプレビューを参照してください](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。





| 列名     | データ型 | 説明   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | レコードが作成された日付と時刻                                                                                                     |
| `Application`          | 文字列        | 記録されたアクションを実行したアプリケーション                                                                                                   |
| `ApplicationId`        | string        | アプリケーションの一意識別子                                                                                                           |
| `IsManagedIdentity`    | ブール値       | サインインが管理 ID によって開始されたかどうかを示します                                                                               |
| `ErrorCode`            | int        | サインイン エラーが発生した場合のエラー コードを含む。 特定のエラー コードの説明を見つけるには、次のページを参照してください <https://aka.ms/AADsigninsErrorCodes> 。 |
| `CorrelationId`        | string        | サインイン イベントの一意識別子                                                                                                          |
| `ServicePrincipalName` | string        | サインインを開始したサービス プリンシパルの名前                                                                                        |
| `ServicePrincipalId`   | string        | サインインを開始したサービス プリンシパルの一意の識別子                                                                           |
| `ResourceDisplayName`  | string        | アクセスされたリソースの表示名                                                                                                           |
| `ResourceId`           | string        | アクセスされるリソースの一意の識別子                                                                                                      |
| `ResourceTenantId`     | string        | アクセスされたリソースのテナントの一意の識別子                                                                                        |
| `IPAddress`            | string        | エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス                                                              |
| `CountryCode`          | string        | クライアント IP アドレスが地理的に位置する国を示す 2 文字のコード                                                                |
| `State`                | string        | サインインが発生した状態 (使用可能な場合)                                                                                                  |
| `City`                 | string        | アカウント ユーザーが位置する市区町町ラ                                                                                                          |
| `Latitude`             | string        | サインイン場所の北から南の座標                                                                                          |
| `Longitude`            | string        | サインイン位置の東から西への座標                                                                                            |
| `RequestId`            | string        | 要求の一意識別子                                                                                                                |
|`ReportId` | string | イベントの一意識別子 | 

 

## <a name="related-articles"></a>関連記事

-   [AADSignInEventsBeta](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-aadsignineventsbeta-table)
-   [高度な検出の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [クエリ言語の説明](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [スキーマを理解する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)

