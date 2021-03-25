---
title: PowerShell API ガイドを使用した高度なハンティング
ms.reviewer: ''
description: これらのコード サンプルを使用して、いくつかの Microsoft Defender for Endpoint API を照会します。
keywords: apis、サポートされている API、高度な検索、クエリ
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198327"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="1d98f-104">PowerShell を使用したエンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d98f-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d98f-105">**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1d98f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1d98f-106">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1d98f-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d98f-107">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1d98f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="1d98f-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1d98f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d98f-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1d98f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="1d98f-110">Microsoft Defender for Endpoint の複数の API を使用した完全なシナリオ。</span><span class="sxs-lookup"><span data-stu-id="1d98f-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="1d98f-111">このセクションでは、PowerShell サンプルを</span><span class="sxs-lookup"><span data-stu-id="1d98f-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="1d98f-112">トークンの取得</span><span class="sxs-lookup"><span data-stu-id="1d98f-112">Retrieve a token</span></span> 
- <span data-ttu-id="1d98f-113">トークンを使用して Microsoft Defender for Endpoint の最新のアラートを取得する</span><span class="sxs-lookup"><span data-stu-id="1d98f-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1d98f-114">アラートごとに、アラートの優先度が中または高で、まだ進行中の場合は、デバイスが不審な URL に接続した回数を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d98f-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="1d98f-115">**前提条件**: 最初にアプリを [作成する必要があります](apis-intro.md)。</span><span class="sxs-lookup"><span data-stu-id="1d98f-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="1d98f-116">準備手順</span><span class="sxs-lookup"><span data-stu-id="1d98f-116">Preparation instructions</span></span>

- <span data-ttu-id="1d98f-117">PowerShell のウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="1d98f-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="1d98f-118">ポリシーで PowerShell コマンドを実行できない場合は、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1d98f-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="1d98f-119">詳細については [、「PowerShell のドキュメント」を参照してください。](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="1d98f-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="1d98f-120">トークンの取得</span><span class="sxs-lookup"><span data-stu-id="1d98f-120">Get token</span></span>

<span data-ttu-id="1d98f-121">以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d98f-121">Run the below:</span></span>

- <span data-ttu-id="1d98f-122">$tenantId: クエリを実行する代わりにテナントの ID (つまり、このテナントのデータに対してクエリが実行されます)</span><span class="sxs-lookup"><span data-stu-id="1d98f-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="1d98f-123">$appId: AAD アプリの ID (アプリに Defender for Endpoint への 「高度なクエリの実行」 アクセス許可が必要)</span><span class="sxs-lookup"><span data-stu-id="1d98f-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="1d98f-124">$appSecret: Azure AD アプリの秘密</span><span class="sxs-lookup"><span data-stu-id="1d98f-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="1d98f-125">$suspiciousUrl: URL</span><span class="sxs-lookup"><span data-stu-id="1d98f-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="1d98f-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d98f-126">See also</span></span>
- [<span data-ttu-id="1d98f-127">エンドポイント API 用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d98f-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="1d98f-128">高度な追及 API</span><span class="sxs-lookup"><span data-stu-id="1d98f-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="1d98f-129">Python を使用した高度なハンティング</span><span class="sxs-lookup"><span data-stu-id="1d98f-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
