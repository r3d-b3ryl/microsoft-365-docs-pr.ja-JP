---
title: メール フロー ダッシュボードの承認済みでないドメイン レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで承認されていないドメイン レポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミス組織からのメッセージを監視する方法を学習できます。
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826943"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="788ec-103">セキュリティ コンプライアンス センターの承認済みでない& レポート</span><span class="sxs-lookup"><span data-stu-id="788ec-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="788ec-104">セキュリティ & コンプライアンス **センターのメール** フロー ダッシュボード [に表示される [承認](mail-flow-insights-v2.md) 済みでないドメイン] レポートには、送信者のドメインが Microsoft 365 組織の承認済みドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="788ec-105">Microsoft 365 がこれらのメッセージの意図を悪意のあるものに証明するためのデータがある場合、Microsoft 365 によってこれらのメッセージが調整される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="788ec-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="788ec-106">そのため、何が起こったかを把理解して問題を解決するのが重要です。</span><span class="sxs-lookup"><span data-stu-id="788ec-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードで承認されていないドメイン ウィジ&ジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="788ec-108">承認されていないドメイン レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="788ec-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="788ec-109">[承認されていないドメイン] **ウィジェットの** グラフをクリックすると、承認されていない **ドメイン レポートに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="788ec-110">既定では、影響を受けるコネクタすべてのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="788ec-111">[データの **表示] をクリック**すると、ドロップダウンから特定のコネクタを選択できます。</span><span class="sxs-lookup"><span data-stu-id="788ec-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="788ec-112">グラフ内のデータ ポイント (日) にポイントすると、コネクタのメッセージの合計数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

!["承認されていないドメイン" レポートのレポート ビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="788ec-114">承認されていないドメイン レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="788ec-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="788ec-115">レポート ビューで **詳細テーブルの表示** をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="788ec-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="788ec-116">**Date**</span></span>
- <span data-ttu-id="788ec-117">**受信コネクタの名前**</span><span class="sxs-lookup"><span data-stu-id="788ec-117">**Inbound connector name**</span></span>
- <span data-ttu-id="788ec-118">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="788ec-118">**Sender domain**</span></span>
- <span data-ttu-id="788ec-119">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="788ec-119">**Message count**</span></span>
- <span data-ttu-id="788ec-120">**サンプル メッセージ**: 影響を受けつメッセージのサンプルのメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="788ec-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="788ec-121">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="788ec-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="788ec-122">特定の日付範囲のレポートを 1 名以上の受信者にメールで送信するには、[ **ダウンロードを要求] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="788ec-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="788ec-123">表で行を選択すると、以下の情報を含むポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="788ec-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="788ec-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="788ec-124">**Date**</span></span>
- <span data-ttu-id="788ec-125">**受信コネクタの名前**</span><span class="sxs-lookup"><span data-stu-id="788ec-125">**Inbound connector name**</span></span>
- <span data-ttu-id="788ec-126">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="788ec-126">**Sender domain**</span></span>
- <span data-ttu-id="788ec-127">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="788ec-127">**Message count**</span></span>
- <span data-ttu-id="788ec-128">**サンプル メッセージ**: [サンプル メッセージの **表示] をクリック** すると、影響 [を受けつ](message-trace-scc.md) つサンプル メッセージのメッセージトレース結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="788ec-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![[承認されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="788ec-130">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="788ec-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="788ec-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="788ec-131">Related topics</span></span>

<span data-ttu-id="788ec-132">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="788ec-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
