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
ms.openlocfilehash: 0a9022c0448ae0ddc16dc996ca93075abf6b2857
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060817"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="a7467-104">Microsoft 365Defender インシデント API とインシデント リソースの種類</span><span class="sxs-lookup"><span data-stu-id="a7467-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a7467-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a7467-105">**Applies to:**</span></span>

- <span data-ttu-id="a7467-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7467-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7467-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="a7467-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a7467-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="a7467-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a7467-109">インシデント [とは](incidents-overview.md) 、攻撃の説明に役立つ関連アラートのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a7467-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="a7467-110">組織内の異なるエンティティからのイベントは、Defender によって自動的にMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="a7467-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="a7467-111">インシデント API を使用して、組織のインシデントと関連するアラートにプログラムでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a7467-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="a7467-112">クォータとリソース割り当て</span><span class="sxs-lookup"><span data-stu-id="a7467-112">Quotas and resource allocation</span></span>

<span data-ttu-id="a7467-113">1 分あたり最大 50 回の通話または 1 時間あたり 1500 回の通話を要求できます。</span><span class="sxs-lookup"><span data-stu-id="a7467-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="a7467-114">また、各メソッドには独自のクォータがあります。</span><span class="sxs-lookup"><span data-stu-id="a7467-114">Each method also has its own quotas.</span></span> <span data-ttu-id="a7467-115">メソッド固有のクォータの詳細については、使用するメソッドの各記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7467-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="a7467-116">HTTP 応答コードは、送信された要求の数または割り当てられた実行時間のいずれかによって、クォータに達 `429` したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a7467-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="a7467-117">応答本文には、到達したクォータがリセットされるまでの時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a7467-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="a7467-118">権限</span><span class="sxs-lookup"><span data-stu-id="a7467-118">Permissions</span></span>

<span data-ttu-id="a7467-119">インシデント API では、それぞれのメソッドに対してさまざまな種類のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a7467-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="a7467-120">必要なアクセス許可の詳細については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7467-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="a7467-121">メソッド</span><span class="sxs-lookup"><span data-stu-id="a7467-121">Methods</span></span>

