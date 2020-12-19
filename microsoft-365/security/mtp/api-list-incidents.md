---
title: Microsoft 365 Defender でインシデント API を一覧表示する
description: Microsoft 365 Defender でインシデント API を一覧表示する方法について説明します
keywords: リスト、インシデント、インシデント、API
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
ms.openlocfilehash: 13508d3ad9d61797517ccb55a27152883947843a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719430"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="2abc3-104">Microsoft 365 Defender でインシデント API を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="2abc3-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2abc3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2abc3-105">**Applies to:**</span></span>

- <span data-ttu-id="2abc3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2abc3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2abc3-107">一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="2abc3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2abc3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="2abc3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="2abc3-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-109">API description</span></span>

<span data-ttu-id="2abc3-110">リスト インシデント API を使用すると、インシデントを並べ替え、情報に基づいたサイバーセキュリティ対応を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="2abc3-111">環境保持ポリシーで指定した時間範囲内に、ネットワーク内でフラグが設定されたインシデントのコレクションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="2abc3-112">最新のインシデントがリストの一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="2abc3-113">各インシデントには、関連するアラートとその関連エンティティの配列が含まれる。</span><span class="sxs-lookup"><span data-stu-id="2abc3-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="2abc3-114">この API は、次の **OData 演算子をサポート** しています。</span><span class="sxs-lookup"><span data-stu-id="2abc3-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="2abc3-115">`$filter`on `lastUpdateTime` `createdTime` `status` 、、、properties `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="2abc3-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="2abc3-116">`$top`、最大値は **100 です。**</span><span class="sxs-lookup"><span data-stu-id="2abc3-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="2abc3-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="2abc3-117">Limitations</span></span>

1. <span data-ttu-id="2abc3-118">最大ページ サイズは **100 インシデントです**。</span><span class="sxs-lookup"><span data-stu-id="2abc3-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="2abc3-119">要求の最大速度は **、1 分あたり 50 回\*\*\*\*、1 時間あたり 1500 件の通話です**。</span><span class="sxs-lookup"><span data-stu-id="2abc3-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="2abc3-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2abc3-120">Permissions</span></span>

<span data-ttu-id="2abc3-121">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="2abc3-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2abc3-122">アクセス許可の選択方法など、詳細については[、「Access Microsoft 365 Defender API」を参照してください](api-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2abc3-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="2abc3-123">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="2abc3-123">Permission type</span></span> | <span data-ttu-id="2abc3-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="2abc3-124">Permission</span></span> | <span data-ttu-id="2abc3-125">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="2abc3-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="2abc3-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2abc3-126">Application</span></span> | <span data-ttu-id="2abc3-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="2abc3-127">Incident.Read.All</span></span> | <span data-ttu-id="2abc3-128">すべてのインシデントの読み取り</span><span class="sxs-lookup"><span data-stu-id="2abc3-128">Read all incidents</span></span>
<span data-ttu-id="2abc3-129">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2abc3-129">Application</span></span> | <span data-ttu-id="2abc3-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2abc3-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="2abc3-131">すべてのインシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="2abc3-131">Read and write all incidents</span></span>
<span data-ttu-id="2abc3-132">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="2abc3-132">Delegated (work or school account)</span></span> | <span data-ttu-id="2abc3-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="2abc3-133">Incident.Read</span></span> | <span data-ttu-id="2abc3-134">インシデントの読み取り</span><span class="sxs-lookup"><span data-stu-id="2abc3-134">Read incidents</span></span>
<span data-ttu-id="2abc3-135">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="2abc3-135">Delegated (work or school account)</span></span> | <span data-ttu-id="2abc3-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2abc3-136">Incident.ReadWrite</span></span> | <span data-ttu-id="2abc3-137">インシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="2abc3-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="2abc3-138">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="2abc3-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="2abc3-139">ユーザーは、ポータルでインシデントに対する表示権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2abc3-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="2abc3-140">応答には、ユーザーが公開されているインシデントだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="2abc3-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="2abc3-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="2abc3-142">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="2abc3-142">Request headers</span></span>

<span data-ttu-id="2abc3-143">名前</span><span class="sxs-lookup"><span data-stu-id="2abc3-143">Name</span></span> | <span data-ttu-id="2abc3-144">型</span><span class="sxs-lookup"><span data-stu-id="2abc3-144">Type</span></span> | <span data-ttu-id="2abc3-145">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-145">Description</span></span>
-|-|-
<span data-ttu-id="2abc3-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="2abc3-146">Authorization</span></span> | <span data-ttu-id="2abc3-147">String</span><span class="sxs-lookup"><span data-stu-id="2abc3-147">String</span></span> | <span data-ttu-id="2abc3-148">ベアラー {トークン}。</span><span class="sxs-lookup"><span data-stu-id="2abc3-148">Bearer {token}.</span></span> <span data-ttu-id="2abc3-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="2abc3-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="2abc3-150">要求本文</span><span class="sxs-lookup"><span data-stu-id="2abc3-150">Request body</span></span>

<span data-ttu-id="2abc3-151">なし。</span><span class="sxs-lookup"><span data-stu-id="2abc3-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="2abc3-152">応答</span><span class="sxs-lookup"><span data-stu-id="2abc3-152">Response</span></span>

<span data-ttu-id="2abc3-153">成功した場合、このメソッドは応答本文でインシデントの一覧 `200 OK` を返します。 [](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="2abc3-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="2abc3-154">スキーマ マッピング</span><span class="sxs-lookup"><span data-stu-id="2abc3-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="2abc3-155">インシデント メタデータ</span><span class="sxs-lookup"><span data-stu-id="2abc3-155">Incident metadata</span></span>

<span data-ttu-id="2abc3-156">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2abc3-156">Field name</span></span> | <span data-ttu-id="2abc3-157">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-157">Description</span></span> | <span data-ttu-id="2abc3-158">値の例</span><span class="sxs-lookup"><span data-stu-id="2abc3-158">Example value</span></span>
-|-|-
<span data-ttu-id="2abc3-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="2abc3-159">incidentId</span></span> | <span data-ttu-id="2abc3-160">インシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="2abc3-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="2abc3-161">924565</span><span class="sxs-lookup"><span data-stu-id="2abc3-161">924565</span></span>
<span data-ttu-id="2abc3-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="2abc3-162">redirectIncidentId</span></span> | <span data-ttu-id="2abc3-163">インシデント処理ロジックの一部として、インシデントが別のインシデントとグループ化されている場合にのみ入力されます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="2abc3-164">924569</span><span class="sxs-lookup"><span data-stu-id="2abc3-164">924569</span></span>
<span data-ttu-id="2abc3-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="2abc3-165">incidentName</span></span> | <span data-ttu-id="2abc3-166">すべてのインシデントで使用可能な文字列値。</span><span class="sxs-lookup"><span data-stu-id="2abc3-166">String value available for every incident.</span></span> | <span data-ttu-id="2abc3-167">ランサムウェア アクティビティ</span><span class="sxs-lookup"><span data-stu-id="2abc3-167">Ransomware activity</span></span>
<span data-ttu-id="2abc3-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-168">createdTime</span></span> | <span data-ttu-id="2abc3-169">インシデントが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-169">Time when incident was first created.</span></span> | <span data-ttu-id="2abc3-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="2abc3-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-171">lastUpdateTime</span></span> | <span data-ttu-id="2abc3-172">バックエンドでインシデントが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="2abc3-173">このフィールドは、インシデントが取得される時間の範囲に対して要求パラメーターを設定する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="2abc3-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="2abc3-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2abc3-175">assignedTo</span></span> | <span data-ttu-id="2abc3-176">インシデントの所有者、または *所有者が割り* 当てられていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="2abc3-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="2abc3-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-177">secop2@contoso.com</span></span>
<span data-ttu-id="2abc3-178">classification</span><span class="sxs-lookup"><span data-stu-id="2abc3-178">classification</span></span> | <span data-ttu-id="2abc3-179">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="2abc3-179">The specification for the incident.</span></span> <span data-ttu-id="2abc3-180">プロパティの値は *、Unknown、FalsePositive、TruePositive\*\*です。* </span><span class="sxs-lookup"><span data-stu-id="2abc3-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="2abc3-181">不明</span><span class="sxs-lookup"><span data-stu-id="2abc3-181">Unknown</span></span>
<span data-ttu-id="2abc3-182">判断</span><span class="sxs-lookup"><span data-stu-id="2abc3-182">determination</span></span> | <span data-ttu-id="2abc3-183">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="2abc3-184">プロパティの値は *、NotAvailable*、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware  *、Other です。*    </span><span class="sxs-lookup"><span data-stu-id="2abc3-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="2abc3-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="2abc3-185">NotAvailable</span></span>
<span data-ttu-id="2abc3-186">status</span><span class="sxs-lookup"><span data-stu-id="2abc3-186">status</span></span> | <span data-ttu-id="2abc3-187">インシデント (アクティブまたは解決 *済* み) *を分類します*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="2abc3-188">これは、インシデントへの対応を整理して管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="2abc3-189">Active</span><span class="sxs-lookup"><span data-stu-id="2abc3-189">Active</span></span>
<span data-ttu-id="2abc3-190">severity</span><span class="sxs-lookup"><span data-stu-id="2abc3-190">severity</span></span> | <span data-ttu-id="2abc3-191">資産への影響の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="2abc3-192">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="2abc3-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="2abc3-193">通常、重要度の高いアイテムでは、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2abc3-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="2abc3-194">次のいずれかの値:*情報、低\*\*、*\* 中、および *高。*</span><span class="sxs-lookup"><span data-stu-id="2abc3-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="2abc3-195">中</span><span class="sxs-lookup"><span data-stu-id="2abc3-195">Medium</span></span>
<span data-ttu-id="2abc3-196">tags</span><span class="sxs-lookup"><span data-stu-id="2abc3-196">tags</span></span> | <span data-ttu-id="2abc3-197">共通の特性を持つインシデントのグループにフラグを設定する場合など、インシデントに関連付けられたカスタム タグの配列。</span><span class="sxs-lookup"><span data-stu-id="2abc3-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="2abc3-198">アラート</span><span class="sxs-lookup"><span data-stu-id="2abc3-198">alerts</span></span> | <span data-ttu-id="2abc3-199">インシデントに関連するアラートのすべてと、重大度、アラートに関与したエンティティ、アラートのソースなどのその他の情報を含む配列。</span><span class="sxs-lookup"><span data-stu-id="2abc3-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="2abc3-200">\[\] (下記のアラート フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="2abc3-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="2abc3-201">通知メタデータ</span><span class="sxs-lookup"><span data-stu-id="2abc3-201">Alerts metadata</span></span>

<span data-ttu-id="2abc3-202">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2abc3-202">Field name</span></span> | <span data-ttu-id="2abc3-203">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-203">Description</span></span> | <span data-ttu-id="2abc3-204">値の例</span><span class="sxs-lookup"><span data-stu-id="2abc3-204">Example value</span></span>
-|-|-
<span data-ttu-id="2abc3-205">alertId</span><span class="sxs-lookup"><span data-stu-id="2abc3-205">alertId</span></span> | <span data-ttu-id="2abc3-206">アラートを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="2abc3-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="2abc3-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="2abc3-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="2abc3-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="2abc3-208">incidentId</span></span> | <span data-ttu-id="2abc3-209">このアラートが関連付けられているインシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="2abc3-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="2abc3-210">924565</span><span class="sxs-lookup"><span data-stu-id="2abc3-210">924565</span></span>
<span data-ttu-id="2abc3-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="2abc3-211">serviceSource</span></span> | <span data-ttu-id="2abc3-212">Microsoft Defender for Endpoint、Microsoft Cloud App Security、Id 用 Microsoft Defender、Microsoft Defender for Office 365 など、アラートの発信元となるサービス。</span><span class="sxs-lookup"><span data-stu-id="2abc3-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="2abc3-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="2abc3-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="2abc3-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-214">creationTime</span></span> | <span data-ttu-id="2abc3-215">アラートが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-215">Time when alert was first created.</span></span> | <span data-ttu-id="2abc3-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="2abc3-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-217">lastUpdatedTime</span></span> | <span data-ttu-id="2abc3-218">バックエンドでアラートが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="2abc3-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="2abc3-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-220">resolvedTime</span></span> | <span data-ttu-id="2abc3-221">アラートが解決された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-221">Time when alert was resolved.</span></span> | <span data-ttu-id="2abc3-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="2abc3-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="2abc3-223">firstActivity</span></span> | <span data-ttu-id="2abc3-224">バックエンドでアクティビティが更新されたとアラートが最初に報告された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="2abc3-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="2abc3-226">title</span><span class="sxs-lookup"><span data-stu-id="2abc3-226">title</span></span> | <span data-ttu-id="2abc3-227">各アラートで使用可能な文字列値を簡単に識別します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="2abc3-228">ランサムウェア アクティビティ</span><span class="sxs-lookup"><span data-stu-id="2abc3-228">Ransomware activity</span></span>
<span data-ttu-id="2abc3-229">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-229">description</span></span> | <span data-ttu-id="2abc3-230">各アラートを説明する文字列値。</span><span class="sxs-lookup"><span data-stu-id="2abc3-230">String value describing each alert.</span></span> | <span data-ttu-id="2abc3-231">ユーザー Test User2 (testUser2@contoso.com) は、一般的でない拡張子 *の herunterladen* で終わる複数の拡張子を持つ 99 のファイルを操作しました。</span><span class="sxs-lookup"><span data-stu-id="2abc3-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="2abc3-232">これは、異常な数のファイル操作であり、潜在的なランサムウェア攻撃を示しています。</span><span class="sxs-lookup"><span data-stu-id="2abc3-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="2abc3-233">category</span><span class="sxs-lookup"><span data-stu-id="2abc3-233">category</span></span> | <span data-ttu-id="2abc3-234">キル チェーンに沿った攻撃の進行状況を視覚的および数値で表示します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="2abc3-235">[MITRE ATT&CK™配置されます](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="2abc3-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="2abc3-236">影響</span><span class="sxs-lookup"><span data-stu-id="2abc3-236">Impact</span></span>
<span data-ttu-id="2abc3-237">status</span><span class="sxs-lookup"><span data-stu-id="2abc3-237">status</span></span> | <span data-ttu-id="2abc3-238">通知を分類します ( *新規*、 *アクティブ*、 *または解決済み*)。</span><span class="sxs-lookup"><span data-stu-id="2abc3-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="2abc3-239">これは、アラートへの応答を整理して管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="2abc3-240">新規</span><span class="sxs-lookup"><span data-stu-id="2abc3-240">New</span></span>
<span data-ttu-id="2abc3-241">severity</span><span class="sxs-lookup"><span data-stu-id="2abc3-241">severity</span></span> | <span data-ttu-id="2abc3-242">資産への影響の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="2abc3-243">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="2abc3-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="2abc3-244">通常、重要度の高いアイテムでは、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="2abc3-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="2abc3-245">次のいずれかの値:*情報、低\*\*、*\* 中、および *高。*</span><span class="sxs-lookup"><span data-stu-id="2abc3-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="2abc3-246">中</span><span class="sxs-lookup"><span data-stu-id="2abc3-246">Medium</span></span>
<span data-ttu-id="2abc3-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="2abc3-247">investigationId</span></span> | <span data-ttu-id="2abc3-248">このアラートによってトリガーされる自動調査 ID。</span><span class="sxs-lookup"><span data-stu-id="2abc3-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="2abc3-249">1234</span><span class="sxs-lookup"><span data-stu-id="2abc3-249">1234</span></span>
<span data-ttu-id="2abc3-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="2abc3-250">investigationState</span></span> | <span data-ttu-id="2abc3-251">調査の現在の状態に関する情報。</span><span class="sxs-lookup"><span data-stu-id="2abc3-251">Information on the investigation's current status.</span></span> <span data-ttu-id="2abc3-252">Unknown 、 *Terminated*、 *SuccessfullyRemediated 、 SuccessfullyRemediated*、   *PartiallyRemediated*、 *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*. </span><span class="sxs-lookup"><span data-stu-id="2abc3-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="2abc3-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="2abc3-253">UnsupportedAlertType</span></span>
<span data-ttu-id="2abc3-254">classification</span><span class="sxs-lookup"><span data-stu-id="2abc3-254">classification</span></span> | <span data-ttu-id="2abc3-255">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="2abc3-255">The specification for the incident.</span></span> <span data-ttu-id="2abc3-256">プロパティの値は、Unknown、FalsePositive、TruePositive、*または null です。*   </span><span class="sxs-lookup"><span data-stu-id="2abc3-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="2abc3-257">不明</span><span class="sxs-lookup"><span data-stu-id="2abc3-257">Unknown</span></span>
<span data-ttu-id="2abc3-258">判断</span><span class="sxs-lookup"><span data-stu-id="2abc3-258">determination</span></span> | <span data-ttu-id="2abc3-259">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="2abc3-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="2abc3-260">プロパティの値は *、NotAvailable*、Apt、Malware、SecurityPersonnel、SecurityTesting、UnwantedSoftware、Other または null *です。*   </span><span class="sxs-lookup"><span data-stu-id="2abc3-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="2abc3-261">Apt</span><span class="sxs-lookup"><span data-stu-id="2abc3-261">Apt</span></span>
<span data-ttu-id="2abc3-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="2abc3-262">assignedTo</span></span> | <span data-ttu-id="2abc3-263">インシデントの所有者、または *所有者が割り* 当てられていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="2abc3-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="2abc3-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-264">secop2@contoso.com</span></span>
<span data-ttu-id="2abc3-265">actorName</span><span class="sxs-lookup"><span data-stu-id="2abc3-265">actorName</span></span> | <span data-ttu-id="2abc3-266">このアラートに関連付けられているアクティビティ グループ (含まれる場合)。</span><span class="sxs-lookup"><span data-stu-id="2abc3-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="2abc3-267">1997</span><span class="sxs-lookup"><span data-stu-id="2abc3-267">BORON</span></span>
<span data-ttu-id="2abc3-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="2abc3-268">threatFamilyName</span></span> | <span data-ttu-id="2abc3-269">このアラートに関連付けられている脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="2abc3-270">null</span><span class="sxs-lookup"><span data-stu-id="2abc3-270">null</span></span>
<span data-ttu-id="2abc3-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="2abc3-271">mitreTechniques</span></span> | <span data-ttu-id="2abc3-272">MITRE ATT と [CK](https://attack.mitre.org/)フレームワークに合&攻撃™です。</span><span class="sxs-lookup"><span data-stu-id="2abc3-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="2abc3-273">devices</span><span class="sxs-lookup"><span data-stu-id="2abc3-273">devices</span></span> | <span data-ttu-id="2abc3-274">インシデントに関連するアラートが送信されたデバイスすべて。</span><span class="sxs-lookup"><span data-stu-id="2abc3-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="2abc3-275">\[\] (以下のエンティティ フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="2abc3-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="2abc3-276">デバイスの形式</span><span class="sxs-lookup"><span data-stu-id="2abc3-276">Device format</span></span>

<span data-ttu-id="2abc3-277">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2abc3-277">Field name</span></span> | <span data-ttu-id="2abc3-278">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-278">Description</span></span> | <span data-ttu-id="2abc3-279">値の例</span><span class="sxs-lookup"><span data-stu-id="2abc3-279">Example value</span></span>
-|-|-
<span data-ttu-id="2abc3-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="2abc3-280">DeviceId</span></span> | <span data-ttu-id="2abc3-281">Microsoft Defender ATP で指定されているデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="2abc3-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="2abc3-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="2abc3-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="2abc3-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="2abc3-283">aadDeviceId</span></span> |  <span data-ttu-id="2abc3-284">Azure Active Directory で指定されているデバイス[ID。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="2abc3-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="2abc3-285">ドメインに参加しているデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2abc3-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="2abc3-286">null</span><span class="sxs-lookup"><span data-stu-id="2abc3-286">null</span></span>
<span data-ttu-id="2abc3-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="2abc3-287">deviceDnsName</span></span> | <span data-ttu-id="2abc3-288">デバイスの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="2abc3-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="2abc3-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="2abc3-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="2abc3-290">osPlatform</span></span> | <span data-ttu-id="2abc3-291">デバイスが実行されている OS プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="2abc3-291">The OS platform the device is running.</span></span>| <span data-ttu-id="2abc3-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="2abc3-292">WindowsServer2016</span></span>
<span data-ttu-id="2abc3-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="2abc3-293">osBuild</span></span> | <span data-ttu-id="2abc3-294">デバイスが実行されている OS のビルド バージョン。</span><span class="sxs-lookup"><span data-stu-id="2abc3-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="2abc3-295">14393</span><span class="sxs-lookup"><span data-stu-id="2abc3-295">14393</span></span>
<span data-ttu-id="2abc3-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2abc3-296">rbacGroupName</span></span> | <span data-ttu-id="2abc3-297">デバイス [に関連付けられている役割ベースの](https://docs.microsoft.com/azure/role-based-access-control/overview) アクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="2abc3-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="2abc3-298">WDATP-Ring0</span></span>
<span data-ttu-id="2abc3-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="2abc3-299">firstSeen</span></span> | <span data-ttu-id="2abc3-300">デバイスが最初に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="2abc3-300">Time when device was first seen.</span></span> | <span data-ttu-id="2abc3-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="2abc3-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="2abc3-302">healthStatus</span></span> | <span data-ttu-id="2abc3-303">デバイスの正常性状態。</span><span class="sxs-lookup"><span data-stu-id="2abc3-303">The health state of the device.</span></span> | <span data-ttu-id="2abc3-304">Active</span><span class="sxs-lookup"><span data-stu-id="2abc3-304">Active</span></span>
<span data-ttu-id="2abc3-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="2abc3-305">riskScore</span></span> | <span data-ttu-id="2abc3-306">デバイスのリスク スコア。</span><span class="sxs-lookup"><span data-stu-id="2abc3-306">The risk score for the  device.</span></span> | <span data-ttu-id="2abc3-307">高</span><span class="sxs-lookup"><span data-stu-id="2abc3-307">High</span></span>
<span data-ttu-id="2abc3-308">entities</span><span class="sxs-lookup"><span data-stu-id="2abc3-308">entities</span></span> | <span data-ttu-id="2abc3-309">特定のアラートの一部として識別された、または関連付けされているすべてのエンティティ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="2abc3-310">\[\] (以下のエンティティ フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="2abc3-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="2abc3-311">エンティティの形式</span><span class="sxs-lookup"><span data-stu-id="2abc3-311">Entity Format</span></span>

<span data-ttu-id="2abc3-312">フィールド名</span><span class="sxs-lookup"><span data-stu-id="2abc3-312">Field name</span></span> | <span data-ttu-id="2abc3-313">説明</span><span class="sxs-lookup"><span data-stu-id="2abc3-313">Description</span></span> | <span data-ttu-id="2abc3-314">値の例</span><span class="sxs-lookup"><span data-stu-id="2abc3-314">Example value</span></span>
-|-|-
<span data-ttu-id="2abc3-315">entityType</span><span class="sxs-lookup"><span data-stu-id="2abc3-315">entityType</span></span> | <span data-ttu-id="2abc3-316">特定のアラートの一部として識別された、または関連付けされているエンティティ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="2abc3-317">プロパティの値は *、User*、Ip、Url、File、Process、MailBox、MailMessage、MailCluster、Registry *です*。       </span><span class="sxs-lookup"><span data-stu-id="2abc3-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="2abc3-318">User</span><span class="sxs-lookup"><span data-stu-id="2abc3-318">User</span></span>
<span data-ttu-id="2abc3-319">sha1</span><span class="sxs-lookup"><span data-stu-id="2abc3-319">sha1</span></span> | <span data-ttu-id="2abc3-320">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="2abc3-321">ファイルまたはプロセスに関連付けられているアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="2abc3-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="2abc3-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="2abc3-323">sha256</span><span class="sxs-lookup"><span data-stu-id="2abc3-323">sha256</span></span> | <span data-ttu-id="2abc3-324">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="2abc3-325">ファイルまたはプロセスに関連付けられているアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="2abc3-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="2abc3-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="2abc3-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="2abc3-327">fileName</span><span class="sxs-lookup"><span data-stu-id="2abc3-327">fileName</span></span> | <span data-ttu-id="2abc3-328">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="2abc3-329">ファイルまたはプロセスに関連付けられているアラートのファイル名</span><span class="sxs-lookup"><span data-stu-id="2abc3-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="2abc3-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="2abc3-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="2abc3-331">filePath</span><span class="sxs-lookup"><span data-stu-id="2abc3-331">filePath</span></span> | <span data-ttu-id="2abc3-332">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="2abc3-333">ファイルまたはプロセスに関連付けられているアラートのファイル パス</span><span class="sxs-lookup"><span data-stu-id="2abc3-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="2abc3-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="2abc3-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="2abc3-335">processId</span><span class="sxs-lookup"><span data-stu-id="2abc3-335">processId</span></span> | <span data-ttu-id="2abc3-336">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2abc3-337">24348</span><span class="sxs-lookup"><span data-stu-id="2abc3-337">24348</span></span>
<span data-ttu-id="2abc3-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="2abc3-338">processCommandLine</span></span> | <span data-ttu-id="2abc3-339">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2abc3-340">"ファイルをダウンロードする準備が \_ できました1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="2abc3-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="2abc3-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-341">processCreationTime</span></span> | <span data-ttu-id="2abc3-342">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2abc3-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="2abc3-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="2abc3-344">parentProcessId</span></span> | <span data-ttu-id="2abc3-345">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2abc3-346">16840</span><span class="sxs-lookup"><span data-stu-id="2abc3-346">16840</span></span>
<span data-ttu-id="2abc3-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="2abc3-347">parentProcessCreationTime</span></span> | <span data-ttu-id="2abc3-348">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="2abc3-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="2abc3-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="2abc3-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="2abc3-350">ipAddress</span></span> | <span data-ttu-id="2abc3-351">entityType が Ip の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="2abc3-352">悪意のあるネットワークの宛先への通信など、ネットワーク イベントに関連付けられている *アラートの* IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="2abc3-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="2abc3-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="2abc3-353">62.216.203.204</span></span>
<span data-ttu-id="2abc3-354">url</span><span class="sxs-lookup"><span data-stu-id="2abc3-354">url</span></span> | <span data-ttu-id="2abc3-355">entityType が Url の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="2abc3-356">悪意のあるネットワークの宛先への通信など、ネットワーク イベントに関連付 *けられているアラートの URL。*</span><span class="sxs-lookup"><span data-stu-id="2abc3-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="2abc3-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="2abc3-357">down.esales360.cn</span></span>
<span data-ttu-id="2abc3-358">accountName</span><span class="sxs-lookup"><span data-stu-id="2abc3-358">accountName</span></span> | <span data-ttu-id="2abc3-359">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="2abc3-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="2abc3-360">testUser2</span></span>
<span data-ttu-id="2abc3-361">domainName</span><span class="sxs-lookup"><span data-stu-id="2abc3-361">domainName</span></span> | <span data-ttu-id="2abc3-362">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="2abc3-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="2abc3-363">europe.corp.contoso</span></span>
<span data-ttu-id="2abc3-364">userSid</span><span class="sxs-lookup"><span data-stu-id="2abc3-364">userSid</span></span> | <span data-ttu-id="2abc3-365">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="2abc3-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="2abc3-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="2abc3-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="2abc3-367">aadUserId</span></span> | <span data-ttu-id="2abc3-368">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="2abc3-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="2abc3-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="2abc3-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2abc3-370">userPrincipalName</span></span> | <span data-ttu-id="2abc3-371">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2abc3-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-372">testUser2@contoso.com</span></span>
<span data-ttu-id="2abc3-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="2abc3-373">mailboxDisplayName</span></span> | <span data-ttu-id="2abc3-374">entityType が *MailBox の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="2abc3-375">User2 のテスト</span><span class="sxs-lookup"><span data-stu-id="2abc3-375">test User2</span></span>
<span data-ttu-id="2abc3-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="2abc3-376">mailboxAddress</span></span> | <span data-ttu-id="2abc3-377">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2abc3-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-378">testUser2@contoso.com</span></span>
<span data-ttu-id="2abc3-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="2abc3-379">clusterBy</span></span> | <span data-ttu-id="2abc3-380">entityType が  *MailCluster の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="2abc3-381">件名P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="2abc3-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="2abc3-382">sender</span><span class="sxs-lookup"><span data-stu-id="2abc3-382">sender</span></span> | <span data-ttu-id="2abc3-383">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="2abc3-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="2abc3-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="2abc3-385">受信者</span><span class="sxs-lookup"><span data-stu-id="2abc3-385">recipient</span></span> | <span data-ttu-id="2abc3-386">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2abc3-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2abc3-387">testUser2@contoso.com</span></span>
<span data-ttu-id="2abc3-388">subject</span><span class="sxs-lookup"><span data-stu-id="2abc3-388">subject</span></span> | <span data-ttu-id="2abc3-389">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2abc3-390">\[外部 \] の注意</span><span class="sxs-lookup"><span data-stu-id="2abc3-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="2abc3-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="2abc3-391">deliveryAction</span></span> | <span data-ttu-id="2abc3-392">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="2abc3-393">配信</span><span class="sxs-lookup"><span data-stu-id="2abc3-393">Delivered</span></span>
<span data-ttu-id="2abc3-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="2abc3-394">securityGroupId</span></span> | <span data-ttu-id="2abc3-395">entityType が  *SecurityGroup の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="2abc3-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="2abc3-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="2abc3-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="2abc3-397">securityGroupName</span></span> | <span data-ttu-id="2abc3-398">entityType が  *SecurityGroup の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="2abc3-399">ネットワーク構成演算子</span><span class="sxs-lookup"><span data-stu-id="2abc3-399">Network Configuration Operators</span></span>
<span data-ttu-id="2abc3-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="2abc3-400">registryHive</span></span> | <span data-ttu-id="2abc3-401">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2abc3-402">HKEY \_ ローカル \_ コンピューター</span><span class="sxs-lookup"><span data-stu-id="2abc3-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="2abc3-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="2abc3-403">registryKey</span></span> | <span data-ttu-id="2abc3-404">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2abc3-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="2abc3-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="2abc3-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="2abc3-406">registryValueType</span></span> | <span data-ttu-id="2abc3-407">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2abc3-408">String</span><span class="sxs-lookup"><span data-stu-id="2abc3-408">String</span></span>
<span data-ttu-id="2abc3-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="2abc3-409">registryValue</span></span> | <span data-ttu-id="2abc3-410">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="2abc3-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="2abc3-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="2abc3-411">31-00-00-00</span></span>
<span data-ttu-id="2abc3-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="2abc3-412">deviceId</span></span> | <span data-ttu-id="2abc3-413">エンティティに関連するデバイスの ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="2abc3-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="2abc3-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="2abc3-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="2abc3-415">例</span><span class="sxs-lookup"><span data-stu-id="2abc3-415">Example</span></span>

<span data-ttu-id="2abc3-416">**要求**</span><span class="sxs-lookup"><span data-stu-id="2abc3-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="2abc3-417">**応答**</span><span class="sxs-lookup"><span data-stu-id="2abc3-417">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="2abc3-418">関連記事</span><span class="sxs-lookup"><span data-stu-id="2abc3-418">Related articles</span></span>

- [<span data-ttu-id="2abc3-419">Microsoft 365 Defender API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="2abc3-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="2abc3-420">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="2abc3-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="2abc3-421">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="2abc3-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="2abc3-422">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="2abc3-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2abc3-423">インシデント API</span><span class="sxs-lookup"><span data-stu-id="2abc3-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="2abc3-424">インシデント API を更新する</span><span class="sxs-lookup"><span data-stu-id="2abc3-424">Update incident API</span></span>](api-update-incidents.md)
