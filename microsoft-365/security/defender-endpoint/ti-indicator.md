---
title: インジケーター リソースの種類
description: エンティティの詳細を指定し、Microsoft Defender for Endpointを使用してインジケーターの有効期限を定義します。
keywords: apis, サポートされている API, get, TiIndicator, Indicator, recent
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: dcdba63fe99d092f2ce6a9839a94f5e4c297ee66
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67330765"
---
# <a name="indicator-resource-type"></a>インジケーター リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

- ポータルの対応する [インジケーター ページ](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) を参照してください。

メソッド|戻り値の型|説明
:---|:---|:---
[インジケーターの一覧表示](get-ti-indicators-collection.md)|[インジケーター](ti-indicator.md) コレクション|[インジケーター](ti-indicator.md) エンティティを一覧表示します。
[インジケーターの送信](post-ti-indicator.md)|[インジケーター](ti-indicator.md)|[Indicator](ti-indicator.md) エンティティを送信または更新します。
[インジケーターのインポート](import-ti-indicators.md)|[インジケーター](ti-indicator.md) コレクション|[Indicators エンティティを](ti-indicator.md)送信または更新します。
[インジケーターの削除](delete-ti-indicator-by-id.md)|コンテンツはありません|[インジケーター](ti-indicator.md) エンティティを削除します。

## <a name="properties"></a>プロパティ

プロパティ|種類|説明
:---|:---|:---
id|文字列|[インジケーター](ti-indicator.md) エンティティの ID。
indicatorValue|文字列|[インジケーター](ti-indicator.md)の値。
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileSha256"、"FileMd5"、"CertificateThumbprint"、"IpAddress"、"DomainName"、"Url" です。
アプリケーション|文字列|インジケーターに関連付けられているアプリケーション。
action|列挙|インジケーターが組織内で検出された場合に実行されるアクション。 指定できる値は、"警告"、"ブロック"、"監査"、"アラート"、"AlertAndBlock"、"BlockAndRemediate"、"許可" です。
|externalID|文字列|顧客がカスタム関連付けの要求で送信できる ID。|
sourceType|列挙|ユーザーによって作成されたインジケーター (ポータルからなど) の場合は "ユーザー"、API を使用して自動アプリケーションを使用して送信した場合は "AadApp"。
createdBySource|string|インジケーターを送信したユーザー/アプリケーションの名前。
createdBy|String|インジケーターを送信したユーザー/アプリケーションの一意の ID。
lastUpdatedBy|文字列|インジケーターを最後に更新したユーザー/アプリケーションの ID。
creationTimeDateTimeUtc|DateTimeOffset|インジケーターが作成された日時。
expirationTime|DateTimeOffset|インジケーターの有効期限。
lastUpdateTime|DateTimeOffset|インジケーターが最後に更新された時刻。
severity|列挙|インジケーターの重大度。 指定できる値は、"Informational"、"Low"、"Medium"、"High" です。
title|String|インジケーターのタイトル。
説明|String|インジケーターの説明。
recommendedActions|文字列|インジケーターに推奨されるアクション。
rbacGroupNames|文字列の一覧|インジケーターが公開され、アクティブになっている RBAC デバイス グループ名。 すべてのデバイスに公開されている場合の空の一覧。
rbacGroupIds|文字列の一覧|RBAC デバイス グループ ID は、インジケーターが公開され、アクティブになっている場所です。 すべてのデバイスに公開されている場合の空の一覧。
generateAlert|列挙|**True アラート** 生成が必要な場合は False、このインジケーターでアラートを生成しない場合は **False** 。

## <a name="indicator-types"></a>インジケーターの種類

API でサポートされているインジケーター アクションの種類は次のとおりです。

- 可
- 監査
- ブロック
- BlockAndRemediate
- 警告 (Defender for Cloud Apps のみ)

応答アクションの種類の説明の詳細については、「 [インジケーターの作成](manage-indicators.md)」を参照してください。

> [!Note]
>
> 以前の応答アクション (AlertAndBlock、および Alert) は、2022 年 1 月までサポートされます。 この日以降、すべての顧客は、上記のいずれかのアクションの種類を使用する必要があります。

## <a name="json-representation"></a>Json 表現

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
