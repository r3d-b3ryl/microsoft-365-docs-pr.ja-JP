---
title: Microsoft 365 Defender API のインシデントリソースの種類
description: Microsoft 365 Defender の Incident リソースタイプのメソッドとプロパティについて説明します。
keywords: インシデント、インシデント、api
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844022"
---
# <a name="incident-resource-type"></a><span data-ttu-id="3866e-104">インシデントリソースの種類</span><span class="sxs-lookup"><span data-stu-id="3866e-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3866e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3866e-105">**Applies to:**</span></span>
- <span data-ttu-id="3866e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3866e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="3866e-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="3866e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3866e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3866e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="3866e-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="3866e-109">Methods</span></span>

<span data-ttu-id="3866e-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="3866e-110">Method</span></span> |<span data-ttu-id="3866e-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="3866e-111">Return Type</span></span> |<span data-ttu-id="3866e-112">説明</span><span class="sxs-lookup"><span data-stu-id="3866e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="3866e-113">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="3866e-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="3866e-114">[インシデント](api-incident.md) リスト</span><span class="sxs-lookup"><span data-stu-id="3866e-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="3866e-115">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="3866e-115">Get a list of incidents.</span></span>
[<span data-ttu-id="3866e-116">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="3866e-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="3866e-117">事例</span><span class="sxs-lookup"><span data-stu-id="3866e-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="3866e-118">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="3866e-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="3866e-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3866e-119">Properties</span></span>

<span data-ttu-id="3866e-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3866e-120">Property</span></span> |    <span data-ttu-id="3866e-121">型</span><span class="sxs-lookup"><span data-stu-id="3866e-121">Type</span></span>    |    <span data-ttu-id="3866e-122">説明</span><span class="sxs-lookup"><span data-stu-id="3866e-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="3866e-123">インシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="3866e-123">incidentId</span></span> | <span data-ttu-id="3866e-124">long</span><span class="sxs-lookup"><span data-stu-id="3866e-124">long</span></span> | <span data-ttu-id="3866e-125">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="3866e-125">Incident unique ID.</span></span>
<span data-ttu-id="3866e-126">Redirectインシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="3866e-126">redirectIncidentId</span></span> | <span data-ttu-id="3866e-127">null 許容長</span><span class="sxs-lookup"><span data-stu-id="3866e-127">nullable long</span></span> | <span data-ttu-id="3866e-128">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="3866e-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="3866e-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="3866e-129">incidentName</span></span> | <span data-ttu-id="3866e-130">string</span><span class="sxs-lookup"><span data-stu-id="3866e-130">string</span></span> | <span data-ttu-id="3866e-131">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="3866e-131">The name of the Incident.</span></span>
<span data-ttu-id="3866e-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="3866e-132">createdTime</span></span> | <span data-ttu-id="3866e-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3866e-133">DateTimeOffset</span></span> | <span data-ttu-id="3866e-134">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="3866e-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="3866e-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="3866e-135">lastUpdateTime</span></span> | <span data-ttu-id="3866e-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="3866e-136">DateTimeOffset</span></span> | <span data-ttu-id="3866e-137">インシデントが最後に更新された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="3866e-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="3866e-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="3866e-138">assignedTo</span></span> | <span data-ttu-id="3866e-139">string</span><span class="sxs-lookup"><span data-stu-id="3866e-139">string</span></span> | <span data-ttu-id="3866e-140">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="3866e-140">Owner of the Incident.</span></span>
<span data-ttu-id="3866e-141">severity</span><span class="sxs-lookup"><span data-stu-id="3866e-141">severity</span></span> | <span data-ttu-id="3866e-142">列挙</span><span class="sxs-lookup"><span data-stu-id="3866e-142">Enum</span></span> | <span data-ttu-id="3866e-143">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="3866e-143">Severity of the Incident.</span></span> <span data-ttu-id="3866e-144">可能な値は ```UnSpecified``` 、、、 ```Informational``` ```Low``` 、 ```Medium``` ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="3866e-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="3866e-145">status</span><span class="sxs-lookup"><span data-stu-id="3866e-145">status</span></span> | <span data-ttu-id="3866e-146">列挙</span><span class="sxs-lookup"><span data-stu-id="3866e-146">Enum</span></span> | <span data-ttu-id="3866e-147">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="3866e-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="3866e-148">可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="3866e-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="3866e-149">classification</span><span class="sxs-lookup"><span data-stu-id="3866e-149">classification</span></span> | <span data-ttu-id="3866e-150">列挙</span><span class="sxs-lookup"><span data-stu-id="3866e-150">Enum</span></span> | <span data-ttu-id="3866e-151">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="3866e-151">Specification of the incident.</span></span> <span data-ttu-id="3866e-152">可能な値は ```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="3866e-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="3866e-153">決定</span><span class="sxs-lookup"><span data-stu-id="3866e-153">determination</span></span> | <span data-ttu-id="3866e-154">列挙</span><span class="sxs-lookup"><span data-stu-id="3866e-154">Enum</span></span> | <span data-ttu-id="3866e-155">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3866e-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="3866e-156">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="3866e-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="3866e-157">tags</span><span class="sxs-lookup"><span data-stu-id="3866e-157">tags</span></span> | <span data-ttu-id="3866e-158">文字列リスト</span><span class="sxs-lookup"><span data-stu-id="3866e-158">string List</span></span> | <span data-ttu-id="3866e-159">インシデントタグのリスト。</span><span class="sxs-lookup"><span data-stu-id="3866e-159">List of Incident tags.</span></span>
<span data-ttu-id="3866e-160">アラート</span><span class="sxs-lookup"><span data-stu-id="3866e-160">alerts</span></span> | <span data-ttu-id="3866e-161">通知リスト</span><span class="sxs-lookup"><span data-stu-id="3866e-161">Alert List</span></span> | <span data-ttu-id="3866e-162">関連する通知のリスト。</span><span class="sxs-lookup"><span data-stu-id="3866e-162">List of related alerts.</span></span> <span data-ttu-id="3866e-163">「 [List インシデント](api-list-incidents.md) API ドキュメント」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3866e-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
