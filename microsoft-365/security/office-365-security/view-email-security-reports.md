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
ms.openlocfilehash: fafb499e40c0014a85c9566b3e5aadf2751202a1
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941477"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="49ef0-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="49ef0-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="49ef0-105">[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールセキュリティ機能が組織を保護していることを確認するのに役立つさまざまなレポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="49ef0-106">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、 **レポート** ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard** ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="49ef0-107">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="49ef0-109">侵害されたユーザーレポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="49ef0-110">このレポートは、Microsoft 365 組織の Exchange Online メールボックスを使用して利用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="49ef0-111">これは、スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="49ef0-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="49ef0-112">侵害された **ユーザー** のレポートには、過去7日間以内に **疑わしい** または **制限** されたユーザーアカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="49ef0-113">これらの状態のいずれかのアカウントは、問題が発生しているか、侵害されています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="49ef0-114">よく使用されるので、レポートを使用して、不審なアカウントや制限付きのアカウントでスパイクや傾向を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="49ef0-115">侵害されたユーザーの詳細については、「 [危害を受けた電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポートダッシュボードの侵害されたユーザーウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="49ef0-117">集計ビューには過去90日間のデータが表示され、詳細ビューには過去30日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="49ef0-118">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** ] \> **ダッシュボード** に移動して、[侵害された **ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="49ef0-119">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=CompromisedUsers> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="49ef0-120">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="49ef0-121">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="49ef0-122">**疑わしい** : ユーザーアカウントは、不審な電子メールを送信しているため、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-122">**Suspicious** : The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="49ef0-123">**制限** : 非常に疑わしいパターンがあるため、ユーザーアカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-123">**Restricted** : The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザーレポートのレポートビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="49ef0-125">[ **詳細テーブルの表示** ] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-125">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="49ef0-126">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="49ef0-126">**Creation time**</span></span>
- <span data-ttu-id="49ef0-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-127">**User ID**</span></span>
- <span data-ttu-id="49ef0-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="49ef0-128">**Action**</span></span>

<span data-ttu-id="49ef0-129">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="49ef0-130">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-130">Encryption report</span></span>

<span data-ttu-id="49ef0-131">**暗号化レポート** は、EOP (exchange online またはスタンドアロン EOP の exchange online メールボックスなしのメールボックスを使用したサブスクリプション) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="49ef0-132">組織のセキュリティチームは、このレポートの情報を使用して、パターンを識別し、機密性の高い電子メールメッセージのポリシーを事前に適用または調整することができます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="49ef0-133">例:</span><span class="sxs-lookup"><span data-stu-id="49ef0-133">For example:</span></span>

- <span data-ttu-id="49ef0-134">ユーザーによって大量の電子メールメッセージが暗号化されている場合、暗号化ポリシーを追加して、特定のユースケースの暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="49ef0-135">詳細については、「 [Microsoft 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="49ef0-136">使用可能な暗号化テンプレートが多数あり、それを使用しているものがない場合は、ユーザーが機能のトレーニングを必要としているかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="49ef0-137">集計ビューでは、過去90日間のフィルターを使用でき、詳細ビューでは10日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="49ef0-138">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **暗号化レポート** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="49ef0-139">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=EncryptionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="49ef0-140">暗号化の詳細については、「 [Microsoft 365 の電子メールの暗号化](../../compliance/email-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="49ef0-141">暗号化レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-141">Report view for the Encryption report</span></span>

<span data-ttu-id="49ef0-142">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="49ef0-143">**データの表示: メッセージの暗号化レポート** と次の **方法で分割** します。暗号化方法: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-143">**View data by: Message Encryption Report** and **Break down by: Encryption method** : The following encryption methods are available:</span></span>

  - <span data-ttu-id="49ef0-144">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="49ef0-144">**Encryption by user**</span></span>
  - <span data-ttu-id="49ef0-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="49ef0-145">**Encryption by policy**</span></span>

  <span data-ttu-id="49ef0-146">[ **フィルター** ] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-146">If you click **Filters** , you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="49ef0-147">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="49ef0-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="49ef0-148">Encryption method.</span></span>
  - <span data-ttu-id="49ef0-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="49ef0-149">Encryption template.</span></span>

- <span data-ttu-id="49ef0-150">**データの表示形式: メッセージの暗号化レポート** と **分解: 暗号化テンプレート** : 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-150">**View data by: Message Encryption Report** and **Break down by: Encryption template** : The following encryption methods are available:</span></span>

  - <span data-ttu-id="49ef0-151">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="49ef0-151">**Do not forward**</span></span>
  - <span data-ttu-id="49ef0-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="49ef0-152">**Encrypt only**</span></span>
  - <span data-ttu-id="49ef0-153">**OME previous**</span><span class="sxs-lookup"><span data-stu-id="49ef0-153">**OME previous**</span></span>
  - <span data-ttu-id="49ef0-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="49ef0-154">**Custom**</span></span>

  <span data-ttu-id="49ef0-155">[ **フィルター** ] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-155">If you click **Filters** , you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="49ef0-156">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="49ef0-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="49ef0-157">Encryption method</span></span>
  - <span data-ttu-id="49ef0-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="49ef0-158">Encryption template</span></span>

- <span data-ttu-id="49ef0-159">**データの表示形式: 上位5受信者ドメイン** : このビューには、上位5受信者ドメインの送信されたメッセージ数が円グラフで表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-159">**View data by: Top 5 recipient domains** : This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="49ef0-160">[ **フィルター** ] をクリックすると、 **開始日** と **終了日** を選択できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-160">If you click **Filters** , you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="49ef0-161">暗号化レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="49ef0-162">[ **詳細テーブルの表示** ] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-162">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="49ef0-163">**下に移動: 暗号化方法** または次のよう **に分割します。暗号化テンプレート** : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-163">**Break down by: Encryption method** or **Break down by: Encryption template** : The following information is shown:</span></span>

  - <span data-ttu-id="49ef0-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-164">**Date**</span></span>
  - <span data-ttu-id="49ef0-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-165">**Sender address**</span></span>
  - <span data-ttu-id="49ef0-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="49ef0-166">**Encryption template**</span></span>
  - <span data-ttu-id="49ef0-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="49ef0-167">**Encryption method**</span></span>
  - <span data-ttu-id="49ef0-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="49ef0-168">**Recipient address**</span></span>
  - <span data-ttu-id="49ef0-169">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-169">**Subject**</span></span>

- <span data-ttu-id="49ef0-170">**データの表示方法: 上位5受信者ドメイン** :</span><span class="sxs-lookup"><span data-stu-id="49ef0-170">**View data by: Top 5 recipient domains** :</span></span>

  - <span data-ttu-id="49ef0-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-171">**Date**</span></span>
  - <span data-ttu-id="49ef0-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-172">**Recipient domain**</span></span>
  - <span data-ttu-id="49ef0-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="49ef0-173">**Message count**</span></span>
  
<span data-ttu-id="49ef0-174">詳細テーブルビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="49ef0-175">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="49ef0-176">Encryption method</span></span>
- <span data-ttu-id="49ef0-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="49ef0-177">Encryption template</span></span>

<span data-ttu-id="49ef0-178">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="49ef0-179">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-179">Mailflow status report</span></span>

<span data-ttu-id="49ef0-180">**メールフロー status レポート** には、マルウェア、スパム、フィッシングおよびエッジブロックされたメッセージに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="49ef0-181">詳細については、「 [メールフロー status report](view-mail-flow-reports.md#mailflow-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="49ef0-182">電子メールレポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="49ef0-182">Malware detections in email report</span></span>

<span data-ttu-id="49ef0-183">**電子メールのマルウェア検出** レポートには、受信および送信電子メールメッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) でのマルウェアの検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="49ef0-184">EOP でのマルウェア保護の詳細については、「 [EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="49ef0-185">集計ビューのフィルターでは90日間が許可されますが、詳細テーブルのフィルターでは10日間しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="49ef0-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="49ef0-186">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> ] **ダッシュボード** に移動して、[ **電子メールでマルウェアの検出** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="49ef0-187">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MalwareDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポートダッシュボードの電子メールウィジェットでのマルウェアの検出](../../media/malware-detections-widget.png)

<span data-ttu-id="49ef0-189">[ **フィルター** ] をクリックして、次のものを選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="49ef0-190">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="49ef0-191">**Inbound**</span></span>
- <span data-ttu-id="49ef0-192">**向き**</span><span class="sxs-lookup"><span data-stu-id="49ef0-192">**Outbound**</span></span>

![電子メールレポートでのマルウェア検出のレポートビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="49ef0-194">[ **詳細テーブルの表示** ] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-194">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="49ef0-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-195">**Date**</span></span>
- <span data-ttu-id="49ef0-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-196">**Sender address**</span></span>
- <span data-ttu-id="49ef0-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="49ef0-197">**Recipient address**</span></span>
- <span data-ttu-id="49ef0-198">メッセージ **id** : メッセージヘッダーの **メッセージ id** ヘッダーフィールドで利用可能で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-198">**Message ID** : Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="49ef0-199">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="49ef0-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="49ef0-200">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-200">**Subject**</span></span>
- <span data-ttu-id="49ef0-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="49ef0-201">**Filename**</span></span>
- <span data-ttu-id="49ef0-202">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="49ef0-202">**Malware name**</span></span>

<span data-ttu-id="49ef0-203">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="49ef0-204">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-204">Sent and received email report</span></span>

<span data-ttu-id="49ef0-205">**送信および受信した電子メール** レポートには、マルウェア、スパム、メールフロールール (トランスポートルールとも呼ばれる) に関する情報と、電子メールがサービスに入った後の高度なマルウェアの検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="49ef0-206">詳細については、「 [送信および受信した電子メールレポート](view-mail-flow-reports.md#sent-and-received-email-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="49ef0-207">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-207">Spam detections report</span></span>

<span data-ttu-id="49ef0-208">**スパム検出** レポートには、EOP によってブロックされたスパム電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="49ef0-209">メッセージは、受信者ごとではなく個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="49ef0-210">たとえば、同じスパムメッセージが組織内の100の受信者に送信された場合は、1つのメッセージとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="49ef0-211">集計ビューでは90日間のフィルター処理が可能で、詳細テーブルでは10日のフィルター処理が許可されています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="49ef0-212">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** ] ダッシュボードに移動し \> **Dashboard** て、[ **スパム検出** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="49ef0-213">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpamDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポートダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="49ef0-215">スパム対策保護の詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="49ef0-216">スパム検出レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="49ef0-217">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="49ef0-218">**分割ダウン: アクション** : 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-218">**Break down by: Action** : The following event types are shown:</span></span>

  - <span data-ttu-id="49ef0-219">**スパムコンテンツのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="49ef0-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="49ef0-220">**スパム IP 禁止**</span><span class="sxs-lookup"><span data-stu-id="49ef0-220">**Spam IP block**</span></span>
  - <span data-ttu-id="49ef0-221">**スパムの封筒ブロック**</span><span class="sxs-lookup"><span data-stu-id="49ef0-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="49ef0-222">**スパム dbeb フィルター** : ディレクトリベースのエッジブロック (dbeb)</span><span class="sxs-lookup"><span data-stu-id="49ef0-222">**Spam DBEB filter** : Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="49ef0-223">グラフの1日 (データポイント) にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクションビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="49ef0-225">次のよう **に分割します。方向** : 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-225">**Break down by: Direction** : The following directions are shown:</span></span>

  - <span data-ttu-id="49ef0-226">**受信**</span><span class="sxs-lookup"><span data-stu-id="49ef0-226">**Inbound**</span></span>
  - <span data-ttu-id="49ef0-227">**向き**</span><span class="sxs-lookup"><span data-stu-id="49ef0-227">**Outbound**</span></span>

  ![スパム検出レポートでの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="49ef0-229">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="49ef0-230">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-231">Direction 値</span><span class="sxs-lookup"><span data-stu-id="49ef0-231">Direction values</span></span>
- <span data-ttu-id="49ef0-232">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="49ef0-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="49ef0-233">スパム検出レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="49ef0-234">いずれかのレポートビューで [ **詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="49ef0-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-235">**Date**</span></span>
- <span data-ttu-id="49ef0-236">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-236">**Sender address**</span></span>
- <span data-ttu-id="49ef0-237">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="49ef0-237">**Recipient address**</span></span>
- <span data-ttu-id="49ef0-238">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="49ef0-238">**Event type**</span></span>
- <span data-ttu-id="49ef0-239">**操作**</span><span class="sxs-lookup"><span data-stu-id="49ef0-239">**Action**</span></span>
- <span data-ttu-id="49ef0-240">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-240">**Subject**</span></span>

<span data-ttu-id="49ef0-241">詳細テーブルで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="49ef0-242">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-243">Direction 値</span><span class="sxs-lookup"><span data-stu-id="49ef0-243">Direction values</span></span>
- <span data-ttu-id="49ef0-244">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="49ef0-244">Event type values</span></span>

<span data-ttu-id="49ef0-245">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="49ef0-246">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-246">Spoof detections report</span></span>

<span data-ttu-id="49ef0-247">**スプーフィング検出** レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="49ef0-248">スプーフィングの詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="49ef0-249">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="49ef0-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="49ef0-250">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** ] ダッシュボードに移動し \> **Dashboard** て、[ **スプーフィング検出** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="49ef0-251">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpoofMailReport> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポートダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="49ef0-253">グラフの1日 (データポイント) にカーソルを置くと、受信したスプーフィングメールメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="49ef0-254">[ **フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="49ef0-255">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="49ef0-256">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="49ef0-256">**Good mail**</span></span>

- <span data-ttu-id="49ef0-257">**スパムとして検出された**</span><span class="sxs-lookup"><span data-stu-id="49ef0-257">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポートビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="49ef0-259">[ **詳細テーブルの表示** ] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-259">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="49ef0-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-260">**Date**</span></span>
- <span data-ttu-id="49ef0-261">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-261">**Spoofed sender**</span></span>
- <span data-ttu-id="49ef0-262">**True 送信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-262">**True sender**</span></span>
- <span data-ttu-id="49ef0-263">[ **Sender IP (送信者の IP)** ]</span><span class="sxs-lookup"><span data-stu-id="49ef0-263">**Sender IP**</span></span>
- <span data-ttu-id="49ef0-264">**操作**</span><span class="sxs-lookup"><span data-stu-id="49ef0-264">**Action**</span></span>
- <span data-ttu-id="49ef0-265">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="49ef0-265">**Message count**</span></span>

<span data-ttu-id="49ef0-266">レポートビューに戻るには、[ **レポートの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="49ef0-267">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-267">Threat protection status report</span></span>

<span data-ttu-id="49ef0-268">**脅威保護の状態** レポートは、EOP と Microsoft Defender for Office 365 の両方で使用できます。ただし、レポートには異なるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-268">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="49ef0-269">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint、OneDrive、Microsoft Teams 用の ATP によって検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="49ef0-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected by ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="49ef0-270">このレポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、 [ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Office 365 機能 ( [安全なリンク](atp-safe-links.md)、 [安全な添付ファイル](atp-safe-attachments.md)、 [フィッシング詐欺対策](set-up-anti-phishing-policies.md)など) などの悪意のあるコンテンツを含む電子メールメッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="49ef0-271">この情報を使用して、傾向を特定したり、組織のポリシーを調整する必要があるかどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="49ef0-272">メッセージが5人の受信者に送信される場合は、メッセージを5つの異なるメッセージとしてカウントし、1つのメッセージではないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="49ef0-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="49ef0-273">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** ] ダッシュボードに移動し \> **Dashboard** て、[ **脅威保護の状態** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="49ef0-274">レポートに直接移動するには、次のいずれかの Url を開きます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="49ef0-275">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="49ef0-275">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="49ef0-276">EOP <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="49ef0-276">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポートダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="49ef0-278">既定では、グラフに過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="49ef0-279">[ **フィルター** ] をクリックした場合は、90日の日付の範囲を選択できます (試用版のサブスクリプションは30日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="49ef0-279">If you click **Filters** , you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="49ef0-280">詳細テーブルビューでは、30日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="49ef0-281">脅威保護状態レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="49ef0-282">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-282">The following views are available:</span></span>

- <span data-ttu-id="49ef0-283">**データの表示: 概要** : 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-283">**View data by: Overview** : The following detection information is shown:</span></span>

  - <span data-ttu-id="49ef0-284">**メールマルウェア**</span><span class="sxs-lookup"><span data-stu-id="49ef0-284">**Email malware**</span></span>
  - <span data-ttu-id="49ef0-285">**電子メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="49ef0-285">**Email phish**</span></span>
  - <span data-ttu-id="49ef0-286">**コンテンツマルウェア**</span><span class="sxs-lookup"><span data-stu-id="49ef0-286">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="49ef0-288">**データの表示方法: コンテンツ \> マルウェア**<sup>1</sup>: Microsoft Defender for Office 365 組織の場合は、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="49ef0-289">**マルウェア対策エンジン** : マルウェア対策によって Sharepoint Online、OneDrive、Teams の悪意のあるファイルをキャッチします。</span><span class="sxs-lookup"><span data-stu-id="49ef0-289">**Anti-malware engine** : Catches of malicious files in Sharepoint Online, OneDrive, and Teams by anti-malware.</span></span>
  - <span data-ttu-id="49ef0-290">**ファイル分析** : 安全な添付ファイルによる、Sharepoint Online、OneDrive、Teams 内の悪意のあるファイルの分析。</span><span class="sxs-lookup"><span data-stu-id="49ef0-290">**File detonation** : Detonation of malicious files in Sharepoint Online, OneDrive, and Teams by Safe Attachments.</span></span>

  ![脅威保護状態レポートのコンテンツマルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="49ef0-292">**データの表示方法: メッセージの上書き** : 次のオーバーライドの理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-292">**View data by: Message Override** : The following override reason information is shown:</span></span>

  - <span data-ttu-id="49ef0-293">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="49ef0-293">**On-premises skip**</span></span>
  - <span data-ttu-id="49ef0-294">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="49ef0-294">**IP Allow**</span></span>
  - <span data-ttu-id="49ef0-295">**メールフロールール**</span><span class="sxs-lookup"><span data-stu-id="49ef0-295">**Mail flow rule**</span></span>
  - <span data-ttu-id="49ef0-296">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="49ef0-296">**Sender allow**</span></span>
  - <span data-ttu-id="49ef0-297">**ドメイン許可**</span><span class="sxs-lookup"><span data-stu-id="49ef0-297">**Domain allow**</span></span>
  - <span data-ttu-id="49ef0-298">**ZAP が無効**</span><span class="sxs-lookup"><span data-stu-id="49ef0-298">**ZAP not enabled**</span></span>
  - <span data-ttu-id="49ef0-299">**迷惑メールフォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="49ef0-299">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="49ef0-300">**ユーザーの信頼できる差出人**</span><span class="sxs-lookup"><span data-stu-id="49ef0-300">**User Safe Sender**</span></span>
  - <span data-ttu-id="49ef0-301">**ユーザーの安全なドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-301">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージ上書きの表示](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="49ef0-303">**下に移動: 検出テクノロジ** と **View data: Email \> フィッシング** : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-303">**Break down by: Detection technology** and **View data by: Email \> Phish** : The following information is shown:</span></span>

  - <span data-ttu-id="49ef0-304">**ATP によって生成された url 評価**<sup>1</sup>: defender for office 365 detonations で、office 365 ユーザーの他の defender に対して生成された悪意のある url 評価。</span><span class="sxs-lookup"><span data-stu-id="49ef0-304">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Defender for Office 365 customers.</span></span>
  - <span data-ttu-id="49ef0-305">**Advanced フィッシング filter** : コンピューター学習に基づくフィッシング信号。</span><span class="sxs-lookup"><span data-stu-id="49ef0-305">**Advanced phish filter** : Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="49ef0-306">**DMARC の失敗** : メッセージの DMARC 認証が失敗した。</span><span class="sxs-lookup"><span data-stu-id="49ef0-306">**Anti-spoof - DMARC failure** : DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="49ef0-307">**組織内のスプーフィング** : Sender が受信者ドメインのスプーフィングを試行しています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-307">**Anti-spoof - intra-org** : Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="49ef0-308">**スプーフィング防止-外部ドメイン** : 送信者が他のドメインのスプーフィングを試行しています。</span><span class="sxs-lookup"><span data-stu-id="49ef0-308">**Anti-spoof - external domain** : Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="49ef0-309">**ブランド偽装** : 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="49ef0-309">**Brand impersonation** : Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="49ef0-310">**ドメイン偽装**<sup>1</sup>: お客様が所有または定義しているドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="49ef0-310">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="49ef0-311">**EOP url 評価** : 悪意のある url の評価。</span><span class="sxs-lookup"><span data-stu-id="49ef0-311">**EOP URL reputation** : Malicious URL reputation.</span></span>
  - <span data-ttu-id="49ef0-312">**General フィッシング filter** : アナリストルールに基づいたフィッシング信号。</span><span class="sxs-lookup"><span data-stu-id="49ef0-312">**General phish filter** : Phishing signals based on analyst rules.</span></span> 
  - <span data-ttu-id="49ef0-313">**Others**</span><span class="sxs-lookup"><span data-stu-id="49ef0-313">**Others**</span></span>
  - <span data-ttu-id="49ef0-314">**フィッシング ZAP**<sup>2</sup>: 0 時間自動削除フィッシングメッセージ。</span><span class="sxs-lookup"><span data-stu-id="49ef0-314">**Phish ZAP**<sup>2</sup>: Zero hour auto purge phishing messages.</span></span>
  - <span data-ttu-id="49ef0-315">**URL 分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="49ef0-315">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="49ef0-316">**ユーザー偽装**<sup>1</sup>: 管理者によって定義されたユーザーの偽装またはメールボックスインテリジェンスによる学習。</span><span class="sxs-lookup"><span data-stu-id="49ef0-316">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="49ef0-318">**分割ダウン: 検出テクノロジ** と **データの表示者: 電子メール \> マルウェア** : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-318">**Break down by: Detection technology** and **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="49ef0-319">**ATP で生成されたファイル評価**<sup>1</sup>: Defender が Office 365 detonations に対して生成した悪意のあるファイルの評価。</span><span class="sxs-lookup"><span data-stu-id="49ef0-319">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="49ef0-320">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="49ef0-320">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="49ef0-321">**マルウェア対策ポリシーファイルの種類のブロック** : これらは、メッセージで特定された悪意のあるファイルの種類によってフィルター処理された電子メールメッセージです。</span><span class="sxs-lookup"><span data-stu-id="49ef0-321">**Anti-malware policy file type block** : These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="49ef0-322">**ファイル分析**<sup>1</sup>: ファイル分析は、安全な添付ファイルによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-322">**File detonation**<sup>1</sup>: File detonation catches by Safe Attachments.</span></span>  
  - <span data-ttu-id="49ef0-323">**悪意のあるファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="49ef0-323">**Malicious file reputation**</span></span>
  - <span data-ttu-id="49ef0-324">**マルウェアの ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="49ef0-324">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="49ef0-325">**Others**</span><span class="sxs-lookup"><span data-stu-id="49ef0-325">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="49ef0-327">**分割ダウン: Policy type** and **view Data by: Email \> フィッシング** Or **view data by: email \> マル** : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-327">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="49ef0-328">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="49ef0-328">**Anti-malware**</span></span>
  - <span data-ttu-id="49ef0-329">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="49ef0-329">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="49ef0-330">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="49ef0-330">**Anti-phish**</span></span>
  - <span data-ttu-id="49ef0-331">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="49ef0-331">**Anti-spam**</span></span>
  - <span data-ttu-id="49ef0-332">**メールフロールール** (トランスポートルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="49ef0-332">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="49ef0-333">**Others**</span><span class="sxs-lookup"><span data-stu-id="49ef0-333">**Others**</span></span>

  ![脅威保護の状態レポートに表示されるフィッシング電子メールのポリシーの種類](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="49ef0-335">**分割ダウン: 配信状態** および **表示データ: 電子メールの \> フィッシング** または **view by: email \> マルウェア** : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-335">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware** : The following information is shown:</span></span>

  - <span data-ttu-id="49ef0-336">**配信失敗**</span><span class="sxs-lookup"><span data-stu-id="49ef0-336">**Delivery failed**</span></span>
  - <span data-ttu-id="49ef0-337">**落下**</span><span class="sxs-lookup"><span data-stu-id="49ef0-337">**Dropped**</span></span>
  - <span data-ttu-id="49ef0-338">**転送**</span><span class="sxs-lookup"><span data-stu-id="49ef0-338">**Forwarded**</span></span>
  - <span data-ttu-id="49ef0-339">**ホストされているメールボックス: カスタムフォルダー**</span><span class="sxs-lookup"><span data-stu-id="49ef0-339">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="49ef0-340">**ホストされているメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="49ef0-340">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="49ef0-341">**ホストされているメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="49ef0-341">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="49ef0-342">**ホストされているメールボックス: 迷惑**</span><span class="sxs-lookup"><span data-stu-id="49ef0-342">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="49ef0-343">**オンプレミスサーバー: 配信済み**</span><span class="sxs-lookup"><span data-stu-id="49ef0-343">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="49ef0-344">**検疫**</span><span class="sxs-lookup"><span data-stu-id="49ef0-344">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="49ef0-346"><sup>1</sup> Defender Office 365 のみ</span><span class="sxs-lookup"><span data-stu-id="49ef0-346"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="49ef0-347"><sup>2</sup> ゼロ時間自動削除 (ZAP) は、スタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。</span><span class="sxs-lookup"><span data-stu-id="49ef0-347"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="49ef0-348">[ **フィルター** ] をクリックすると、使用可能なフィルターは、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-348">If you click **Filters** , the filters available depends on the chart you were looking at:</span></span>

<span data-ttu-id="49ef0-349">**コンテンツ \> マルウェア** の場合は、 **開始** 日と **終了日** によってレポートを変更し、 **検出** 値を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-349">For **Content \> Malware** , you can modify the report by **Start date** and **End date** , and the **Detection** value.</span></span>

<span data-ttu-id="49ef0-350">**メッセージを上書き** する場合は、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-350">For **Message Override** , you can modify the report with the following filters:</span></span>

- <span data-ttu-id="49ef0-351">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-351">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-352">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="49ef0-352">**Override Reason**</span></span>
- <span data-ttu-id="49ef0-353">**タグ** : タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-353">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="49ef0-354">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-354">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="49ef0-355">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-355">**Domain**</span></span>

<span data-ttu-id="49ef0-356">他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-356">For all other views, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="49ef0-357">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-357">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-358">**検出**</span><span class="sxs-lookup"><span data-stu-id="49ef0-358">**Detection**</span></span>
- <span data-ttu-id="49ef0-359">**保護対象** : **ATP** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="49ef0-359">**Protected by** : **ATP** or **EOP**</span></span>
- <span data-ttu-id="49ef0-360">**タグ** : タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-360">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="49ef0-361">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="49ef0-362">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-362">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="49ef0-363">脅威保護状態レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="49ef0-363">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="49ef0-364">[ **詳細テーブルの表示** ] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-364">If you click **View details table** , the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="49ef0-365">**データの表示方法: コンテンツ \> マルウェア** :</span><span class="sxs-lookup"><span data-stu-id="49ef0-365">**View data by: Content \> Malware** :</span></span>

  - <span data-ttu-id="49ef0-366">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-366">**Date**</span></span>
  - <span data-ttu-id="49ef0-367">**Location**</span><span class="sxs-lookup"><span data-stu-id="49ef0-367">**Location**</span></span>
  - <span data-ttu-id="49ef0-368">**転送者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-368">**Directed by**</span></span>
  - <span data-ttu-id="49ef0-369">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="49ef0-369">**Malware name**</span></span>

<span data-ttu-id="49ef0-370">このビューで [ **フィルター** ] をクリックすると、レポートを **開始日** と **終了日** で変更することができ、 **検出** 値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-370">If you click **Filters** in this view, you can modify the report by **Start date** and **End date** , and the **Detection** value.</span></span>

- <span data-ttu-id="49ef0-371">**データの表示: メッセージの上書き** :</span><span class="sxs-lookup"><span data-stu-id="49ef0-371">**View data by: Message Override** :</span></span>

  - <span data-ttu-id="49ef0-372">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-372">**Date**</span></span>
  - <span data-ttu-id="49ef0-373">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-373">**Subject**</span></span>
  - <span data-ttu-id="49ef0-374">**送信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-374">**Sender**</span></span>
  - <span data-ttu-id="49ef0-375">**受信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-375">**Recipients**</span></span>
  - <span data-ttu-id="49ef0-376">**検出者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-376">**Detected by**</span></span>
  - <span data-ttu-id="49ef0-377">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="49ef0-377">**Override Reason**</span></span>
  - <span data-ttu-id="49ef0-378">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="49ef0-378">**Source of Compromise**</span></span>
  - <span data-ttu-id="49ef0-379">**Tags**</span><span class="sxs-lookup"><span data-stu-id="49ef0-379">**Tags**</span></span>

<span data-ttu-id="49ef0-380">このビューで [ **フィルター** ] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-380">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="49ef0-381">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-381">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-382">**オーバーライドの理由**</span><span class="sxs-lookup"><span data-stu-id="49ef0-382">**Override Reason**</span></span>
- <span data-ttu-id="49ef0-383">**タグ** : タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-383">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="49ef0-384">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-384">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="49ef0-385">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-385">**Domain**</span></span>
- <span data-ttu-id="49ef0-386">**受信者** (このフィルター処理可能なプロパティは、詳細テーブルビューでのみ使用可能であることに注意してください)</span><span class="sxs-lookup"><span data-stu-id="49ef0-386">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

<span data-ttu-id="49ef0-387">**データの表示: 概要** : [ **表示の詳細] テーブル** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="49ef0-387">**View data by: Overview** : No **View details table** button is available.</span></span>

- <span data-ttu-id="49ef0-388">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="49ef0-388">All other charts:</span></span>

  - <span data-ttu-id="49ef0-389">**Date**</span><span class="sxs-lookup"><span data-stu-id="49ef0-389">**Date**</span></span>
  - <span data-ttu-id="49ef0-390">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="49ef0-390">**Subject**</span></span>
  - <span data-ttu-id="49ef0-391">**送信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-391">**Sender**</span></span>
  - <span data-ttu-id="49ef0-392">**受信者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-392">**Recipients**</span></span>
  - <span data-ttu-id="49ef0-393">**検出者**</span><span class="sxs-lookup"><span data-stu-id="49ef0-393">**Detected by**</span></span>
  - <span data-ttu-id="49ef0-394">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="49ef0-394">**Delivery Status**</span></span>
  - <span data-ttu-id="49ef0-395">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="49ef0-395">**Source of Compromise**</span></span>
  - <span data-ttu-id="49ef0-396">**Tags**</span><span class="sxs-lookup"><span data-stu-id="49ef0-396">**Tags**</span></span>

<span data-ttu-id="49ef0-397">[ **フィルター** ] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-397">If you click **Filters** , you can modify the report with the following filters:</span></span>

- <span data-ttu-id="49ef0-398">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="49ef0-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="49ef0-399">**検出**</span><span class="sxs-lookup"><span data-stu-id="49ef0-399">**Detection**</span></span>
- <span data-ttu-id="49ef0-400">**保護者** : **Defender for Office 365** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="49ef0-400">**Protected by** : **Defender for Office 365** or **EOP**</span></span>
- <span data-ttu-id="49ef0-401">**タグ** : タグでフィルター処理して、特定のタグが適用されたユーザーまたはグループを返します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-401">**Tag** : filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="49ef0-402">ユーザータグの詳細については、「 [user tags](user-tags.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-402">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="49ef0-403">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="49ef0-403">**Domain**</span></span>
- <span data-ttu-id="49ef0-404">**受信者** (このフィルター処理可能なプロパティは、詳細テーブルビューでのみ使用可能であることに注意してください)</span><span class="sxs-lookup"><span data-stu-id="49ef0-404">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="49ef0-405">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-405">Top malware report</span></span>

<span data-ttu-id="49ef0-406">**上位マルウェア** レポートには、 [EOP でマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-406">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="49ef0-407">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** ] \> **ダッシュボード** に移動して [ **上位マルウェア** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-407">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="49ef0-408">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopMalware> ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-408">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポートダッシュボードのトップマルウェアウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="49ef0-410">円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-410">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップマルウェアレポートビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="49ef0-412">[ **詳細テーブルの表示** ] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-412">If you click **View details table** , you can see the following details:</span></span>

- <span data-ttu-id="49ef0-413">**上位マルウェア**</span><span class="sxs-lookup"><span data-stu-id="49ef0-413">**Top malware**</span></span>
- <span data-ttu-id="49ef0-414">**Count**</span><span class="sxs-lookup"><span data-stu-id="49ef0-414">**Count**</span></span>

<span data-ttu-id="49ef0-415">レポートビューまたは詳細テーブルビューで [ **フィルター** ] をクリックすると、 **開始** 日と **終了日** を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-415">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="49ef0-416">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-416">URL threat protection report</span></span>

<span data-ttu-id="49ef0-417">Office 365 の Microsoft Defender では、 **URL の脅威保護レポート** を利用できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-417">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="49ef0-418">詳細については、「 [URL の脅威保護レポート](view-reports-for-atp.md#url-threat-protection-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-418">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="49ef0-419">ユーザーによって報告されたメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="49ef0-419">User-reported messages report</span></span>

<span data-ttu-id="49ef0-420">ユーザーによって報告された **メッセージ** レポートには、ユーザーが [レポートメッセージアドイン](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-420">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="49ef0-421">組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-421">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="49ef0-422">詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[ **概要** ] タブと [ **詳細** ] タブで情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-422">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![User-Reported Messages レポートには、ユーザーが迷惑メール、迷惑メールではないというラベルが付けられたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="49ef0-424">このレポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-424">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="49ef0-425">[ **脅威管理** ] ダッシュボードのユーザーによって報告されたメッセージに移動 \> **Dashboard** \> **User-reported messages** します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-425">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="49ef0-426">[ **脅威の管理** ] に移動して \> **Review** \> **、ユーザーから報告** されたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="49ef0-426">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ & コンプライアンスセンターで、[脅威管理] [ \> ユーザーが報告するメッセージを確認する] を選択します。 \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="49ef0-428">ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の **監査ログを有効にする必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-428">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="49ef0-429">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="49ef0-429">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="49ef0-430">詳細については、「 [Microsoft 365 監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-430">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="49ef0-431">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="49ef0-431">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="49ef0-432">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター **および** Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-432">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="49ef0-433">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-433">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="49ef0-434">-組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="49ef0-434">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="49ef0-435">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-435">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="49ef0-436">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="49ef0-436">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="49ef0-437">-組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="49ef0-437">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="49ef0-438">詳細については、「exchange online の [アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) 」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-438">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="49ef0-439">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="49ef0-439">What if the reports aren't showing data?</span></span>

<span data-ttu-id="49ef0-440">レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-440">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="49ef0-441">詳細については、「 [脅威からの保護](protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49ef0-441">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49ef0-442">関連項目</span><span class="sxs-lookup"><span data-stu-id="49ef0-442">Related topics</span></span>

[<span data-ttu-id="49ef0-443">EOP でのスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="49ef0-443">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="49ef0-444">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="49ef0-444">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="49ef0-445">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="49ef0-445">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="49ef0-446">Defender for Office 365 のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="49ef0-446">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
