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
ms.openlocfilehash: 587d6107b0c09b2178311d8da6606968e7fda083
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730932"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="a70fb-104">Microsoft 365Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="a70fb-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a70fb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a70fb-105">**Applies to:**</span></span>

- [<span data-ttu-id="a70fb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a70fb-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="a70fb-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="a70fb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a70fb-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="a70fb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a70fb-109">インシデント [とは](incidents-overview.md) 、攻撃の説明に役立つ関連アラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a70fb-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="a70fb-110">組織内の異なるエンティティからのイベントは、Defender によって自動的にMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="a70fb-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="a70fb-111">インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a70fb-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="a70fb-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="a70fb-112">Quotas and resource allocation</span></span>

<span data-ttu-id="a70fb-113">1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="a70fb-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="a70fb-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="a70fb-114">Each method also has its own quotas.</span></span> <span data-ttu-id="a70fb-115">メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70fb-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="a70fb-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a70fb-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="a70fb-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a70fb-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="a70fb-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="a70fb-118">Permissions</span></span>

<span data-ttu-id="a70fb-119">インシデント API では、それぞれのメソッドに対してさまざまな種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a70fb-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="a70fb-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70fb-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="a70fb-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="a70fb-121">Methods</span></span>

<span data-ttu-id="a70fb-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="a70fb-122">Method</span></span> | <span data-ttu-id="a70fb-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a70fb-123">Return Type</span></span> | <span data-ttu-id="a70fb-124">説明</span><span class="sxs-lookup"><span data-stu-id="a70fb-124">Description</span></span>
-|-|-
[<span data-ttu-id="a70fb-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="a70fb-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="a70fb-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="a70fb-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="a70fb-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a70fb-127">Get a list of incidents.</span></span>
[<span data-ttu-id="a70fb-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="a70fb-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="a70fb-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="a70fb-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="a70fb-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="a70fb-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="a70fb-131">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="a70fb-131">Request body, response, and examples</span></span>

<span data-ttu-id="a70fb-132">要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70fb-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="a70fb-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="a70fb-133">Common properties</span></span>

<span data-ttu-id="a70fb-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a70fb-134">Property</span></span> | <span data-ttu-id="a70fb-135">型</span><span class="sxs-lookup"><span data-stu-id="a70fb-135">Type</span></span> | <span data-ttu-id="a70fb-136">説明</span><span class="sxs-lookup"><span data-stu-id="a70fb-136">Description</span></span>
-|-|-
<span data-ttu-id="a70fb-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="a70fb-137">incidentId</span></span> | <span data-ttu-id="a70fb-138">long</span><span class="sxs-lookup"><span data-stu-id="a70fb-138">long</span></span> | <span data-ttu-id="a70fb-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a70fb-139">Incident unique ID.</span></span>
<span data-ttu-id="a70fb-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="a70fb-140">redirectIncidentId</span></span> | <span data-ttu-id="a70fb-141">null 許容長</span><span class="sxs-lookup"><span data-stu-id="a70fb-141">nullable long</span></span> | <span data-ttu-id="a70fb-142">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="a70fb-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="a70fb-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="a70fb-143">incidentName</span></span> | <span data-ttu-id="a70fb-144">string</span><span class="sxs-lookup"><span data-stu-id="a70fb-144">string</span></span> | <span data-ttu-id="a70fb-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="a70fb-145">The name of the Incident.</span></span>
<span data-ttu-id="a70fb-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="a70fb-146">createdTime</span></span> | <span data-ttu-id="a70fb-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a70fb-147">DateTimeOffset</span></span> | <span data-ttu-id="a70fb-148">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="a70fb-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="a70fb-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="a70fb-149">lastUpdateTime</span></span> | <span data-ttu-id="a70fb-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a70fb-150">DateTimeOffset</span></span> | <span data-ttu-id="a70fb-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="a70fb-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="a70fb-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a70fb-152">assignedTo</span></span> | <span data-ttu-id="a70fb-153">string</span><span class="sxs-lookup"><span data-stu-id="a70fb-153">string</span></span> | <span data-ttu-id="a70fb-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="a70fb-154">Owner of the Incident.</span></span>
<span data-ttu-id="a70fb-155">severity</span><span class="sxs-lookup"><span data-stu-id="a70fb-155">severity</span></span> | <span data-ttu-id="a70fb-156">列挙</span><span class="sxs-lookup"><span data-stu-id="a70fb-156">Enum</span></span> | <span data-ttu-id="a70fb-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="a70fb-157">Severity of the Incident.</span></span> <span data-ttu-id="a70fb-158">使用できる値は ```UnSpecified``` ```Informational``` ```Low``` 、、、、、 ```Medium``` および ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="a70fb-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="a70fb-159">status</span><span class="sxs-lookup"><span data-stu-id="a70fb-159">status</span></span> | <span data-ttu-id="a70fb-160">列挙</span><span class="sxs-lookup"><span data-stu-id="a70fb-160">Enum</span></span> | <span data-ttu-id="a70fb-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="a70fb-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="a70fb-162">使用できる値は ```Active``` ```Resolved``` 、、、および ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="a70fb-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="a70fb-163">classification</span><span class="sxs-lookup"><span data-stu-id="a70fb-163">classification</span></span> | <span data-ttu-id="a70fb-164">列挙</span><span class="sxs-lookup"><span data-stu-id="a70fb-164">Enum</span></span> | <span data-ttu-id="a70fb-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="a70fb-165">Specification of the incident.</span></span> <span data-ttu-id="a70fb-166">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="a70fb-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a70fb-167">決定</span><span class="sxs-lookup"><span data-stu-id="a70fb-167">determination</span></span> | <span data-ttu-id="a70fb-168">列挙</span><span class="sxs-lookup"><span data-stu-id="a70fb-168">Enum</span></span> | <span data-ttu-id="a70fb-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a70fb-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="a70fb-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="a70fb-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a70fb-171">tags</span><span class="sxs-lookup"><span data-stu-id="a70fb-171">tags</span></span> | <span data-ttu-id="a70fb-172">string List</span><span class="sxs-lookup"><span data-stu-id="a70fb-172">string List</span></span> | <span data-ttu-id="a70fb-173">インシデント タグの一覧。</span><span class="sxs-lookup"><span data-stu-id="a70fb-173">List of Incident tags.</span></span>
<span data-ttu-id="a70fb-174">comments</span><span class="sxs-lookup"><span data-stu-id="a70fb-174">comments</span></span> | <span data-ttu-id="a70fb-175">インシデント コメントの一覧</span><span class="sxs-lookup"><span data-stu-id="a70fb-175">List of incident comments</span></span> | <span data-ttu-id="a70fb-176">インシデント コメント オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a70fb-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="a70fb-177">アラート</span><span class="sxs-lookup"><span data-stu-id="a70fb-177">alerts</span></span> | <span data-ttu-id="a70fb-178">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="a70fb-178">Alert List</span></span> | <span data-ttu-id="a70fb-179">関連するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="a70fb-179">List of related alerts.</span></span> <span data-ttu-id="a70fb-180">「List Incidents [API」のドキュメントの例](api-list-incidents.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a70fb-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a70fb-181">関連資料</span><span class="sxs-lookup"><span data-stu-id="a70fb-181">Related articles</span></span>

- [<span data-ttu-id="a70fb-182">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="a70fb-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a70fb-183">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="a70fb-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a70fb-184">インシデント API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="a70fb-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="a70fb-185">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="a70fb-185">Update incident API</span></span>](api-update-incidents.md)
