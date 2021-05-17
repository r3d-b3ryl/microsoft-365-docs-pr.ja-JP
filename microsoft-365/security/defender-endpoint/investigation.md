---
title: 調査リソースの種類
description: Microsoft Defender for Endpoint Investigation エンティティ。
keywords: apis、graph api、サポートされている API、get、アラート、調査
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587685"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="a8a37-104">調査リソースの種類</span><span class="sxs-lookup"><span data-stu-id="a8a37-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a8a37-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a8a37-105">**Applies to:**</span></span>
- [<span data-ttu-id="a8a37-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a8a37-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a8a37-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8a37-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a8a37-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="a8a37-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a8a37-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a8a37-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a8a37-110">Defender for Endpoint の自動調査エンティティを表します。</span><span class="sxs-lookup"><span data-stu-id="a8a37-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="a8a37-111">詳細 [については、「自動調査の概要](automated-investigations.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8a37-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="a8a37-112">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8a37-112">Methods</span></span>
<span data-ttu-id="a8a37-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="a8a37-113">Method</span></span>|<span data-ttu-id="a8a37-114">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="a8a37-114">Return Type</span></span> |<span data-ttu-id="a8a37-115">説明</span><span class="sxs-lookup"><span data-stu-id="a8a37-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a8a37-116">リスト調査</span><span class="sxs-lookup"><span data-stu-id="a8a37-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="a8a37-117">調査コレクション</span><span class="sxs-lookup"><span data-stu-id="a8a37-117">Investigation collection</span></span> | <span data-ttu-id="a8a37-118">調査のコレクションを取得する</span><span class="sxs-lookup"><span data-stu-id="a8a37-118">Get collection of Investigation</span></span>
[<span data-ttu-id="a8a37-119">単一の調査を取得する</span><span class="sxs-lookup"><span data-stu-id="a8a37-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="a8a37-120">調査エンティティ</span><span class="sxs-lookup"><span data-stu-id="a8a37-120">Investigation entity</span></span> | <span data-ttu-id="a8a37-121">単一の Investigation エンティティを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8a37-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="a8a37-122">調査の開始</span><span class="sxs-lookup"><span data-stu-id="a8a37-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="a8a37-123">調査エンティティ</span><span class="sxs-lookup"><span data-stu-id="a8a37-123">Investigation entity</span></span> | <span data-ttu-id="a8a37-124">デバイスで調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="a8a37-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="a8a37-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a8a37-125">Properties</span></span>
<span data-ttu-id="a8a37-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a8a37-126">Property</span></span> |  <span data-ttu-id="a8a37-127">型</span><span class="sxs-lookup"><span data-stu-id="a8a37-127">Type</span></span>    |   <span data-ttu-id="a8a37-128">説明</span><span class="sxs-lookup"><span data-stu-id="a8a37-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="a8a37-129">id</span><span class="sxs-lookup"><span data-stu-id="a8a37-129">id</span></span> | <span data-ttu-id="a8a37-130">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-130">String</span></span> | <span data-ttu-id="a8a37-131">調査エンティティの ID。</span><span class="sxs-lookup"><span data-stu-id="a8a37-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="a8a37-132">startTime</span><span class="sxs-lookup"><span data-stu-id="a8a37-132">startTime</span></span> | <span data-ttu-id="a8a37-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="a8a37-133">DateTime Nullable</span></span> | <span data-ttu-id="a8a37-134">調査が作成された日時。</span><span class="sxs-lookup"><span data-stu-id="a8a37-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="a8a37-135">endTime</span><span class="sxs-lookup"><span data-stu-id="a8a37-135">endTime</span></span> | <span data-ttu-id="a8a37-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="a8a37-136">DateTime Nullable</span></span> | <span data-ttu-id="a8a37-137">調査が完了した日時。</span><span class="sxs-lookup"><span data-stu-id="a8a37-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="a8a37-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="a8a37-138">cancelledBy</span></span> | <span data-ttu-id="a8a37-139">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-139">String</span></span> | <span data-ttu-id="a8a37-140">その調査を取り消したユーザー/アプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="a8a37-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="a8a37-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="a8a37-141">investigationState</span></span> | <span data-ttu-id="a8a37-142">列挙</span><span class="sxs-lookup"><span data-stu-id="a8a37-142">Enum</span></span> | <span data-ttu-id="a8a37-143">調査の現在の状態。</span><span class="sxs-lookup"><span data-stu-id="a8a37-143">The current state of the investigation.</span></span> <span data-ttu-id="a8a37-144">指定できる値は、'Unknown'、'Terminated'、 'SuccessfullyRemediated', '良性', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'unsupportedAlertType', 'unsupportedAlertType''</span><span class="sxs-lookup"><span data-stu-id="a8a37-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="a8a37-145">statusDetails</span><span class="sxs-lookup"><span data-stu-id="a8a37-145">statusDetails</span></span> | <span data-ttu-id="a8a37-146">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-146">String</span></span> | <span data-ttu-id="a8a37-147">調査の状態に関する追加情報。</span><span class="sxs-lookup"><span data-stu-id="a8a37-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="a8a37-148">machineId</span><span class="sxs-lookup"><span data-stu-id="a8a37-148">machineId</span></span> | <span data-ttu-id="a8a37-149">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-149">String</span></span> | <span data-ttu-id="a8a37-150">調査が実行されるデバイスの ID。</span><span class="sxs-lookup"><span data-stu-id="a8a37-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="a8a37-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="a8a37-151">computerDnsName</span></span> | <span data-ttu-id="a8a37-152">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-152">String</span></span> | <span data-ttu-id="a8a37-153">調査が実行されるデバイスの名前。</span><span class="sxs-lookup"><span data-stu-id="a8a37-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="a8a37-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="a8a37-154">triggeringAlertId</span></span> | <span data-ttu-id="a8a37-155">String</span><span class="sxs-lookup"><span data-stu-id="a8a37-155">String</span></span> | <span data-ttu-id="a8a37-156">調査をトリガーしたアラートの ID。</span><span class="sxs-lookup"><span data-stu-id="a8a37-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="a8a37-157">Json 表記</span><span class="sxs-lookup"><span data-stu-id="a8a37-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
