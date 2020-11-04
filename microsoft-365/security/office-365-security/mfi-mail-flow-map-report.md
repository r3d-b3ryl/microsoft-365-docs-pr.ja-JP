---
title: メール フローのマップ
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローのダッシュボードにあるメールフローマップを使用して、コネクタ経由のメールフローと、コネクタを使用せずに組織との間で送受信されるメールフローを視覚的に追跡する方法を学習できます。
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877767"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="54074-103">セキュリティ & コンプライアンスセンターのメールフローマップ</span><span class="sxs-lookup"><span data-stu-id="54074-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="54074-104">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の [メールフローダッシュボード](mail-flow-insights-v2.md)の **メールフローマップ** は、組織内のメールフローについての洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="54074-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="54074-105">この情報を使用すると、パターンを学習し、異常を特定し、発生した問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="54074-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのメールフローマップウィジェット](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="54074-107">既定では、このウィジェットは、前の日のメールフローパターンを、 *Sankey* 図と呼ばれるグラフに表示します。</span><span class="sxs-lookup"><span data-stu-id="54074-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="54074-108">左向き矢印←および→右矢印を使用して、 ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) さまざまな日からの情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="54074-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="54074-109">それぞれの異なる色は、異なる受信コネクタまたは送信コネクタ経由のメールフローを表します (またはコネクタを使用しない)。</span><span class="sxs-lookup"><span data-stu-id="54074-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="54074-110">特定の色の上にカーソルを置くと、そのコネクタの種類に応じたメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="54074-111">メールフローマップのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="54074-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="54074-112">**メールフローマップ** ウィジェットをクリックすると、 **メールフローマップ** レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="54074-113">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="54074-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="54074-114">**データの表示: 概要** : これは基本的に、ウィジェットの大きな表示です。</span><span class="sxs-lookup"><span data-stu-id="54074-114">**Show data for: Overview** : This is basically a larger view of the widget.</span></span> <span data-ttu-id="54074-115">特定の色の上にカーソルを置くと、そのコネクタの種類に応じたメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![メールフローマップレポートの概要ビュー](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="54074-117">**データの表示: 詳細** : このビューには、コネクタと送信先ドメインの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-117">**Show data for: Detail** : This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="54074-118">上位の送信者と受信者のドメインが一覧表示され、残りは **他のユーザー** に配置されます。</span><span class="sxs-lookup"><span data-stu-id="54074-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="54074-119">特定の色とセクションの上にカーソルを移動すると、メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![メールフローマップレポートの詳細表示](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="54074-121">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日** を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54074-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="54074-122">特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54074-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="54074-123">関連する洞察は、使用可能な場合はメールフローマップの下に表示されます (たとえば、[ [可能なメールループ](mfi-mail-loop-insight.md)の状況を修正する] など)。</span><span class="sxs-lookup"><span data-stu-id="54074-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="54074-124">メールフローマップの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="54074-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="54074-125">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="54074-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="54074-126">**Date**</span></span>
- <span data-ttu-id="54074-127">**カテゴリ**</span><span class="sxs-lookup"><span data-stu-id="54074-127">**Category**</span></span>
- <span data-ttu-id="54074-128">**コネクタ/サードパーティのサービスプロバイダー**</span><span class="sxs-lookup"><span data-stu-id="54074-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="54074-129">**送信者/受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="54074-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="54074-130">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="54074-130">**Message count**</span></span>

<span data-ttu-id="54074-131">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日** を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="54074-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="54074-132">行を選択すると、同様の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="54074-132">If you select a row, similar details are shown in a flyout:</span></span>

![メールフローマップの詳細表の詳細ポップアップ](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="54074-134">特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54074-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="54074-135">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54074-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="54074-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="54074-136">See also</span></span>

<span data-ttu-id="54074-137">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54074-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
