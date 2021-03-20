---
title: Microsoft 365 利用状況分析でレポート間を移動して活用する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 286fcf0b-ffc7-4593-8073-d7a4a5dd2b45
description: ナビゲーション タブとフィルターを使用してレポートを表示する方法について学習します。
ms.openlocfilehash: d3f080bdf2ec5544a0ef9d06139cad682962d57d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913912"
---
# <a name="navigate-and-utilize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="e578e-103">Microsoft 365 利用状況分析でレポート間を移動して活用する</span><span class="sxs-lookup"><span data-stu-id="e578e-103">Navigate and utilize the reports in Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e578e-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e578e-104">The admin center is changing.</span></span> <span data-ttu-id="e578e-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e578e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e578e-106">このダッシュボードでは、利用状況と導入状況の主なメトリックを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="e578e-106">The dashboard provides you with a quick overview of the main usage and adoption metrics.</span></span> <span data-ttu-id="e578e-107">トップ レベルの指標を選択すると、詳細と分析情報を提供するレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e578e-107">By selecting the top-level metrics, you can access reports that provide more details and insights.</span></span> <span data-ttu-id="e578e-108">各レポート タブには、組織の利用状況と導入の側面に固有のデータの視覚化が含まれる。</span><span class="sxs-lookup"><span data-stu-id="e578e-108">Each report tab contains data visualizations specific to an aspect of usage and adoption for your organization.</span></span> <span data-ttu-id="e578e-109">収集されたデータは、各レポートのタイトルで説明され、表示しているレポート タブの視覚化に関する詳細を含むタイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e578e-109">The data collected is explained in the title of each report and a tile appears that contains further information about the visualizations on the report tab that you are viewing.</span></span>

<span data-ttu-id="e578e-110">初めに、レポートのヒントをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="e578e-110">To get started with your reports, here are some tips:</span></span>

- <span data-ttu-id="e578e-111">左側のナビゲーション タブ、または [エグゼクティブの概要]ページの関連する指標のナビゲーション タブを使用して、各トップ レベル レポートに移動します。</span><span class="sxs-lookup"><span data-stu-id="e578e-111">Use the navigation tabs on the left or on a related metric on the **Executive Summary** page to navigate to each top-level report.</span></span>

    ![左側のナビゲーション タブを表示する](../../media/navigate-usage-analytics1.png)

- <span data-ttu-id="e578e-113">各トップ レベル レポートの上部にあるナビゲーション タブを使用して、そのレベル内の異なるレポートに移動します。</span><span class="sxs-lookup"><span data-stu-id="e578e-113">Use the navigation tabs at the top of each top-level report to navigate to different reports within that level.</span></span>

    ![各レポートの上部にナビゲーション タブを表示する](../../media/navigate-usage-analytics2.png)

- <span data-ttu-id="e578e-115">多くのレポートにはスライサーが含まれているので、表示する製品、AAD 属性、またはアクティビティをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e578e-115">Many reports contain a slicer where you can filter on the product, AAD attribute, or activity that you want to view.</span></span> <span data-ttu-id="e578e-116">これらは、単一選択または複数選択のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="e578e-116">These can be either single-select or multi-select.</span></span>

    ![スライサーを表示する](../../media/navigate-usage-analytics3.png)

    ![スライサーを表示する](../../media/navigate-usage-analytics4.png)


- <span data-ttu-id="e578e-119">データ ポイントにマウス ポインターを移動すると、詳細な情報の吹き出しが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e578e-119">Hover over data points to view a callout that contains details.</span></span>

    ![ホバーの例を表示する](../../media/navigate-usage-analytics6.png)

<span data-ttu-id="e578e-121">テンプレート アプリをインスタンス化したユーザーは、必要に応じてレポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e578e-121">The user who has instantiated the template app will have the ability to customize the report to their needs.</span></span> <span data-ttu-id="e578e-122">テンプレート アプリをカスタマイズするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e578e-122">To customize the template app:</span></span>

- <span data-ttu-id="e578e-123">レポート **の上部にある** [レポートの編集] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e578e-123">Select **Edit report** at the top of the report.</span></span>

    ![レポートの編集を表示する](../../media/navigate-usage-analytics7.png)


- <span data-ttu-id="e578e-125">基になる[データセット](usage-analytics-data-model.md)を利用し、独自のビジュアルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e578e-125">Create your own visuals by using the underlying [datasets](usage-analytics-data-model.md).</span></span>

- <span data-ttu-id="e578e-126">PowerBI Desktop を利用し、独自のデータ ソースを導入します。</span><span class="sxs-lookup"><span data-stu-id="e578e-126">Use PowerBI Desktop to bring in your own data sources.</span></span>

<span data-ttu-id="e578e-127">レポートを共有するには、[共有] ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e578e-127">To share your reports, just select the share button</span></span> ![Power BI Share icon](../../media/dbb0569d-2013-4f9d-ab9d-d01b09631b92.png) <span data-ttu-id="e578e-129">ページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e578e-129">at the top of the page.</span></span>

<span data-ttu-id="e578e-130">レポートをカスタマイズする方法については [、「Microsoft 365](customize-reports.md)利用状況分析でのレポートのカスタマイズ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e578e-130">To learn how to customize the reports, see [Customizing the reports in Microsoft 365 usage analytics](customize-reports.md).</span></span>

<span data-ttu-id="e578e-131">Power BI のヘルプドキュメントで多くの他の情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e578e-131">You can find lots of additional information in the Power BI help documentation:</span></span>

- [<span data-ttu-id="e578e-132">Power BI の基本的な概念</span><span class="sxs-lookup"><span data-stu-id="e578e-132">Power BI basic concepts</span></span>](/power-bi/service-basic-concepts)

    <span data-ttu-id="e578e-133">ダッシュボード、データセット、レポート、その他の Power BI の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="e578e-133">Learn about dashboard, datasets, reports, and other Power BI concepts.</span></span>

- [<span data-ttu-id="e578e-134">Power BI の概要</span><span class="sxs-lookup"><span data-stu-id="e578e-134">Get started with Power BI</span></span>](/power-bi/service-get-started?wt.mc_id=O365_Reports_PBI_contentpack)

    <span data-ttu-id="e578e-p105">Power BI の基本的な機能について説明します。PowerBI Desktop の使用方法へのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e578e-p105">Learn the basic functionality in Power BI. Find links to how to use Power BI Desktop.</span></span>

- [<span data-ttu-id="e578e-137">ダッシュボードやレポートを共有する</span><span class="sxs-lookup"><span data-stu-id="e578e-137">Share dashboards and reports</span></span>](/power-bi/service-share-dashboards)

    <span data-ttu-id="e578e-138">組織外の同僚やユーザーとレポートを共有する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="e578e-138">Learn how to share reports with your colleagues or people outside your organization.</span></span> <span data-ttu-id="e578e-139">レポートまたはフィルター処理されたバージョンのレポートを共有できます。</span><span class="sxs-lookup"><span data-stu-id="e578e-139">You can also share the report or a filtered version of the report.</span></span>