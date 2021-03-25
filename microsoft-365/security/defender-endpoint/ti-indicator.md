---
title: インジケーター リソースの種類
description: エンティティの詳細を指定し、Microsoft Defender for Endpoint を使用してインジケーターの有効期限を定義します。
keywords: apis, サポートされている api, get, TiIndicator, Indicator, recent
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187209"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="afe0f-104">インジケーター リソースの種類</span><span class="sxs-lookup"><span data-stu-id="afe0f-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="afe0f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="afe0f-105">**Applies to:**</span></span>
- [<span data-ttu-id="afe0f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="afe0f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="afe0f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="afe0f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="afe0f-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="afe0f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="afe0f-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="afe0f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="afe0f-110">ポータルの対応 [する [インジケーター] ページ](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afe0f-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="afe0f-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="afe0f-111">Method</span></span>|<span data-ttu-id="afe0f-112">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="afe0f-112">Return Type</span></span> |<span data-ttu-id="afe0f-113">説明</span><span class="sxs-lookup"><span data-stu-id="afe0f-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="afe0f-114">リスト インジケーター</span><span class="sxs-lookup"><span data-stu-id="afe0f-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="afe0f-115">[インジケーター](ti-indicator.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="afe0f-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="afe0f-116">インジケーター [エンティティを](ti-indicator.md) 一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="afe0f-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="afe0f-117">送信インジケーター</span><span class="sxs-lookup"><span data-stu-id="afe0f-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="afe0f-118">インジケーター</span><span class="sxs-lookup"><span data-stu-id="afe0f-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="afe0f-119">Indicator エンティティを [送信または更新](ti-indicator.md) します。</span><span class="sxs-lookup"><span data-stu-id="afe0f-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="afe0f-120">インポート インジケーター</span><span class="sxs-lookup"><span data-stu-id="afe0f-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="afe0f-121">[インジケーター](ti-indicator.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="afe0f-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="afe0f-122">インジケーター エンティティを [送信または](ti-indicator.md) 更新します。</span><span class="sxs-lookup"><span data-stu-id="afe0f-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="afe0f-123">インジケーターの削除</span><span class="sxs-lookup"><span data-stu-id="afe0f-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="afe0f-124">コンテンツはありません</span><span class="sxs-lookup"><span data-stu-id="afe0f-124">No Content</span></span> | <span data-ttu-id="afe0f-125">Indicator エンティティ [を削除](ti-indicator.md) します。</span><span class="sxs-lookup"><span data-stu-id="afe0f-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="afe0f-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afe0f-126">Properties</span></span>
<span data-ttu-id="afe0f-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="afe0f-127">Property</span></span> |  <span data-ttu-id="afe0f-128">種類</span><span class="sxs-lookup"><span data-stu-id="afe0f-128">Type</span></span>    |   <span data-ttu-id="afe0f-129">説明</span><span class="sxs-lookup"><span data-stu-id="afe0f-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="afe0f-130">id</span><span class="sxs-lookup"><span data-stu-id="afe0f-130">id</span></span> | <span data-ttu-id="afe0f-131">文字列</span><span class="sxs-lookup"><span data-stu-id="afe0f-131">String</span></span> | <span data-ttu-id="afe0f-132">Indicator エンティティ [の](ti-indicator.md) ID。</span><span class="sxs-lookup"><span data-stu-id="afe0f-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="afe0f-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="afe0f-133">indicatorValue</span></span> | <span data-ttu-id="afe0f-134">文字列</span><span class="sxs-lookup"><span data-stu-id="afe0f-134">String</span></span> | <span data-ttu-id="afe0f-135">Indicator の [値](ti-indicator.md)です。</span><span class="sxs-lookup"><span data-stu-id="afe0f-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="afe0f-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="afe0f-136">indicatorType</span></span> | <span data-ttu-id="afe0f-137">列挙</span><span class="sxs-lookup"><span data-stu-id="afe0f-137">Enum</span></span> | <span data-ttu-id="afe0f-138">インジケーターの種類。</span><span class="sxs-lookup"><span data-stu-id="afe0f-138">Type of the indicator.</span></span> <span data-ttu-id="afe0f-139">指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName" および "Url" です。</span><span class="sxs-lookup"><span data-stu-id="afe0f-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="afe0f-140">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="afe0f-140">application</span></span> | <span data-ttu-id="afe0f-141">文字列</span><span class="sxs-lookup"><span data-stu-id="afe0f-141">String</span></span> | <span data-ttu-id="afe0f-142">インジケーターに関連付けられているアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="afe0f-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="afe0f-143">action</span><span class="sxs-lookup"><span data-stu-id="afe0f-143">action</span></span> | <span data-ttu-id="afe0f-144">列挙</span><span class="sxs-lookup"><span data-stu-id="afe0f-144">Enum</span></span> | <span data-ttu-id="afe0f-145">インジケーターが組織内で検出される場合に実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="afe0f-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="afe0f-146">指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。</span><span class="sxs-lookup"><span data-stu-id="afe0f-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="afe0f-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="afe0f-147">sourceType</span></span> | <span data-ttu-id="afe0f-148">列挙</span><span class="sxs-lookup"><span data-stu-id="afe0f-148">Enum</span></span> | <span data-ttu-id="afe0f-149">"User" (ポータルからなど) ユーザーが作成したインジケーターの場合、API を介して自動アプリケーションを使用して送信された場合は "AadApp"。</span><span class="sxs-lookup"><span data-stu-id="afe0f-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="afe0f-150">source</span><span class="sxs-lookup"><span data-stu-id="afe0f-150">source</span></span> | <span data-ttu-id="afe0f-151">string</span><span class="sxs-lookup"><span data-stu-id="afe0f-151">string</span></span> | <span data-ttu-id="afe0f-152">インジケーターを送信したユーザー/アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="afe0f-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="afe0f-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="afe0f-153">createdBy</span></span> | <span data-ttu-id="afe0f-154">String</span><span class="sxs-lookup"><span data-stu-id="afe0f-154">String</span></span> | <span data-ttu-id="afe0f-155">インジケーターを送信したユーザー/アプリケーションの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="afe0f-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="afe0f-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="afe0f-156">lastUpdatedBy</span></span> | <span data-ttu-id="afe0f-157">文字列</span><span class="sxs-lookup"><span data-stu-id="afe0f-157">String</span></span> | <span data-ttu-id="afe0f-158">インジケーターを最後に更新したユーザー/アプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="afe0f-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="afe0f-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="afe0f-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="afe0f-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="afe0f-160">DateTimeOffset</span></span> | <span data-ttu-id="afe0f-161">インジケーターが作成された日時。</span><span class="sxs-lookup"><span data-stu-id="afe0f-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="afe0f-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="afe0f-162">expirationTime</span></span> | <span data-ttu-id="afe0f-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="afe0f-163">DateTimeOffset</span></span> | <span data-ttu-id="afe0f-164">インジケーターの有効期限。</span><span class="sxs-lookup"><span data-stu-id="afe0f-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="afe0f-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="afe0f-165">lastUpdateTime</span></span> | <span data-ttu-id="afe0f-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="afe0f-166">DateTimeOffset</span></span> | <span data-ttu-id="afe0f-167">インジケーターが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="afe0f-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="afe0f-168">severity</span><span class="sxs-lookup"><span data-stu-id="afe0f-168">severity</span></span> | <span data-ttu-id="afe0f-169">列挙</span><span class="sxs-lookup"><span data-stu-id="afe0f-169">Enum</span></span> | <span data-ttu-id="afe0f-170">インジケーターの重大度。</span><span class="sxs-lookup"><span data-stu-id="afe0f-170">The severity of the indicator.</span></span> <span data-ttu-id="afe0f-171">指定できる値は、"Informational"、"Low"、"Medium"、"High" です。</span><span class="sxs-lookup"><span data-stu-id="afe0f-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="afe0f-172">title</span><span class="sxs-lookup"><span data-stu-id="afe0f-172">title</span></span> | <span data-ttu-id="afe0f-173">String</span><span class="sxs-lookup"><span data-stu-id="afe0f-173">String</span></span> | <span data-ttu-id="afe0f-174">インジケーター のタイトル。</span><span class="sxs-lookup"><span data-stu-id="afe0f-174">Indicator title.</span></span>
<span data-ttu-id="afe0f-175">説明</span><span class="sxs-lookup"><span data-stu-id="afe0f-175">description</span></span> | <span data-ttu-id="afe0f-176">String</span><span class="sxs-lookup"><span data-stu-id="afe0f-176">String</span></span> | <span data-ttu-id="afe0f-177">インジケーターの説明。</span><span class="sxs-lookup"><span data-stu-id="afe0f-177">Description of the indicator.</span></span>
<span data-ttu-id="afe0f-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="afe0f-178">recommendedActions</span></span> | <span data-ttu-id="afe0f-179">文字列</span><span class="sxs-lookup"><span data-stu-id="afe0f-179">String</span></span> | <span data-ttu-id="afe0f-180">インジケーターの推奨アクション。</span><span class="sxs-lookup"><span data-stu-id="afe0f-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="afe0f-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="afe0f-181">rbacGroupNames</span></span> | <span data-ttu-id="afe0f-182">文字列の一覧</span><span class="sxs-lookup"><span data-stu-id="afe0f-182">List of strings</span></span> | <span data-ttu-id="afe0f-183">インジケーターが公開され、アクティブな RBAC デバイス グループ名。</span><span class="sxs-lookup"><span data-stu-id="afe0f-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="afe0f-184">すべてのデバイスに公開されている場合の空のリスト。</span><span class="sxs-lookup"><span data-stu-id="afe0f-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="afe0f-185">Json 表記</span><span class="sxs-lookup"><span data-stu-id="afe0f-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
