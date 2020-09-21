---
title: セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 組織の電子メールセキュリティレポートを検索して使用する方法について説明します。 電子メールセキュリティレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a87cee31b4e0251aea8eb39640d37184ccd0ee96
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104524"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="4b74f-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4b74f-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="4b74f-105">[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールセキュリティ機能が組織を保護していることを確認するのに役立つさまざまなレポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="4b74f-106">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="4b74f-107">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="4b74f-109">侵害されたユーザーレポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="4b74f-110">このレポートは、Microsoft 365 組織の Exchange Online メールボックスを使用して利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="4b74f-111">これは、スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="4b74f-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="4b74f-112">侵害された **ユーザー** のレポートには、過去7日間以内に **疑わしい** または **制限** されたユーザーアカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="4b74f-113">これらの状態のいずれかのアカウントは、問題が発生しているか、侵害されています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="4b74f-114">よく使用されるので、レポートを使用して、不審なアカウントや制限付きのアカウントでスパイクや傾向を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="4b74f-115">侵害されたユーザーの詳細については、「 [危害を受けた電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポートダッシュボードの侵害されたユーザーウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="4b74f-117">集計ビューには過去90日間のデータが表示され、詳細ビューには過去30日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="4b74f-118">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して、[侵害された **ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="4b74f-119">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=CompromisedUsers> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="4b74f-120">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="4b74f-121">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="4b74f-122">**疑わしい**: ユーザーアカウントは、不審な電子メールを送信しているため、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="4b74f-123">**制限**: 非常に疑わしいパターンがあるため、ユーザーアカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザーレポートのレポートビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="4b74f-125">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="4b74f-126">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="4b74f-126">**Creation time**</span></span>
- <span data-ttu-id="4b74f-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-127">**User ID**</span></span>
- <span data-ttu-id="4b74f-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="4b74f-128">**Action**</span></span>

<span data-ttu-id="4b74f-129">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b74f-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="4b74f-130">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-130">Encryption report</span></span>

<span data-ttu-id="4b74f-131">**暗号化レポート**は、EOP (exchange online またはスタンドアロン EOP の exchange online メールボックスなしのメールボックスを使用したサブスクリプション) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="4b74f-132">組織のセキュリティチームは、このレポートの情報を使用して、パターンを識別し、機密性の高い電子メールメッセージのポリシーを事前に適用または調整することができます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="4b74f-133">例:</span><span class="sxs-lookup"><span data-stu-id="4b74f-133">For example:</span></span>

- <span data-ttu-id="4b74f-134">ユーザーによって大量の電子メールメッセージが暗号化されている場合、暗号化ポリシーを追加して、特定のユースケースの暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="4b74f-135">詳細については、「 [Microsoft 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="4b74f-136">使用可能な暗号化テンプレートが多数あり、それを使用しているものがない場合は、ユーザーが機能のトレーニングを必要としているかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="4b74f-137">集計ビューでは、過去90日間のフィルターを使用でき、詳細ビューでは10日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="4b74f-138">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **暗号化レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="4b74f-139">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=EncryptionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="4b74f-140">暗号化の詳細については、「 [Microsoft 365 の電子メールの暗号化](../../compliance/email-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="4b74f-141">暗号化レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-141">Report view for the Encryption report</span></span>

<span data-ttu-id="4b74f-142">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="4b74f-143">**データの表示: メッセージの暗号化レポート** と次の **方法で分割**します。暗号化方法: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="4b74f-144">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="4b74f-144">**Encryption by user**</span></span>
  - <span data-ttu-id="4b74f-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="4b74f-145">**Encryption by policy**</span></span>

  <span data-ttu-id="4b74f-146">[ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="4b74f-147">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4b74f-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="4b74f-148">Encryption method.</span></span>
  - <span data-ttu-id="4b74f-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="4b74f-149">Encryption template.</span></span>

- <span data-ttu-id="4b74f-150">**データの表示形式: メッセージの暗号化レポート** と **分解: 暗号化テンプレート**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="4b74f-151">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="4b74f-151">**Do not forward**</span></span>
  - <span data-ttu-id="4b74f-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="4b74f-152">**Encrypt only**</span></span>
  - <span data-ttu-id="4b74f-153">**OME previous**</span><span class="sxs-lookup"><span data-stu-id="4b74f-153">**OME previous**</span></span>
  - <span data-ttu-id="4b74f-154">**ユーザー設定**</span><span class="sxs-lookup"><span data-stu-id="4b74f-154">**Custom**</span></span>

  <span data-ttu-id="4b74f-155">[ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="4b74f-156">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4b74f-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="4b74f-157">Encryption method</span></span>
  - <span data-ttu-id="4b74f-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="4b74f-158">Encryption template</span></span>

- <span data-ttu-id="4b74f-159">**データの表示形式: 上位5受信者ドメイン**: このビューには、上位5受信者ドメインの送信されたメッセージ数が円グラフで表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="4b74f-160">[ **フィルター**] をクリックすると、 **開始日** と **終了日**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="4b74f-161">暗号化レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="4b74f-162">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4b74f-163">**下に移動: 暗号化方法** または次のよう **に分割します。暗号化テンプレート**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="4b74f-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-164">**Date**</span></span>
  - <span data-ttu-id="4b74f-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-165">**Sender address**</span></span>
  - <span data-ttu-id="4b74f-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="4b74f-166">**Encryption template**</span></span>
  - <span data-ttu-id="4b74f-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="4b74f-167">**Encryption method**</span></span>
  - <span data-ttu-id="4b74f-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4b74f-168">**Recipient address**</span></span>
  - <span data-ttu-id="4b74f-169">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-169">**Subject**</span></span>

- <span data-ttu-id="4b74f-170">**データの表示方法: 上位5受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="4b74f-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="4b74f-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-171">**Date**</span></span>
  - <span data-ttu-id="4b74f-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4b74f-172">**Recipient domain**</span></span>
  - <span data-ttu-id="4b74f-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="4b74f-173">**Message count**</span></span>
  
<span data-ttu-id="4b74f-174">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b74f-175">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="4b74f-176">Encryption method</span></span>
- <span data-ttu-id="4b74f-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="4b74f-177">Encryption template</span></span>

<span data-ttu-id="4b74f-178">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b74f-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="4b74f-179">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-179">Mailflow status report</span></span>

<span data-ttu-id="4b74f-180">**メールフロー status レポート**には、マルウェア、スパム、フィッシングおよびエッジブロックされたメッセージに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="4b74f-181">詳細については、「 [メールフロー status report](view-mail-flow-reports.md#mailflow-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="4b74f-182">電子メールレポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="4b74f-182">Malware detections in email report</span></span>

<span data-ttu-id="4b74f-183">**電子メールのマルウェア検出**レポートには、受信および送信電子メールメッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) でのマルウェアの検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="4b74f-184">EOP でのマルウェア保護の詳細については、「 [EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="4b74f-185">集計ビューのフィルターでは90日間が許可されますが、詳細テーブルのフィルターでは10日間しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="4b74f-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="4b74f-186">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> ] **ダッシュボード** に移動して、[ **電子メールでマルウェアの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="4b74f-187">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MalwareDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポートダッシュボードの電子メールウィジェットでのマルウェアの検出](../../media/malware-detections-widget.png)

<span data-ttu-id="4b74f-189">[ **フィルター** ] をクリックして、次のものを選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="4b74f-190">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="4b74f-191">**Inbound**</span></span>
- <span data-ttu-id="4b74f-192">**向き**</span><span class="sxs-lookup"><span data-stu-id="4b74f-192">**Outbound**</span></span>

![電子メールレポートでのマルウェア検出のレポートビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="4b74f-194">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="4b74f-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-195">**Date**</span></span>
- <span data-ttu-id="4b74f-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-196">**Sender address**</span></span>
- <span data-ttu-id="4b74f-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4b74f-197">**Recipient address**</span></span>
- <span data-ttu-id="4b74f-198">メッセージ**id**: メッセージヘッダーの**メッセージ id**ヘッダーフィールドで利用可能で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="4b74f-199">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="4b74f-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="4b74f-200">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-200">**Subject**</span></span>
- <span data-ttu-id="4b74f-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="4b74f-201">**Filename**</span></span>
- <span data-ttu-id="4b74f-202">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="4b74f-202">**Malware name**</span></span>

<span data-ttu-id="4b74f-203">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b74f-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="4b74f-204">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-204">Sent and received email report</span></span>

<span data-ttu-id="4b74f-205">**送信および受信した電子メール**レポートには、マルウェア、スパム、メールフロールール (トランスポートルールとも呼ばれる) に関する情報と、電子メールがサービスに入った後の高度なマルウェアの検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="4b74f-206">詳細については、「 [送信および受信した電子メールレポート](view-mail-flow-reports.md#sent-and-received-email-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="4b74f-207">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-207">Spam detections report</span></span>

<span data-ttu-id="4b74f-208">**スパム検出**レポートには、EOP によってブロックされたスパム電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="4b74f-209">メッセージは、受信者ごとではなく個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="4b74f-210">たとえば、同じスパムメッセージが組織内の100の受信者に送信された場合は、1つのメッセージとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="4b74f-211">集計ビューでは90日間のフィルター処理が可能で、詳細テーブルでは10日のフィルター処理が許可されています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="4b74f-212">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スパム検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="4b74f-213">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpamDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポートダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="4b74f-215">スパム対策保護の詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="4b74f-216">スパム検出レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="4b74f-217">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="4b74f-218">**分割ダウン: アクション**: 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="4b74f-219">**スパムコンテンツのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="4b74f-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="4b74f-220">**スパム IP 禁止**</span><span class="sxs-lookup"><span data-stu-id="4b74f-220">**Spam IP block**</span></span>
  - <span data-ttu-id="4b74f-221">**スパムの封筒ブロック**</span><span class="sxs-lookup"><span data-stu-id="4b74f-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="4b74f-222">**スパム dbeb フィルター**: ディレクトリベースのエッジブロック (dbeb)</span><span class="sxs-lookup"><span data-stu-id="4b74f-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="4b74f-223">グラフの1日 (データポイント) にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクションビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="4b74f-225">次のよう**に分割します。方向**: 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="4b74f-226">**受信**</span><span class="sxs-lookup"><span data-stu-id="4b74f-226">**Inbound**</span></span>
  - <span data-ttu-id="4b74f-227">**向き**</span><span class="sxs-lookup"><span data-stu-id="4b74f-227">**Outbound**</span></span>

  ![スパム検出レポートでの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="4b74f-229">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b74f-230">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-231">Direction 値</span><span class="sxs-lookup"><span data-stu-id="4b74f-231">Direction values</span></span>
- <span data-ttu-id="4b74f-232">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="4b74f-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="4b74f-233">スパム検出レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="4b74f-234">いずれかのレポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="4b74f-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-235">**Date**</span></span>
- <span data-ttu-id="4b74f-236">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-236">**Sender address**</span></span>
- <span data-ttu-id="4b74f-237">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4b74f-237">**Recipient address**</span></span>
- <span data-ttu-id="4b74f-238">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="4b74f-238">**Event type**</span></span>
- <span data-ttu-id="4b74f-239">**操作**</span><span class="sxs-lookup"><span data-stu-id="4b74f-239">**Action**</span></span>
- <span data-ttu-id="4b74f-240">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-240">**Subject**</span></span>

<span data-ttu-id="4b74f-241">詳細テーブルで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4b74f-242">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-243">Direction 値</span><span class="sxs-lookup"><span data-stu-id="4b74f-243">Direction values</span></span>
- <span data-ttu-id="4b74f-244">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="4b74f-244">Event type values</span></span>

<span data-ttu-id="4b74f-245">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b74f-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="4b74f-246">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-246">Spoof detections report</span></span>

<span data-ttu-id="4b74f-247">**スプーフィング検出**レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="4b74f-248">スプーフィングの詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="4b74f-249">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="4b74f-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="4b74f-250">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スプーフィング検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="4b74f-251">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpoofMailReport> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポートダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="4b74f-253">グラフの1日 (データポイント) にカーソルを置くと、受信したスプーフィングメールメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="4b74f-254">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="4b74f-255">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="4b74f-256">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="4b74f-256">**Good mail**</span></span>

- <span data-ttu-id="4b74f-257">**スパムとして検出された**</span><span class="sxs-lookup"><span data-stu-id="4b74f-257">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポートビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="4b74f-259">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="4b74f-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-260">**Date**</span></span>
- <span data-ttu-id="4b74f-261">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-261">**Spoofed sender**</span></span>
- <span data-ttu-id="4b74f-262">**True 送信者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-262">**True sender**</span></span>
- <span data-ttu-id="4b74f-263">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="4b74f-263">**Sender IP**</span></span>
- <span data-ttu-id="4b74f-264">**操作**</span><span class="sxs-lookup"><span data-stu-id="4b74f-264">**Action**</span></span>
- <span data-ttu-id="4b74f-265">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="4b74f-265">**Message count**</span></span>

<span data-ttu-id="4b74f-266">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b74f-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="4b74f-267">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-267">Threat protection status report</span></span>

<span data-ttu-id="4b74f-268">**脅威保護の状態**レポートは、EOP と OFFICE 365 ATP の両方で使用できます。ただし、レポートには異なるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b74f-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="4b74f-269">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="4b74f-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4b74f-270">このレポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、 [ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Atp の [安全なリンク](atp-safe-links.md)、Atp の [安全な添付ファイル](atp-safe-attachments.md)、 [atp のフィッシング対策](set-up-anti-phishing-policies.md)など、さまざまなコンテンツを含む電子メールメッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="4b74f-271">この情報を使用して、傾向を特定したり、組織のポリシーを調整する必要があるかどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="4b74f-272">メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="4b74f-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="4b74f-273">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**脅威保護の状態**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="4b74f-274">レポートに直接移動するには、次のいずれかの Url を開きます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="4b74f-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> 。</span><span class="sxs-lookup"><span data-stu-id="4b74f-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="4b74f-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="4b74f-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![レポートダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="4b74f-278">既定では、グラフに過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="4b74f-279">[ **フィルター**] をクリックした場合は、90日の日付の範囲を選択できます (試用版のサブスクリプションは30日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4b74f-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="4b74f-280">詳細テーブルビューでは、30日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="4b74f-281">脅威保護状態レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="4b74f-282">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-282">The following views are available:</span></span>

- <span data-ttu-id="4b74f-283">**データの表示: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="4b74f-284">**メールマルウェア**</span><span class="sxs-lookup"><span data-stu-id="4b74f-284">**Email malware**</span></span>
  - <span data-ttu-id="4b74f-285">**電子メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="4b74f-285">**Email phish**</span></span>
  - <span data-ttu-id="4b74f-286">**コンテンツマルウェア**</span><span class="sxs-lookup"><span data-stu-id="4b74f-286">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="4b74f-288">**データの表示方法: コンテンツ \> マルウェア**<sup>1</sup>: 次の情報は、Office 365 ATP 組織で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="4b74f-289">**マルウェア対策エンジン**</span><span class="sxs-lookup"><span data-stu-id="4b74f-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="4b74f-290">**ファイル分析**</span><span class="sxs-lookup"><span data-stu-id="4b74f-290">**File detonation**</span></span>

  ![脅威保護状態レポートのコンテンツマルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="4b74f-292">**下に移動: 検出テクノロジ** と **View data: Email \> フィッシング**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="4b74f-293">**ATP で生成された URL 評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-294">**高度なフィッシングフィルター**</span><span class="sxs-lookup"><span data-stu-id="4b74f-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="4b74f-295">**スプーフィング防止: DMARC エラー**</span><span class="sxs-lookup"><span data-stu-id="4b74f-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="4b74f-296">**スプーフィング対策: 組織内**</span><span class="sxs-lookup"><span data-stu-id="4b74f-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="4b74f-297">**スプーフィング防止: 外部ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4b74f-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="4b74f-298">**ブランド偽装**</span><span class="sxs-lookup"><span data-stu-id="4b74f-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="4b74f-299">**ドメイン偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-300">**EOP URL 評価**</span><span class="sxs-lookup"><span data-stu-id="4b74f-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="4b74f-301">**一般的なフィッシングフィルター**</span><span class="sxs-lookup"><span data-stu-id="4b74f-301">**General phish filter**</span></span>
  - <span data-ttu-id="4b74f-302">**Others**</span><span class="sxs-lookup"><span data-stu-id="4b74f-302">**Others**</span></span>
  - <span data-ttu-id="4b74f-303">**フィッシング ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="4b74f-304">**URL 分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-305">**ユーザー偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-305">**User impersonation**<sup>1</sup></span></span>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="4b74f-307">**分割ダウン: 検出テクノロジ** と **データの表示者: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="4b74f-308">**ATP で生成されたファイル評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-309">**マルウェア対策エンジン**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-310">**マルウェア対策ポリシーファイルの種類ブロック**</span><span class="sxs-lookup"><span data-stu-id="4b74f-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="4b74f-311">**ファイル分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-312">**悪意のあるファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="4b74f-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="4b74f-313">**マルウェアの ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="4b74f-314">**Others**</span><span class="sxs-lookup"><span data-stu-id="4b74f-314">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="4b74f-316">**分割ダウン: Policy type** and **view Data by: Email \> フィッシング** Or **view data by: email \> マル**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="4b74f-317">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="4b74f-317">**Anti-malware**</span></span>
  - <span data-ttu-id="4b74f-318">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b74f-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="4b74f-319">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="4b74f-319">**Anti-phish**</span></span>
  - <span data-ttu-id="4b74f-320">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="4b74f-320">**Anti-spam**</span></span>
  - <span data-ttu-id="4b74f-321">**メールフロールール** (トランスポートルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="4b74f-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="4b74f-322">**Others**</span><span class="sxs-lookup"><span data-stu-id="4b74f-322">**Others**</span></span>

  ![脅威保護の状態レポートに表示されるフィッシング電子メールのポリシーの種類](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="4b74f-324">**分割ダウン: 配信状態** および **表示データ: 電子メールの \> フィッシング** または **view by: email \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="4b74f-325">**配信失敗**</span><span class="sxs-lookup"><span data-stu-id="4b74f-325">**Delivery failed**</span></span>
  - <span data-ttu-id="4b74f-326">**落下**</span><span class="sxs-lookup"><span data-stu-id="4b74f-326">**Dropped**</span></span>
  - <span data-ttu-id="4b74f-327">**転送**</span><span class="sxs-lookup"><span data-stu-id="4b74f-327">**Forwarded**</span></span>
  - <span data-ttu-id="4b74f-328">**ホストされているメールボックス: カスタムフォルダー**</span><span class="sxs-lookup"><span data-stu-id="4b74f-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="4b74f-329">**ホストされているメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="4b74f-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="4b74f-330">**ホストされているメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="4b74f-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="4b74f-331">**ホストされているメールボックス: 迷惑**</span><span class="sxs-lookup"><span data-stu-id="4b74f-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="4b74f-332">**オンプレミスサーバー: 配信済み**</span><span class="sxs-lookup"><span data-stu-id="4b74f-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="4b74f-333">**検疫**</span><span class="sxs-lookup"><span data-stu-id="4b74f-333">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="4b74f-335"><sup>1</sup> OFFICE 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="4b74f-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="4b74f-336"><sup>2</sup> ゼロ時間自動削除 (ZAP) は、スタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。</span><span class="sxs-lookup"><span data-stu-id="4b74f-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="4b74f-337">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="4b74f-338">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-339">検出値</span><span class="sxs-lookup"><span data-stu-id="4b74f-339">Detection value</span></span>
- <span data-ttu-id="4b74f-340">**保護者** (OFFICE 365 ATP のみ): **ATP** または **EOP**。</span><span class="sxs-lookup"><span data-stu-id="4b74f-340">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="4b74f-341">このフィルター処理可能なプロパティは、 **「データの表示方法: コンテンツ \> マルウェア**」では使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-341">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="4b74f-342">脅威保護状態レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="4b74f-342">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="4b74f-343">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-343">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4b74f-344">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="4b74f-344">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="4b74f-345">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-345">**Date**</span></span>
  - <span data-ttu-id="4b74f-346">**Location**</span><span class="sxs-lookup"><span data-stu-id="4b74f-346">**Location**</span></span>
  - <span data-ttu-id="4b74f-347">**転送者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-347">**Directed by**</span></span>
  - <span data-ttu-id="4b74f-348">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="4b74f-348">**Malware name**</span></span>

- <span data-ttu-id="4b74f-349">**データの表示: 概要**: [ **表示の詳細] テーブル** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4b74f-349">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="4b74f-350">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="4b74f-350">All other charts:</span></span>

  - <span data-ttu-id="4b74f-351">**Date**</span><span class="sxs-lookup"><span data-stu-id="4b74f-351">**Date**</span></span>
  - <span data-ttu-id="4b74f-352">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4b74f-352">**Subject**</span></span>
  - <span data-ttu-id="4b74f-353">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-353">**Sender**</span></span>
  - <span data-ttu-id="4b74f-354">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-354">**Recipients**</span></span>
  - <span data-ttu-id="4b74f-355">**検出者**</span><span class="sxs-lookup"><span data-stu-id="4b74f-355">**Detected by**</span></span>
  - <span data-ttu-id="4b74f-356">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4b74f-356">**Delivery status**</span></span>
  - <span data-ttu-id="4b74f-357">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4b74f-357">**Source of compromise**</span></span>

<span data-ttu-id="4b74f-358">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-358">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="4b74f-359">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4b74f-359">**Start date** and **End date**</span></span>
- <span data-ttu-id="4b74f-360">検出値</span><span class="sxs-lookup"><span data-stu-id="4b74f-360">Detection value</span></span>
- <span data-ttu-id="4b74f-361">**保護者** (OFFICE 365 ATP のみ): **ATP** または **EOP**。</span><span class="sxs-lookup"><span data-stu-id="4b74f-361">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="4b74f-362">このフィルター処理可能なプロパティは、 **「データの表示方法: コンテンツ \> マルウェア**」では使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-362">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="4b74f-363">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-363">Top malware report</span></span>

<span data-ttu-id="4b74f-364">**上位マルウェア**レポートには、 [EOP でマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-364">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="4b74f-365">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して [ **上位マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-365">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="4b74f-366">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopMalware> ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-366">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポートダッシュボードのトップマルウェアウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="4b74f-368">円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-368">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップマルウェアレポートビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="4b74f-370">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-370">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="4b74f-371">**上位マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4b74f-371">**Top malware**</span></span>
- <span data-ttu-id="4b74f-372">**Count**</span><span class="sxs-lookup"><span data-stu-id="4b74f-372">**Count**</span></span>

<span data-ttu-id="4b74f-373">レポートビューまたは詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始** 日と **終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-373">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="4b74f-374">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-374">URL threat protection report</span></span>

<span data-ttu-id="4b74f-375">**URL 脅威保護レポート**は、Office 365 Advanced threat PROTECTION (ATP) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-375">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="4b74f-376">詳細については、「 [URL の脅威保護レポート](view-reports-for-atp.md#url-threat-protection-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-376">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="4b74f-377">ユーザーによって報告されたメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="4b74f-377">User-reported messages report</span></span>

<span data-ttu-id="4b74f-378">ユーザーによって報告された **メッセージ** レポートには、ユーザーが [レポートメッセージアドイン](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-378">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="4b74f-379">組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-379">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="4b74f-380">詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[ **概要** ] タブと [ **詳細** ] タブで情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-380">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![ユーザーによって報告されたメッセージのレポートには、ユーザーが迷惑メールではないというラベルが付けられます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="4b74f-382">このレポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-382">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="4b74f-383">[**脅威管理**] ダッシュボードのユーザーによって報告されたメッセージに移動 \> **Dashboard** \> **User-reported messages**します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-383">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="4b74f-384">[**脅威の管理**] に移動して \> **Review** \> **、ユーザーから報告**されたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b74f-384">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ & コンプライアンスセンターで、[脅威管理] [ \> ユーザーが報告するメッセージを確認する] を選択します。 \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="4b74f-386">ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の **監査ログを有効にする必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-386">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="4b74f-387">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="4b74f-387">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="4b74f-388">詳細については、「 [Microsoft 365 監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-388">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4b74f-389">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="4b74f-389">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4b74f-390">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター **および** Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-390">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="4b74f-391">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-391">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="4b74f-392">-組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="4b74f-392">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="4b74f-393">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-393">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="4b74f-394">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b74f-394">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="4b74f-395">-組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="4b74f-395">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="4b74f-396">詳細については、「exchange online の [アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-396">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4b74f-397">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="4b74f-397">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4b74f-398">レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-398">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4b74f-399">詳細については、「 [脅威からの保護](protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b74f-399">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b74f-400">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b74f-400">Related topics</span></span>

[<span data-ttu-id="4b74f-401">EOP でのスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="4b74f-401">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="4b74f-402">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="4b74f-402">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4b74f-403">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4b74f-403">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="4b74f-404">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4b74f-404">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
