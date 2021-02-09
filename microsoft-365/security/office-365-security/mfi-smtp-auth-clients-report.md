---
title: SMTP 認証クライアントの分析情報とメール フロー ダッシュボードでのレポート
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
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで SMTP 認証の分析情報とレポートを使用して、認証済み SMTP (SMTP AUTH) を使用して電子メール メッセージを送信する組織内の電子メール送信者を監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3476ee2f9388245fb105a0910fa7b7d11ec3aeee
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150245"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="a4dca-103">セキュリティ/コンプライアンス センターでの SMTP 認証&レポート</span><span class="sxs-lookup"><span data-stu-id="a4dca-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4dca-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="a4dca-104">**Applies to**</span></span>
- [<span data-ttu-id="a4dca-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a4dca-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a4dca-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="a4dca-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a4dca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4dca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a4dca-108">メール フロー ダッシュボード内の [](mail-flow-insights-v2.md)SMTP 認証クライアントの分析情報と、セキュリティ [&](https://protection.office.com)コンプライアンス センターの関連付けられた [SMTP 認証](#smtp-auth-clients-report)クライアント レポートでは、組織内のユーザーまたはシステム アカウントによる **SMTP** AUTH クライアント送信プロトコルの使用が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="a4dca-109">この従来のプロトコル (エンドポイント smtp.office365.com を使用) は基本認証のみを提供し、侵害されたアカウントが電子メールを送信するために使用される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4dca-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="a4dca-110">分析情報とレポートを使用すると、SMTP AUTH 電子メール送信の異常なアクティビティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="a4dca-111">また、SMTP AUTH を使用するクライアントまたはデバイスの TLS 使用状況データも示します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="a4dca-112">ウィジェットは、過去 7 日間に SMTP 認証プロトコルを使用したユーザーまたはサービス アカウントの数を示します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの SMTP 認証&ウィジェット](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="a4dca-114">ウィジェット上のメッセージ数をクリックすると **、SMTP 認証クライアント** のフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="a4dca-115">このフライアウトは、先週の TLS の使用状況とボリュームの集計ビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![メール フロー ダッシュボードで SMTP 認証クライアント ウィジェットをクリックした後の詳細フライアウト](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="a4dca-117">次のセクションで説明 **するように、SMTP 認証** クライアント レポートのリンクをクリックして SMTP 認証クライアント レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="a4dca-118">SMTP Auth クライアントのレポート</span><span class="sxs-lookup"><span data-stu-id="a4dca-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a4dca-119">SMTP 認証クライアント レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="a4dca-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a4dca-120">既定では、レポートには過去 7 日間のデータが表示されますが、過去 90 日間のデータは使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="a4dca-121">概要セクションには、次のグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a4dca-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="a4dca-122">データ **の表示:** 送信ボリューム : 既定では、すべてのドメインから送信された SMTP 認証クライアント メッセージの数がグラフに表示されます **([** データの表示: すべての送信者ドメインが既定で選択されています]。</span><span class="sxs-lookup"><span data-stu-id="a4dca-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="a4dca-123">[データの表示] をクリックし、ドロップダウン リストから送信者ドメインを選択すると、結果を特定の送信者ドメインにフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="a4dca-124">特定のデータ ポイント (日) をポイントすると、メッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![セキュリティ/コンプライアンス センターの SMTP 認証クライアント レポートでボリューム &送信する](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="a4dca-126">**[データの表示方法]: [TLS** の使用状況]: 選択した期間中のすべての SMTP 認証クライアント メッセージに対する TLS 使用状況の割合がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="a4dca-127">このグラフを使用すると、古いバージョンの TLS をまだ使用しているユーザーとシステム アカウントを特定し、アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![セキュリティ/コンプライアンス センターの SMTP 認証クライアント レポート&表示](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="a4dca-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span><span class="sxs-lookup"><span data-stu-id="a4dca-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a4dca-130">[ **レポートの要求]** をクリックして、より詳細なバージョンのレポートを電子メール メッセージで受信します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a4dca-131">レポートを受信する日付範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="a4dca-132">SMTP 認証クライアント レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="a4dca-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="a4dca-133">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a4dca-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a4dca-134">**データの表示:ボリュームの送信**: 次の情報を表に示します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a4dca-135">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="a4dca-135">**Sender address**</span></span>
  - <span data-ttu-id="a4dca-136">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="a4dca-136">**Message count**</span></span>

  <span data-ttu-id="a4dca-137">行を選択すると、同じ詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="a4dca-138">**データの表示方法: TLS 使用法**: 次の情報を表に示します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="a4dca-139">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="a4dca-139">**Sender address**</span></span>
  - <span data-ttu-id="a4dca-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4dca-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4dca-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4dca-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4dca-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4dca-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="a4dca-143">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="a4dca-143">**Message count**</span></span>

  <span data-ttu-id="a4dca-144"><sup>\*</sup> この列には、送信者からのメッセージの割合と数の両方が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="a4dca-145">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="a4dca-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a4dca-146">行を選択すると、同様の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-146">If you select a row, similar details are shown in a flyout:</span></span>

![SMTP 認証クライアント レポートの TLS 使用状況ビューの詳細テーブルからの詳細フライアウト](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="a4dca-148">[ **レポートの要求]** をクリックして、より詳細なバージョンのレポートを電子メール メッセージで受信します。</span><span class="sxs-lookup"><span data-stu-id="a4dca-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="a4dca-149">レポートを受信する日付範囲と受信者を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4dca-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="a4dca-150">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a4dca-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4dca-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4dca-151">Related topics</span></span>

<span data-ttu-id="a4dca-152">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="a4dca-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
