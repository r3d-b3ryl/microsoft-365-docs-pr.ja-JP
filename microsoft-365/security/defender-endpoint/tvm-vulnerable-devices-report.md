---
title: 脆弱なデバイス レポート - 脅威と脆弱性の管理
description: 脆弱なデバイスの傾向と現在の統計情報を示すレポート。 目標は、デバイスの露出の呼吸と範囲を理解する目的です。
keywords: Microsoft Defender for Endpoint-tvm の脆弱なデバイス、Microsoft Defender for Endpoint、tvm、脅威& 脆弱性の暴露を減らす、脅威と脆弱性を軽減する、セキュリティ構成を監視する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245482"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="a5c1c-105">脆弱なデバイス レポート - 脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="a5c1c-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5c1c-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a5c1c-106">**Applies to:**</span></span>

- [<span data-ttu-id="a5c1c-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5c1c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a5c1c-108">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="a5c1c-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a5c1c-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5c1c-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a5c1c-110">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="a5c1c-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5c1c-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a5c1c-112">レポートには、脆弱なデバイスの傾向と現在の統計を含むグラフと棒グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="a5c1c-113">目標は、デバイスの露出の呼吸と範囲を理解する目的です。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="a5c1c-114">[脆弱なデバイスのレポート] Microsoft Defender セキュリティ センターにアクセスして、>**レポートにアクセスします。**</span><span class="sxs-lookup"><span data-stu-id="a5c1c-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="a5c1c-115">次の 2 つの列があります。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-115">There are two columns:</span></span>

- <span data-ttu-id="a5c1c-116">傾向 (時間の流れる)。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-116">Trends (over time).</span></span> <span data-ttu-id="a5c1c-117">過去 30 日間、3 か月、6 か月、またはカスタムの日付範囲を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="a5c1c-118">今日 (現在の情報)</span><span class="sxs-lookup"><span data-stu-id="a5c1c-118">Today (current information)</span></span>

<span data-ttu-id="a5c1c-119">**フィルター**: 脆弱性の重大度レベル、悪用の可用性、脆弱性の年齢、オペレーティング システム プラットフォーム、Windows 10 バージョン、またはデバイス グループでデータをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="a5c1c-120">**ドリルダウン:** さらに詳しい分析情報がある場合は、関連する棒グラフを選択して、[デバイス インベントリ] ページにフィルター処理されたデバイスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="a5c1c-121">そこからリストをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="a5c1c-122">重大度レベルのグラフ</span><span class="sxs-lookup"><span data-stu-id="a5c1c-122">Severity level graphs</span></span>

<span data-ttu-id="a5c1c-123">各デバイスは、そのデバイスで見つかった最も重大な脆弱性に従って 1 回だけカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![現在のデバイスの脆弱性の重大度レベルの 1 つのグラフと、時間の流中のレベルを示す 1 つのグラフ。](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="a5c1c-125">可用性グラフの活用</span><span class="sxs-lookup"><span data-stu-id="a5c1c-125">Exploit availability graphs</span></span>

<span data-ttu-id="a5c1c-126">各デバイスは、既知の悪用の最高レベルに基づいて 1 回だけカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![現在のデバイスの利用可能性のグラフと、時間の流れによる可用性を示すグラフが 1 つ表示されます。](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="a5c1c-128">脆弱性の年齢グラフ</span><span class="sxs-lookup"><span data-stu-id="a5c1c-128">Vulnerability age graphs</span></span>

<span data-ttu-id="a5c1c-129">各デバイスは、最も古い脆弱性公開日の下で 1 回だけカウントされます。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="a5c1c-130">古い脆弱性は悪用される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![現在のデバイスの脆弱性の年齢のグラフと、時間の経時を示す 1 つのグラフ。](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="a5c1c-132">オペレーティング システム プラットフォームグラフによる脆弱なデバイス</span><span class="sxs-lookup"><span data-stu-id="a5c1c-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="a5c1c-133">ソフトウェアの脆弱性により公開される各オペレーティング システム上のデバイスの数。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![オペレーティング システム プラットフォーム別の現在の脆弱なデバイスの 1 つのグラフと、OS プラットフォームによる脆弱なデバイスの時間の経時を示す 1 つのグラフ。](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="a5c1c-135">バージョン グラフによるWindows 10デバイス</span><span class="sxs-lookup"><span data-stu-id="a5c1c-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="a5c1c-136">脆弱なアプリケーションまたは OS Windows 10される各バージョンのデバイスの数。</span><span class="sxs-lookup"><span data-stu-id="a5c1c-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![現在の脆弱なデバイスのバージョン別の 1 つのグラフWindows 10、1 つのグラフは、Windows 10バージョンで脆弱なデバイスを示します。](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="a5c1c-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5c1c-138">Related topics</span></span>

- [<span data-ttu-id="a5c1c-139">脅威と脆弱性の管理概要</span><span class="sxs-lookup"><span data-stu-id="a5c1c-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a5c1c-140">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="a5c1c-140">Security recommendations</span></span>](tvm-security-recommendation.md)
