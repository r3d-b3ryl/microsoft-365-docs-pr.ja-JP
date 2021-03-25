---
title: アラート API の一覧表示
description: リスト 通知 API を使用して、Microsoft Defender for Endpoint のアラートのコレクションを取得する方法について説明します。
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
ms.technology: mde
ms.openlocfilehash: f4b62ca7fecb8e66fc082b6cf0972c1c2c06afb5
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166972"
---
# <a name="list-alerts-api"></a><span data-ttu-id="0fda6-104">アラート API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="0fda6-104">List alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0fda6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0fda6-105">**Applies to:**</span></span>
- [<span data-ttu-id="0fda6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0fda6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0fda6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0fda6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0fda6-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="0fda6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0fda6-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="0fda6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="0fda6-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="0fda6-110">API description</span></span>
<span data-ttu-id="0fda6-111">アラートのコレクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="0fda6-111">Retrieves a collection of Alerts.</span></span>
<br><span data-ttu-id="0fda6-112">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="0fda6-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="0fda6-113">OData でサポートされている演算子:</span><span class="sxs-lookup"><span data-stu-id="0fda6-113">OData supported operators:</span></span>
<br><span data-ttu-id="0fda6-114">```$filter``` on: ```alertCreationTime``` ```lastUpdateTime``` , , , , ```incidentId``` and ```InvestigationId``` ```status``` ```severity``` ```category``` properties.</span><span class="sxs-lookup"><span data-stu-id="0fda6-114">```$filter``` on: ```alertCreationTime```, ```lastUpdateTime```, ```incidentId```,```InvestigationId```, ```status```, ```severity``` and ```category``` properties.</span></span>
<br><span data-ttu-id="0fda6-115">```$top``` 最大値が 10,000 の場合</span><span class="sxs-lookup"><span data-stu-id="0fda6-115">```$top``` with max value of 10,000</span></span>
<br>```$skip```
<br><span data-ttu-id="0fda6-116">```$expand``` の ```evidence```</span><span class="sxs-lookup"><span data-stu-id="0fda6-116">```$expand``` of ```evidence```</span></span>
<br><span data-ttu-id="0fda6-117">Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="0fda6-117">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="0fda6-118">制限事項</span><span class="sxs-lookup"><span data-stu-id="0fda6-118">Limitations</span></span>
1. <span data-ttu-id="0fda6-119">構成済みの保持期間に従って、最後に更新されたアラートを取得できます。</span><span class="sxs-lookup"><span data-stu-id="0fda6-119">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="0fda6-120">最大ページ サイズは 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-120">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="0fda6-121">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="0fda6-121">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="0fda6-122">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0fda6-122">Permissions</span></span>
<span data-ttu-id="0fda6-123">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-123">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0fda6-124">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0fda6-124">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0fda6-125">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="0fda6-125">Permission type</span></span> |   <span data-ttu-id="0fda6-126">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0fda6-126">Permission</span></span>  |   <span data-ttu-id="0fda6-127">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="0fda6-127">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0fda6-128">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0fda6-128">Application</span></span> |   <span data-ttu-id="0fda6-129">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="0fda6-129">Alert.Read.All</span></span> |    <span data-ttu-id="0fda6-130">'すべてのアラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="0fda6-130">'Read all alerts'</span></span>
<span data-ttu-id="0fda6-131">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0fda6-131">Application</span></span> |   <span data-ttu-id="0fda6-132">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0fda6-132">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="0fda6-133">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="0fda6-133">'Read and write all alerts'</span></span>
<span data-ttu-id="0fda6-134">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="0fda6-134">Delegated (work or school account)</span></span> | <span data-ttu-id="0fda6-135">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="0fda6-135">Alert.Read</span></span> | <span data-ttu-id="0fda6-136">'アラートの読み取り'</span><span class="sxs-lookup"><span data-stu-id="0fda6-136">'Read alerts'</span></span>
<span data-ttu-id="0fda6-137">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="0fda6-137">Delegated (work or school account)</span></span> | <span data-ttu-id="0fda6-138">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0fda6-138">Alert.ReadWrite</span></span> | <span data-ttu-id="0fda6-139">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="0fda6-139">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="0fda6-140">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="0fda6-140">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0fda6-141">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="0fda6-141">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="0fda6-142">応答には、デバイス グループ設定に基づいて、ユーザーがアクセスできるデバイスに関連付けられているアラートだけが含まれます[](machine-groups.md)(詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="0fda6-142">The response will include only alerts that are associated with devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0fda6-143">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="0fda6-143">HTTP request</span></span>
```
GET /api/alerts
```

## <a name="request-headers"></a><span data-ttu-id="0fda6-144">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="0fda6-144">Request headers</span></span>

<span data-ttu-id="0fda6-145">名前</span><span class="sxs-lookup"><span data-stu-id="0fda6-145">Name</span></span> | <span data-ttu-id="0fda6-146">種類</span><span class="sxs-lookup"><span data-stu-id="0fda6-146">Type</span></span> | <span data-ttu-id="0fda6-147">説明</span><span class="sxs-lookup"><span data-stu-id="0fda6-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="0fda6-148">Authorization</span><span class="sxs-lookup"><span data-stu-id="0fda6-148">Authorization</span></span> | <span data-ttu-id="0fda6-149">文字列</span><span class="sxs-lookup"><span data-stu-id="0fda6-149">String</span></span> | <span data-ttu-id="0fda6-150">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="0fda6-150">Bearer {token}.</span></span> <span data-ttu-id="0fda6-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="0fda6-151">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0fda6-152">要求本文</span><span class="sxs-lookup"><span data-stu-id="0fda6-152">Request body</span></span>
<span data-ttu-id="0fda6-153">Empty</span><span class="sxs-lookup"><span data-stu-id="0fda6-153">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0fda6-154">応答</span><span class="sxs-lookup"><span data-stu-id="0fda6-154">Response</span></span>
<span data-ttu-id="0fda6-155">成功した場合、このメソッドは 200 OK を返し、応答本文の [アラート](alerts.md) オブジェクトの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="0fda6-155">If successful, this method returns 200 OK, and a list of [alert](alerts.md) objects in the response body.</span></span>


## <a name="example-1---default"></a><span data-ttu-id="0fda6-156">例 1 - 既定</span><span class="sxs-lookup"><span data-stu-id="0fda6-156">Example 1 - Default</span></span>

<span data-ttu-id="0fda6-157">**要求**</span><span class="sxs-lookup"><span data-stu-id="0fda6-157">**Request**</span></span>

<span data-ttu-id="0fda6-158">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-158">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts
```

<span data-ttu-id="0fda6-159">**応答**</span><span class="sxs-lookup"><span data-stu-id="0fda6-159">**Response**</span></span>

<span data-ttu-id="0fda6-160">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-160">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="0fda6-161">ここに示す応答リストは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="0fda6-161">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="0fda6-162">すべてのアラートは、実際の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="0fda6-162">All alerts will be returned from an actual call.</span></span>


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
                "domainName": "MIDDLEEAST"
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

## <a name="example-2---get-10-latest-alerts-with-related-evidence"></a><span data-ttu-id="0fda6-163">例 2 - 関連する証拠を含む最新のアラートを 10 件取得する</span><span class="sxs-lookup"><span data-stu-id="0fda6-163">Example 2 - Get 10 latest Alerts with related Evidence</span></span>

<span data-ttu-id="0fda6-164">**要求**</span><span class="sxs-lookup"><span data-stu-id="0fda6-164">**Request**</span></span>

<span data-ttu-id="0fda6-165">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-165">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts?$top=10&$expand=evidence
```


<span data-ttu-id="0fda6-166">**応答**</span><span class="sxs-lookup"><span data-stu-id="0fda6-166">**Response**</span></span>

<span data-ttu-id="0fda6-167">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="0fda6-167">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="0fda6-168">ここに示す応答リストは、簡単に切り詰められることがあります。</span><span class="sxs-lookup"><span data-stu-id="0fda6-168">The response list shown here may be truncated for brevity.</span></span> <span data-ttu-id="0fda6-169">すべてのアラートは、実際の呼び出しから返されます。</span><span class="sxs-lookup"><span data-stu-id="0fda6-169">All alerts will be returned from an actual call.</span></span>


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
                "domainName": "MIDDLEEAST"
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
                    "accountName": "eranb",
                    "domainName": "MIDDLEEAST",
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


## <a name="see-also"></a><span data-ttu-id="0fda6-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="0fda6-170">See also</span></span>
- [<span data-ttu-id="0fda6-171">エンドポイント用 Microsoft Defender を使用した OData クエリ</span><span class="sxs-lookup"><span data-stu-id="0fda6-171">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
