---
title: マシン タグ API の追加と削除
description: Add or Remove machine tags API を使用して、Microsoft Defender for Endpoint のマシンのタグを追加または削除する方法について説明します。
keywords: apis、graph api、サポートされている API、タグ、マシン タグ
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199779"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="240ab-104">マシン タグ API の追加と削除</span><span class="sxs-lookup"><span data-stu-id="240ab-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="240ab-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="240ab-105">**Applies to:**</span></span>

- [<span data-ttu-id="240ab-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="240ab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="240ab-107">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="240ab-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="240ab-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="240ab-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="240ab-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="240ab-109">API description</span></span>

<span data-ttu-id="240ab-110">特定のコンピューターにタグを追加または削除 [します](machine.md)。</span><span class="sxs-lookup"><span data-stu-id="240ab-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="240ab-111">制限事項</span><span class="sxs-lookup"><span data-stu-id="240ab-111">Limitations</span></span>

1. <span data-ttu-id="240ab-112">構成済みの保持期間に従って最後に表示されたコンピューターに投稿できます。</span><span class="sxs-lookup"><span data-stu-id="240ab-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="240ab-113">この API のレート制限は、1 分あたり 100 回の呼び出しと 1 時間あたり 1500 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="240ab-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="240ab-114">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="240ab-114">Permissions</span></span>

<span data-ttu-id="240ab-115">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="240ab-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="240ab-116">アクセス許可の選択方法などの詳細については [、「Use Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="240ab-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="240ab-117">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="240ab-117">Permission type</span></span> |    <span data-ttu-id="240ab-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="240ab-118">Permission</span></span>    |    <span data-ttu-id="240ab-119">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="240ab-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="240ab-120">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="240ab-120">Application</span></span> |    <span data-ttu-id="240ab-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="240ab-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="240ab-122">'すべてのコンピューター情報の読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="240ab-122">'Read and write all machine information'</span></span>
<span data-ttu-id="240ab-123">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="240ab-123">Delegated (work or school account)</span></span> | <span data-ttu-id="240ab-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="240ab-124">Machine.ReadWrite</span></span> | <span data-ttu-id="240ab-125">'コンピューター情報の読み取りおよび書き込み'</span><span class="sxs-lookup"><span data-stu-id="240ab-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="240ab-126">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="240ab-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="240ab-127">ユーザーには、少なくとも次の役割のアクセス許可が必要です。'セキュリティ設定の管理' 。</span><span class="sxs-lookup"><span data-stu-id="240ab-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="240ab-128">詳細については、「役割の [作成と管理」を](user-roles.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="240ab-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="240ab-129">ユーザーは、コンピューター グループの設定に基づいてコンピューターにアクセスする必要があります (詳細については、「 [コンピューター](machine-groups.md) グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="240ab-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="240ab-130">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="240ab-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="240ab-131">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="240ab-131">Request headers</span></span>

<span data-ttu-id="240ab-132">名前</span><span class="sxs-lookup"><span data-stu-id="240ab-132">Name</span></span> | <span data-ttu-id="240ab-133">型</span><span class="sxs-lookup"><span data-stu-id="240ab-133">Type</span></span> | <span data-ttu-id="240ab-134">説明</span><span class="sxs-lookup"><span data-stu-id="240ab-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="240ab-135">Authorization</span><span class="sxs-lookup"><span data-stu-id="240ab-135">Authorization</span></span> | <span data-ttu-id="240ab-136">String</span><span class="sxs-lookup"><span data-stu-id="240ab-136">String</span></span> | <span data-ttu-id="240ab-137">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="240ab-137">Bearer {token}.</span></span> <span data-ttu-id="240ab-138">**必須**</span><span class="sxs-lookup"><span data-stu-id="240ab-138">**Required**.</span></span>
<span data-ttu-id="240ab-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="240ab-139">Content-Type</span></span> | <span data-ttu-id="240ab-140">string</span><span class="sxs-lookup"><span data-stu-id="240ab-140">string</span></span> | <span data-ttu-id="240ab-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="240ab-141">application/json.</span></span> <span data-ttu-id="240ab-142">**必須**</span><span class="sxs-lookup"><span data-stu-id="240ab-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="240ab-143">要求本文</span><span class="sxs-lookup"><span data-stu-id="240ab-143">Request body</span></span>

<span data-ttu-id="240ab-144">要求本文で、JSON オブジェクトに次のパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="240ab-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="240ab-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="240ab-145">Parameter</span></span> |    <span data-ttu-id="240ab-146">型</span><span class="sxs-lookup"><span data-stu-id="240ab-146">Type</span></span>    | <span data-ttu-id="240ab-147">説明</span><span class="sxs-lookup"><span data-stu-id="240ab-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="240ab-148">値</span><span class="sxs-lookup"><span data-stu-id="240ab-148">Value</span></span> |    <span data-ttu-id="240ab-149">String</span><span class="sxs-lookup"><span data-stu-id="240ab-149">String</span></span> |    <span data-ttu-id="240ab-150">タグ名。</span><span class="sxs-lookup"><span data-stu-id="240ab-150">The tag name.</span></span> <span data-ttu-id="240ab-151">**必須**</span><span class="sxs-lookup"><span data-stu-id="240ab-151">**Required**.</span></span>
<span data-ttu-id="240ab-152">Action</span><span class="sxs-lookup"><span data-stu-id="240ab-152">Action</span></span>    | <span data-ttu-id="240ab-153">列挙</span><span class="sxs-lookup"><span data-stu-id="240ab-153">Enum</span></span> |    <span data-ttu-id="240ab-154">追加または削除。</span><span class="sxs-lookup"><span data-stu-id="240ab-154">Add or Remove.</span></span> <span data-ttu-id="240ab-155">使用できる値は、'Add' または 'Remove' です。</span><span class="sxs-lookup"><span data-stu-id="240ab-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="240ab-156">**必須**</span><span class="sxs-lookup"><span data-stu-id="240ab-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="240ab-157">応答</span><span class="sxs-lookup"><span data-stu-id="240ab-157">Response</span></span>

<span data-ttu-id="240ab-158">成功した場合、このメソッドは 200 - OK 応答コードと更新された Machine を応答本文で返します。</span><span class="sxs-lookup"><span data-stu-id="240ab-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="240ab-159">例</span><span class="sxs-lookup"><span data-stu-id="240ab-159">Example</span></span>

<span data-ttu-id="240ab-160">**要求**</span><span class="sxs-lookup"><span data-stu-id="240ab-160">**Request**</span></span>

<span data-ttu-id="240ab-161">コンピューター タグを追加する要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="240ab-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="240ab-162">コンピューター タグを削除するには、要求本文で [追加] ではなく [アクション] を [削除] に設定します。</span><span class="sxs-lookup"><span data-stu-id="240ab-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
