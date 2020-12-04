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
ms.openlocfilehash: 1ab78f17cd5689f9110227762c149d3691433179
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572563"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="9c9a0-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="9c9a0-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9c9a0-105">[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールセキュリティ機能が組織を保護していることを確認するのに役立つさまざまなレポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="9c9a0-106">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート** ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard** ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="9c9a0-107">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="9c9a0-109">侵害されたユーザーレポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="9c9a0-110">このレポートは、Microsoft 365 組織の Exchange Online メールボックスを使用して利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="9c9a0-111">これは、スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="9c9a0-112">侵害された **ユーザー** のレポートには、過去7日間以内に **疑わしい** または **制限** されたユーザーアカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="9c9a0-113">これらの状態のいずれかのアカウントは、問題が発生しているか、侵害されています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="9c9a0-114">よく使用されるので、レポートを使用して、不審なアカウントや制限付きのアカウントでスパイクや傾向を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="9c9a0-115">侵害されたユーザーの詳細については、「 [危害を受けた電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポートダッシュボードの侵害されたユーザーウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="9c9a0-117">集計ビューには過去90日間のデータが表示され、詳細ビューには過去30日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="9c9a0-118">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して、[侵害された **ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="9c9a0-119">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=CompromisedUsers> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="9c9a0-120">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9c9a0-121">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="9c9a0-122">**疑わしい**: ユーザーアカウントは、不審な電子メールを送信しているため、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="9c9a0-123">**制限**: 非常に疑わしいパターンがあるため、ユーザーアカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザーレポートのレポートビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="9c9a0-125">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9c9a0-126">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-126">**Creation time**</span></span>
- <span data-ttu-id="9c9a0-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-127">**User ID**</span></span>
- <span data-ttu-id="9c9a0-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-128">**Action**</span></span>

<span data-ttu-id="9c9a0-129">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="9c9a0-130">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-130">Encryption report</span></span>

<span data-ttu-id="9c9a0-131">**暗号化レポート** は、EOP (exchange online またはスタンドアロン EOP の exchange online メールボックスなしのメールボックスを使用したサブスクリプション) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="9c9a0-132">組織のセキュリティチームは、このレポートの情報を使用して、パターンを識別し、機密性の高い電子メールメッセージのポリシーを事前に適用または調整することができます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="9c9a0-133">例:</span><span class="sxs-lookup"><span data-stu-id="9c9a0-133">For example:</span></span>

- <span data-ttu-id="9c9a0-134">ユーザーによって大量の電子メールメッセージが暗号化されている場合、暗号化ポリシーを追加して、特定のユースケースの暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="9c9a0-135">詳細については、「 [Microsoft 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="9c9a0-136">使用可能な暗号化テンプレートが多数あり、それを使用しているものがない場合は、ユーザーが機能のトレーニングを必要としているかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="9c9a0-137">集計ビューでは、過去90日間のフィルターを使用でき、詳細ビューでは10日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="9c9a0-138">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **暗号化レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="9c9a0-139">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=EncryptionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="9c9a0-140">暗号化の詳細については、「 [Microsoft 365 の電子メールの暗号化](../../compliance/email-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="9c9a0-141">暗号化レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-141">Report view for the Encryption report</span></span>

<span data-ttu-id="9c9a0-142">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="9c9a0-143">**データの表示: メッセージの暗号化レポート** と次の **方法で分割** します。暗号化方法: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9c9a0-144">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-144">**Encryption by user**</span></span>
  - <span data-ttu-id="9c9a0-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-145">**Encryption by policy**</span></span>

  <span data-ttu-id="9c9a0-146">[ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-147">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-148">Encryption method.</span></span>
  - <span data-ttu-id="9c9a0-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-149">Encryption template.</span></span>

- <span data-ttu-id="9c9a0-150">**データの表示形式: メッセージの暗号化レポート** と **分解: 暗号化テンプレート**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="9c9a0-151">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-151">**Do not forward**</span></span>
  - <span data-ttu-id="9c9a0-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-152">**Encrypt only**</span></span>
  - <span data-ttu-id="9c9a0-153">**OME previous**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-153">**OME previous**</span></span>
  - <span data-ttu-id="9c9a0-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-154">**Custom**</span></span>

  <span data-ttu-id="9c9a0-155">[ **フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-156">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="9c9a0-157">Encryption method</span></span>
  - <span data-ttu-id="9c9a0-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-158">Encryption template</span></span>

- <span data-ttu-id="9c9a0-159">**データの表示形式: 上位5受信者ドメイン**: このビューには、上位5受信者ドメインの送信されたメッセージ数が円グラフで表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="9c9a0-160">[ **フィルター**] をクリックすると、 **開始日** と **終了日** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="9c9a0-161">暗号化レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="9c9a0-162">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9c9a0-163">**下に移動: 暗号化方法** または次のよう **に分割します。暗号化テンプレート**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="9c9a0-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-164">**Date**</span></span>
  - <span data-ttu-id="9c9a0-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-165">**Sender address**</span></span>
  - <span data-ttu-id="9c9a0-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-166">**Encryption template**</span></span>
  - <span data-ttu-id="9c9a0-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-167">**Encryption method**</span></span>
  - <span data-ttu-id="9c9a0-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-168">**Recipient address**</span></span>
  - <span data-ttu-id="9c9a0-169">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-169">**Subject**</span></span>

- <span data-ttu-id="9c9a0-170">**データの表示方法: 上位5受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="9c9a0-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="9c9a0-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-171">**Date**</span></span>
  - <span data-ttu-id="9c9a0-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-172">**Recipient domain**</span></span>
  - <span data-ttu-id="9c9a0-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-173">**Message count**</span></span>

<span data-ttu-id="9c9a0-174">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9c9a0-175">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="9c9a0-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="9c9a0-176">Encryption method</span></span>
- <span data-ttu-id="9c9a0-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-177">Encryption template</span></span>

<span data-ttu-id="9c9a0-178">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="9c9a0-179">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-179">Mailflow status report</span></span>

<span data-ttu-id="9c9a0-180">**メールフロー status レポート** には、マルウェア、スパム、フィッシングおよびエッジブロックされたメッセージに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="9c9a0-181">詳細については、「 [メールフロー status report](view-mail-flow-reports.md#mailflow-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="9c9a0-182">電子メールレポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="9c9a0-182">Malware detections in email report</span></span>

<span data-ttu-id="9c9a0-183">**電子メールのマルウェア検出** レポートには、受信および送信電子メールメッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) でのマルウェアの検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="9c9a0-184">EOP でのマルウェア保護の詳細については、「 [EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="9c9a0-185">集計ビューのフィルターでは90日間が許可されますが、詳細テーブルのフィルターでは10日間しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="9c9a0-186">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> ] **ダッシュボード** に移動して、[ **電子メールでマルウェアの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="9c9a0-187">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MalwareDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポートダッシュボードの電子メールウィジェットでのマルウェアの検出](../../media/malware-detections-widget.png)

<span data-ttu-id="9c9a0-189">[ **フィルター** ] をクリックして、次のものを選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="9c9a0-190">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="9c9a0-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-191">**Inbound**</span></span>
- <span data-ttu-id="9c9a0-192">**向き**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-192">**Outbound**</span></span>

![電子メールレポートでのマルウェア検出のレポートビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="9c9a0-194">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9c9a0-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-195">**Date**</span></span>
- <span data-ttu-id="9c9a0-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-196">**Sender address**</span></span>
- <span data-ttu-id="9c9a0-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-197">**Recipient address**</span></span>
- <span data-ttu-id="9c9a0-198">メッセージ **id**: メッセージヘッダーの **メッセージ id** ヘッダーフィールドで利用可能で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="9c9a0-199">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="9c9a0-200">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-200">**Subject**</span></span>
- <span data-ttu-id="9c9a0-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-201">**Filename**</span></span>
- <span data-ttu-id="9c9a0-202">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-202">**Malware name**</span></span>

<span data-ttu-id="9c9a0-203">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="9c9a0-204">メール待機時間レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-204">Mail latency report</span></span>

<span data-ttu-id="9c9a0-205">**メール待機時間レポート** には、組織内で発生したメール配信および分析待機時間に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="9c9a0-206">詳細については、「 [メール待機時間レポート](view-reports-for-atp.md#mail-latency-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="9c9a0-207">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-207">Sent and received email report</span></span>

<span data-ttu-id="9c9a0-208">**送信および受信した電子メール** レポートには、マルウェア、スパム、メールフロールール (トランスポートルールとも呼ばれる) に関する情報と、電子メールがサービスに入った後の高度なマルウェアの検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="9c9a0-209">詳細については、「 [送信および受信した電子メールレポート](view-mail-flow-reports.md#sent-and-received-email-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="9c9a0-210">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-210">Spam detections report</span></span>

<span data-ttu-id="9c9a0-211">**スパム検出** レポートには、EOP によってブロックされたスパム電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="9c9a0-212">メッセージは、受信者ごとではなく個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="9c9a0-213">たとえば、同じスパムメッセージが組織内の100の受信者に送信された場合は、1つのメッセージとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="9c9a0-214">集計ビューでは90日間のフィルター処理が可能で、詳細テーブルでは10日のフィルター処理が許可されています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="9c9a0-215">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard** て、[**スパム検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="9c9a0-216">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpamDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポートダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="9c9a0-218">スパム対策保護の詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="9c9a0-219">スパム検出レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="9c9a0-220">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9c9a0-221">**分割ダウン: アクション**: 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="9c9a0-222">**スパムコンテンツのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="9c9a0-223">**スパム IP 禁止**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-223">**Spam IP block**</span></span>
  - <span data-ttu-id="9c9a0-224">**スパムの封筒ブロック**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="9c9a0-225">**スパム dbeb フィルター**: ディレクトリベースのエッジブロック (dbeb)</span><span class="sxs-lookup"><span data-stu-id="9c9a0-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="9c9a0-226">グラフの1日 (データポイント) にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクションビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="9c9a0-228">次のよう **に分割します。方向**: 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="9c9a0-229">**受信**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-229">**Inbound**</span></span>
  - <span data-ttu-id="9c9a0-230">**向き**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-230">**Outbound**</span></span>

  ![スパム検出レポートでの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="9c9a0-232">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9c9a0-233">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="9c9a0-234">Direction 値</span><span class="sxs-lookup"><span data-stu-id="9c9a0-234">Direction values</span></span>
- <span data-ttu-id="9c9a0-235">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="9c9a0-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="9c9a0-236">スパム検出レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="9c9a0-237">いずれかのレポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="9c9a0-238">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-238">**Date**</span></span>
- <span data-ttu-id="9c9a0-239">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-239">**Sender address**</span></span>
- <span data-ttu-id="9c9a0-240">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-240">**Recipient address**</span></span>
- <span data-ttu-id="9c9a0-241">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-241">**Event type**</span></span>
- <span data-ttu-id="9c9a0-242">**操作**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-242">**Action**</span></span>
- <span data-ttu-id="9c9a0-243">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-243">**Subject**</span></span>

<span data-ttu-id="9c9a0-244">詳細テーブルで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9c9a0-245">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="9c9a0-246">Direction 値</span><span class="sxs-lookup"><span data-stu-id="9c9a0-246">Direction values</span></span>
- <span data-ttu-id="9c9a0-247">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="9c9a0-247">Event type values</span></span>

<span data-ttu-id="9c9a0-248">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="9c9a0-249">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-249">Spoof detections report</span></span>

<span data-ttu-id="9c9a0-250">**スプーフィング検出** レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="9c9a0-251">スプーフィングの詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="9c9a0-252">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="9c9a0-253">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard** て、[**スプーフィング検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="9c9a0-254">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpoofMailReport> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポートダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="9c9a0-256">グラフの1日 (データポイント) にカーソルを置くと、受信したスプーフィングメールメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="9c9a0-257">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="9c9a0-258">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="9c9a0-259">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-259">**Good mail**</span></span>

- <span data-ttu-id="9c9a0-260">**スパムとして検出された**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-260">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポートビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="9c9a0-262">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9c9a0-263">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-263">**Date**</span></span>
- <span data-ttu-id="9c9a0-264">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-264">**Spoofed sender**</span></span>
- <span data-ttu-id="9c9a0-265">**True 送信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-265">**True sender**</span></span>
- <span data-ttu-id="9c9a0-266">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="9c9a0-266">**Sender IP**</span></span>
- <span data-ttu-id="9c9a0-267">**操作**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-267">**Action**</span></span>
- <span data-ttu-id="9c9a0-268">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-268">**Message count**</span></span>

<span data-ttu-id="9c9a0-269">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="9c9a0-270">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-270">Threat protection status report</span></span>

<span data-ttu-id="9c9a0-271">**脅威保護の状態** レポートは、EOP と Microsoft Defender for Office 365 の両方で使用できます。ただし、レポートには異なるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="9c9a0-272">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)によって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9c9a0-273">このレポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、 [ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Office 365 機能 ( [安全なリンク](atp-safe-links.md)、 [安全な添付ファイル](atp-safe-attachments.md)、 [フィッシング詐欺対策](set-up-anti-phishing-policies.md)など) などの悪意のあるコンテンツを含む電子メールメッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="9c9a0-274">この情報を使用して、傾向を特定したり、組織のポリシーを調整する必要があるかどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="9c9a0-275">**注**: メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="9c9a0-276">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard** て、[**脅威保護の状態**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="9c9a0-277">レポートに直接移動するには、次のいずれかの Url を開きます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="9c9a0-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="9c9a0-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="9c9a0-279">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="9c9a0-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポートダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="9c9a0-281">既定では、グラフに過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="9c9a0-282">[ **フィルター**] をクリックした場合は、90日の日付の範囲を選択できます (試用版のサブスクリプションは30日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="9c9a0-283">詳細テーブルビューでは、30日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9c9a0-284">脅威保護状態レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="9c9a0-285">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-285">The following views are available:</span></span>

- <span data-ttu-id="9c9a0-286">**データの表示: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="9c9a0-287">**メールマルウェア**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-287">**Email malware**</span></span>
  - <span data-ttu-id="9c9a0-288">**電子メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-288">**Email phish**</span></span>
  - <span data-ttu-id="9c9a0-289">**コンテンツマルウェア**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-289">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="9c9a0-291">**データの表示方法: コンテンツ \> マルウェア**<sup>1</sup>: Microsoft Defender for Office 365 組織の場合は、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="9c9a0-292">**マルウェア対策エンジン**: [microsoft 365 の組み込みのウイルス検出](virus-detection-in-spo.md)によって、Sharepoint、OneDrive、microsoft Teams で検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="9c9a0-293">**ファイル分析**: [Sharepoint、OneDrive、Microsoft Teams の ATP](atp-for-spo-odb-and-teams.md)によって検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![脅威保護状態レポートのコンテンツマルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="9c9a0-295">**データの表示方法: メッセージの上書き**: 次のオーバーライドの理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="9c9a0-296">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-296">**On-premises skip**</span></span>
  - <span data-ttu-id="9c9a0-297">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-297">**IP Allow**</span></span>
  - <span data-ttu-id="9c9a0-298">**メールフロールール**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="9c9a0-299">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-299">**Sender allow**</span></span>
  - <span data-ttu-id="9c9a0-300">**ドメイン許可**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-300">**Domain allow**</span></span>
  - <span data-ttu-id="9c9a0-301">**ZAP が無効**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="9c9a0-302">**迷惑メールフォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="9c9a0-303">**ユーザーの信頼できる差出人**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="9c9a0-304">**ユーザーの安全なドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-304">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージ上書きの表示](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="9c9a0-306">**下に移動: 検出テクノロジ** と **View data: Email \> フィッシング**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="9c9a0-307">**ATP が生成した url 評価**<sup>1</sup>: 他の Microsoft 365 お客様のために、Defender (Office 365 detonations) から生成された悪意のある url 評価。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="9c9a0-308">**Advanced フィッシング filter**: コンピューター学習に基づくフィッシング信号。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="9c9a0-309">**DMARC の失敗**: メッセージの DMARC 認証が失敗した。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="9c9a0-310">**組織内のスプーフィング**: Sender が受信者ドメインのスプーフィングを試行しています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="9c9a0-311">**スプーフィング防止-外部ドメイン**: 送信者が他のドメインのスプーフィングを試行しています。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="9c9a0-312">**ブランド偽装**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="9c9a0-313">**ドメイン偽装**<sup>1</sup>: お客様が所有または定義しているドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="9c9a0-314">**EOP url 評価**: 悪意のある url の評価。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="9c9a0-315">**General フィッシング filter**: アナリストルールに基づいたフィッシング信号。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="9c9a0-316">**Others**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-316">**Others**</span></span>
  - <span data-ttu-id="9c9a0-317">**フィッシング ZAP**<sup>2</sup>: 0 時間のフィッシングメッセージの自動削除。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="9c9a0-318">**URL 分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9c9a0-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="9c9a0-319">**ユーザー偽装**<sup>1</sup>: 管理者によって定義されたユーザーの偽装またはメールボックスインテリジェンスによる学習。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="9c9a0-321">**分割ダウン: 検出テクノロジ** と **データの表示者: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9c9a0-322">**ATP で生成されたファイル評価**<sup>1</sup>: Defender が Office 365 detonations に対して生成した悪意のあるファイルの評価。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="9c9a0-323">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="9c9a0-324">**マルウェア対策ポリシーファイルの種類のブロック**: これらは、メッセージで特定された悪意のあるファイルの種類によってフィルター処理された電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="9c9a0-325">**ファイル分析**<sup>1</sup>: 安全な添付ファイルによる検出。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="9c9a0-326">**悪意のあるファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="9c9a0-327">**マルウェアの ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9c9a0-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="9c9a0-328">**Others**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-328">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="9c9a0-330">**分割ダウン: Policy type** and **view Data by: Email \> フィッシング** Or **view data by: email \> マル**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9c9a0-331">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-331">**Anti-malware**</span></span>
  - <span data-ttu-id="9c9a0-332">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9c9a0-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="9c9a0-333">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-333">**Anti-phish**</span></span>
  - <span data-ttu-id="9c9a0-334">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-334">**Anti-spam**</span></span>
  - <span data-ttu-id="9c9a0-335">**メールフロールール** (トランスポートルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="9c9a0-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="9c9a0-336">**Others**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-336">**Others**</span></span>

  ![脅威保護の状態レポートに表示されるフィッシング電子メールのポリシーの種類](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="9c9a0-338">**分割ダウン: 配信状態** および **表示データ: 電子メールの \> フィッシング** または **view by: email \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="9c9a0-339">**配信失敗**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-339">**Delivery failed**</span></span>
  - <span data-ttu-id="9c9a0-340">**落下**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-340">**Dropped**</span></span>
  - <span data-ttu-id="9c9a0-341">**転送**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-341">**Forwarded**</span></span>
  - <span data-ttu-id="9c9a0-342">**ホストされているメールボックス: カスタムフォルダー**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="9c9a0-343">**ホストされているメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="9c9a0-344">**ホストされているメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="9c9a0-345">**ホストされているメールボックス: 迷惑**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="9c9a0-346">**オンプレミスサーバー: 配信済み**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="9c9a0-347">**検疫**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-347">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="9c9a0-349"><sup>1</sup> Defender Office 365 のみ</span><span class="sxs-lookup"><span data-stu-id="9c9a0-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="9c9a0-350"><sup>2</sup> ゼロ時間自動削除 (ZAP) は、スタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="9c9a0-351">[ **フィルター**] をクリックすると、使用可能なフィルターは、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9c9a0-352">**データの表示形式: コンテンツ \> マルウェア** は、レポートを **開始日** と **終了日** で変更し、**検出** 値を使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="9c9a0-353">**データの表示方法: メッセージを上書き** するには、次のフィルターを使用してレポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-354">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-355">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-355">**Override Reason**</span></span>
  - <span data-ttu-id="9c9a0-356">**タグ**: 指定されたユーザータグ (優先度アカウントを含む) が適用されているユーザーまたはグループで結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9c9a0-357">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9c9a0-358">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-358">**Domain**</span></span>

- <span data-ttu-id="9c9a0-359">他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-360">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-361">**検出**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-361">**Detection**</span></span>
  - <span data-ttu-id="9c9a0-362">**保護対象**: **ATP** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="9c9a0-363">**タグ**: 指定されたユーザータグ (優先度アカウントを含む) が適用されているユーザーまたはグループで結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9c9a0-364">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9c9a0-365">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="9c9a0-366">脅威保護状態レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="9c9a0-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="9c9a0-367">[ **詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9c9a0-368">**データの表示: 概要**: [ **表示の詳細] テーブル** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="9c9a0-369">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="9c9a0-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="9c9a0-370">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-370">**Date**</span></span>
  - <span data-ttu-id="9c9a0-371">**Location**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-371">**Location**</span></span>
  - <span data-ttu-id="9c9a0-372">**転送者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-372">**Directed by**</span></span>
  - <span data-ttu-id="9c9a0-373">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-373">**Malware name**</span></span>

  <span data-ttu-id="9c9a0-374">このビューで [ **フィルター** ] をクリックすると、レポートを **開始日** と **終了日** で変更することができ、 **検出** 値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="9c9a0-375">**データの表示: メッセージの上書き**:</span><span class="sxs-lookup"><span data-stu-id="9c9a0-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="9c9a0-376">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-376">**Date**</span></span>
  - <span data-ttu-id="9c9a0-377">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-377">**Subject**</span></span>
  - <span data-ttu-id="9c9a0-378">**送信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-378">**Sender**</span></span>
  - <span data-ttu-id="9c9a0-379">**受信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-379">**Recipients**</span></span>
  - <span data-ttu-id="9c9a0-380">**検出者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-380">**Detected by**</span></span>
  - <span data-ttu-id="9c9a0-381">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-381">**Override Reason**</span></span>
  - <span data-ttu-id="9c9a0-382">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="9c9a0-383">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-383">**Tags**</span></span>

  <span data-ttu-id="9c9a0-384">このビューで [ **フィルター** ] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-385">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-386">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-386">**Override Reason**</span></span>
  - <span data-ttu-id="9c9a0-387">**タグ**: 指定されたユーザータグ (優先度アカウントを含む) が適用されているユーザーまたはグループで結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9c9a0-388">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9c9a0-389">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-389">**Domain**</span></span>
  - <span data-ttu-id="9c9a0-390">**受信者** (このフィルター処理可能なプロパティは、詳細テーブルビューでのみ使用可能であることに注意してください)</span><span class="sxs-lookup"><span data-stu-id="9c9a0-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="9c9a0-391">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="9c9a0-391">All other charts:</span></span>

  - <span data-ttu-id="9c9a0-392">**Date**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-392">**Date**</span></span>
  - <span data-ttu-id="9c9a0-393">**Subject**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-393">**Subject**</span></span>
  - <span data-ttu-id="9c9a0-394">**送信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-394">**Sender**</span></span>
  - <span data-ttu-id="9c9a0-395">**受信者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-395">**Recipients**</span></span>
  - <span data-ttu-id="9c9a0-396">**検出者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-396">**Detected by**</span></span>
  - <span data-ttu-id="9c9a0-397">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-397">**Delivery Status**</span></span>
  - <span data-ttu-id="9c9a0-398">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="9c9a0-399">**Tags**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-399">**Tags**</span></span>

  <span data-ttu-id="9c9a0-400">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="9c9a0-401">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="9c9a0-402">**検出**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-402">**Detection**</span></span>
  - <span data-ttu-id="9c9a0-403">**保護者**: **Defender for Office 365** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="9c9a0-404">**タグ**: 指定されたユーザータグ (優先度アカウントを含む) が適用されているユーザーまたはグループで結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="9c9a0-405">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="9c9a0-406">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-406">**Domain**</span></span>
  - <span data-ttu-id="9c9a0-407">**受信者** (このフィルター処理可能なプロパティは、詳細テーブルビューでのみ使用可能であることに注意してください)</span><span class="sxs-lookup"><span data-stu-id="9c9a0-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="9c9a0-408">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-408">Top malware report</span></span>

<span data-ttu-id="9c9a0-409">**上位マルウェア** レポートには、 [EOP でマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="9c9a0-410">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート**] \> **ダッシュボード** に移動して [ **上位マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="9c9a0-411">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopMalware> ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポートダッシュボードのトップマルウェアウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="9c9a0-413">円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップマルウェアレポートビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="9c9a0-415">[ **詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="9c9a0-416">**上位マルウェア**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-416">**Top malware**</span></span>
- <span data-ttu-id="9c9a0-417">**Count**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-417">**Count**</span></span>

<span data-ttu-id="9c9a0-418">レポートビューまたは詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始** 日と **終了日** を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="9c9a0-419">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-419">URL threat protection report</span></span>

<span data-ttu-id="9c9a0-420">Office 365 の Microsoft Defender では、 **URL の脅威保護レポート** を利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9c9a0-421">詳細については、「 [URL の脅威保護レポート](view-reports-for-atp.md#url-threat-protection-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="9c9a0-422">ユーザーによって報告されたメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="9c9a0-422">User-reported messages report</span></span>

<span data-ttu-id="9c9a0-423">ユーザーによって報告された **メッセージ** レポートには、ユーザーが [レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="9c9a0-424">組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="9c9a0-425">詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[ **概要** ] タブと [ **詳細** ] タブで情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![User-Reported Messages レポートには、ユーザーが迷惑メール、迷惑メールではないというラベルが付けられたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="9c9a0-427">このレポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="9c9a0-428">[**脅威管理**] ダッシュボードのユーザーによって報告されたメッセージに移動 \> **Dashboard** \> **User-reported messages** します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="9c9a0-429">[**脅威の管理**] に移動して \> **Review** \> **、ユーザーから報告** されたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ & コンプライアンスセンターで、[脅威管理] [ \> ユーザーが報告するメッセージを確認する] を選択します。 \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="9c9a0-431">ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の **監査ログを有効にする必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="9c9a0-432">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="9c9a0-433">詳細については、「 [Microsoft 365 監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="9c9a0-434">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="9c9a0-435">このトピックで説明されているレポートを表示して使用するには、セキュリティ & コンプライアンスセンターの次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-435">In order to view and use the reports described in this topic, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9c9a0-436">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-436">**Organization Management**</span></span>
- <span data-ttu-id="9c9a0-437">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-437">**Security Administrator**</span></span>
- <span data-ttu-id="9c9a0-438">**セキュリティリーダ**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-438">**Security Reader**</span></span>
- <span data-ttu-id="9c9a0-439">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="9c9a0-439">**Global Reader**</span></span>

<span data-ttu-id="9c9a0-440">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-440">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="9c9a0-441">**注**: microsoft 365 管理センターで対応する Azure Active Directory の役割にユーザーを追加すると、セキュリティ & コンプライアンスセンター _と_ 、microsoft 365 の他の機能に対するアクセス許可で必要なアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-441">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9c9a0-442">詳細については、[「管理者の役割について」](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-442">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="9c9a0-443">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-443">What if the reports aren't showing data?</span></span>

<span data-ttu-id="9c9a0-444">レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-444">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="9c9a0-445">詳細については、「 [脅威からの保護](protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c9a0-445">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9c9a0-446">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c9a0-446">Related topics</span></span>

[<span data-ttu-id="9c9a0-447">EOP でのスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="9c9a0-447">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="9c9a0-448">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="9c9a0-448">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="9c9a0-449">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="9c9a0-449">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="9c9a0-450">Defender for Office 365 のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="9c9a0-450">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
