---
title: Microsoft 365 Defender インシデント API とインシデント リソースの種類
description: Microsoft 365 Defender の Incident リソースタイプのメソッドとプロパティについて説明します
keywords: incident, incidents, api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719336"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="f54a8-104">Microsoft 365 Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="f54a8-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f54a8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f54a8-105">**Applies to:**</span></span>

- <span data-ttu-id="f54a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f54a8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f54a8-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="f54a8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f54a8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="f54a8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f54a8-109">インシデント [は](incidents-overview.md) 、攻撃の説明に役立つ関連するアラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f54a8-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="f54a8-110">組織内の異なるエンティティからのイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="f54a8-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f54a8-111">インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f54a8-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="f54a8-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="f54a8-112">Quotas and resource allocation</span></span>

<span data-ttu-id="f54a8-113">1 分あたり最大 50 件、または 1 時間あたり 1500 件の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f54a8-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="f54a8-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="f54a8-114">Each method also has its own quotas.</span></span> <span data-ttu-id="f54a8-115">メソッド固有のクォータの詳細については、使用する方法に関するそれぞれの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f54a8-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="f54a8-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によってクォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f54a8-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="f54a8-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f54a8-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="f54a8-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f54a8-118">Permissions</span></span>

<span data-ttu-id="f54a8-119">インシデント API では、そのメソッドごとに異なる種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f54a8-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="f54a8-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f54a8-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="f54a8-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="f54a8-121">Methods</span></span>

<span data-ttu-id="f54a8-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="f54a8-122">Method</span></span> | <span data-ttu-id="f54a8-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="f54a8-123">Return Type</span></span> | <span data-ttu-id="f54a8-124">説明</span><span class="sxs-lookup"><span data-stu-id="f54a8-124">Description</span></span>
-|-|-
[<span data-ttu-id="f54a8-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f54a8-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="f54a8-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="f54a8-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="f54a8-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="f54a8-127">Get a list of incidents.</span></span>
[<span data-ttu-id="f54a8-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="f54a8-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="f54a8-129">Incident</span><span class="sxs-lookup"><span data-stu-id="f54a8-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="f54a8-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="f54a8-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="f54a8-131">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="f54a8-131">Request body, response, and examples</span></span>

<span data-ttu-id="f54a8-132">要求を作成する方法や応答を解析する方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f54a8-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="f54a8-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="f54a8-133">Common properties</span></span>

<span data-ttu-id="f54a8-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f54a8-134">Property</span></span> | <span data-ttu-id="f54a8-135">型</span><span class="sxs-lookup"><span data-stu-id="f54a8-135">Type</span></span> | <span data-ttu-id="f54a8-136">説明</span><span class="sxs-lookup"><span data-stu-id="f54a8-136">Description</span></span>
-|-|-
<span data-ttu-id="f54a8-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="f54a8-137">incidentId</span></span> | <span data-ttu-id="f54a8-138">long</span><span class="sxs-lookup"><span data-stu-id="f54a8-138">long</span></span> | <span data-ttu-id="f54a8-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="f54a8-139">Incident unique ID.</span></span>
<span data-ttu-id="f54a8-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f54a8-140">redirectIncidentId</span></span> | <span data-ttu-id="f54a8-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="f54a8-141">nullable long</span></span> | <span data-ttu-id="f54a8-142">現在のインシデントがマージされたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="f54a8-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="f54a8-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="f54a8-143">incidentName</span></span> | <span data-ttu-id="f54a8-144">string</span><span class="sxs-lookup"><span data-stu-id="f54a8-144">string</span></span> | <span data-ttu-id="f54a8-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="f54a8-145">The name of the Incident.</span></span>
<span data-ttu-id="f54a8-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="f54a8-146">createdTime</span></span> | <span data-ttu-id="f54a8-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f54a8-147">DateTimeOffset</span></span> | <span data-ttu-id="f54a8-148">インシデントが作成された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f54a8-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="f54a8-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f54a8-149">lastUpdateTime</span></span> | <span data-ttu-id="f54a8-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f54a8-150">DateTimeOffset</span></span> | <span data-ttu-id="f54a8-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f54a8-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="f54a8-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f54a8-152">assignedTo</span></span> | <span data-ttu-id="f54a8-153">string</span><span class="sxs-lookup"><span data-stu-id="f54a8-153">string</span></span> | <span data-ttu-id="f54a8-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="f54a8-154">Owner of the Incident.</span></span>
<span data-ttu-id="f54a8-155">severity</span><span class="sxs-lookup"><span data-stu-id="f54a8-155">severity</span></span> | <span data-ttu-id="f54a8-156">列挙</span><span class="sxs-lookup"><span data-stu-id="f54a8-156">Enum</span></span> | <span data-ttu-id="f54a8-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="f54a8-157">Severity of the Incident.</span></span> <span data-ttu-id="f54a8-158">使用できる値は ```UnSpecified``` 、 ```Informational``` 次 ```Low``` ```Medium``` のとおりです ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="f54a8-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="f54a8-159">status</span><span class="sxs-lookup"><span data-stu-id="f54a8-159">status</span></span> | <span data-ttu-id="f54a8-160">列挙</span><span class="sxs-lookup"><span data-stu-id="f54a8-160">Enum</span></span> | <span data-ttu-id="f54a8-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="f54a8-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="f54a8-162">使用できる値は ```Active``` 、次 ```Resolved``` のとおりです ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="f54a8-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="f54a8-163">classification</span><span class="sxs-lookup"><span data-stu-id="f54a8-163">classification</span></span> | <span data-ttu-id="f54a8-164">列挙</span><span class="sxs-lookup"><span data-stu-id="f54a8-164">Enum</span></span> | <span data-ttu-id="f54a8-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="f54a8-165">Specification of the incident.</span></span> <span data-ttu-id="f54a8-166">可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="f54a8-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="f54a8-167">判断</span><span class="sxs-lookup"><span data-stu-id="f54a8-167">determination</span></span> | <span data-ttu-id="f54a8-168">列挙</span><span class="sxs-lookup"><span data-stu-id="f54a8-168">Enum</span></span> | <span data-ttu-id="f54a8-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f54a8-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="f54a8-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="f54a8-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="f54a8-171">tags</span><span class="sxs-lookup"><span data-stu-id="f54a8-171">tags</span></span> | <span data-ttu-id="f54a8-172">string List</span><span class="sxs-lookup"><span data-stu-id="f54a8-172">string List</span></span> | <span data-ttu-id="f54a8-173">インシデント タグのリスト。</span><span class="sxs-lookup"><span data-stu-id="f54a8-173">List of Incident tags.</span></span>
<span data-ttu-id="f54a8-174">アラート</span><span class="sxs-lookup"><span data-stu-id="f54a8-174">alerts</span></span> | <span data-ttu-id="f54a8-175">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="f54a8-175">Alert List</span></span> | <span data-ttu-id="f54a8-176">関連するアラートのリスト。</span><span class="sxs-lookup"><span data-stu-id="f54a8-176">List of related alerts.</span></span> <span data-ttu-id="f54a8-177">インシデント一覧 API ドキュメント [の例を](api-list-incidents.md) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="f54a8-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f54a8-178">関連記事</span><span class="sxs-lookup"><span data-stu-id="f54a8-178">Related articles</span></span>

- [<span data-ttu-id="f54a8-179">Microsoft 365 Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="f54a8-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f54a8-180">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="f54a8-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f54a8-181">インシデント API を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f54a8-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="f54a8-182">インシデント API を更新する</span><span class="sxs-lookup"><span data-stu-id="f54a8-182">Update incident API</span></span>](api-update-incidents.md)
