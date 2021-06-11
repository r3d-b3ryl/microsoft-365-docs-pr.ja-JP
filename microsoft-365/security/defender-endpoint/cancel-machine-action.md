---
title: マシン アクション API のキャンセル
description: 既に起動されているコンピューターアクションをキャンセルする方法について
keywords: apis, graph api,
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
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879757"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="b931b-104">マシン アクション API のキャンセル</span><span class="sxs-lookup"><span data-stu-id="b931b-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b931b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b931b-105">**Applies to:**</span></span>
- [<span data-ttu-id="b931b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b931b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="b931b-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="b931b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b931b-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="b931b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b931b-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="b931b-109">API description</span></span>

<span data-ttu-id="b931b-110">(完了、キャンセル、失敗) まだ最終状態ではない既に起動されているコンピューターアクションをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="b931b-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="b931b-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="b931b-111">Limitations</span></span>

1.  <span data-ttu-id="b931b-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="b931b-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="b931b-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b931b-113">Permissions</span></span>

<span data-ttu-id="b931b-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b931b-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b931b-115">アクセス許可を選択する方法など、詳細については、「開始する」 [を参照してください](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="b931b-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="b931b-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="b931b-116">Permission    type</span></span>     |     <span data-ttu-id="b931b-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="b931b-117">Permission</span></span>     |    <span data-ttu-id="b931b-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="b931b-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="b931b-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b931b-119">Application</span></span>    |    <br><span data-ttu-id="b931b-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="b931b-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="b931b-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="b931b-121">Machine.Isolate</span></span>   <br><span data-ttu-id="b931b-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b931b-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="b931b-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="b931b-123">Machine.Scan</span></span><br>   <span data-ttu-id="b931b-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="b931b-124">Machine.Offboard</span></span><br>   <span data-ttu-id="b931b-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="b931b-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="b931b-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b931b-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="b931b-127">forensics の収集</span><span class="sxs-lookup"><span data-stu-id="b931b-127">Collect   forensics</span></span>   <br><span data-ttu-id="b931b-128">コンピューターを分離する</span><span class="sxs-lookup"><span data-stu-id="b931b-128">Isolate   machine</span></span><br><span data-ttu-id="b931b-129">コードの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="b931b-129">Restrict   code execution</span></span><br>  <span data-ttu-id="b931b-130">スキャン マシン</span><span class="sxs-lookup"><span data-stu-id="b931b-130">Scan   machine</span></span><br>  <span data-ttu-id="b931b-131">オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="b931b-131">Offboard   machine</span></span><br>   <span data-ttu-id="b931b-132">停止と検疫</span><span class="sxs-lookup"><span data-stu-id="b931b-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="b931b-133">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="b931b-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="b931b-134">委任 (仕事または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="b931b-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="b931b-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="b931b-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="b931b-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="b931b-136">Machine.Isolate</span></span>    <br><span data-ttu-id="b931b-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="b931b-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="b931b-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="b931b-138">Machine.Scan</span></span><br>   <span data-ttu-id="b931b-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="b931b-139">Machine.Offboard</span></span><br>   <span data-ttu-id="b931b-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="b931b-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="b931b-141">forensics の収集</span><span class="sxs-lookup"><span data-stu-id="b931b-141">Collect   forensics</span></span><br>   <span data-ttu-id="b931b-142">コンピューターを分離する</span><span class="sxs-lookup"><span data-stu-id="b931b-142">Isolate   machine</span></span><br>  <span data-ttu-id="b931b-143">コードの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="b931b-143">Restrict   code execution</span></span><br> <span data-ttu-id="b931b-144">スキャン マシン</span><span class="sxs-lookup"><span data-stu-id="b931b-144">Scan   machine</span></span><br><span data-ttu-id="b931b-145">オフボード マシン</span><span class="sxs-lookup"><span data-stu-id="b931b-145">Offboard   machine</span></span><br> <span data-ttu-id="b931b-146">停止と検疫</span><span class="sxs-lookup"><span data-stu-id="b931b-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="b931b-147">特定のコンピューターでライブ応答を実行する</span><span class="sxs-lookup"><span data-stu-id="b931b-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="b931b-148">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="b931b-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="b931b-149">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="b931b-149">Request headers</span></span>

| <span data-ttu-id="b931b-150">名前</span><span class="sxs-lookup"><span data-stu-id="b931b-150">Name</span></span>      | <span data-ttu-id="b931b-151">型</span><span class="sxs-lookup"><span data-stu-id="b931b-151">Type</span></span> | <span data-ttu-id="b931b-152">説明</span><span class="sxs-lookup"><span data-stu-id="b931b-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="b931b-153">Authorization</span><span class="sxs-lookup"><span data-stu-id="b931b-153">Authorization</span></span> | <span data-ttu-id="b931b-154">String</span><span class="sxs-lookup"><span data-stu-id="b931b-154">String</span></span>   | <span data-ttu-id="b931b-p103">ベアラー {トークン}。必須。</span><span class="sxs-lookup"><span data-stu-id="b931b-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="b931b-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b931b-157">Content-Type</span></span>  | <span data-ttu-id="b931b-158">string</span><span class="sxs-lookup"><span data-stu-id="b931b-158">string</span></span>   | <span data-ttu-id="b931b-p104">application/json. Required.</span><span class="sxs-lookup"><span data-stu-id="b931b-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="b931b-161">要求本文</span><span class="sxs-lookup"><span data-stu-id="b931b-161">Request body</span></span>

| <span data-ttu-id="b931b-162">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b931b-162">Parameter</span></span> | <span data-ttu-id="b931b-163">型</span><span class="sxs-lookup"><span data-stu-id="b931b-163">Type</span></span> | <span data-ttu-id="b931b-164">説明</span><span class="sxs-lookup"><span data-stu-id="b931b-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="b931b-165">コメント</span><span class="sxs-lookup"><span data-stu-id="b931b-165">Comment</span></span>       | <span data-ttu-id="b931b-166">文字列</span><span class="sxs-lookup"><span data-stu-id="b931b-166">String</span></span>   | <span data-ttu-id="b931b-167">キャンセル アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="b931b-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="b931b-168">応答</span><span class="sxs-lookup"><span data-stu-id="b931b-168">Response</span></span>

<span data-ttu-id="b931b-169">成功した場合、このメソッドは Machine Action エンティティを持つ 200 Ok 応答コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b931b-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="b931b-170">指定した ID を持つコンピューター アクション エンティティが見つからなかった場合 - 404 Not Found。</span><span class="sxs-lookup"><span data-stu-id="b931b-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b931b-171">例</span><span class="sxs-lookup"><span data-stu-id="b931b-171">Example</span></span>

<span data-ttu-id="b931b-172">**要求**</span><span class="sxs-lookup"><span data-stu-id="b931b-172">**Request**</span></span>

<span data-ttu-id="b931b-173">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="b931b-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="b931b-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b931b-174">Related topic</span></span>

- [<span data-ttu-id="b931b-175">コンピューター アクション API の取得</span><span class="sxs-lookup"><span data-stu-id="b931b-175">Get machine action API</span></span>](get-machineaction-object.md)