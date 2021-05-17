---
title: ウイルス対策スキャン API の実行
description: この API を使用して、デバイスでのウイルス対策スキャンの実行に関連する呼び出しを作成します。
keywords: apis、graph api、サポートされている api、分離からデバイスを削除する
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200211"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="12e13-104">ウイルス対策スキャン API の実行</span><span class="sxs-lookup"><span data-stu-id="12e13-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12e13-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="12e13-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="12e13-106">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="12e13-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="12e13-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="12e13-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="12e13-108">API の説明</span><span class="sxs-lookup"><span data-stu-id="12e13-108">API description</span></span>
<span data-ttu-id="12e13-109">デバイスMicrosoft Defender ウイルス対策スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="12e13-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="12e13-110">制限事項</span><span class="sxs-lookup"><span data-stu-id="12e13-110">Limitations</span></span>
1. <span data-ttu-id="12e13-111">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="12e13-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="12e13-112">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="12e13-112">Permissions</span></span>
<span data-ttu-id="12e13-113">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="12e13-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="12e13-114">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="12e13-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="12e13-115">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="12e13-115">Permission type</span></span> |   <span data-ttu-id="12e13-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="12e13-116">Permission</span></span>  |   <span data-ttu-id="12e13-117">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="12e13-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="12e13-118">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="12e13-118">Application</span></span> |   <span data-ttu-id="12e13-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="12e13-119">Machine.Scan</span></span> |  <span data-ttu-id="12e13-120">'スキャン マシン'</span><span class="sxs-lookup"><span data-stu-id="12e13-120">'Scan machine'</span></span>
<span data-ttu-id="12e13-121">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="12e13-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="12e13-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="12e13-122">Machine.Scan</span></span> |  <span data-ttu-id="12e13-123">'スキャン マシン'</span><span class="sxs-lookup"><span data-stu-id="12e13-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="12e13-124">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="12e13-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="12e13-125">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="12e13-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="12e13-126">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="12e13-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="12e13-127">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="12e13-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="12e13-128">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="12e13-128">Request headers</span></span>

<span data-ttu-id="12e13-129">名前</span><span class="sxs-lookup"><span data-stu-id="12e13-129">Name</span></span> | <span data-ttu-id="12e13-130">型</span><span class="sxs-lookup"><span data-stu-id="12e13-130">Type</span></span> | <span data-ttu-id="12e13-131">説明</span><span class="sxs-lookup"><span data-stu-id="12e13-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="12e13-132">Authorization</span><span class="sxs-lookup"><span data-stu-id="12e13-132">Authorization</span></span> | <span data-ttu-id="12e13-133">String</span><span class="sxs-lookup"><span data-stu-id="12e13-133">String</span></span> | <span data-ttu-id="12e13-134">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="12e13-134">Bearer {token}.</span></span> <span data-ttu-id="12e13-135">**必須**</span><span class="sxs-lookup"><span data-stu-id="12e13-135">**Required**.</span></span>
<span data-ttu-id="12e13-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="12e13-136">Content-Type</span></span> | <span data-ttu-id="12e13-137">string</span><span class="sxs-lookup"><span data-stu-id="12e13-137">string</span></span> | <span data-ttu-id="12e13-138">application/json</span><span class="sxs-lookup"><span data-stu-id="12e13-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="12e13-139">要求本文</span><span class="sxs-lookup"><span data-stu-id="12e13-139">Request body</span></span>
<span data-ttu-id="12e13-140">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="12e13-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="12e13-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12e13-141">Parameter</span></span> | <span data-ttu-id="12e13-142">型</span><span class="sxs-lookup"><span data-stu-id="12e13-142">Type</span></span>    | <span data-ttu-id="12e13-143">説明</span><span class="sxs-lookup"><span data-stu-id="12e13-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="12e13-144">コメント</span><span class="sxs-lookup"><span data-stu-id="12e13-144">Comment</span></span> |   <span data-ttu-id="12e13-145">文字列</span><span class="sxs-lookup"><span data-stu-id="12e13-145">String</span></span> | <span data-ttu-id="12e13-146">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="12e13-146">Comment to associate with the action.</span></span> <span data-ttu-id="12e13-147">**必須**</span><span class="sxs-lookup"><span data-stu-id="12e13-147">**Required**.</span></span>
<span data-ttu-id="12e13-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="12e13-148">ScanType</span></span>|   <span data-ttu-id="12e13-149">String</span><span class="sxs-lookup"><span data-stu-id="12e13-149">String</span></span>  | <span data-ttu-id="12e13-150">スキャンの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="12e13-150">Defines the type of the Scan.</span></span> <span data-ttu-id="12e13-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="12e13-151">**Required**.</span></span>

<span data-ttu-id="12e13-152">**ScanType** は、実行するスキャンの種類を制御し、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="12e13-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="12e13-153">**クイック** – デバイスでクイック スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="12e13-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="12e13-154">**[完全** ] – デバイスでフル スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="12e13-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="12e13-155">応答</span><span class="sxs-lookup"><span data-stu-id="12e13-155">Response</span></span>
<span data-ttu-id="12e13-156">成功した場合、このメソッドは応答本文に 201、Created 応答コード _、MachineAction_ オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="12e13-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="12e13-157">例</span><span class="sxs-lookup"><span data-stu-id="12e13-157">Example</span></span>

<span data-ttu-id="12e13-158">**要求**</span><span class="sxs-lookup"><span data-stu-id="12e13-158">**Request**</span></span>

<span data-ttu-id="12e13-159">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="12e13-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

