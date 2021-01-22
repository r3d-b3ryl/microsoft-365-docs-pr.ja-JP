---
title: Microsoft 365 Defender インシデント API とインシデント リソースの種類
description: Microsoft 365 Defender の Incident リソースタイプのメソッドとプロパティについて説明します。
keywords: incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928356"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="6eee3-104">Microsoft 365 Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="6eee3-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6eee3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6eee3-105">**Applies to:**</span></span>

- <span data-ttu-id="6eee3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6eee3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eee3-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="6eee3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6eee3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="6eee3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6eee3-109">インシデント [は](incidents-overview.md) 、攻撃の説明に役立つ関連するアラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6eee3-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6eee3-110">組織内の異なるエンティティからのイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="6eee3-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6eee3-111">インシデント API を使用すると、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6eee3-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6eee3-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="6eee3-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6eee3-113">1 分あたり最大 50 件、または 1 時間あたり 1500 件の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="6eee3-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6eee3-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="6eee3-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6eee3-115">メソッド固有のクォータの詳細については、使用する方法に関するそれぞれの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eee3-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6eee3-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によってクォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6eee3-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6eee3-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6eee3-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6eee3-118">Permissions</span><span class="sxs-lookup"><span data-stu-id="6eee3-118">Permissions</span></span>

<span data-ttu-id="6eee3-119">インシデント API では、そのメソッドごとに異なる種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6eee3-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6eee3-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eee3-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6eee3-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="6eee3-121">Methods</span></span>

<span data-ttu-id="6eee3-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="6eee3-122">Method</span></span> | <span data-ttu-id="6eee3-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="6eee3-123">Return Type</span></span> | <span data-ttu-id="6eee3-124">説明</span><span class="sxs-lookup"><span data-stu-id="6eee3-124">Description</span></span>
-|-|-
[<span data-ttu-id="6eee3-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6eee3-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6eee3-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="6eee3-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6eee3-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6eee3-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6eee3-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="6eee3-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6eee3-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="6eee3-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6eee3-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="6eee3-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6eee3-131">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="6eee3-131">Request body, response, and examples</span></span>

<span data-ttu-id="6eee3-132">要求を作成する方法や応答を解析する方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eee3-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6eee3-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6eee3-133">Common properties</span></span>

<span data-ttu-id="6eee3-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6eee3-134">Property</span></span> | <span data-ttu-id="6eee3-135">種類</span><span class="sxs-lookup"><span data-stu-id="6eee3-135">Type</span></span> | <span data-ttu-id="6eee3-136">説明</span><span class="sxs-lookup"><span data-stu-id="6eee3-136">Description</span></span>
-|-|-
<span data-ttu-id="6eee3-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="6eee3-137">incidentId</span></span> | <span data-ttu-id="6eee3-138">long</span><span class="sxs-lookup"><span data-stu-id="6eee3-138">long</span></span> | <span data-ttu-id="6eee3-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="6eee3-139">Incident unique ID.</span></span>
<span data-ttu-id="6eee3-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="6eee3-140">redirectIncidentId</span></span> | <span data-ttu-id="6eee3-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="6eee3-141">nullable long</span></span> | <span data-ttu-id="6eee3-142">現在のインシデントがマージされたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="6eee3-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6eee3-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="6eee3-143">incidentName</span></span> | <span data-ttu-id="6eee3-144">string</span><span class="sxs-lookup"><span data-stu-id="6eee3-144">string</span></span> | <span data-ttu-id="6eee3-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="6eee3-145">The name of the Incident.</span></span>
<span data-ttu-id="6eee3-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="6eee3-146">createdTime</span></span> | <span data-ttu-id="6eee3-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6eee3-147">DateTimeOffset</span></span> | <span data-ttu-id="6eee3-148">インシデントが作成された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6eee3-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6eee3-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6eee3-149">lastUpdateTime</span></span> | <span data-ttu-id="6eee3-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6eee3-150">DateTimeOffset</span></span> | <span data-ttu-id="6eee3-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6eee3-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6eee3-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6eee3-152">assignedTo</span></span> | <span data-ttu-id="6eee3-153">string</span><span class="sxs-lookup"><span data-stu-id="6eee3-153">string</span></span> | <span data-ttu-id="6eee3-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="6eee3-154">Owner of the Incident.</span></span>
<span data-ttu-id="6eee3-155">severity</span><span class="sxs-lookup"><span data-stu-id="6eee3-155">severity</span></span> | <span data-ttu-id="6eee3-156">列挙</span><span class="sxs-lookup"><span data-stu-id="6eee3-156">Enum</span></span> | <span data-ttu-id="6eee3-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="6eee3-157">Severity of the Incident.</span></span> <span data-ttu-id="6eee3-158">使用できる値は ```UnSpecified``` 、 ```Informational``` 次 ```Low``` ```Medium``` のとおりです ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="6eee3-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6eee3-159">status</span><span class="sxs-lookup"><span data-stu-id="6eee3-159">status</span></span> | <span data-ttu-id="6eee3-160">列挙</span><span class="sxs-lookup"><span data-stu-id="6eee3-160">Enum</span></span> | <span data-ttu-id="6eee3-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="6eee3-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="6eee3-162">使用できる値は ```Active``` 、次 ```Resolved``` のとおりです ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="6eee3-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6eee3-163">classification</span><span class="sxs-lookup"><span data-stu-id="6eee3-163">classification</span></span> | <span data-ttu-id="6eee3-164">列挙</span><span class="sxs-lookup"><span data-stu-id="6eee3-164">Enum</span></span> | <span data-ttu-id="6eee3-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="6eee3-165">Specification of the incident.</span></span> <span data-ttu-id="6eee3-166">可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="6eee3-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6eee3-167">判断</span><span class="sxs-lookup"><span data-stu-id="6eee3-167">determination</span></span> | <span data-ttu-id="6eee3-168">列挙</span><span class="sxs-lookup"><span data-stu-id="6eee3-168">Enum</span></span> | <span data-ttu-id="6eee3-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6eee3-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="6eee3-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="6eee3-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6eee3-171">tags</span><span class="sxs-lookup"><span data-stu-id="6eee3-171">tags</span></span> | <span data-ttu-id="6eee3-172">string List</span><span class="sxs-lookup"><span data-stu-id="6eee3-172">string List</span></span> | <span data-ttu-id="6eee3-173">インシデント タグのリスト。</span><span class="sxs-lookup"><span data-stu-id="6eee3-173">List of Incident tags.</span></span>
<span data-ttu-id="6eee3-174">アラート</span><span class="sxs-lookup"><span data-stu-id="6eee3-174">alerts</span></span> | <span data-ttu-id="6eee3-175">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="6eee3-175">Alert List</span></span> | <span data-ttu-id="6eee3-176">関連するアラートのリスト。</span><span class="sxs-lookup"><span data-stu-id="6eee3-176">List of related alerts.</span></span> <span data-ttu-id="6eee3-177">インシデント一覧 API [ドキュメントの例を](api-list-incidents.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eee3-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6eee3-178">関連記事</span><span class="sxs-lookup"><span data-stu-id="6eee3-178">Related articles</span></span>

- [<span data-ttu-id="6eee3-179">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="6eee3-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6eee3-180">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="6eee3-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6eee3-181">インシデント API を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6eee3-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6eee3-182">インシデント API を更新する</span><span class="sxs-lookup"><span data-stu-id="6eee3-182">Update incident API</span></span>](api-update-incidents.md)
