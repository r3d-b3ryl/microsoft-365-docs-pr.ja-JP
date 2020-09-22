---
title: Microsoft Threat Protection のインシデント API を一覧表示する
description: Microsoft の脅威保護でインシデント API を一覧表示する方法について説明します。
keywords: リスト、インシデント、インシデント、api
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195390"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="170f8-104">Microsoft Threat Protection のインシデント API を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="170f8-104">List incidents API in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="170f8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="170f8-105">**Applies to:**</span></span>

- <span data-ttu-id="170f8-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="170f8-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="170f8-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="170f8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="170f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="170f8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="170f8-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="170f8-109">API description</span></span>

<span data-ttu-id="170f8-110">インシデント API を使用すると、インシデントを優先して優先度を設定し、通知された cybersecurity 応答を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="170f8-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="170f8-111">これにより、環境のアイテム保持ポリシーで指定した時間の範囲内で、ネットワーク内のデバイス、電子メールアカウント、ユーザーのフラグが付けられたインシデントのコレクションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="170f8-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="170f8-112">最新のインシデントは、リストの一番上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="170f8-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="170f8-113">各インシデントには、関連する通知の配列と、関連するエンティティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="170f8-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="170f8-114">この API は、次の **OData** 演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="170f8-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="170f8-115">```$filter``` on: ```lastUpdateTime``` 、 ```createdTime``` 、 ```status``` および ```assignedTo``` プロパティ。</span><span class="sxs-lookup"><span data-stu-id="170f8-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="170f8-116">```$top``` 最大値 **100**</span><span class="sxs-lookup"><span data-stu-id="170f8-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="170f8-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="170f8-117">Limitations</span></span>

1. <span data-ttu-id="170f8-118">最大ページサイズは **100 インシデント**です。</span><span class="sxs-lookup"><span data-stu-id="170f8-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="170f8-119">要求の最大速度は、1 **分あたり50通話** 、1 **時間あたり1500通話**です。</span><span class="sxs-lookup"><span data-stu-id="170f8-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="170f8-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="170f8-120">Permissions</span></span>

<span data-ttu-id="170f8-121">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="170f8-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="170f8-122">アクセス許可の選択方法を含む詳細については、「 [Microsoft の脅威保護 api にアクセス](api-access.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="170f8-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="170f8-123">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="170f8-123">Permission type</span></span> |   <span data-ttu-id="170f8-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="170f8-124">Permission</span></span>  |   <span data-ttu-id="170f8-125">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="170f8-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="170f8-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="170f8-126">Application</span></span> |   <span data-ttu-id="170f8-127">インシデント。すべてを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="170f8-127">Incident.Read.All</span></span> | <span data-ttu-id="170f8-128">' すべてのインシデントの読み取り '</span><span class="sxs-lookup"><span data-stu-id="170f8-128">'Read all incidents'</span></span>
<span data-ttu-id="170f8-129">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="170f8-129">Application</span></span> |   <span data-ttu-id="170f8-130">インシデント。すべて</span><span class="sxs-lookup"><span data-stu-id="170f8-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="170f8-131">' すべてのインシデントの読み取りと書き込み '</span><span class="sxs-lookup"><span data-stu-id="170f8-131">'Read and write all incidents'</span></span>
<span data-ttu-id="170f8-132">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="170f8-132">Delegated (work or school account)</span></span> | <span data-ttu-id="170f8-133">インシデント。読み取り</span><span class="sxs-lookup"><span data-stu-id="170f8-133">Incident.Read</span></span> | <span data-ttu-id="170f8-134">' 読み取りインシデント '</span><span class="sxs-lookup"><span data-stu-id="170f8-134">'Read incidents'</span></span>
<span data-ttu-id="170f8-135">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="170f8-135">Delegated (work or school account)</span></span> | <span data-ttu-id="170f8-136">障害/書き込み</span><span class="sxs-lookup"><span data-stu-id="170f8-136">Incident.ReadWrite</span></span> | <span data-ttu-id="170f8-137">' 読み取りおよび書き込みのインシデント '</span><span class="sxs-lookup"><span data-stu-id="170f8-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="170f8-138">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="170f8-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="170f8-139">ユーザーはポータルのインシデントに対する表示権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="170f8-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="170f8-140">応答には、ユーザーが公開されているインシデントのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="170f8-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="170f8-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="170f8-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="170f8-142">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="170f8-142">Request headers</span></span>

