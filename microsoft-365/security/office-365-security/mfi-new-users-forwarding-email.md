---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターの新しいユーザー転送メールのインサイトを使用して、組織内のユーザーが新しいドメインにメッセージを転送しているときに調査する方法を学習できます。
ms.openlocfilehash: cb2e16d321e181916219e3425c26e59ebe31b866
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826981"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="08e45-103">セキュリティ コンプライアンス センターの新しいユーザーがメールの&情報を転送する</span><span class="sxs-lookup"><span data-stu-id="08e45-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="08e45-104">外部ドメインへの電子メール メッセージの転送が一時的に開始されたときは、不審な操作になります。</span><span class="sxs-lookup"><span data-stu-id="08e45-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="08e45-105">電子 **メールの分析情報が転送** されている新しいドメインは、組織内の新しく作成されたユーザーが外部のドメインにメッセージを転送しているときに通知します。</span><span class="sxs-lookup"><span data-stu-id="08e45-105">The **New domains being forwarded email** insight notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="08e45-106">この状態は、新しいユーザーの作成に管理者アカウントが使用されたことを示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08e45-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="08e45-107">アカウントが侵害されている可能性がある場合は、「侵害 [されたメール アカウントへの対応」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)。</span><span class="sxs-lookup"><span data-stu-id="08e45-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="08e45-108">この分析情報は、問題が検出されたときのみ表示され、[転送レポート] [ページに表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="08e45-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="08e45-110">ウィジェットをクリックすると、ポップアップが表示され、転送されたメッセージに関する詳細が表示されます。ここには、後の説明に従って [転送変更レポートへの](#forwarding-modifications-report) リンクを含めて確認できます。</span><span class="sxs-lookup"><span data-stu-id="08e45-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![[新しいユーザーがメールの分析情報を転送する] をクリックした後に表示される詳細ポップアップ](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="08e45-112">この詳細ページは、**トップ**インサイト &推奨事項領域 (レポート ダッシュボードまたはレポート**View all**) で [すべてのインサイトを表示] をクリックした後で、そのインサイト**を** \> **選択すると**表示されます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="08e45-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="08e45-113">**[Insight] リンクに関連付けられているレポートをクリック**すると、次のセクションで説明するように転送**変更**レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="08e45-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="08e45-114">転送変更レポート</span><span class="sxs-lookup"><span data-stu-id="08e45-114">Forwarding modifications report</span></span>

<span data-ttu-id="08e45-115">転送 **変更レポートには、** 組織内の送信者から自動的に転送されるメッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e45-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="08e45-116">メッセージを外部ドメインに転送する、新しく作成されたアカウント。</span><span class="sxs-lookup"><span data-stu-id="08e45-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="08e45-117">組織内の他の送信者によって一度も転送されたのがない外部ドメインにメッセージを転送しているアカウント。</span><span class="sxs-lookup"><span data-stu-id="08e45-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="08e45-118">このような転送されたメッセージは、セキュリティやコンプライアンスリスクが発生する可能性があるため、アカウントが侵害された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08e45-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="08e45-119">レポートには、最大 90 日間のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="08e45-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="08e45-120">既定では、過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e45-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="08e45-121">このレポートは、メール フロー ダッシュボード [またはレポート ダッシュボード](mail-flow-insights-v2.md) では直接 [使用できません](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="08e45-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="08e45-122">新しいユーザーの電子メール イン **サイトのインサイト リンクに** 関連付けられた [インサイト] **リンク** をクリックする以外に、次のレポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08e45-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="08e45-123">新しい **ドメインが転送されている電子** メールの分析情報の詳細の [転送通知レポート リンクをクリックします](mfi-new-domains-being-forwarded-email.md)。</span><span class="sxs-lookup"><span data-stu-id="08e45-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="08e45-124">. <https://protection.office.com/reportv2?id=MailFlowNewForwarding></span><span class="sxs-lookup"><span data-stu-id="08e45-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="08e45-125">転送変更レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="08e45-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="08e45-126">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08e45-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="08e45-127">**表示データ: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="08e45-127">**Show data for: New forwarding users**:</span></span>

  ![転送変更レポートで新しい転送ユーザーに表示される](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="08e45-129">**データの表示: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="08e45-129">**Show data for: New forwarding domains**:</span></span>

  ![転送変更レポートの新しい転送されたドメイン ビュー](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="08e45-131">レポート ビューで **[フィルター** ] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="08e45-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="08e45-132">転送変更レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="08e45-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="08e45-133">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="08e45-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="08e45-134">**表示データ: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="08e45-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="08e45-135">**Name:** 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="08e45-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="08e45-136">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="08e45-136">**Forwarding type**</span></span>
  - <span data-ttu-id="08e45-137">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="08e45-137">**Recipient address**</span></span>
  - <span data-ttu-id="08e45-138">**詳細**</span><span class="sxs-lookup"><span data-stu-id="08e45-138">**Details**</span></span>
  - <span data-ttu-id="08e45-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="08e45-139">**Count**</span></span>
  - <span data-ttu-id="08e45-140">**1 つ目の転送日**</span><span class="sxs-lookup"><span data-stu-id="08e45-140">**First forward date**</span></span>

- <span data-ttu-id="08e45-141">**データの表示: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="08e45-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="08e45-142">**Name**:送信者の電子メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="08e45-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="08e45-143">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="08e45-143">**Forwarding type**</span></span>
  - <span data-ttu-id="08e45-144">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="08e45-144">**Recipient address**</span></span>
  - <span data-ttu-id="08e45-145">**詳細**</span><span class="sxs-lookup"><span data-stu-id="08e45-145">**Details**</span></span>
  - <span data-ttu-id="08e45-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="08e45-146">**Count**</span></span>
  - <span data-ttu-id="08e45-147">**1 つ目の転送日**</span><span class="sxs-lookup"><span data-stu-id="08e45-147">**First forward date**</span></span>

<span data-ttu-id="08e45-148">詳細テーブル ビュー**の [** フィルター] をクリックすると、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="08e45-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="08e45-149">テーブルから行を選択すると、[ **詳細]** ポップアップが表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="08e45-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="08e45-150">**Name:** 送信者のメール アドレス ([データの表示 **] ビュー:新** しい転送ユーザー ビューからのもの) または送信者のメール ドメイン ([新しい転送ドメイン] ビューの [データの表示] ビュー) **のいずれか** です。</span><span class="sxs-lookup"><span data-stu-id="08e45-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="08e45-151">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="08e45-151">**Forwarding type**</span></span>
- <span data-ttu-id="08e45-152">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="08e45-152">**Recipient**</span></span>
- <span data-ttu-id="08e45-153">**詳細**</span><span class="sxs-lookup"><span data-stu-id="08e45-153">**Details**</span></span>
- <span data-ttu-id="08e45-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="08e45-154">**Count**</span></span>
- <span data-ttu-id="08e45-155">**開始日**</span><span class="sxs-lookup"><span data-stu-id="08e45-155">**Start date**</span></span>
- <span data-ttu-id="08e45-156">**推奨**: ここで、Microsoft 365 管理センターのユーザーは、リンクをクリックしてユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="08e45-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![[転送変更] レポートの [新しい転送ユーザー] ビューの詳細テーブルの詳細なポップアップ](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="08e45-158">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="08e45-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="08e45-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="08e45-159">Related topics</span></span>

<span data-ttu-id="08e45-160">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="08e45-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
