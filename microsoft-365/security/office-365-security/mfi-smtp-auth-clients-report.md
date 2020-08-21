---
title: メール フロー ダッシュボードの SMTP Auth クライアントインサイトとレポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで SMTP Auth insight を使用してレポートし、認証済み SMTP (SMTP AUTH) を使用してメール メッセージを送信する、組織内のメール送信者を監視する方法を学習できます。
ms.openlocfilehash: 65e5569bcd79caef071ee2103d18a4e985c19dbb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826871"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="bc10f-103">セキュリティ コンプライアンス センターの SMTP Auth クライアントのインサイト& レポート</span><span class="sxs-lookup"><span data-stu-id="bc10f-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="bc10f-104">**メール フローのダッシュボードおよび**関連する SMTP Auth[クライアント](mail-flow-insights-v2.md)レポートの[SMTP Auth クライアントから、組織内](#smtp-auth-clients-report)のユーザーまたはシステム アカウントでの SMTP AUTH クライアント送信プロトコルの使用状況を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="bc10f-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="bc10f-105">このレガシ プロトコル (エンドポイント smtp.office365.com を使用する) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用するのを受け付けします。</span><span class="sxs-lookup"><span data-stu-id="bc10f-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="bc10f-106">インサイトとレポートでは、SMTP AUTH メールを送信するための異形式のアクティビティをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="bc10f-107">また、SMTP AUTH を使用したクライアントまたはデバイスの TLS 使用状況データも示しています。</span><span class="sxs-lookup"><span data-stu-id="bc10f-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="bc10f-108">ウィジェットは、過去 7 日間の SMTP Auth プロトコルを使用したユーザーまたはサービス アカウントの数を示します。</span><span class="sxs-lookup"><span data-stu-id="bc10f-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![セキュリティ センター センターのメール フロー ダッシュボードの SMTP Auth クライアント &イジェット](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="bc10f-110">ウィジェット上のメッセージ数をクリックすると **、SMTP Auth クライアントのポップ** アップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="bc10f-111">ポップアップでは、過去 1 週間の TLS 使用状況とボリュームの集計ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![[メール フロー ダッシュボード] で SMTP Auth クライアント ウィジェットをクリックした後の詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="bc10f-113">SMTP Auth クライアント レポート **リンクをクリックすると** 、次のセクションの説明に示されている SMTP Auth クライアント レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="bc10f-114">SMTP Auth クライアントのレポート</span><span class="sxs-lookup"><span data-stu-id="bc10f-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="bc10f-115">SMTP Auth クライアント レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="bc10f-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="bc10f-116">既定では、レポートには最も期間 7 日間のデータが表示されますが、過去 90 日間のデータが取得可能になります。</span><span class="sxs-lookup"><span data-stu-id="bc10f-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="bc10f-117">概要セクションには、次のグラフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="bc10f-118">**データの表示: ボリュームの送信**: 既定では、すべてのドメインから送信された SMTP Auth クライアント メッセージの数がグラフに表示されます **([表示: 既定ではすべての送信者ドメイン** ] が選択されています)。</span><span class="sxs-lookup"><span data-stu-id="bc10f-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="bc10f-119">特定の送信者ドメインに結果をフィルターするには、[ **データの** 表示] をクリックし、ドロップダウン リストから送信者ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="bc10f-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="bc10f-120">特定のデータ ポイントをポイントする場合は、メッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![コンプライアンス センターの SMTP Auth クライアント レポートでのボリューム & ビューの送信](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="bc10f-122">**データの閲覧元: TLS 使用**率: 選択した期間中のすべての SMTP Auth クライアント メッセージに対する TLS 使用率がグラフに示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="bc10f-123">このグラフを使用すると、ユーザーおよびシステム アカウントを特定して、以前のバージョンの TLS を使用しているユーザー アカウントを特定してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![セキュリティ コンプライアンス センターの SMTP Auth クライアント レポートの TLS 使用&ビュー](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="bc10f-125">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="bc10f-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bc10f-126">[ **要求] レポートを** クリックすると、メール メッセージでレポートの詳細バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="bc10f-127">レポートを受信する日付範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="bc10f-128">SMTP Auth クライアント レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="bc10f-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="bc10f-129">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="bc10f-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bc10f-130">**データの表示: Sending volume:** 次の情報が表に表示されています。</span><span class="sxs-lookup"><span data-stu-id="bc10f-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="bc10f-131">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="bc10f-131">**Sender address**</span></span>
  - <span data-ttu-id="bc10f-132">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="bc10f-132">**Message count**</span></span>

  <span data-ttu-id="bc10f-133">行を選択すると、詳細と同じ詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="bc10f-134">**データの表示元: TLS の使用**方法: 次の情報を表に示します。</span><span class="sxs-lookup"><span data-stu-id="bc10f-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="bc10f-135">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="bc10f-135">**Sender address**</span></span>
  - <span data-ttu-id="bc10f-136">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc10f-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bc10f-137">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc10f-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bc10f-138">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bc10f-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bc10f-139">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="bc10f-139">**Message count**</span></span>

  <span data-ttu-id="bc10f-140"><sup>\*</sup> この列には、送信者からのメッセージの割合と数の両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="bc10f-141">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="bc10f-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bc10f-142">行を選択すると、同様の詳細がポップアップに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-142">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP Auth クライアント レポートの TLS 使用状況ビューの詳細テーブルからの詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="bc10f-144">[ **要求] レポートを** クリックすると、メール メッセージでレポートの詳細バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="bc10f-145">レポートを受信する日付範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bc10f-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="bc10f-146">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bc10f-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc10f-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bc10f-147">Related topics</span></span>

<span data-ttu-id="bc10f-148">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="bc10f-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
