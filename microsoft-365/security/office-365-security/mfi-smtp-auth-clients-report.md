---
title: メールフローダッシュボードの SMTP 認証クライアントの洞察とレポート
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで SMTP 認証の洞察とレポートを使用して、組織内で、認証済みの SMTP (SMTP AUTH) を使用して電子メールメッセージを送信する電子メール送信者を監視する方法を学習できます。
ms.openlocfilehash: afdcf01260dd6dfcaf6b53d107e5addd007b1fb3
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577237"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="481a5-103">セキュリティ & コンプライアンスセンターでの SMTP 認証クライアントの洞察とレポート</span><span class="sxs-lookup"><span data-stu-id="481a5-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

<span data-ttu-id="481a5-104">[メールフローダッシュボード](mail-flow-insights-v2.md)とそれに関連付けられている[smtp auth clients レポート](#smtp-auth-clients-report)に記載されている**smtp 認証**クライアントは、組織内のユーザーまたはシステムアカウントによる smtp auth クライアント送信プロトコルの使用を強調します。</span><span class="sxs-lookup"><span data-stu-id="481a5-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="481a5-105">この従来のプロトコル (エンドポイント smtp.office365.com を使用します) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用されやすくなります。</span><span class="sxs-lookup"><span data-stu-id="481a5-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="481a5-106">洞察とレポートを使用すると、SMTP 認証の電子メールの送信に関する異常な動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="481a5-107">また、SMTP 認証を使用するクライアントまたはデバイスの TLS 使用状況データも表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="481a5-108">ウィジェットは、過去7日間に SMTP 認証プロトコルを使用したユーザーまたはサービスアカウントの数を示します。</span><span class="sxs-lookup"><span data-stu-id="481a5-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの SMTP 認証クライアントウィジェット](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="481a5-110">ウィジェットのメッセージ数をクリックすると、[ **SMTP Auth clients** ] ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="481a5-111">フライアウトは、過去1週間の TLS 使用量とボリュームを集約したビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="481a5-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![メールフローダッシュボードの SMTP 認証クライアントウィジェットをクリックした後の詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="481a5-113">[ **Smtp auth clients レポート**] リンクをクリックすると、次のセクションで説明されているように、smtp auth clients レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="481a5-114">SMTP Auth クライアントのレポート</span><span class="sxs-lookup"><span data-stu-id="481a5-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="481a5-115">SMTP 認証クライアントレポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="481a5-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="481a5-116">既定では、レポートには過去7日間のデータが表示されますが、データは過去90日間で利用可能です。</span><span class="sxs-lookup"><span data-stu-id="481a5-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="481a5-117">概要セクションには、次のグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="481a5-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="481a5-118">**データの表示: 送信ボリューム**: 既定では、すべてのドメインから送信された SMTP Auth クライアントメッセージの数 ([**データの表示: 既定ではすべての送信者ドメイン**が選択されています)] を示しています。</span><span class="sxs-lookup"><span data-stu-id="481a5-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="481a5-119">結果を特定の送信者のドメインにフィルター処理するには、ドロップダウンリストから [**データの表示]** をクリックし、送信者のドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="481a5-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="481a5-120">特定のデータポイント (日単位) をポイントすると、メッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![セキュリティ & コンプライアンスセンターの SMTP 認証クライアントレポートでのボリューム表示の送信](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="481a5-122">**データの表示方法: TLS 使用法**: 選択した期間におけるすべての SMTP Auth クライアントメッセージの tls 使用率を示します。</span><span class="sxs-lookup"><span data-stu-id="481a5-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="481a5-123">このグラフでは、以前のバージョンの TLS を使用しているユーザーとシステムアカウントを識別し、アクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="481a5-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![セキュリティ & コンプライアンスセンターの SMTP 認証クライアントレポートの TLS 使用法の表示](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="481a5-125">レポートビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="481a5-126">[**要求レポート**] をクリックして、レポートの詳細バージョンを電子メールメッセージで受信します。</span><span class="sxs-lookup"><span data-stu-id="481a5-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="481a5-127">レポートを受信する日付の範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="481a5-128">SMTP Auth clients レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="481a5-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="481a5-129">[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="481a5-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="481a5-130">**データの表示: 送信ボリューム**: 次の情報が表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="481a5-131">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="481a5-131">**Sender address**</span></span>
  - <span data-ttu-id="481a5-132">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="481a5-132">**Message count**</span></span>

  <span data-ttu-id="481a5-133">行を選択すると、同じ詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="481a5-134">**データの表示方法: TLS 使用法**: 次の情報を表に示します。</span><span class="sxs-lookup"><span data-stu-id="481a5-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="481a5-135">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="481a5-135">**Sender address**</span></span>
  - <span data-ttu-id="481a5-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="481a5-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="481a5-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="481a5-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="481a5-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="481a5-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="481a5-139">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="481a5-139">**Message count**</span></span>

  <span data-ttu-id="481a5-140"><sup>\*</sup>この列には、送信者からのメッセージの割合と数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="481a5-141">詳細テーブルビューで [**フィルター** ] をクリックすると、**開始日**と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="481a5-142">行を選択すると、同様の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="481a5-142">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP Auth clients レポートの [TLS usage] ビューの詳細表からの詳細ポップアップ](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="481a5-144">[**要求レポート**] をクリックして、レポートの詳細バージョンを電子メールメッセージで受信します。</span><span class="sxs-lookup"><span data-stu-id="481a5-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="481a5-145">レポートを受信する日付の範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="481a5-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="481a5-146">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="481a5-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="481a5-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="481a5-147">Related topics</span></span>

<span data-ttu-id="481a5-148">メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="481a5-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
