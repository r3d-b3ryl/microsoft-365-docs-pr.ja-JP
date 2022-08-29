---
title: Microsoft Defender for Endpointを使用した OData クエリ
ms.reviewer: ''
description: 次の Open Data Protocol (OData) クエリの例を使用して、Microsoft Defender for Endpointのデータ アクセス プロトコルに役立ちます。
keywords: apis, サポートされている apis, odata, query
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
ms.openlocfilehash: b10c54474427002e82a3639578ce2c9192bf735f
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327803"
---
# <a name="odata-queries-with-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointを使用した OData クエリ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

OData クエリに慣れていない場合は、「[OData V4 クエリ](https://www.odata.org/documentation/)」を参照してください。

すべてのプロパティがフィルター可能なわけではありません。

## <a name="properties-that-support-filter"></a>$filterをサポートするプロパティ

- [アラート](alerts.md): `alertCreationTime`、、`lastUpdateTime`、`incidentId`、`InvestigationId`、、`status``severity`および `category`.
- [コンピューター](machine.md): `ComputerDnsName`、、`LastSeen`、`HealthStatus`、`OsPlatform`、 `RiskScore``onboardingStatus``RbacGroupId`.
- [MachineAction](machineaction.md): `Status`、、 `MachineId`、 `Type`、 `Requestor`および `CreationDateTimeUtc`.
- [インジケーター](ti-indicator.md): `indicatorValue`, , `indicatorType`, `createdBy``creationTimeDateTimeUtc`, `severity`および `action`.

### <a name="example-1"></a>例 1

関連する証拠を含む 10 個の最新のアラートを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```

#### <a name="response"></a>応答

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

### <a name="example-2"></a>例 2

2019-11-22 00:00:00 以降に最後に更新されたすべてのアラートを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/alerts?$filter=lastUpdateTime+ge+2019-11-22T00:00:00Z
```

#### <a name="response"></a>応答

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

### <a name="example-3"></a>例 3

'High' 'RiskScore' を持つすべてのデバイスを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machines?$filter=riskScore+eq+'High'
```

#### <a name="response"></a>応答

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2021-01-25T07:27:36.052313Z",
            "osPlatform": "Windows10" "Windows11",
            "osProcessor": "x64",
            "version": "1901",
            "lastIpAddress": "10.166.113.46",
            "lastExternalIpAddress": "167.220.203.175",
            "osBuild": 19042,
            "healthStatus": "Active",
            "deviceValue": "Normal",
            "rbacGroupName": "The-A-Team",
            "riskScore": "High",
            "exposureLevel": "Low",
            "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
            "machineTags": [
                "Tag1",
                "Tag2"
            ],
            "ipAddresses": [
                {
                    "ipAddress": "10.166.113.47",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                },
                {
                    "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                }
            ]
        },
        ...
    ]
}
```

### <a name="example-4"></a>例 4

'HealthStatus' が 'Active' に等しくない上位 100 個のデバイスを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machines?$filter=healthStatus+ne+'Active'&$top=100 
```

#### <a name="response"></a>応答

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2021-01-25T07:27:36.052313Z",
            "osPlatform": "Windows10",
            "osProcessor": "x64",
            "version": "1901",
            "lastIpAddress": "10.166.113.46",
            "lastExternalIpAddress": "167.220.203.175",
            "osBuild": 19042,
            "healthStatus": "Active",
            "deviceValue": "Normal",
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Low",
            "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
            "machineTags": [
                "Tag1",
                "Tag2"
            ],
            "ipAddresses": [
                {
                    "ipAddress": "10.166.113.47",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                },
                {
                    "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                }
            ]
        },
        ...
    ]
}
```

### <a name="example-5"></a>例 5

2018-10-20 以降に最後に表示されたすべてのデバイスを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machines?$filter=lastSeen gt 2018-08-01Z
```

#### <a name="response"></a>応答

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2021-01-25T07:27:36.052313Z",
            "osPlatform": "Windows10",
            "osProcessor": "x64",
            "version": "1901",
            "lastIpAddress": "10.166.113.46",
            "lastExternalIpAddress": "167.220.203.175",
            "osBuild": 19042,
            "healthStatus": "Active",
            "deviceValue": "Normal",
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Low",
            "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
            "machineTags": [
                "Tag1",
                "Tag2"
            ],
            "ipAddresses": [
                {
                    "ipAddress": "10.166.113.47",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                },
                {
                    "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                }
            ]
        },
        ...
    ]
}
```

### <a name="example-6"></a>例 6

ユーザーがMicrosoft Defender for Endpointを使用して作成したすべてのウイルス対策スキャン Analyst@examples.onmicrosoft.com 取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machineactions?$filter=requestor eq 'Analyst@contoso.com' and type eq 'RunAntiVirusScan'
```

#### <a name="response"></a>応答

```json
json{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        ...
    ]
}
```

### <a name="example-7"></a>例 7

特定のデバイスの開いているアラートの数を取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machines/123321d0c675eaa415b8e5f383c6388bff446c62/alerts/$count?$filter=status ne 'Resolved'
```

#### <a name="response"></a>応答

```json
4
```

### <a name="example-8"></a>例 8

'mymachine' で始まる 'computerDnsName' を持つすべてのデバイスを取得します。

```http
HTTP GET  https://api.securitycenter.microsoft.com/api/machines?$filter=startswith(computerDnsName,'mymachine')
```

#### <a name="response"></a>応答

```json
json{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
            "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
            "computerDnsName": "mymachine1.contoso.com",
            "firstSeen": "2018-08-02T14:55:03.7791856Z",
            "lastSeen": "2021-01-25T07:27:36.052313Z",
            "osPlatform": "Windows10",
            "osProcessor": "x64",
            "version": "1901",
            "lastIpAddress": "10.166.113.46",
            "lastExternalIpAddress": "167.220.203.175",
            "osBuild": 19042,
            "healthStatus": "Active",
            "deviceValue": "Normal",
            "rbacGroupName": "The-A-Team",
            "riskScore": "Low",
            "exposureLevel": "Low",
            "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
            "machineTags": [
                "Tag1",
                "Tag2"
            ],
            "ipAddresses": [
                {
                    "ipAddress": "10.166.113.47",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                },
                {
                    "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
                    "macAddress": "8CEC4B897E73",
                    "operationalStatus": "Up"
                }
            ]
        },
        ...
    ]
}
```

## <a name="see-also"></a>関連項目

[Microsoft Defender for Endpoint API](apis-intro.md)
