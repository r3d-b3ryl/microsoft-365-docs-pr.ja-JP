---
title: すべての修復作業を一覧表示する
description: すべての修復アクティビティに関する情報を返します。
keywords: apis、修復、修復 API、get、修復タスク、すべての修復、
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3e387c8fb6ca9f1aca756ef2ab0b4c0684033370
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074452"
---
# <a name="list-all-remediation-activities"></a>すべての修復作業を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

すべての修復アクティビティに関する情報を返します。

[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。

**URL:** GET: /api/remediationTasks
<br>[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。
<br>OData でサポートされている演算子:
<br>```$filter``` on:  ```createdon``` と ```status``` プロパティ。
<br>```$top``` 最大値は 10,000 です。
<br>```$skip```.
<br>Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください](exposed-apis-odata-samples.md)。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|RemediationTasks.Read.All|\'脅威と脆弱性管理の脆弱性情報の読み取り\'
委任 (職場または学校のアカウント)|RemediationTask.Read|\'脅威と脆弱性管理の脆弱性情報の読み取り\'

## <a name="properties"></a>プロパティ

プロパティ (ID)|データ型|説明|返される値の例
:---|:---|:---|:---
カテゴリ|文字列|修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)|ソフトウェア
completerEmail|文字列|修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる|Null
completerId|文字列|修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる|Null
completionMethod|文字列|修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。|自動
createdOn|DateTime|この修復アクティビティが作成された時刻|2021-01-12T18:54:11.5499478Z
説明|文字列|この修復アクティビティの説明|デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。
dueOn|DateTime|この修復アクティビティの作成者セットの期限|2021-01-13T00:00:00Z
fixedDevices|.|固定されているデバイスの数|2
ID|文字列|この修復アクティビティの ID|097d9735-5479-4899-b1b7-77398899df92
nameId|文字列|関連する製品名|Microsoft Silverlight
優先度|文字列|この修復アクティビティの作成者セットの優先度 (High\Medium\Low)|高
productId|文字列|関連する製品 ID|microsoft-_-silverlight
productivityImpactRemediationType|文字列|ユーザーに影響を与えないデバイスに対してだけ、いくつかの構成変更を要求できます。 この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。|AllExposedAssets
rbacGroupNames|文字列|関連するデバイス グループ名|[ "Windows サーバー", "Windows 11", "Windows 10" ]
recommendedProgram|文字列|にアップグレードする推奨プログラム|Null
recommendedVendor|文字列|アップグレードの推奨ベンダー|Null
recommendedVersion|文字列|更新/アップグレードの推奨バージョン|Null
relatedComponent|文字列|この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)|Microsoft Silverlight
requesterEmail|文字列|作成者の電子メール アドレス|globaladmin@UserName.contoso.com
requesterId|文字列|Creator オブジェクト ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|文字列|この修復アクティビティに作成者が追加したメモ (フリー テキスト)|Null
Scid|文字列|関連するセキュリティ推奨事項の SCID|Null
状態|文字列|修復アクティビティの状態 (アクティブ/完了)|Active
statusLastModifiedOn|DateTime|状態フィールドが更新された日付|2021-01-12T18:54:11.5499487Z
targetDevices|Long|この修復が適用される公開デバイスの数|43
Title|String|この修復アクティビティのタイトル|Microsoft Silverlight の更新
型|String|修復の種類|Update
vendorId|文字列|関連ベンダー名|Microsoft

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a>応答の例

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
            "relatedComponent": "Microsoft Silverlight",
            "targetDevices": 18511,
            "rbacGroupNames": [
                "UnassignedGroup",
                "hhh"
            ],
            "fixedDevices": 2866,
            "requesterNotes": "test",
            "dueOn": "2021-02-11T00:00:00Z",
            "category": "Software",
            "productivityImpactRemediationType": null,
            "priority": "Medium",
            "completionMethod": null,
            "completerId": null,
            "completerEmail": null,
            "scid": null,
            "type": "Update",
            "productId": "microsoft-_-silverlight",
            "vendorId": "microsoft",
            "nameId": "silverlight",
            "recommendedVersion": null,
            "recommendedVendor": null,
            "recommendedProgram": null
        }
    ]
}
```

## <a name="see-also"></a>関連項目

- [修復方法とプロパティ](get-remediation-methods-properties.md)
- [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)
- [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)
- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
