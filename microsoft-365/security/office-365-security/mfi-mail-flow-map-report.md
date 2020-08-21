---
title: メール フローのマップ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用する方法を学習し、コネクタを使用することなく組織との間でメールがどのようにやり取りされるかを視覚化して追跡する方法を学習できます。
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827003"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="26451-103">セキュリティ コンプライアンス センターの& フロー マップ</span><span class="sxs-lookup"><span data-stu-id="26451-103">Mail flow map in the Security & Compliance Center</span></span>

<span data-ttu-id="26451-104">セキュリティ & **コンプライアンス センター** のメール [フロー ダッシュボードの](mail-flow-insights-v2.md) メール フロー マップは、組織を介してメールがどのようにフローするのかを分析する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="26451-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="26451-105">この情報を使用して、パターンの学習、と語の特定、問題の発生などを修正できます。</span><span class="sxs-lookup"><span data-stu-id="26451-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![セキュリティ グループ ポリシーのメール フロー ダッシュボードのメール フロー マップ ウィジ& ウィジェット](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="26451-107">既定では、グラフの前の 1 日のメール フロー パターンが *、Sankey 図として表示* されます。</span><span class="sxs-lookup"><span data-stu-id="26451-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="26451-108">左方向キーと右矢印 ![ を使用して ](../../media/scc-left-arrow.png) ![ 、数日 ](../../media/scc-right-arrow.png) が異なる情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="26451-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="26451-109">それぞれの色は、別の受信コネクタまたは送信コネクタ経由のメール フローを表します (またはコネクタを使用しない)。</span><span class="sxs-lookup"><span data-stu-id="26451-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="26451-110">特定の色に上書きを設定すると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="26451-111">メール フロー マップのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="26451-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="26451-112">メール フロー マップ **ウィジェ** ットをクリックすると、メール フロー **マップ レポートが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="26451-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="26451-113">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="26451-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="26451-114">**[概要] : 基本的**にはウィジェットの大規模なビューです。</span><span class="sxs-lookup"><span data-stu-id="26451-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="26451-115">特定の色に上書きを設定すると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![メール フロー マップ レポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="26451-117">**データの表示: 詳細**: このビューには、コネクタと宛先ドメインの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="26451-118">一覧に上位の送信者と受信者のドメインがリストされ、残りのドメインは他のユーザー **に配置されます**。</span><span class="sxs-lookup"><span data-stu-id="26451-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="26451-119">特定のカラーとセクションを上に重かけた場合、メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![メール フロー マップ レポートの詳細ビュー](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="26451-121">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="26451-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="26451-122">特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="26451-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="26451-123">関連分析情報は、利用できる場合にメール フロー マップの上に表示されます (例、メール ループの [可能性がある分析情報の修正](mfi-mail-loop-insight.md))。</span><span class="sxs-lookup"><span data-stu-id="26451-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="26451-124">メール フロー マップの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="26451-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="26451-125">レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="26451-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="26451-126">**Date**</span></span>
- <span data-ttu-id="26451-127">**分類**</span><span class="sxs-lookup"><span data-stu-id="26451-127">**Category**</span></span>
- <span data-ttu-id="26451-128">**コネクタ / サードパーティのサービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="26451-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="26451-129">**送信者/受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="26451-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="26451-130">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="26451-130">**Message count**</span></span>

<span data-ttu-id="26451-131">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="26451-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="26451-132">行を選択すると、同様の詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="26451-132">If you select a row, similar details are shown in a flyout:</span></span>

![メール フロー マップの詳細テーブルの詳細ポップアップ](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="26451-134">特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="26451-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="26451-135">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="26451-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="26451-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="26451-136">See also</span></span>

<span data-ttu-id="26451-137">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="26451-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
