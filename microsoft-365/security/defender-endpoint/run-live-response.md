---
title: デバイスでライブ応答コマンドを実行する
description: デバイスで一連のライブ応答コマンドを実行する方法について説明します。
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
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879702"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="d5cb3-104">デバイスでライブ応答コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="d5cb3-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5cb3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d5cb3-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5cb3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d5cb3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="d5cb3-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="d5cb3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d5cb3-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d5cb3-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="d5cb3-109">API description</span></span>

<span data-ttu-id="d5cb3-110">デバイスで一連のライブ応答コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="d5cb3-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="d5cb3-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="d5cb3-111">Limitations</span></span>

1.  <span data-ttu-id="d5cb3-112">この API のレート制限は、1 分あたり 10 回の呼び出しです (追加の要求は HTTP 429 で応答されます)。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="d5cb3-113">25 の同時実行セッション (調整制限を超える要求は"429 - 要求が多すぎます" という応答を受け取ります)。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="d5cb3-114">コンピューターが使用できない場合、セッションは最大 3 日間キューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="d5cb3-115">RunScript コマンドは 10 分後にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="d5cb3-116">ライブ応答コマンドが失敗すると、フォローしているすべてのアクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="d5cb3-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5cb3-117">Permissions</span></span>

<span data-ttu-id="d5cb3-118">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d5cb3-119">アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="d5cb3-120">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="d5cb3-120">Permission type</span></span>                    | <span data-ttu-id="d5cb3-121">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5cb3-121">Permission</span></span>           | <span data-ttu-id="d5cb3-122">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="d5cb3-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="d5cb3-123">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d5cb3-123">Application</span></span>                        | <span data-ttu-id="d5cb3-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="d5cb3-124">Machine.LiveResponse</span></span> | <span data-ttu-id="d5cb3-125">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="d5cb3-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="d5cb3-126">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="d5cb3-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d5cb3-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="d5cb3-127">Machine.LiveResponse</span></span> | <span data-ttu-id="d5cb3-128">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="d5cb3-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="d5cb3-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d5cb3-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="d5cb3-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d5cb3-130">Request headers</span></span>

| <span data-ttu-id="d5cb3-131">名前</span><span class="sxs-lookup"><span data-stu-id="d5cb3-131">Name</span></span>      | <span data-ttu-id="d5cb3-132">型</span><span class="sxs-lookup"><span data-stu-id="d5cb3-132">Type</span></span> | <span data-ttu-id="d5cb3-133">説明</span><span class="sxs-lookup"><span data-stu-id="d5cb3-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="d5cb3-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="d5cb3-134">Authorization</span></span> | <span data-ttu-id="d5cb3-135">String</span><span class="sxs-lookup"><span data-stu-id="d5cb3-135">String</span></span>   | <span data-ttu-id="d5cb3-136">ベアラー\<token>\.</span><span class="sxs-lookup"><span data-stu-id="d5cb3-136">Bearer\<token>\.</span></span> <span data-ttu-id="d5cb3-137">必須です。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-137">Required.</span></span>   |
| <span data-ttu-id="d5cb3-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d5cb3-138">Content-Type</span></span>  | <span data-ttu-id="d5cb3-139">string</span><span class="sxs-lookup"><span data-stu-id="d5cb3-139">string</span></span>   | <span data-ttu-id="d5cb3-p104">application/json. Required.</span><span class="sxs-lookup"><span data-stu-id="d5cb3-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="d5cb3-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="d5cb3-142">Request body</span></span>

| <span data-ttu-id="d5cb3-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5cb3-143">Parameter</span></span> | <span data-ttu-id="d5cb3-144">型</span><span class="sxs-lookup"><span data-stu-id="d5cb3-144">Type</span></span> | <span data-ttu-id="d5cb3-145">説明</span><span class="sxs-lookup"><span data-stu-id="d5cb3-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="d5cb3-146">コメント</span><span class="sxs-lookup"><span data-stu-id="d5cb3-146">Comment</span></span>       | <span data-ttu-id="d5cb3-147">文字列</span><span class="sxs-lookup"><span data-stu-id="d5cb3-147">String</span></span>   | <span data-ttu-id="d5cb3-148">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="d5cb3-149">コマンド</span><span class="sxs-lookup"><span data-stu-id="d5cb3-149">Commands</span></span>      | <span data-ttu-id="d5cb3-150">配列</span><span class="sxs-lookup"><span data-stu-id="d5cb3-150">Array</span></span>    | <span data-ttu-id="d5cb3-151">実行するコマンド。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-151">Commands to run.</span></span> <span data-ttu-id="d5cb3-152">使用できる値は PutFile、RunScript、GetFile です。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="d5cb3-153">コマンド:</span><span class="sxs-lookup"><span data-stu-id="d5cb3-153">Commands:</span></span>

