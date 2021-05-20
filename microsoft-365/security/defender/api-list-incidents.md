---
title: Defender でインシデント API をMicrosoft 365する
description: Defender でインシデント API を一覧表示するMicrosoft 365する
keywords: リスト, インシデント, インシデント, API
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
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="65465-104">Defender でインシデント API をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="65465-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65465-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="65465-105">**Applies to:**</span></span>

- <span data-ttu-id="65465-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65465-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65465-107">一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。</span><span class="sxs-lookup"><span data-stu-id="65465-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="65465-108">Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="65465-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="65465-109">API の説明</span><span class="sxs-lookup"><span data-stu-id="65465-109">API description</span></span>

<span data-ttu-id="65465-110">リスト インシデント API を使用すると、インシデントを並べ替え、情報に基づいたサイバーセキュリティ対応を作成できます。</span><span class="sxs-lookup"><span data-stu-id="65465-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="65465-111">環境保持ポリシーで指定した時間範囲内で、ネットワークでフラグが設定されたインシデントのコレクションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="65465-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="65465-112">最新のインシデントがリストの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="65465-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="65465-113">各インシデントには、関連するアラートとその関連エンティティの配列が含まれる。</span><span class="sxs-lookup"><span data-stu-id="65465-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="65465-114">API では、次の **OData 演算子がサポート** されています。</span><span class="sxs-lookup"><span data-stu-id="65465-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="65465-115">`$filter` on `lastUpdateTime` the `createdTime` , , and `status` `assignedTo` properties</span><span class="sxs-lookup"><span data-stu-id="65465-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="65465-116">`$top`で、最大値 **は 100 です。**</span><span class="sxs-lookup"><span data-stu-id="65465-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="65465-117">制限事項</span><span class="sxs-lookup"><span data-stu-id="65465-117">Limitations</span></span>

1. <span data-ttu-id="65465-118">最大ページ サイズは **100 インシデントです**。</span><span class="sxs-lookup"><span data-stu-id="65465-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="65465-119">要求の最大レートは **、1 分あたり 50 通話\*\*\*\*、1 時間あたり 1500 通話です**。</span><span class="sxs-lookup"><span data-stu-id="65465-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="65465-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="65465-120">Permissions</span></span>

<span data-ttu-id="65465-121">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="65465-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="65465-122">アクセス許可の選択方法などの詳細については、「Access Microsoft 365 [Defender API」を参照してください。](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="65465-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="65465-123">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="65465-123">Permission type</span></span> | <span data-ttu-id="65465-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="65465-124">Permission</span></span> | <span data-ttu-id="65465-125">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="65465-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="65465-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="65465-126">Application</span></span> | <span data-ttu-id="65465-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="65465-127">Incident.Read.All</span></span> | <span data-ttu-id="65465-128">すべてのインシデントを読み取る</span><span class="sxs-lookup"><span data-stu-id="65465-128">Read all incidents</span></span>
<span data-ttu-id="65465-129">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="65465-129">Application</span></span> | <span data-ttu-id="65465-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="65465-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="65465-131">すべてのインシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="65465-131">Read and write all incidents</span></span>
<span data-ttu-id="65465-132">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="65465-132">Delegated (work or school account)</span></span> | <span data-ttu-id="65465-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="65465-133">Incident.Read</span></span> | <span data-ttu-id="65465-134">インシデントの読み取り</span><span class="sxs-lookup"><span data-stu-id="65465-134">Read incidents</span></span>
<span data-ttu-id="65465-135">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="65465-135">Delegated (work or school account)</span></span> | <span data-ttu-id="65465-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="65465-136">Incident.ReadWrite</span></span> | <span data-ttu-id="65465-137">インシデントの読み取りおよび書き込み</span><span class="sxs-lookup"><span data-stu-id="65465-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="65465-138">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="65465-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="65465-139">ユーザーは、ポータルでインシデントの表示アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65465-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="65465-140">応答には、ユーザーが公開されているインシデントだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="65465-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="65465-141">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="65465-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="65465-142">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="65465-142">Request headers</span></span>

