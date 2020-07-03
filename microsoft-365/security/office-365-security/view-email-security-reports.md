---
title: セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: 6fbaa0b57c888f5eaf90a2a30d1850a145c33a80
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035794"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="70ff0-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="70ff0-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="70ff0-105">[セキュリティ & コンプライアンスセンター](https://protection.office.com)では、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールセキュリティ機能が組織を保護していることを確認するのに役立つさまざまなレポートが提供されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="70ff0-106">[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="70ff0-107">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-107">To go directly to the reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="70ff0-109">侵害されたユーザーレポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="70ff0-110">このレポートは、Microsoft 365 組織の Exchange Online メールボックスを使用して利用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="70ff0-111">これは、Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="70ff0-111">It's not available in standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="70ff0-112">侵害された**ユーザー**のレポートには、過去7日間以内に**疑わしい**または**制限**されたユーザーアカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="70ff0-113">これらの状態のいずれかのアカウントは、問題が発生しているか、侵害されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="70ff0-114">よく使用されるので、レポートを使用して、不審なアカウントや制限付きのアカウントでスパイクや傾向を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="70ff0-115">侵害されたユーザーの詳細については、「[危害を受けた電子メールアカウントへの対応](responding-to-a-compromised-email-account.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="70ff0-116">集計ビューには過去90日間のデータが表示され、詳細ビューには過去30日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-116">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="70ff0-117">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] \> **ダッシュボード**に移動して、[侵害された**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="70ff0-118">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=CompromisedUsers> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-118">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="70ff0-119">[**フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-119">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="70ff0-120">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-120">**Start date** and **End date**</span></span>

