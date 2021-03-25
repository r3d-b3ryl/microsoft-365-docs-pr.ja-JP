---
title: 新しいユーザーがメールを転送していますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターで電子メールの分析情報を転送する新しいユーザーを使用して、組織内のユーザーが新しいドメインにメッセージを転送する際に調査する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206195"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="8b7cf-103">セキュリティ コンプライアンス センターで電子メールの分析情報を&する新しいユーザー</span><span class="sxs-lookup"><span data-stu-id="8b7cf-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8b7cf-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-104">**Applies to**</span></span>
- [<span data-ttu-id="8b7cf-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8b7cf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8b7cf-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="8b7cf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8b7cf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b7cf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8b7cf-108">組織の新しいユーザー アカウントが突然外部ドメインへの電子メール メッセージの転送を開始すると、疑わしい場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="8b7cf-109">セキュリティ **&** コンプライアンス センターで転送される新しいドメインは、組織内 [の](https://protection.office.com) 新しく作成されたユーザーが外部ドメインにメッセージを転送するときに通知します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="8b7cf-110">この条件は、侵害された管理者アカウントが新しいユーザーの作成に使用された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="8b7cf-111">アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントに応答 [する」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="8b7cf-112">この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="8b7cf-114">ウィジェットをクリックすると、この記事で後述する転送変更レポートへのリンクなど、転送されたメッセージの詳細を確認できるフライアウトが表示[](#forwarding-modifications-report)されます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![電子メールの分析情報を転送する新しいユーザーをクリックした後に表示される詳細フライアウト](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="8b7cf-116">[レポート ダッシュボード] または [ おすすめ] 領域の[トップ インサイト] 領域で [すべて表示] をクリックした後で&を選択すると、**この詳細** ページに \> **アクセス** することもできます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="8b7cf-117">[分析情報に関連付 **けられているレポートを表示する**] リンクをクリックすると、次のセクションで説明されている [転送の変更] レポートに移動できます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="8b7cf-118">変更レポートの転送</span><span class="sxs-lookup"><span data-stu-id="8b7cf-118">Forwarding modifications report</span></span>

<span data-ttu-id="8b7cf-119">[ **転送の変更] レポート** には、組織内の送信者から自動的に転送されるメッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="8b7cf-120">メッセージを外部ドメインに転送する新しく作成されたアカウント。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="8b7cf-121">組織内の他の送信者が転送したことがない外部ドメインにメッセージを転送するアカウント。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="8b7cf-122">これらの種類の転送されたメッセージは、セキュリティまたはコンプライアンスのリスクを引き起し、侵害されたアカウントを示す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="8b7cf-123">レポートには、最大 90 日間のデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="8b7cf-124">既定では、レポートには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="8b7cf-125">このレポートは、メール フロー ダッシュボードまたは [レポート](mail-flow-insights-v2.md) ダッシュボードでは [直接使用できません](view-mail-flow-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="8b7cf-126">[新しいユーザーがメールの分析情報を転送する]の [インサイトに関連付けられているレポートを表示する] リンクをクリックする以外に、次の方法でレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="8b7cf-127">[転送中の **新しい** ドメイン] の詳細にある [転送通知レポート] リンク [をクリック](mfi-new-domains-being-forwarded-email.md)します。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="8b7cf-128">を開く <https://protection.office.com/reportv2?id=MailFlowNewForwarding> 。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8b7cf-129">転送変更レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="8b7cf-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="8b7cf-130">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8b7cf-131">**データを表示する: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="8b7cf-131">**Show data for: New forwarding users**:</span></span>

  ![[転送の変更] レポートの [新しい転送ユーザー] ビュー](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="8b7cf-133">**データを表示する: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="8b7cf-133">**Show data for: New forwarding domains**:</span></span>

  ![転送変更レポートの新しい転送ドメイン ビュー](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="8b7cf-135">レポート ビューで **[フィルター]** をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8b7cf-136">転送変更レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="8b7cf-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="8b7cf-137">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8b7cf-138">**データを表示する: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="8b7cf-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="8b7cf-139">**名前**: 送信者の電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="8b7cf-140">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-140">**Forwarding type**</span></span>
  - <span data-ttu-id="8b7cf-141">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-141">**Recipient address**</span></span>
  - <span data-ttu-id="8b7cf-142">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-142">**Details**</span></span>
  - <span data-ttu-id="8b7cf-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-143">**Count**</span></span>
  - <span data-ttu-id="8b7cf-144">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-144">**First forward date**</span></span>

- <span data-ttu-id="8b7cf-145">**データを表示する: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="8b7cf-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="8b7cf-146">**名前**: 送信者の電子メール ドメイン。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="8b7cf-147">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-147">**Forwarding type**</span></span>
  - <span data-ttu-id="8b7cf-148">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-148">**Recipient address**</span></span>
  - <span data-ttu-id="8b7cf-149">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-149">**Details**</span></span>
  - <span data-ttu-id="8b7cf-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-150">**Count**</span></span>
  - <span data-ttu-id="8b7cf-151">**最初の転送日**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-151">**First forward date**</span></span>

<span data-ttu-id="8b7cf-152">詳細テーブル ビューで **[フィルター** ] をクリックすると、[開始日] と [終了日] で日付 **範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8b7cf-153">テーブルから行を選択すると、[ **詳細** ] フライアウトが表示され、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="8b7cf-154">**名前**: これは、送信者の電子メール アドレス ([データの表示 **:** 新しい転送ユーザー ビュー] から) または送信者のメール ドメイン ([データの表示 **:** 新しい転送ドメイン] ビューから) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="8b7cf-155">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-155">**Forwarding type**</span></span>
- <span data-ttu-id="8b7cf-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-156">**Recipient**</span></span>
- <span data-ttu-id="8b7cf-157">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-157">**Details**</span></span>
- <span data-ttu-id="8b7cf-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-158">**Count**</span></span>
- <span data-ttu-id="8b7cf-159">**開始日**</span><span class="sxs-lookup"><span data-stu-id="8b7cf-159">**Start date**</span></span>
- <span data-ttu-id="8b7cf-160">**推奨事項**: ここから、リンクをクリックして Microsoft 365 管理センターでユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![転送変更レポートの [新しい転送ユーザー] ビューの詳細テーブルからの詳細フライアウト](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="8b7cf-162">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8b7cf-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b7cf-163">Related topics</span></span>

<span data-ttu-id="8b7cf-164">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="8b7cf-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