<span data-ttu-id="170f8-143">名前</span><span class="sxs-lookup"><span data-stu-id="170f8-143">Name</span></span> | <span data-ttu-id="170f8-144">種類</span><span class="sxs-lookup"><span data-stu-id="170f8-144">Type</span></span> | <span data-ttu-id="170f8-145">説明</span><span class="sxs-lookup"><span data-stu-id="170f8-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="170f8-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="170f8-146">Authorization</span></span> | <span data-ttu-id="170f8-147">String</span><span class="sxs-lookup"><span data-stu-id="170f8-147">String</span></span> | <span data-ttu-id="170f8-148">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="170f8-148">Bearer {token}.</span></span> <span data-ttu-id="170f8-149">**必須**。</span><span class="sxs-lookup"><span data-stu-id="170f8-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="170f8-150">要求本文</span><span class="sxs-lookup"><span data-stu-id="170f8-150">Request body</span></span>
<span data-ttu-id="170f8-151">なし。</span><span class="sxs-lookup"><span data-stu-id="170f8-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="170f8-152">応答</span><span class="sxs-lookup"><span data-stu-id="170f8-152">Response</span></span>
<span data-ttu-id="170f8-153">成功した場合、このメソッドは 200 OK と、応答本文で [インシデント](api-incident.md) の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="170f8-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="170f8-154">スキーママッピング</span><span class="sxs-lookup"><span data-stu-id="170f8-154">Schema mapping</span></span>

