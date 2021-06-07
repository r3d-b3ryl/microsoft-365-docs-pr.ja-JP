---
title: アプリ制限 API の削除
description: この API を使用して、アプリケーションからの制限の実行からの削除に関連する呼び出しを作成します。
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 989e44647a5f0661bfdefa184c6c26f4cdf2b456
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770879"
---
# <a name="remove-app-restriction-api"></a><span data-ttu-id="287ca-104">アプリ制限 API の削除</span><span class="sxs-lookup"><span data-stu-id="287ca-104">Remove app restriction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="287ca-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="287ca-105">**Applies to:**</span></span>
- [<span data-ttu-id="287ca-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="287ca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="287ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="287ca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="287ca-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="287ca-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="287ca-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="287ca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="287ca-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="287ca-110">API description</span></span>
<span data-ttu-id="287ca-111">デバイス上の任意のアプリケーションの実行を有効にします。</span><span class="sxs-lookup"><span data-stu-id="287ca-111">Enable execution of any application on the device.</span></span>


## <a name="limitations"></a><span data-ttu-id="287ca-112">制限事項</span><span class="sxs-lookup"><span data-stu-id="287ca-112">Limitations</span></span>
1. <span data-ttu-id="287ca-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="287ca-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="287ca-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="287ca-114">Permissions</span></span>
<span data-ttu-id="287ca-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="287ca-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="287ca-116">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="287ca-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="287ca-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="287ca-117">Permission type</span></span> |   <span data-ttu-id="287ca-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="287ca-118">Permission</span></span>  |   <span data-ttu-id="287ca-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="287ca-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="287ca-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="287ca-120">Application</span></span> |   <span data-ttu-id="287ca-121">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="287ca-121">Machine.RestrictExecution</span></span> | <span data-ttu-id="287ca-122">'コードの実行を制限する'</span><span class="sxs-lookup"><span data-stu-id="287ca-122">'Restrict code execution'</span></span>
<span data-ttu-id="287ca-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="287ca-123">Delegated (work or school account)</span></span> | <span data-ttu-id="287ca-124">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="287ca-124">Machine.RestrictExecution</span></span> | <span data-ttu-id="287ca-125">'コードの実行を制限する'</span><span class="sxs-lookup"><span data-stu-id="287ca-125">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="287ca-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="287ca-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="287ca-127">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'Active 修復アクション' (詳細については、「役割の作成と管理 [」](user-roles.md) を参照してください)</span><span class="sxs-lookup"><span data-stu-id="287ca-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="287ca-128">ユーザーは、デバイス グループ設定に基づいてデバイスにアクセスする必要があります (詳細については、「 [デバイス](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="287ca-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="287ca-129">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="287ca-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unrestrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="287ca-130">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="287ca-130">Request headers</span></span>
<span data-ttu-id="287ca-131">名前</span><span class="sxs-lookup"><span data-stu-id="287ca-131">Name</span></span> | <span data-ttu-id="287ca-132">種類</span><span class="sxs-lookup"><span data-stu-id="287ca-132">Type</span></span> | <span data-ttu-id="287ca-133">説明</span><span class="sxs-lookup"><span data-stu-id="287ca-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="287ca-134">Authorization</span><span class="sxs-lookup"><span data-stu-id="287ca-134">Authorization</span></span> | <span data-ttu-id="287ca-135">String</span><span class="sxs-lookup"><span data-stu-id="287ca-135">String</span></span> | <span data-ttu-id="287ca-136">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="287ca-136">Bearer {token}.</span></span> <span data-ttu-id="287ca-137">**必須**</span><span class="sxs-lookup"><span data-stu-id="287ca-137">**Required**.</span></span>
<span data-ttu-id="287ca-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="287ca-138">Content-Type</span></span> | <span data-ttu-id="287ca-139">string</span><span class="sxs-lookup"><span data-stu-id="287ca-139">string</span></span> | <span data-ttu-id="287ca-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="287ca-140">application/json.</span></span> <span data-ttu-id="287ca-141">**必須**</span><span class="sxs-lookup"><span data-stu-id="287ca-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="287ca-142">要求本文</span><span class="sxs-lookup"><span data-stu-id="287ca-142">Request body</span></span>
<span data-ttu-id="287ca-143">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="287ca-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="287ca-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="287ca-144">Parameter</span></span> | <span data-ttu-id="287ca-145">種類</span><span class="sxs-lookup"><span data-stu-id="287ca-145">Type</span></span>    | <span data-ttu-id="287ca-146">説明</span><span class="sxs-lookup"><span data-stu-id="287ca-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="287ca-147">コメント</span><span class="sxs-lookup"><span data-stu-id="287ca-147">Comment</span></span> |   <span data-ttu-id="287ca-148">文字列</span><span class="sxs-lookup"><span data-stu-id="287ca-148">String</span></span> | <span data-ttu-id="287ca-149">アクションに関連付けるコメント。</span><span class="sxs-lookup"><span data-stu-id="287ca-149">Comment to associate with the action.</span></span> <span data-ttu-id="287ca-150">**必須**</span><span class="sxs-lookup"><span data-stu-id="287ca-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="287ca-151">応答</span><span class="sxs-lookup"><span data-stu-id="287ca-151">Response</span></span>
<span data-ttu-id="287ca-152">成功した場合、このメソッドは応答本文に 201 - Created response code and [Machine Action](machineaction.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="287ca-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="287ca-153">例</span><span class="sxs-lookup"><span data-stu-id="287ca-153">Example</span></span>

<span data-ttu-id="287ca-154">**要求**</span><span class="sxs-lookup"><span data-stu-id="287ca-154">**Request**</span></span>

<span data-ttu-id="287ca-155">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="287ca-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unrestrictCodeExecution 
```

```json
{
  "Comment": "Unrestrict code execution since machine was cleaned and validated"
}

```


<span data-ttu-id="287ca-156">デバイスでのコードの実行を制限するには、「アプリの実行を [制限する」を参照してください](restrict-code-execution.md)。</span><span class="sxs-lookup"><span data-stu-id="287ca-156">To restrict code execution on a device, see [Restrict app execution](restrict-code-execution.md).</span></span>
