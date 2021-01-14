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
ms.openlocfilehash: 568144c449d2f1a70082130cc847d48c3486d9da
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865106"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="b93c5-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b93c5-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b93c5-105">セキュリティ & コンプライアンス センターでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護する方法を確認するのに役立つさまざまなレポートが用意されています。 [](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="b93c5-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="b93c5-106">必要な [アクセス許可がある](#what-permissions-are-needed-to-view-these-reports)場合は、レポート ダッシュボードに移動して、セキュリティ/コンプライアンス センター&レポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b93c5-107">レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ/コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="b93c5-109">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="b93c5-110">このレポートは、Exchange Online メールボックスを使用している Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="b93c5-111">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b93c5-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="b93c5-112">[**侵害されたユーザー]** レポートには、過去 7 日以内に[不審] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="b93c5-113">これらのいずれかの状態のアカウントは、問題がある場合や、侵害されている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="b93c5-114">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限されたアカウントのスパイクや傾向を特定できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="b93c5-115">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの対応 [」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポート ダッシュボードの侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="b93c5-117">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="b93c5-118">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&**ダッシュボード** に移動し、[侵害されたユーザー \>  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="b93c5-119">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="b93c5-120">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b93c5-121">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="b93c5-122">**不審**: ユーザー アカウントが不審なメールを送信し、電子メールの送信が制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="b93c5-123">**制限**: 不審なパターンが原因で、ユーザー アカウントによるメールの送信が制限されています。</span><span class="sxs-lookup"><span data-stu-id="b93c5-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザー レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="b93c5-125">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b93c5-126">**作成時刻**</span><span class="sxs-lookup"><span data-stu-id="b93c5-126">**Creation time**</span></span>
- <span data-ttu-id="b93c5-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-127">**User ID**</span></span>
- <span data-ttu-id="b93c5-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="b93c5-128">**Action**</span></span>

<span data-ttu-id="b93c5-129">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="b93c5-130">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-130">Encryption report</span></span>

<span data-ttu-id="b93c5-131">暗号化 **レポートは** 、EOP (Exchange Online のメールボックスを持つサブスクリプション、または Exchange Online メールボックスを使用しないスタンドアロン EOP) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="b93c5-132">組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーを事前に適用または調整できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="b93c5-133">例:</span><span class="sxs-lookup"><span data-stu-id="b93c5-133">For example:</span></span>

- <span data-ttu-id="b93c5-134">ユーザーによって暗号化された電子メール メッセージの数が多い場合は、暗号化ポリシーを追加して、特定の使用例の暗号化を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="b93c5-135">詳細については [、「Microsoft 365 でメール メッセージを暗号化するメール](../../compliance/define-mail-flow-rules-to-encrypt-email.md)フロー ルールを定義する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93c5-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="b93c5-136">利用可能な暗号化テンプレートが多数あるが、誰も使用できない場合は、ユーザーが機能トレーニングを必要とするかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="b93c5-137">集計ビューでは過去 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="b93c5-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="b93c5-138">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&レポート ダッシュボード **に移動し**、[暗号化] \> レポート **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="b93c5-139">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="b93c5-140">暗号化の詳細については [、「Microsoft 365 での電子メールの暗号化」を参照してください](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="b93c5-141">暗号化レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-141">Report view for the Encryption report</span></span>

<span data-ttu-id="b93c5-142">グラフでは、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="b93c5-143">**データの表示方法: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span><span class="sxs-lookup"><span data-stu-id="b93c5-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="b93c5-144">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="b93c5-144">**Encryption by user**</span></span>
  - <span data-ttu-id="b93c5-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="b93c5-145">**Encryption by policy**</span></span>

  <span data-ttu-id="b93c5-146">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="b93c5-147">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="b93c5-148">Encryption method.</span></span>
  - <span data-ttu-id="b93c5-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="b93c5-149">Encryption template.</span></span>

- <span data-ttu-id="b93c5-150">**データの表示方法: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span><span class="sxs-lookup"><span data-stu-id="b93c5-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="b93c5-151">**転送しない**</span><span class="sxs-lookup"><span data-stu-id="b93c5-151">**Do not forward**</span></span>
  - <span data-ttu-id="b93c5-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="b93c5-152">**Encrypt only**</span></span>
  - <span data-ttu-id="b93c5-153">**前の OME**</span><span class="sxs-lookup"><span data-stu-id="b93c5-153">**OME previous**</span></span>
  - <span data-ttu-id="b93c5-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="b93c5-154">**Custom**</span></span>

  <span data-ttu-id="b93c5-155">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="b93c5-156">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="b93c5-157">Encryption method</span></span>
  - <span data-ttu-id="b93c5-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="b93c5-158">Encryption template</span></span>

- <span data-ttu-id="b93c5-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span><span class="sxs-lookup"><span data-stu-id="b93c5-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="b93c5-160">[フィルター]**をクリック** すると、開始日と **終了日を\*\*\*\*選択できます**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="b93c5-161">暗号化レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="b93c5-162">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b93c5-163">**[Break down by: Encryption method] (暗号化方法** ) または **[Break down by]**(暗号化テンプレート): 次の情報を示します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="b93c5-164">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-164">**Date**</span></span>
  - <span data-ttu-id="b93c5-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-165">**Sender address**</span></span>
  - <span data-ttu-id="b93c5-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="b93c5-166">**Encryption template**</span></span>
  - <span data-ttu-id="b93c5-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="b93c5-167">**Encryption method**</span></span>
  - <span data-ttu-id="b93c5-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="b93c5-168">**Recipient address**</span></span>
  - <span data-ttu-id="b93c5-169">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-169">**Subject**</span></span>

- <span data-ttu-id="b93c5-170">**データの表示方法: 上位 5 つの受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="b93c5-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="b93c5-171">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-171">**Date**</span></span>
  - <span data-ttu-id="b93c5-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-172">**Recipient domain**</span></span>
  - <span data-ttu-id="b93c5-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="b93c5-173">**Message count**</span></span>

<span data-ttu-id="b93c5-174">詳細テーブル ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b93c5-175">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="b93c5-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="b93c5-176">Encryption method</span></span>
- <span data-ttu-id="b93c5-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="b93c5-177">Encryption template</span></span>

<span data-ttu-id="b93c5-178">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b93c5-179">メールフロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-179">Mailflow status report</span></span>

<span data-ttu-id="b93c5-180">Mailflow **ステータス レポートには、** マルウェア、スパム、フィッシング、およびエッジでブロックされたメッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="b93c5-181">詳細については、「メールフローの [状態レポート」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="b93c5-182">メール レポートでのマルウェアの検出</span><span class="sxs-lookup"><span data-stu-id="b93c5-182">Malware detections in email report</span></span>

<span data-ttu-id="b93c5-183">電子 **メール レポートのマルウェア検出** では、受信および送信電子メール メッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) のマルウェア検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="b93c5-184">EOP でのマルウェア保護の詳細については、「EOP での [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="b93c5-185">集計ビュー フィルターでは 90 日間、詳細テーブルフィルターは 10 日間のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="b93c5-186">レポートを表示するには、[セキュリティ](https://protection.office.com)/コンプライアンス センターを&レポート ダッシュボードに移動し、メールで \> **[マルウェアの検出] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="b93c5-187">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポート ダッシュボードのメール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

<span data-ttu-id="b93c5-189">[フィルター] をクリックして次の項目を選択すると、グラフと詳細テーブル **の両方** をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="b93c5-190">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="b93c5-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-191">**Inbound**</span></span>
- <span data-ttu-id="b93c5-192">**送信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-192">**Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="b93c5-194">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b93c5-195">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-195">**Date**</span></span>
- <span data-ttu-id="b93c5-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-196">**Sender address**</span></span>
- <span data-ttu-id="b93c5-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="b93c5-197">**Recipient address**</span></span>
- <span data-ttu-id="b93c5-198">**メッセージ ID**: メッセージ ヘッダーの **Message-ID** ヘッダー フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="b93c5-199">値の例を `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次に示します (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="b93c5-200">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-200">**Subject**</span></span>
- <span data-ttu-id="b93c5-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="b93c5-201">**Filename**</span></span>
- <span data-ttu-id="b93c5-202">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="b93c5-202">**Malware name**</span></span>

<span data-ttu-id="b93c5-203">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-203">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b93c5-204">メール待機時間レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-204">Mail latency report</span></span>

<span data-ttu-id="b93c5-205">メール **の待機時間レポートには** 、組織内で発生したメール配信と分析の待機時間に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="b93c5-205">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b93c5-206">詳細については、「メールの待機時間 [レポート」を参照してください](view-reports-for-atp.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-206">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b93c5-207">送信および受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-207">Sent and received email report</span></span>

<span data-ttu-id="b93c5-208">送信 **および受信メール** レポートには、マルウェア、スパム、メール フロー ルール (トランスポート ルールとも呼ばれる)、およびメールがサービスに入った後の高度なマルウェア検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b93c5-208">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="b93c5-209">詳細については、「送信および受信 [メール レポート」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-209">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="b93c5-210">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-210">Spam detections report</span></span>

<span data-ttu-id="b93c5-211">スパム **検出レポートには** 、EOP によってブロックされたスパム 電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-211">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="b93c5-212">メッセージは個別にカウントされ、受信者ごとにカウントされません。</span><span class="sxs-lookup"><span data-stu-id="b93c5-212">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="b93c5-213">たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、1 つのメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-213">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="b93c5-214">集計ビューでは 90 日間のフィルター処理が可能で、詳細テーブルでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="b93c5-214">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="b93c5-215">レポートを表示するには、セキュリティ/コンプライアンス センターを [開](https://protection.office.com)&ダッシュボード **に移動し**、[スパム検出] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-215">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="b93c5-216">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-216">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="b93c5-218">スパム対策保護の詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-218">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="b93c5-219">スパム検出レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-219">Report view for the Spam detections report</span></span>

<span data-ttu-id="b93c5-220">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-220">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b93c5-221">**[Break down by: Action]:** 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-221">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="b93c5-222">**フィルター処理されたスパム コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="b93c5-222">**Spam content filtered**</span></span>
  - <span data-ttu-id="b93c5-223">**スパム IP ブロック**</span><span class="sxs-lookup"><span data-stu-id="b93c5-223">**Spam IP block**</span></span>
  - <span data-ttu-id="b93c5-224">**スパム エンベロープ ブロック**</span><span class="sxs-lookup"><span data-stu-id="b93c5-224">**Spam envelope block**</span></span>
  - <span data-ttu-id="b93c5-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span><span class="sxs-lookup"><span data-stu-id="b93c5-225">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="b93c5-226">グラフ内の 1 日 (データ ポイント) の上にマウス ポインターを移動すると、その日にブロックされたアイテムの数と、それらのアイテムの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-226">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="b93c5-228">**[Break down by: Direction]**(方向): 次の方向を示します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-228">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="b93c5-229">**受信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-229">**Inbound**</span></span>
  - <span data-ttu-id="b93c5-230">**送信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-230">**Outbound**</span></span>

  ![スパム検出レポートの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="b93c5-232">レポート ビューで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-232">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b93c5-233">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-233">**Start date** and **End date**</span></span>
- <span data-ttu-id="b93c5-234">方向の値</span><span class="sxs-lookup"><span data-stu-id="b93c5-234">Direction values</span></span>
- <span data-ttu-id="b93c5-235">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="b93c5-235">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="b93c5-236">スパム検出レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-236">Details table view for the Spam detections report</span></span>

<span data-ttu-id="b93c5-237">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-237">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="b93c5-238">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-238">**Date**</span></span>
- <span data-ttu-id="b93c5-239">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-239">**Sender address**</span></span>
- <span data-ttu-id="b93c5-240">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="b93c5-240">**Recipient address**</span></span>
- <span data-ttu-id="b93c5-241">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="b93c5-241">**Event type**</span></span>
- <span data-ttu-id="b93c5-242">**操作**</span><span class="sxs-lookup"><span data-stu-id="b93c5-242">**Action**</span></span>
- <span data-ttu-id="b93c5-243">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-243">**Subject**</span></span>

<span data-ttu-id="b93c5-244">詳細テーブルで **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-244">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b93c5-245">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-245">**Start date** and **End date**</span></span>
- <span data-ttu-id="b93c5-246">方向の値</span><span class="sxs-lookup"><span data-stu-id="b93c5-246">Direction values</span></span>
- <span data-ttu-id="b93c5-247">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="b93c5-247">Event type values</span></span>

<span data-ttu-id="b93c5-248">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-248">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="b93c5-249">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-249">Spoof detections report</span></span>

<span data-ttu-id="b93c5-250">ス **プーフィン** グ検出レポートには、検出されたスプーフィング メール メッセージの数と、それらのスプーフィング メール メッセージの数が示されます。それらのメッセージは "良好" と見なされました (正当なビジネス上の理由で行われたスプーフィング メール)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-250">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="b93c5-251">スプーフィングの詳細については、「EOP でのスプーフィング対策 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-251">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b93c5-252">レポートの集計ビューでは 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="b93c5-252">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="b93c5-253">レポートを表示するには、Security [& Compliance Center](https://protection.office.com)を開き、[**レポート** ダッシュボード] に移動し、[スプーフィング \> **の検出] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-253">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="b93c5-254">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-254">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="b93c5-256">グラフの 1 日 (データ ポイント) をポイントすると、スプーフィング メール メッセージの受信数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-256">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="b93c5-257">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-257">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b93c5-258">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-258">**Start date** and **End date**</span></span>

- <span data-ttu-id="b93c5-259">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="b93c5-259">**Good mail**</span></span>

- <span data-ttu-id="b93c5-260">**スパムとして検出された**</span><span class="sxs-lookup"><span data-stu-id="b93c5-260">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="b93c5-262">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-262">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b93c5-263">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-263">**Date**</span></span>
- <span data-ttu-id="b93c5-264">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-264">**Spoofed sender**</span></span>
- <span data-ttu-id="b93c5-265">**真の送信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-265">**True sender**</span></span>
- <span data-ttu-id="b93c5-266">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="b93c5-266">**Sender IP**</span></span>
- <span data-ttu-id="b93c5-267">**操作**</span><span class="sxs-lookup"><span data-stu-id="b93c5-267">**Action**</span></span>
- <span data-ttu-id="b93c5-268">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="b93c5-268">**Message count**</span></span>

<span data-ttu-id="b93c5-269">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-269">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="b93c5-270">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-270">Threat protection status report</span></span>

<span data-ttu-id="b93c5-271">脅威 **保護状態レポート** は、EOP と Microsoft Defender の両方で、Office 365 で利用できます。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="b93c5-271">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="b93c5-272">たとえば、EOP のお客様は電子メールで検出されたマルウェアに関する情報を表示できますが [、ATP for SharePoint、OneDrive、または Microsoft Teams](atp-for-spo-odb-and-teams.md)で検出された悪意のあるファイルに関する情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="b93c5-272">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b93c5-273">このレポートは、マルウェア対策エンジン、ゼロアワー自動消去[(ZAP)、Defender](zero-hour-auto-purge.md)for Office 365 の機能 (安全なリンク、安全な添付ファイル、フィッシング対策など) によってブロックされたファイルや Web サイト アドレス[](atp-safe-attachments.md)(URL)[](set-up-anti-phishing-policies.md)など、悪意のあるコンテンツを含む電子メール メッセージの数を提供します。 [](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b93c5-273">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="b93c5-274">この情報を使用して、傾向を特定したり、組織のポリシーに調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-274">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="b93c5-275">**注**: メッセージが 5 人の受信者に送信される場合、1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされる点を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b93c5-275">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b93c5-276">レポートを表示するには、Security [& Compliance Center](https://protection.office.com)を開き、[**レポート** ダッシュボード] に移動し、[脅威保護の状態 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-276">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="b93c5-277">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-277">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="b93c5-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="b93c5-278">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="b93c5-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="b93c5-279">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="b93c5-281">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-281">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="b93c5-282">[フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションの期間は 30 日間に制限されます)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-282">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="b93c5-283">詳細テーブル ビューでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="b93c5-283">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="b93c5-284">脅威保護状態レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-284">Report view for the Threat protection status report</span></span>

<span data-ttu-id="b93c5-285">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-285">The following views are available:</span></span>

- <span data-ttu-id="b93c5-286">**データの表示方法: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-286">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="b93c5-287">**マルウェアへのメール送信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-287">**Email malware**</span></span>
  - <span data-ttu-id="b93c5-288">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="b93c5-288">**Email phish**</span></span>
  - <span data-ttu-id="b93c5-289">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="b93c5-289">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="b93c5-291">**データの表示方法: コンテンツ \> マルウェア**<sup>1:</sup>次の情報は、365 組織の Microsoft Defender Office示されています。</span><span class="sxs-lookup"><span data-stu-id="b93c5-291">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="b93c5-292">**マルウェア対策エンジン**: [Microsoft 365](virus-detection-in-spo.md)の組み込みウイルス検出により、Sharepoint、OneDrive、および Microsoft Teams で悪意のあるファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="b93c5-292">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="b93c5-293">**ファイル分析**: [Sharepoint、OneDrive、および Microsoft Teams](atp-for-spo-odb-and-teams.md)の ATP によって検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="b93c5-293">**File detonation**: Malicious files detected by [ATP for Sharepoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="b93c5-295">**データの表示:メッセージの上書き**: 次の上書き理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-295">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="b93c5-296">**オンプレミス のスキップ**</span><span class="sxs-lookup"><span data-stu-id="b93c5-296">**On-premises skip**</span></span>
  - <span data-ttu-id="b93c5-297">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="b93c5-297">**IP Allow**</span></span>
  - <span data-ttu-id="b93c5-298">**メール フロー ルール**</span><span class="sxs-lookup"><span data-stu-id="b93c5-298">**Mail flow rule**</span></span>
  - <span data-ttu-id="b93c5-299">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="b93c5-299">**Sender allow**</span></span>
  - <span data-ttu-id="b93c5-300">**ドメインの許可**</span><span class="sxs-lookup"><span data-stu-id="b93c5-300">**Domain allow**</span></span>
  - <span data-ttu-id="b93c5-301">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="b93c5-301">**ZAP not enabled**</span></span>
  - <span data-ttu-id="b93c5-302">**迷惑メール フォルダーが有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="b93c5-302">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="b93c5-303">**ユーザーの差出人セーフ リスト**</span><span class="sxs-lookup"><span data-stu-id="b93c5-303">**User Safe Sender**</span></span>
  - <span data-ttu-id="b93c5-304">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-304">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージ上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="b93c5-306">**詳しくは、「検出テクノロジ」と「\*\*\*\*データの表示方法 \> :メール** フィッシング」をご覧ください。次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-306">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="b93c5-307">**ATP 生成 URL 評価**<sup>1</sup>: 他の Microsoft 365 ユーザーの Office 365 分析に対して Defender から生成された悪意のある URL 評価。</span><span class="sxs-lookup"><span data-stu-id="b93c5-307">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="b93c5-308">**高度なフィッシング フィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="b93c5-308">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="b93c5-309">**スプーフィング対策 - DMARC エラー**: メッセージに対する DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="b93c5-309">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="b93c5-310">**スプーフィング対策 - 組織内**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="b93c5-310">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="b93c5-311">**スプーフィング対策 - 外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="b93c5-311">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="b93c5-312">**ブランド偽装**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="b93c5-312">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="b93c5-313">**ドメイン偽装**<sup>1</sup>: 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="b93c5-313">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="b93c5-314">**EOP URL 評価**: 悪意のある URL 評価。</span><span class="sxs-lookup"><span data-stu-id="b93c5-314">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="b93c5-315">**一般的なフィッシング フィルター**: アナリストのルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="b93c5-315">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="b93c5-316">**Others**</span><span class="sxs-lookup"><span data-stu-id="b93c5-316">**Others**</span></span>
  - <span data-ttu-id="b93c5-317">**フィッシング ZAP**<sup>2</sup>: フィッシング メッセージのゼロアワー自動消去。</span><span class="sxs-lookup"><span data-stu-id="b93c5-317">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="b93c5-318">**URL デトレーション**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b93c5-318">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="b93c5-319">**ユーザー偽装**<sup>1</sup>: 管理者によって定義された、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="b93c5-319">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="b93c5-321">**ブレークダウン: 検出テクノロジと\*\*\*\*データの表示方法: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-321">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b93c5-322">**ATP 生成ファイル評価**<sup>1</sup>: Defender によって 365 回の分析のために生成Office悪意のあるファイル評価。</span><span class="sxs-lookup"><span data-stu-id="b93c5-322">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="b93c5-323">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="b93c5-323">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="b93c5-324">**マルウェア対策ポリシーのファイルの種類** ブロック : これらは、メッセージで識別された悪意のあるファイルの種類のためにフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="b93c5-324">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="b93c5-325">**ファイル分析**<sup>1</sup>: 安全な添付ファイルによる検出。</span><span class="sxs-lookup"><span data-stu-id="b93c5-325">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="b93c5-326">**悪意のあるファイル評価**</span><span class="sxs-lookup"><span data-stu-id="b93c5-326">**Malicious file reputation**</span></span>
  - <span data-ttu-id="b93c5-327">**マルウェア ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b93c5-327">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="b93c5-328">**Others**</span><span class="sxs-lookup"><span data-stu-id="b93c5-328">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="b93c5-330">**ブレークダウン:ポリシーの種類** とデータ **の表示方法: メール \> フィッシング** またはデータの **表示方法: 電子メール \> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-330">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b93c5-331">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="b93c5-331">**Anti-malware**</span></span>
  - <span data-ttu-id="b93c5-332">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b93c5-332">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="b93c5-333">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="b93c5-333">**Anti-phish**</span></span>
  - <span data-ttu-id="b93c5-334">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="b93c5-334">**Anti-spam**</span></span>
  - <span data-ttu-id="b93c5-335">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="b93c5-335">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="b93c5-336">**Others**</span><span class="sxs-lookup"><span data-stu-id="b93c5-336">**Others**</span></span>

  ![脅威保護状態レポートのフィッシング メールのポリシーの種類ビュー](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="b93c5-338">**配信の状態と** データの表示 **\>** 方法:メール フィッシングまたはデータの表示方法:メール **\> マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-338">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b93c5-339">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="b93c5-339">**Delivery failed**</span></span>
  - <span data-ttu-id="b93c5-340">**破棄**</span><span class="sxs-lookup"><span data-stu-id="b93c5-340">**Dropped**</span></span>
  - <span data-ttu-id="b93c5-341">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="b93c5-341">**Forwarded**</span></span>
  - <span data-ttu-id="b93c5-342">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="b93c5-342">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="b93c5-343">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="b93c5-343">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="b93c5-344">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="b93c5-344">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="b93c5-345">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="b93c5-345">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="b93c5-346">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="b93c5-346">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="b93c5-347">**検疫**</span><span class="sxs-lookup"><span data-stu-id="b93c5-347">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="b93c5-349"><sup>365</sup> の場合のみ 1 Office Defender</span><span class="sxs-lookup"><span data-stu-id="b93c5-349"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b93c5-350"><sup>2</sup> ゼロアワー自動消去 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ機能します)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-350"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="b93c5-351">[フィルター] **をクリック** すると、使用できるフィルターは、表示していたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-351">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b93c5-352">[**データの表示方法]: コンテンツ \> マルウェア** の場合は、開始日と終了日、および検出値でレポートを **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-352">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="b93c5-353">[ **データの表示方法]: [メッセージの上書** き] では、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-353">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b93c5-354">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-354">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-355">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="b93c5-355">**Override Reason**</span></span>
  - <span data-ttu-id="b93c5-356">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-356">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b93c5-357">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-357">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b93c5-358">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-358">**Domain**</span></span>

- <span data-ttu-id="b93c5-359">その他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-359">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b93c5-360">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-360">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-361">**検出**</span><span class="sxs-lookup"><span data-stu-id="b93c5-361">**Detection**</span></span>
  - <span data-ttu-id="b93c5-362">**Protected by**: **ATP** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="b93c5-362">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="b93c5-363">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-363">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b93c5-364">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-364">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b93c5-365">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-365">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="b93c5-366">脅威保護状態レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="b93c5-366">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="b93c5-367">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-367">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b93c5-368">**View data by: Overview**: No **View details table** button is available.</span><span class="sxs-lookup"><span data-stu-id="b93c5-368">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="b93c5-369">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="b93c5-369">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="b93c5-370">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-370">**Date**</span></span>
  - <span data-ttu-id="b93c5-371">**Location**</span><span class="sxs-lookup"><span data-stu-id="b93c5-371">**Location**</span></span>
  - <span data-ttu-id="b93c5-372">**提供者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-372">**Directed by**</span></span>
  - <span data-ttu-id="b93c5-373">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="b93c5-373">**Malware name**</span></span>

  <span data-ttu-id="b93c5-374">このビューで **[フィルター** ] をクリックすると、レポートを開始日と終了日、および検出値で **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-374">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="b93c5-375">**View data by: Message Override**:</span><span class="sxs-lookup"><span data-stu-id="b93c5-375">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="b93c5-376">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-376">**Date**</span></span>
  - <span data-ttu-id="b93c5-377">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-377">**Subject**</span></span>
  - <span data-ttu-id="b93c5-378">**送信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-378">**Sender**</span></span>
  - <span data-ttu-id="b93c5-379">**受信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-379">**Recipients**</span></span>
  - <span data-ttu-id="b93c5-380">**検出者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-380">**Detected by**</span></span>
  - <span data-ttu-id="b93c5-381">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="b93c5-381">**Override Reason**</span></span>
  - <span data-ttu-id="b93c5-382">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="b93c5-382">**Source of Compromise**</span></span>
  - <span data-ttu-id="b93c5-383">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b93c5-383">**Tags**</span></span>

  <span data-ttu-id="b93c5-384">このビューで **[フィルター]** をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-384">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b93c5-385">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-385">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-386">**上書き理由**</span><span class="sxs-lookup"><span data-stu-id="b93c5-386">**Override Reason**</span></span>
  - <span data-ttu-id="b93c5-387">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-387">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b93c5-388">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-388">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b93c5-389">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-389">**Domain**</span></span>
  - <span data-ttu-id="b93c5-390">**受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="b93c5-390">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="b93c5-391">その他すべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="b93c5-391">All other charts:</span></span>

  - <span data-ttu-id="b93c5-392">**日付**</span><span class="sxs-lookup"><span data-stu-id="b93c5-392">**Date**</span></span>
  - <span data-ttu-id="b93c5-393">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="b93c5-393">**Subject**</span></span>
  - <span data-ttu-id="b93c5-394">**送信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-394">**Sender**</span></span>
  - <span data-ttu-id="b93c5-395">**受信者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-395">**Recipients**</span></span>
  - <span data-ttu-id="b93c5-396">**検出者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-396">**Detected by**</span></span>
  - <span data-ttu-id="b93c5-397">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="b93c5-397">**Delivery Status**</span></span>
  - <span data-ttu-id="b93c5-398">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="b93c5-398">**Source of Compromise**</span></span>
  - <span data-ttu-id="b93c5-399">**Tags**</span><span class="sxs-lookup"><span data-stu-id="b93c5-399">**Tags**</span></span>

  <span data-ttu-id="b93c5-400">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-400">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b93c5-401">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="b93c5-401">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b93c5-402">**検出**</span><span class="sxs-lookup"><span data-stu-id="b93c5-402">**Detection**</span></span>
  - <span data-ttu-id="b93c5-403">**Protected by**: **Defender for Office 365** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="b93c5-403">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="b93c5-404">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) で結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b93c5-405">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b93c5-406">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="b93c5-406">**Domain**</span></span>
  - <span data-ttu-id="b93c5-407">**受信者** (このフィルター可能なプロパティは詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="b93c5-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="b93c5-408">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-408">Top malware report</span></span>

<span data-ttu-id="b93c5-409">Top **malware report** shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b93c5-409">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b93c5-410">レポートを表示するには、セキュリティ/コンプライアンス センターを [&](https://protection.office.com)レポート **ダッシュボード** に移動し、[上位マルウェア] \> を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-410">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="b93c5-411">レポートに直接移動するには、開きます <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="b93c5-411">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポート ダッシュボードの上位マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="b93c5-413">円グラフでくさびの上にマウス ポインターを移動すると、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-413">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="b93c5-415">[詳細テーブルの **表示] をクリックすると**、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-415">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b93c5-416">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="b93c5-416">**Top malware**</span></span>
- <span data-ttu-id="b93c5-417">**Count**</span><span class="sxs-lookup"><span data-stu-id="b93c5-417">**Count**</span></span>

<span data-ttu-id="b93c5-418">レポート ビュー **または詳細** テーブル ビューで [フィルター] をクリックすると、開始日と終了日で日付範囲 **を\*\*\*\*指定できます**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-418">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="b93c5-419">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-419">URL threat protection report</span></span>

<span data-ttu-id="b93c5-420">URL **脅威保護レポートは、Microsoft** Defender で Office 365 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-420">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b93c5-421">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-421">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="b93c5-422">ユーザーから報告されたメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="b93c5-422">User-reported messages report</span></span>

<span data-ttu-id="b93c5-423">ユーザー **報告メッセージ** レポートには、迷惑メール報告アドインまたはフィッシング報告アドインを使用して、ユーザーが迷惑メール、フィッシング詐欺、または良 [](enable-the-report-message-add-in.md)いメールとして報告した電子メール メッセージに関する情報が表示 [されます。](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="b93c5-423">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="b93c5-424">配信理由 (組織に構成されているスパム ポリシーの例外やメール フロー ルールなど) など、メッセージごとに詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-424">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="b93c5-425">詳細を表示するには、ユーザー レポート リストでアイテムを選択し、[概要] タブと [詳細] タブ **に** 情報を **表示** します。</span><span class="sxs-lookup"><span data-stu-id="b93c5-425">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![[User-Reported メッセージ] レポートには、迷惑メール、迷惑メール、フィッシングの試行としてラベルが付いたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="b93c5-427">このレポートを表示するには、セキュリティ & [コンプライアンス センターで、](https://protection.office.com)次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b93c5-427">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="b93c5-428">脅威管理 **ダッシュボードのユーザー** \> **から** \> **報告されたメッセージに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-428">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="b93c5-429">[脅威の管理 **] ユーザーから** \> **報告** \> **されたメッセージを確認するに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b93c5-429">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ/コンプライアンス センターで、[脅威&レビュー ユーザーが \> 報告 \> したメッセージ] を選択します。](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="b93c5-431">ユーザーから報告されたメッセージ レポートが正しく機能するには、365 環境で監査ログを有効Office必要があります。 </span><span class="sxs-lookup"><span data-stu-id="b93c5-431">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="b93c5-432">これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-432">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="b93c5-433">詳細については [、「Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)監査ログ検索を有効またはオフにする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93c5-433">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b93c5-434">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b93c5-434">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b93c5-435">この記事で説明されているレポートを表示して使用するには、セキュリティ/コンプライアンス センターの次のいずれかの役割グループのメンバー&必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93c5-435">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b93c5-436">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="b93c5-436">**Organization Management**</span></span>
- <span data-ttu-id="b93c5-437">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-437">**Security Administrator**</span></span>
- <span data-ttu-id="b93c5-438">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="b93c5-438">**Security Reader**</span></span>
- <span data-ttu-id="b93c5-439">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="b93c5-439">**Global Reader**</span></span>

<span data-ttu-id="b93c5-440">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93c5-440">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b93c5-441">**注**: Microsoft 365 管理センターで対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="b93c5-441">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b93c5-442">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b93c5-442">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b93c5-443">レポートにデータが表示されない場合</span><span class="sxs-lookup"><span data-stu-id="b93c5-443">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b93c5-444">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b93c5-444">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b93c5-445">詳細については、「脅威からの保護 [」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="b93c5-445">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b93c5-446">関連項目</span><span class="sxs-lookup"><span data-stu-id="b93c5-446">Related topics</span></span>

[<span data-ttu-id="b93c5-447">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="b93c5-447">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="b93c5-448">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="b93c5-448">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b93c5-449">セキュリティ/コンプライアンス センターでメール フロー レポート&表示する</span><span class="sxs-lookup"><span data-stu-id="b93c5-449">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="b93c5-450">Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b93c5-450">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
