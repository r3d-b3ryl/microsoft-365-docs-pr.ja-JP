---
title: アラート API の取得
description: Microsoft Defender for Endpoint の Alert リソースタイプのメソッドとプロパティについて説明します。
keywords: apis, graph api, supported apis, get, alerts, recent
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
ms.openlocfilehash: 5d7fe37cfb4dc923bd7ddc73db9ff8443bca0a0a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179400"
---
# <a name="alert-resource-type"></a>アラート リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="methods"></a>メソッド

<br>

****

|メソッド|戻り値の型|説明|
|---|---|---|
|[警告の取得](get-alert-info-by-id.md)|[アラート](alerts.md)|1 つのアラート [オブジェクトを取得](alerts.md) します。|
|[アラートの一覧表示](get-alerts.md)|[アラート](alerts.md) コレクション|アラート [コレクションを一覧表示](alerts.md) します。|
|[警告の更新](update-alert.md)|[アラート](alerts.md)|特定のアラートを [更新します](alerts.md)。|
|[アラートのバッチ更新](batch-update-alerts.md)||アラートのバッチを更新 [します](alerts.md)。|
|[アラートの作成](create-alert-by-reference.md)|[アラート](alerts.md)|Advanced Hunting から取得したイベント データに基づいてアラート [を作成します](run-advanced-query-api.md)。|
|[関連するドメインを一覧表示する](get-alert-related-domain-info.md)|ドメイン コレクション|アラートに関連付けられている URL を一覧表示します。|
|[関連ファイルを一覧表示する](get-alert-related-files-info.md)|[ファイル](files.md) コレクション|アラートに [関連](files.md) 付けられているファイル エンティティを一覧表示 [します](alerts.md)。|
|[関連する IPs の一覧](get-alert-related-ip-info.md)|IP コレクション|アラートに関連付けられているリストの AP。|
|[関連するコンピューターを取得する](get-alert-related-machine-info.md)|[マシン](machine.md)|アラート [に](machine.md) 関連付けられている [コンピューター](alerts.md)。|
|[関連ユーザーの取得](get-alert-related-user-info.md)|[ユーザー](user.md)|アラート [に](user.md) 関連付けられている [ユーザー](alerts.md)。|
|

## <a name="properties"></a>プロパティ

<br>

****

|プロパティ|型|説明|
|---|---|---|
|id|String|アラート ID。|
|title|String|警告タイトル。|
|説明|String|警告の説明。|
|alertCreationTime|Null 許容の DateTimeOffset|アラートが作成された日付と時刻 (UTC)。|
|lastEventTime|Null 許容の DateTimeOffset|同じデバイスでアラートをトリガーしたイベントの最後の発生。|
|firstEventTime|Null 許容の DateTimeOffset|そのデバイスでアラートをトリガーしたイベントの最初の発生。|
|lastUpdateTime|Null 許容の DateTimeOffset|アラートが最後に更新された日付と時刻 (UTC)。|
|resolvedTime|Null 許容の DateTimeOffset|アラートの状態が [解決済み] に変更された日時。|
|incidentId|Null 許容長|アラート [の](view-incidents-queue.md) インシデント ID。|
|investigationId|Null 許容長|アラート [に](automated-investigations.md) 関連する調査 ID。|
|investigationState|Null 許容列挙|調査の現在の [状態](automated-investigations.md)です。 指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''|
|assignedTo|String|アラートの所有者。|
|rbacGroupName|String|RBAC デバイス グループ名。|
|mitreTechniques|String|Mitre Enterprise ID。|
|relatedUser|String|特定のアラートに関連するユーザーの詳細。|
|severity|列挙|アラートの重大度。 指定できる値は、'UnSpecified'、'Informational'、'Low'、'Medium' および 'High' です。|
|status|列挙|アラートの現在の状態を指定します。 指定できる値は、'Unknown'、'New'、'InProgress'、'Resolved' です。|
|classification|Null 許容列挙|アラートの仕様。 指定できる値は、'Unknown'、'FalsePositive'、'TruePositive'です。|
|決定|Null 許容列挙|アラートの決定を指定します。 指定できる値は、'NotAvailable'、'Apt'、'Malware'、'SecurityPersonnel'、'SecurityTesting'、'UnwantedSoftware'、'Other' です。|
|category|String|アラートのカテゴリ。|
|detectionSource|String|検出ソース。|
|threatFamilyName|String|脅威ファミリ。|
|threatName|String|脅威の名前。|
|machineId|String|アラートに [関連付](machine.md) けられているコンピューター エンティティの ID。|
|computerDnsName|String|[コンピューター](machine.md) の完全修飾名。|
|aadTenantId|String|ユーザー ID Azure Active Directory ID。|
|detectorId|String|アラートをトリガーした検出器の ID。|
|comments|アラートコメントの一覧|Alert Comment オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。|
|証拠|アラート証拠の一覧|アラートに関連する証拠。 次の例を参照してください。|
|

### <a name="response-example-for-getting-single-alert"></a>1 つのアラートを取得する場合の応答例:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
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
}
```
