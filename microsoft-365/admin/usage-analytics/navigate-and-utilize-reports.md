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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 286fcf0b-ffc7-4593-8073-d7a4a5dd2b45
description: ナビゲーションタブとフィルターを使用してレポートを表示する方法について説明します。
ms.openlocfilehash: 3abbd2362cb6216d5dd561c7792fa41588daac66
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42355108"
---
# <a name="navigate-and-utilize-the-reports-in-microsoft-365-usage-analytics"></a><span data-ttu-id="20d36-103">Microsoft 365 利用状況分析でレポート間を移動して活用する</span><span class="sxs-lookup"><span data-stu-id="20d36-103">Navigate and utilize the reports in Microsoft 365 usage analytics</span></span>

<span data-ttu-id="20d36-104">このダッシュボードでは、利用状況と導入状況の主なメトリックを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="20d36-104">The dashboard provides you with a quick overview of the main usage and adoption metrics.</span></span> <span data-ttu-id="20d36-105">最上位の測定基準を選択することにより、詳細と洞察を提供するレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="20d36-105">By selecting the top-level metrics, you can access reports that provide more details and insights.</span></span> <span data-ttu-id="20d36-106">各 [レポート] タブには、組織での使用状況と導入の側面に固有のデータビジュアライゼーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20d36-106">Each report tab contains data visualizations specific to an aspect of usage and adoption for your organization.</span></span> <span data-ttu-id="20d36-107">収集されたデータについては各レポートのタイトルで説明されており、表示している [レポート] タブの視覚エフェクトに関する詳細を含むタイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d36-107">The data collected is explained in the title of each report and a tile appears that contains further information about the visualizations on the report tab that you are viewing.</span></span>

<span data-ttu-id="20d36-108">初めに、レポートのヒントをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="20d36-108">To get started with your reports, here are some tips:</span></span>

- <span data-ttu-id="20d36-109">各トップレベルレポートに移動するには、左側のナビゲーションタブ、または**エグゼクティブサマリー**ページの関連する指標を使用します。</span><span class="sxs-lookup"><span data-stu-id="20d36-109">Use the navigation tabs on the left or on a related metric on the **Executive Summary** page to navigate to each top-level report.</span></span>

    ![左側のナビゲーションタブを表示します。](../../media/navigate-usage-analytics1.png)

- <span data-ttu-id="20d36-111">各トップレベルレポートの上部にあるナビゲーションタブを使用して、そのレベルのさまざまなレポートに移動します。</span><span class="sxs-lookup"><span data-stu-id="20d36-111">Use the navigation tabs at the top of each top-level report to navigate to different reports within that level.</span></span>

    ![各レポートの一番上にあるナビゲーションタブを表示します。](../../media/navigate-usage-analytics2.png)

- <span data-ttu-id="20d36-113">多くのレポートには、表示する product、AAD 属性、またはアクティビティにフィルターを適用できるスライサーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20d36-113">Many reports contain a slicer where you can filter on the product, AAD attribute, or activity that you want to view.</span></span> <span data-ttu-id="20d36-114">単一選択と複数選択のどちらも可能です。</span><span class="sxs-lookup"><span data-stu-id="20d36-114">These can be either single-select or multi-select.</span></span>

    ![スライサーの表示](../../media/navigate-usage-analytics3.png)

    ![スライサーの表示](../../media/navigate-usage-analytics4.png)


- <span data-ttu-id="20d36-117">データ ポイントにマウス ポインターを移動すると、詳細な情報の吹き出しが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20d36-117">Hover over data points to view a callout that contains details.</span></span>

    ![ホバーの例を表示します。](../../media/navigate-usage-analytics6.png)

<span data-ttu-id="20d36-119">テンプレートアプリをインスタンス化したユーザーは、必要に応じてレポートをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="20d36-119">The user who has instantiated the template app will have the ability to customize the report to their needs.</span></span> <span data-ttu-id="20d36-120">テンプレートアプリをカスタマイズするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="20d36-120">To customize the template app:</span></span>

- <span data-ttu-id="20d36-121">レポートの上部にある [**レポートの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20d36-121">Select **Edit report** at the top of the report.</span></span>

    ![編集レポートを表示します。](../../media/navigate-usage-analytics7.png)


- <span data-ttu-id="20d36-123">基になる[データセット](usage-analytics-data-model.md)を利用し、独自のビジュアルを作成します。</span><span class="sxs-lookup"><span data-stu-id="20d36-123">Create your own visuals by using the underlying [datasets](usage-analytics-data-model.md).</span></span>

- <span data-ttu-id="20d36-124">PowerBI Desktop を利用し、独自のデータ ソースを導入します。</span><span class="sxs-lookup"><span data-stu-id="20d36-124">Use PowerBI Desktop to bring in your own data sources.</span></span>

<span data-ttu-id="20d36-125">レポートを共有するには、[共有] ボタンを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="20d36-125">To share your reports, just select the share button</span></span> ![Power BI Share icon](../../media/dbb0569d-2013-4f9d-ab9d-d01b09631b92.png) <span data-ttu-id="20d36-127">ページの上部にあります。</span><span class="sxs-lookup"><span data-stu-id="20d36-127">at the top of the page.</span></span>

<span data-ttu-id="20d36-128">レポートをカスタマイズする方法については、「 [Microsoft 365 usage analytics でレポートをカスタマイズ](customize-reports.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d36-128">To learn how to customize the reports, see [Customizing the reports in Microsoft 365 usage analytics](customize-reports.md).</span></span>

<span data-ttu-id="20d36-129">Power BI のヘルプドキュメントで多くの他の情報を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="20d36-129">You can find lots of additional information in the Power BI help documentation:</span></span>

- [<span data-ttu-id="20d36-130">Power BI の基本的な概念</span><span class="sxs-lookup"><span data-stu-id="20d36-130">Power BI basic concepts</span></span>](https://docs.microsoft.com/power-bi/service-basic-concepts)

    <span data-ttu-id="20d36-131">ダッシュボード、データセット、レポート、およびその他の Power BI の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="20d36-131">Learn about dashboard, datasets, reports, and other Power BI concepts.</span></span>

- [<span data-ttu-id="20d36-132">Power BI の概要</span><span class="sxs-lookup"><span data-stu-id="20d36-132">Get started with Power BI</span></span>](https://docs.microsoft.com/power-bi/service-get-started?wt.mc_id=O365_Reports_PBI_contentpack)

    <span data-ttu-id="20d36-p104">Power BI の基本的な機能について説明します。PowerBI Desktop の使用方法へのリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20d36-p104">Learn the basic functionality in Power BI. Find links to how to use Power BI Desktop.</span></span>

- [<span data-ttu-id="20d36-135">ダッシュボードやレポートを共有する</span><span class="sxs-lookup"><span data-stu-id="20d36-135">Share dashboards and reports</span></span>](https://docs.microsoft.com/power-bi/service-share-dashboards)

    <span data-ttu-id="20d36-136">仕事仲間や組織外の人とレポートを共有する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20d36-136">Learn how to share reports with your colleagues or people outside your organization.</span></span> <span data-ttu-id="20d36-137">レポートまたはレポートのフィルター処理されたバージョンを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="20d36-137">You can also share the report or a filtered version of the report.</span></span>
