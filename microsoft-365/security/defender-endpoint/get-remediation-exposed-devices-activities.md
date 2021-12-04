---
title: 1 つの修復アクティビティの暴露デバイスを一覧表示する
description: 指定した修復タスクの公開されているデバイスに関する情報を返します。
keywords: apis、修復、修復 API、取得、修復タスク、公開されているデバイスの修復
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
ms.openlocfilehash: 1a7dffa064b68b2c1ce0296b66eef663eb471496
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301992"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>1 つの修復アクティビティの暴露デバイスを一覧表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API の説明

指定した修復タスクの公開されているデバイスに関する情報を返します。

[修復アクティビティの詳細については、次の情報を参照してください](tvm-remediation.md)。

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>修復タスクに関連付けられている公開されているデバイスの一覧 (ID)

**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences

## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|RemediationTasks.Read.All|\'脅威と脆弱性管理の脆弱性情報の読み取り\'
委任 (職場または学校のアカウント)|RemediationTask.Read.Read|\'脅威と脆弱性管理の脆弱性情報の読み取り\'

## <a name="properties-details"></a>プロパティの詳細

プロパティ (id)|データ型|説明|例
:---|:---|:---|:---
id|String|デバイス ID|w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName|String|デバイス名|PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform|String|デバイス オペレーティング システム|WindowsServer2012R2
rbacGroupName|String|このデバイスが関連付けられているデバイス グループの名前|サーバー

## <a name="example"></a>例

### <a name="request-example"></a>要求の例

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>応答の例

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        }
]
}
```

## <a name="see-also"></a>関連項目

- [修復方法とプロパティ](get-remediation-methods-properties.md)
- [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)
- [すべての修復作業を一覧表示する](get-remediation-all-activities.md)
- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
