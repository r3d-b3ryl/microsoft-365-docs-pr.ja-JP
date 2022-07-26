---
title: すべての修復作業を一覧表示する
description: すべての修復アクティビティに関する情報を返します。
keywords: apis, 修復, 修復 API, get, 修復タスク, すべての修復,
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
ms.openlocfilehash: 2540e1d9521771bd9ae4d49b96384fefd8766aec
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020068"
---
# <a name="list-all-remediation-activities"></a>すべての修復作業を一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink).

> Microsoft Defender 脆弱性の管理を体験しますか? [Microsoft Defender 脆弱性の管理パブリック プレビュー試用版](../defender-vulnerability-management/get-defender-vulnerability-management.md)にサインアップする方法の詳細については、こちらを参照してください。

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

すべての修復アクティビティに関する情報を返します。

[修復アクティビティの詳細については、こちらを参照してください](tvm-remediation.md)。

**URL：** GET: /api/remediationTasks
<br>[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。
<br>OData でサポートされている演算子:
<br>```$filter``` on:  ```createdon``` と ```status``` プロパティ。
<br>```$top``` 最大値が 10,000 です。
<br>```$skip```.
<br>[Microsoft Defender for Endpointを使用した OData クエリの](exposed-apis-odata-samples.md)例を参照してください。

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|RemediationTasks.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|RemediationTask.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

## <a name="properties"></a>プロパティ

プロパティ (ID)|データ型|説明|返された値の例
:---|:---|:---|:---
カテゴリ|文字列|修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)|ソフトウェア
completerEmail|String|修復アクティビティが他のユーザーによって手動で完了した場合、この列には自分のメールが含まれます|Null
completerId|String|修復アクティビティが他のユーザーによって手動で完了した場合、この列にはオブジェクト ID が含まれます。|Null
completionMethod|String|修復アクティビティは、"自動的に" (すべてのデバイスに修正プログラムが適用されている場合) 完了するか、"完了としてマーク" を選択したユーザーが "手動" で完了できます。|自動
createdOn|DateTime|この修復アクティビティが作成された時刻|2021-01-12T18:54:11.5499478Z
説明|String|この修復アクティビティの説明|デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。
dueOn|DateTime|この修復アクティビティに対して作成者が設定した期限|2021-01-13T00:00:00Z
fixedDevices|.|修正されたデバイスの数|2
ID|String|この修復アクティビティの ID|097d9735-5479-4899-b1b7-77398899df92
Nameid|String|関連する製品名|Microsoft Silverlight
優先度|String|この修復アクティビティの作成者セットの優先度 (高\中\低)|高い
Productid|String|関連する製品 ID|microsoft-_-silverlight
productivityImpactRemediationType|String|いくつかの構成変更は、ユーザーに影響を与えないデバイスに対してのみ要求できます。 この値は、"すべての公開デバイス" または "ユーザーに影響のないデバイスのみ" の選択を示します。|AllExposedAssets
rbacGroupNames|String|関連するデバイス グループ名|[ "Windows サーバー"、"Windows 11"、"Windows 10" ]
recommendedProgram|String|にアップグレードするための推奨プログラム|Null
recommendedVendor|String|アップグレード先として推奨されるベンダー|Null
recommendedVersion|String|更新/アップグレードに推奨されるバージョン|Null
relatedComponent|String|この修復アクティビティの関連コンポーネント (セキュリティに関する推奨事項の関連コンポーネントと同様)|Microsoft Silverlight
requesterEmail|String|作成者の電子メール アドレス|globaladmin@UserName.contoso.com
requesterId|String|Creator オブジェクト ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|String|この修復アクティビティに対して作成者が追加したノート (フリー テキスト)|Null
Scid|String|関連するセキュリティ推奨事項の SCID|Null
状態|String|修復アクティビティの状態 (アクティブ/完了)|アクティブ
statusLastModifiedOn|DateTime|状態フィールドが更新された日付|2021-01-12T18:54:11.5499487Z
targetDevices|Long|この修復が適用できる公開デバイスの数|43
Title|String|この修復アクティビティのタイトル|Microsoft Silverlight を更新する
型|String|修復の種類|Update
vendorId|String|関連するベンダー名|Microsoft

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

- [修復メソッドとプロパティ](get-remediation-methods-properties.md)
- [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)
- [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)
- [リスクベースの脅威&脆弱性管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
