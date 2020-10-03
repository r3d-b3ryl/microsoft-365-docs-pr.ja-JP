---
title: 分析情報を操作する
description: Microsoft マネージドデスクトップで利用可能な insights の概要
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ba91a33da9f4d2187938c27398d5ef7c1cacebcd
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350836"
---
# <a name="work-with-insights"></a><span data-ttu-id="d148a-104">分析情報を操作する</span><span class="sxs-lookup"><span data-stu-id="d148a-104">Work with insights</span></span>

<span data-ttu-id="d148a-105">Microsoft マネージドデスクトップには、テナントの管理者が、デバイスの作成に関するさまざまな側面を理解するために使用できる多数のダッシュボードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d148a-105">Microsoft Managed Desktop provides a number of dashboards that IT admins in your tenant can use to understand various aspects of the population of devices.</span></span> <span data-ttu-id="d148a-106">これらには、 [Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop)で直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="d148a-106">You access these directly, in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span>

<span data-ttu-id="d148a-107">これらのダッシュボードを使用すると、次のような質問に対する回答を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d148a-107">With these dashboards you can find the answers to questions like these:</span></span>

- <span data-ttu-id="d148a-108">アクティブなデバイスの数と、最後に使用された時間。</span><span class="sxs-lookup"><span data-stu-id="d148a-108">How many devices are active and when were they last used?</span></span>
- <span data-ttu-id="d148a-109">最もよく使用されているアプリと、その時間。</span><span class="sxs-lookup"><span data-stu-id="d148a-109">Which apps are most used and during which times?</span></span>
- <span data-ttu-id="d148a-110">クラッシュまたはハングによって問題が発生しているのはどのアプリか。</span><span class="sxs-lookup"><span data-stu-id="d148a-110">Which apps are causing trouble by crashing or hanging a lot?</span></span>
- <span data-ttu-id="d148a-111">Microsoft マネージドデスクトップの運用において、このような問題を軽減または解決する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="d148a-111">How is Microsoft Managed Desktop Operations mitigating or resolving such problems?</span></span>
- <span data-ttu-id="d148a-112">どのアプリが最も多くの電力を消費していますか?</span><span class="sxs-lookup"><span data-stu-id="d148a-112">Which apps are consuming the most energy?</span></span>
- <span data-ttu-id="d148a-113">予想されるバッテリの寿命はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="d148a-113">What's the predicted battery life my devices?</span></span>
- <span data-ttu-id="d148a-114">デバイス上のセキュリティ更新プログラムの現在の状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="d148a-114">What is the current status of security updates on devices?</span></span>
- <span data-ttu-id="d148a-115">デバイスの95% が最新のセキュリティ更新プログラムで最新の状態になるまでにどのくらいの時間がかかりましたか?</span><span class="sxs-lookup"><span data-stu-id="d148a-115">How long did it take for 95% of the devices to get current with the latest security update?</span></span>


<span data-ttu-id="d148a-116">[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)からこれらのビューにアクセスするには、ホームページの [Microsoft Managed Desktop] タブに移動して、[**レポート**] 領域の [**詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d148a-116">To access these views from the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), navigate to the Microsoft Managed Desktop tab on the homepage and select **View details** in the **Reporting** area:</span></span>


![レポート領域が表示された管理センターメインページ、左下および詳細情報のリンク](../../media/insights-main.png)


## <a name="usage-insights"></a><span data-ttu-id="d148a-118">使用状況の分析情報</span><span class="sxs-lookup"><span data-stu-id="d148a-118">Usage insights</span></span>
<span data-ttu-id="d148a-119">このビューは、Microsoft マネージドデスクトップデバイスの使用指標を提供します。</span><span class="sxs-lookup"><span data-stu-id="d148a-119">This view provides usage metrics for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="d148a-120">利用状況データを表示するには、[ **利用状況** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d148a-120">To view usage data, select the **Usage** tab.</span></span>

<span data-ttu-id="d148a-121">[利用状況分析](usage-insights.md)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d148a-121">Learn more about [usage insights](usage-insights.md).</span></span>

## <a name="reliability-insights"></a><span data-ttu-id="d148a-122">信頼性の分析情報</span><span class="sxs-lookup"><span data-stu-id="d148a-122">Reliability insights</span></span>
<span data-ttu-id="d148a-123">このビューでは、管理対象デバイスの正常性の概要が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d148a-123">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="d148a-124">信頼性データを表示するには、[ **信頼性** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d148a-124">To view reliability data, select the **Reliability** tab.</span></span>

<span data-ttu-id="d148a-125">[信頼性の分析](reliability-insights.md)について説明します。</span><span class="sxs-lookup"><span data-stu-id="d148a-125">Learn more about [reliability insights](reliability-insights.md).</span></span>

## <a name="battery-insights"></a><span data-ttu-id="d148a-126">バッテリーの分析情報</span><span class="sxs-lookup"><span data-stu-id="d148a-126">Battery insights</span></span>
<span data-ttu-id="d148a-127">このビューには、環境内のデバイスの電力消費量と予想されるバッテリ寿命に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d148a-127">This view shows you information about the energy consumption of apps and projected battery life for devices in your environment.</span></span> <span data-ttu-id="d148a-128">この情報を表示するには、[ **バッテリ** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d148a-128">To view this information, select the **Battery** tab.</span></span>

<span data-ttu-id="d148a-129">[詳細につい](battery-insights.md)ては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d148a-129">Learn more about [Battery insights](battery-insights.md).</span></span>

## <a name="windows-security-update-insights"></a><span data-ttu-id="d148a-130">Windows セキュリティ更新プログラムの分析情報</span><span class="sxs-lookup"><span data-stu-id="d148a-130">Windows security update insights</span></span>
<span data-ttu-id="d148a-131">このビューには、Microsoft マネージドデスクトップデバイスのセキュリティ更新プログラムの状態に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d148a-131">This view shows you information about the status of security updates for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="d148a-132">この情報を表示するには、[ **Windows セキュリティの更新** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d148a-132">To view this information, select the **Windows security updates** tab.</span></span>

<span data-ttu-id="d148a-133">[セキュリティ更新プログラム](security-update-insights.md)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d148a-133">Learn more about [Security update insights](security-update-insights.md).</span></span>
