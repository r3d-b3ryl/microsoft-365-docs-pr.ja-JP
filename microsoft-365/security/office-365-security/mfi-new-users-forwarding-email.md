---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターで新しいユーザーが電子メールの分析情報を転送して、組織内のユーザーが新しいドメインにメッセージを転送する状況を調査する方法について学習できます。
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660019"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="a2e07-103">新しいユーザーがセキュリティ/コンプライアンス センターで電子&を転送する</span><span class="sxs-lookup"><span data-stu-id="a2e07-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a2e07-104">組織内の新しいユーザー アカウントが突然外部ドメインに電子メール メッセージを転送し始める場合、疑わしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2e07-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="a2e07-105">セキュリティ **&** コンプライアンス センターで電子メールの [](https://protection.office.com)分析情報を転送する新しいドメインは、組織内で新しく作成されたユーザーが外部ドメインにメッセージを転送するときに通知します。</span><span class="sxs-lookup"><span data-stu-id="a2e07-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="a2e07-106">この状態は、侵害された管理者アカウントが新しいユーザーの作成に使用された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2e07-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="a2e07-107">アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e07-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="a2e07-108">この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="a2e07-110">ウィジェットをクリックすると、この記事で後述するように転送変更レポートへのリンクなど、転送されたメッセージの詳細を確認できるフライアウトが表示[](#forwarding-modifications-report)されます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![メールを転送する新しいユーザーの分析情報をクリックした後に表示される詳細フライアウト](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="a2e07-112">[上位の分析情報とおすすめ] 領域 **([** レポート ダッシュボード] または [ &]) で [すべて表示] をクリックした後に、分析情報を選択すると、**この詳細ページ** に移動 \> することもできます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="a2e07-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="a2e07-113">次のセクションで **説明するように、[インサイト** に関連付けられているレポートを表示] リンクをクリックすると、転送の変更レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="a2e07-114">変更レポートの転送</span><span class="sxs-lookup"><span data-stu-id="a2e07-114">Forwarding modifications report</span></span>

<span data-ttu-id="a2e07-115">転送 **変更レポートには、** 組織内の送信者から自動的に転送されるメッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="a2e07-116">メッセージを外部ドメインに転送する新しく作成されたアカウント。</span><span class="sxs-lookup"><span data-stu-id="a2e07-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="a2e07-117">組織内の他の送信者によって転送されたことがない外部ドメインにメッセージを転送するアカウント。</span><span class="sxs-lookup"><span data-stu-id="a2e07-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="a2e07-118">このような種類の転送されたメッセージは、セキュリティまたはコンプライアンスのリスクを引き起し、アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2e07-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="a2e07-119">レポートには、最大 90 日間のデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="a2e07-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="a2e07-120">既定では、レポートには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="a2e07-121">このレポートは、メール フロー ダッシュボードまたは [レポート](mail-flow-insights-v2.md) ダッシュボードでは直接 [使用できません](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e07-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="a2e07-122">新しいユーザーが電子メールの分析 **情報** を転送する場合に、分析情報に関連付けられている [表示] リンクをクリックすると、次の方法でレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="a2e07-123">転送される電子 **メールの分析情報の** [新しいドメイン] の詳細にある [[転送通知] レポートのリンクをクリックします](mfi-new-domains-being-forwarded-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e07-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="a2e07-124">開く <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="a2e07-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="a2e07-125">転送変更レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="a2e07-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="a2e07-126">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a2e07-127">**次のデータを表示します。新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="a2e07-127">**Show data for: New forwarding users**:</span></span>

  ![転送変更レポートの [新しい転送ユーザー] ビュー](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="a2e07-129">**次のデータを表示します。新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="a2e07-129">**Show data for: New forwarding domains**:</span></span>

  ![転送変更レポートの [新しい転送されたドメイン] ビュー](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="a2e07-131">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="a2e07-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="a2e07-132">転送変更レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="a2e07-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="a2e07-133">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a2e07-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a2e07-134">**次のデータを表示します。新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="a2e07-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="a2e07-135">**Name**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="a2e07-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="a2e07-136">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="a2e07-136">**Forwarding type**</span></span>
  - <span data-ttu-id="a2e07-137">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="a2e07-137">**Recipient address**</span></span>
  - <span data-ttu-id="a2e07-138">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a2e07-138">**Details**</span></span>
  - <span data-ttu-id="a2e07-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="a2e07-139">**Count**</span></span>
  - <span data-ttu-id="a2e07-140">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="a2e07-140">**First forward date**</span></span>

- <span data-ttu-id="a2e07-141">**次のデータを表示します。新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="a2e07-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="a2e07-142">**Name**: 送信者の電子メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="a2e07-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="a2e07-143">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="a2e07-143">**Forwarding type**</span></span>
  - <span data-ttu-id="a2e07-144">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="a2e07-144">**Recipient address**</span></span>
  - <span data-ttu-id="a2e07-145">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a2e07-145">**Details**</span></span>
  - <span data-ttu-id="a2e07-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="a2e07-146">**Count**</span></span>
  - <span data-ttu-id="a2e07-147">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="a2e07-147">**First forward date**</span></span>

<span data-ttu-id="a2e07-148">詳細テーブル ビューで **[フィルター** ] をクリックすると、開始日と終了日で **日付範囲** を **指定できます**。</span><span class="sxs-lookup"><span data-stu-id="a2e07-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a2e07-149">テーブルから行を選択すると、 **詳細のフライ** アウトが次の情報と一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="a2e07-150">**名前**: これは、送信者のメール アドレス ([データの表示: 新しい転送ユーザー ビュー] から) または送信者のメール ドメイン ([データの表示先 **:** 新しい転送ドメイン] ビュー) のいずれかです。 </span><span class="sxs-lookup"><span data-stu-id="a2e07-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="a2e07-151">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="a2e07-151">**Forwarding type**</span></span>
- <span data-ttu-id="a2e07-152">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="a2e07-152">**Recipient**</span></span>
- <span data-ttu-id="a2e07-153">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a2e07-153">**Details**</span></span>
- <span data-ttu-id="a2e07-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="a2e07-154">**Count**</span></span>
- <span data-ttu-id="a2e07-155">**開始日**</span><span class="sxs-lookup"><span data-stu-id="a2e07-155">**Start date**</span></span>
- <span data-ttu-id="a2e07-156">**推奨事項**: ここから、リンクをクリックして、Microsoft 365 管理センターでユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2e07-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![転送変更レポートの [転送ユーザーの新規] ビューの詳細テーブルからの詳細フライアウト](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="a2e07-158">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2e07-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2e07-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2e07-159">Related topics</span></span>

<span data-ttu-id="a2e07-160">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e07-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