| <span data-ttu-id="d5cb3-154">コマンドの種類</span><span class="sxs-lookup"><span data-stu-id="d5cb3-154">Command Type</span></span> | <span data-ttu-id="d5cb3-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d5cb3-155">Parameters</span></span>                                                                          | <span data-ttu-id="d5cb3-156">説明</span><span class="sxs-lookup"><span data-stu-id="d5cb3-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d5cb3-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="d5cb3-157">PutFile</span></span>      | <span data-ttu-id="d5cb3-158">キー: FileName</span><span class="sxs-lookup"><span data-stu-id="d5cb3-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="d5cb3-159">値: \<file name\></span><span class="sxs-lookup"><span data-stu-id="d5cb3-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="d5cb3-160">ライブラリからデバイスにファイルを置く。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="d5cb3-161">ファイルは作業フォルダーに保存され、デバイスが既定で再起動すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="d5cb3-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="d5cb3-162">RunScript</span></span>    | <span data-ttu-id="d5cb3-163">キー: ScriptName</span><span class="sxs-lookup"><span data-stu-id="d5cb3-163">Key: ScriptName</span></span><br><span data-ttu-id="d5cb3-164">値: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="d5cb3-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="d5cb3-165">キー: Args</span><span class="sxs-lookup"><span data-stu-id="d5cb3-165">Key: Args</span></span>  <br> <span data-ttu-id="d5cb3-166">値: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="d5cb3-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="d5cb3-167">デバイス上のライブラリからスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="d5cb3-168">Args パラメーターはスクリプトに渡されます。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="d5cb3-169">10 分後のタイムアウト。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="d5cb3-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="d5cb3-170">GetFile</span></span>      | <span data-ttu-id="d5cb3-171">キー: パス</span><span class="sxs-lookup"><span data-stu-id="d5cb3-171">Key: Path</span></span> <br> <span data-ttu-id="d5cb3-172">値: \<File path\></span><span class="sxs-lookup"><span data-stu-id="d5cb3-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="d5cb3-173">デバイスからファイルを収集します。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-173">Collect file from a device.</span></span> <span data-ttu-id="d5cb3-174">注: パス内の円記号はエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="d5cb3-175">応答</span><span class="sxs-lookup"><span data-stu-id="d5cb3-175">Response</span></span>

-   <span data-ttu-id="d5cb3-176">成功した場合、このメソッドは 200 Ok を返します。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="d5cb3-177">アクション エンティティ。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-177">Action entity.</span></span> <span data-ttu-id="d5cb3-178">指定した ID を持つコンピューターが見つからない場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="d5cb3-179">例</span><span class="sxs-lookup"><span data-stu-id="d5cb3-179">Example</span></span>

<span data-ttu-id="d5cb3-180">**要求**</span><span class="sxs-lookup"><span data-stu-id="d5cb3-180">**Request**</span></span>

<span data-ttu-id="d5cb3-181">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="d5cb3-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="d5cb3-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="d5cb3-183">**応答**</span><span class="sxs-lookup"><span data-stu-id="d5cb3-183">**Response**</span></span>

<span data-ttu-id="d5cb3-184">以下は、応答の例です。</span><span class="sxs-lookup"><span data-stu-id="d5cb3-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="d5cb3-185">コンテンツタイプ: application/json</span><span class="sxs-lookup"><span data-stu-id="d5cb3-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="d5cb3-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5cb3-186">Related topics</span></span>
- [<span data-ttu-id="d5cb3-187">コンピューター アクション API の取得</span><span class="sxs-lookup"><span data-stu-id="d5cb3-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="d5cb3-188">ライブ応答の結果を取得する</span><span class="sxs-lookup"><span data-stu-id="d5cb3-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="d5cb3-189">コンピューターの操作をキャンセルする</span><span class="sxs-lookup"><span data-stu-id="d5cb3-189">Cancel machine action</span></span>](cancel-machine-action.md)
