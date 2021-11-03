---
title: 高度なハンティング スキーマの AADSpnSignInEventsBeta テーブル
description: 高度なハンティング スキーマの Azure Active Directory サービス プリンシパルおよびマネージ ID サインイン イベント テーブルに関連付けられている情報について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、AlertInfo、アラート、エンティティ、証拠、ファイル、IP アドレス、デバイス、コンピューター、ユーザー、アカウント、ID、AAD
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: acae853032be246184b4f74f83d308fbde1d43b5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667074"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> このテーブルは現在ベータ版で、Azure Active Directory (AAD) サインイン イベントをハントするために、短期的に `AADSpnSignInEventsBeta` 提供されています。 このテーブルのアクティビティを収集Azure Active Directory Premium P2表示するには、ユーザーライセンスが必要です。 最終的に、すべてのサインイン スキーマ情報をテーブルに移動 `IdentityLogonEvents` します。

高度 `AADSpnSignInEventsBeta` な検索スキーマの表には、サービス プリンシパルAzure Active Directoryマネージド ID サインインに関する情報が含まれている。さまざまな種類のサインインの詳細については、「Azure Active Directoryアクティビティ レポート - プレビュー」を[参照してください](/azure/active-directory/reports-monitoring/concept-all-sign-ins)。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。

<br>

****

|列名|データ型|説明|
|---|---|---|
|`Timestamp`|datetime|レコードが作成された日付と時刻|
|`Application`|文字列|記録されたアクションを実行したアプリケーション|
|`ApplicationId`|string|アプリケーションの一意の識別子|
|`IsManagedIdentity`|ブール値|マネージ ID によってサインインが開始されたかどうかを示します。|
|`ErrorCode`|int|サインイン エラーが発生した場合のエラー コードを格納します。 特定のエラー コードの説明を見つけるには、 を参照してください <https://aka.ms/AADsigninsErrorCodes> 。|
|`CorrelationId`|string|サインイン イベントの一意の識別子|
|`ServicePrincipalName`|string|サインインを開始したサービス プリンシパルの名前|
|`ServicePrincipalId`|string|サインインを開始したサービス プリンシパルの一意の識別子|
|`ResourceDisplayName`|string|アクセスされたリソースの表示名|
|`ResourceId`|string|アクセスされるリソースの一意の識別子|
|`ResourceTenantId`|string|アクセスされるリソースのテナントの一意の識別子|
|`IPAddress`|string|エンドポイントに割り当て、関連するネットワーク通信中に使用される IP アドレス|
|`Country`|string|クライアント IP アドレスが地理的に位置付けされている国を示す 2 文字のコード|
|`State`|string|使用可能な場合は、サインインが発生した状態|
|`City`|string|アカウント ユーザーが保存されている都市|
|`Latitude`|string|サインイン場所の北から南の座標|
|`Longitude`|string|サインイン場所の東から西への座標|
|`RequestId`|string|要求の一意の識別子|
|`ReportId`|string|イベントの一意識別子|
||||

## <a name="related-articles"></a>関連記事

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
