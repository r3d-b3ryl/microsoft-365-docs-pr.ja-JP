---
title: Microsoft Threat Protection API のインシデントリソースの種類
description: Microsoft Threat Protection の Incident リソースタイプのメソッドとプロパティについて説明します。
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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650414"
---
# <a name="incident-resource-type"></a><span data-ttu-id="bd064-104">インシデントリソースの種類</span><span class="sxs-lookup"><span data-stu-id="bd064-104">Incident resource type</span></span>

<span data-ttu-id="bd064-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bd064-105">**Applies to:**</span></span>
- <span data-ttu-id="bd064-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bd064-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="bd064-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="bd064-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="bd064-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="bd064-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="bd064-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="bd064-109">Methods</span></span>

<span data-ttu-id="bd064-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="bd064-110">Method</span></span> |<span data-ttu-id="bd064-111">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="bd064-111">Return Type</span></span> |<span data-ttu-id="bd064-112">説明</span><span class="sxs-lookup"><span data-stu-id="bd064-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bd064-113">インシデントを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="bd064-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="bd064-114">[インシデント](api-incident.md) リスト</span><span class="sxs-lookup"><span data-stu-id="bd064-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="bd064-115">インシデントの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="bd064-115">Get a list of incidents.</span></span>
[<span data-ttu-id="bd064-116">インシデントの更新</span><span class="sxs-lookup"><span data-stu-id="bd064-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="bd064-117">事例</span><span class="sxs-lookup"><span data-stu-id="bd064-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="bd064-118">特定のインシデントを更新します。</span><span class="sxs-lookup"><span data-stu-id="bd064-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="bd064-119">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bd064-119">Properties</span></span>

<span data-ttu-id="bd064-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bd064-120">Property</span></span> |    <span data-ttu-id="bd064-121">種類</span><span class="sxs-lookup"><span data-stu-id="bd064-121">Type</span></span>    |    <span data-ttu-id="bd064-122">説明</span><span class="sxs-lookup"><span data-stu-id="bd064-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="bd064-123">インシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="bd064-123">incidentId</span></span> | <span data-ttu-id="bd064-124">long</span><span class="sxs-lookup"><span data-stu-id="bd064-124">long</span></span> | <span data-ttu-id="bd064-125">インシデントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="bd064-125">Incident unique ID.</span></span>
<span data-ttu-id="bd064-126">Redirectインシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="bd064-126">redirectIncidentId</span></span> | <span data-ttu-id="bd064-127">null 許容長</span><span class="sxs-lookup"><span data-stu-id="bd064-127">nullable long</span></span> | <span data-ttu-id="bd064-128">現在のインシデントが結合されたインシデント ID。</span><span class="sxs-lookup"><span data-stu-id="bd064-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="bd064-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="bd064-129">incidentName</span></span> | <span data-ttu-id="bd064-130">string</span><span class="sxs-lookup"><span data-stu-id="bd064-130">string</span></span> | <span data-ttu-id="bd064-131">インシデントの名前。</span><span class="sxs-lookup"><span data-stu-id="bd064-131">The name of the Incident.</span></span>
<span data-ttu-id="bd064-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="bd064-132">createdTime</span></span> | <span data-ttu-id="bd064-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bd064-133">DateTimeOffset</span></span> | <span data-ttu-id="bd064-134">インシデントが作成された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="bd064-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="bd064-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="bd064-135">lastUpdateTime</span></span> | <span data-ttu-id="bd064-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="bd064-136">DateTimeOffset</span></span> | <span data-ttu-id="bd064-137">インシデントが最後に更新された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="bd064-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="bd064-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="bd064-138">assignedTo</span></span> | <span data-ttu-id="bd064-139">string</span><span class="sxs-lookup"><span data-stu-id="bd064-139">string</span></span> | <span data-ttu-id="bd064-140">インシデントの所有者。</span><span class="sxs-lookup"><span data-stu-id="bd064-140">Owner of the Incident.</span></span>
<span data-ttu-id="bd064-141">severity</span><span class="sxs-lookup"><span data-stu-id="bd064-141">severity</span></span> | <span data-ttu-id="bd064-142">列挙</span><span class="sxs-lookup"><span data-stu-id="bd064-142">Enum</span></span> | <span data-ttu-id="bd064-143">インシデントの重大度。</span><span class="sxs-lookup"><span data-stu-id="bd064-143">Severity of the Incident.</span></span> <span data-ttu-id="bd064-144">可能な値は ```UnSpecified``` 、、、 ```Informational``` ```Low``` 、 ```Medium``` ```High``` です。</span><span class="sxs-lookup"><span data-stu-id="bd064-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="bd064-145">status</span><span class="sxs-lookup"><span data-stu-id="bd064-145">status</span></span> | <span data-ttu-id="bd064-146">列挙</span><span class="sxs-lookup"><span data-stu-id="bd064-146">Enum</span></span> | <span data-ttu-id="bd064-147">インシデントの現在の状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd064-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="bd064-148">可能な値は ```Active``` 、、、 ```Resolved``` ```Redirected``` です。</span><span class="sxs-lookup"><span data-stu-id="bd064-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="bd064-149">classification</span><span class="sxs-lookup"><span data-stu-id="bd064-149">classification</span></span> | <span data-ttu-id="bd064-150">列挙</span><span class="sxs-lookup"><span data-stu-id="bd064-150">Enum</span></span> | <span data-ttu-id="bd064-151">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="bd064-151">Specification of the incident.</span></span> <span data-ttu-id="bd064-152">可能な値は、```Unknown```、```FalsePositive```、```TruePositive``` です。</span><span class="sxs-lookup"><span data-stu-id="bd064-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="bd064-153">決定</span><span class="sxs-lookup"><span data-stu-id="bd064-153">determination</span></span> | <span data-ttu-id="bd064-154">列挙</span><span class="sxs-lookup"><span data-stu-id="bd064-154">Enum</span></span> | <span data-ttu-id="bd064-155">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd064-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="bd064-156">可能な値は、```NotAvailable```、```Apt```、```Malware```、```SecurityPersonnel```、```SecurityTesting```、```UnwantedSoftware```、```Other``` です。</span><span class="sxs-lookup"><span data-stu-id="bd064-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="bd064-157">tags</span><span class="sxs-lookup"><span data-stu-id="bd064-157">tags</span></span> | <span data-ttu-id="bd064-158">文字列リスト</span><span class="sxs-lookup"><span data-stu-id="bd064-158">string List</span></span> | <span data-ttu-id="bd064-159">インシデントタグのリスト。</span><span class="sxs-lookup"><span data-stu-id="bd064-159">List of Incident tags.</span></span>
<span data-ttu-id="bd064-160">アラート</span><span class="sxs-lookup"><span data-stu-id="bd064-160">alerts</span></span> | <span data-ttu-id="bd064-161">通知リスト</span><span class="sxs-lookup"><span data-stu-id="bd064-161">Alert List</span></span> | <span data-ttu-id="bd064-162">関連する通知のリスト。</span><span class="sxs-lookup"><span data-stu-id="bd064-162">List of related alerts.</span></span> <span data-ttu-id="bd064-163">「 [List インシデント](api-list-incidents.md) API ドキュメント」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd064-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>