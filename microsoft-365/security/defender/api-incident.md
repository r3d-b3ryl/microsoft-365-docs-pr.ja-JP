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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888435"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="f4229-104">Microsoft 365Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="f4229-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f4229-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f4229-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4229-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4229-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="f4229-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="f4229-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f4229-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="f4229-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="f4229-109">インシデント [とは](incidents-overview.md) 、攻撃の説明に役立つ関連アラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f4229-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="f4229-110">組織内の異なるエンティティからのイベントは、Defender によって自動的にMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="f4229-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f4229-111">インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f4229-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="f4229-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="f4229-112">Quotas and resource allocation</span></span>

<span data-ttu-id="f4229-113">1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f4229-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="f4229-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="f4229-114">Each method also has its own quotas.</span></span> <span data-ttu-id="f4229-115">メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4229-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="f4229-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f4229-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="f4229-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4229-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="f4229-118">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4229-118">Permissions</span></span>

<span data-ttu-id="f4229-119">インシデント API では、それぞれのメソッドに対してさまざまな種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4229-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="f4229-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4229-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="f4229-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="f4229-121">Methods</span></span>

<span data-ttu-id="f4229-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="f4229-122">Method</span></span> | <span data-ttu-id="f4229-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="f4229-123">Return Type</span></span> | <span data-ttu-id="f4229-124">説明</span><span class="sxs-lookup"><span data-stu-id="f4229-124">Description</span></span>
-|-|-
[<span data-ttu-id="f4229-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f4229-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="f4229-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="f4229-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="f4229-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="f4229-127">Get a list of incidents.</span></span>
[<span data-ttu-id="f4229-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="f4229-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="f4229-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="f4229-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="f4229-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="f4229-130">Update a specific incident.</span></span>
[<span data-ttu-id="f4229-131">インシデントの取得</span><span class="sxs-lookup"><span data-stu-id="f4229-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="f4229-132">インシデント</span><span class="sxs-lookup"><span data-stu-id="f4229-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="f4229-133">1 つのインシデントを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4229-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="f4229-134">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="f4229-134">Request body, response, and examples</span></span>

<span data-ttu-id="f4229-135">要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4229-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="f4229-136">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4229-136">Common properties</span></span>

<span data-ttu-id="f4229-137">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4229-137">Property</span></span> | <span data-ttu-id="f4229-138">型</span><span class="sxs-lookup"><span data-stu-id="f4229-138">Type</span></span> | <span data-ttu-id="f4229-139">説明</span><span class="sxs-lookup"><span data-stu-id="f4229-139">Description</span></span>
-|-|-
<span data-ttu-id="f4229-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="f4229-140">incidentId</span></span> | <span data-ttu-id="f4229-141">long</span><span class="sxs-lookup"><span data-stu-id="f4229-141">long</span></span> | <span data-ttu-id="f4229-142">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="f4229-142">Incident unique ID.</span></span>
<span data-ttu-id="f4229-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="f4229-143">redirectIncidentId</span></span> | <span data-ttu-id="f4229-144">null 許容長</span><span class="sxs-lookup"><span data-stu-id="f4229-144">nullable long</span></span> | <span data-ttu-id="f4229-145">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="f4229-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="f4229-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="f4229-146">incidentName</span></span> | <span data-ttu-id="f4229-147">string</span><span class="sxs-lookup"><span data-stu-id="f4229-147">string</span></span> | <span data-ttu-id="f4229-148">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="f4229-148">The name of the Incident.</span></span>
<span data-ttu-id="f4229-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="f4229-149">createdTime</span></span> | <span data-ttu-id="f4229-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f4229-150">DateTimeOffset</span></span> | <span data-ttu-id="f4229-151">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f4229-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="f4229-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="f4229-152">lastUpdateTime</span></span> | <span data-ttu-id="f4229-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f4229-153">DateTimeOffset</span></span> | <span data-ttu-id="f4229-154">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="f4229-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="f4229-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f4229-155">assignedTo</span></span> | <span data-ttu-id="f4229-156">string</span><span class="sxs-lookup"><span data-stu-id="f4229-156">string</span></span> | <span data-ttu-id="f4229-157">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="f4229-157">Owner of the Incident.</span></span>
<span data-ttu-id="f4229-158">severity</span><span class="sxs-lookup"><span data-stu-id="f4229-158">severity</span></span> | <span data-ttu-id="f4229-159">列挙</span><span class="sxs-lookup"><span data-stu-id="f4229-159">Enum</span></span> | <span data-ttu-id="f4229-160">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="f4229-160">Severity of the Incident.</span></span> <span data-ttu-id="f4229-161">使用できる値は ```UnSpecified``` ```Informational``` ```Low``` 、、、、、 ```Medium``` および ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="f4229-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="f4229-162">status</span><span class="sxs-lookup"><span data-stu-id="f4229-162">status</span></span> | <span data-ttu-id="f4229-163">列挙</span><span class="sxs-lookup"><span data-stu-id="f4229-163">Enum</span></span> | <span data-ttu-id="f4229-164">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4229-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="f4229-165">使用できる値は ```Active``` ```Resolved``` 、、、および ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="f4229-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="f4229-166">classification</span><span class="sxs-lookup"><span data-stu-id="f4229-166">classification</span></span> | <span data-ttu-id="f4229-167">列挙</span><span class="sxs-lookup"><span data-stu-id="f4229-167">Enum</span></span> | <span data-ttu-id="f4229-168">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="f4229-168">Specification of the incident.</span></span> <span data-ttu-id="f4229-169">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="f4229-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="f4229-170">決定</span><span class="sxs-lookup"><span data-stu-id="f4229-170">determination</span></span> | <span data-ttu-id="f4229-171">列挙</span><span class="sxs-lookup"><span data-stu-id="f4229-171">Enum</span></span> | <span data-ttu-id="f4229-172">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f4229-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="f4229-173">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="f4229-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="f4229-174">tags</span><span class="sxs-lookup"><span data-stu-id="f4229-174">tags</span></span> | <span data-ttu-id="f4229-175">string List</span><span class="sxs-lookup"><span data-stu-id="f4229-175">string List</span></span> | <span data-ttu-id="f4229-176">インシデント タグの一覧。</span><span class="sxs-lookup"><span data-stu-id="f4229-176">List of Incident tags.</span></span>
<span data-ttu-id="f4229-177">comments</span><span class="sxs-lookup"><span data-stu-id="f4229-177">comments</span></span> | <span data-ttu-id="f4229-178">インシデント コメントの一覧</span><span class="sxs-lookup"><span data-stu-id="f4229-178">List of incident comments</span></span> | <span data-ttu-id="f4229-179">インシデント コメント オブジェクトには、コメント文字列、createBy 文字列、createTime 日付時刻が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f4229-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="f4229-180">アラート</span><span class="sxs-lookup"><span data-stu-id="f4229-180">alerts</span></span> | <span data-ttu-id="f4229-181">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="f4229-181">Alert List</span></span> | <span data-ttu-id="f4229-182">関連するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="f4229-182">List of related alerts.</span></span> <span data-ttu-id="f4229-183">「List Incidents [API」のドキュメントの例](api-list-incidents.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4229-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f4229-184">関連資料</span><span class="sxs-lookup"><span data-stu-id="f4229-184">Related articles</span></span>

- [<span data-ttu-id="f4229-185">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="f4229-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="f4229-186">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="f4229-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f4229-187">インシデント API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="f4229-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="f4229-188">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="f4229-188">Update incident API</span></span>](api-update-incidents.md)
