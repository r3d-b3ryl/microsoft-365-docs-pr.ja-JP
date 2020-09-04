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
description: 管理者は、新しいユーザーを使用して、組織内のユーザーが新しいドメインにメッセージを転送している場合に、メールの洞察をセキュリティ & コンプライアンスセンターで転送する方法を学習できます。
ms.openlocfilehash: 4d8c88cef182ab1c521d23970797e4746e188916
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357368"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="f157d-103">セキュリティ & コンプライアンスセンターで新しいユーザーが電子メールの洞察を転送する</span><span class="sxs-lookup"><span data-stu-id="f157d-103">New users forwarding email insight in the Security & Compliance Center</span></span>

<span data-ttu-id="f157d-104">組織内の新しいユーザーアカウントが、突然電子メールメッセージを外部ドメインに転送し始めたときに、疑わしいことがあります。</span><span class="sxs-lookup"><span data-stu-id="f157d-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="f157d-105">**メールを転送している新しいドメイン**この[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、組織内で新しく作成されたユーザーが外部ドメインにメッセージを転送したときに通知します。</span><span class="sxs-lookup"><span data-stu-id="f157d-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="f157d-106">この条件は、新しいユーザーの作成に侵害された管理者アカウントが使用されたことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f157d-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="f157d-107">アカウントが侵害されている疑いがある場合は、「 [危害を受けた電子メールアカウントへの対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f157d-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).</span></span>

<span data-ttu-id="f157d-108">この洞察は、問題が検出されたときにのみ表示され、 [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157d-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![新しいユーザーがメールを転送していますのインサイト](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="f157d-110">ウィジェットをクリックすると、このトピックで後述するように、転送 [変更レポート](#forwarding-modifications-report) へのリンクを含む、転送されたメッセージの詳細を確認できるフライアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157d-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this topic.</span></span>

![新しいユーザーの [メールの転送] をクリックした後に表示される詳細ポップアップ](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="f157d-112">また、[詳細] を選択した後に [詳細] を選択すると、[詳細] を選択した後に、[詳細] を選択したときに、この詳細ページ**を表示でき**ます (**レポート**ダッシュボードまたは) の [**上位の分析 &** \> **Dashboard** <https://protection.office.com/insightdashboard></span><span class="sxs-lookup"><span data-stu-id="f157d-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="f157d-113">次のセクションで説明するように、[ **洞察に関連付けられたレポート** ] リンクをクリックして、 **転送変更レポート** に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f157d-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="f157d-114">変更の転送レポート</span><span class="sxs-lookup"><span data-stu-id="f157d-114">Forwarding modifications report</span></span>

<span data-ttu-id="f157d-115">**転送変更レポート**には、組織内の送信者から自動的に転送されるメッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157d-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="f157d-116">新たに作成されたアカウントで、外部ドメインにメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="f157d-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="f157d-117">組織内の他の送信者によって転送されたことがない外部ドメインにメッセージを転送するアカウント。</span><span class="sxs-lookup"><span data-stu-id="f157d-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="f157d-118">これらの種類の転送メッセージは、セキュリティまたはコンプライアンスのリスクを引き起こす可能性があり、侵害されたアカウントを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="f157d-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="f157d-119">レポートには、最大90日間のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f157d-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="f157d-120">既定では、このレポートには過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157d-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="f157d-121">このレポートは、 [メールフローダッシュボード](mail-flow-insights-v2.md) または [レポートダッシュボード](view-mail-flow-reports.md)では直接使用できません。</span><span class="sxs-lookup"><span data-stu-id="f157d-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="f157d-122">**新しいユーザーが電子メールを転送**する場合は、「サイトに**関連付けられたレポートを表示する」** リンクをクリックするだけでなく、次の方法でレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f157d-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="f157d-123">[転送される新しいドメイン](mfi-new-domains-being-forwarded-email.md)の詳細については、「**通知の転送レポート**」リンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="f157d-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="f157d-124">開いて <https://protection.office.com/reportv2?id=MailFlowNewForwarding> います。</span><span class="sxs-lookup"><span data-stu-id="f157d-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="f157d-125">転送変更レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="f157d-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="f157d-126">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f157d-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="f157d-127">**データの表示: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="f157d-127">**Show data for: New forwarding users**:</span></span>

  ![転送変更レポートでの新しい転送ユーザーの表示](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="f157d-129">**データの表示: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="f157d-129">**Show data for: New forwarding domains**:</span></span>

  ![転送変更レポートの [転送された新しいドメインの表示形式](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="f157d-131">レポートビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f157d-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="f157d-132">転送変更レポートの詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="f157d-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="f157d-133">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f157d-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f157d-134">**データの表示: 新しい転送ユーザー**:</span><span class="sxs-lookup"><span data-stu-id="f157d-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="f157d-135">**Name**: 送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="f157d-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="f157d-136">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="f157d-136">**Forwarding type**</span></span>
  - <span data-ttu-id="f157d-137">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f157d-137">**Recipient address**</span></span>
  - <span data-ttu-id="f157d-138">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f157d-138">**Details**</span></span>
  - <span data-ttu-id="f157d-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="f157d-139">**Count**</span></span>
  - <span data-ttu-id="f157d-140">**最初の繰越日付**</span><span class="sxs-lookup"><span data-stu-id="f157d-140">**First forward date**</span></span>

- <span data-ttu-id="f157d-141">**データの表示: 新しい転送ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="f157d-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="f157d-142">**Name**: 送信者の電子メールドメイン。</span><span class="sxs-lookup"><span data-stu-id="f157d-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="f157d-143">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="f157d-143">**Forwarding type**</span></span>
  - <span data-ttu-id="f157d-144">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f157d-144">**Recipient address**</span></span>
  - <span data-ttu-id="f157d-145">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f157d-145">**Details**</span></span>
  - <span data-ttu-id="f157d-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="f157d-146">**Count**</span></span>
  - <span data-ttu-id="f157d-147">**最初の繰越日付**</span><span class="sxs-lookup"><span data-stu-id="f157d-147">**First forward date**</span></span>

<span data-ttu-id="f157d-148">詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始日** と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f157d-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="f157d-149">表から行を選択すると、 **詳細** ポップアップが次の情報と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f157d-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="f157d-150">**Name**: これは、送信者の電子メールアドレス ([ **データの表示: 新しい転送ユーザービュー]** ) または送信者の電子メールドメイン ([ **データの表示元: 新しい転送ドメインビュー]** ) のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="f157d-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="f157d-151">**転送の種類**</span><span class="sxs-lookup"><span data-stu-id="f157d-151">**Forwarding type**</span></span>
- <span data-ttu-id="f157d-152">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="f157d-152">**Recipient**</span></span>
- <span data-ttu-id="f157d-153">**詳細**</span><span class="sxs-lookup"><span data-stu-id="f157d-153">**Details**</span></span>
- <span data-ttu-id="f157d-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="f157d-154">**Count**</span></span>
- <span data-ttu-id="f157d-155">**開始日**</span><span class="sxs-lookup"><span data-stu-id="f157d-155">**Start date**</span></span>
- <span data-ttu-id="f157d-156">**推奨事項**: ここからリンクをクリックすると、Microsoft 365 管理センターでユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f157d-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![転送変更レポートの新しい転送ユーザー表示の詳細表からの詳細ポップアップ](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="f157d-158">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f157d-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f157d-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="f157d-159">Related topics</span></span>

<span data-ttu-id="f157d-160">メールフローダッシュボードの他の洞察の詳細については、「 [セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f157d-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