<span data-ttu-id="65465-143">名前</span><span class="sxs-lookup"><span data-stu-id="65465-143">Name</span></span> | <span data-ttu-id="65465-144">型</span><span class="sxs-lookup"><span data-stu-id="65465-144">Type</span></span> | <span data-ttu-id="65465-145">説明</span><span class="sxs-lookup"><span data-stu-id="65465-145">Description</span></span>
-|-|-
<span data-ttu-id="65465-146">Authorization</span><span class="sxs-lookup"><span data-stu-id="65465-146">Authorization</span></span> | <span data-ttu-id="65465-147">String</span><span class="sxs-lookup"><span data-stu-id="65465-147">String</span></span> | <span data-ttu-id="65465-148">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="65465-148">Bearer {token}.</span></span> <span data-ttu-id="65465-149">**必須**</span><span class="sxs-lookup"><span data-stu-id="65465-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="65465-150">要求本文</span><span class="sxs-lookup"><span data-stu-id="65465-150">Request body</span></span>

<span data-ttu-id="65465-151">なし。</span><span class="sxs-lookup"><span data-stu-id="65465-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="65465-152">応答</span><span class="sxs-lookup"><span data-stu-id="65465-152">Response</span></span>

<span data-ttu-id="65465-153">成功した場合、このメソッドは `200 OK` 応答本文のインシデントの一 [覧](api-incident.md) を返します。</span><span class="sxs-lookup"><span data-stu-id="65465-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="65465-154">スキーマ マッピング</span><span class="sxs-lookup"><span data-stu-id="65465-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="65465-155">インシデント メタデータ</span><span class="sxs-lookup"><span data-stu-id="65465-155">Incident metadata</span></span>

<span data-ttu-id="65465-156">フィールド名</span><span class="sxs-lookup"><span data-stu-id="65465-156">Field name</span></span> | <span data-ttu-id="65465-157">説明</span><span class="sxs-lookup"><span data-stu-id="65465-157">Description</span></span> | <span data-ttu-id="65465-158">値の例</span><span class="sxs-lookup"><span data-stu-id="65465-158">Example value</span></span>
-|-|-
<span data-ttu-id="65465-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="65465-159">incidentId</span></span> | <span data-ttu-id="65465-160">インシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="65465-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="65465-161">924565</span><span class="sxs-lookup"><span data-stu-id="65465-161">924565</span></span>
<span data-ttu-id="65465-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="65465-162">redirectIncidentId</span></span> | <span data-ttu-id="65465-163">インシデント処理ロジックの一部として、インシデントが別のインシデントとグループ化されている場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="65465-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="65465-164">924569</span><span class="sxs-lookup"><span data-stu-id="65465-164">924569</span></span>
<span data-ttu-id="65465-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="65465-165">incidentName</span></span> | <span data-ttu-id="65465-166">すべてのインシデントで使用できる文字列値。</span><span class="sxs-lookup"><span data-stu-id="65465-166">String value available for every incident.</span></span> | <span data-ttu-id="65465-167">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="65465-167">Ransomware activity</span></span>
<span data-ttu-id="65465-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="65465-168">createdTime</span></span> | <span data-ttu-id="65465-169">インシデントが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-169">Time when incident was first created.</span></span> | <span data-ttu-id="65465-170">2020-09-06T14:46:57.073333Z</span><span class="sxs-lookup"><span data-stu-id="65465-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="65465-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="65465-171">lastUpdateTime</span></span> | <span data-ttu-id="65465-172">バックエンドでインシデントが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="65465-173">このフィールドは、インシデントが取得される時間の範囲に対して要求パラメーターを設定するときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="65465-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="65465-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="65465-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="65465-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="65465-175">assignedTo</span></span> | <span data-ttu-id="65465-176">インシデントの所有者、または所有者 *が割り当* てられていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="65465-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="65465-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-177">secop2@contoso.com</span></span>
<span data-ttu-id="65465-178">classification</span><span class="sxs-lookup"><span data-stu-id="65465-178">classification</span></span> | <span data-ttu-id="65465-179">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="65465-179">The specification for the incident.</span></span> <span data-ttu-id="65465-180">プロパティの値は次 *のとおりです。不明\*\*、FalsePositive、TruePositive* </span><span class="sxs-lookup"><span data-stu-id="65465-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="65465-181">不明</span><span class="sxs-lookup"><span data-stu-id="65465-181">Unknown</span></span>
<span data-ttu-id="65465-182">決定</span><span class="sxs-lookup"><span data-stu-id="65465-182">determination</span></span> | <span data-ttu-id="65465-183">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="65465-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="65465-184">プロパティの値は次 *のとおりです。 NotAvailable*、 *Apt*、 *Malware*、 *SecurityPersonnel*、 *SecurityTesting*、 *UnwantedSoftware*、*その* 他</span><span class="sxs-lookup"><span data-stu-id="65465-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="65465-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="65465-185">NotAvailable</span></span>
<span data-ttu-id="65465-186">status</span><span class="sxs-lookup"><span data-stu-id="65465-186">status</span></span> | <span data-ttu-id="65465-187">インシデント (アクティブ *、または解決* 済み) *を分類します*。</span><span class="sxs-lookup"><span data-stu-id="65465-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="65465-188">インシデントに対する対応を整理および管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="65465-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="65465-189">有効</span><span class="sxs-lookup"><span data-stu-id="65465-189">Active</span></span>
<span data-ttu-id="65465-190">severity</span><span class="sxs-lookup"><span data-stu-id="65465-190">severity</span></span> | <span data-ttu-id="65465-191">アセットへの影響の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="65465-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="65465-192">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="65465-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="65465-193">通常、重要度の高い項目では、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="65465-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="65465-194">次のいずれかの値: Informational、Low、\*Medium、High です。  </span><span class="sxs-lookup"><span data-stu-id="65465-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="65465-195">中</span><span class="sxs-lookup"><span data-stu-id="65465-195">Medium</span></span>
<span data-ttu-id="65465-196">tags</span><span class="sxs-lookup"><span data-stu-id="65465-196">tags</span></span> | <span data-ttu-id="65465-197">インシデントに関連付けられたカスタム タグの配列 。たとえば、共通の特性を持つインシデントのグループにフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="65465-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="65465-198">comments</span><span class="sxs-lookup"><span data-stu-id="65465-198">comments</span></span> | <span data-ttu-id="65465-199">インシデントの管理時に secops によって作成されたコメントの配列 (分類の選択に関する追加情報など)。</span><span class="sxs-lookup"><span data-stu-id="65465-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="65465-200">アラート</span><span class="sxs-lookup"><span data-stu-id="65465-200">alerts</span></span> | <span data-ttu-id="65465-201">インシデントに関連するアラートのすべてと、重大度、アラートに関係していたエンティティ、アラートのソースなどのその他の情報を含む配列。</span><span class="sxs-lookup"><span data-stu-id="65465-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="65465-202">\[\] (以下のアラート フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="65465-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="65465-203">アラート メタデータ</span><span class="sxs-lookup"><span data-stu-id="65465-203">Alerts metadata</span></span>