- <span data-ttu-id="70ff0-121">**疑わしい**: ユーザーアカウントは、不審な電子メールを送信しているため、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-121">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="70ff0-122">**制限**: 非常に疑わしいパターンがあるため、ユーザーアカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-122">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザーが Microsoft 365 に表示されるレポート](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

<span data-ttu-id="70ff0-124">[**詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-124">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="70ff0-125">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="70ff0-125">**Creation time**</span></span>
- <span data-ttu-id="70ff0-126">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-126">**User ID**</span></span>
- <span data-ttu-id="70ff0-127">**Action**</span><span class="sxs-lookup"><span data-stu-id="70ff0-127">**Action**</span></span>

<span data-ttu-id="70ff0-128">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-128">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="70ff0-129">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-129">Encryption report</span></span>

<span data-ttu-id="70ff0-130">**暗号化レポート**は、EOP (exchange online またはスタンドアロン EOP の exchange online メールボックスなしのメールボックスを使用したサブスクリプション) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-130">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="70ff0-131">組織のセキュリティチームは、このレポートの情報を使用して、パターンを識別し、機密性の高い電子メールメッセージのポリシーを事前に適用または調整することができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-131">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="70ff0-132">例:</span><span class="sxs-lookup"><span data-stu-id="70ff0-132">For example:</span></span>

- <span data-ttu-id="70ff0-133">ユーザーによって大量の電子メールメッセージが暗号化されている場合、暗号化ポリシーを追加して、特定のユースケースの暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-133">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="70ff0-134">詳細については、「 [Microsoft 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-134">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="70ff0-135">使用可能な暗号化テンプレートが多数あり、それを使用しているものがない場合は、ユーザーが機能のトレーニングを必要としているかどうかを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-135">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="70ff0-136">集計ビューでは、過去90日間のフィルターを使用でき、詳細ビューでは10日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-136">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="70ff0-137">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[**暗号化レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-137">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="70ff0-138">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=EncryptionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-138">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="70ff0-139">暗号化の詳細については、「 [Microsoft 365 の電子メールの暗号化](../../compliance/email-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-139">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="70ff0-140">暗号化レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-140">Report view for the Encryption report</span></span>

<span data-ttu-id="70ff0-141">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-141">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="70ff0-142">**データの表示: メッセージの暗号化レポート**と次の**方法で分割**します。暗号化方法: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-142">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="70ff0-143">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="70ff0-143">**Encryption by user**</span></span>
  - <span data-ttu-id="70ff0-144">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="70ff0-144">**Encryption by policy**</span></span>

  <span data-ttu-id="70ff0-145">[**フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-145">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="70ff0-146">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-146">**Start date** and **End date**</span></span>
  - <span data-ttu-id="70ff0-147">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="70ff0-147">Encryption method.</span></span>
  - <span data-ttu-id="70ff0-148">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="70ff0-148">Encryption template.</span></span>

- <span data-ttu-id="70ff0-149">**データの表示形式: メッセージの暗号化レポート**と**分解: 暗号化テンプレート**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-149">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="70ff0-150">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="70ff0-150">**Do not forward**</span></span>
  - <span data-ttu-id="70ff0-151">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="70ff0-151">**Encrypt only**</span></span>
  - <span data-ttu-id="70ff0-152">**OME previous**</span><span class="sxs-lookup"><span data-stu-id="70ff0-152">**OME previous**</span></span>
  - <span data-ttu-id="70ff0-153">**Custom**</span><span class="sxs-lookup"><span data-stu-id="70ff0-153">**Custom**</span></span>

  <span data-ttu-id="70ff0-154">[**フィルター**] をクリックすると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-154">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="70ff0-155">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-155">**Start date** and **End date**</span></span>
  - <span data-ttu-id="70ff0-156">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="70ff0-156">Encryption method</span></span>
  - <span data-ttu-id="70ff0-157">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="70ff0-157">Encryption template</span></span>

- <span data-ttu-id="70ff0-158">**データの表示形式: 上位5受信者ドメイン**: このビューには、上位5受信者ドメインの送信されたメッセージ数が円グラフで表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-158">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="70ff0-159">[**フィルター**] をクリックすると、**開始日**と**終了日**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-159">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="70ff0-160">暗号化レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-160">Details table view for the Encryption report</span></span>

<span data-ttu-id="70ff0-161">[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-161">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="70ff0-162">**下に移動: 暗号化方法**または次のよう**に分割します。暗号化テンプレート**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-162">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="70ff0-163">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-163">**Date**</span></span>
  - <span data-ttu-id="70ff0-164">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-164">**Sender address**</span></span>
  - <span data-ttu-id="70ff0-165">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="70ff0-165">**Encryption template**</span></span>
  - <span data-ttu-id="70ff0-166">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="70ff0-166">**Encryption method**</span></span>
  - <span data-ttu-id="70ff0-167">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="70ff0-167">**Recipient address**</span></span>
  - <span data-ttu-id="70ff0-168">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-168">**Subject**</span></span>

- <span data-ttu-id="70ff0-169">**データの表示方法: 上位5受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="70ff0-169">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="70ff0-170">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-170">**Date**</span></span>
  - <span data-ttu-id="70ff0-171">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="70ff0-171">**Recipient domain**</span></span>
  - <span data-ttu-id="70ff0-172">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="70ff0-172">**Message count**</span></span>
  
<span data-ttu-id="70ff0-173">詳細テーブルビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-173">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="70ff0-174">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-174">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-175">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="70ff0-175">Encryption method</span></span>
- <span data-ttu-id="70ff0-176">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="70ff0-176">Encryption template</span></span>

<span data-ttu-id="70ff0-177">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-177">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="70ff0-178">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-178">Mailflow status report</span></span>

<span data-ttu-id="70ff0-179">**メールフロー status レポート**には、マルウェア、スパム、フィッシングおよびエッジブロックされたメッセージに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-179">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="70ff0-180">詳細については、「[メールフロー status report](view-mail-flow-reports.md#mailflow-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-180">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detection-in-email-report"></a><span data-ttu-id="70ff0-181">電子メールレポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="70ff0-181">Malware detection in email report</span></span>

<span data-ttu-id="70ff0-182">**電子メールのマルウェア検出**レポートには、受信および送信電子メールメッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) でのマルウェアの検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-182">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="70ff0-183">EOP でのマルウェア保護の詳細については、「 [EOP のマルウェア対策保護](anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-183">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="70ff0-184">集計ビューのフィルターでは90日間が許可されますが、詳細テーブルのフィルターでは10日間しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="70ff0-184">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="70ff0-185">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> ]**ダッシュボード**に移動して、[**電子メールでマルウェアの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-185">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="70ff0-186">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=MalwareDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-186">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポートダッシュボードの電子メールウィジェットでのマルウェアの検出](../../media/malware-detections-widget.png)

<span data-ttu-id="70ff0-188">[**フィルター** ] をクリックして、次のものを選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-188">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="70ff0-189">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-190">**受信**</span><span class="sxs-lookup"><span data-stu-id="70ff0-190">**Inbound**</span></span>
- <span data-ttu-id="70ff0-191">**向き**</span><span class="sxs-lookup"><span data-stu-id="70ff0-191">**Outbound**</span></span>

![電子メールレポートでのマルウェア検出のレポートビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="70ff0-193">[**詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-193">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="70ff0-194">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-194">**Date**</span></span>
- <span data-ttu-id="70ff0-195">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-195">**Sender address**</span></span>
- <span data-ttu-id="70ff0-196">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="70ff0-196">**Recipient address**</span></span>
- <span data-ttu-id="70ff0-197">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-197">**Message ID**</span></span>
- <span data-ttu-id="70ff0-198">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-198">**Subject**</span></span>
- <span data-ttu-id="70ff0-199">**Filename**</span><span class="sxs-lookup"><span data-stu-id="70ff0-199">**Filename**</span></span>
- <span data-ttu-id="70ff0-200">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="70ff0-200">**Malware name**</span></span>

<span data-ttu-id="70ff0-201">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-201">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="70ff0-202">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-202">Sent and received email report</span></span>

<span data-ttu-id="70ff0-203">**送信および受信した電子メール**レポートには、マルウェア、スパム、メールフロールール (トランスポートルールとも呼ばれる) に関する情報と、電子メールがサービスに入った後の高度なマルウェアの検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-203">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="70ff0-204">詳細については、「[送信および受信した電子メールレポート](view-mail-flow-reports.md#sent-and-received-email-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-204">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="70ff0-205">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-205">Spam detections report</span></span>

<span data-ttu-id="70ff0-206">**スパム検出**レポートには、EOP によってブロックされたスパム電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-206">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="70ff0-207">メッセージは、受信者ごとではなく個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-207">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="70ff0-208">たとえば、同じスパムメッセージが組織内の100の受信者に送信された場合は、1つのメッセージとして数えられます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-208">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="70ff0-209">集計ビューでは90日間のフィルター処理が可能で、詳細テーブルでは10日のフィルター処理が許可されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-209">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="70ff0-210">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スパム検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-210">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="70ff0-211">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpamDetections> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-211">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポートダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="70ff0-213">スパム対策保護の詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-213">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="70ff0-214">スパム検出レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-214">Report view for the Spam detections report</span></span>

<span data-ttu-id="70ff0-215">次のグラフがレポートビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-215">The following charts are available in the report view:</span></span>

- <span data-ttu-id="70ff0-216">**分割ダウン: アクション**: 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-216">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="70ff0-217">**スパムコンテンツのフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="70ff0-217">**Spam content filtered**</span></span>
  - <span data-ttu-id="70ff0-218">**スパム IP 禁止**</span><span class="sxs-lookup"><span data-stu-id="70ff0-218">**Spam IP block**</span></span>
  - <span data-ttu-id="70ff0-219">**スパムの封筒ブロック**</span><span class="sxs-lookup"><span data-stu-id="70ff0-219">**Spam envelope block**</span></span>
  - <span data-ttu-id="70ff0-220">**スパム dbeb フィルター**: ディレクトリベースのエッジブロック (dbeb)</span><span class="sxs-lookup"><span data-stu-id="70ff0-220">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="70ff0-221">グラフの1日 (データポイント) にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-221">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクションビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="70ff0-223">次のよう**に分割します。方向**: 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-223">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="70ff0-224">**受信**</span><span class="sxs-lookup"><span data-stu-id="70ff0-224">**Inbound**</span></span>
  - <span data-ttu-id="70ff0-225">**向き**</span><span class="sxs-lookup"><span data-stu-id="70ff0-225">**Outbound**</span></span>

  ![スパム検出レポートでの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="70ff0-227">レポートビューで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-227">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="70ff0-228">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-228">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-229">Direction 値</span><span class="sxs-lookup"><span data-stu-id="70ff0-229">Direction values</span></span>
- <span data-ttu-id="70ff0-230">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="70ff0-230">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="70ff0-231">スパム検出レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-231">Details table view for the Spam detections report</span></span>

<span data-ttu-id="70ff0-232">いずれかのレポートビューで [**詳細テーブルの表示**] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-232">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="70ff0-233">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-233">**Date**</span></span>
- <span data-ttu-id="70ff0-234">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-234">**Sender address**</span></span>
- <span data-ttu-id="70ff0-235">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="70ff0-235">**Recipient address**</span></span>
- <span data-ttu-id="70ff0-236">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="70ff0-236">**Event type**</span></span>
- <span data-ttu-id="70ff0-237">**Action**</span><span class="sxs-lookup"><span data-stu-id="70ff0-237">**Action**</span></span>
- <span data-ttu-id="70ff0-238">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-238">**Subject**</span></span>

<span data-ttu-id="70ff0-239">詳細テーブルで [**フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-239">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="70ff0-240">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-240">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-241">Direction 値</span><span class="sxs-lookup"><span data-stu-id="70ff0-241">Direction values</span></span>
- <span data-ttu-id="70ff0-242">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="70ff0-242">Event type values</span></span>

<span data-ttu-id="70ff0-243">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-243">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="70ff0-244">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-244">Spoof detections report</span></span>

<span data-ttu-id="70ff0-245">**スプーフィング検出**レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-245">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="70ff0-246">スプーフィングの詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-246">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="70ff0-247">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理しか許可されません。</span><span class="sxs-lookup"><span data-stu-id="70ff0-247">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="70ff0-248">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**スプーフィング検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-248">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="70ff0-249">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=SpoofMailReport> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-249">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポートダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="70ff0-251">グラフの1日 (データポイント) にカーソルを置くと、受信したスプーフィングメールメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-251">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="70ff0-252">[**フィルター** ] をクリックして、次のいずれかまたは複数の値を選択することによって、グラフと詳細テーブルの両方をフィルターできます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-252">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="70ff0-253">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-253">**Start date** and **End date**</span></span>

- <span data-ttu-id="70ff0-254">**正常なメール**</span><span class="sxs-lookup"><span data-stu-id="70ff0-254">**Good mail**</span></span>

- <span data-ttu-id="70ff0-255">**スパムとして検出された**</span><span class="sxs-lookup"><span data-stu-id="70ff0-255">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポートビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="70ff0-257">[**詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-257">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="70ff0-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-258">**Date**</span></span>
- <span data-ttu-id="70ff0-259">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-259">**Spoofed sender**</span></span>
- <span data-ttu-id="70ff0-260">**True 送信者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-260">**True sender**</span></span>
- <span data-ttu-id="70ff0-261">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="70ff0-261">**Sender IP**</span></span>
- <span data-ttu-id="70ff0-262">**Action**</span><span class="sxs-lookup"><span data-stu-id="70ff0-262">**Action**</span></span>
- <span data-ttu-id="70ff0-263">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="70ff0-263">**Message count**</span></span>

<span data-ttu-id="70ff0-264">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-264">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="70ff0-265">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-265">Threat protection status report</span></span>

<span data-ttu-id="70ff0-266">**脅威保護の状態**レポートは、EOP と OFFICE 365 ATP の両方で使用できます。ただし、レポートには異なるデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-266">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="70ff0-267">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="70ff0-267">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="70ff0-268">Office 365 ATP レポートの詳細については、「 [View reports For office 365 Advanced Threat Protection](view-reports-for-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-268">For more information about Office 365 ATP reports, see [View reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md).</span></span>

<span data-ttu-id="70ff0-269">これは、検出およびブロックされた悪意のある電子メールを示すスマートレポートです。これにより、セキュリティ管理者は傾向を特定したり、組織のポリシーを調整する必要があるかどうかを判断したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-269">This is a smart report that shows malicious email that was detected and blocked, and it enables security admins to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="70ff0-270">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[**脅威保護の状態**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-270">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="70ff0-271">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPV2AggregateReport> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-271">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>

![レポートダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="70ff0-273">既定では、グラフに過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-273">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="70ff0-274">[**フィルター**] をクリックした場合は、90日の日付の範囲を選択できます (試用版のサブスクリプションは30日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="70ff0-274">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="70ff0-275">詳細テーブルビューでは、30日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-275">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="70ff0-276">脅威保護状態レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-276">Report view for the Threat protection status report</span></span>

<span data-ttu-id="70ff0-277">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-277">The following views are available:</span></span>

- <span data-ttu-id="70ff0-278">**データの表示: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-278">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="70ff0-279">**メールマルウェア**</span><span class="sxs-lookup"><span data-stu-id="70ff0-279">**Email malware**</span></span>
  - <span data-ttu-id="70ff0-280">**電子メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="70ff0-280">**Email phish**</span></span>
  - <span data-ttu-id="70ff0-281">**コンテンツマルウェア**</span><span class="sxs-lookup"><span data-stu-id="70ff0-281">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="70ff0-283">**データの表示方法: コンテンツ \>マルウェア**<sup>1</sup>: 次の情報は、Office 365 ATP 組織で表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-283">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="70ff0-284">**マルウェア対策エンジン**</span><span class="sxs-lookup"><span data-stu-id="70ff0-284">**Anti-malware engine**</span></span>
  - <span data-ttu-id="70ff0-285">**ファイル分析**</span><span class="sxs-lookup"><span data-stu-id="70ff0-285">**File detonation**</span></span>

  ![脅威保護状態レポートのコンテンツマルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="70ff0-287">**下に移動: 検出テクノロジ**と**View data: Email \> フィッシング**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-287">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="70ff0-288">**ATP で生成された URL 評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-288">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-289">**高度なフィッシングフィルター**</span><span class="sxs-lookup"><span data-stu-id="70ff0-289">**Advanced phish filter**</span></span>
  - <span data-ttu-id="70ff0-290">**スプーフィング防止: DMARC エラー**</span><span class="sxs-lookup"><span data-stu-id="70ff0-290">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="70ff0-291">**スプーフィング対策: 組織内**</span><span class="sxs-lookup"><span data-stu-id="70ff0-291">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="70ff0-292">**スプーフィング防止: 外部ドメイン**</span><span class="sxs-lookup"><span data-stu-id="70ff0-292">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="70ff0-293">**ブランド偽装**</span><span class="sxs-lookup"><span data-stu-id="70ff0-293">**Brand impersonation**</span></span>
  - <span data-ttu-id="70ff0-294">**ドメイン偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-294">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-295">**EOP URL 評価**</span><span class="sxs-lookup"><span data-stu-id="70ff0-295">**EOP URL reputation**</span></span>
  - <span data-ttu-id="70ff0-296">**一般的なフィッシングフィルター**</span><span class="sxs-lookup"><span data-stu-id="70ff0-296">**General phish filter**</span></span>
  - <span data-ttu-id="70ff0-297">**Others**</span><span class="sxs-lookup"><span data-stu-id="70ff0-297">**Others**</span></span>
  - <span data-ttu-id="70ff0-298">**フィッシング ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-298">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="70ff0-299">**URL 分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-299">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-300">**ユーザー偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-300">**User impersonation**<sup>1</sup></span></span>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="70ff0-302">**分割ダウン: 検出テクノロジ**と**データの表示者: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-302">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="70ff0-303">**ATP で生成されたファイル評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-303">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-304">**マルウェア対策エンジン**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-304">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-305">**マルウェア対策ポリシーファイルの種類ブロック**</span><span class="sxs-lookup"><span data-stu-id="70ff0-305">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="70ff0-306">**ファイル分析**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-306">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-307">**悪意のあるファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="70ff0-307">**Malicious file reputation**</span></span>
  - <span data-ttu-id="70ff0-308">**マルウェアの ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-308">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="70ff0-309">**Others**</span><span class="sxs-lookup"><span data-stu-id="70ff0-309">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="70ff0-311">**分割ダウン: Policy type** and **view Data by: Email \> フィッシング**Or **view data by: email \> マル**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-311">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="70ff0-312">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="70ff0-312">**Anti-malware**</span></span>
  - <span data-ttu-id="70ff0-313">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="70ff0-313">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="70ff0-314">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="70ff0-314">**Anti-phish**</span></span>
  - <span data-ttu-id="70ff0-315">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="70ff0-315">**Anti-spam**</span></span>
  - <span data-ttu-id="70ff0-316">**メールフロールール**(トランスポートルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="70ff0-316">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="70ff0-317">**Others**</span><span class="sxs-lookup"><span data-stu-id="70ff0-317">**Others**</span></span>

  ![脅威保護の状態レポートに表示されるフィッシング電子メールのポリシーの種類](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="70ff0-319">**分割ダウン: 配信状態**および**表示データ: 電子メールの \> フィッシング**または**view by: email \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-319">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="70ff0-320">**配信失敗**</span><span class="sxs-lookup"><span data-stu-id="70ff0-320">**Delivery failed**</span></span>
  - <span data-ttu-id="70ff0-321">**落下**</span><span class="sxs-lookup"><span data-stu-id="70ff0-321">**Dropped**</span></span>
  - <span data-ttu-id="70ff0-322">**転送**</span><span class="sxs-lookup"><span data-stu-id="70ff0-322">**Forwarded**</span></span>
  - <span data-ttu-id="70ff0-323">**ホストされているメールボックス: カスタムフォルダー**</span><span class="sxs-lookup"><span data-stu-id="70ff0-323">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="70ff0-324">**ホストされているメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="70ff0-324">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="70ff0-325">**ホストされているメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="70ff0-325">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="70ff0-326">**ホストされているメールボックス: 迷惑**</span><span class="sxs-lookup"><span data-stu-id="70ff0-326">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="70ff0-327">**オンプレミスサーバー: 配信済み**</span><span class="sxs-lookup"><span data-stu-id="70ff0-327">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="70ff0-328">**検疫**</span><span class="sxs-lookup"><span data-stu-id="70ff0-328">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="70ff0-330"><sup>1</sup> OFFICE 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="70ff0-330"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="70ff0-331"><sup>2</sup>ゼロ時間自動削除 (ZAP) は、スタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。</span><span class="sxs-lookup"><span data-stu-id="70ff0-331"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="70ff0-332">[**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-332">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="70ff0-333">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-333">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-334">検出値</span><span class="sxs-lookup"><span data-stu-id="70ff0-334">Detection value</span></span>
- <span data-ttu-id="70ff0-335">**保護者**(OFFICE 365 ATP のみ): **ATP**または**EOP**。</span><span class="sxs-lookup"><span data-stu-id="70ff0-335">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="70ff0-336">このフィルター処理可能なプロパティは、 **「データの表示方法: コンテンツ \> マルウェア**」では使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-336">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="70ff0-337">脅威保護状態レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-337">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="70ff0-338">[**詳細テーブルの表示**] をクリックした場合、表示されている情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-338">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="70ff0-339">**データの表示方法: コンテンツ \>マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="70ff0-339">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="70ff0-340">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-340">**Date**</span></span>
  - <span data-ttu-id="70ff0-341">**Location**</span><span class="sxs-lookup"><span data-stu-id="70ff0-341">**Location**</span></span>
  - <span data-ttu-id="70ff0-342">**転送者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-342">**Directed by**</span></span>
  - <span data-ttu-id="70ff0-343">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="70ff0-343">**Malware name**</span></span>

- <span data-ttu-id="70ff0-344">**データの表示: 概要**: [**表示の詳細] テーブル**ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="70ff0-344">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="70ff0-345">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="70ff0-345">All other charts:</span></span>

  - <span data-ttu-id="70ff0-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="70ff0-346">**Date**</span></span>
  - <span data-ttu-id="70ff0-347">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="70ff0-347">**Subject**</span></span>
  - <span data-ttu-id="70ff0-348">**送信者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-348">**Sender**</span></span>
  - <span data-ttu-id="70ff0-349">**受信者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-349">**Recipients**</span></span>
  - <span data-ttu-id="70ff0-350">**検出者**</span><span class="sxs-lookup"><span data-stu-id="70ff0-350">**Detected by**</span></span>
  - <span data-ttu-id="70ff0-351">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="70ff0-351">**Delivery status**</span></span>
  - <span data-ttu-id="70ff0-352">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="70ff0-352">**Source of compromise**</span></span>

<span data-ttu-id="70ff0-353">[**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-353">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="70ff0-354">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-354">**Start date** and **End date**</span></span>
- <span data-ttu-id="70ff0-355">検出値</span><span class="sxs-lookup"><span data-stu-id="70ff0-355">Detection value</span></span>
- <span data-ttu-id="70ff0-356">**保護者**(OFFICE 365 ATP のみ): **ATP**または**EOP**。</span><span class="sxs-lookup"><span data-stu-id="70ff0-356">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="70ff0-357">このフィルター処理可能なプロパティは、 **「データの表示方法: コンテンツ \> マルウェア**」では使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-357">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="70ff0-358">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-358">Top malware report</span></span>

<span data-ttu-id="70ff0-359">**上位マルウェア**レポートには、 [EOP でマルウェア対策保護](anti-malware-protection.md)によって検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-359">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="70ff0-360">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] \> **ダッシュボード**に移動して [**上位マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-360">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="70ff0-361">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=TopMalware> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-361">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポートダッシュボードのトップマルウェアウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="70ff0-363">円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-363">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップマルウェアレポートビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="70ff0-365">[**詳細テーブルの表示**] をクリックすると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-365">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="70ff0-366">**上位マルウェア**</span><span class="sxs-lookup"><span data-stu-id="70ff0-366">**Top malware**</span></span>
- <span data-ttu-id="70ff0-367">**Count**</span><span class="sxs-lookup"><span data-stu-id="70ff0-367">**Count**</span></span>

<span data-ttu-id="70ff0-368">レポートビューまたは詳細テーブルビューで [**フィルター** ] をクリックすると、**開始**日と**終了日**を含む日付範囲を指定できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-368">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="70ff0-369">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-369">URL threat protection report</span></span>

> [!NOTE]
> <span data-ttu-id="70ff0-370">このレポートは、Office 365 Advanced Threat Protection (ATP) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-370">This report is available only in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="70ff0-371">たとえば、Microsoft 365 E5 サブスクリプション、または ATP プラン1または ATP Plan 2 アドオンがあります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-371">For example, a Microsoft 365 E5 subscription, or an ATP Plan 1 or ATP Plan 2 add-on.</span></span>

<span data-ttu-id="70ff0-372">**Url 脅威保護レポート**には、検出された脅威と、 [ATP の安全なリンク](atp-safe-links.md)の一部として、URL クリックに対して行われた操作の概要と傾向のビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-372">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="70ff0-373">このレポートには、安全なリンクポリシーが適用されているユーザーのクリックデータがありません。 [ユーザーのクリックを**追跡**しない] オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="70ff0-373">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="70ff0-374">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** \> **ダッシュボード**] に移動して、[ **URL の保護**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-374">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection**.</span></span> <span data-ttu-id="70ff0-375">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=URLProtectionActionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-375">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="70ff0-376">URL 脅威保護レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-376">Report view for the URL threat protection report</span></span>

<span data-ttu-id="70ff0-377">**URL 脅威保護**レポートには、過去90日間のデータを表示する4時間ごとに更新される2つの集計ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-377">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="70ff0-378">**[URL] [保護アクション] をクリック**します。組織内のユーザーによる URL クリック数、およびクリックの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-378">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="70ff0-379">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="70ff0-379">**Blocked**</span></span>
  - <span data-ttu-id="70ff0-380">**ブロックとクリックスルー**</span><span class="sxs-lookup"><span data-stu-id="70ff0-380">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="70ff0-381">**スキャン中にクリックでクリック**</span><span class="sxs-lookup"><span data-stu-id="70ff0-381">**Clicked through during scan**</span></span>

  <span data-ttu-id="70ff0-382">クリックすると、ユーザーが悪意のある web サイトをクリックしたことを示します (管理者は、安全なリンクポリシーでクリックを無効にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="70ff0-382">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="70ff0-383">[**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-383">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="70ff0-384">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-384">**Start date** and **End date**</span></span>
  - <span data-ttu-id="70ff0-385">使用可能なクリック保護アクションと、すべての URL クリック (ブロックされたクリックのみではない) の情報を表示**できる値を**加えたもの。</span><span class="sxs-lookup"><span data-stu-id="70ff0-385">The available click protection actions, plus the value **Allowed** to see information for all URL clicks (not just blocked clicks).</span></span>

  ![URL URL の脅威保護レポートにある [保護アクション表示] をクリックします。](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="70ff0-387">**Url [アプリケーションごと]**: OFFICE 365 ATP の安全なリンクをサポートしているアプリケーションによる url クリックの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-387">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="70ff0-388">**電子メール クライアント**</span><span class="sxs-lookup"><span data-stu-id="70ff0-388">**Email client**</span></span>
  - <span data-ttu-id="70ff0-389">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="70ff0-389">**PowerPoint**</span></span>
  - <span data-ttu-id="70ff0-390">**Word**</span><span class="sxs-lookup"><span data-stu-id="70ff0-390">**Word**</span></span>
  - <span data-ttu-id="70ff0-391">**Excel**</span><span class="sxs-lookup"><span data-stu-id="70ff0-391">**Excel**</span></span>
  - <span data-ttu-id="70ff0-392">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="70ff0-392">**OneNote**</span></span>
  - <span data-ttu-id="70ff0-393">**Visio**</span><span class="sxs-lookup"><span data-stu-id="70ff0-393">**Visio**</span></span>
  - <span data-ttu-id="70ff0-394">**Teams**</span><span class="sxs-lookup"><span data-stu-id="70ff0-394">**Teams**</span></span>
  - <span data-ttu-id="70ff0-395">**その他**</span><span class="sxs-lookup"><span data-stu-id="70ff0-395">**Other**</span></span>

  <span data-ttu-id="70ff0-396">[**フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-396">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="70ff0-397">**開始日**と**終了日**</span><span class="sxs-lookup"><span data-stu-id="70ff0-397">**Start date** and **End date**</span></span>
  - <span data-ttu-id="70ff0-398">利用可能なアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="70ff0-398">The available applications.</span></span>

### <a name="details-table-view-for-the-threat-protection-report"></a><span data-ttu-id="70ff0-399">脅威保護レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="70ff0-399">Details table view for the threat protection report</span></span>

<span data-ttu-id="70ff0-400">[**詳細テーブルの表示**] をクリックすると、このレポートでは、過去7日間の組織内で発生したすべてのクリックが、次のようなほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-400">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="70ff0-401">**[時刻] をクリック**</span><span class="sxs-lookup"><span data-stu-id="70ff0-401">**Click time**</span></span>
- <span data-ttu-id="70ff0-402">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="70ff0-402">**User**</span></span>
- <span data-ttu-id="70ff0-403">\*\* URL \*\*</span><span class="sxs-lookup"><span data-stu-id="70ff0-403">**URL**</span></span>
- <span data-ttu-id="70ff0-404">**Action**</span><span class="sxs-lookup"><span data-stu-id="70ff0-404">**Action**</span></span>
- <span data-ttu-id="70ff0-405">**App**</span><span class="sxs-lookup"><span data-stu-id="70ff0-405">**App**</span></span>

<span data-ttu-id="70ff0-406">詳細テーブルビューで [**フィルター** ] をクリックすると、レポートビューと同じ条件で、およびコンマで区切られた**ドメイン**または**受信者**によってフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-406">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="70ff0-407">レポートビューに戻るには、[**レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70ff0-407">To get back to the reports view, click **View report**.</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="70ff0-408">ユーザーによって報告されたメッセージレポート</span><span class="sxs-lookup"><span data-stu-id="70ff0-408">User-reported messages report</span></span>

<span data-ttu-id="70ff0-409">ユーザーによって報告された**メッセージ**レポートには、ユーザーが[レポートメッセージアドイン](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-409">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="70ff0-410">組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-410">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="70ff0-411">詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[**概要**] タブと [**詳細**] タブで情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-411">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![ユーザーによって報告されたメッセージのレポートには、ユーザーが迷惑メールではないというラベルが付けられます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="70ff0-413">このレポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-413">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="70ff0-414">[**脅威管理**] ダッシュボードのユーザーによって報告されたメッセージに移動 \> **Dashboard** \> **User-reported messages**します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-414">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="70ff0-415">[**脅威の管理**] に移動して \> **Review** \> **、ユーザーから報告**されたメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="70ff0-415">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ & コンプライアンスセンターで、[脅威管理] [ \> ユーザーが報告するメッセージを確認する] を選択します。 \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="70ff0-417">ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の**監査ログを有効にする必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-417">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="70ff0-418">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="70ff0-418">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="70ff0-419">詳細については、「 [Microsoft 365 監査ログ検索を有効または無効にする](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-419">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="70ff0-420">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="70ff0-420">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="70ff0-421">レポートを表示して使用するには、セキュリティ & コンプライアンスセンター**および**Exchange Online で、指定された役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-421">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="70ff0-422">セキュリティ & コンプライアンスセンターでは、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-422">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="70ff0-423">-組織の管理-セキュリティ管理者 ( [Azure Active Directory 管理センター](https://aad.portal.azure.com) -セキュリティリーダでこれを実行することもできます)</span><span class="sxs-lookup"><span data-stu-id="70ff0-423">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="70ff0-424">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-424">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="70ff0-425">Exchange Online では、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="70ff0-425">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="70ff0-426">-組織の管理-表示のみの組織の管理-表示のみの受信者-コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="70ff0-426">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="70ff0-427">詳細については、「exchange online の[アクセス許可](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo)」および「 [Manage Role Groups in exchange online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-427">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="70ff0-428">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="70ff0-428">What if the reports aren't showing data?</span></span>

<span data-ttu-id="70ff0-429">レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-429">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="70ff0-430">詳細については、「[脅威からの保護](protect-against-threats.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70ff0-430">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="70ff0-431">関連トピック</span><span class="sxs-lookup"><span data-stu-id="70ff0-431">Related topics</span></span>

[<span data-ttu-id="70ff0-432">EOP でのスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="70ff0-432">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="70ff0-433">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="70ff0-433">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
