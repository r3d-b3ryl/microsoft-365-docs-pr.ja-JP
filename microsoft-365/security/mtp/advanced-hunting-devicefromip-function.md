---
title: Microsoft 365 Defender の高度な検索での DeviceFromIP() 関数
description: DeviceFromIP() 関数を使用して、特定の IP アドレスが割り当てられているデバイスを取得する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、device、devicefromIP、function、enrichment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931304"
---
# <a name="devicefromip"></a><span data-ttu-id="97c69-104">DeviceFromIP()</span><span class="sxs-lookup"><span data-stu-id="97c69-104">DeviceFromIP()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="97c69-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="97c69-105">**Applies to:**</span></span>
- <span data-ttu-id="97c69-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="97c69-106">Microsoft 365 Defender</span></span>


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


<span data-ttu-id="97c69-107">高度な検索クエリの関数を使用して、特定の時点で特定の IP アドレスに割り当てられたデバイスの一覧 `DeviceFromIP()` をすばやく取得します。 [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="97c69-107">Use the `DeviceFromIP()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the list of devices that have been assigned to a certain IP address at a given point in time.</span></span> 

<span data-ttu-id="97c69-108">この関数は、次の列を含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="97c69-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="97c69-109">Column</span><span class="sxs-lookup"><span data-stu-id="97c69-109">Column</span></span> | <span data-ttu-id="97c69-110">データ型</span><span class="sxs-lookup"><span data-stu-id="97c69-110">Data type</span></span> | <span data-ttu-id="97c69-111">説明</span><span class="sxs-lookup"><span data-stu-id="97c69-111">Description</span></span> |
|------------|-------------|-------------|
| `IP` | <span data-ttu-id="97c69-112">string</span><span class="sxs-lookup"><span data-stu-id="97c69-112">string</span></span> | <span data-ttu-id="97c69-113">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="97c69-113">IP address</span></span>  |
| `DeviceId` | <span data-ttu-id="97c69-114">string</span><span class="sxs-lookup"><span data-stu-id="97c69-114">string</span></span> | <span data-ttu-id="97c69-115">サービス内のデバイスの一意識別子</span><span class="sxs-lookup"><span data-stu-id="97c69-115">Unique identifier for the device in the service</span></span> |


## <a name="syntax"></a><span data-ttu-id="97c69-116">構文</span><span class="sxs-lookup"><span data-stu-id="97c69-116">Syntax</span></span>

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a><span data-ttu-id="97c69-117">引数</span><span class="sxs-lookup"><span data-stu-id="97c69-117">Arguments</span></span>

<span data-ttu-id="97c69-118">この関数はクエリの一部として呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="97c69-118">This function is invoked as part of a query.</span></span>

- <span data-ttu-id="97c69-119">**x**- 最初のパラメーターは、通常、クエリ内の列です。</span><span class="sxs-lookup"><span data-stu-id="97c69-119">**x**—The first parameter is typically already a column in the query.</span></span> <span data-ttu-id="97c69-120">この場合は、割り当てられているデバイスの一覧を表示する IP アドレスという名前の列 `IP` です。</span><span class="sxs-lookup"><span data-stu-id="97c69-120">In this case, it is the column named `IP`, the IP address for which you want to see a list of devices that have been assigned to it.</span></span> <span data-ttu-id="97c69-121">ローカル IP アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="97c69-121">It should be a local IP address.</span></span> <span data-ttu-id="97c69-122">外部 IP アドレスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97c69-122">External IP addresses are not supported.</span></span>
- <span data-ttu-id="97c69-123">**y**- 2 番目の省略可能なパラメーターは、 特定の時刻から最新の割り当てられたデバイスを取得するように関数 `Timestamp` に指示するパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="97c69-123">**y**—A second optional parameter is the `Timestamp`, which instructs the function to obtain the most recent assigned devices from a specific time.</span></span> <span data-ttu-id="97c69-124">指定しない場合、関数は使用可能な最新のレコードを返します。</span><span class="sxs-lookup"><span data-stu-id="97c69-124">If not specified, the function returns the latest available records.</span></span>

## <a name="example"></a><span data-ttu-id="97c69-125">例</span><span class="sxs-lookup"><span data-stu-id="97c69-125">Example</span></span>


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a><span data-ttu-id="97c69-126">特定の IP アドレスが割り当てられている最新のデバイスを取得する</span><span class="sxs-lookup"><span data-stu-id="97c69-126">Get the latest devices that have been assigned specific IP addresses</span></span>

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a><span data-ttu-id="97c69-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="97c69-127">Related topics</span></span>
- [<span data-ttu-id="97c69-128">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="97c69-128">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="97c69-129">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="97c69-129">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="97c69-130">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="97c69-130">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
