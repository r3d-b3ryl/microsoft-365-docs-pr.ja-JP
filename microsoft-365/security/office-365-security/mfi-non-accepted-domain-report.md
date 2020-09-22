---
title: メールフローダッシュボードの承認されていないドメインレポート
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
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで承認されていないドメインレポートを使用して、送信者のドメインが Microsoft 365 で構成されていないオンプレミスの組織からのメッセージを監視する方法を学習できます。
ms.openlocfilehash: d05489ec4a6d670fc89b5d943b3e7061506b6fe8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199327"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="fdaa2-103">セキュリティ & コンプライアンスセンターの承認されていないドメインレポート</span><span class="sxs-lookup"><span data-stu-id="fdaa2-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fdaa2-104">[セキュリティ & コンプライアンスセンター](https://protection.office.com)の[メールフローダッシュボード](mail-flow-insights-v2.md)の承認されてい**ないドメイン**レポートには、送信者のドメインが Microsoft 365 組織の承認済みドメインとして構成されていないオンプレミスの電子メール組織からのメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="fdaa2-105">これらのメッセージが悪意のあるものであることを証明するためのデータがある場合、Microsoft 365 はこれらのメッセージを調整する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="fdaa2-106">そのため、何が起こっているのかを理解し、問題を修正することが重要です。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの承認されていないドメインウィジェット](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="fdaa2-108">承認されていないドメインレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="fdaa2-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="fdaa2-109">承認されてい **ないドメイン** ウィジェットのグラフをクリックすると、承認されてい **ないドメイン** レポートに移動します。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="fdaa2-110">既定では、影響を受けるすべてのコネクタのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="fdaa2-111">[ **データの表示**] をクリックすると、ドロップダウンから特定のコネクタを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="fdaa2-112">グラフのデータ要素 (日単位) の上にポインターを置くと、そのコネクタの合計メッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![承認されていないドメインレポートのレポートビュー](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="fdaa2-114">承認されていないドメインレポートの詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="fdaa2-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="fdaa2-115">レポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fdaa2-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-116">**Date**</span></span>
- <span data-ttu-id="fdaa2-117">**受信コネクタ名**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-117">**Inbound connector name**</span></span>
- <span data-ttu-id="fdaa2-118">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-118">**Sender domain**</span></span>
- <span data-ttu-id="fdaa2-119">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-119">**Message count**</span></span>
- <span data-ttu-id="fdaa2-120">**サンプルメッセージ**: 影響を受けるメッセージのサンプルのメッセージ id。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="fdaa2-121">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fdaa2-122">特定の日付範囲のレポートに対して1人以上の受信者を電子メールで送信するには、[ **ダウンロードの依頼**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="fdaa2-123">表の行を選択すると、次の情報を含むフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="fdaa2-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-124">**Date**</span></span>
- <span data-ttu-id="fdaa2-125">**受信コネクタ名**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-125">**Inbound connector name**</span></span>
- <span data-ttu-id="fdaa2-126">**送信元ドメイン**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-126">**Sender domain**</span></span>
- <span data-ttu-id="fdaa2-127">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="fdaa2-127">**Message count**</span></span>
- <span data-ttu-id="fdaa2-128">**サンプルメッセージ**: [ **サンプルメッセージの表示** ] をクリックすると、影響を受けたメッセージのサンプルの [メッセージの追跡](message-trace-scc.md) 結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![承認されていないドメインレポートの [詳細] テーブルビューで行を選択した後の詳細ポップアップ](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="fdaa2-130">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdaa2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdaa2-131">Related topics</span></span>

<span data-ttu-id="fdaa2-132">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdaa2-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