| <span data-ttu-id="170f8-155">フィールド名</span><span class="sxs-lookup"><span data-stu-id="170f8-155">Field name</span></span>                                | <span data-ttu-id="170f8-156">説明</span><span class="sxs-lookup"><span data-stu-id="170f8-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-157">値の例</span><span class="sxs-lookup"><span data-stu-id="170f8-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="170f8-158">**インシデントのメタデータ**</span><span class="sxs-lookup"><span data-stu-id="170f8-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="170f8-159">インシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="170f8-159">incidentId</span></span>                                | <span data-ttu-id="170f8-160">インシデントを表す一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="170f8-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-161">924565</span><span class="sxs-lookup"><span data-stu-id="170f8-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-162">Redirectインシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="170f8-162">redirectIncidentId</span></span>                        | <span data-ttu-id="170f8-163">インシデントが別のインシデントと一緒にグループ化されている場合にのみ、インシデント処理ロジックの一部として設定されます。</span><span class="sxs-lookup"><span data-stu-id="170f8-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="170f8-164">924569</span><span class="sxs-lookup"><span data-stu-id="170f8-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="170f8-165">incidentName</span></span>                              | <span data-ttu-id="170f8-166">すべてのインシデントで利用可能な文字列値。</span><span class="sxs-lookup"><span data-stu-id="170f8-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="170f8-167">ランサムウェアアクティビティ</span><span class="sxs-lookup"><span data-stu-id="170f8-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="170f8-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="170f8-168">createdTime</span></span>                               | <span data-ttu-id="170f8-169">インシデントが最初に作成された日時。</span><span class="sxs-lookup"><span data-stu-id="170f8-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="170f8-170">2020-09-06T14:46: 57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="170f8-171">lastUpdateTime</span></span>                            | <span data-ttu-id="170f8-172">インシデントがバックエンドで最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="170f8-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="170f8-173">このフィールドは、インシデントを取得する時間の範囲の request パラメータを設定するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="170f8-174">2020-09-06T14:46: 57.29 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="170f8-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="170f8-175">assignedTo</span></span>                                | <span data-ttu-id="170f8-176">インシデントの所有者。所有者が割り当てられていない場合は、 *null* 。</span><span class="sxs-lookup"><span data-stu-id="170f8-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="170f8-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="170f8-178">classification</span><span class="sxs-lookup"><span data-stu-id="170f8-178">classification</span></span>                            | <span data-ttu-id="170f8-179">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="170f8-179">The specification for the incident.</span></span> <span data-ttu-id="170f8-180">プロパティの値は次のとおりです。 *Unknown*、 *false 陽性*、 *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="170f8-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="170f8-181">不明</span><span class="sxs-lookup"><span data-stu-id="170f8-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="170f8-182">決定</span><span class="sxs-lookup"><span data-stu-id="170f8-182">determination</span></span>                             | <span data-ttu-id="170f8-183">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="170f8-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="170f8-184">プロパティの値は次のとおりです。 *Notavailable*、 *Apt*、 *マルウェア*、 *securitypersonnel*、 *securitypersonnel*、 *UnwantedSoftware*、 *Other*</span><span class="sxs-lookup"><span data-stu-id="170f8-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="170f8-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="170f8-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-186">status</span><span class="sxs-lookup"><span data-stu-id="170f8-186">status</span></span>                                    | <span data-ttu-id="170f8-187">インシデント ( *アクティブ*または *解決済み*) を分類します。</span><span class="sxs-lookup"><span data-stu-id="170f8-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="170f8-188">これにより、インシデントへの対応を整理し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="170f8-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="170f8-189">Active</span><span class="sxs-lookup"><span data-stu-id="170f8-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-190">severity</span><span class="sxs-lookup"><span data-stu-id="170f8-190">severity</span></span>                                  | <span data-ttu-id="170f8-191">アセットに影響を与える可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="170f8-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="170f8-192">重要度が高いほど、影響が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="170f8-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="170f8-193">通常、重要度が高いアイテムは、即時注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="170f8-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="170f8-194">次のいずれかの値: [ *情報*]、[ *低*]、[中]、[ *高*]。</span><span class="sxs-lookup"><span data-stu-id="170f8-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="170f8-195">中</span><span class="sxs-lookup"><span data-stu-id="170f8-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-196">tags</span><span class="sxs-lookup"><span data-stu-id="170f8-196">tags</span></span>                                      | <span data-ttu-id="170f8-197">インシデントに関連付けられているカスタムタグの配列です。たとえば、共通の特性を使用して、インシデントのグループにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="170f8-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-198">アラート</span><span class="sxs-lookup"><span data-stu-id="170f8-198">alerts</span></span>                                    | <span data-ttu-id="170f8-199">インシデントに関連付けられているすべての警告とその他の情報 (重要度、警告に関係していたエンティティ、アラートのソースなど) の配列。</span><span class="sxs-lookup"><span data-stu-id="170f8-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="170f8-200">\[\] (下の警告フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="170f8-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="170f8-201">**通知のメタデータ**</span><span class="sxs-lookup"><span data-stu-id="170f8-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="170f8-202">alertId</span><span class="sxs-lookup"><span data-stu-id="170f8-202">alertId</span></span>                                   | <span data-ttu-id="170f8-203">通知を表す一意識別子</span><span class="sxs-lookup"><span data-stu-id="170f8-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="170f8-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-205">インシデント識別子 d</span><span class="sxs-lookup"><span data-stu-id="170f8-205">incidentId</span></span>                                | <span data-ttu-id="170f8-206">このアラートが関連付けられているインシデントを表す一意識別子</span><span class="sxs-lookup"><span data-stu-id="170f8-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="170f8-207">924565</span><span class="sxs-lookup"><span data-stu-id="170f8-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-208">サービス Ource</span><span class="sxs-lookup"><span data-stu-id="170f8-208">serviceSource</span></span>                             | <span data-ttu-id="170f8-209">Microsoft Defender ATP、Microsoft Cloud App Security、Azure ATP、Office 365 ATP などの通知の発生元であるサービス。</span><span class="sxs-lookup"><span data-stu-id="170f8-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-210">Microsoft Cloudappsecurity</span><span class="sxs-lookup"><span data-stu-id="170f8-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="170f8-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="170f8-211">creationTime</span></span>                              | <span data-ttu-id="170f8-212">通知が最初に作成された日時。</span><span class="sxs-lookup"><span data-stu-id="170f8-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="170f8-213">2020-09-06T14:46: 55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-214">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="170f8-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="170f8-215">バックエンドで通知が最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="170f8-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="170f8-216">2020-09-06T14:46: 57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-217">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="170f8-217">resolvedTime</span></span>                              | <span data-ttu-id="170f8-218">通知が解決された時刻。</span><span class="sxs-lookup"><span data-stu-id="170f8-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="170f8-219">2020-09-10T05:22: 59Z</span><span class="sxs-lookup"><span data-stu-id="170f8-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="170f8-220">firstActivity</span></span>                             | <span data-ttu-id="170f8-221">警告が最初にアクティビティが更新されたことを報告した日時です。</span><span class="sxs-lookup"><span data-stu-id="170f8-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="170f8-222">2020-09-04T05:22: 59Z</span><span class="sxs-lookup"><span data-stu-id="170f8-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-223">title</span><span class="sxs-lookup"><span data-stu-id="170f8-223">title</span></span>                                     | <span data-ttu-id="170f8-224">各警告で使用可能な短い識別文字列値。</span><span class="sxs-lookup"><span data-stu-id="170f8-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-225">ランサムウェアアクティビティ</span><span class="sxs-lookup"><span data-stu-id="170f8-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="170f8-226">description</span><span class="sxs-lookup"><span data-stu-id="170f8-226">description</span></span>                               | <span data-ttu-id="170f8-227">各警告を説明する文字列値。</span><span class="sxs-lookup"><span data-stu-id="170f8-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-228">ユーザーテスト User2 (testUser2@contoso.com) は、複数の拡張子を持つ99ファイルを、一般的でない拡張子 *herunterladen*で終了するように操作します。</span><span class="sxs-lookup"><span data-stu-id="170f8-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="170f8-229">これは、通常のファイル操作の数で、ランサムウェアによる可能性のある攻撃を示しています。</span><span class="sxs-lookup"><span data-stu-id="170f8-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="170f8-230">category</span><span class="sxs-lookup"><span data-stu-id="170f8-230">category</span></span>                                  | <span data-ttu-id="170f8-231">キルチェーンに沿った攻撃の進行状況を示す視覚的および数値のビュー。</span><span class="sxs-lookup"><span data-stu-id="170f8-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="170f8-232">[MITRE ATT&の™ framework](https://attack.mitre.org/)に配置されます。</span><span class="sxs-lookup"><span data-stu-id="170f8-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="170f8-233">影響</span><span class="sxs-lookup"><span data-stu-id="170f8-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-234">status</span><span class="sxs-lookup"><span data-stu-id="170f8-234">status</span></span>                                    | <span data-ttu-id="170f8-235">通知を分類します ( *新規*、 *アクティブ*、または *解決済み*)。</span><span class="sxs-lookup"><span data-stu-id="170f8-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="170f8-236">これにより、アラートへの対応を整理し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="170f8-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-237">新規</span><span class="sxs-lookup"><span data-stu-id="170f8-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="170f8-238">severity</span><span class="sxs-lookup"><span data-stu-id="170f8-238">severity</span></span>                                  | <span data-ttu-id="170f8-239">アセットに影響を与える可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="170f8-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="170f8-240">重要度が高いほど、影響が大きくなります。</span><span class="sxs-lookup"><span data-stu-id="170f8-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="170f8-241">通常、重要度が高いアイテムは、即時注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="170f8-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="170f8-242">次のいずれかの値: [ *情報*]、[ *低*]、[中]、[ *高*]。</span><span class="sxs-lookup"><span data-stu-id="170f8-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="170f8-243">中</span><span class="sxs-lookup"><span data-stu-id="170f8-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-244">investigationId</span><span class="sxs-lookup"><span data-stu-id="170f8-244">investigationId</span></span>                           | <span data-ttu-id="170f8-245">このアラートによってトリガーされた自動調査 id。</span><span class="sxs-lookup"><span data-stu-id="170f8-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-246">1234</span><span class="sxs-lookup"><span data-stu-id="170f8-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-247">investigationState</span><span class="sxs-lookup"><span data-stu-id="170f8-247">investigationState</span></span>                        | <span data-ttu-id="170f8-248">調査の現在の状態に関する情報。</span><span class="sxs-lookup"><span data-stu-id="170f8-248">Information on the investigation's current status.</span></span> <span data-ttu-id="170f8-249">*Unknown*、*終わら*れた*修復*済み、*無害*、 *Failed*、 *PartiallyRemediated*、 *Running*、 *pendingapproval*、 *pendingapproval*、 *PartiallyInvestigated*、 *TerminatedByUser*、 *TerminatedBySystem*、 *Queued*、 *innerfailure*、 *preexistingalert*、 *UnsupportedOs*、 *presupportedalerttype*、 *SuppressedAlert*のいずれか。</span><span class="sxs-lookup"><span data-stu-id="170f8-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="170f8-250">アン Supportedalerttype</span><span class="sxs-lookup"><span data-stu-id="170f8-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-251">classification</span><span class="sxs-lookup"><span data-stu-id="170f8-251">classification</span></span>                            | <span data-ttu-id="170f8-252">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="170f8-252">The specification for the incident.</span></span> <span data-ttu-id="170f8-253">プロパティの値は次のとおりです。 *Unknown*、 *false 陽性*、 *TruePositive* 、または *null*</span><span class="sxs-lookup"><span data-stu-id="170f8-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-254">不明</span><span class="sxs-lookup"><span data-stu-id="170f8-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="170f8-255">決定</span><span class="sxs-lookup"><span data-stu-id="170f8-255">determination</span></span>                             | <span data-ttu-id="170f8-256">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="170f8-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="170f8-257">プロパティの値は次のとおりです。 *Notavailable*、 *Apt*、 *マルウェア*、 *securitypersonnel*、 *securitypersonnel*、 *UnwantedSoftware*、 *Other* 、または  *null*</span><span class="sxs-lookup"><span data-stu-id="170f8-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="170f8-258">Excel</span><span class="sxs-lookup"><span data-stu-id="170f8-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="170f8-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="170f8-259">assignedTo</span></span>                                | <span data-ttu-id="170f8-260">インシデントの所有者。所有者が割り当てられていない場合は、 *null* 。</span><span class="sxs-lookup"><span data-stu-id="170f8-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="170f8-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="170f8-262">actorName</span><span class="sxs-lookup"><span data-stu-id="170f8-262">actorName</span></span>                                 | <span data-ttu-id="170f8-263">このアラートに関連付けられているアクティビティグループ (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="170f8-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-264">BORON</span><span class="sxs-lookup"><span data-stu-id="170f8-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="170f8-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="170f8-265">threatFamilyName</span></span>                          | <span data-ttu-id="170f8-266">このアラートに関連付けられている脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="170f8-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-267">null</span><span class="sxs-lookup"><span data-stu-id="170f8-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="170f8-268">mitreTechniques</span></span>                           | <span data-ttu-id="170f8-269">[MITRE ATT&](https://attack.mitre.org/)の™ framework に沿った攻撃手法。</span><span class="sxs-lookup"><span data-stu-id="170f8-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-270">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="170f8-270">devices</span></span>                                   | <span data-ttu-id="170f8-271">インシデントに関連するアラートが送信されたすべてのデバイス。</span><span class="sxs-lookup"><span data-stu-id="170f8-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-272">\[\] (以下のエンティティフィールドの詳細を参照)</span><span class="sxs-lookup"><span data-stu-id="170f8-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="170f8-273">**デバイス形式**</span><span class="sxs-lookup"><span data-stu-id="170f8-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="170f8-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="170f8-274">DeviceId</span></span>                                  | <span data-ttu-id="170f8-275">Microsoft Defender ATP で指定されているデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="170f8-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="170f8-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="170f8-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="170f8-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="170f8-277">aadDeviceId</span></span>                               |  <span data-ttu-id="170f8-278">[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD) で指定されているデバイス Id。</span><span class="sxs-lookup"><span data-stu-id="170f8-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="170f8-279">ドメインに参加しているデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="170f8-280">null</span><span class="sxs-lookup"><span data-stu-id="170f8-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="170f8-281">deviceDnsName</span></span>                             | <span data-ttu-id="170f8-282">デバイスの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="170f8-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="170f8-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="170f8-284">osPlatform</span></span>                                | <span data-ttu-id="170f8-285">デバイスが実行されている OS プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="170f8-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="170f8-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="170f8-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="170f8-287">osBuild</span></span>                                   | <span data-ttu-id="170f8-288">デバイスが実行している OS のビルドバージョン。</span><span class="sxs-lookup"><span data-stu-id="170f8-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-289">14393</span><span class="sxs-lookup"><span data-stu-id="170f8-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="170f8-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="170f8-290">rbacGroupName</span></span>                             | <span data-ttu-id="170f8-291">デバイスに関連付けられている [役割ベースのアクセス制御](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="170f8-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="170f8-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="170f8-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="170f8-293">最初の表示</span><span class="sxs-lookup"><span data-stu-id="170f8-293">firstSeen</span></span>                                 | <span data-ttu-id="170f8-294">デバイスが最初に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="170f8-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="170f8-295">2020-02-06T14:16: 01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="170f8-296">healthStatus</span></span>                              | <span data-ttu-id="170f8-297">デバイスの正常性の状態。</span><span class="sxs-lookup"><span data-stu-id="170f8-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-298">Active</span><span class="sxs-lookup"><span data-stu-id="170f8-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="170f8-299">riskScore</span></span>                                 | <span data-ttu-id="170f8-300">デバイスのリスクスコア。</span><span class="sxs-lookup"><span data-stu-id="170f8-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="170f8-301">高</span><span class="sxs-lookup"><span data-stu-id="170f8-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-302">法人</span><span class="sxs-lookup"><span data-stu-id="170f8-302">entities</span></span>                                  | <span data-ttu-id="170f8-303">特定のアラートに含まれている、またはそれに関連付けられているすべてのエンティティ。</span><span class="sxs-lookup"><span data-stu-id="170f8-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-304">\[\] (以下のエンティティフィールドの詳細を参照)</span><span class="sxs-lookup"><span data-stu-id="170f8-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="170f8-305">**エンティティ形式**</span><span class="sxs-lookup"><span data-stu-id="170f8-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="170f8-306">entityType</span><span class="sxs-lookup"><span data-stu-id="170f8-306">entityType</span></span>                                | <span data-ttu-id="170f8-307">特定の警告に含まれている、または関連するエンティティ。</span><span class="sxs-lookup"><span data-stu-id="170f8-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="170f8-308">プロパティの値は次のとおりです。 *ユーザー*、 *Ip*、 *Url*、 *ファイル*、 *プロセス*、 *メールボックス*、 *MailMessage*、 *mailcluster*、 *Registry*</span><span class="sxs-lookup"><span data-stu-id="170f8-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="170f8-309">ユーザー</span><span class="sxs-lookup"><span data-stu-id="170f8-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-310">sha1</span><span class="sxs-lookup"><span data-stu-id="170f8-310">sha1</span></span>                                      | <span data-ttu-id="170f8-311">EntityType が *File*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="170f8-312">ファイルまたはプロセスに関連付けられた通知のファイルハッシュ。</span><span class="sxs-lookup"><span data-stu-id="170f8-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="170f8-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="170f8-314">sha256</span><span class="sxs-lookup"><span data-stu-id="170f8-314">sha256</span></span>                                    | <span data-ttu-id="170f8-315">EntityType が *File*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="170f8-316">ファイルまたはプロセスに関連付けられた通知のファイルハッシュ。</span><span class="sxs-lookup"><span data-stu-id="170f8-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="170f8-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="170f8-318">fileName</span><span class="sxs-lookup"><span data-stu-id="170f8-318">fileName</span></span>                                  | <span data-ttu-id="170f8-319">EntityType が *File*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="170f8-320">ファイルまたはプロセスに関連付けられた通知のファイル名</span><span class="sxs-lookup"><span data-stu-id="170f8-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="170f8-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-322">パス</span><span class="sxs-lookup"><span data-stu-id="170f8-322">filePath</span></span>                                  | <span data-ttu-id="170f8-323">EntityType が *File*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="170f8-324">ファイルまたはプロセスに関連付けられた通知のファイルパス</span><span class="sxs-lookup"><span data-stu-id="170f8-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-325">C: \\ \\ エージェント \\ \\ \_ 作業 \\ \\ \_ 温度 \\ \\ 展開 \_ システム 2020-09-06 12 \_ 14 \_ 54 \\ \\ アウト</span><span class="sxs-lookup"><span data-stu-id="170f8-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="170f8-326">processId</span><span class="sxs-lookup"><span data-stu-id="170f8-326">processId</span></span>                                 | <span data-ttu-id="170f8-327">EntityType が *Process*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-328">24348</span><span class="sxs-lookup"><span data-stu-id="170f8-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="170f8-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="170f8-329">processCommandLine</span></span>                        | <span data-ttu-id="170f8-330">EntityType が *Process*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-331">" \\ " ファイルをダウンロードする準備ができました \_1911150169.exe\\ "</span><span class="sxs-lookup"><span data-stu-id="170f8-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="170f8-332">Process/時間</span><span class="sxs-lookup"><span data-stu-id="170f8-332">processCreationTime</span></span>                       | <span data-ttu-id="170f8-333">EntityType が *Process*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-334">2020-07-18T03:25: 38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="170f8-335">parentProcessId</span></span>                           | <span data-ttu-id="170f8-336">EntityType が *Process*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-337">16840</span><span class="sxs-lookup"><span data-stu-id="170f8-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="170f8-338">Parentprocess/時間</span><span class="sxs-lookup"><span data-stu-id="170f8-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="170f8-339">EntityType が *Process*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-340">2020-07-18T02:12: 32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="170f8-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="170f8-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="170f8-341">ipAddress</span></span>                                 | <span data-ttu-id="170f8-342">EntityType が *Ip*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="170f8-343">*悪意のあるネットワークの宛先への通信*など、ネットワークイベントに関連付けられた通知の IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="170f8-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="170f8-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="170f8-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="170f8-345">url</span><span class="sxs-lookup"><span data-stu-id="170f8-345">url</span></span>                                       | <span data-ttu-id="170f8-346">EntityType が *Url*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="170f8-347">ネットワークイベント ( *悪意のあるネットワークの宛先への通信*など) に関連付けられた通知の Url。</span><span class="sxs-lookup"><span data-stu-id="170f8-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="170f8-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="170f8-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="170f8-349">アカウント</span><span class="sxs-lookup"><span data-stu-id="170f8-349">accountName</span></span>                               | <span data-ttu-id="170f8-350">EntityType が *User*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="170f8-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="170f8-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="170f8-352">domainName</span><span class="sxs-lookup"><span data-stu-id="170f8-352">domainName</span></span>                                | <span data-ttu-id="170f8-353">EntityType が *User*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-354">欧州. contoso</span><span class="sxs-lookup"><span data-stu-id="170f8-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-355">userSid</span><span class="sxs-lookup"><span data-stu-id="170f8-355">userSid</span></span>                                   | <span data-ttu-id="170f8-356">EntityType が *User*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="170f8-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="170f8-358">Usersecuritystate</span><span class="sxs-lookup"><span data-stu-id="170f8-358">aadUserId</span></span>                                 | <span data-ttu-id="170f8-359">EntityType が *User*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="170f8-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="170f8-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="170f8-361">userPrincipalName</span></span>                         | <span data-ttu-id="170f8-362">EntityType がユーザーの*User* / *メールボックス*MailMessage の場合に使用でき / *MailMessage*ます。</span><span class="sxs-lookup"><span data-stu-id="170f8-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="170f8-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="170f8-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="170f8-365">EntityType が *MailBox*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-366">User2 のテスト</span><span class="sxs-lookup"><span data-stu-id="170f8-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="170f8-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="170f8-367">mailboxAddress</span></span>                            | <span data-ttu-id="170f8-368">EntityType がユーザーの*User* / *メールボックス*MailMessage の場合に使用でき / *MailMessage*ます。</span><span class="sxs-lookup"><span data-stu-id="170f8-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="170f8-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="170f8-370">clusterBy</span></span>                                 | <span data-ttu-id="170f8-371">EntityType が  *Mailcluster*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="170f8-372">対象P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="170f8-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="170f8-373">sender</span><span class="sxs-lookup"><span data-stu-id="170f8-373">sender</span></span>                                    | <span data-ttu-id="170f8-374">EntityType がユーザーの*User* / *メールボックス*MailMessage の場合に使用でき / *MailMessage*ます。</span><span class="sxs-lookup"><span data-stu-id="170f8-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="170f8-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="170f8-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="170f8-376">受信者</span><span class="sxs-lookup"><span data-stu-id="170f8-376">recipient</span></span>                                 | <span data-ttu-id="170f8-377">EntityType が *MailMessage*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="170f8-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="170f8-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="170f8-379">subject</span><span class="sxs-lookup"><span data-stu-id="170f8-379">subject</span></span>                                   | <span data-ttu-id="170f8-380">EntityType が *MailMessage*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="170f8-381">\[外部 \] 注目</span><span class="sxs-lookup"><span data-stu-id="170f8-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-382">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="170f8-382">deliveryAction</span></span>                            | <span data-ttu-id="170f8-383">EntityType が *MailMessage*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="170f8-384">届け</span><span class="sxs-lookup"><span data-stu-id="170f8-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="170f8-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="170f8-385">securityGroupId</span></span>                           | <span data-ttu-id="170f8-386">EntityType が  *microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="170f8-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="170f8-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="170f8-388">securityGroupName</span></span>                         | <span data-ttu-id="170f8-389">EntityType が  *microsoft.rtc.management.writableconfig.settings.centralizedlogging.securitygroup*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="170f8-390">ネットワーク構成演算子</span><span class="sxs-lookup"><span data-stu-id="170f8-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="170f8-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="170f8-391">registryHive</span></span>                              | <span data-ttu-id="170f8-392">EntityType が  *レジストリ*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-393">HKEY \_ ローカル \_ コンピューター</span><span class="sxs-lookup"><span data-stu-id="170f8-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="170f8-394">Rename</span><span class="sxs-lookup"><span data-stu-id="170f8-394">registryKey</span></span>                               | <span data-ttu-id="170f8-395">EntityType が  *レジストリ*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="170f8-396">ソフトウェア \\ \\ MICROSOFT \\ \\ Windows NT \\ \\ currentversion: \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="170f8-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="170f8-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="170f8-397">registryValueType</span></span>                         | <span data-ttu-id="170f8-398">EntityType が  *レジストリ*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-399">String</span><span class="sxs-lookup"><span data-stu-id="170f8-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="170f8-400">registryValue</span><span class="sxs-lookup"><span data-stu-id="170f8-400">registryValue</span></span>                             | <span data-ttu-id="170f8-401">EntityType が  *レジストリ*の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="170f8-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="170f8-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="170f8-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="170f8-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="170f8-403">deviceId</span></span>                                  | <span data-ttu-id="170f8-404">エンティティに関連付けられているデバイスの ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="170f8-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="170f8-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="170f8-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="170f8-406">例</span><span class="sxs-lookup"><span data-stu-id="170f8-406">Example</span></span>

<span data-ttu-id="170f8-407">**要求**</span><span class="sxs-lookup"><span data-stu-id="170f8-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="170f8-408">**応答**</span><span class="sxs-lookup"><span data-stu-id="170f8-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="170f8-409">関連トピック</span><span class="sxs-lookup"><span data-stu-id="170f8-409">Related topic</span></span>
- [<span data-ttu-id="170f8-410">インシデント API</span><span class="sxs-lookup"><span data-stu-id="170f8-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="170f8-411">インシデントを更新する</span><span class="sxs-lookup"><span data-stu-id="170f8-411">Update incident</span></span>](api-update-incidents.md)
