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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでメール フロー マップを使用して、コネクタを使用してコネクタを使用せずに組織と組織間のメール フローを視覚化および追跡する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206960"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="e6d3a-103">セキュリティ コンプライアンス センターのメール フロー &マップ</span><span class="sxs-lookup"><span data-stu-id="e6d3a-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6d3a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-104">**Applies to**</span></span>
- [<span data-ttu-id="e6d3a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e6d3a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e6d3a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="e6d3a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e6d3a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6d3a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e6d3a-108">セキュリティ **コンプライアンス センターの**[メール フロー [](https://protection.office.com) ] ダッシュボード&メール フロー マップは、組織を通じてメールがどのように流れるかについての洞察を提供します。 [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e6d3a-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="e6d3a-109">この情報を使用して、パターンの学習、異常の特定、発生した問題の修正を行います。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボードのメール フロー マップ &ウィジェット](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="e6d3a-111">既定では、ウィジェットには、サンキー図と呼ばれるグラフに、前の日のメール フロー *パターンが表示* されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="e6d3a-112">左矢印左矢印と右矢印右矢印を使用して、 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) 異なる日の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="e6d3a-113">各異なる色は、異なる受信コネクタまたは送信コネクタ (またはコネクタを使用しない) 上のメール フローを表します。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="e6d3a-114">特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="e6d3a-115">メール フロー マップのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="e6d3a-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="e6d3a-116">メール フロー マップ **ウィジェットをクリックすると** 、メール フロー マップ **レポートにアクセス** できます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="e6d3a-117">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e6d3a-118">**[データの表示: 概要**] : これは基本的にウィジェットの大きなビューです。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="e6d3a-119">特定の色にカーソルを合わせると、その種類のコネクタのメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![メール フロー マップ レポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="e6d3a-121">**データの表示: 詳細**: このビューには、コネクタと宛先ドメインに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="e6d3a-122">上位の送信者と受信者のドメインが一覧表示され、残りは [その他] に **設定されます**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="e6d3a-123">特定の色とセクションにカーソルを合わせると、メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![メール フロー マップ レポートの詳細ビュー](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="e6d3a-125">レポート ビューで **[フィルター]** をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6d3a-126">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e6d3a-127">関連する分析情報は、利用可能な場合はメール フロー マップの下に表示されます (たとえば、可能なメール ループの分析情報 [を修正する](mfi-mail-loop-insight.md))。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="e6d3a-128">メール フロー マップの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="e6d3a-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="e6d3a-129">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e6d3a-130">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-130">**Date**</span></span>
- <span data-ttu-id="e6d3a-131">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-131">**Category**</span></span>
- <span data-ttu-id="e6d3a-132">**コネクタ/サードパーティ のサービス プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="e6d3a-133">**送信者/受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="e6d3a-134">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="e6d3a-134">**Message count**</span></span>

<span data-ttu-id="e6d3a-135">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6d3a-136">行を選択すると、同様の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-136">If you select a row, similar details are shown in a flyout:</span></span>

![メール フロー マップの詳細テーブルからの詳細フライアウト](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="e6d3a-138">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e6d3a-139">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6d3a-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6d3a-140">See also</span></span>

<span data-ttu-id="e6d3a-141">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