<span data-ttu-id="65465-204">フィールド名</span><span class="sxs-lookup"><span data-stu-id="65465-204">Field name</span></span> | <span data-ttu-id="65465-205">説明</span><span class="sxs-lookup"><span data-stu-id="65465-205">Description</span></span> | <span data-ttu-id="65465-206">値の例</span><span class="sxs-lookup"><span data-stu-id="65465-206">Example value</span></span>
-|-|-
<span data-ttu-id="65465-207">alertId</span><span class="sxs-lookup"><span data-stu-id="65465-207">alertId</span></span> | <span data-ttu-id="65465-208">アラートを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="65465-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="65465-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="65465-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="65465-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="65465-210">incidentId</span></span> | <span data-ttu-id="65465-211">このアラートが関連付けられているインシデントを表す一意の識別子</span><span class="sxs-lookup"><span data-stu-id="65465-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="65465-212">924565</span><span class="sxs-lookup"><span data-stu-id="65465-212">924565</span></span>
<span data-ttu-id="65465-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="65465-213">serviceSource</span></span> | <span data-ttu-id="65465-214">Microsoft Defender for Endpoint、microsoft Defender for Endpoint、Microsoft Cloud App Security Id、Microsoft Defender for Identity など、アラートの発生元となるサービスOffice 365。</span><span class="sxs-lookup"><span data-stu-id="65465-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="65465-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="65465-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="65465-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="65465-216">creationTime</span></span> | <span data-ttu-id="65465-217">アラートが最初に作成された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-217">Time when alert was first created.</span></span> | <span data-ttu-id="65465-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="65465-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="65465-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="65465-219">lastUpdatedTime</span></span> | <span data-ttu-id="65465-220">バックエンドでアラートが最後に更新された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="65465-221">2020-09-06T14:46:57.243333Z</span><span class="sxs-lookup"><span data-stu-id="65465-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="65465-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="65465-222">resolvedTime</span></span> | <span data-ttu-id="65465-223">アラートが解決された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-223">Time when alert was resolved.</span></span> | <span data-ttu-id="65465-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="65465-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="65465-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="65465-225">firstActivity</span></span> | <span data-ttu-id="65465-226">アクティビティがバックエンドで更新されたとアラートが最初に報告された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="65465-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="65465-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="65465-228">title</span><span class="sxs-lookup"><span data-stu-id="65465-228">title</span></span> | <span data-ttu-id="65465-229">各アラートで使用できる文字列値を簡単に識別します。</span><span class="sxs-lookup"><span data-stu-id="65465-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="65465-230">ランサムウェアのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="65465-230">Ransomware activity</span></span>
<span data-ttu-id="65465-231">説明</span><span class="sxs-lookup"><span data-stu-id="65465-231">description</span></span> | <span data-ttu-id="65465-232">各アラートを表す文字列値。</span><span class="sxs-lookup"><span data-stu-id="65465-232">String value describing each alert.</span></span> | <span data-ttu-id="65465-233">ユーザー Test User2 (testUser2@contoso.com) は、複数の拡張子を持つ 99 ファイルを操作し、珍しい拡張子 *herunterladen で終わらせた*。</span><span class="sxs-lookup"><span data-stu-id="65465-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="65465-234">これは、ファイル操作の異常な数であり、潜在的なランサムウェア攻撃を示しています。</span><span class="sxs-lookup"><span data-stu-id="65465-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="65465-235">category</span><span class="sxs-lookup"><span data-stu-id="65465-235">category</span></span> | <span data-ttu-id="65465-236">キル チェーンに沿って攻撃がどこまで進んでいるかの視覚的および数値的なビュー。</span><span class="sxs-lookup"><span data-stu-id="65465-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="65465-237">CK の [MITRE ATT&に™します](https://attack.mitre.org/)。</span><span class="sxs-lookup"><span data-stu-id="65465-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="65465-238">影響</span><span class="sxs-lookup"><span data-stu-id="65465-238">Impact</span></span>
<span data-ttu-id="65465-239">status</span><span class="sxs-lookup"><span data-stu-id="65465-239">status</span></span> | <span data-ttu-id="65465-240">アラートを分類する (*新規、\*\*アクティブ*、*または解決済み*)。</span><span class="sxs-lookup"><span data-stu-id="65465-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="65465-241">アラートに対する応答を整理および管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="65465-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="65465-242">新規</span><span class="sxs-lookup"><span data-stu-id="65465-242">New</span></span>
<span data-ttu-id="65465-243">severity</span><span class="sxs-lookup"><span data-stu-id="65465-243">severity</span></span> | <span data-ttu-id="65465-244">アセットへの影響の可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="65465-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="65465-245">重大度が高いほど、影響は大きくなります。</span><span class="sxs-lookup"><span data-stu-id="65465-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="65465-246">通常、重要度の高い項目では、最も迅速な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="65465-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="65465-247">次のいずれかの値: Informational、Low、\*Medium、High です。  </span><span class="sxs-lookup"><span data-stu-id="65465-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="65465-248">中</span><span class="sxs-lookup"><span data-stu-id="65465-248">Medium</span></span>
<span data-ttu-id="65465-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="65465-249">investigationId</span></span> | <span data-ttu-id="65465-250">このアラートによってトリガーされる自動調査 ID。</span><span class="sxs-lookup"><span data-stu-id="65465-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="65465-251">1234</span><span class="sxs-lookup"><span data-stu-id="65465-251">1234</span></span>
<span data-ttu-id="65465-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="65465-252">investigationState</span></span> | <span data-ttu-id="65465-253">調査の現在の状態に関する情報。</span><span class="sxs-lookup"><span data-stu-id="65465-253">Information on the investigation's current status.</span></span> <span data-ttu-id="65465-254">次の値の 1 つ:不明、終了 、正常に修復された、良性、失敗、*部分的* に修復された、*実行中\*\*、PendingApproval 、PendingApproval* *、PendingResource* *、PartiallyInvestigated 、TerminatedByUser 、TerminatedBySystem*、キューに入れられ *、InnerFailure 、PreexistingAlert*   *、UnsupportedOs* *、UnsupportedAlertType* *、SuppressedAlert*。 </span><span class="sxs-lookup"><span data-stu-id="65465-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="65465-255">サポートされていないAlertType</span><span class="sxs-lookup"><span data-stu-id="65465-255">UnsupportedAlertType</span></span>
<span data-ttu-id="65465-256">classification</span><span class="sxs-lookup"><span data-stu-id="65465-256">classification</span></span> | <span data-ttu-id="65465-257">インシデントの仕様。</span><span class="sxs-lookup"><span data-stu-id="65465-257">The specification for the incident.</span></span> <span data-ttu-id="65465-258">プロパティの値は、*不明\*\*、FalsePositive、TruePositive、* または *null です。* </span><span class="sxs-lookup"><span data-stu-id="65465-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="65465-259">不明</span><span class="sxs-lookup"><span data-stu-id="65465-259">Unknown</span></span>
<span data-ttu-id="65465-260">決定</span><span class="sxs-lookup"><span data-stu-id="65465-260">determination</span></span> | <span data-ttu-id="65465-261">インシデントの決定を指定します。</span><span class="sxs-lookup"><span data-stu-id="65465-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="65465-262">プロパティの値は次 *のとおりです。 NotAvailable*、 *Apt*、 *Malware*、 *SecurityPersonnel*、 *SecurityTesting* *、* *UnwantedSoftware*、 Other or *null*</span><span class="sxs-lookup"><span data-stu-id="65465-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="65465-263">Apt</span><span class="sxs-lookup"><span data-stu-id="65465-263">Apt</span></span>
<span data-ttu-id="65465-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="65465-264">assignedTo</span></span> | <span data-ttu-id="65465-265">インシデントの所有者、または所有者 *が割り当* てられていない場合は null。</span><span class="sxs-lookup"><span data-stu-id="65465-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="65465-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-266">secop2@contoso.com</span></span>
<span data-ttu-id="65465-267">actorName</span><span class="sxs-lookup"><span data-stu-id="65465-267">actorName</span></span> | <span data-ttu-id="65465-268">このアラートに関連付けられているアクティビティ グループ (その場合)。</span><span class="sxs-lookup"><span data-stu-id="65465-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="65465-269">ボロン</span><span class="sxs-lookup"><span data-stu-id="65465-269">BORON</span></span>
<span data-ttu-id="65465-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="65465-270">threatFamilyName</span></span> | <span data-ttu-id="65465-271">このアラートに関連付けられた脅威ファミリ。</span><span class="sxs-lookup"><span data-stu-id="65465-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="65465-272">null</span><span class="sxs-lookup"><span data-stu-id="65465-272">null</span></span>
<span data-ttu-id="65465-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="65465-273">mitreTechniques</span></span> | <span data-ttu-id="65465-274">攻撃手法は [、MITRE ATT](https://attack.mitre.org/)および CK&に™されます。</span><span class="sxs-lookup"><span data-stu-id="65465-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="65465-275">デバイス</span><span class="sxs-lookup"><span data-stu-id="65465-275">devices</span></span> | <span data-ttu-id="65465-276">インシデントに関連する通知が送信されたすべてのデバイス。</span><span class="sxs-lookup"><span data-stu-id="65465-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="65465-277">\[\] (以下のエンティティ フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="65465-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="65465-278">デバイスの形式</span><span class="sxs-lookup"><span data-stu-id="65465-278">Device format</span></span>

