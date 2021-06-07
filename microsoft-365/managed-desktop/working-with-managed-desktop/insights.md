---
title: 分析情報を操作する
description: サイトで利用できる分析情報のMicrosoft マネージド デスクトップ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ba91a33da9f4d2187938c27398d5ef7c1cacebcd
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739823"
---
# <a name="work-with-insights"></a><span data-ttu-id="55928-104">分析情報を操作する</span><span class="sxs-lookup"><span data-stu-id="55928-104">Work with insights</span></span>

<span data-ttu-id="55928-105">Microsoft マネージド デスクトップには、テナントの IT 管理者がデバイスの人口のさまざまな側面を理解するために使用できるダッシュボードが多数提供されています。</span><span class="sxs-lookup"><span data-stu-id="55928-105">Microsoft Managed Desktop provides a number of dashboards that IT admins in your tenant can use to understand various aspects of the population of devices.</span></span> <span data-ttu-id="55928-106">これらを直接アクセスするには、管理[センターのMicrosoft 365します](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)。</span><span class="sxs-lookup"><span data-stu-id="55928-106">You access these directly, in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span>

<span data-ttu-id="55928-107">これらのダッシュボードを使用すると、次のような質問に対する回答を確認できます。</span><span class="sxs-lookup"><span data-stu-id="55928-107">With these dashboards you can find the answers to questions like these:</span></span>

- <span data-ttu-id="55928-108">アクティブなデバイスの数と、最後に使用されたデバイスの数。</span><span class="sxs-lookup"><span data-stu-id="55928-108">How many devices are active and when were they last used?</span></span>
- <span data-ttu-id="55928-109">どのアプリが最も使用され、どの時間に使用されますか?</span><span class="sxs-lookup"><span data-stu-id="55928-109">Which apps are most used and during which times?</span></span>
- <span data-ttu-id="55928-110">クラッシュしたり、たくさんぶら下げてトラブルを引き起こしているアプリは何ですか?</span><span class="sxs-lookup"><span data-stu-id="55928-110">Which apps are causing trouble by crashing or hanging a lot?</span></span>
- <span data-ttu-id="55928-111">このような問題Microsoft マネージド デスクトップを軽減または解決する方法</span><span class="sxs-lookup"><span data-stu-id="55928-111">How is Microsoft Managed Desktop Operations mitigating or resolving such problems?</span></span>
- <span data-ttu-id="55928-112">どのアプリが最も多くのエネルギーを消費していますか?</span><span class="sxs-lookup"><span data-stu-id="55928-112">Which apps are consuming the most energy?</span></span>
- <span data-ttu-id="55928-113">デバイスの予測バッテリ寿命は何ですか?</span><span class="sxs-lookup"><span data-stu-id="55928-113">What's the predicted battery life my devices?</span></span>
- <span data-ttu-id="55928-114">デバイスのセキュリティ更新プログラムの現在の状態は何ですか?</span><span class="sxs-lookup"><span data-stu-id="55928-114">What is the current status of security updates on devices?</span></span>
- <span data-ttu-id="55928-115">最新のセキュリティ更新プログラムでデバイスの 95% が最新の状態を取得するにはどのくらいの時間が必要でしたか?</span><span class="sxs-lookup"><span data-stu-id="55928-115">How long did it take for 95% of the devices to get current with the latest security update?</span></span>


<span data-ttu-id="55928-116">これらのビューにアクセスするには、Microsoft エンドポイント マネージャーの [Microsoft マネージド デスクトップ] タブに移動し、[レポート] 領域で[詳細の表示]**を選択** します。 [](https://endpoint.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="55928-116">To access these views from the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), navigate to the Microsoft Managed Desktop tab on the homepage and select **View details** in the **Reporting** area:</span></span>


![左下の [レポート] 領域と [詳細の表示] リンクを含む管理センターのメイン ページ](../../media/insights-main.png)


## <a name="usage-insights"></a><span data-ttu-id="55928-118">使用状況の分析情報</span><span class="sxs-lookup"><span data-stu-id="55928-118">Usage insights</span></span>
<span data-ttu-id="55928-119">このビューには、デバイスの使用状況Microsoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="55928-119">This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="55928-120">使用状況データを表示するには、[使用状況] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="55928-120">To view usage data, select the **Usage** tab.</span></span>

<span data-ttu-id="55928-121">使用状況の分析情報 [について詳しくは、次のページをご覧ください](usage-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="55928-121">Learn more about [usage insights](usage-insights.md).</span></span>

## <a name="reliability-insights"></a><span data-ttu-id="55928-122">信頼性の分析情報</span><span class="sxs-lookup"><span data-stu-id="55928-122">Reliability insights</span></span>
<span data-ttu-id="55928-123">このビューには、管理対象デバイスの正常性の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55928-123">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="55928-124">信頼性データを表示するには、[信頼性] **タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="55928-124">To view reliability data, select the **Reliability** tab.</span></span>

<span data-ttu-id="55928-125">信頼性に関する [分析情報について詳しくは、次のページを参照してください](reliability-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="55928-125">Learn more about [reliability insights](reliability-insights.md).</span></span>

## <a name="battery-insights"></a><span data-ttu-id="55928-126">バッテリーの分析情報</span><span class="sxs-lookup"><span data-stu-id="55928-126">Battery insights</span></span>
<span data-ttu-id="55928-127">このビューには、環境内のデバイスのアプリのエネルギー消費量と、投影されるバッテリー寿命に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55928-127">This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span> <span data-ttu-id="55928-128">この情報を表示するには、[バッテリー] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="55928-128">To view this information, select the **Battery** tab.</span></span>

<span data-ttu-id="55928-129">バッテリーの分析情報 [について詳しくは、次のページを参照してください](battery-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="55928-129">Learn more about [Battery insights](battery-insights.md).</span></span>

## <a name="windows-security-update-insights"></a><span data-ttu-id="55928-130">Windows セキュリティ更新プログラムの分析情報</span><span class="sxs-lookup"><span data-stu-id="55928-130">Windows security update insights</span></span>
<span data-ttu-id="55928-131">このビューには、デバイスのセキュリティ更新プログラムの状態に関するMicrosoft マネージド デスクトップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="55928-131">This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="55928-132">この情報を表示するには、[セキュリティ更新プログラム] **Windowsを選択** します。</span><span class="sxs-lookup"><span data-stu-id="55928-132">To view this information, select the **Windows security updates** tab.</span></span>

<span data-ttu-id="55928-133">セキュリティ更新プログラム [の分析情報について詳しくは、次のページを参照してください](security-update-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="55928-133">Learn more about [Security update insights](security-update-insights.md).</span></span>
