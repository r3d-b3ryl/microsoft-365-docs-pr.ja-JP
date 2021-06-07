---
title: REST API を使用したエンドポイント検出用の Microsoft Defender のプル
description: SIEM REST API を使用して MICROSOFT Defender for Endpoint API エンドポイントを呼び出して JSON 形式で検出をプルする方法について説明します。
keywords: 検出、プル検出、rest api、要求、応答
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771671"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="bb3f0-104">SIEM REST API を使用したエンドポイント検出用の Microsoft Defender のプル</span><span class="sxs-lookup"><span data-stu-id="bb3f0-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bb3f0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bb3f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="bb3f0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bb3f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bb3f0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb3f0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bb3f0-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="bb3f0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bb3f0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="bb3f0-110">[Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="bb3f0-111">[Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="bb3f0-112">-Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="bb3f0-113">詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="bb3f0-114">Microsoft Defender for Endpoint は、API から検出を引き出す OAuth 2.0 プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="bb3f0-115">一般に、OAuth 2.0 プロトコルは 4 種類のフローをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="bb3f0-116">承認の付与フロー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-116">Authorization grant flow</span></span>
- <span data-ttu-id="bb3f0-117">暗黙的フロー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-117">Implicit flow</span></span>
- <span data-ttu-id="bb3f0-118">クライアント資格情報フロー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-118">Client credentials flow</span></span>
- <span data-ttu-id="bb3f0-119">リソース所有者フロー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-119">Resource owner flow</span></span>

<span data-ttu-id="bb3f0-120">OAuth 仕様の詳細については [、「OAuth Web サイト」を参照してください](http://www.oauth.net)。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="bb3f0-121">Microsoft Defender for  Endpoint では、承認許可フローとクライアント資格情報フローがサポートされ、認証サーバーとして Azure Active Directory (AAD) を使用してプル検出へのアクセスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="bb3f0-122">承認 _付与フローは、_ ユーザー資格情報を使用して承認コードを取得し、アクセス トークンを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="bb3f0-123">クライアント _資格情報フローでは、_ クライアント資格情報を使用して Microsoft Defender for Endpoint エンドポイント URL に対する認証を行います。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="bb3f0-124">このフローは、OAuth クライアントがユーザー資格情報を必要としない API への要求を作成するシナリオに適しています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="bb3f0-125">Microsoft Defender for Endpoint API の次のメソッドを使用して、JSON 形式で検出をプルします。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="bb3f0-126">Microsoft Defender セキュリティ センター同様のアラート検出を 1 つのアラートにマージします。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="bb3f0-127">この API は、設定したクエリ パラメーターに基づいて生の形式でアラート検出をプルし、独自のグループ化とフィルター処理を適用できます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="bb3f0-128">はじめに</span><span class="sxs-lookup"><span data-stu-id="bb3f0-128">Before you begin</span></span>
- <span data-ttu-id="bb3f0-129">検出をプルするために Microsoft Defender for Endpoint エンドポイントを呼び出す前に、デバイス (AAD) で SIEM 統合アプリケーションAzure Active Directory必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="bb3f0-130">詳細については [、「Enable SIEM integration in Microsoft Defender for Endpoint」を参照してください](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="bb3f0-p106">Azure アプリケーション登録の次の値をメモしてください。サービスまたはデーモンアプリ内に OAuth フローを構成するにはこれらの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="bb3f0-133">アプリケーション ID (アプリケーションで一意)</span><span class="sxs-lookup"><span data-stu-id="bb3f0-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="bb3f0-134">アプリ キー、またはシークレット (アプリケーションで一意)</span><span class="sxs-lookup"><span data-stu-id="bb3f0-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="bb3f0-135">アプリの OAuth 2.0 のトークン エンドポイント</span><span class="sxs-lookup"><span data-stu-id="bb3f0-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="bb3f0-p107">この値は、Azure 管理ポータルでアプリのページの下部にある **[エンドポイントの表示]** をクリックすると表示されます。エンドポイントは `https://login.microsoftonline.com/{tenantId}/oauth2/token` のようになります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="bb3f0-138">アクセス トークンを取得する</span><span class="sxs-lookup"><span data-stu-id="bb3f0-138">Get an access token</span></span>
<span data-ttu-id="bb3f0-139">エンドポイントへの呼び出しを作成する前に、アクセス トークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="bb3f0-140">アクセス トークンを使用して、保護されたリソース (Microsoft Defender for Endpoint での検出) にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bb3f0-141">アクセス トークンを取得するには、トークン発行エンドポイントに対して POST 要求を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="bb3f0-142">要求の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="bb3f0-143">応答には、アクセス トークンと有効期限の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="bb3f0-144">Defender for Endpoint API への要求 *access_tokenフィールドの* 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="bb3f0-145">要求</span><span class="sxs-lookup"><span data-stu-id="bb3f0-145">Request</span></span>
<span data-ttu-id="bb3f0-146">アクセス トークンを使用すると、アプリは Microsoft Defender for Endpoint API に対して認証された要求を行います。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="bb3f0-147">アプリで各要求の Authorization ヘッダーにアクセス トークンを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="bb3f0-148">要求構文</span><span class="sxs-lookup"><span data-stu-id="bb3f0-148">Request syntax</span></span>
<span data-ttu-id="bb3f0-149">Method</span><span class="sxs-lookup"><span data-stu-id="bb3f0-149">Method</span></span> | <span data-ttu-id="bb3f0-150">要求 URI</span><span class="sxs-lookup"><span data-stu-id="bb3f0-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="bb3f0-151">GET</span><span class="sxs-lookup"><span data-stu-id="bb3f0-151">GET</span></span>| <span data-ttu-id="bb3f0-152">地域に適用可能な URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="bb3f0-153">**EU の場合**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bb3f0-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="bb3f0-154">**米国の場合**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bb3f0-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="bb3f0-155">**英国の場合**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="bb3f0-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="bb3f0-156">要求ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-156">Request header</span></span>
<span data-ttu-id="bb3f0-157">ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bb3f0-157">Header</span></span> | <span data-ttu-id="bb3f0-158">種類</span><span class="sxs-lookup"><span data-stu-id="bb3f0-158">Type</span></span> | <span data-ttu-id="bb3f0-159">説明</span><span class="sxs-lookup"><span data-stu-id="bb3f0-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="bb3f0-160">Authorization</span><span class="sxs-lookup"><span data-stu-id="bb3f0-160">Authorization</span></span> | <span data-ttu-id="bb3f0-161">string</span><span class="sxs-lookup"><span data-stu-id="bb3f0-161">string</span></span> | <span data-ttu-id="bb3f0-162">必須です。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-162">Required.</span></span> <span data-ttu-id="bb3f0-163">Azure ADベアラー トークンという形式の **アクセス トークンです** &lt;  &gt; 。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="bb3f0-164">要求パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb3f0-164">Request parameters</span></span>

<span data-ttu-id="bb3f0-165">オプションのクエリ パラメーターを使用して、応答で返されるデータ量を指定および制御します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="bb3f0-166">パラメーターを指定せずにこのメソッドを呼び出した場合、過去 2 時間の組織のすべての通知が応答に含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="bb3f0-167">名前</span><span class="sxs-lookup"><span data-stu-id="bb3f0-167">Name</span></span> | <span data-ttu-id="bb3f0-168">値</span><span class="sxs-lookup"><span data-stu-id="bb3f0-168">Value</span></span>| <span data-ttu-id="bb3f0-169">説明</span><span class="sxs-lookup"><span data-stu-id="bb3f0-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="bb3f0-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="bb3f0-170">sinceTimeUtc</span></span> | <span data-ttu-id="bb3f0-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="bb3f0-171">DateTime</span></span> | <span data-ttu-id="bb3f0-172">フィールドに基づいて、取得される下限時間のアラートを定義します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="bb3f0-173">時間範囲は次の値です。sinceTimeUtc 時刻から現在の時刻までです。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="bb3f0-174">**注**: 指定しない場合、過去 2 時間に生成されたアラートはすべて取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="bb3f0-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="bb3f0-175">untilTimeUtc</span></span> | <span data-ttu-id="bb3f0-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="bb3f0-176">DateTime</span></span> | <span data-ttu-id="bb3f0-177">取得される上限時間のアラートを定義します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="bb3f0-178">時間範囲は、次の場合に `sinceTimeUtc` 指定 `untilTimeUtc` します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="bb3f0-179">**注**: 指定しない場合、既定値は現在の時刻になります。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="bb3f0-180">前</span><span class="sxs-lookup"><span data-stu-id="bb3f0-180">ago</span></span> | <span data-ttu-id="bb3f0-181">string</span><span class="sxs-lookup"><span data-stu-id="bb3f0-181">string</span></span> | <span data-ttu-id="bb3f0-182">次の時間範囲のアラートを引き `(current_time - ago)` 出 `current_time` します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="bb3f0-183">値は ISO **8601 期間形式に従って** 設定する必要があります</span><span class="sxs-lookup"><span data-stu-id="bb3f0-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="bb3f0-184">例: `ago=PT10M` 過去 10 分間に受信したアラートをプルします。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="bb3f0-185">limit</span><span class="sxs-lookup"><span data-stu-id="bb3f0-185">limit</span></span> | <span data-ttu-id="bb3f0-186">int</span><span class="sxs-lookup"><span data-stu-id="bb3f0-186">int</span></span> | <span data-ttu-id="bb3f0-187">取得するアラートの数を定義します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="bb3f0-188">最新のアラートは、定義された番号に基づいて取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="bb3f0-189">**注**: 指定しない場合、時間範囲内で使用可能なすべてのアラートが取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="bb3f0-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="bb3f0-190">machinegroups</span></span> | <span data-ttu-id="bb3f0-191">string</span><span class="sxs-lookup"><span data-stu-id="bb3f0-191">string</span></span> | <span data-ttu-id="bb3f0-192">アラートをプルするデバイス グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="bb3f0-193">**注**: 指定しない場合、すべてのデバイス グループからのアラートが取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="bb3f0-194">例:</span><span class="sxs-lookup"><span data-stu-id="bb3f0-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="bb3f0-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="bb3f0-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="bb3f0-196">string</span><span class="sxs-lookup"><span data-stu-id="bb3f0-196">string</span></span> | <span data-ttu-id="bb3f0-197">レジストリからの単一のデバイス タグ。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-197">Single device tag from the registry.</span></span>
<span data-ttu-id="bb3f0-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="bb3f0-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="bb3f0-199">string</span><span class="sxs-lookup"><span data-stu-id="bb3f0-199">string</span></span> | <span data-ttu-id="bb3f0-200">このページで作成されたデバイス Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="bb3f0-201">要求の例</span><span class="sxs-lookup"><span data-stu-id="bb3f0-201">Request example</span></span>
<span data-ttu-id="bb3f0-202">次の例は、組織内のすべての検出を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="bb3f0-203">次の例は、2016-09-12 00:00:00 以降の最後の 20 件の検出を取得する要求を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="bb3f0-204">応答</span><span class="sxs-lookup"><span data-stu-id="bb3f0-204">Response</span></span>
<span data-ttu-id="bb3f0-205">戻り値は、JSON 形式のアラート オブジェクトの配列です。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="bb3f0-206">戻り値の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="bb3f0-207">コード例</span><span class="sxs-lookup"><span data-stu-id="bb3f0-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="bb3f0-208">アクセス トークンの取得</span><span class="sxs-lookup"><span data-stu-id="bb3f0-208">Get access token</span></span>
<span data-ttu-id="bb3f0-209">次のコード例は、Microsoft Defender for Endpoint SIEM API を呼び出すアクセス トークンを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="bb3f0-210">トークンを使用して検出エンドポイントに接続する</span><span class="sxs-lookup"><span data-stu-id="bb3f0-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="bb3f0-211">次のコード例は、Defender for Endpoint SIEM API を呼び出してアラートを取得するためにアクセス トークンを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="bb3f0-212">エラー コード</span><span class="sxs-lookup"><span data-stu-id="bb3f0-212">Error codes</span></span>
<span data-ttu-id="bb3f0-213">Microsoft Defender for Endpoint REST API は、無効な要求によって引き起こされた次のエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="bb3f0-214">HTTP エラー コード</span><span class="sxs-lookup"><span data-stu-id="bb3f0-214">HTTP error code</span></span> | <span data-ttu-id="bb3f0-215">説明</span><span class="sxs-lookup"><span data-stu-id="bb3f0-215">Description</span></span>
:---|:---
<span data-ttu-id="bb3f0-216">401</span><span class="sxs-lookup"><span data-stu-id="bb3f0-216">401</span></span> | <span data-ttu-id="bb3f0-217">不正な形式の要求または無効なトークン。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="bb3f0-218">403</span><span class="sxs-lookup"><span data-stu-id="bb3f0-218">403</span></span> | <span data-ttu-id="bb3f0-219">承認されていない例外 - テナント管理者によって管理されていないドメインまたはテナントの状態が削除されます。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="bb3f0-220">500</span><span class="sxs-lookup"><span data-stu-id="bb3f0-220">500</span></span> | <span data-ttu-id="bb3f0-221">サービスのエラー。</span><span class="sxs-lookup"><span data-stu-id="bb3f0-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb3f0-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb3f0-222">Related topics</span></span>
- [<span data-ttu-id="bb3f0-223">エンドポイント向け Microsoft Defender で SIEM 統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="bb3f0-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="bb3f0-224">エンドポイント検出用の Microsoft Defender をプルする ArcSight の構成</span><span class="sxs-lookup"><span data-stu-id="bb3f0-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="bb3f0-225">SIEM ツールへの検出のプル</span><span class="sxs-lookup"><span data-stu-id="bb3f0-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="bb3f0-226">Microsoft Defender for Endpoint Detection フィールド</span><span class="sxs-lookup"><span data-stu-id="bb3f0-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="bb3f0-227">SIEM ツール統合に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bb3f0-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
