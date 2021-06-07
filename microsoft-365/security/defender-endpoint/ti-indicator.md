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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771383"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="03506-104">インジケーター リソースの種類</span><span class="sxs-lookup"><span data-stu-id="03506-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03506-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="03506-105">**Applies to:**</span></span>
- [<span data-ttu-id="03506-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="03506-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03506-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03506-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03506-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="03506-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03506-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="03506-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="03506-110">ポータルの対応 [する [インジケーター] ページ](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03506-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="03506-111">メソッド</span><span class="sxs-lookup"><span data-stu-id="03506-111">Method</span></span>|<span data-ttu-id="03506-112">戻り値の型</span><span class="sxs-lookup"><span data-stu-id="03506-112">Return Type</span></span> |<span data-ttu-id="03506-113">説明</span><span class="sxs-lookup"><span data-stu-id="03506-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="03506-114">インジケーターの一覧表示</span><span class="sxs-lookup"><span data-stu-id="03506-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="03506-115">[インジケーター](ti-indicator.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="03506-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="03506-116">インジケーター [エンティティを](ti-indicator.md) 一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="03506-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="03506-117">インジケーターの送信</span><span class="sxs-lookup"><span data-stu-id="03506-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="03506-118">インジケーター</span><span class="sxs-lookup"><span data-stu-id="03506-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="03506-119">Indicator エンティティを [送信または更新](ti-indicator.md) します。</span><span class="sxs-lookup"><span data-stu-id="03506-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="03506-120">インジケーターのインポート</span><span class="sxs-lookup"><span data-stu-id="03506-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="03506-121">[インジケーター](ti-indicator.md) コレクション</span><span class="sxs-lookup"><span data-stu-id="03506-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="03506-122">インジケーター エンティティを [送信または](ti-indicator.md) 更新します。</span><span class="sxs-lookup"><span data-stu-id="03506-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="03506-123">インジケーターの削除</span><span class="sxs-lookup"><span data-stu-id="03506-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="03506-124">コンテンツはありません</span><span class="sxs-lookup"><span data-stu-id="03506-124">No Content</span></span> | <span data-ttu-id="03506-125">Indicator エンティティ [を削除](ti-indicator.md) します。</span><span class="sxs-lookup"><span data-stu-id="03506-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="03506-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="03506-126">Properties</span></span>
<span data-ttu-id="03506-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="03506-127">Property</span></span> |  <span data-ttu-id="03506-128">種類</span><span class="sxs-lookup"><span data-stu-id="03506-128">Type</span></span>    |   <span data-ttu-id="03506-129">説明</span><span class="sxs-lookup"><span data-stu-id="03506-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="03506-130">id</span><span class="sxs-lookup"><span data-stu-id="03506-130">id</span></span> | <span data-ttu-id="03506-131">String</span><span class="sxs-lookup"><span data-stu-id="03506-131">String</span></span> | <span data-ttu-id="03506-132">Indicator エンティティ [の](ti-indicator.md) ID。</span><span class="sxs-lookup"><span data-stu-id="03506-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="03506-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="03506-133">indicatorValue</span></span> | <span data-ttu-id="03506-134">String</span><span class="sxs-lookup"><span data-stu-id="03506-134">String</span></span> | <span data-ttu-id="03506-135">Indicator の [値](ti-indicator.md)です。</span><span class="sxs-lookup"><span data-stu-id="03506-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="03506-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="03506-136">indicatorType</span></span> | <span data-ttu-id="03506-137">列挙</span><span class="sxs-lookup"><span data-stu-id="03506-137">Enum</span></span> | <span data-ttu-id="03506-138">インジケーターの種類。</span><span class="sxs-lookup"><span data-stu-id="03506-138">Type of the indicator.</span></span> <span data-ttu-id="03506-139">指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName" および "Url" です。</span><span class="sxs-lookup"><span data-stu-id="03506-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="03506-140">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="03506-140">application</span></span> | <span data-ttu-id="03506-141">String</span><span class="sxs-lookup"><span data-stu-id="03506-141">String</span></span> | <span data-ttu-id="03506-142">インジケーターに関連付けられているアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="03506-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="03506-143">action</span><span class="sxs-lookup"><span data-stu-id="03506-143">action</span></span> | <span data-ttu-id="03506-144">列挙</span><span class="sxs-lookup"><span data-stu-id="03506-144">Enum</span></span> | <span data-ttu-id="03506-145">インジケーターが組織内で検出される場合に実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="03506-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="03506-146">指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。</span><span class="sxs-lookup"><span data-stu-id="03506-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="03506-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="03506-147">sourceType</span></span> | <span data-ttu-id="03506-148">列挙</span><span class="sxs-lookup"><span data-stu-id="03506-148">Enum</span></span> | <span data-ttu-id="03506-149">"User" (ポータルからなど) ユーザーが作成したインジケーターの場合、API を介して自動アプリケーションを使用して送信された場合は "AadApp"。</span><span class="sxs-lookup"><span data-stu-id="03506-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="03506-150">source</span><span class="sxs-lookup"><span data-stu-id="03506-150">source</span></span> | <span data-ttu-id="03506-151">string</span><span class="sxs-lookup"><span data-stu-id="03506-151">string</span></span> | <span data-ttu-id="03506-152">インジケーターを送信したユーザー/アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="03506-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="03506-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="03506-153">createdBy</span></span> | <span data-ttu-id="03506-154">String</span><span class="sxs-lookup"><span data-stu-id="03506-154">String</span></span> | <span data-ttu-id="03506-155">インジケーターを送信したユーザー/アプリケーションの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="03506-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="03506-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="03506-156">lastUpdatedBy</span></span> | <span data-ttu-id="03506-157">String</span><span class="sxs-lookup"><span data-stu-id="03506-157">String</span></span> | <span data-ttu-id="03506-158">インジケーターを最後に更新したユーザー/アプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="03506-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="03506-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="03506-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="03506-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="03506-160">DateTimeOffset</span></span> | <span data-ttu-id="03506-161">インジケーターが作成された日時。</span><span class="sxs-lookup"><span data-stu-id="03506-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="03506-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="03506-162">expirationTime</span></span> | <span data-ttu-id="03506-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="03506-163">DateTimeOffset</span></span> | <span data-ttu-id="03506-164">インジケーターの有効期限。</span><span class="sxs-lookup"><span data-stu-id="03506-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="03506-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="03506-165">lastUpdateTime</span></span> | <span data-ttu-id="03506-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="03506-166">DateTimeOffset</span></span> | <span data-ttu-id="03506-167">インジケーターが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="03506-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="03506-168">severity</span><span class="sxs-lookup"><span data-stu-id="03506-168">severity</span></span> | <span data-ttu-id="03506-169">列挙</span><span class="sxs-lookup"><span data-stu-id="03506-169">Enum</span></span> | <span data-ttu-id="03506-170">インジケーターの重大度。</span><span class="sxs-lookup"><span data-stu-id="03506-170">The severity of the indicator.</span></span> <span data-ttu-id="03506-171">指定できる値は、"Informational"、"Low"、"Medium"、"High" です。</span><span class="sxs-lookup"><span data-stu-id="03506-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="03506-172">title</span><span class="sxs-lookup"><span data-stu-id="03506-172">title</span></span> | <span data-ttu-id="03506-173">String</span><span class="sxs-lookup"><span data-stu-id="03506-173">String</span></span> | <span data-ttu-id="03506-174">インジケーター のタイトル。</span><span class="sxs-lookup"><span data-stu-id="03506-174">Indicator title.</span></span>
<span data-ttu-id="03506-175">説明</span><span class="sxs-lookup"><span data-stu-id="03506-175">description</span></span> | <span data-ttu-id="03506-176">String</span><span class="sxs-lookup"><span data-stu-id="03506-176">String</span></span> | <span data-ttu-id="03506-177">インジケーターの説明。</span><span class="sxs-lookup"><span data-stu-id="03506-177">Description of the indicator.</span></span>
<span data-ttu-id="03506-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="03506-178">recommendedActions</span></span> | <span data-ttu-id="03506-179">String</span><span class="sxs-lookup"><span data-stu-id="03506-179">String</span></span> | <span data-ttu-id="03506-180">インジケーターの推奨アクション。</span><span class="sxs-lookup"><span data-stu-id="03506-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="03506-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="03506-181">rbacGroupNames</span></span> | <span data-ttu-id="03506-182">文字列の一覧</span><span class="sxs-lookup"><span data-stu-id="03506-182">List of strings</span></span> | <span data-ttu-id="03506-183">インジケーターが公開され、アクティブな RBAC デバイス グループ名。</span><span class="sxs-lookup"><span data-stu-id="03506-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="03506-184">すべてのデバイスに公開されている場合の空のリスト。</span><span class="sxs-lookup"><span data-stu-id="03506-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="03506-185">Json 表記</span><span class="sxs-lookup"><span data-stu-id="03506-185">Json representation</span></span>

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
