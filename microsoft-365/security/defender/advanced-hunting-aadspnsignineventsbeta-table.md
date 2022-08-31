---
title: 高度なハンティング スキーマの AADSpnSignInEventsBeta テーブル
description: Azure Active Directory のサービス プリンシパルとマネージド ID サインイン イベントテーブルに関連付けられている情報について説明します。
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 74e8ff6319799da8e9893a65b447a8e3c693cd8f
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67472944"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> この `AADSpnSignInEventsBeta` テーブルは現在ベータ版であり、Azure Active Directory (AAD) のサインイン イベントを探索できるように、短期的に提供されています。 このテーブルのアクティビティを収集して表示するには、Azure Active Directory Premium P2 ライセンスが必要です。 Microsoft は最終的にすべてのサインイン スキーマ情報をテーブルに `IdentityLogonEvents` 移動します。

`AADSpnSignInEventsBeta`高度なハンティング スキーマの表には、Azure Active Directory サービス プリンシパルとマネージド ID サインインに関する情報が含まれています。[Azure Active Directory サインイン アクティビティ レポート - プレビュー](/azure/active-directory/reports-monitoring/concept-all-sign-ins)では、さまざまな種類のサインインの詳細を確認できます。

このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)」 を参照してください。

<br>

****

|列名|データ型|説明|
|---|---|---|
|`Timestamp`|`datetime`|レコードが作成された日付と時刻|
|`Application`|`string`|記録されたアクションを実行したアプリケーション|
|`ApplicationId`|`string`|アプリケーションの一意の識別子|
|`IsManagedIdentity`|`boolean`|マネージド ID によってサインインが開始されたかどうかを示します。|
|`ErrorCode`|`int`|サインイン エラーが発生した場合のエラー コードを含みます。 特定のエラー コードの説明を見つけるには、次のページを参照してください <https://aka.ms/AADsigninsErrorCodes>。|
|`CorrelationId`|`string`|サインイン イベントの一意識別子|
|`ServicePrincipalName`|`string`|サインインを開始したサービス プリンシパルの名前|
|`ServicePrincipalId`|`string`|サインインを開始したサービス プリンシパルの一意の識別子|
|`ResourceDisplayName`|`string`|アクセスされたリソースの表示名|
|`ResourceId`|`string`|アクセスされたリソースの一意の識別子|
|`ResourceTenantId`|`string`|アクセスされたリソースのテナントの一意の識別子|
|`IPAddress`|`string`|エンドポイントに割り当てられ、関連するネットワーク通信中に使用される IP アドレス|
|`Country`|`string`|クライアント IP アドレスが地理的に割り当てられた国を示す 2 文字のコード|
|`State`|`string`|サインインが発生した状態 (使用可能な場合)|
|`City`|`string`|アカウント ユーザーが配置されている市区町村|
|`Latitude`|`string`|サインイン場所の北から南の座標|
|`Longitude`|`string`|サインイン場所の東から西の座標|
|`RequestId`|`string`|要求の一意の識別子|
|`ReportId`|`string`|イベントの一意識別子|
||||

## <a name="related-articles"></a>関連記事

- [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
- [高度な追求の概要](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [クエリ言語の説明](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [スキーマを理解する](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
