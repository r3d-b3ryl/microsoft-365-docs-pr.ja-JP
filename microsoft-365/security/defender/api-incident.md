---
title: Microsoft 365Defender インシデント API とインシデント リソースタイプ
description: defender でのインシデント リソースの種類のメソッドとプロパティMicrosoft 365確認します。
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
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="6ea90-104">Microsoft 365ディフェンダー インシデント API とインシデント リソースタイプ</span><span class="sxs-lookup"><span data-stu-id="6ea90-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6ea90-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6ea90-105">**Applies to:**</span></span>

- <span data-ttu-id="6ea90-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ea90-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ea90-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="6ea90-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6ea90-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="6ea90-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="6ea90-109">[インシデント](incidents-overview.md)とは、攻撃の説明に役立つ関連アラートの集まりです。</span><span class="sxs-lookup"><span data-stu-id="6ea90-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="6ea90-110">組織内のさまざまなエンティティからのイベントは、Microsoft 365 Defender によって自動的に集計されます。</span><span class="sxs-lookup"><span data-stu-id="6ea90-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="6ea90-111">インシデント API を使用すると、組織のインシデントおよび関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ea90-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="6ea90-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="6ea90-112">Quotas and resource allocation</span></span>

<span data-ttu-id="6ea90-113">1 分あたり最大 50 件のコール、または 1 時間あたり 1500 件のコールをリクエストできます。</span><span class="sxs-lookup"><span data-stu-id="6ea90-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="6ea90-114">各メソッドには、独自のクォータもあります。</span><span class="sxs-lookup"><span data-stu-id="6ea90-114">Each method also has its own quotas.</span></span> <span data-ttu-id="6ea90-115">メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea90-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="6ea90-116">`429`HTTP 応答コードは、送信された要求の数または割り当てられた実行時間によって、クォータに達したことを示します。</span><span class="sxs-lookup"><span data-stu-id="6ea90-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="6ea90-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ea90-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="6ea90-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="6ea90-118">Permissions</span></span>

<span data-ttu-id="6ea90-119">インシデント API では、それぞれのメソッドに対して異なる種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ea90-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="6ea90-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea90-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="6ea90-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="6ea90-121">Methods</span></span>

