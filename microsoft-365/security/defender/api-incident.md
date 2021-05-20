---
title: Microsoft 365Defender インシデント API とインシデント リソースの種類
description: Defender のインシデント リソースの種類のメソッドとプロパティMicrosoft 365する
keywords: インシデント、インシデント、API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572587"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="2946e-104">Microsoft 365Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="2946e-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2946e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2946e-105">**Applies to:**</span></span>

- <span data-ttu-id="2946e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2946e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2946e-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="2946e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2946e-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="2946e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2946e-109">インシデント [とは](incidents-overview.md) 、攻撃の説明に役立つ関連アラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="2946e-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="2946e-110">組織内の異なるエンティティからのイベントは、Defender によって自動的にMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="2946e-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="2946e-111">インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2946e-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="2946e-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="2946e-112">Quotas and resource allocation</span></span>

<span data-ttu-id="2946e-113">1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="2946e-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="2946e-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="2946e-114">Each method also has its own quotas.</span></span> <span data-ttu-id="2946e-115">メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2946e-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="2946e-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2946e-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="2946e-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2946e-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="2946e-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2946e-118">Permissions</span></span>

<span data-ttu-id="2946e-119">インシデント API では、それぞれのメソッドに対してさまざまな種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2946e-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="2946e-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2946e-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="2946e-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="2946e-121">Methods</span></span>

<span data-ttu-id="2946e-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="2946e-122">Method</span></span> | <span data-ttu-id="2946e-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="2946e-123">Return Type</span></span> | <span data-ttu-id="2946e-124">説明</span><span class="sxs-lookup"><span data-stu-id="2946e-124">Description</span></span>
-|-|-
[<span data-ttu-id="2946e-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="2946e-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="2946e-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="2946e-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="2946e-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2946e-127">Get a list of incidents.</span></span>
[<span data-ttu-id="2946e-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="2946e-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="2946e-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="2946e-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="2946e-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="2946e-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="2946e-131">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="2946e-131">Request body, response, and examples</span></span>

<span data-ttu-id="2946e-132">要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2946e-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="2946e-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="2946e-133">Common properties</span></span>

<span data-ttu-id="2946e-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2946e-134">Property</span></span> | <span data-ttu-id="2946e-135">型</span><span class="sxs-lookup"><span data-stu-id="2946e-135">Type</span></span> | <span data-ttu-id="2946e-136">説明</span><span class="sxs-lookup"><span data-stu-id="2946e-136">Description</span></span>
-|-|-
<span data-ttu-id="2946e-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="2946e-137">incidentId</span></span> | <span data-ttu-id="2946e-138">long</span><span class="sxs-lookup"><span data-stu-id="2946e-138">long</span></span> | <span data-ttu-id="2946e-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="2946e-139">Incident unique ID.</span></span>
<span data-ttu-id="2946e-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="2946e-140">redirectIncidentId</span></span> | <span data-ttu-id="2946e-141">null 許容長</span><span class="sxs-lookup"><span data-stu-id="2946e-141">nullable long</span></span> | <span data-ttu-id="2946e-142">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="2946e-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="2946e-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="2946e-143">incidentName</span></span> | <span data-ttu-id="2946e-144">string</span><span class="sxs-lookup"><span data-stu-id="2946e-144">string</span></span> | <span data-ttu-id="2946e-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="2946e-145">The name of the Incident.</span></span>
<span data-ttu-id="2946e-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="2946e-146">createdTime</span></span> | <span data-ttu-id="2946e-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2946e-147">DateTimeOffset</span></span> | <span data-ttu-id="2946e-148">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="2946e-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="2946e-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="2946e-149">lastUpdateTime</span></span> | <span data-ttu-id="2946e-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2946e-150">DateTimeOffset</span></span> | <span data-ttu-id="2946e-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="2946e-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="2946e-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2946e-152">assignedTo</span></span> | <span data-ttu-id="2946e-153">string</span><span class="sxs-lookup"><span data-stu-id="2946e-153">string</span></span> | <span data-ttu-id="2946e-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="2946e-154">Owner of the Incident.</span></span>
<span data-ttu-id="2946e-155">severity</span><span class="sxs-lookup"><span data-stu-id="2946e-155">severity</span></span> | <span data-ttu-id="2946e-156">列挙</span><span class="sxs-lookup"><span data-stu-id="2946e-156">Enum</span></span> | <span data-ttu-id="2946e-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="2946e-157">Severity of the Incident.</span></span> <span data-ttu-id="2946e-158">使用できる値は ```UnSpecified``` ```Informational``` ```Low``` 、、、、、 ```Medium``` および ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="2946e-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="2946e-159">status</span><span class="sxs-lookup"><span data-stu-id="2946e-159">status</span></span> | <span data-ttu-id="2946e-160">列挙</span><span class="sxs-lookup"><span data-stu-id="2946e-160">Enum</span></span> | <span data-ttu-id="2946e-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="2946e-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="2946e-162">使用できる値は ```Active``` ```Resolved``` 、、、および ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="2946e-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="2946e-163">classification</span><span class="sxs-lookup"><span data-stu-id="2946e-163">classification</span></span> | <span data-ttu-id="2946e-164">列挙</span><span class="sxs-lookup"><span data-stu-id="2946e-164">Enum</span></span> | <span data-ttu-id="2946e-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="2946e-165">Specification of the incident.</span></span> <span data-ttu-id="2946e-166">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="2946e-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="2946e-167">決定</span><span class="sxs-lookup"><span data-stu-id="2946e-167">determination</span></span> | <span data-ttu-id="2946e-168">列挙</span><span class="sxs-lookup"><span data-stu-id="2946e-168">Enum</span></span> | <span data-ttu-id="2946e-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2946e-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="2946e-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="2946e-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="2946e-171">tags</span><span class="sxs-lookup"><span data-stu-id="2946e-171">tags</span></span> | <span data-ttu-id="2946e-172">string List</span><span class="sxs-lookup"><span data-stu-id="2946e-172">string List</span></span> | <span data-ttu-id="2946e-173">インシデント タグの一覧。</span><span class="sxs-lookup"><span data-stu-id="2946e-173">List of Incident tags.</span></span>
<span data-ttu-id="2946e-174">comments</span><span class="sxs-lookup"><span data-stu-id="2946e-174">comments</span></span> | <span data-ttu-id="2946e-175">インシデント コメントの一覧</span><span class="sxs-lookup"><span data-stu-id="2946e-175">List of incident comments</span></span> | <span data-ttu-id="2946e-176">インシデント コメント オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2946e-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="2946e-177">アラート</span><span class="sxs-lookup"><span data-stu-id="2946e-177">alerts</span></span> | <span data-ttu-id="2946e-178">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="2946e-178">Alert List</span></span> | <span data-ttu-id="2946e-179">関連するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="2946e-179">List of related alerts.</span></span> <span data-ttu-id="2946e-180">「List Incidents [API」のドキュメントの例](api-list-incidents.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2946e-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2946e-181">関連記事</span><span class="sxs-lookup"><span data-stu-id="2946e-181">Related articles</span></span>

- [<span data-ttu-id="2946e-182">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="2946e-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="2946e-183">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="2946e-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2946e-184">インシデント API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="2946e-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="2946e-185">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="2946e-185">Update incident API</span></span>](api-update-incidents.md)