<span data-ttu-id="65465-279">フィールド名</span><span class="sxs-lookup"><span data-stu-id="65465-279">Field name</span></span> | <span data-ttu-id="65465-280">説明</span><span class="sxs-lookup"><span data-stu-id="65465-280">Description</span></span> | <span data-ttu-id="65465-281">値の例</span><span class="sxs-lookup"><span data-stu-id="65465-281">Example value</span></span>
-|-|-
<span data-ttu-id="65465-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="65465-282">DeviceId</span></span> | <span data-ttu-id="65465-283">Microsoft Defender for Endpoint で指定されているデバイス ID。</span><span class="sxs-lookup"><span data-stu-id="65465-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="65465-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="65465-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="65465-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="65465-285">aadDeviceId</span></span> |  <span data-ttu-id="65465-286">デバイス ID は、デバイス ID で指定[Azure Active Directory。](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="65465-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="65465-287">ドメインに参加しているデバイスでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="65465-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="65465-288">null</span><span class="sxs-lookup"><span data-stu-id="65465-288">null</span></span>
<span data-ttu-id="65465-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="65465-289">deviceDnsName</span></span> | <span data-ttu-id="65465-290">デバイスの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="65465-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="65465-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="65465-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="65465-292">osPlatform</span></span> | <span data-ttu-id="65465-293">デバイスが実行されている OS プラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="65465-293">The OS platform the device is running.</span></span>| <span data-ttu-id="65465-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="65465-294">WindowsServer2016</span></span>
<span data-ttu-id="65465-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="65465-295">osBuild</span></span> | <span data-ttu-id="65465-296">デバイスが実行されている OS のビルド バージョン。</span><span class="sxs-lookup"><span data-stu-id="65465-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="65465-297">14393</span><span class="sxs-lookup"><span data-stu-id="65465-297">14393</span></span>
<span data-ttu-id="65465-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="65465-298">rbacGroupName</span></span> | <span data-ttu-id="65465-299">デバイス [に関連付けられた役割ベース](/azure/role-based-access-control/overview) のアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="65465-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="65465-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="65465-300">WDATP-Ring0</span></span>
<span data-ttu-id="65465-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="65465-301">firstSeen</span></span> | <span data-ttu-id="65465-302">デバイスが最初に表示された時刻。</span><span class="sxs-lookup"><span data-stu-id="65465-302">Time when device was first seen.</span></span> | <span data-ttu-id="65465-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="65465-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="65465-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="65465-304">healthStatus</span></span> | <span data-ttu-id="65465-305">デバイスの正常性状態。</span><span class="sxs-lookup"><span data-stu-id="65465-305">The health state of the device.</span></span> | <span data-ttu-id="65465-306">有効</span><span class="sxs-lookup"><span data-stu-id="65465-306">Active</span></span>
<span data-ttu-id="65465-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="65465-307">riskScore</span></span> | <span data-ttu-id="65465-308">デバイスのリスク スコア。</span><span class="sxs-lookup"><span data-stu-id="65465-308">The risk score for the  device.</span></span> | <span data-ttu-id="65465-309">高い</span><span class="sxs-lookup"><span data-stu-id="65465-309">High</span></span>
<span data-ttu-id="65465-310">エンティティ</span><span class="sxs-lookup"><span data-stu-id="65465-310">entities</span></span> | <span data-ttu-id="65465-311">特定のアラートの一部として、または関連付けと識別されたすべてのエンティティ。</span><span class="sxs-lookup"><span data-stu-id="65465-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="65465-312">\[\] (以下のエンティティ フィールドの詳細を参照してください)</span><span class="sxs-lookup"><span data-stu-id="65465-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="65465-313">エンティティの形式</span><span class="sxs-lookup"><span data-stu-id="65465-313">Entity Format</span></span>