<span data-ttu-id="6ea90-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="6ea90-122">Method</span></span> | <span data-ttu-id="6ea90-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="6ea90-123">Return Type</span></span> | <span data-ttu-id="6ea90-124">説明</span><span class="sxs-lookup"><span data-stu-id="6ea90-124">Description</span></span>
-|-|-
[<span data-ttu-id="6ea90-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6ea90-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="6ea90-126">[インシデント](api-incident.md) リスト</span><span class="sxs-lookup"><span data-stu-id="6ea90-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="6ea90-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ea90-127">Get a list of incidents.</span></span>
[<span data-ttu-id="6ea90-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="6ea90-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="6ea90-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="6ea90-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="6ea90-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="6ea90-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="6ea90-131">要求本文、応答、例</span><span class="sxs-lookup"><span data-stu-id="6ea90-131">Request body, response, and examples</span></span>

<span data-ttu-id="6ea90-132">リクエストの作成方法や応答の解析方法、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea90-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="6ea90-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ea90-133">Common properties</span></span>

<span data-ttu-id="6ea90-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ea90-134">Property</span></span> | <span data-ttu-id="6ea90-135">型</span><span class="sxs-lookup"><span data-stu-id="6ea90-135">Type</span></span> | <span data-ttu-id="6ea90-136">説明</span><span class="sxs-lookup"><span data-stu-id="6ea90-136">Description</span></span>
-|-|-
<span data-ttu-id="6ea90-137">インシデントId</span><span class="sxs-lookup"><span data-stu-id="6ea90-137">incidentId</span></span> | <span data-ttu-id="6ea90-138">long</span><span class="sxs-lookup"><span data-stu-id="6ea90-138">long</span></span> | <span data-ttu-id="6ea90-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="6ea90-139">Incident unique ID.</span></span>
<span data-ttu-id="6ea90-140">インシデント ID をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="6ea90-140">redirectIncidentId</span></span> | <span data-ttu-id="6ea90-141">null 許容長</span><span class="sxs-lookup"><span data-stu-id="6ea90-141">nullable long</span></span> | <span data-ttu-id="6ea90-142">現在のインシデントがマージされたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="6ea90-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="6ea90-143">インシデント名</span><span class="sxs-lookup"><span data-stu-id="6ea90-143">incidentName</span></span> | <span data-ttu-id="6ea90-144">string</span><span class="sxs-lookup"><span data-stu-id="6ea90-144">string</span></span> | <span data-ttu-id="6ea90-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="6ea90-145">The name of the Incident.</span></span>
<span data-ttu-id="6ea90-146">作成された時刻</span><span class="sxs-lookup"><span data-stu-id="6ea90-146">createdTime</span></span> | <span data-ttu-id="6ea90-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6ea90-147">DateTimeOffset</span></span> | <span data-ttu-id="6ea90-148">インシデントが作成された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6ea90-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="6ea90-149">ラストアップデート時間</span><span class="sxs-lookup"><span data-stu-id="6ea90-149">lastUpdateTime</span></span> | <span data-ttu-id="6ea90-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6ea90-150">DateTimeOffset</span></span> | <span data-ttu-id="6ea90-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6ea90-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="6ea90-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6ea90-152">assignedTo</span></span> | <span data-ttu-id="6ea90-153">string</span><span class="sxs-lookup"><span data-stu-id="6ea90-153">string</span></span> | <span data-ttu-id="6ea90-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="6ea90-154">Owner of the Incident.</span></span>
<span data-ttu-id="6ea90-155">severity</span><span class="sxs-lookup"><span data-stu-id="6ea90-155">severity</span></span> | <span data-ttu-id="6ea90-156">列挙</span><span class="sxs-lookup"><span data-stu-id="6ea90-156">Enum</span></span> | <span data-ttu-id="6ea90-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="6ea90-157">Severity of the Incident.</span></span> <span data-ttu-id="6ea90-158">指定できる値は ```UnSpecified``` ```Informational``` 、 、 、 、 、 ```Low``` 、 ```Medium``` です ```High``` 。</span><span class="sxs-lookup"><span data-stu-id="6ea90-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="6ea90-159">status</span><span class="sxs-lookup"><span data-stu-id="6ea90-159">status</span></span> | <span data-ttu-id="6ea90-160">列挙</span><span class="sxs-lookup"><span data-stu-id="6ea90-160">Enum</span></span> | <span data-ttu-id="6ea90-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ea90-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="6ea90-162">使用できる値は ```Active``` 、 ```Resolved``` 、 、 、 です ```Redirected``` 。</span><span class="sxs-lookup"><span data-stu-id="6ea90-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="6ea90-163">classification</span><span class="sxs-lookup"><span data-stu-id="6ea90-163">classification</span></span> | <span data-ttu-id="6ea90-164">列挙</span><span class="sxs-lookup"><span data-stu-id="6ea90-164">Enum</span></span> | <span data-ttu-id="6ea90-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="6ea90-165">Specification of the incident.</span></span> <span data-ttu-id="6ea90-166">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="6ea90-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="6ea90-167">決定</span><span class="sxs-lookup"><span data-stu-id="6ea90-167">determination</span></span> | <span data-ttu-id="6ea90-168">列挙</span><span class="sxs-lookup"><span data-stu-id="6ea90-168">Enum</span></span> | <span data-ttu-id="6ea90-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6ea90-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="6ea90-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="6ea90-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="6ea90-171">tags</span><span class="sxs-lookup"><span data-stu-id="6ea90-171">tags</span></span> | <span data-ttu-id="6ea90-172">文字列リスト</span><span class="sxs-lookup"><span data-stu-id="6ea90-172">string List</span></span> | <span data-ttu-id="6ea90-173">インシデント タグのリスト。</span><span class="sxs-lookup"><span data-stu-id="6ea90-173">List of Incident tags.</span></span>
<span data-ttu-id="6ea90-174">comments</span><span class="sxs-lookup"><span data-stu-id="6ea90-174">comments</span></span> | <span data-ttu-id="6ea90-175">インシデントコメントの一覧</span><span class="sxs-lookup"><span data-stu-id="6ea90-175">List of incident comments</span></span> | <span data-ttu-id="6ea90-176">インシデント コメント オブジェクトには、コメント文字列、作成文字列、および作成時刻の日時が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ea90-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="6ea90-177">アラート</span><span class="sxs-lookup"><span data-stu-id="6ea90-177">alerts</span></span> | <span data-ttu-id="6ea90-178">アラート一覧</span><span class="sxs-lookup"><span data-stu-id="6ea90-178">Alert List</span></span> | <span data-ttu-id="6ea90-179">関連するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="6ea90-179">List of related alerts.</span></span> <span data-ttu-id="6ea90-180">インシデント API のドキュメントの [例](api-list-incidents.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea90-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6ea90-181">関連記事</span><span class="sxs-lookup"><span data-stu-id="6ea90-181">Related articles</span></span>

- [<span data-ttu-id="6ea90-182">Microsoft 365ディフェンダー API の概要</span><span class="sxs-lookup"><span data-stu-id="6ea90-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6ea90-183">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="6ea90-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6ea90-184">インシデント API の一覧</span><span class="sxs-lookup"><span data-stu-id="6ea90-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="6ea90-185">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="6ea90-185">Update incident API</span></span>](api-update-incidents.md)
