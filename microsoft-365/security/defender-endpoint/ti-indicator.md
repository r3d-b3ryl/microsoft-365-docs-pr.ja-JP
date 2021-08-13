---
title: インジケーター リソースの種類
description: エンティティの詳細を指定し、Microsoft Defender for Endpoint を使用してインジケーターの有効期限を定義します。
keywords: apis, サポートされている api, get, TiIndicator, Indicator, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 836f3974da913dc27010cbc8d3162f35618e123e1c596dac42d9bf5e24863da3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817209"
---
# <a name="indicator-resource-type"></a>インジケーター リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- ポータルの対応 [する [インジケーター] ページ](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) を参照してください。 

メソッド|戻り値の型|説明
:---|:---|:---
[インジケーターの一覧表示](get-ti-indicators-collection.md)|[インジケーター](ti-indicator.md) コレクション|インジケーター [エンティティを](ti-indicator.md) 一覧表示します。
[インジケーターの送信](post-ti-indicator.md)|[インジケーター](ti-indicator.md)|Indicator エンティティを [送信または更新](ti-indicator.md) します。
[インジケーターのインポート](import-ti-indicators.md)|[インジケーター](ti-indicator.md) コレクション|インジケーター エンティティを [送信または](ti-indicator.md) 更新します。
[インジケーターの削除](delete-ti-indicator-by-id.md)|コンテンツはありません|Indicator エンティティ [を削除](ti-indicator.md) します。

## <a name="properties"></a>プロパティ

プロパティ|種類|説明
:---|:---|:---
id|String|Indicator エンティティ [の](ti-indicator.md) ID。
indicatorValue|String|Indicator の [値](ti-indicator.md)です。
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName" および "Url" です。
アプリケーション|String|インジケーターに関連付けられているアプリケーション。
action|列挙|インジケーターが組織内で検出される場合に実行されるアクション。 指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。
sourceType|列挙|"User" (ポータルからなど) ユーザーが作成したインジケーターの場合、API を介して自動アプリケーションを使用して送信された場合は "AadApp"。
source|string|インジケーターを送信したユーザー/アプリケーションの名前。
createdBy|String|インジケーターを送信したユーザー/アプリケーションの一意の ID。
lastUpdatedBy|String|インジケーターを最後に更新したユーザー/アプリケーションの ID。
creationTimeDateTimeUtc|DateTimeOffset|インジケーターが作成された日時。
expirationTime|DateTimeOffset|インジケーターの有効期限。
lastUpdateTime|DateTimeOffset|インジケーターが最後に更新された時刻。
severity|列挙|インジケーターの重大度。 指定できる値は、"Informational"、"Low"、"Medium"、"High" です。
title|String|インジケーター のタイトル。
description|String|インジケーターの説明。
recommendedActions|String|インジケーターの推奨アクション。
rbacGroupNames|文字列の一覧|インジケーターが公開され、アクティブな RBAC デバイス グループ名。 すべてのデバイスに公開されている場合の空のリスト。

## <a name="json-representation"></a>Json 表記

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
