---
title: Microsoft 365ディフェンダーでインシデント API を一覧表示する
description: Microsoft 365ディフェンダーでインシデント API を一覧表示する方法を学ぶ
keywords: リスト,インシデント,インシデント,API
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
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572155"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="18c98-104">Microsoft 365ディフェンダーでインシデント API を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="18c98-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="18c98-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="18c98-105">**Applies to:**</span></span>

- <span data-ttu-id="18c98-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18c98-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18c98-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="18c98-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="18c98-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="18c98-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="18c98-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="18c98-109">API description</span></span>

<span data-ttu-id="18c98-110">リスト インシデント API を使用すると、インシデントを並べ替えて、情報に基づいたサイバーセキュリティ対応を作成できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="18c98-111">環境の保持ポリシーで指定した時間範囲内で、ネットワークでフラグが設定されたインシデントのコレクションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="18c98-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="18c98-112">最新のインシデントがリストの先頭に表示されます。</span><span class="sxs-lookup"><span data-stu-id="18c98-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="18c98-113">各インシデントには、関連するアラートと関連エンティティの配列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="18c98-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="18c98-114">API は、次の **OData** 演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="18c98-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="18c98-115">`$filter` 、 `lastUpdateTime` `createdTime` 、 、 `status` および `assignedTo` プロパティ</span><span class="sxs-lookup"><span data-stu-id="18c98-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="18c98-116">`$top`の最大値が **100** の場合</span><span class="sxs-lookup"><span data-stu-id="18c98-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="18c98-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="18c98-117">Limitations</span></span>

1. <span data-ttu-id="18c98-118">最大ページ サイズは **100 件です**。</span><span class="sxs-lookup"><span data-stu-id="18c98-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="18c98-119">要求の最大レートは **、1 分あたり 50 回の呼び出し** と **1 時間あたり 1500 件の呼び出し** です。</span><span class="sxs-lookup"><span data-stu-id="18c98-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="18c98-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="18c98-120">Permissions</span></span>

<span data-ttu-id="18c98-121">この API を呼び出すためには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="18c98-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="18c98-122">アクセス許可の選択方法など、詳細については[、「Defender API へのアクセスMicrosoft 365」を](api-access.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="18c98-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="18c98-123">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="18c98-123">Permission type</span></span> | <span data-ttu-id="18c98-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="18c98-124">Permission</span></span> | <span data-ttu-id="18c98-125">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="18c98-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="18c98-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="18c98-126">Application</span></span> | <span data-ttu-id="18c98-127">インシデント.読み取り.すべて</span><span class="sxs-lookup"><span data-stu-id="18c98-127">Incident.Read.All</span></span> | <span data-ttu-id="18c98-128">すべてのインシデントを読み取る</span><span class="sxs-lookup"><span data-stu-id="18c98-128">Read all incidents</span></span>
<span data-ttu-id="18c98-129">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="18c98-129">Application</span></span> | <span data-ttu-id="18c98-130">インシデント.読み書き.すべて</span><span class="sxs-lookup"><span data-stu-id="18c98-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="18c98-131">すべてのインシデントの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="18c98-131">Read and write all incidents</span></span>
<span data-ttu-id="18c98-132">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="18c98-132">Delegated (work or school account)</span></span> | <span data-ttu-id="18c98-133">インシデント.読み取り</span><span class="sxs-lookup"><span data-stu-id="18c98-133">Incident.Read</span></span> | <span data-ttu-id="18c98-134">インシデントを読む</span><span class="sxs-lookup"><span data-stu-id="18c98-134">Read incidents</span></span>
<span data-ttu-id="18c98-135">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="18c98-135">Delegated (work or school account)</span></span> | <span data-ttu-id="18c98-136">インシデント.読み取り書き込み</span><span class="sxs-lookup"><span data-stu-id="18c98-136">Incident.ReadWrite</span></span> | <span data-ttu-id="18c98-137">インシデントの読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="18c98-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="18c98-138">ユーザーの資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="18c98-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="18c98-139">ユーザには、ポータルのインシデントに対する表示権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="18c98-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="18c98-140">応答には、ユーザーが公開されているインシデントのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="18c98-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="18c98-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="18c98-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="18c98-142">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="18c98-142">Request headers</span></span>

<span data-ttu-id="18c98-143">名前</span><span class="sxs-lookup"><span data-stu-id="18c98-143">Name</span></span> | <span data-ttu-id="18c98-144">型</span><span class="sxs-lookup"><span data-stu-id="18c98-144">Type</span></span> | <span data-ttu-id="18c98-145">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-145">Description</span></span>
-|-|-
<span data-ttu-id="18c98-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="18c98-146">Authorization</span></span> | <span data-ttu-id="18c98-147">String</span><span class="sxs-lookup"><span data-stu-id="18c98-147">String</span></span> | <span data-ttu-id="18c98-148">ベアラー {トークン}</span><span class="sxs-lookup"><span data-stu-id="18c98-148">Bearer {token}.</span></span> <span data-ttu-id="18c98-149">**必須**</span><span class="sxs-lookup"><span data-stu-id="18c98-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="18c98-150">要求本文</span><span class="sxs-lookup"><span data-stu-id="18c98-150">Request body</span></span>

