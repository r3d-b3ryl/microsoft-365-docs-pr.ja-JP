---
title: メール フロー ダッシュボードの非承諾ドメイン レポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで非承諾ドメイン レポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミス組織からのメッセージを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150822"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="8a9b0-103">セキュリティ/コンプライアンス センターの非& レポート</span><span class="sxs-lookup"><span data-stu-id="8a9b0-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8a9b0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-104">**Applies to**</span></span>
- [<span data-ttu-id="8a9b0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8a9b0-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="8a9b0-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="8a9b0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="8a9b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a9b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8a9b0-108">セキュリティ & コンプライアンス センターのメール[](mail-flow-insights-v2.md)フロー ダッシュボードの[](https://protection.office.com)[非承諾ドメイン] レポートには、送信者のドメインが Microsoft 365 組織の承認されたドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="8a9b0-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="8a9b0-109">これらのメッセージの意図が悪意のあるものであることを証明するデータがある場合、Microsoft 365 はこれらのメッセージを調整する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="8a9b0-110">そのため、何が起こっているかを理解し、問題を解決することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの&ドメイン ウィジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="8a9b0-112">[非承諾ドメイン] レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="8a9b0-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="8a9b0-113">非承諾ドメイン ウィジェットのグラフ **を** クリックすると、非承諾ドメイン レポート **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="8a9b0-114">既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="8a9b0-115">[データの **表示] をクリック** すると、ドロップダウンから特定のコネクタを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="8a9b0-116">グラフ内のデータ ポイント (日) の上にマウス ポインターを移動すると、コネクタのメッセージの総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![[非承諾ドメイン] レポートのレポート ビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="8a9b0-118">非承諾ドメイン レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="8a9b0-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="8a9b0-119">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8a9b0-120">**日付**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-120">**Date**</span></span>
- <span data-ttu-id="8a9b0-121">**受信コネクタ名**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-121">**Inbound connector name**</span></span>
- <span data-ttu-id="8a9b0-122">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-122">**Sender domain**</span></span>
- <span data-ttu-id="8a9b0-123">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-123">**Message count**</span></span>
- <span data-ttu-id="8a9b0-124">**サンプル メッセージ**: 影響を受けるメッセージのサンプルのメッセージ ID。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="8a9b0-125">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8a9b0-126">特定の日付範囲のレポートを 1 人または複数の受信者に電子メールで送信するには、[ダウンロードの要求] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8a9b0-127">テーブル内の行を選択すると、次の情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="8a9b0-128">**日付**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-128">**Date**</span></span>
- <span data-ttu-id="8a9b0-129">**受信コネクタ名**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-129">**Inbound connector name**</span></span>
- <span data-ttu-id="8a9b0-130">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-130">**Sender domain**</span></span>
- <span data-ttu-id="8a9b0-131">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="8a9b0-131">**Message count**</span></span>
- <span data-ttu-id="8a9b0-132">**サンプル メッセージ**: [サンプル メッセージの表示 [](message-trace-scc.md)]**を** クリックすると、影響を受けるメッセージのサンプルのメッセージ追跡結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![[承認されていないドメイン] レポートの [詳細] テーブル ビューで行を選択した後の詳細フライアウト](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="8a9b0-134">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a9b0-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a9b0-135">Related topics</span></span>

<span data-ttu-id="8a9b0-136">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="8a9b0-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
