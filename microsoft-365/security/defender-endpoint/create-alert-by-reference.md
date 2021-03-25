---
title: イベント API からアラートを作成する
description: Create alert API を使用して、Microsoft Defender for Endpoint のイベントの上に新しいアラートを作成する方法について説明します。
keywords: apis, graph api, supported apis, get, alert, information, id
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
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167068"
---
# <a name="create-alert-api"></a><span data-ttu-id="bac50-104">アラート API の作成</span><span class="sxs-lookup"><span data-stu-id="bac50-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bac50-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bac50-105">**Applies to:**</span></span>
- [<span data-ttu-id="bac50-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bac50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bac50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bac50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="bac50-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bac50-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bac50-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="bac50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bac50-110">API の説明</span><span class="sxs-lookup"><span data-stu-id="bac50-110">API description</span></span>
<span data-ttu-id="bac50-111">イベントの上 [に新しいアラート](alerts.md) を **作成します**。</span><span class="sxs-lookup"><span data-stu-id="bac50-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="bac50-112">**Microsoft Defender for Endpoint Event は** 、アラートの作成に必要です。</span><span class="sxs-lookup"><span data-stu-id="bac50-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="bac50-113">要求でイベントから 3 つのパラメーターを指定する必要があります **。イベント** 時間、 **コンピューター ID、** レポート **ID です**。</span><span class="sxs-lookup"><span data-stu-id="bac50-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="bac50-114">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac50-114">See example below.</span></span>
<br><span data-ttu-id="bac50-115">Advanced Hunting API または Portal で見つかったイベントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac50-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="bac50-116">同じタイトルを持つ同じデバイスに開いているアラートが既存の場合、新しく作成されたアラートは、そのデバイスとマージされます。</span><span class="sxs-lookup"><span data-stu-id="bac50-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="bac50-117">自動調査は、API を介して作成されたアラートで自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="bac50-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="bac50-118">制限事項</span><span class="sxs-lookup"><span data-stu-id="bac50-118">Limitations</span></span>
1. <span data-ttu-id="bac50-119">この API のレート制限は、1 分あたり 15 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="bac50-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="bac50-120">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="bac50-120">Permissions</span></span>

<span data-ttu-id="bac50-121">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="bac50-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bac50-122">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bac50-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bac50-123">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="bac50-123">Permission type</span></span> |   <span data-ttu-id="bac50-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="bac50-124">Permission</span></span>  |   <span data-ttu-id="bac50-125">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="bac50-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bac50-126">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bac50-126">Application</span></span> |   <span data-ttu-id="bac50-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="bac50-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="bac50-128">'すべてのアラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="bac50-128">'Read and write all alerts'</span></span>
<span data-ttu-id="bac50-129">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="bac50-129">Delegated (work or school account)</span></span> | <span data-ttu-id="bac50-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="bac50-130">Alert.ReadWrite</span></span> | <span data-ttu-id="bac50-131">'アラートの読み取りと書き込み'</span><span class="sxs-lookup"><span data-stu-id="bac50-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="bac50-132">ユーザー資格情報を使用してトークンを取得する場合:</span><span class="sxs-lookup"><span data-stu-id="bac50-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bac50-133">ユーザーは、少なくとも次の役割のアクセス許可を持っている必要があります。 'アラートの調査' (詳細については、「 [役割](user-roles.md) の作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="bac50-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bac50-134">ユーザーは、デバイス グループ設定に基づいて、アラートに関連付けられたデバイスにアクセスできる必要[](machine-groups.md)があります (詳細については、「デバイス グループの作成と管理」を参照してください)</span><span class="sxs-lookup"><span data-stu-id="bac50-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bac50-135">HTTP 要求</span><span class="sxs-lookup"><span data-stu-id="bac50-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="bac50-136">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bac50-136">Request headers</span></span>

<span data-ttu-id="bac50-137">名前</span><span class="sxs-lookup"><span data-stu-id="bac50-137">Name</span></span> | <span data-ttu-id="bac50-138">種類</span><span class="sxs-lookup"><span data-stu-id="bac50-138">Type</span></span> | <span data-ttu-id="bac50-139">説明</span><span class="sxs-lookup"><span data-stu-id="bac50-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="bac50-140">Authorization</span><span class="sxs-lookup"><span data-stu-id="bac50-140">Authorization</span></span> | <span data-ttu-id="bac50-141">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-141">String</span></span> | <span data-ttu-id="bac50-142">ベアラー {token}。</span><span class="sxs-lookup"><span data-stu-id="bac50-142">Bearer {token}.</span></span> <span data-ttu-id="bac50-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-143">**Required**.</span></span>
<span data-ttu-id="bac50-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bac50-144">Content-Type</span></span> | <span data-ttu-id="bac50-145">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-145">String</span></span> | <span data-ttu-id="bac50-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="bac50-146">application/json.</span></span> <span data-ttu-id="bac50-147">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bac50-148">要求本文</span><span class="sxs-lookup"><span data-stu-id="bac50-148">Request body</span></span>

<span data-ttu-id="bac50-149">要求本文で、次の値を指定します (すべて必須)。</span><span class="sxs-lookup"><span data-stu-id="bac50-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="bac50-150">プロパティ</span><span class="sxs-lookup"><span data-stu-id="bac50-150">Property</span></span> | <span data-ttu-id="bac50-151">種類</span><span class="sxs-lookup"><span data-stu-id="bac50-151">Type</span></span> | <span data-ttu-id="bac50-152">説明</span><span class="sxs-lookup"><span data-stu-id="bac50-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="bac50-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="bac50-153">eventTime</span></span> | <span data-ttu-id="bac50-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="bac50-154">DateTime(UTC)</span></span> | <span data-ttu-id="bac50-155">高度な検索から取得したイベントの正確な時刻を文字列として指定します。</span><span class="sxs-lookup"><span data-stu-id="bac50-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="bac50-156">例: ```2018-08-03T16:45:21.7115183Z``` **必須です**。</span><span class="sxs-lookup"><span data-stu-id="bac50-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="bac50-157">reportId</span><span class="sxs-lookup"><span data-stu-id="bac50-157">reportId</span></span> | <span data-ttu-id="bac50-158">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-158">String</span></span> | <span data-ttu-id="bac50-159">高度な狩猟から取得したイベントの reportId。</span><span class="sxs-lookup"><span data-stu-id="bac50-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="bac50-160">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-160">**Required**.</span></span>
<span data-ttu-id="bac50-161">machineId</span><span class="sxs-lookup"><span data-stu-id="bac50-161">machineId</span></span> | <span data-ttu-id="bac50-162">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-162">String</span></span> | <span data-ttu-id="bac50-163">イベントが識別されたデバイスの ID。</span><span class="sxs-lookup"><span data-stu-id="bac50-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="bac50-164">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-164">**Required**.</span></span>
<span data-ttu-id="bac50-165">severity</span><span class="sxs-lookup"><span data-stu-id="bac50-165">severity</span></span> | <span data-ttu-id="bac50-166">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-166">String</span></span> | <span data-ttu-id="bac50-167">アラートの重大度。</span><span class="sxs-lookup"><span data-stu-id="bac50-167">Severity of the alert.</span></span> <span data-ttu-id="bac50-168">プロパティの値は、'Low'、'Medium'、および 'High' です。</span><span class="sxs-lookup"><span data-stu-id="bac50-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="bac50-169">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-169">**Required**.</span></span>
<span data-ttu-id="bac50-170">title</span><span class="sxs-lookup"><span data-stu-id="bac50-170">title</span></span> | <span data-ttu-id="bac50-171">String</span><span class="sxs-lookup"><span data-stu-id="bac50-171">String</span></span> | <span data-ttu-id="bac50-172">アラートのタイトル。</span><span class="sxs-lookup"><span data-stu-id="bac50-172">Title for the alert.</span></span> <span data-ttu-id="bac50-173">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-173">**Required**.</span></span>
<span data-ttu-id="bac50-174">説明</span><span class="sxs-lookup"><span data-stu-id="bac50-174">description</span></span> | <span data-ttu-id="bac50-175">String</span><span class="sxs-lookup"><span data-stu-id="bac50-175">String</span></span> | <span data-ttu-id="bac50-176">アラートの説明。</span><span class="sxs-lookup"><span data-stu-id="bac50-176">Description of the alert.</span></span> <span data-ttu-id="bac50-177">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-177">**Required**.</span></span>
<span data-ttu-id="bac50-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="bac50-178">recommendedAction</span></span>| <span data-ttu-id="bac50-179">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-179">String</span></span> | <span data-ttu-id="bac50-180">アラートの分析時にセキュリティ担当者が実行するアクションを推奨します。</span><span class="sxs-lookup"><span data-stu-id="bac50-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="bac50-181">**必須**</span><span class="sxs-lookup"><span data-stu-id="bac50-181">**Required**.</span></span>
<span data-ttu-id="bac50-182">category</span><span class="sxs-lookup"><span data-stu-id="bac50-182">category</span></span>| <span data-ttu-id="bac50-183">文字列</span><span class="sxs-lookup"><span data-stu-id="bac50-183">String</span></span> | <span data-ttu-id="bac50-184">アラートのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="bac50-184">Category of the alert.</span></span> <span data-ttu-id="bac50-185">プロパティの値は、"General"、"CommandAndControl"、"Collection"、"CredentialAccess"、"DefenseEvasion"、"Discovery"、"エクスプロイト"、"Exploit"、"Execution"、"InitialAccess"、"LateralMovement"、"Malware"、"Persistence"、"PrivilegeEscalation"、"Ransomware"、"SuspiciousActivity" が必要です。</span><span class="sxs-lookup"><span data-stu-id="bac50-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bac50-186">応答</span><span class="sxs-lookup"><span data-stu-id="bac50-186">Response</span></span>

<span data-ttu-id="bac50-187">成功した場合、このメソッドは 200 OK を返し、応答本文に新しい [アラート](alerts.md) オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bac50-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="bac50-188">指定したプロパティ _(reportId、eventTime、machineId)_ を持つイベントが見つからなかった場合は、404 Not Found です。  </span><span class="sxs-lookup"><span data-stu-id="bac50-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="bac50-189">例</span><span class="sxs-lookup"><span data-stu-id="bac50-189">Example</span></span>

<span data-ttu-id="bac50-190">**要求**</span><span class="sxs-lookup"><span data-stu-id="bac50-190">**Request**</span></span>

<span data-ttu-id="bac50-191">以下は、要求の例です。</span><span class="sxs-lookup"><span data-stu-id="bac50-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