<span data-ttu-id="18c98-151">なし。</span><span class="sxs-lookup"><span data-stu-id="18c98-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="18c98-152">応答</span><span class="sxs-lookup"><span data-stu-id="18c98-152">Response</span></span>

<span data-ttu-id="18c98-153">成功した場合、このメソッドは `200 OK` 、応答本文に [インシデント](api-incident.md) の一覧とを返します。</span><span class="sxs-lookup"><span data-stu-id="18c98-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="18c98-154">スキーママッピング</span><span class="sxs-lookup"><span data-stu-id="18c98-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="18c98-155">インシデントメタデータ</span><span class="sxs-lookup"><span data-stu-id="18c98-155">Incident metadata</span></span>

<span data-ttu-id="18c98-156">フィールド名</span><span class="sxs-lookup"><span data-stu-id="18c98-156">Field name</span></span> | <span data-ttu-id="18c98-157">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-157">Description</span></span> | <span data-ttu-id="18c98-158">値の例</span><span class="sxs-lookup"><span data-stu-id="18c98-158">Example value</span></span>
-|-|-
<span data-ttu-id="18c98-159">インシデントId</span><span class="sxs-lookup"><span data-stu-id="18c98-159">incidentId</span></span> | <span data-ttu-id="18c98-160">インシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="18c98-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="18c98-161">924565</span><span class="sxs-lookup"><span data-stu-id="18c98-161">924565</span></span>
<span data-ttu-id="18c98-162">インシデント ID をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="18c98-162">redirectIncidentId</span></span> | <span data-ttu-id="18c98-163">インシデント処理ロジックの一部として、インシデントが別のインシデントとグループ化されている場合にのみ、設定されます。</span><span class="sxs-lookup"><span data-stu-id="18c98-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="18c98-164">924569</span><span class="sxs-lookup"><span data-stu-id="18c98-164">924569</span></span>
<span data-ttu-id="18c98-165">インシデント名</span><span class="sxs-lookup"><span data-stu-id="18c98-165">incidentName</span></span> | <span data-ttu-id="18c98-166">すべてのインシデントで使用できる文字列値。</span><span class="sxs-lookup"><span data-stu-id="18c98-166">String value available for every incident.</span></span> | <span data-ttu-id="18c98-167">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="18c98-167">Ransomware activity</span></span>
<span data-ttu-id="18c98-168">作成された時刻</span><span class="sxs-lookup"><span data-stu-id="18c98-168">createdTime</span></span> | <span data-ttu-id="18c98-169">インシデントが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-169">Time when incident was first created.</span></span> | <span data-ttu-id="18c98-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="18c98-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="18c98-171">ラストアップデート時間</span><span class="sxs-lookup"><span data-stu-id="18c98-171">lastUpdateTime</span></span> | <span data-ttu-id="18c98-172">バックエンドでインシデントが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="18c98-173">このフィールドは、インシデントが取得される時間範囲の要求パラメーターを設定するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="18c98-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="18c98-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="18c98-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="18c98-175">assignedTo</span></span> | <span data-ttu-id="18c98-176">インシデントの所有者、または所有者が割り当てられていない場合は *null。*</span><span class="sxs-lookup"><span data-stu-id="18c98-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="18c98-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-177">secop2@contoso.com</span></span>
<span data-ttu-id="18c98-178">classification</span><span class="sxs-lookup"><span data-stu-id="18c98-178">classification</span></span> | <span data-ttu-id="18c98-179">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="18c98-179">The specification for the incident.</span></span> <span data-ttu-id="18c98-180">プロパティ値は *、不明*、 *誤検出*、 *真陽性です。*</span><span class="sxs-lookup"><span data-stu-id="18c98-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="18c98-181">不明</span><span class="sxs-lookup"><span data-stu-id="18c98-181">Unknown</span></span>
<span data-ttu-id="18c98-182">決定</span><span class="sxs-lookup"><span data-stu-id="18c98-182">determination</span></span> | <span data-ttu-id="18c98-183">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c98-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="18c98-184">プロパティ値は次のとおりです: *利用できません*, *Apt*, *マルウェア*, *セキュリティ要員*, *セキュリティテスト*, *不要なソフトウェア*, *その他*</span><span class="sxs-lookup"><span data-stu-id="18c98-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="18c98-185">利用できません</span><span class="sxs-lookup"><span data-stu-id="18c98-185">NotAvailable</span></span>
<span data-ttu-id="18c98-186">status</span><span class="sxs-lookup"><span data-stu-id="18c98-186">status</span></span> | <span data-ttu-id="18c98-187">インシデントを *[アクティブ*] 、または [ *解決済み*] として分類します。</span><span class="sxs-lookup"><span data-stu-id="18c98-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="18c98-188">インシデントへの対応を整理して管理できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="18c98-189">有効</span><span class="sxs-lookup"><span data-stu-id="18c98-189">Active</span></span>
<span data-ttu-id="18c98-190">severity</span><span class="sxs-lookup"><span data-stu-id="18c98-190">severity</span></span> | <span data-ttu-id="18c98-191">資産に与える可能性のある影響を示します。</span><span class="sxs-lookup"><span data-stu-id="18c98-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="18c98-192">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="18c98-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="18c98-193">通常、重大度が高い項目は、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="18c98-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="18c98-194">次の値の 1 つ:*情報、\*\*低*、\*中、および *高*。</span><span class="sxs-lookup"><span data-stu-id="18c98-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="18c98-195">中</span><span class="sxs-lookup"><span data-stu-id="18c98-195">Medium</span></span>
<span data-ttu-id="18c98-196">tags</span><span class="sxs-lookup"><span data-stu-id="18c98-196">tags</span></span> | <span data-ttu-id="18c98-197">インシデントに関連付けられたカスタム タグの配列 (たとえば、共通の特性を持つインシデントのグループにフラグを付ける場合)。</span><span class="sxs-lookup"><span data-stu-id="18c98-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="18c98-198">comments</span><span class="sxs-lookup"><span data-stu-id="18c98-198">comments</span></span> | <span data-ttu-id="18c98-199">インシデントを管理するときに secops によって作成されたコメントの配列です。</span><span class="sxs-lookup"><span data-stu-id="18c98-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="18c98-200">アラート</span><span class="sxs-lookup"><span data-stu-id="18c98-200">alerts</span></span> | <span data-ttu-id="18c98-201">インシデントに関連するすべてのアラートと、重大度、アラートに関与したエンティティ、アラートのソースなどのその他の情報を含む配列。</span><span class="sxs-lookup"><span data-stu-id="18c98-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="18c98-202">\[\] (下記のアラートフィールドの詳細を参照)</span><span class="sxs-lookup"><span data-stu-id="18c98-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="18c98-203">アラートメタデータ</span><span class="sxs-lookup"><span data-stu-id="18c98-203">Alerts metadata</span></span>