<span data-ttu-id="65465-314">フィールド名</span><span class="sxs-lookup"><span data-stu-id="65465-314">Field name</span></span> | <span data-ttu-id="65465-315">説明</span><span class="sxs-lookup"><span data-stu-id="65465-315">Description</span></span> | <span data-ttu-id="65465-316">値の例</span><span class="sxs-lookup"><span data-stu-id="65465-316">Example value</span></span>
-|-|-
<span data-ttu-id="65465-317">entityType</span><span class="sxs-lookup"><span data-stu-id="65465-317">entityType</span></span> | <span data-ttu-id="65465-318">特定のアラートの一部または関連付けと識別されたエンティティ。</span><span class="sxs-lookup"><span data-stu-id="65465-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="65465-319">プロパティの値は次 *のとおりです*。 ユーザー 、 *Ip*、 *Url*、*ファイル*、*プロセス*、 MailBox 、 *MailMessage*、  *MailCluster*、*レジストリ*</span><span class="sxs-lookup"><span data-stu-id="65465-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="65465-320">User</span><span class="sxs-lookup"><span data-stu-id="65465-320">User</span></span>
<span data-ttu-id="65465-321">sha1</span><span class="sxs-lookup"><span data-stu-id="65465-321">sha1</span></span> | <span data-ttu-id="65465-322">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="65465-323">ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="65465-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="65465-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="65465-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="65465-325">sha256</span><span class="sxs-lookup"><span data-stu-id="65465-325">sha256</span></span> | <span data-ttu-id="65465-326">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="65465-327">ファイルまたはプロセスに関連付けられたアラートのファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="65465-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="65465-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="65465-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="65465-329">fileName</span><span class="sxs-lookup"><span data-stu-id="65465-329">fileName</span></span> | <span data-ttu-id="65465-330">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="65465-331">ファイルまたはプロセスに関連付けられたアラートのファイル名</span><span class="sxs-lookup"><span data-stu-id="65465-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="65465-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="65465-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="65465-333">filePath</span><span class="sxs-lookup"><span data-stu-id="65465-333">filePath</span></span> | <span data-ttu-id="65465-334">entityType が File の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="65465-335">ファイルまたはプロセスに関連付けられたアラートのファイル パス</span><span class="sxs-lookup"><span data-stu-id="65465-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="65465-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="65465-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="65465-337">processId</span><span class="sxs-lookup"><span data-stu-id="65465-337">processId</span></span> | <span data-ttu-id="65465-338">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="65465-339">24348</span><span class="sxs-lookup"><span data-stu-id="65465-339">24348</span></span>
<span data-ttu-id="65465-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="65465-340">processCommandLine</span></span> | <span data-ttu-id="65465-341">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="65465-342">"ファイルがダウンロードできる状態 \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="65465-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="65465-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="65465-343">processCreationTime</span></span> | <span data-ttu-id="65465-344">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="65465-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="65465-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="65465-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="65465-346">parentProcessId</span></span> | <span data-ttu-id="65465-347">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="65465-348">16840</span><span class="sxs-lookup"><span data-stu-id="65465-348">16840</span></span>
<span data-ttu-id="65465-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="65465-349">parentProcessCreationTime</span></span> | <span data-ttu-id="65465-350">entityType が Process の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="65465-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="65465-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="65465-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="65465-352">ipAddress</span></span> | <span data-ttu-id="65465-353">entityType が Ip の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="65465-354">悪意のあるネットワーク宛先への通信など、ネットワーク イベントに関連付 *けられたアラートの* IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="65465-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="65465-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="65465-355">62.216.203.204</span></span>
<span data-ttu-id="65465-356">url</span><span class="sxs-lookup"><span data-stu-id="65465-356">url</span></span> | <span data-ttu-id="65465-357">entityType が Url の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="65465-358">ネットワーク イベント (悪意のあるネットワーク宛先への通信など) に関連付 *けられたアラートの URL* です。</span><span class="sxs-lookup"><span data-stu-id="65465-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="65465-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="65465-359">down.esales360.cn</span></span>
<span data-ttu-id="65465-360">accountName</span><span class="sxs-lookup"><span data-stu-id="65465-360">accountName</span></span> | <span data-ttu-id="65465-361">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="65465-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="65465-362">testUser2</span></span>
<span data-ttu-id="65465-363">domainName</span><span class="sxs-lookup"><span data-stu-id="65465-363">domainName</span></span> | <span data-ttu-id="65465-364">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="65465-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="65465-365">europe.corp.contoso</span></span>
<span data-ttu-id="65465-366">userSid</span><span class="sxs-lookup"><span data-stu-id="65465-366">userSid</span></span> | <span data-ttu-id="65465-367">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="65465-368">S-1-5-21-1721254763-462695806-1538882281-41566657</span><span class="sxs-lookup"><span data-stu-id="65465-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="65465-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="65465-369">aadUserId</span></span> | <span data-ttu-id="65465-370">entityType が User の場合に *使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="65465-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="65465-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="65465-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="65465-372">userPrincipalName</span></span> | <span data-ttu-id="65465-373">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="65465-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-374">testUser2@contoso.com</span></span>
<span data-ttu-id="65465-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="65465-375">mailboxDisplayName</span></span> | <span data-ttu-id="65465-376">entityType が *MailBox の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="65465-377">Test User2</span><span class="sxs-lookup"><span data-stu-id="65465-377">test User2</span></span>
<span data-ttu-id="65465-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="65465-378">mailboxAddress</span></span> | <span data-ttu-id="65465-379">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="65465-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-380">testUser2@contoso.com</span></span>
<span data-ttu-id="65465-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="65465-381">clusterBy</span></span> | <span data-ttu-id="65465-382">entityType が  *MailCluster の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="65465-383">件名。P2SenderDomain;ContentType</span><span class="sxs-lookup"><span data-stu-id="65465-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="65465-384">sender</span><span class="sxs-lookup"><span data-stu-id="65465-384">sender</span></span> | <span data-ttu-id="65465-385">entityType がUser / *MailBox* / *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="65465-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="65465-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="65465-387">受信者</span><span class="sxs-lookup"><span data-stu-id="65465-387">recipient</span></span> | <span data-ttu-id="65465-388">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="65465-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="65465-389">testUser2@contoso.com</span></span>
<span data-ttu-id="65465-390">subject</span><span class="sxs-lookup"><span data-stu-id="65465-390">subject</span></span> | <span data-ttu-id="65465-391">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="65465-392">\[EXTERNAL \] Attention</span><span class="sxs-lookup"><span data-stu-id="65465-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="65465-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="65465-393">deliveryAction</span></span> | <span data-ttu-id="65465-394">entityType が *MailMessage の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="65465-395">配信</span><span class="sxs-lookup"><span data-stu-id="65465-395">Delivered</span></span>
<span data-ttu-id="65465-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="65465-396">securityGroupId</span></span> | <span data-ttu-id="65465-397">entityType が  *SecurityGroup の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="65465-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="65465-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="65465-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="65465-399">securityGroupName</span></span> | <span data-ttu-id="65465-400">entityType が  *SecurityGroup の場合に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="65465-401">ネットワーク構成演算子</span><span class="sxs-lookup"><span data-stu-id="65465-401">Network Configuration Operators</span></span>
<span data-ttu-id="65465-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="65465-402">registryHive</span></span> | <span data-ttu-id="65465-403">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="65465-404">HKEY \_ ローカル \_ コンピューター</span><span class="sxs-lookup"><span data-stu-id="65465-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="65465-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="65465-405">registryKey</span></span> | <span data-ttu-id="65465-406">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="65465-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="65465-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="65465-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="65465-408">registryValueType</span></span> | <span data-ttu-id="65465-409">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="65465-410">String</span><span class="sxs-lookup"><span data-stu-id="65465-410">String</span></span>
<span data-ttu-id="65465-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="65465-411">registryValue</span></span> | <span data-ttu-id="65465-412">entityType がレジストリの場合  *に使用できます*。</span><span class="sxs-lookup"><span data-stu-id="65465-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="65465-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="65465-413">31-00-00-00</span></span>
<span data-ttu-id="65465-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="65465-414">deviceId</span></span> | <span data-ttu-id="65465-415">エンティティに関連するデバイスの ID (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="65465-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="65465-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="65465-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="65465-417">例</span><span class="sxs-lookup"><span data-stu-id="65465-417">Example</span></span>

<span data-ttu-id="65465-418">**要求**</span><span class="sxs-lookup"><span data-stu-id="65465-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="65465-419">**応答**</span><span class="sxs-lookup"><span data-stu-id="65465-419">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="65465-420">関連記事</span><span class="sxs-lookup"><span data-stu-id="65465-420">Related articles</span></span>

- [<span data-ttu-id="65465-421">Defender API Microsoft 365アクセスする</span><span class="sxs-lookup"><span data-stu-id="65465-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="65465-422">API の制限とライセンスの詳細</span><span class="sxs-lookup"><span data-stu-id="65465-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="65465-423">エラー コードについて</span><span class="sxs-lookup"><span data-stu-id="65465-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="65465-424">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="65465-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="65465-425">インシデント API</span><span class="sxs-lookup"><span data-stu-id="65465-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="65465-426">インシデント API の更新</span><span class="sxs-lookup"><span data-stu-id="65465-426">Update incident API</span></span>](api-update-incidents.md)
