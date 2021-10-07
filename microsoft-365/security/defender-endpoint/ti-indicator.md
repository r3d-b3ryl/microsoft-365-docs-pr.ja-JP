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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d7805ad7a2c1aae750b6588a6dd2c4141c9b93c3
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191637"
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

プロパティ|型|説明
:---|:---|:---
id|String|Indicator エンティティ [の](ti-indicator.md) ID。
indicatorValue|String|Indicator の [値](ti-indicator.md)です。
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileSha256"、"FileMd5"、"CertificateThumbprint"、"IpAddress"、"DomainName"、"Url" です。
アプリケーション|String|インジケーターに関連付けられているアプリケーション。
action|列挙|インジケーターが組織内で検出される場合に実行されるアクション。 指定できる値は、"Warn"、"Block"、"Audit"、"Alert"、"AlertAndBlock"、"BlockAndRemediate"、"Allowed" です。
|externalID|String|カスタム相関関係の要求で顧客が送信できる ID。|
sourceType|列挙|"User" (ポータルからなど) ユーザーが作成したインジケーターの場合、API を介して自動アプリケーションを使用して送信された場合は "AadApp"。
createdBySource|string|インジケーターを送信したユーザー/アプリケーションの名前。
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
rbacGroupIds|文字列の一覧|RBAC デバイス グループ ID は、インジケーターが公開され、アクティブな場所です。 すべてのデバイスに公開されている場合の空のリスト。
## <a name="public-preview-indicator-types"></a>パブリック プレビュー: インジケーターの種類

> [!IMPORTANT]
> このセクションの情報 (**自動** 調査および修復エンジンのパブリック プレビュー) は、製品の商用リリース前に大幅に変更される可能性がある、事前リリース済みの製品に関連します。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

API でサポートされるインジケーター アクションの種類は次のとおりです。

- 可
- 通知
- AlertAndBlock
- 監査
- ブロック
- BlockAndRemediate
- 警告

アクションの種類の API リストには、新しい応答アクションと、以前の応答アクション (AlertAndBlock、および Alert) が含まれる。 応答アクションの種類の説明の詳細については、「Create indicators 」 [を参照してください](manage-indicators.md)。

許可、警告、ブロック、および BlockAndRemediate の IoC 応答アクションはパブリック プレビューに表示されます。 パブリック プレビューの詳細については、「パブリック プレビュー: カスタム ファイル IoC 拡張機能と API スキーマ[更新プログラム - Microsoft Tech Community」 を参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/public-preview-custom-file-ioc-enhancements-and-api-schema/ba-p/2676997)。




> [!Note]
>
> 機能が GAed に達すると、以前の応答アクション (AlertAndBlock、および Alert) は削除されます。 猶予期間付き GA 日付は 2021 年 10 月の終わりです。  既存のテンプレートまたはスクリプトをできるだけ早く更新してください。

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