<span data-ttu-id="18c98-204">フィールド名</span><span class="sxs-lookup"><span data-stu-id="18c98-204">Field name</span></span> | <span data-ttu-id="18c98-205">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-205">Description</span></span> | <span data-ttu-id="18c98-206">値の例</span><span class="sxs-lookup"><span data-stu-id="18c98-206">Example value</span></span>
-|-|-
<span data-ttu-id="18c98-207">アラートId</span><span class="sxs-lookup"><span data-stu-id="18c98-207">alertId</span></span> | <span data-ttu-id="18c98-208">警告を表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="18c98-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="18c98-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="18c98-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="18c98-210">インシデントId</span><span class="sxs-lookup"><span data-stu-id="18c98-210">incidentId</span></span> | <span data-ttu-id="18c98-211">このアラートが関連付けられているインシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="18c98-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="18c98-212">924565</span><span class="sxs-lookup"><span data-stu-id="18c98-212">924565</span></span>
<span data-ttu-id="18c98-213">サービスソース</span><span class="sxs-lookup"><span data-stu-id="18c98-213">serviceSource</span></span> | <span data-ttu-id="18c98-214">エンドポイントの Microsoft Defender、Microsoft Cloud App Security、Id のマイクロソフト ディフェンダー、Office 365用のマイクロソフト ディフェンダーなど、アラートの発生元のサービス。</span><span class="sxs-lookup"><span data-stu-id="18c98-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="18c98-215">マイクロソフトクラウドアプセキュリティ</span><span class="sxs-lookup"><span data-stu-id="18c98-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="18c98-216">作成時間</span><span class="sxs-lookup"><span data-stu-id="18c98-216">creationTime</span></span> | <span data-ttu-id="18c98-217">アラートが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-217">Time when alert was first created.</span></span> | <span data-ttu-id="18c98-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="18c98-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="18c98-219">最後に更新された時間</span><span class="sxs-lookup"><span data-stu-id="18c98-219">lastUpdatedTime</span></span> | <span data-ttu-id="18c98-220">バックエンドでアラートが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="18c98-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="18c98-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="18c98-222">解決された時間</span><span class="sxs-lookup"><span data-stu-id="18c98-222">resolvedTime</span></span> | <span data-ttu-id="18c98-223">アラートが解決された時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-223">Time when alert was resolved.</span></span> | <span data-ttu-id="18c98-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="18c98-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="18c98-225">最初の活動</span><span class="sxs-lookup"><span data-stu-id="18c98-225">firstActivity</span></span> | <span data-ttu-id="18c98-226">バックエンドでアクティビティが更新されたことをアラートが最初に報告した時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="18c98-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="18c98-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="18c98-228">title</span><span class="sxs-lookup"><span data-stu-id="18c98-228">title</span></span> | <span data-ttu-id="18c98-229">各アラートに使用できる簡単な識別文字列値。</span><span class="sxs-lookup"><span data-stu-id="18c98-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="18c98-230">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="18c98-230">Ransomware activity</span></span>
<span data-ttu-id="18c98-231">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-231">description</span></span> | <span data-ttu-id="18c98-232">各アラートを説明する文字列値。</span><span class="sxs-lookup"><span data-stu-id="18c98-232">String value describing each alert.</span></span> | <span data-ttu-id="18c98-233">ユーザーテストUser2 (testUser2@contoso.com) は、複数の拡張子が一般的でない拡張子 *herunterladen* で終わる 99 のファイルを操作しました。</span><span class="sxs-lookup"><span data-stu-id="18c98-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="18c98-234">これは、ファイル操作の異常な数であり、潜在的なランサムウェア攻撃を示しています。</span><span class="sxs-lookup"><span data-stu-id="18c98-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="18c98-235">category</span><span class="sxs-lookup"><span data-stu-id="18c98-235">category</span></span> | <span data-ttu-id="18c98-236">キルチェーンに沿って攻撃がどこまで進行したかの視覚的および数値的なビュー。</span><span class="sxs-lookup"><span data-stu-id="18c98-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="18c98-237">[MITRE ATT&CK™ フレームワーク](https://attack.mitre.org/)に合わせて配置します。</span><span class="sxs-lookup"><span data-stu-id="18c98-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="18c98-238">影響</span><span class="sxs-lookup"><span data-stu-id="18c98-238">Impact</span></span>
<span data-ttu-id="18c98-239">status</span><span class="sxs-lookup"><span data-stu-id="18c98-239">status</span></span> | <span data-ttu-id="18c98-240">アラートを [ *新規作成*]、[ *アクティブ*]、[ *解決済み*] の順に分類します。</span><span class="sxs-lookup"><span data-stu-id="18c98-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="18c98-241">アラートへの対応を整理して管理できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="18c98-242">新規</span><span class="sxs-lookup"><span data-stu-id="18c98-242">New</span></span>
<span data-ttu-id="18c98-243">severity</span><span class="sxs-lookup"><span data-stu-id="18c98-243">severity</span></span> | <span data-ttu-id="18c98-244">資産に与える可能性のある影響を示します。</span><span class="sxs-lookup"><span data-stu-id="18c98-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="18c98-245">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="18c98-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="18c98-246">通常、重大度が高い項目は、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="18c98-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="18c98-247">次の値の 1 つ:*情報、\*\*低*、\*中、および *高*。</span><span class="sxs-lookup"><span data-stu-id="18c98-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="18c98-248">中</span><span class="sxs-lookup"><span data-stu-id="18c98-248">Medium</span></span>
<span data-ttu-id="18c98-249">調査Id</span><span class="sxs-lookup"><span data-stu-id="18c98-249">investigationId</span></span> | <span data-ttu-id="18c98-250">このアラートによってトリガーされる自動調査 ID。</span><span class="sxs-lookup"><span data-stu-id="18c98-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="18c98-251">1234</span><span class="sxs-lookup"><span data-stu-id="18c98-251">1234</span></span>
<span data-ttu-id="18c98-252">調査状態</span><span class="sxs-lookup"><span data-stu-id="18c98-252">investigationState</span></span> | <span data-ttu-id="18c98-253">調査の現在の状態に関する情報。</span><span class="sxs-lookup"><span data-stu-id="18c98-253">Information on the investigation's current status.</span></span> <span data-ttu-id="18c98-254">次の値の 1 つ:*不明*,*終了しました ,\*\*正常に修復されました*,*問題**が発生しました ,**部分的に修復されました*,*実行中*,*保留中の承認*,*保留中のリソース*,*部分的に調査済み*,*終了バイユーザー*,*終了システム ,**キューに入れ,**内部失敗*,*既存の警告*,*サポートされていない人*,*サポートされていないAlertType*,*抑制されたアラート*.</span><span class="sxs-lookup"><span data-stu-id="18c98-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="18c98-255">サポートされていないアラートタイプ</span><span class="sxs-lookup"><span data-stu-id="18c98-255">UnsupportedAlertType</span></span>
<span data-ttu-id="18c98-256">classification</span><span class="sxs-lookup"><span data-stu-id="18c98-256">classification</span></span> | <span data-ttu-id="18c98-257">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="18c98-257">The specification for the incident.</span></span> <span data-ttu-id="18c98-258">プロパティ値は *、不明*、*誤検出\*\*、TruePositive*、または *null です。*</span><span class="sxs-lookup"><span data-stu-id="18c98-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="18c98-259">不明</span><span class="sxs-lookup"><span data-stu-id="18c98-259">Unknown</span></span>
<span data-ttu-id="18c98-260">決定</span><span class="sxs-lookup"><span data-stu-id="18c98-260">determination</span></span> | <span data-ttu-id="18c98-261">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c98-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="18c98-262">プロパティ値は次のとおりです: *利用できません*, *Apt*, *マルウェア*, *セキュリティ要員*, *セキュリティテスト*, *不要なソフトウェア*, *その他* または  *ヌル*</span><span class="sxs-lookup"><span data-stu-id="18c98-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="18c98-263">アプト</span><span class="sxs-lookup"><span data-stu-id="18c98-263">Apt</span></span>
<span data-ttu-id="18c98-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="18c98-264">assignedTo</span></span> | <span data-ttu-id="18c98-265">インシデントの所有者、または所有者が割り当てられていない場合は *null。*</span><span class="sxs-lookup"><span data-stu-id="18c98-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="18c98-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-266">secop2@contoso.com</span></span>
<span data-ttu-id="18c98-267">俳優名</span><span class="sxs-lookup"><span data-stu-id="18c98-267">actorName</span></span> | <span data-ttu-id="18c98-268">このアラートに関連付けられている活動グループ (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="18c98-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="18c98-269">硼素</span><span class="sxs-lookup"><span data-stu-id="18c98-269">BORON</span></span>
<span data-ttu-id="18c98-270">脅威家族名</span><span class="sxs-lookup"><span data-stu-id="18c98-270">threatFamilyName</span></span> | <span data-ttu-id="18c98-271">このアラートに関連付けられている脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="18c98-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="18c98-272">null</span><span class="sxs-lookup"><span data-stu-id="18c98-272">null</span></span>
<span data-ttu-id="18c98-273">ミトレテクニック</span><span class="sxs-lookup"><span data-stu-id="18c98-273">mitreTechniques</span></span> | <span data-ttu-id="18c98-274">[MITRE ATT と](https://attack.mitre.org/)一致する攻撃手法&CK ™ フレームワーク。</span><span class="sxs-lookup"><span data-stu-id="18c98-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="18c98-275">デバイス</span><span class="sxs-lookup"><span data-stu-id="18c98-275">devices</span></span> | <span data-ttu-id="18c98-276">インシデントに関連するアラートが送信されたすべてのデバイス。</span><span class="sxs-lookup"><span data-stu-id="18c98-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="18c98-277">\[\] (下のエンティティ フィールドの詳細を参照)</span><span class="sxs-lookup"><span data-stu-id="18c98-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="18c98-278">デバイス形式</span><span class="sxs-lookup"><span data-stu-id="18c98-278">Device format</span></span>

<span data-ttu-id="18c98-279">フィールド名</span><span class="sxs-lookup"><span data-stu-id="18c98-279">Field name</span></span> | <span data-ttu-id="18c98-280">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-280">Description</span></span> | <span data-ttu-id="18c98-281">値の例</span><span class="sxs-lookup"><span data-stu-id="18c98-281">Example value</span></span>
-|-|-
<span data-ttu-id="18c98-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="18c98-282">DeviceId</span></span> | <span data-ttu-id="18c98-283">エンドポイントの Microsoft Defender で指定されたデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="18c98-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="18c98-284">24c222b0b60fe148eece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="18c98-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="18c98-285">アアドデバイスId</span><span class="sxs-lookup"><span data-stu-id="18c98-285">aadDeviceId</span></span> |  <span data-ttu-id="18c98-286">[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis)で指定されたデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="18c98-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="18c98-287">ドメインに参加しているデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="18c98-288">null</span><span class="sxs-lookup"><span data-stu-id="18c98-288">null</span></span>
<span data-ttu-id="18c98-289">を使用します。</span><span class="sxs-lookup"><span data-stu-id="18c98-289">deviceDnsName</span></span> | <span data-ttu-id="18c98-290">デバイスの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="18c98-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="18c98-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="18c98-292">osプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="18c98-292">osPlatform</span></span> | <span data-ttu-id="18c98-293">デバイスが実行されている OS プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="18c98-293">The OS platform the device is running.</span></span>| <span data-ttu-id="18c98-294">2016</span><span class="sxs-lookup"><span data-stu-id="18c98-294">WindowsServer2016</span></span>
<span data-ttu-id="18c98-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="18c98-295">osBuild</span></span> | <span data-ttu-id="18c98-296">デバイスが実行されている OS のビルド バージョン。</span><span class="sxs-lookup"><span data-stu-id="18c98-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="18c98-297">14393</span><span class="sxs-lookup"><span data-stu-id="18c98-297">14393</span></span>
<span data-ttu-id="18c98-298">バクグループ名</span><span class="sxs-lookup"><span data-stu-id="18c98-298">rbacGroupName</span></span> | <span data-ttu-id="18c98-299">デバイスに関連付けられている [ロール ベースのアクセス制御](/azure/role-based-access-control/overview) (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="18c98-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="18c98-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="18c98-300">WDATP-Ring0</span></span>
<span data-ttu-id="18c98-301">最初に見た</span><span class="sxs-lookup"><span data-stu-id="18c98-301">firstSeen</span></span> | <span data-ttu-id="18c98-302">デバイスが最初に見られた時刻。</span><span class="sxs-lookup"><span data-stu-id="18c98-302">Time when device was first seen.</span></span> | <span data-ttu-id="18c98-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="18c98-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="18c98-304">ヘルスステータス</span><span class="sxs-lookup"><span data-stu-id="18c98-304">healthStatus</span></span> | <span data-ttu-id="18c98-305">デバイスのヘルス状態。</span><span class="sxs-lookup"><span data-stu-id="18c98-305">The health state of the device.</span></span> | <span data-ttu-id="18c98-306">有効</span><span class="sxs-lookup"><span data-stu-id="18c98-306">Active</span></span>
<span data-ttu-id="18c98-307">リスクスコア</span><span class="sxs-lookup"><span data-stu-id="18c98-307">riskScore</span></span> | <span data-ttu-id="18c98-308">デバイスのリスク スコア。</span><span class="sxs-lookup"><span data-stu-id="18c98-308">The risk score for the  device.</span></span> | <span data-ttu-id="18c98-309">高い</span><span class="sxs-lookup"><span data-stu-id="18c98-309">High</span></span>
<span data-ttu-id="18c98-310">エンティティ</span><span class="sxs-lookup"><span data-stu-id="18c98-310">entities</span></span> | <span data-ttu-id="18c98-311">特定のアラートの一部であるか、または関連していると識別されたすべてのエンティティ。</span><span class="sxs-lookup"><span data-stu-id="18c98-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="18c98-312">\[\] (下のエンティティ フィールドの詳細を参照)</span><span class="sxs-lookup"><span data-stu-id="18c98-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="18c98-313">エンティティの形式</span><span class="sxs-lookup"><span data-stu-id="18c98-313">Entity Format</span></span>

<span data-ttu-id="18c98-314">フィールド名</span><span class="sxs-lookup"><span data-stu-id="18c98-314">Field name</span></span> | <span data-ttu-id="18c98-315">説明</span><span class="sxs-lookup"><span data-stu-id="18c98-315">Description</span></span> | <span data-ttu-id="18c98-316">値の例</span><span class="sxs-lookup"><span data-stu-id="18c98-316">Example value</span></span>
-|-|-
<span data-ttu-id="18c98-317">エンティティタイプ</span><span class="sxs-lookup"><span data-stu-id="18c98-317">entityType</span></span> | <span data-ttu-id="18c98-318">特定のアラートの一部であるか、または関連していると識別されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="18c98-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="18c98-319">プロパティの値は、 *次* のとおりです: ユーザー , *Ip*, *URL*, *ファイル*, *プロセス*, *メール ボックス*, *メール メッセージ*, *メールクラスタ*, *レジストリ*</span><span class="sxs-lookup"><span data-stu-id="18c98-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="18c98-320">User</span><span class="sxs-lookup"><span data-stu-id="18c98-320">User</span></span>
<span data-ttu-id="18c98-321">sha1</span><span class="sxs-lookup"><span data-stu-id="18c98-321">sha1</span></span> | <span data-ttu-id="18c98-322">entityType が *ファイル* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="18c98-323">ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="18c98-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="18c98-324">5de839186691aa9ee2ca6d74f0a38fb8d1bd6d</span><span class="sxs-lookup"><span data-stu-id="18c98-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="18c98-325">sha256</span><span class="sxs-lookup"><span data-stu-id="18c98-325">sha256</span></span> | <span data-ttu-id="18c98-326">entityType が *ファイル* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="18c98-327">ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="18c98-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="18c98-328">28cb017dfc99073aa1b47c1b30f413e3ce777c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="18c98-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="18c98-329">fileName</span><span class="sxs-lookup"><span data-stu-id="18c98-329">fileName</span></span> | <span data-ttu-id="18c98-330">entityType が *ファイル* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="18c98-331">ファイルまたはプロセスに関連付けられた警告のファイル名</span><span class="sxs-lookup"><span data-stu-id="18c98-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="18c98-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="18c98-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="18c98-333">ファイルパス</span><span class="sxs-lookup"><span data-stu-id="18c98-333">filePath</span></span> | <span data-ttu-id="18c98-334">entityType が *ファイル* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="18c98-335">ファイルまたはプロセスに関連付けられたアラートのファイル パス</span><span class="sxs-lookup"><span data-stu-id="18c98-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="18c98-336">C: \\ \agent_work_temp\展開\システム\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="18c98-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="18c98-337">プロセスId</span><span class="sxs-lookup"><span data-stu-id="18c98-337">processId</span></span> | <span data-ttu-id="18c98-338">エンティティの種類が *プロセス* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="18c98-339">24348</span><span class="sxs-lookup"><span data-stu-id="18c98-339">24348</span></span>
<span data-ttu-id="18c98-340">コマンドラインを処理します。</span><span class="sxs-lookup"><span data-stu-id="18c98-340">processCommandLine</span></span> | <span data-ttu-id="18c98-341">エンティティの種類が *プロセス* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="18c98-342">"ファイルは1911150169.exeダウンロードする準備ができています \_ "</span><span class="sxs-lookup"><span data-stu-id="18c98-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="18c98-343">プロセス作成時間</span><span class="sxs-lookup"><span data-stu-id="18c98-343">processCreationTime</span></span> | <span data-ttu-id="18c98-344">エンティティの種類が *プロセス* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="18c98-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="18c98-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="18c98-346">親プロセスId</span><span class="sxs-lookup"><span data-stu-id="18c98-346">parentProcessId</span></span> | <span data-ttu-id="18c98-347">エンティティの種類が *プロセス* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="18c98-348">16840</span><span class="sxs-lookup"><span data-stu-id="18c98-348">16840</span></span>
<span data-ttu-id="18c98-349">親プロセス作成時間</span><span class="sxs-lookup"><span data-stu-id="18c98-349">parentProcessCreationTime</span></span> | <span data-ttu-id="18c98-350">エンティティの種類が *プロセス* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="18c98-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="18c98-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="18c98-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="18c98-352">ipAddress</span></span> | <span data-ttu-id="18c98-353">エンティティタイプが *Ip* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="18c98-354">ネットワーク イベントに関連するアラートの IP アドレス ( *悪質なネットワーク宛先への通信* など )。</span><span class="sxs-lookup"><span data-stu-id="18c98-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="18c98-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="18c98-355">62.216.203.204</span></span>
<span data-ttu-id="18c98-356">url</span><span class="sxs-lookup"><span data-stu-id="18c98-356">url</span></span> | <span data-ttu-id="18c98-357">エンティティの種類が *[ Url ]* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="18c98-358">ネットワーク イベントに関連付けられたアラートの URL( *悪意のあるネットワーク宛先への通信* など)。</span><span class="sxs-lookup"><span data-stu-id="18c98-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="18c98-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="18c98-359">down.esales360.cn</span></span>
<span data-ttu-id="18c98-360">アカウント名</span><span class="sxs-lookup"><span data-stu-id="18c98-360">accountName</span></span> | <span data-ttu-id="18c98-361">entityType が *ユーザー* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="18c98-362">テストユーザー2</span><span class="sxs-lookup"><span data-stu-id="18c98-362">testUser2</span></span>
<span data-ttu-id="18c98-363">domainName</span><span class="sxs-lookup"><span data-stu-id="18c98-363">domainName</span></span> | <span data-ttu-id="18c98-364">entityType が *ユーザー* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="18c98-365">ヨーロッパ.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="18c98-365">europe.corp.contoso</span></span>
<span data-ttu-id="18c98-366">ユーザー Sid</span><span class="sxs-lookup"><span data-stu-id="18c98-366">userSid</span></span> | <span data-ttu-id="18c98-367">entityType が *ユーザー* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="18c98-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="18c98-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="18c98-369">アアドユーザーId</span><span class="sxs-lookup"><span data-stu-id="18c98-369">aadUserId</span></span> | <span data-ttu-id="18c98-370">entityType が *ユーザー* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="18c98-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="18c98-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="18c98-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="18c98-372">userPrincipalName</span></span> | <span data-ttu-id="18c98-373">エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="18c98-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-374">testUser2@contoso.com</span></span>
<span data-ttu-id="18c98-375">メールボックス表示名</span><span class="sxs-lookup"><span data-stu-id="18c98-375">mailboxDisplayName</span></span> | <span data-ttu-id="18c98-376">エンティティの種類が *[メール ボックス]* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="18c98-377">テスト ユーザー 2</span><span class="sxs-lookup"><span data-stu-id="18c98-377">test User2</span></span>
<span data-ttu-id="18c98-378">メールボックスアドレス</span><span class="sxs-lookup"><span data-stu-id="18c98-378">mailboxAddress</span></span> | <span data-ttu-id="18c98-379">エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="18c98-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-380">testUser2@contoso.com</span></span>
<span data-ttu-id="18c98-381">クラスターによって</span><span class="sxs-lookup"><span data-stu-id="18c98-381">clusterBy</span></span> | <span data-ttu-id="18c98-382">エンティティの種類が  *メール クラスタ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="18c98-383">件名;をクリックします。コンテンツタイプ</span><span class="sxs-lookup"><span data-stu-id="18c98-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="18c98-384">sender</span><span class="sxs-lookup"><span data-stu-id="18c98-384">sender</span></span> | <span data-ttu-id="18c98-385">エンティティの種類が *ユーザー* / *メール ボックス* / *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="18c98-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="18c98-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="18c98-387">受信者</span><span class="sxs-lookup"><span data-stu-id="18c98-387">recipient</span></span> | <span data-ttu-id="18c98-388">エンティティの種類が *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="18c98-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="18c98-389">testUser2@contoso.com</span></span>
<span data-ttu-id="18c98-390">subject</span><span class="sxs-lookup"><span data-stu-id="18c98-390">subject</span></span> | <span data-ttu-id="18c98-391">エンティティの種類が *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="18c98-392">\[外部 \] の注意</span><span class="sxs-lookup"><span data-stu-id="18c98-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="18c98-393">デリバリーアクション</span><span class="sxs-lookup"><span data-stu-id="18c98-393">deliveryAction</span></span> | <span data-ttu-id="18c98-394">エンティティの種類が *メール メッセージ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="18c98-395">配信</span><span class="sxs-lookup"><span data-stu-id="18c98-395">Delivered</span></span>
<span data-ttu-id="18c98-396">セキュリティグループID</span><span class="sxs-lookup"><span data-stu-id="18c98-396">securityGroupId</span></span> | <span data-ttu-id="18c98-397">エンティティの種類が  *セキュリティ グループ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="18c98-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="18c98-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="18c98-399">グループ名をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="18c98-399">securityGroupName</span></span> | <span data-ttu-id="18c98-400">エンティティの種類が  *セキュリティ グループ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="18c98-401">ネットワーク構成オペレーター</span><span class="sxs-lookup"><span data-stu-id="18c98-401">Network Configuration Operators</span></span>
<span data-ttu-id="18c98-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="18c98-402">registryHive</span></span> | <span data-ttu-id="18c98-403">entityType が  *レジストリ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="18c98-404">HKEY \_ ローカル \_ マシン</span><span class="sxs-lookup"><span data-stu-id="18c98-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="18c98-405">レジストリキー</span><span class="sxs-lookup"><span data-stu-id="18c98-405">registryKey</span></span> | <span data-ttu-id="18c98-406">entityType が  *レジストリ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="18c98-407">ソフトウェア\マイクロソフト\Windows NT\現在のバージョン\ウィンログオン</span><span class="sxs-lookup"><span data-stu-id="18c98-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="18c98-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="18c98-408">registryValueType</span></span> | <span data-ttu-id="18c98-409">entityType が  *レジストリ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="18c98-410">String</span><span class="sxs-lookup"><span data-stu-id="18c98-410">String</span></span>
<span data-ttu-id="18c98-411">レジストリ値</span><span class="sxs-lookup"><span data-stu-id="18c98-411">registryValue</span></span> | <span data-ttu-id="18c98-412">entityType が  *レジストリ* の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="18c98-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="18c98-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="18c98-413">31-00-00-00</span></span>
<span data-ttu-id="18c98-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="18c98-414">deviceId</span></span> | <span data-ttu-id="18c98-415">エンティティに関連付けられているデバイスの ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="18c98-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="18c98-416">986e5df8b73dac43c8917d17e523376b13c75cd</span><span class="sxs-lookup"><span data-stu-id="18c98-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="18c98-417">例</span><span class="sxs-lookup"><span data-stu-id="18c98-417">Example</span></span>

<span data-ttu-id="18c98-418">**要求**</span><span class="sxs-lookup"><span data-stu-id="18c98-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="18c98-419">**応答**</span><span class="sxs-lookup"><span data-stu-id="18c98-419">**Response**</span></span>

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
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
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
            "comments": [],
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
            "comments": [],
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

## <a name="related-articles"></a><span data-ttu-id="18c98-420">関連記事</span><span class="sxs-lookup"><span data-stu-id="18c98-420">Related articles</span></span>

- [<span data-ttu-id="18c98-421">Microsoft 365ディフェンダー API へのアクセス</span><span class="sxs-lookup"><span data-stu-id="18c98-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="18c98-422">API の制限とライセンスについて</span><span class="sxs-lookup"><span data-stu-id="18c98-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="18c98-423">エラー コードを理解する</span><span class="sxs-lookup"><span data-stu-id="18c98-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="18c98-424">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="18c98-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="18c98-425">インシデント API</span><span class="sxs-lookup"><span data-stu-id="18c98-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="18c98-426">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="18c98-426">Update incident API</span></span>](api-update-incidents.md)
