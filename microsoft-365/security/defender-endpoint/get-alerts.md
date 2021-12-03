---
title: アラート API の一覧表示
description: リスト 通知 API を使用して、Microsoft Defender for Endpoint のアラートのコレクションを取得する方法について説明します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: 7c720e7743fda39f7950a7df44bea0007988b94b
ms.sourcegitcommit: c11d4a2b9cb891ba22e16a96cb9d6389f6482459
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61283499"
---
# <a name="list-alerts-api"></a>アラート API の一覧表示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API の説明
アラートのコレクションを取得します。
<br>[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。
<br>OData でサポートされている演算子:
<br>```$filter``` on: ```alertCreationTime``` ```lastUpdateTime``` , , , , ```incidentId``` , , , , , and ```InvestigationId``` ```id``` ```asssignedTo``` ```detectionSource``` ```lastEventTime``` ```status``` ```severity``` ```category``` properties.
<br>```$top``` 最大値が 10,000 の場合
<br>```$skip```
<br>```$expand``` の ```evidence```
<br>Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください。](exposed-apis-odata-samples.md)


## <a name="limitations"></a>制限事項
1. 構成済みの保持期間に従って、最後に更新されたアラートを取得できます。
2. 最大ページ サイズは 10,000 です。
3. この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。 


## <a name="permissions"></a>アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
:---|:---|:---
アプリケーション | Alert.Read.All | 'すべてのアラートの読み取り'
アプリケーション | Alert.ReadWrite.All | 'すべてのアラートの読み取りと書き込み'
委任 (職場または学校のアカウント) | Alert.Read | 'アラートの読み取り'
委任 (職場または学校のアカウント) | Alert.ReadWrite | 'アラートの読み取りと書き込み'

> [!NOTE]
> ユーザー資格情報を使用してトークンを取得する場合:
>
> - ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)
> - 応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられているアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)

## <a name="http-request"></a>HTTP 要求

```http
GET /api/alerts
```

## <a name="request-headers"></a>要求ヘッダー

名前|種類|説明
:---|:---|:---
Authorization | String | ベアラー {token}。 **必須**。

## <a name="request-body"></a>要求本文

Empty

## <a name="response"></a>応答

成功した場合、このメソッドは 200 OK を返し、応答本文の [アラート](alerts.md) オブジェクトの一覧を返します。

## <a name="example-1---default"></a>例 1 - 既定

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

### <a name="response"></a>応答

以下は、応答の例です。

> [!NOTE]
> ここに示す応答リストは、簡単に切り詰められることがあります。 すべてのアラートは、実際の呼び出しから返されます。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637308392288907382_-880718168",
            "incidentId": 7587,
            "investigationId": 723156,
            "assignedTo": "secop123@contoso.com",
            "severity": "Low",
            "status": "New",
            "classification": "TruePositive",
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAv",
            "category": "SuspiciousActivity",
            "threatFamilyName": "Meterpreter",
            "title": "Suspicious 'Meterpreter' behavior was detected",
            "description": "Malware and unwanted software are undesirable applications that perform annoying, disruptive, or harmful actions on affected machines. Some of these undesirable applications can replicate and spread from one machine to another. Others are able to receive commands from remote attackers and perform activities associated with cyber attacks.\n\nA malware is considered active if it is found running on the machine or it already has persistence mechanisms in place. Active malware detections are assigned higher severity ratings.\n\nBecause this malware was active, take precautionary measures and check for residual signs of infection.",
            "alertCreationTime": "2020-07-20T10:53:48.7657932Z",
            "firstEventTime": "2020-07-20T10:52:17.6654369Z",
            "lastEventTime": "2020-07-20T10:52:18.1362905Z",
            "lastUpdateTime": "2020-07-20T10:53:50.19Z",
            "resolvedTime": null,
            "machineId": "12ee6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "MiddleEast",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "DOMAIN"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2020-07-21T01:00:37.8404534Z"
                }
            ],
            "evidence": []
        }
        ...
    ]
}
```

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a>例 2 - 関連する証拠を含む最新のアラートを 10 件取得する

### <a name="request"></a>要求

以下は、要求の例です。

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```

### <a name="response"></a>応答

以下は、応答の例です。

> [!NOTE]
> ここに示す応答リストは、簡単に切り詰められることがあります。 すべてのアラートは、実際の呼び出しから返されます。

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Alerts",
    "value": [
        {
            "id": "da637472900382838869_1364969609",
            "incidentId": 1126093,
            "investigationId": null,
            "assignedTo": null,
            "severity": "Low",
            "status": "New",
            "classification": null,
            "determination": null,
            "investigationState": "Queued",
            "detectionSource": "WindowsDefenderAtp",
            "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
            "category": "Execution",
            "threatFamilyName": null,
            "title": "Low-reputation arbitrary code executed by signed executable",
            "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
            "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
            "firstEventTime": "2021-01-26T20:31:32.9562661Z",
            "lastEventTime": "2021-01-26T20:31:33.0577322Z",
            "lastUpdateTime": "2021-01-26T20:33:59.2Z",
            "resolvedTime": null,
            "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
            "computerDnsName": "temp123.middleeast.corp.microsoft.com",
            "rbacGroupName": "A",
            "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
            "threatName": null,
            "mitreTechniques": [
                "T1064",
                "T1085",
                "T1220"
            ],
            "relatedUser": {
                "userName": "temp123",
                "domainName": "DOMAIN"
            },
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "evidence": [
                {
                    "entityType": "User",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": null,
                    "sha256": null,
                    "fileName": null,
                    "filePath": null,
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": "name",
                    "domainName": "DOMAIN",
                    "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
                    "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
                    "userPrincipalName": "temp123@microsoft.com",
                    "detectionStatus": null
                },
                {
                    "entityType": "Process",
                    "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
                    "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
                    "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
                    "fileName": "rundll32.exe",
                    "filePath": "C:\\Windows\\SysWOW64",
                    "processId": 3276,
                    "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
                    "processCreationTime": "2021-01-26T20:31:32.9581596Z",
                    "parentProcessId": 8420,
                    "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
                    "parentProcessFileName": "rundll32.exe",
                    "parentProcessFilePath": "C:\\Windows\\System32",
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                },
                {
                    "entityType": "File",
                    "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
                    "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
                    "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
                    "fileName": "suspicious.dll",
                    "filePath": "c:\\temp",
                    "processId": null,
                    "processCommandLine": null,
                    "processCreationTime": null,
                    "parentProcessId": null,
                    "parentProcessCreationTime": null,
                    "parentProcessFileName": null,
                    "parentProcessFilePath": null,
                    "ipAddress": null,
                    "url": null,
                    "registryKey": null,
                    "registryHive": null,
                    "registryValueType": null,
                    "registryValue": null,
                    "accountName": null,
                    "domainName": null,
                    "userSid": null,
                    "aadUserId": null,
                    "userPrincipalName": null,
                    "detectionStatus": "Detected"
                }
            ]
        },
        ...
    ]
}
```

## <a name="see-also"></a>関連項目

[エンドポイント用 Microsoft Defender を使用した OData クエリ](exposed-apis-odata-samples.md)
