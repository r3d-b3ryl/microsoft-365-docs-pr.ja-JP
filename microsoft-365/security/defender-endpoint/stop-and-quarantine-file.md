---
title: ファイル API の停止と検疫
description: デバイスでのファイルの実行を停止し、Microsoft Defender for Endpoint でファイルを削除する方法について説明します。 例を参照してください。
keywords: apis、graph api、サポートされている API、停止および検疫ファイル
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199731"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="d55e6-105">ファイル API の停止と検疫</span><span class="sxs-lookup"><span data-stu-id="d55e6-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d55e6-106">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d55e6-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="d55e6-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="d55e6-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d55e6-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d55e6-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="d55e6-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="d55e6-109">API description</span></span>
<span data-ttu-id="d55e6-110">デバイス上のファイルの実行を停止し、削除します。</span><span class="sxs-lookup"><span data-stu-id="d55e6-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="d55e6-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="d55e6-111">Limitations</span></span>
1. <span data-ttu-id="d55e6-112">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="d55e6-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="d55e6-113">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d55e6-113">Permissions</span></span>
<span data-ttu-id="d55e6-114">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d55e6-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d55e6-115">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d55e6-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d55e6-116">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="d55e6-116">Permission type</span></span> |   <span data-ttu-id="d55e6-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d55e6-117">Permission</span></span>  |   <span data-ttu-id="d55e6-118">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="d55e6-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d55e6-119">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d55e6-119">Application</span></span> |   <span data-ttu-id="d55e6-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="d55e6-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="d55e6-121">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="d55e6-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="d55e6-122">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="d55e6-122">Delegated (work or school account)</span></span> | <span data-ttu-id="d55e6-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="d55e6-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="d55e6-124">'Stop and Quarantine'</span><span class="sxs-lookup"><span data-stu-id="d55e6-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="d55e6-125">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="d55e6-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d55e6-126">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="d55e6-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="d55e6-127">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="d55e6-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d55e6-128">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="d55e6-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="d55e6-129">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="d55e6-129">Request headers</span></span>

<span data-ttu-id="d55e6-130">名前</span><span class="sxs-lookup"><span data-stu-id="d55e6-130">Name</span></span> | <span data-ttu-id="d55e6-131">型</span><span class="sxs-lookup"><span data-stu-id="d55e6-131">Type</span></span> | <span data-ttu-id="d55e6-132">説明</span><span class="sxs-lookup"><span data-stu-id="d55e6-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="d55e6-133">Authorization</span><span class="sxs-lookup"><span data-stu-id="d55e6-133">Authorization</span></span> | <span data-ttu-id="d55e6-134">String</span><span class="sxs-lookup"><span data-stu-id="d55e6-134">String</span></span> | <span data-ttu-id="d55e6-135">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="d55e6-135">Bearer {token}.</span></span> <span data-ttu-id="d55e6-136">**必須**</span><span class="sxs-lookup"><span data-stu-id="d55e6-136">**Required**.</span></span>
<span data-ttu-id="d55e6-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d55e6-137">Content-Type</span></span> | <span data-ttu-id="d55e6-138">string</span><span class="sxs-lookup"><span data-stu-id="d55e6-138">string</span></span> | <span data-ttu-id="d55e6-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="d55e6-139">application/json.</span></span> <span data-ttu-id="d55e6-140">**必須**</span><span class="sxs-lookup"><span data-stu-id="d55e6-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="d55e6-141">要求本文</span><span class="sxs-lookup"><span data-stu-id="d55e6-141">Request body</span></span>
<span data-ttu-id="d55e6-142">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="d55e6-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d55e6-143">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d55e6-143">Parameter</span></span> | <span data-ttu-id="d55e6-144">型</span><span class="sxs-lookup"><span data-stu-id="d55e6-144">Type</span></span>    | <span data-ttu-id="d55e6-145">説明</span><span class="sxs-lookup"><span data-stu-id="d55e6-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="d55e6-146">コメント</span><span class="sxs-lookup"><span data-stu-id="d55e6-146">Comment</span></span> |   <span data-ttu-id="d55e6-147">文字列</span><span class="sxs-lookup"><span data-stu-id="d55e6-147">String</span></span> |    <span data-ttu-id="d55e6-148">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="d55e6-148">Comment to associate with the action.</span></span> <span data-ttu-id="d55e6-149">**必須**</span><span class="sxs-lookup"><span data-stu-id="d55e6-149">**Required**.</span></span>
<span data-ttu-id="d55e6-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="d55e6-150">Sha1</span></span> |  <span data-ttu-id="d55e6-151">String</span><span class="sxs-lookup"><span data-stu-id="d55e6-151">String</span></span>   | <span data-ttu-id="d55e6-152">デバイスで停止して検疫するファイルの Sha1。</span><span class="sxs-lookup"><span data-stu-id="d55e6-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="d55e6-153">**必須**</span><span class="sxs-lookup"><span data-stu-id="d55e6-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="d55e6-154">応答</span><span class="sxs-lookup"><span data-stu-id="d55e6-154">Response</span></span>
<span data-ttu-id="d55e6-155">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="d55e6-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="d55e6-156">例</span><span class="sxs-lookup"><span data-stu-id="d55e6-156">Example</span></span>

<span data-ttu-id="d55e6-157">**要求**</span><span class="sxs-lookup"><span data-stu-id="d55e6-157">**Request**</span></span>

<span data-ttu-id="d55e6-158">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="d55e6-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