<span data-ttu-id="a7467-122">メソッド</span><span class="sxs-lookup"><span data-stu-id="a7467-122">Method</span></span> | <span data-ttu-id="a7467-123">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a7467-123">Return Type</span></span> | <span data-ttu-id="a7467-124">説明</span><span class="sxs-lookup"><span data-stu-id="a7467-124">Description</span></span>
-|-|-
[<span data-ttu-id="a7467-125">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="a7467-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="a7467-126">[インシデント リスト](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="a7467-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="a7467-127">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a7467-127">Get a list of incidents.</span></span>
[<span data-ttu-id="a7467-128">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="a7467-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="a7467-129">インシデント</span><span class="sxs-lookup"><span data-stu-id="a7467-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="a7467-130">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="a7467-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="a7467-131">要求の本文、応答、および例</span><span class="sxs-lookup"><span data-stu-id="a7467-131">Request body, response, and examples</span></span>

<span data-ttu-id="a7467-132">要求の作成方法や応答の解析方法の詳細、および実際の例については、それぞれのメソッドの記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7467-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="a7467-133">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="a7467-133">Common properties</span></span>

<span data-ttu-id="a7467-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a7467-134">Property</span></span> | <span data-ttu-id="a7467-135">型</span><span class="sxs-lookup"><span data-stu-id="a7467-135">Type</span></span> | <span data-ttu-id="a7467-136">説明</span><span class="sxs-lookup"><span data-stu-id="a7467-136">Description</span></span>
-|-|-
<span data-ttu-id="a7467-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="a7467-137">incidentId</span></span> | <span data-ttu-id="a7467-138">long</span><span class="sxs-lookup"><span data-stu-id="a7467-138">long</span></span> | <span data-ttu-id="a7467-139">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a7467-139">Incident unique ID.</span></span>
<span data-ttu-id="a7467-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="a7467-140">redirectIncidentId</span></span> | <span data-ttu-id="a7467-141">null 許容長</span><span class="sxs-lookup"><span data-stu-id="a7467-141">nullable long</span></span> | <span data-ttu-id="a7467-142">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="a7467-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="a7467-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="a7467-143">incidentName</span></span> | <span data-ttu-id="a7467-144">string</span><span class="sxs-lookup"><span data-stu-id="a7467-144">string</span></span> | <span data-ttu-id="a7467-145">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="a7467-145">The name of the Incident.</span></span>
<span data-ttu-id="a7467-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="a7467-146">createdTime</span></span> | <span data-ttu-id="a7467-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a7467-147">DateTimeOffset</span></span> | <span data-ttu-id="a7467-148">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="a7467-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="a7467-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="a7467-149">lastUpdateTime</span></span> | <span data-ttu-id="a7467-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a7467-150">DateTimeOffset</span></span> | <span data-ttu-id="a7467-151">インシデントが最後に更新された日時 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="a7467-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="a7467-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="a7467-152">assignedTo</span></span> | <span data-ttu-id="a7467-153">string</span><span class="sxs-lookup"><span data-stu-id="a7467-153">string</span></span> | <span data-ttu-id="a7467-154">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="a7467-154">Owner of the Incident.</span></span>
<span data-ttu-id="a7467-155">severity</span><span class="sxs-lookup"><span data-stu-id="a7467-155">severity</span></span> | <span data-ttu-id="a7467-156">列挙</span><span class="sxs-lookup"><span data-stu-id="a7467-156">Enum</span></span> | <span data-ttu-id="a7467-157">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="a7467-157">Severity of the Incident.</span></span> <span data-ttu-id="a7467-158">使用できる値は ```UnSpecified``` ```Informational``` ```Low``` 、、、、、 ```Medium``` および ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="a7467-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="a7467-159">status</span><span class="sxs-lookup"><span data-stu-id="a7467-159">status</span></span> | <span data-ttu-id="a7467-160">列挙</span><span class="sxs-lookup"><span data-stu-id="a7467-160">Enum</span></span> | <span data-ttu-id="a7467-161">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7467-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="a7467-162">使用できる値は ```Active``` ```Resolved``` 、、、および ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="a7467-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="a7467-163">classification</span><span class="sxs-lookup"><span data-stu-id="a7467-163">classification</span></span> | <span data-ttu-id="a7467-164">列挙</span><span class="sxs-lookup"><span data-stu-id="a7467-164">Enum</span></span> | <span data-ttu-id="a7467-165">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="a7467-165">Specification of the incident.</span></span> <span data-ttu-id="a7467-166">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="a7467-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a7467-167">決定</span><span class="sxs-lookup"><span data-stu-id="a7467-167">determination</span></span> | <span data-ttu-id="a7467-168">列挙</span><span class="sxs-lookup"><span data-stu-id="a7467-168">Enum</span></span> | <span data-ttu-id="a7467-169">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7467-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="a7467-170">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="a7467-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a7467-171">tags</span><span class="sxs-lookup"><span data-stu-id="a7467-171">tags</span></span> | <span data-ttu-id="a7467-172">string List</span><span class="sxs-lookup"><span data-stu-id="a7467-172">string List</span></span> | <span data-ttu-id="a7467-173">インシデント タグの一覧。</span><span class="sxs-lookup"><span data-stu-id="a7467-173">List of Incident tags.</span></span>
<span data-ttu-id="a7467-174">アラート</span><span class="sxs-lookup"><span data-stu-id="a7467-174">alerts</span></span> | <span data-ttu-id="a7467-175">アラート リスト</span><span class="sxs-lookup"><span data-stu-id="a7467-175">Alert List</span></span> | <span data-ttu-id="a7467-176">関連するアラートの一覧。</span><span class="sxs-lookup"><span data-stu-id="a7467-176">List of related alerts.</span></span> <span data-ttu-id="a7467-177">「List Incidents [API」のドキュメントの例](api-list-incidents.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7467-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="a7467-178">関連記事</span><span class="sxs-lookup"><span data-stu-id="a7467-178">Related articles</span></span>

- [<span data-ttu-id="a7467-179">Microsoft 365Defender API の概要</span><span class="sxs-lookup"><span data-stu-id="a7467-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="a7467-180">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="a7467-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="a7467-181">インシデント API の一覧表示</span><span class="sxs-lookup"><span data-stu-id="a7467-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="a7467-182">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="a7467-182">Update incident API</span></span>](api-update-incidents.md)
