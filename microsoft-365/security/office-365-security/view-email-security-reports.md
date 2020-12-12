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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について学習します。 電子メール セキュリティ レポートは、セキュリティ/コンプライアンス センター&利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e98e59d39744d67427a272f456a03fc123034aa7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659479"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="90806-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="90806-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="90806-105">セキュリティ & コンプライアンス センターでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護する方法を確認するのに役立つさまざまなレポートが用意されています。 [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="90806-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="90806-106">必要な [アクセス許可がある](#what-permissions-are-needed-to-view-these-reports)場合は、レポート ダッシュボードに移動して、セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="90806-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="90806-107">レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="90806-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ/コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="90806-109">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="90806-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="90806-110">このレポートは、Exchange Online メールボックスを使用している Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="90806-111">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="90806-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="90806-112">[**侵害されたユーザー]** レポートには、過去 7 日以内に[不審] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="90806-113">これらのいずれかの状態のアカウントは、問題がある場合も、侵害されている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="90806-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="90806-114">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限されたアカウントのスパイクや傾向を特定できます。</span><span class="sxs-lookup"><span data-stu-id="90806-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="90806-115">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポート ダッシュボードの侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="90806-117">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="90806-118">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&**ダッシュボード** に移動し、[侵害されたユーザー \>  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="90806-119">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="90806-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="90806-120">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="90806-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="90806-121">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="90806-122">**不審**: ユーザー アカウントが不審なメールを送信し、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="90806-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="90806-123">**制限**: 不審なパターンが原因で、ユーザー アカウントによるメールの送信が制限されています。</span><span class="sxs-lookup"><span data-stu-id="90806-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザー レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="90806-125">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90806-126">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="90806-126">**Creation time**</span></span>
- <span data-ttu-id="90806-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="90806-127">**User ID**</span></span>
- <span data-ttu-id="90806-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="90806-128">**Action**</span></span>

<span data-ttu-id="90806-129">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90806-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="90806-130">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="90806-130">Encryption report</span></span>

<span data-ttu-id="90806-131">暗号化 **レポートは** 、EOP (Exchange Online のメールボックスを持つサブスクリプション、または Exchange Online メールボックスを使用しないスタンドアロン EOP) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="90806-132">組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーを事前に適用または調整できます。</span><span class="sxs-lookup"><span data-stu-id="90806-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="90806-133">例:</span><span class="sxs-lookup"><span data-stu-id="90806-133">For example:</span></span>

- <span data-ttu-id="90806-134">ユーザーによって暗号化された電子メール メッセージの数が多い場合は、暗号化ポリシーを追加して、特定の使用例の暗号化を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="90806-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="90806-135">詳細については [、「Microsoft 365 でメール メッセージを暗号化するメール](../../compliance/define-mail-flow-rules-to-encrypt-email.md)フロー ルールを定義する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90806-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="90806-136">利用可能な暗号化テンプレートが多数あるが、誰も使用できない場合は、ユーザーが機能トレーニングを必要とするかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="90806-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="90806-137">集計ビューでは過去 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="90806-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="90806-138">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&レポート ダッシュボード **に移動し**、[暗号化] \> レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="90806-139">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="90806-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="90806-140">暗号化の詳細については [、「Microsoft 365](../../compliance/email-encryption.md)での電子メールの暗号化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90806-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="90806-141">暗号化レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-141">Report view for the Encryption report</span></span>

<span data-ttu-id="90806-142">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="90806-143">**データの表示方法: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span><span class="sxs-lookup"><span data-stu-id="90806-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="90806-144">**ユーザー別の暗号化**</span><span class="sxs-lookup"><span data-stu-id="90806-144">**Encryption by user**</span></span>
  - <span data-ttu-id="90806-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="90806-145">**Encryption by policy**</span></span>

  <span data-ttu-id="90806-146">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="90806-147">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="90806-148">Encryption method.</span></span>
  - <span data-ttu-id="90806-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="90806-149">Encryption template.</span></span>

- <span data-ttu-id="90806-150">**データの表示方法: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span><span class="sxs-lookup"><span data-stu-id="90806-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="90806-151">**転送しない**</span><span class="sxs-lookup"><span data-stu-id="90806-151">**Do not forward**</span></span>
  - <span data-ttu-id="90806-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="90806-152">**Encrypt only**</span></span>
  - <span data-ttu-id="90806-153">**前の OME**</span><span class="sxs-lookup"><span data-stu-id="90806-153">**OME previous**</span></span>
  - <span data-ttu-id="90806-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="90806-154">**Custom**</span></span>

  <span data-ttu-id="90806-155">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="90806-156">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="90806-157">Encryption method</span></span>
  - <span data-ttu-id="90806-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="90806-158">Encryption template</span></span>

- <span data-ttu-id="90806-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span><span class="sxs-lookup"><span data-stu-id="90806-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="90806-160">[フィルター]**をクリック** すると、開始日と **終了日を\*\*\*\*選択できます**。</span><span class="sxs-lookup"><span data-stu-id="90806-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="90806-161">暗号化レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="90806-162">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="90806-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="90806-163">**[Break down by: Encryption method] (暗号化方法** ) または **[Break down by]**(暗号化テンプレート): 次の情報を示します。</span><span class="sxs-lookup"><span data-stu-id="90806-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="90806-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-164">**Date**</span></span>
  - <span data-ttu-id="90806-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90806-165">**Sender address**</span></span>
  - <span data-ttu-id="90806-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="90806-166">**Encryption template**</span></span>
  - <span data-ttu-id="90806-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="90806-167">**Encryption method**</span></span>
  - <span data-ttu-id="90806-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90806-168">**Recipient address**</span></span>
  - <span data-ttu-id="90806-169">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90806-169">**Subject**</span></span>

- <span data-ttu-id="90806-170">**データの表示方法: 上位 5 つの受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="90806-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="90806-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-171">**Date**</span></span>
  - <span data-ttu-id="90806-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-172">**Recipient domain**</span></span>
  - <span data-ttu-id="90806-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="90806-173">**Message count**</span></span>

<span data-ttu-id="90806-174">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90806-175">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="90806-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="90806-176">Encryption method</span></span>
- <span data-ttu-id="90806-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="90806-177">Encryption template</span></span>

<span data-ttu-id="90806-178">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90806-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="90806-179">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="90806-179">Mailflow status report</span></span>

<span data-ttu-id="90806-180">Mailflow **ステータス レポートには、** マルウェア、スパム、フィッシング、およびエッジでブロックされたメッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90806-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="90806-181">詳細については、「メールフローの [状態レポート」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="90806-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="90806-182">メール レポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="90806-182">Malware detections in email report</span></span>

<span data-ttu-id="90806-183">電子 **メール レポートのマルウェア検出** では、受信および送信電子メール メッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) のマルウェア検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="90806-184">EOP でのマルウェア保護の詳細については、「EOP での [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="90806-185">集計ビュー フィルターは 90 日間使用できます。詳細テーブルフィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="90806-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="90806-186">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、メールで \> **[マルウェアの検出] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="90806-187">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="90806-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポート ダッシュボードの電子メール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

<span data-ttu-id="90806-189">[フィルター] をクリックして次の項目を選択すると、グラフと詳細テーブル **の両方** をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="90806-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="90806-190">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="90806-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="90806-191">**Inbound**</span></span>
- <span data-ttu-id="90806-192">**送信**</span><span class="sxs-lookup"><span data-stu-id="90806-192">**Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="90806-194">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90806-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-195">**Date**</span></span>
- <span data-ttu-id="90806-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90806-196">**Sender address**</span></span>
- <span data-ttu-id="90806-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90806-197">**Recipient address**</span></span>
- <span data-ttu-id="90806-198">**メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="90806-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="90806-199">値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="90806-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="90806-200">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90806-200">**Subject**</span></span>
- <span data-ttu-id="90806-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="90806-201">**Filename**</span></span>
- <span data-ttu-id="90806-202">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="90806-202">**Malware name**</span></span>

<span data-ttu-id="90806-203">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90806-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="90806-204">メール待機時間レポート</span><span class="sxs-lookup"><span data-stu-id="90806-204">Mail latency report</span></span>

<span data-ttu-id="90806-205">[ **メールの待機時間] レポートには** 、組織内で発生したメール配信と分析の待機時間に関する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="90806-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="90806-206">詳細については、「メールの待機時間 [レポート」を参照してください](view-reports-for-atp.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="90806-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="90806-207">送信および受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="90806-207">Sent and received email report</span></span>

<span data-ttu-id="90806-208">送信 **および受信メール** レポートには、マルウェア、スパム、メール フロー ルール (トランスポート ルールとも呼ばれる) に関する情報、およびメールがサービスに入った後の高度なマルウェア検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="90806-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="90806-209">詳細については、「送信および受信 [メール レポート」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="90806-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="90806-210">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="90806-210">Spam detections report</span></span>

<span data-ttu-id="90806-211">スパム **検出レポートには** 、EOP によってブロックされたスパム 電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="90806-212">メッセージは個別にカウントされ、受信者ごとにカウントされません。</span><span class="sxs-lookup"><span data-stu-id="90806-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="90806-213">たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、1 つのメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="90806-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="90806-214">集計ビューでは 90 日間のフィルター処理が可能で、詳細テーブルでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="90806-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="90806-215">レポートを表示するには、セキュリティ/コンプライアンス センターを [&](https://protection.office.com)レポート ダッシュボードに移動し、[スパム検出 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="90806-216">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="90806-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="90806-218">スパム対策保護の詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="90806-219">スパム検出レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="90806-220">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="90806-221">**[Break down by: Action]:** 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="90806-222">**フィルター処理されたスパム コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="90806-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="90806-223">**スパム IP ブロック**</span><span class="sxs-lookup"><span data-stu-id="90806-223">**Spam IP block**</span></span>
  - <span data-ttu-id="90806-224">**スパム エンベロープ ブロック**</span><span class="sxs-lookup"><span data-stu-id="90806-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="90806-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span><span class="sxs-lookup"><span data-stu-id="90806-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="90806-226">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日にブロックされたアイテムの数と、それらのアイテムの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90806-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="90806-228">**[Break down by: Direction]**(方向): 次の方向を示します。</span><span class="sxs-lookup"><span data-stu-id="90806-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="90806-229">**受信**</span><span class="sxs-lookup"><span data-stu-id="90806-229">**Inbound**</span></span>
  - <span data-ttu-id="90806-230">**送信**</span><span class="sxs-lookup"><span data-stu-id="90806-230">**Outbound**</span></span>

  ![スパム検出レポートの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="90806-232">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90806-233">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="90806-234">方向の値</span><span class="sxs-lookup"><span data-stu-id="90806-234">Direction values</span></span>
- <span data-ttu-id="90806-235">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="90806-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="90806-236">スパム検出レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="90806-237">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="90806-238">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-238">**Date**</span></span>
- <span data-ttu-id="90806-239">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90806-239">**Sender address**</span></span>
- <span data-ttu-id="90806-240">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90806-240">**Recipient address**</span></span>
- <span data-ttu-id="90806-241">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="90806-241">**Event type**</span></span>
- <span data-ttu-id="90806-242">**操作**</span><span class="sxs-lookup"><span data-stu-id="90806-242">**Action**</span></span>
- <span data-ttu-id="90806-243">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90806-243">**Subject**</span></span>

<span data-ttu-id="90806-244">詳細テーブルで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90806-245">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="90806-246">方向の値</span><span class="sxs-lookup"><span data-stu-id="90806-246">Direction values</span></span>
- <span data-ttu-id="90806-247">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="90806-247">Event type values</span></span>

<span data-ttu-id="90806-248">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90806-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="90806-249">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="90806-249">Spoof detections report</span></span>

<span data-ttu-id="90806-250">ス **プー** フィング検出レポートには、検出されたスプーフィング メール メッセージの数と、それらのスプーフィング メール メッセージの数が示されます。それらのメッセージは "良好" と見なされました (正当なビジネス上の理由で行われたスプーフィング メール)。</span><span class="sxs-lookup"><span data-stu-id="90806-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="90806-251">スプーフィングの詳細については、「EOP でのスプーフィング対策 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="90806-252">レポートの集計ビューでは 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="90806-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="90806-253">レポートを表示するには、セキュリティ/コンプライアンス センターを [&](https://protection.office.com)レポート ダッシュボードに移動し、[スプーフィング \> の検出 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="90806-254">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="90806-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="90806-256">グラフで 1 日 (データ ポイント) をポイントすると、スプーフィング メール メッセージの受信数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90806-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="90806-257">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="90806-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="90806-258">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="90806-259">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="90806-259">**Good mail**</span></span>

- <span data-ttu-id="90806-260">**スパムとして検出される**</span><span class="sxs-lookup"><span data-stu-id="90806-260">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="90806-262">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90806-263">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-263">**Date**</span></span>
- <span data-ttu-id="90806-264">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="90806-264">**Spoofed sender**</span></span>
- <span data-ttu-id="90806-265">**真の送信者**</span><span class="sxs-lookup"><span data-stu-id="90806-265">**True sender**</span></span>
- <span data-ttu-id="90806-266">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="90806-266">**Sender IP**</span></span>
- <span data-ttu-id="90806-267">**操作**</span><span class="sxs-lookup"><span data-stu-id="90806-267">**Action**</span></span>
- <span data-ttu-id="90806-268">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="90806-268">**Message count**</span></span>

<span data-ttu-id="90806-269">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90806-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="90806-270">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="90806-270">Threat protection status report</span></span>

<span data-ttu-id="90806-271">脅威 **保護の状態** レポートは、EOP と Microsoft Defender の両方で Office 365 で確認できます。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="90806-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="90806-272">たとえば、EOP のお客様は電子メールで検出されたマルウェアに関する情報を表示できますが [、ATP for SharePoint、OneDrive、または Microsoft Teams](atp-for-spo-odb-and-teams.md)で検出された悪意のあるファイルに関する情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="90806-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="90806-273">このレポートは、マルウェア対策エンジン、ゼロアワー自動消去[(ZAP)、Defender](zero-hour-auto-purge.md)for Office 365 の機能 (安全なリンク、安全な添付ファイル、フィッシング対策など) によってブロックされたファイルや Web サイト アドレス[](atp-safe-attachments.md)(URL)[](set-up-anti-phishing-policies.md)など、悪意のあるコンテンツを含む電子メール メッセージの数を提供します。 [](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="90806-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="90806-274">この情報を使用して、傾向を特定したり、組織のポリシーに調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="90806-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="90806-275">**注**: メッセージが 5 人の受信者に送信される場合、1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされるという点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="90806-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="90806-276">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&ダッシュボード **に移動し**、[脅威の防止の状態] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="90806-277">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="90806-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="90806-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="90806-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="90806-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="90806-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="90806-281">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="90806-282">[フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションの期間は 30 日間に制限されます)。</span><span class="sxs-lookup"><span data-stu-id="90806-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="90806-283">詳細テーブル ビューでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="90806-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="90806-284">脅威保護状態レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="90806-285">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-285">The following views are available:</span></span>

- <span data-ttu-id="90806-286">**データの表示方法: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="90806-287">**マルウェアへのメール送信**</span><span class="sxs-lookup"><span data-stu-id="90806-287">**Email malware**</span></span>
  - <span data-ttu-id="90806-288">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="90806-288">**Email phish**</span></span>
  - <span data-ttu-id="90806-289">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="90806-289">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="90806-291">**データの表示方法: コンテンツ \> マルウェア**<sup>1:</sup>次の情報は、365 組織の Microsoft Defender Office示されています。</span><span class="sxs-lookup"><span data-stu-id="90806-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="90806-292">**マルウェア対策エンジン**: [Microsoft 365](virus-detection-in-spo.md)の組み込みウイルス検出により、Sharepoint、OneDrive、および Microsoft Teams で悪意のあるファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="90806-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="90806-293">**ファイル分析**: [Sharepoint、OneDrive、および Microsoft Teams](atp-for-spo-odb-and-teams.md)の ATP によって検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="90806-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="90806-295">**データの表示:メッセージの上書き**: 次の上書き理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="90806-296">**オンプレミス のスキップ**</span><span class="sxs-lookup"><span data-stu-id="90806-296">**On-premises skip**</span></span>
  - <span data-ttu-id="90806-297">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="90806-297">**IP Allow**</span></span>
  - <span data-ttu-id="90806-298">**メール フロー ルール**</span><span class="sxs-lookup"><span data-stu-id="90806-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="90806-299">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="90806-299">**Sender allow**</span></span>
  - <span data-ttu-id="90806-300">**ドメインの許可**</span><span class="sxs-lookup"><span data-stu-id="90806-300">**Domain allow**</span></span>
  - <span data-ttu-id="90806-301">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="90806-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="90806-302">**迷惑メール フォルダーが有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="90806-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="90806-303">**ユーザーの差出人セーフ リスト**</span><span class="sxs-lookup"><span data-stu-id="90806-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="90806-304">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-304">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージ上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="90806-306">**詳しくは、「検出テクノロジ」と「\*\*\*\*データの表示方法 \> :メール** フィッシング」をご覧ください。次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="90806-307">**ATP 生成 URL 評価**<sup>1</sup>: 他の Microsoft 365 ユーザーの Office 365 分析に対して Defender から生成された悪意のある URL 評価。</span><span class="sxs-lookup"><span data-stu-id="90806-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="90806-308">**高度なフィッシング フィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="90806-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="90806-309">**スプーフィング対策 - DMARC エラー**: メッセージに対する DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="90806-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="90806-310">**スプーフィング対策 - 組織内**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="90806-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="90806-311">**スプーフィング対策 - 外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="90806-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="90806-312">**ブランド偽装**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="90806-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="90806-313">**ドメイン偽装**<sup>1</sup>: 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="90806-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="90806-314">**EOP URL 評価**: 悪意のある URL 評価。</span><span class="sxs-lookup"><span data-stu-id="90806-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="90806-315">**一般的なフィッシング フィルター**: アナリストのルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="90806-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="90806-316">**Others**</span><span class="sxs-lookup"><span data-stu-id="90806-316">**Others**</span></span>
  - <span data-ttu-id="90806-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span><span class="sxs-lookup"><span data-stu-id="90806-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="90806-318">**URL デトレーション**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90806-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="90806-319">**ユーザー偽装**<sup>1</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="90806-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="90806-321">**ブレークダウン: 検出テクノロジと\*\*\*\*データの表示方法: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90806-322">**ATP 生成ファイル評価**<sup>1</sup>: 365 回の分析のために Defender によって生成Officeファイル評価。</span><span class="sxs-lookup"><span data-stu-id="90806-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="90806-323">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="90806-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="90806-324">**マルウェア対策ポリシーのファイルの種類** ブロック : これらは、メッセージで識別された悪意のあるファイルの種類のためにフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="90806-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="90806-325">**ファイル分析**<sup>1</sup>: 安全な添付ファイルによる検出。</span><span class="sxs-lookup"><span data-stu-id="90806-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="90806-326">**悪意のあるファイル評価**</span><span class="sxs-lookup"><span data-stu-id="90806-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="90806-327">**マルウェア ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="90806-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="90806-328">**Others**</span><span class="sxs-lookup"><span data-stu-id="90806-328">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="90806-330">**詳しくは、「** ポリシーの種類」と「データの表示 **方法: \>** 電子メール フィッシング」または「データの **表示方法:電子メール \> マルウェア**」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90806-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90806-331">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="90806-331">**Anti-malware**</span></span>
  - <span data-ttu-id="90806-332">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90806-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="90806-333">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="90806-333">**Anti-phish**</span></span>
  - <span data-ttu-id="90806-334">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="90806-334">**Anti-spam**</span></span>
  - <span data-ttu-id="90806-335">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="90806-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="90806-336">**Others**</span><span class="sxs-lookup"><span data-stu-id="90806-336">**Others**</span></span>

  ![脅威保護状態レポートのフィッシング メールのポリシーの種類ビュー](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="90806-338">**配信の状態と** データの表示 **\>** 方法:メール フィッシングまたはデータの表示方法:メール **\> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90806-339">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="90806-339">**Delivery failed**</span></span>
  - <span data-ttu-id="90806-340">**破棄**</span><span class="sxs-lookup"><span data-stu-id="90806-340">**Dropped**</span></span>
  - <span data-ttu-id="90806-341">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="90806-341">**Forwarded**</span></span>
  - <span data-ttu-id="90806-342">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="90806-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="90806-343">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="90806-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="90806-344">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="90806-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="90806-345">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="90806-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="90806-346">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="90806-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="90806-347">**検疫**</span><span class="sxs-lookup"><span data-stu-id="90806-347">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="90806-349"><sup>365</sup> の場合のみ 1 Office Defender</span><span class="sxs-lookup"><span data-stu-id="90806-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="90806-350"><sup>2</sup> ゼロアワー自動消去 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ機能します)。</span><span class="sxs-lookup"><span data-stu-id="90806-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="90806-351">[フィルター] **をクリック** すると、使用できるフィルターは表示していたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="90806-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="90806-352">[**データの表示方法]: コンテンツ \> マルウェア** の場合は、開始日と終了日、および検出値でレポートを **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="90806-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="90806-353">[ **データの表示方法]: [メッセージの上書** き] では、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="90806-354">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-355">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="90806-355">**Override Reason**</span></span>
  - <span data-ttu-id="90806-356">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="90806-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="90806-357">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="90806-358">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-358">**Domain**</span></span>

- <span data-ttu-id="90806-359">その他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="90806-360">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-361">**検出**</span><span class="sxs-lookup"><span data-stu-id="90806-361">**Detection**</span></span>
  - <span data-ttu-id="90806-362">**Protected by**: **ATP** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="90806-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="90806-363">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="90806-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="90806-364">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="90806-365">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="90806-366">脅威保護状態レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90806-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="90806-367">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="90806-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="90806-368">**View data by: Overview**: No **View details table** button is available.</span><span class="sxs-lookup"><span data-stu-id="90806-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="90806-369">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="90806-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="90806-370">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-370">**Date**</span></span>
  - <span data-ttu-id="90806-371">**Location**</span><span class="sxs-lookup"><span data-stu-id="90806-371">**Location**</span></span>
  - <span data-ttu-id="90806-372">**提供者**</span><span class="sxs-lookup"><span data-stu-id="90806-372">**Directed by**</span></span>
  - <span data-ttu-id="90806-373">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="90806-373">**Malware name**</span></span>

  <span data-ttu-id="90806-374">このビューで **[フィルター]** をクリックすると、開始日と終了日、および検出値によってレポートを **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="90806-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="90806-375">**View data by: Message Override**:</span><span class="sxs-lookup"><span data-stu-id="90806-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="90806-376">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-376">**Date**</span></span>
  - <span data-ttu-id="90806-377">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90806-377">**Subject**</span></span>
  - <span data-ttu-id="90806-378">**送信者**</span><span class="sxs-lookup"><span data-stu-id="90806-378">**Sender**</span></span>
  - <span data-ttu-id="90806-379">**受信者**</span><span class="sxs-lookup"><span data-stu-id="90806-379">**Recipients**</span></span>
  - <span data-ttu-id="90806-380">**検出者**</span><span class="sxs-lookup"><span data-stu-id="90806-380">**Detected by**</span></span>
  - <span data-ttu-id="90806-381">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="90806-381">**Override Reason**</span></span>
  - <span data-ttu-id="90806-382">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="90806-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="90806-383">**Tags**</span><span class="sxs-lookup"><span data-stu-id="90806-383">**Tags**</span></span>

  <span data-ttu-id="90806-384">このビューで **[フィルター]** をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="90806-385">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-386">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="90806-386">**Override Reason**</span></span>
  - <span data-ttu-id="90806-387">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="90806-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="90806-388">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="90806-389">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-389">**Domain**</span></span>
  - <span data-ttu-id="90806-390">**受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="90806-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="90806-391">その他すべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="90806-391">All other charts:</span></span>

  - <span data-ttu-id="90806-392">**Date**</span><span class="sxs-lookup"><span data-stu-id="90806-392">**Date**</span></span>
  - <span data-ttu-id="90806-393">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90806-393">**Subject**</span></span>
  - <span data-ttu-id="90806-394">**送信者**</span><span class="sxs-lookup"><span data-stu-id="90806-394">**Sender**</span></span>
  - <span data-ttu-id="90806-395">**受信者**</span><span class="sxs-lookup"><span data-stu-id="90806-395">**Recipients**</span></span>
  - <span data-ttu-id="90806-396">**検出者**</span><span class="sxs-lookup"><span data-stu-id="90806-396">**Detected by**</span></span>
  - <span data-ttu-id="90806-397">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="90806-397">**Delivery Status**</span></span>
  - <span data-ttu-id="90806-398">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="90806-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="90806-399">**Tags**</span><span class="sxs-lookup"><span data-stu-id="90806-399">**Tags**</span></span>

  <span data-ttu-id="90806-400">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90806-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="90806-401">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="90806-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90806-402">**検出**</span><span class="sxs-lookup"><span data-stu-id="90806-402">**Detection**</span></span>
  - <span data-ttu-id="90806-403">**Protected by**: **Defender for Office 365** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="90806-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="90806-404">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="90806-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="90806-405">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="90806-406">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90806-406">**Domain**</span></span>
  - <span data-ttu-id="90806-407">**受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="90806-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="90806-408">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="90806-408">Top malware report</span></span>

<span data-ttu-id="90806-409">Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="90806-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="90806-410">レポートを表示するには、セキュリティ/コンプライアンス センターを [&](https://protection.office.com)レポート **ダッシュボード** に移動し、[上位マルウェア] \> を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90806-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="90806-411">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="90806-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポート ダッシュボードの上位マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="90806-413">円グラフでくさびの上にマウス ポインターを移動すると、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="90806-415">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90806-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90806-416">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="90806-416">**Top malware**</span></span>
- <span data-ttu-id="90806-417">**Count**</span><span class="sxs-lookup"><span data-stu-id="90806-417">**Count**</span></span>

<span data-ttu-id="90806-418">レポート ビュー **または詳細** テーブル ビューで [フィルター] をクリックすると、開始日と終了日で日付範囲 **を\*\*\*\*指定できます**。</span><span class="sxs-lookup"><span data-stu-id="90806-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="90806-419">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="90806-419">URL threat protection report</span></span>

<span data-ttu-id="90806-420">URL **脅威保護レポートは、Microsoft** Defender で Office 365 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="90806-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="90806-421">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="90806-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="90806-422">ユーザーから報告されたメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="90806-422">User-reported messages report</span></span>

<span data-ttu-id="90806-423">ユーザー **から報告されたメッセージ** レポートには、迷惑メール、フィッシング詐欺、または良いメールとして報告された電子メール メッセージに関する情報が、レポート メッセージ アドインを使用 [して表示されます](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="90806-424">配信理由など、組織に対して構成されたスパム ポリシーの例外やメール フロー ルールなど、メッセージごとに詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90806-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="90806-425">詳細を表示するには、ユーザー レポート リストでアイテムを選択し、[概要] タブと [詳細] タブ **で情報** を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="90806-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![[User-Reported メッセージ] レポートには、迷惑メール、迷惑メール、フィッシングの試行としてラベルが付いたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="90806-427">このレポートを表示するには、セキュリティ & [コンプライアンス センターで、](https://protection.office.com)次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="90806-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="90806-428">脅威管理 **ダッシュボードのユーザー** \> **から** \> **報告されたメッセージに移動します**。</span><span class="sxs-lookup"><span data-stu-id="90806-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="90806-429">[脅威の **管理] ユーザーから** \> **報告** \> **されたメッセージを確認するに移動します**。</span><span class="sxs-lookup"><span data-stu-id="90806-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ/コンプライアンス センターで、[脅威&レビュー ユーザーが \> 報告 \> したメッセージ] を選択します。](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="90806-431">ユーザーから報告されたメッセージ レポートが正しく機能するには、365 環境で監査ログOfficeする必要があります。 </span><span class="sxs-lookup"><span data-stu-id="90806-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="90806-432">これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="90806-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="90806-433">詳細については [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)監査ログ検索を有効またはオフにする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90806-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="90806-434">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="90806-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="90806-435">この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&があります。</span><span class="sxs-lookup"><span data-stu-id="90806-435">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="90806-436">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="90806-436">**Organization Management**</span></span>
- <span data-ttu-id="90806-437">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="90806-437">**Security Administrator**</span></span>
- <span data-ttu-id="90806-438">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="90806-438">**Security Reader**</span></span>
- <span data-ttu-id="90806-439">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="90806-439">**Global Reader**</span></span>

<span data-ttu-id="90806-440">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90806-440">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="90806-441">**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="90806-441">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="90806-442">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90806-442">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="90806-443">レポートにデータが表示されない場合</span><span class="sxs-lookup"><span data-stu-id="90806-443">What if the reports aren't showing data?</span></span>

<span data-ttu-id="90806-444">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="90806-444">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="90806-445">詳細については、「脅威からの保護 [」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="90806-445">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="90806-446">関連項目</span><span class="sxs-lookup"><span data-stu-id="90806-446">Related topics</span></span>

[<span data-ttu-id="90806-447">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="90806-447">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="90806-448">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="90806-448">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="90806-449">セキュリティ/コンプライアンス センターでメール フロー レポート&表示する</span><span class="sxs-lookup"><span data-stu-id="90806-449">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="90806-450">Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="90806-450">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
