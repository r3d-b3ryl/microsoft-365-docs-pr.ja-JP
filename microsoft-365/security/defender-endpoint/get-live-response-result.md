---
title: ライブ応答の結果を取得する
description: インデックスによって特定のライブ応答コマンドの結果を取得する方法について説明します。
keywords: apis、graph api、サポートされている API、ライブラリへのアップロード
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879730"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="8ce4c-104">ライブ応答の結果を取得する</span><span class="sxs-lookup"><span data-stu-id="8ce4c-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ce4c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8ce4c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ce4c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ce4c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="8ce4c-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="8ce4c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ce4c-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8ce4c-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="8ce4c-109">API description</span></span>

<span data-ttu-id="8ce4c-110">インデックスによって特定のライブ応答コマンドの結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="8ce4c-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="8ce4c-111">Limitations</span></span>

1.  <span data-ttu-id="8ce4c-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="8ce4c-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ce4c-113">Permissions</span></span>

<span data-ttu-id="8ce4c-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ce4c-115">アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="8ce4c-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="8ce4c-116">Permission type</span></span>                    | <span data-ttu-id="8ce4c-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ce4c-117">Permission</span></span>           | <span data-ttu-id="8ce4c-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="8ce4c-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="8ce4c-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8ce4c-119">Application</span></span>                        | <span data-ttu-id="8ce4c-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="8ce4c-120">Machine.LiveResponse</span></span> | <span data-ttu-id="8ce4c-121">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="8ce4c-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="8ce4c-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="8ce4c-122">Delegated (work or school account)</span></span> | <span data-ttu-id="8ce4c-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="8ce4c-123">Machine.LiveResponse</span></span> | <span data-ttu-id="8ce4c-124">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="8ce4c-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="8ce4c-125">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="8ce4c-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="8ce4c-126">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="8ce4c-126">Request headers</span></span>

| <span data-ttu-id="8ce4c-127">名前</span><span class="sxs-lookup"><span data-stu-id="8ce4c-127">Name</span></span>      | <span data-ttu-id="8ce4c-128">型</span><span class="sxs-lookup"><span data-stu-id="8ce4c-128">Type</span></span> | <span data-ttu-id="8ce4c-129">説明</span><span class="sxs-lookup"><span data-stu-id="8ce4c-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="8ce4c-130">Authorization</span><span class="sxs-lookup"><span data-stu-id="8ce4c-130">Authorization</span></span> | <span data-ttu-id="8ce4c-131">String</span><span class="sxs-lookup"><span data-stu-id="8ce4c-131">String</span></span>   | <span data-ttu-id="8ce4c-p103">ベアラー {トークン}。必須。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="8ce4c-134">要求本文</span><span class="sxs-lookup"><span data-stu-id="8ce4c-134">Request body</span></span>

<span data-ttu-id="8ce4c-135">Empty</span><span class="sxs-lookup"><span data-stu-id="8ce4c-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8ce4c-136">応答</span><span class="sxs-lookup"><span data-stu-id="8ce4c-136">Response</span></span>

<span data-ttu-id="8ce4c-137">成功した場合、このメソッドは、コマンドへのリンクを保持するオブジェクトを含む 200 Ok 応答コードを value プロパティ *に返* します。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="8ce4c-138">このリンクは 30 分間有効であり、パッケージをローカル ストレージにダウンロードするためにすぐに使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="8ce4c-139">有効期限が切れたリンクは、別の呼び出しによって再作成できます。また、ライブ応答を再度実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="8ce4c-140">*Runscript トランスクリプト プロパティ:*</span><span class="sxs-lookup"><span data-stu-id="8ce4c-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="8ce4c-141">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ce4c-141">Property</span></span>  | <span data-ttu-id="8ce4c-142">説明</span><span class="sxs-lookup"><span data-stu-id="8ce4c-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="8ce4c-143">name</span><span class="sxs-lookup"><span data-stu-id="8ce4c-143">name</span></span>          | <span data-ttu-id="8ce4c-144">実行されたスクリプト名</span><span class="sxs-lookup"><span data-stu-id="8ce4c-144">Executed script name</span></span>                  |
| <span data-ttu-id="8ce4c-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="8ce4c-145">exit_code</span></span>     | <span data-ttu-id="8ce4c-146">実行されたスクリプトの終了コード</span><span class="sxs-lookup"><span data-stu-id="8ce4c-146">Executed script exit code</span></span>             |
| <span data-ttu-id="8ce4c-147">script_output</span><span class="sxs-lookup"><span data-stu-id="8ce4c-147">script_output</span></span> | <span data-ttu-id="8ce4c-148">実行されたスクリプトの標準出力</span><span class="sxs-lookup"><span data-stu-id="8ce4c-148">Executed script standard output</span></span>       |
| <span data-ttu-id="8ce4c-149">script_error</span><span class="sxs-lookup"><span data-stu-id="8ce4c-149">script_error</span></span>  | <span data-ttu-id="8ce4c-150">実行されたスクリプトの標準エラー出力</span><span class="sxs-lookup"><span data-stu-id="8ce4c-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="8ce4c-151">例</span><span class="sxs-lookup"><span data-stu-id="8ce4c-151">Example</span></span>

<span data-ttu-id="8ce4c-152">**要求**</span><span class="sxs-lookup"><span data-stu-id="8ce4c-152">**Request**</span></span>

<span data-ttu-id="8ce4c-153">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="8ce4c-154">**応答**</span><span class="sxs-lookup"><span data-stu-id="8ce4c-154">**Response**</span></span>

<span data-ttu-id="8ce4c-155">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="8ce4c-155">Here is an example of the response.</span></span>

<span data-ttu-id="8ce4c-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="8ce4c-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="8ce4c-157">コンテンツタイプ: application/json</span><span class="sxs-lookup"><span data-stu-id="8ce4c-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="8ce4c-158">*ファイルの内容:*</span><span class="sxs-lookup"><span data-stu-id="8ce4c-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="8ce4c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ce4c-159">Related topics</span></span>

- [<span data-ttu-id="8ce4c-160">コンピューター アクション API の取得</span><span class="sxs-lookup"><span data-stu-id="8ce4c-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="8ce4c-161">コンピューターの操作をキャンセルする</span><span class="sxs-lookup"><span data-stu-id="8ce4c-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="8ce4c-162">ライブ応答の実行</span><span class="sxs-lookup"><span data-stu-id="8ce4c-162">Run live response</span></span>](run-live-response.md) 
