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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について説明します。 セキュリティ グループ コンプライアンス センターでは、電子メールの&レポートを利用できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b714d9dc4e3ca143d2cb2d7164f8c3c737d1928
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826507"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="90d82-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="90d82-104">View email security reports in the Security & Compliance Center</span></span>

<span data-ttu-id="90d82-105">セキュリティ & コンプライアンス センターでは、 [さまざまなレポートを使用して、Microsoft](https://protection.office.com) 365 のスパム対策、マルウェア対策、暗号化機能などの電子メールのセキュリティ機能が組織をどのように保護しているかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="90d82-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="90d82-106">必要なアクセス許可 [があは、](#what-permissions-are-needed-to-view-these-reports)セキュリティ コンプライアンス センターでこれらのレポートを表示するには、[レポート & ダッシュボード] に **移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="90d82-107">レポート ダッシュボードに直接移動するには、開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ センター センターのレポート ダッシュボード& レポート](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="90d82-109">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="90d82-110">このレポートは Exchange Online メールボックスが有効な Microsoft 365 組織で使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="90d82-111">スタンドアロン Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="90d82-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="90d82-112">侵 **害されたユーザー レポートには** 、過去 7 日間以内に **不** 審なか制限 **付き** のマークが付いたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="90d82-113">これらの状態のどちらかのアカウントは問題や、もしくは侵害を受けました。</span><span class="sxs-lookup"><span data-stu-id="90d82-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="90d82-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span><span class="sxs-lookup"><span data-stu-id="90d82-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="90d82-115">侵害されたユーザーの詳細については、「侵害 [されたメール アカウントへの対応」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポート ダッシュボードで侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="90d82-117">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="90d82-118">レポートを表示するには、コンプライアンス センター[でセキュリティ&開き、[](https://protection.office.com)**レポート** \> **ダッシュボード] に移動\*\*\*\*して、侵害されたユーザーを選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="90d82-119">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="90d82-120">グラフと詳細テーブルの両方にフィルターを適用するには、[ **フィルター] をクリックし** 、次の 1 つ以上の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d82-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="90d82-121">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="90d82-122">**不審な情報**: ユーザー アカウントから不審なメールが送信され、電子メールの送信が制限されるリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="90d82-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="90d82-123">**制限 :** ユーザー アカウントは、不審なパターンが原因でメールの送信が制限されています。</span><span class="sxs-lookup"><span data-stu-id="90d82-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![侵害されたユーザー レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="90d82-125">[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90d82-126">**作成日時**</span><span class="sxs-lookup"><span data-stu-id="90d82-126">**Creation time**</span></span>
- <span data-ttu-id="90d82-127">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="90d82-127">**User ID**</span></span>
- <span data-ttu-id="90d82-128">**操作**</span><span class="sxs-lookup"><span data-stu-id="90d82-128">**Action**</span></span>

<span data-ttu-id="90d82-129">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90d82-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="90d82-130">[暗号化] レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-130">Encryption report</span></span>

<span data-ttu-id="90d82-131">暗号化 **レポートは** EOP で使用可能です (Exchange Online のメールボックスでのサブスクリプション、または Exchange Online メールボックスのないスタンドアロン EOP)。</span><span class="sxs-lookup"><span data-stu-id="90d82-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="90d82-132">組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーをプロアクティブに適用または調整できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="90d82-133">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="90d82-133">For example:</span></span>

- <span data-ttu-id="90d82-134">ユーザーが暗号化する電子メール メッセージが多す多い場合は、暗号化ポリシーを追加して、特定の用例で暗号化を自動化することもできます。</span><span class="sxs-lookup"><span data-stu-id="90d82-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="90d82-135">詳細については [、「Microsoft 365 でメール メッセージを暗号化するメール フロー ルールの定義」を参照してください](../../compliance/define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="90d82-136">利用可能な暗号化テンプレートが数回あっても、これらのテンプレートを使用しない場合は、ユーザーに機能のトレーニングが必要かどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="90d82-137">集計ビューでは過去 90 日間のフィルター処理を行い、詳細ビューでは 10 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="90d82-138">レポートを表示するには、セキュリティ コンプライアンス センター [を開&、[レポート](https://protection.office.com)ダッシュボード] **に移動し** \> **、[** 暗号化レポート **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="90d82-139">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="90d82-140">暗号化の詳細については [、「Microsoft 365 での電子メールの暗号化」を参照してください](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="90d82-141">暗号化レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-141">Report view for the Encryption report</span></span>

<span data-ttu-id="90d82-142">グラフには次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="90d82-143">**データの表示方法: 暗号化方法\*\*\*\*: 暗号化方法: 暗号化方法**を次に示します。</span><span class="sxs-lookup"><span data-stu-id="90d82-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="90d82-144">**ユーザー別の暗号化**</span><span class="sxs-lookup"><span data-stu-id="90d82-144">**Encryption by user**</span></span>
  - <span data-ttu-id="90d82-145">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="90d82-145">**Encryption by policy**</span></span>

  <span data-ttu-id="90d82-146">[フィルター] を **クリック**した場合は、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="90d82-147">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90d82-148">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="90d82-148">Encryption method.</span></span>
  - <span data-ttu-id="90d82-149">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="90d82-149">Encryption template.</span></span>

- <span data-ttu-id="90d82-150">**データの表示方法: 暗号化の** 種類: **暗号化テンプレート: 次**の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="90d82-151">**転送不可**</span><span class="sxs-lookup"><span data-stu-id="90d82-151">**Do not forward**</span></span>
  - <span data-ttu-id="90d82-152">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="90d82-152">**Encrypt only**</span></span>
  - <span data-ttu-id="90d82-153">**以前の OME**</span><span class="sxs-lookup"><span data-stu-id="90d82-153">**OME previous**</span></span>
  - <span data-ttu-id="90d82-154">**Custom**</span><span class="sxs-lookup"><span data-stu-id="90d82-154">**Custom**</span></span>

  <span data-ttu-id="90d82-155">[フィルター] を **クリック**した場合は、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="90d82-156">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="90d82-157">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="90d82-157">Encryption method</span></span>
  - <span data-ttu-id="90d82-158">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="90d82-158">Encryption template</span></span>

- <span data-ttu-id="90d82-159">**データの表示元: 上位 5 の受信者ドメイン**: 上位 5 つの受信者ドメインのメッセージ数が、このビューには送信済みメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="90d82-160">[フィルター] を**クリック**した場合は、開始日**と終了日\*\*\*\*を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="90d82-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="90d82-161">暗号化レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="90d82-162">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="90d82-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="90d82-163">**方法の詳細: 暗号化または暗号化** テンプレート **での切り分け:** 次の情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="90d82-164">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-164">**Date**</span></span>
  - <span data-ttu-id="90d82-165">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90d82-165">**Sender address**</span></span>
  - <span data-ttu-id="90d82-166">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="90d82-166">**Encryption template**</span></span>
  - <span data-ttu-id="90d82-167">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="90d82-167">**Encryption method**</span></span>
  - <span data-ttu-id="90d82-168">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90d82-168">**Recipient address**</span></span>
  - <span data-ttu-id="90d82-169">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90d82-169">**Subject**</span></span>

- <span data-ttu-id="90d82-170">**データの表示元: 上位 5 つの受信者のドメイン**:</span><span class="sxs-lookup"><span data-stu-id="90d82-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="90d82-171">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-171">**Date**</span></span>
  - <span data-ttu-id="90d82-172">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90d82-172">**Recipient domain**</span></span>
  - <span data-ttu-id="90d82-173">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="90d82-173">**Message count**</span></span>
  
<span data-ttu-id="90d82-174">詳細テーブル ビュー **で [** フィルター] をクリックした場合、結果は次のフィルターを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90d82-175">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-176">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="90d82-176">Encryption method</span></span>
- <span data-ttu-id="90d82-177">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="90d82-177">Encryption template</span></span>

<span data-ttu-id="90d82-178">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90d82-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="90d82-179">メール フロー状態レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-179">Mailflow status report</span></span>

<span data-ttu-id="90d82-180">メール **フロー状態レポートには、マルウェア** 、スパム、フィッシング、およびエッジでブロックされたメッセージに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="90d82-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="90d82-181">詳細については、「メール フロー ステータス [レポート」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="90d82-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="90d82-182">メール レポートでのマルウェア検出</span><span class="sxs-lookup"><span data-stu-id="90d82-182">Malware detections in email report</span></span>

<span data-ttu-id="90d82-183">メール **レポートでのマルウェア検出は、** 受信および送信電子メール メッセージ内のマルウェア検出に関する情報を示します (マルウェアは Exchange Online Protection または EOP で検出されます)。</span><span class="sxs-lookup"><span data-stu-id="90d82-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="90d82-184">EOP のマルウェア保護の詳細については、EOP の [マルウェア対策保護を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="90d82-185">集計ビュー フィルターでは 90 日間が可能で、詳細テーブル フィルターでは 10 日間のみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="90d82-186">レポートを表示するには、セキュリティ コンプライアンス [センター&開き、[レポート](https://protection.office.com)ダッシュボード **]** に \> **移動して** メールでの **マルウェア検出を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="90d82-187">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポート ダッシュボードのメール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

<span data-ttu-id="90d82-189">次の項目を選択して、グラフと詳細テーブルの **両方を** フィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="90d82-190">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-191">**受信**</span><span class="sxs-lookup"><span data-stu-id="90d82-191">**Inbound**</span></span>
- <span data-ttu-id="90d82-192">**送信**</span><span class="sxs-lookup"><span data-stu-id="90d82-192">**Outbound**</span></span>

![メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="90d82-194">[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90d82-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-195">**Date**</span></span>
- <span data-ttu-id="90d82-196">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90d82-196">**Sender address**</span></span>
- <span data-ttu-id="90d82-197">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90d82-197">**Recipient address**</span></span>
- <span data-ttu-id="90d82-198">**メッセージ ID**: メッセージ ヘッダー内 **の Message-ID** ヘッダー フィールドに使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d82-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="90d82-199">角かっ `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` こなどに注:</span><span class="sxs-lookup"><span data-stu-id="90d82-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="90d82-200">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90d82-200">**Subject**</span></span>
- <span data-ttu-id="90d82-201">**Filename**</span><span class="sxs-lookup"><span data-stu-id="90d82-201">**Filename**</span></span>
- <span data-ttu-id="90d82-202">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="90d82-202">**Malware name**</span></span>

<span data-ttu-id="90d82-203">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90d82-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="90d82-204">送受信メール レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-204">Sent and received email report</span></span>

<span data-ttu-id="90d82-205">送信 **および受信メール レポート** には、マルウェア、スパム、メール フロー ルール (別名トランスポート ルール)、メールがサービスに移行された後の高度なマルウェア検出に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90d82-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="90d82-206">詳細については、「送信および受信 [メール」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="90d82-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="90d82-207">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-207">Spam detections report</span></span>

<span data-ttu-id="90d82-208">スパム **検出レポートには、EOP** によってブロックされたスパム メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="90d82-209">メッセージは受信者ごとにカウントされます。</span><span class="sxs-lookup"><span data-stu-id="90d82-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="90d82-210">たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、そのメッセージは 1 メッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="90d82-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="90d82-211">集計ビューでは 90 日間のフィルター処理を実行できますが、詳細テーブルでは 10 日間のフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="90d82-212">レポートを表示するには、コンプライアンス センターで [セキュリティ &に移動](https://protection.office.com)し、[ **スパム** \> **検出** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="90d82-213">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="90d82-215">スパム対策保護の詳細については、「EOP の [スパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="90d82-216">スパム検出レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="90d82-217">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="90d82-218">**操作の別の方法: 操作**の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90d82-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="90d82-219">**フィルター処理スパム コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="90d82-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="90d82-220">**スパム IP ブロック**</span><span class="sxs-lookup"><span data-stu-id="90d82-220">**Spam IP block**</span></span>
  - <span data-ttu-id="90d82-221">**スパム エンベロープのブロック**</span><span class="sxs-lookup"><span data-stu-id="90d82-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="90d82-222">**スパム DBEB フィルター**: ディレクトリ ベースのエッジ ブロック (DBEB)</span><span class="sxs-lookup"><span data-stu-id="90d82-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="90d82-223">グラフで 1 日 (データ ポイント) にポインターを移動すると、その日がブロックされた項目の数と、それらのアイテムの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![スパム検出レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="90d82-225">**次の手順で区切**りを下します。次の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="90d82-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="90d82-226">**受信**</span><span class="sxs-lookup"><span data-stu-id="90d82-226">**Inbound**</span></span>
  - <span data-ttu-id="90d82-227">**送信**</span><span class="sxs-lookup"><span data-stu-id="90d82-227">**Outbound**</span></span>

  ![スパム検出レポートの方向ビュー](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="90d82-229">レポート ビューで **[フィルター** ] をクリックした場合は、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90d82-230">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-231">Direction の値</span><span class="sxs-lookup"><span data-stu-id="90d82-231">Direction values</span></span>
- <span data-ttu-id="90d82-232">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="90d82-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="90d82-233">スパム検出レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="90d82-234">レポート ビューで **[詳細の表示]** テーブルをクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="90d82-235">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-235">**Date**</span></span>
- <span data-ttu-id="90d82-236">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="90d82-236">**Sender address**</span></span>
- <span data-ttu-id="90d82-237">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="90d82-237">**Recipient address**</span></span>
- <span data-ttu-id="90d82-238">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="90d82-238">**Event type**</span></span>
- <span data-ttu-id="90d82-239">**操作**</span><span class="sxs-lookup"><span data-stu-id="90d82-239">**Action**</span></span>
- <span data-ttu-id="90d82-240">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90d82-240">**Subject**</span></span>

<span data-ttu-id="90d82-241">詳細テーブルの **[フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="90d82-242">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-243">Direction の値</span><span class="sxs-lookup"><span data-stu-id="90d82-243">Direction values</span></span>
- <span data-ttu-id="90d82-244">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="90d82-244">Event type values</span></span>

<span data-ttu-id="90d82-245">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90d82-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="90d82-246">なりすみ検出レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-246">Spoof detections report</span></span>

<span data-ttu-id="90d82-247">**スプーフィング検出レポート**には、検出されたスプーフィング メール メッセージの数と、どのメッセージが「良好」な (正当な業務上の理由で実行された) と見なされたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="90d82-248">スプーフィングの詳細については [、EOP のスプーフィング対策保護を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="90d82-249">レポートの集計ビューには 90 日間のフィルター処理を行えますが、詳細ビューには 10 日間のフィルターしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="90d82-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="90d82-250">レポートを表示するには、セキュリティ/コンプライアンス [センター&開き、[](https://protection.office.com)レポート **ダッシュボード]** \> **に移動して** [ **スプーフィングの検出] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="90d82-251">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="90d82-253">グラフ内の 1 日 (データ ポイント) にポインターを移動すると、通過したスプーフィング メール メッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="90d82-254">グラフと詳細テーブルの両方にフィルターを適用するには、[ **フィルター] をクリックし** 、次の 1 つ以上の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="90d82-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="90d82-255">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="90d82-256">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="90d82-256">**Good mail**</span></span>

- <span data-ttu-id="90d82-257">**スパムとしてキャッチ**</span><span class="sxs-lookup"><span data-stu-id="90d82-257">**Caught as spam**</span></span>

![なりすみ検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="90d82-259">[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90d82-260">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-260">**Date**</span></span>
- <span data-ttu-id="90d82-261">**偽の送信者**</span><span class="sxs-lookup"><span data-stu-id="90d82-261">**Spoofed sender**</span></span>
- <span data-ttu-id="90d82-262">**真の送信者**</span><span class="sxs-lookup"><span data-stu-id="90d82-262">**True sender**</span></span>
- <span data-ttu-id="90d82-263">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="90d82-263">**Sender IP**</span></span>
- <span data-ttu-id="90d82-264">**操作**</span><span class="sxs-lookup"><span data-stu-id="90d82-264">**Action**</span></span>
- <span data-ttu-id="90d82-265">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="90d82-265">**Message count**</span></span>

<span data-ttu-id="90d82-266">レポート ビューに戻るには、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="90d82-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="90d82-267">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-267">Threat protection status report</span></span>

<span data-ttu-id="90d82-268">脅 **威保護の状態** レポートは、EOP と Office 365 ATP の両方で利用できます。ただし、レポートにはデータが異なります。</span><span class="sxs-lookup"><span data-stu-id="90d82-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="90d82-269">たとえば、EOP のお客様は電子メールで検出されたマルウェアに関する情報を [表示できますが、SharePoint Online、OneDrive、または Microsoft Teams](atp-for-spo-odb-and-teams.md)で検出された悪意のあるファイルについての情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="90d82-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="90d82-270">レポートは、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL) など、悪意のあるコンテンツを含む一意のメール メッセージの集計された数を提供します。たとえば、マルウェア対策エンジン、 [ゼロア自動消去 (ZAP) によってブロック](zero-hour-auto-purge.md)された [ATP 機能、ATP](atp-safe-links.md)の安全な添付ファイル [、ATP](atp-safe-attachments.md)の安全な添付ファイル [、ATP](set-up-anti-phishing-policies.md)のフィッシング対策などの ATP 機能です。</span><span class="sxs-lookup"><span data-stu-id="90d82-270">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="90d82-271">この情報を使用して傾向を特定したり、組織のポリシーに調整が必要かどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="90d82-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="90d82-272">レポートを表示するには、セキュリティ/ [コンプライアンス センター&、[レポート ダッシュボード]](https://protection.office.com)に移動 **して** \> **脅** 威保護の **状態を選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-272">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="90d82-273">レポートに直接移動するには、次の URL のいずれかを開きます。</span><span class="sxs-lookup"><span data-stu-id="90d82-273">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="90d82-274">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .</span><span class="sxs-lookup"><span data-stu-id="90d82-274">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="90d82-275">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="90d82-275">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="90d82-277">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-277">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="90d82-278">[フィルター] を **クリック**した場合は、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限されます)。</span><span class="sxs-lookup"><span data-stu-id="90d82-278">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="90d82-279">詳細テーブル ビューでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="90d82-279">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="90d82-280">脅威保護状態レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-280">Report view for the Threat protection status report</span></span>

<span data-ttu-id="90d82-281">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-281">The following views are available:</span></span>

- <span data-ttu-id="90d82-282">**データの表示方法: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-282">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="90d82-283">**マルウェア マルウェア**</span><span class="sxs-lookup"><span data-stu-id="90d82-283">**Email malware**</span></span>
  - <span data-ttu-id="90d82-284">**メールのフィッシング**</span><span class="sxs-lookup"><span data-stu-id="90d82-284">**Email phish**</span></span>
  - <span data-ttu-id="90d82-285">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="90d82-285">**Content malware**</span></span>

  ![脅威保護状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="90d82-287">**データの表示方法: コンテンツ \> マルウェア**<sup>1:</sup>365 ATP 組織Office次の情報を示します。</span><span class="sxs-lookup"><span data-stu-id="90d82-287">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="90d82-288">**マルウェア対策エンジン**</span><span class="sxs-lookup"><span data-stu-id="90d82-288">**Anti-malware engine**</span></span>
  - <span data-ttu-id="90d82-289">**ファイルの追加**</span><span class="sxs-lookup"><span data-stu-id="90d82-289">**File detonation**</span></span>

  ![脅威保護状態レポートのコンテンツ マルウェアビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="90d82-291">**次の手順で詳細に説明します。検出テクノロジ\*\*\*\*ーおよびデータ表示の方法:電子 \> メール フィッシング**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-291">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="90d82-292">**ATP によって生成される URL の評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-292">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-293">**高度なフィッシング フィルター**</span><span class="sxs-lookup"><span data-stu-id="90d82-293">**Advanced phish filter**</span></span>
  - <span data-ttu-id="90d82-294">**スプーフィング対策: DMARC エラー**</span><span class="sxs-lookup"><span data-stu-id="90d82-294">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="90d82-295">**スプーフィング対策: Intra-org**</span><span class="sxs-lookup"><span data-stu-id="90d82-295">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="90d82-296">**スプーフィング対策: 外部ドメイン**</span><span class="sxs-lookup"><span data-stu-id="90d82-296">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="90d82-297">**ブランド偽装**</span><span class="sxs-lookup"><span data-stu-id="90d82-297">**Brand impersonation**</span></span>
  - <span data-ttu-id="90d82-298">**ドメイン偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-298">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-299">**EOP URL の評価**</span><span class="sxs-lookup"><span data-stu-id="90d82-299">**EOP URL reputation**</span></span>
  - <span data-ttu-id="90d82-300">**一般的なフィッシング フィルター**</span><span class="sxs-lookup"><span data-stu-id="90d82-300">**General phish filter**</span></span>
  - <span data-ttu-id="90d82-301">**Others**</span><span class="sxs-lookup"><span data-stu-id="90d82-301">**Others**</span></span>
  - <span data-ttu-id="90d82-302">**フィッシング ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-302">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="90d82-303">**URL の特定**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-303">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-304">**ユーザー偽装**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-304">**User impersonation**<sup>1</sup></span></span>

  ![脅威保護状態レポートのフィッシング電子メールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="90d82-306">**次の手順で詳細に説明します。検出テクノロジ\*\*\*\*ーおよびデータの表示方法:電子 \> メール マルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-306">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90d82-307">**ATP によって生成されたファイルの評価**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-307">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-308">**マルウェア対策エンジン**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-308">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-309">**マルウェア対策ポリシー ファイルの種類のブロック**</span><span class="sxs-lookup"><span data-stu-id="90d82-309">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="90d82-310">**ファイルの追加**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-310">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-311">**悪意のあるファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="90d82-311">**Malicious file reputation**</span></span>
  - <span data-ttu-id="90d82-312">**マルウェア ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-312">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="90d82-313">**Others**</span><span class="sxs-lookup"><span data-stu-id="90d82-313">**Others**</span></span>

  ![脅威保護状態レポートでのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="90d82-315">**ポリシーの種類とデータ表示の\*\*\*\*方法:電子メールの \> フィッ**シングまたは**データの表示方法:電子メール \> のマルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-315">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90d82-316">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="90d82-316">**Anti-malware**</span></span>
  - <span data-ttu-id="90d82-317">**安全な添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90d82-317">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="90d82-318">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="90d82-318">**Anti-phish**</span></span>
  - <span data-ttu-id="90d82-319">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="90d82-319">**Anti-spam**</span></span>
  - <span data-ttu-id="90d82-320">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="90d82-320">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="90d82-321">**Others**</span><span class="sxs-lookup"><span data-stu-id="90d82-321">**Others**</span></span>

  ![脅威保護状態レポートでのフィッシング メールのポリシーの種類のビュー](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="90d82-323">**以下の方法でインスペレーターを分け** 、データ **の表示方法:電子メール \> のフィッシング** または **データの表示方法:電子メール \> のマルウェア**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-323">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="90d82-324">**配信失敗**</span><span class="sxs-lookup"><span data-stu-id="90d82-324">**Delivery failed**</span></span>
  - <span data-ttu-id="90d82-325">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="90d82-325">**Dropped**</span></span>
  - <span data-ttu-id="90d82-326">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="90d82-326">**Forwarded**</span></span>
  - <span data-ttu-id="90d82-327">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="90d82-327">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="90d82-328">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="90d82-328">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="90d82-329">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="90d82-329">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="90d82-330">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="90d82-330">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="90d82-331">**社内サーバー: 配信済み**</span><span class="sxs-lookup"><span data-stu-id="90d82-331">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="90d82-332">**検疫**</span><span class="sxs-lookup"><span data-stu-id="90d82-332">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシング電子メールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="90d82-334"><sup>1</sup> Office 365 ATP のみ</span><span class="sxs-lookup"><span data-stu-id="90d82-334"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="90d82-335"><sup>2</sup> 時間の自動消去 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ動作します)。</span><span class="sxs-lookup"><span data-stu-id="90d82-335"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="90d82-336">[フィルター] を **クリック**すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-336">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="90d82-337">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-337">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-338">検出値</span><span class="sxs-lookup"><span data-stu-id="90d82-338">Detection value</span></span>
- <span data-ttu-id="90d82-339">Office**保護\*\*\*\*ATP\*\*\*\*EOP**</span><span class="sxs-lookup"><span data-stu-id="90d82-339">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="90d82-340">このフィルター処理可能なプロパティは、コンテンツ マルウェアという**表示データでは使用 \> できません。**</span><span class="sxs-lookup"><span data-stu-id="90d82-340">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="90d82-341">脅威保護状態レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="90d82-341">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="90d82-342">[詳細の **表示] テーブルを**クリックした場合に表示される情報は、表示しているグラフによって異なるためです。</span><span class="sxs-lookup"><span data-stu-id="90d82-342">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="90d82-343">**データの表示方法: コンテンツ \> Malware**(マルウェア):</span><span class="sxs-lookup"><span data-stu-id="90d82-343">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="90d82-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-344">**Date**</span></span>
  - <span data-ttu-id="90d82-345">**Location**</span><span class="sxs-lookup"><span data-stu-id="90d82-345">**Location**</span></span>
  - <span data-ttu-id="90d82-346">**ディレクティブ**</span><span class="sxs-lookup"><span data-stu-id="90d82-346">**Directed by**</span></span>
  - <span data-ttu-id="90d82-347">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="90d82-347">**Malware name**</span></span>

- <span data-ttu-id="90d82-348">**[概要] : [概要:** 詳細の **表示] ボタンが** ありません。</span><span class="sxs-lookup"><span data-stu-id="90d82-348">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="90d82-349">その他のグラフ:</span><span class="sxs-lookup"><span data-stu-id="90d82-349">All other charts:</span></span>

  - <span data-ttu-id="90d82-350">**Date**</span><span class="sxs-lookup"><span data-stu-id="90d82-350">**Date**</span></span>
  - <span data-ttu-id="90d82-351">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="90d82-351">**Subject**</span></span>
  - <span data-ttu-id="90d82-352">**送信者**</span><span class="sxs-lookup"><span data-stu-id="90d82-352">**Sender**</span></span>
  - <span data-ttu-id="90d82-353">**受信者**</span><span class="sxs-lookup"><span data-stu-id="90d82-353">**Recipients**</span></span>
  - <span data-ttu-id="90d82-354">**検出元のデータ**</span><span class="sxs-lookup"><span data-stu-id="90d82-354">**Detected by**</span></span>
  - <span data-ttu-id="90d82-355">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="90d82-355">**Delivery status**</span></span>
  - <span data-ttu-id="90d82-356">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="90d82-356">**Source of compromise**</span></span>

<span data-ttu-id="90d82-357">[フィルター] を **クリック**すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-357">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="90d82-358">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="90d82-358">**Start date** and **End date**</span></span>
- <span data-ttu-id="90d82-359">検出値</span><span class="sxs-lookup"><span data-stu-id="90d82-359">Detection value</span></span>
- <span data-ttu-id="90d82-360">Office**保護\*\*\*\*ATP\*\*\*\*EOP**</span><span class="sxs-lookup"><span data-stu-id="90d82-360">**Protected by** (Office 365 ATP only): **ATP** or **EOP**.</span></span> <span data-ttu-id="90d82-361">このフィルター処理可能なプロパティは、コンテンツ マルウェアという**表示データでは使用 \> できません。**</span><span class="sxs-lookup"><span data-stu-id="90d82-361">Note that this filterable property isn't available in **View data by: Content \> Malware**.</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="90d82-362">最上位マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-362">Top malware report</span></span>

<span data-ttu-id="90d82-363">上 **位マルウェア レポート** では、EOP でマルウェア対策保護によって検出されたさまざまな [種類のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-363">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="90d82-364">レポートを表示するには、セキュリティ センターのコンプライアンス [センター&、[レポート](https://protection.office.com)ダッシュボード] に移動 **して**[上 \> **位** マルウェア] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-364">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="90d82-365">レポートに直接進みるには、開きます <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="90d82-365">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポート ダッシュボードの上部のマルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="90d82-367">円グラフのウェイバーにポイントすると、マルウェアの種類と、そのマルウェアが含めたときに検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-367">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![最上位マルウェア レポート ビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="90d82-369">[詳細の表示 **] テーブルをクリック**すると、次の詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-369">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="90d82-370">**[最も一マルウェア]**</span><span class="sxs-lookup"><span data-stu-id="90d82-370">**Top malware**</span></span>
- <span data-ttu-id="90d82-371">**Count**</span><span class="sxs-lookup"><span data-stu-id="90d82-371">**Count**</span></span>

<span data-ttu-id="90d82-372">レポート ビューまたは**詳細**テーブルのビューで [フィルター] をクリックした場合、開始日と終了日で**日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="90d82-372">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="90d82-373">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-373">URL threat protection report</span></span>

<span data-ttu-id="90d82-374">**URL 脅威保護レポートは**、Office 365 Advanced Threat Protection (ATP) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-374">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="90d82-375">詳細については、URL の脅威 [保護レポートを参照してください](view-reports-for-atp.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="90d82-375">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="90d82-376">ユーザーから報告されたメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="90d82-376">User-reported messages report</span></span>

<span data-ttu-id="90d82-377">ユーザー **から報告されたメッセージ レポートは** 、ユーザーが迷惑メール、フィッシングの試行、または適切なメールとして報告した電子メール メッセージに関 [する情報を、メッセージ報告アドインを使用して表示されます](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)。</span><span class="sxs-lookup"><span data-stu-id="90d82-377">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="90d82-378">組織に構成されたスパム ポリシー例外またはメール フロー ルールなど、配信理由などの各メッセージの詳細を利用できます。</span><span class="sxs-lookup"><span data-stu-id="90d82-378">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="90d82-379">詳細を表示するには、ユーザー レポートのリストでアイテムを選択し、[概要と詳細] **タブの** 情報 **を** 表示します。</span><span class="sxs-lookup"><span data-stu-id="90d82-379">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![「ユーザー報告メッセージ」レポートには、迷惑メール、迷惑メール、フィッシングの試行などのラベルが付けされたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="90d82-381">このレポートを表示するには、セキュリティ [/コンプライアンス センターで&](https://protection.office.com)のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="90d82-381">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="90d82-382">脅威**管理ダッシュボードの** \> **Dashboard** \> **ユーザーが報告したメッセージに移動します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-382">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="90d82-383">脅威管理 **に移動** \> **して** \> **、ユーザーが報告したメッセージを確認します**。</span><span class="sxs-lookup"><span data-stu-id="90d82-383">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![セキュリティ/コンプライアンス センター&威管理レビュー ユーザー \> の \> メッセージを選択する](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="90d82-385">ユーザーから報告されたメッセージ レポートが正しく動作するには、Office 365 環境 **で** 監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d82-385">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="90d82-386">これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="90d82-386">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="90d82-387">詳細については [、「Microsoft 365 監査ログの検索を有効または無効にする」をご覧ください](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="90d82-387">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="90d82-388">これらのレポートを表示するにはどのようなアクセス許可が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="90d82-388">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="90d82-389">レポートを表示して使用するには、セキュリティ保護センターおよび Exchange Online で指定された &役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d82-389">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="90d82-390">コンプライアンス センターで&役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d82-390">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="90d82-391">-組織の管理 - セキュリティ管理者 [(Azure Active Directory](https://aad.portal.azure.com) 管理センター -Security Reader でも実行できます)</span><span class="sxs-lookup"><span data-stu-id="90d82-391">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="90d82-392">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90d82-392">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="90d82-393">Exchange Online で、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="90d82-393">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="90d82-394">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span><span class="sxs-lookup"><span data-stu-id="90d82-394">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="90d82-395">詳細については、「Exchange [Online のアクセス許可」と「Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) [の役割グループの管理」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)。</span><span class="sxs-lookup"><span data-stu-id="90d82-395">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="90d82-396">レポートにデータが表示されない場合はどうでしょうか。</span><span class="sxs-lookup"><span data-stu-id="90d82-396">What if the reports aren't showing data?</span></span>

<span data-ttu-id="90d82-397">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="90d82-397">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="90d82-398">詳細については、「脅威からの [保護」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="90d82-398">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="90d82-399">関連トピック</span><span class="sxs-lookup"><span data-stu-id="90d82-399">Related topics</span></span>

[<span data-ttu-id="90d82-400">EOP のスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="90d82-400">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="90d82-401">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="90d82-401">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="90d82-402">セキュリティ グループおよびコンプライアンス センターでメール フロー レポート&表示する</span><span class="sxs-lookup"><span data-stu-id="90d82-402">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="90d82-403">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="90d82-403">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
