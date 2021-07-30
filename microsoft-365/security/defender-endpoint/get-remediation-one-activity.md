---
title: Id で 1 つの修復アクティビティを取得する
description: 指定した修復アクティビティの情報を返します。
keywords: apis、修復、修復 API、get、修復タスク、ID による修復、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0a73e8269f4be23d97ead5a2befb677706c7486a
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656705"
---
# <a name="get-one-remediation-activity-by-id"></a>Id で 1 つの修復アクティビティを取得する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

指定した修復アクティビティの情報を返します。 [すべての修復アクティビティを取得 [する]](get-remediation-all-activities.md)と同じ列を表示しますが、指定した修復アクティビティ _の結果のみを返します_。

[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。

## <a name="list-a-specified-remediation-activity-for-id"></a>(id) の指定された修復アクティビティを一覧表示する

**URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|RemediationTask.Read.All|\'脅威と脆弱性管理の脆弱性情報の読み取り\'
委任 (職場または学校のアカウント)|RemediationTask.Read.Read|\'脅威と脆弱性管理の脆弱性情報の読み取り\'

## <a name="properties"></a>プロパティ

プロパティ (id)|データ型|説明|返される値の例
:---|:---|:---|:---
category|String|修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)|ソフトウェア
completerEmail|String|修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる|null
completerId|String|修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる|null
completionMethod|String|修復アクティビティは、"完了としてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。|自動
createdOn|DateTime|この修復アクティビティが作成された時刻|2021-01-12T18:54:11.5499478Z
description|String|この修復アクティビティの説明|デバイスに影響を与える既知の脆弱性を軽減するために、Microsoft Silverlight を新しいバージョンに更新します。
dueOn|DateTime|この修復アクティビティの作成者セットの期限|2021-01-13T00:00:00Z
fixedDevices||固定されているデバイスの数|2
id|String|この修復アクティビティの ID|097d9735-5479-4899-b1b7-77398899df92
nameId|String|関連する製品名|Microsoft Silverlight
priority|String|この修復アクティビティの作成者セットの優先度 (High\Medium\Low)|高い
productId|String|関連する製品 ID|microsoft-_-silverlight
productivityImpactRemediationType|String|いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。 この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。|AllExposedAssets
rbacGroupNames|String|関連するデバイス グループ名|[ "Windows サーバー", "Windows 10" ]
recommendedProgram|String|にアップグレードする推奨プログラム|null
recommendedVendor|String|アップグレードの推奨ベンダー|null
recommendedVersion|String|更新/アップグレードの推奨バージョン|null
relatedComponent|String|この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)|Microsoft Microsoft Silverlight
requesterEmail|String|作成者の電子メール アドレス|globaladmin@UserName.contoso.com
requesterId|String|Creator オブジェクト ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|String|この修復アクティビティに作成者が追加したメモ (フリー テキスト)|null
scid|String|関連するセキュリティ推奨事項の SCID|null
status|String|修復アクティビティの状態 (アクティブ/完了)|アクティブ
statusLastModifiedOn|DateTime|状態フィールドが更新された日付|2021-01-12T18:54:11.5499487Z
targetDevices|Long|この修復が適用される公開デバイスの数|43
title|String|この修復アクティビティのタイトル|Microsoft Silverlight
type|String|修復の種類|Update
vendorId|String|関連ベンダー名|Microsoft

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>応答の例

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
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
```

## <a name="see-also"></a>関連項目

- [修復方法とプロパティ](get-remediation-methods-properties.md)
- [すべての修復作業を一覧表示する](get-remediation-all-activities.md)
- [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)
- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
