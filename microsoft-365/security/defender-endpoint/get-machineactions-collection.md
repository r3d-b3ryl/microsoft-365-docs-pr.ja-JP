---
title: machineActions API の一覧表示
description: リスト MachineActions API を使用して、Microsoft Defender for Endpoint の Machine Actions のコレクションを取得する方法について説明します。
keywords: apis、graph api、サポートされている API、machineaction コレクション
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: d86303d115912d1c89b5b782bae03db4ccbba6ec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200403"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="01b6c-104">MachineActions API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="01b6c-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="01b6c-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="01b6c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="01b6c-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="01b6c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01b6c-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="01b6c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="01b6c-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="01b6c-108">API description</span></span>
<span data-ttu-id="01b6c-109">Machine Actions のコレクション [を取得します](machineaction.md)。</span><span class="sxs-lookup"><span data-stu-id="01b6c-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="01b6c-110">[OData V4 クエリをサポートします](https://www.odata.org/documentation/)。</span><span class="sxs-lookup"><span data-stu-id="01b6c-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="01b6c-111">OData のクエリは ```$filter``` 、次のプロパティ ```status``` ```machineId``` で ```type``` ```requestor``` サポート ```creationDateTimeUtc``` されています。</span><span class="sxs-lookup"><span data-stu-id="01b6c-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="01b6c-112">Microsoft Defender [for Endpoint を使用した OData クエリの例を参照してください。](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="01b6c-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="01b6c-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="01b6c-113">Limitations</span></span>
1. <span data-ttu-id="01b6c-114">最大ページ サイズは 10,000 です。</span><span class="sxs-lookup"><span data-stu-id="01b6c-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="01b6c-115">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="01b6c-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="01b6c-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="01b6c-116">Permissions</span></span>
<span data-ttu-id="01b6c-117">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="01b6c-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="01b6c-118">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="01b6c-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="01b6c-119">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="01b6c-119">Permission type</span></span> |   <span data-ttu-id="01b6c-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="01b6c-120">Permission</span></span>  |   <span data-ttu-id="01b6c-121">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="01b6c-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="01b6c-122">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="01b6c-122">Application</span></span> |   <span data-ttu-id="01b6c-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="01b6c-123">Machine.Read.All</span></span> |  <span data-ttu-id="01b6c-124">'すべてのコンピューター プロファイルを読み取る'</span><span class="sxs-lookup"><span data-stu-id="01b6c-124">'Read all machine profiles'</span></span>
<span data-ttu-id="01b6c-125">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="01b6c-125">Application</span></span> |   <span data-ttu-id="01b6c-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="01b6c-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="01b6c-127">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="01b6c-127">'Read and write all machine information'</span></span>
<span data-ttu-id="01b6c-128">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="01b6c-128">Delegated (work or school account)</span></span> | <span data-ttu-id="01b6c-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="01b6c-129">Machine.Read</span></span> | <span data-ttu-id="01b6c-130">'コンピューター情報の読み取り'</span><span class="sxs-lookup"><span data-stu-id="01b6c-130">'Read machine information'</span></span>
<span data-ttu-id="01b6c-131">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="01b6c-131">Delegated (work or school account)</span></span> | <span data-ttu-id="01b6c-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="01b6c-132">Machine.ReadWrite</span></span> | <span data-ttu-id="01b6c-133">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="01b6c-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="01b6c-134">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="01b6c-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="01b6c-135">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'データの表示' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="01b6c-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="01b6c-136">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="01b6c-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="01b6c-137">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="01b6c-137">Request headers</span></span>

<span data-ttu-id="01b6c-138">名前</span><span class="sxs-lookup"><span data-stu-id="01b6c-138">Name</span></span> | <span data-ttu-id="01b6c-139">型</span><span class="sxs-lookup"><span data-stu-id="01b6c-139">Type</span></span> | <span data-ttu-id="01b6c-140">説明</span><span class="sxs-lookup"><span data-stu-id="01b6c-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="01b6c-141">Authorization</span><span class="sxs-lookup"><span data-stu-id="01b6c-141">Authorization</span></span> | <span data-ttu-id="01b6c-142">String</span><span class="sxs-lookup"><span data-stu-id="01b6c-142">String</span></span> | <span data-ttu-id="01b6c-143">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="01b6c-143">Bearer {token}.</span></span> <span data-ttu-id="01b6c-144">**必須**</span><span class="sxs-lookup"><span data-stu-id="01b6c-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="01b6c-145">要求本文</span><span class="sxs-lookup"><span data-stu-id="01b6c-145">Request body</span></span>
<span data-ttu-id="01b6c-146">Empty</span><span class="sxs-lookup"><span data-stu-id="01b6c-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="01b6c-147">応答</span><span class="sxs-lookup"><span data-stu-id="01b6c-147">Response</span></span>
<span data-ttu-id="01b6c-148">成功した場合、このメソッドは [machineAction](machineaction.md) エンティティのコレクションを持つ 200 Ok 応答コードを返します。</span><span class="sxs-lookup"><span data-stu-id="01b6c-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="01b6c-149">例 1</span><span class="sxs-lookup"><span data-stu-id="01b6c-149">Example 1</span></span>

<span data-ttu-id="01b6c-150">**要求**</span><span class="sxs-lookup"><span data-stu-id="01b6c-150">**Request**</span></span>

<span data-ttu-id="01b6c-151">3 つの MachineActions を持つ組織での要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="01b6c-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="01b6c-152">**応答**</span><span class="sxs-lookup"><span data-stu-id="01b6c-152">**Response**</span></span>

<span data-ttu-id="01b6c-153">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="01b6c-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
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
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="01b6c-154">例 2</span><span class="sxs-lookup"><span data-stu-id="01b6c-154">Example 2</span></span>

<span data-ttu-id="01b6c-155">**要求**</span><span class="sxs-lookup"><span data-stu-id="01b6c-155">**Request**</span></span>

<span data-ttu-id="01b6c-156">次に、MachineActions をコンピューター ID でフィルター処理し、最新の 2 つの MachineActions を表示する要求の例を示します。</span><span class="sxs-lookup"><span data-stu-id="01b6c-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="01b6c-157">**応答**</span><span class="sxs-lookup"><span data-stu-id="01b6c-157">**Response**</span></span>

<span data-ttu-id="01b6c-158">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="01b6c-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
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
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="01b6c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="01b6c-159">Related topics</span></span>
- [<span data-ttu-id="01b6c-160">エンドポイント用 Microsoft Defender を使用した OData クエリ</span><span class="sxs-lookup"><span data-stu-id="01b6c-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
