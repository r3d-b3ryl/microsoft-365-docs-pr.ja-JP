---
title: メール フローのマップ
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用したりコネクタを使用せずに組織とメールのフローを視覚化したり追跡したりする方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c07730f3abcec8905285cdfdf1579ffb71573ec1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029920"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="a1222-103">セキュリティ/コンプライアンス センター&フロー マップ</span><span class="sxs-lookup"><span data-stu-id="a1222-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a1222-104">セキュリティ **/コンプライアンス センター** の [](mail-flow-insights-v2.md)メール フロー ダッシュボード [](https://protection.office.com)のメール フロー マップ&、メールが組織を通過する方法に関する洞察が得られる。</span><span class="sxs-lookup"><span data-stu-id="a1222-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="a1222-105">この情報を使用して、パターンの学習、異常の特定、発生した問題の修正を行います。</span><span class="sxs-lookup"><span data-stu-id="a1222-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードのメール フロー &ウィジェット](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="a1222-107">既定では、ウィジェットはサンキー図と呼ばれるグラフに、前の日からのメール フロー *パターンを表示* します。</span><span class="sxs-lookup"><span data-stu-id="a1222-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="a1222-108">左矢印の左矢印と右矢印の右矢印を使用して、さまざまな日の情報 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a1222-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="a1222-109">それぞれの異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 上のメール フローを表します。</span><span class="sxs-lookup"><span data-stu-id="a1222-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="a1222-110">特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="a1222-111">メール フロー マップのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="a1222-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="a1222-112">メール フロー マップ **ウィジェットをクリック** すると、メール フロー **マップ レポートにアクセス** できます。</span><span class="sxs-lookup"><span data-stu-id="a1222-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="a1222-113">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1222-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a1222-114">**Show data for: Overview**: This is basically a larger view of the widget.</span><span class="sxs-lookup"><span data-stu-id="a1222-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="a1222-115">特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![メール フロー マップ レポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="a1222-117">**データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="a1222-118">上位の送信者と受信者のドメインが一覧表示され、残りは [その他] に **入れらます**。</span><span class="sxs-lookup"><span data-stu-id="a1222-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="a1222-119">特定の色とセクションにカーソルを合わせると、メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![メール フロー マップ レポートの詳細ビュー](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="a1222-121">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="a1222-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a1222-122">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1222-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a1222-123">関連する分析情報が使用可能な場合は、メール フロー マップの下に表示されます (たとえば、可能なメール ループの分析 [情報を修正します](mfi-mail-loop-insight.md))。</span><span class="sxs-lookup"><span data-stu-id="a1222-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="a1222-124">メール フロー マップの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="a1222-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="a1222-125">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a1222-126">**日付**</span><span class="sxs-lookup"><span data-stu-id="a1222-126">**Date**</span></span>
- <span data-ttu-id="a1222-127">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="a1222-127">**Category**</span></span>
- <span data-ttu-id="a1222-128">**コネクタ/サードパーティのサービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="a1222-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="a1222-129">**送信者/受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="a1222-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="a1222-130">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="a1222-130">**Message count**</span></span>

<span data-ttu-id="a1222-131">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="a1222-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a1222-132">行を選択すると、同様の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a1222-132">If you select a row, similar details are shown in a flyout:</span></span>

![メール フロー マップの詳細テーブルからの詳細フライアウト](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="a1222-134">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1222-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="a1222-135">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1222-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1222-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1222-136">See also</span></span>

<span data-ttu-id="a1222-137">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="a1222-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
