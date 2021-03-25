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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について学習します。 電子メール セキュリティ レポートは、コンプライアンス センターのセキュリティ &使用できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206240"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="cb79f-104">セキュリティ/コンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="cb79f-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cb79f-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cb79f-105">**Applies to**</span></span>
- [<span data-ttu-id="cb79f-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cb79f-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cb79f-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="cb79f-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cb79f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb79f-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cb79f-109">セキュリティ [& コンプライアンス](https://protection.office.com) センターでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="cb79f-110">必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-these-reports)場合は、[レポート ダッシュボード] に移動して、セキュリティ & コンプライアンス センターでこれらのレポート **を表示** \> **できます**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cb79f-111">レポート ダッシュボードに直接移動するには、を開きます <https://protection.office.com/insightdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ 管理コンプライアンス センター&ダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="cb79f-113">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="cb79f-114">このレポートは、Exchange Online メールボックスを持つ Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="cb79f-115">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb79f-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="cb79f-116">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="cb79f-117">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="cb79f-118">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="cb79f-119">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポート ダッシュボードの侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="cb79f-121">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="cb79f-122">レポートを表示するには、コンプライアンス センターで [セキュリティ](https://protection.office.com)&を開き、[レポート **ダッシュボード]** に移動し、[侵害されたユーザー] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="cb79f-123">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="cb79f-124">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cb79f-125">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="cb79f-126">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="cb79f-127">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="cb79f-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="cb79f-129">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cb79f-130">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="cb79f-130">**Creation time**</span></span>
- <span data-ttu-id="cb79f-131">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="cb79f-131">**User ID**</span></span>
- <span data-ttu-id="cb79f-132">**操作**</span><span class="sxs-lookup"><span data-stu-id="cb79f-132">**Action**</span></span>

<span data-ttu-id="cb79f-133">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="cb79f-134">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-134">Encryption report</span></span>

<span data-ttu-id="cb79f-135">暗号化 **レポートは** 、EOP (Exchange Online のメールボックスがあるサブスクリプション、または Exchange Online メールボックスのないスタンドアロン EOP) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="cb79f-136">組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーを積極的に適用または調整できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="cb79f-137">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-137">For example:</span></span>

- <span data-ttu-id="cb79f-138">ユーザーによって暗号化された電子メール メッセージの数が多い場合は、暗号化ポリシーを追加して、特定の使用例の暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="cb79f-139">詳細については [、「Microsoft 365 でメール メッセージを暗号化する](../../compliance/define-mail-flow-rules-to-encrypt-email.md)メール フロー ルールを定義する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb79f-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="cb79f-140">使用可能な暗号化テンプレートが多数あるが、使用しているユーザーがいない場合は、ユーザーが機能トレーニングを必要とするかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="cb79f-141">集計ビューでは過去 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="cb79f-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="cb79f-142">レポートを表示するには、コンプライアンス センターのセキュリティ &[開き、[](https://protection.office.com)レポート **ダッシュボード]** に移動し、[暗号化レポート] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="cb79f-143">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="cb79f-144">暗号化の詳細については [、「Microsoft 365 でのメール暗号化」を参照してください](../../compliance/email-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="cb79f-145">暗号化レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-145">Report view for the Encryption report</span></span>

<span data-ttu-id="cb79f-146">グラフで次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="cb79f-147">**データの表示方法: [メッセージの暗号化レポート** ] と [詳細: 暗号化 **方法]**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cb79f-148">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="cb79f-148">**Encryption by user**</span></span>
  - <span data-ttu-id="cb79f-149">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="cb79f-149">**Encryption by policy**</span></span>

  <span data-ttu-id="cb79f-150">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cb79f-151">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-152">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="cb79f-152">Encryption method.</span></span>
  - <span data-ttu-id="cb79f-153">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="cb79f-153">Encryption template.</span></span>

- <span data-ttu-id="cb79f-154">**データの表示方法: [メッセージの暗号化レポート** ] と [詳細: 暗号化テンプレート **]**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="cb79f-155">**転送しない**</span><span class="sxs-lookup"><span data-stu-id="cb79f-155">**Do not forward**</span></span>
  - <span data-ttu-id="cb79f-156">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="cb79f-156">**Encrypt only**</span></span>
  - <span data-ttu-id="cb79f-157">**OME 前**</span><span class="sxs-lookup"><span data-stu-id="cb79f-157">**OME previous**</span></span>
  - <span data-ttu-id="cb79f-158">**Custom**</span><span class="sxs-lookup"><span data-stu-id="cb79f-158">**Custom**</span></span>

  <span data-ttu-id="cb79f-159">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="cb79f-160">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-161">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="cb79f-161">Encryption method</span></span>
  - <span data-ttu-id="cb79f-162">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="cb79f-162">Encryption template</span></span>

- <span data-ttu-id="cb79f-163">**データの表示方法: 上位 5** つの受信者ドメイン : このビューには、上位 5 つの受信者ドメインの送信メッセージ数を含む円グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="cb79f-164">[フィルター] **をクリックすると**、[開始日] と **[終了日]** **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="cb79f-165">暗号化レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="cb79f-166">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb79f-167">**[詳細]: [暗号化方法] または** [ **詳細: 暗号化テンプレート]**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="cb79f-168">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-168">**Date**</span></span>
  - <span data-ttu-id="cb79f-169">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="cb79f-169">**Sender address**</span></span>
  - <span data-ttu-id="cb79f-170">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="cb79f-170">**Encryption template**</span></span>
  - <span data-ttu-id="cb79f-171">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="cb79f-171">**Encryption method**</span></span>
  - <span data-ttu-id="cb79f-172">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="cb79f-172">**Recipient address**</span></span>
  - <span data-ttu-id="cb79f-173">**件名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-173">**Subject**</span></span>

- <span data-ttu-id="cb79f-174">**データの表示方法: 上位 5 つの受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="cb79f-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="cb79f-175">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-175">**Date**</span></span>
  - <span data-ttu-id="cb79f-176">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-176">**Recipient domain**</span></span>
  - <span data-ttu-id="cb79f-177">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="cb79f-177">**Message count**</span></span>

<span data-ttu-id="cb79f-178">詳細テーブル ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb79f-179">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb79f-180">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="cb79f-180">Encryption method</span></span>
- <span data-ttu-id="cb79f-181">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="cb79f-181">Encryption template</span></span>

<span data-ttu-id="cb79f-182">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="cb79f-183">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-183">Mailflow status report</span></span>

<span data-ttu-id="cb79f-184">Mailflow **状態レポートには、** マルウェア、スパム、フィッシング、およびエッジブロックされたメッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="cb79f-185">詳細については [、「Mailflow status report」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="cb79f-186">電子メール レポートのマルウェア検出</span><span class="sxs-lookup"><span data-stu-id="cb79f-186">Malware detections in email report</span></span>

<span data-ttu-id="cb79f-187">電子 **メール レポートのマルウェア検出** には、受信および送信電子メール メッセージ (Exchange Online Protection または EOP によって検出されたマルウェア) のマルウェア検出に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="cb79f-188">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="cb79f-189">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="cb79f-190">レポートを表示するには、セキュリティ & コンプライアンス センターを開き [、[](https://protection.office.com)レポートダッシュボード] に移動し、[電子メールのマルウェア検出] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="cb79f-191">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![レポート ダッシュボードの電子メール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

<span data-ttu-id="cb79f-193">[フィルター] をクリックして次の項目を選択すると、グラフと詳細テーブル **の両方** をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="cb79f-194">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb79f-195">**受信**</span><span class="sxs-lookup"><span data-stu-id="cb79f-195">**Inbound**</span></span>
- <span data-ttu-id="cb79f-196">**送信**</span><span class="sxs-lookup"><span data-stu-id="cb79f-196">**Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="cb79f-198">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cb79f-199">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-199">**Date**</span></span>
- <span data-ttu-id="cb79f-200">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="cb79f-200">**Sender address**</span></span>
- <span data-ttu-id="cb79f-201">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="cb79f-201">**Recipient address**</span></span>
- <span data-ttu-id="cb79f-202">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="cb79f-203">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="cb79f-204">**件名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-204">**Subject**</span></span>
- <span data-ttu-id="cb79f-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="cb79f-205">**Filename**</span></span>
- <span data-ttu-id="cb79f-206">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-206">**Malware name**</span></span>

<span data-ttu-id="cb79f-207">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="cb79f-208">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-208">Mail latency report</span></span>

<span data-ttu-id="cb79f-209">[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間に関する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="cb79f-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="cb79f-210">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="cb79f-211">送信および受信した電子メール レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-211">Sent and received email report</span></span>

<span data-ttu-id="cb79f-212">送信 **および受信電子** メール レポートには、マルウェア、スパム、メール フロー ルール (トランスポート ルールとも呼ばれる)、およびメールがサービスに入った後の高度なマルウェア検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb79f-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="cb79f-213">詳細については、「送信および受信 [メール レポート」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="cb79f-214">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-214">Spam detections report</span></span>

<span data-ttu-id="cb79f-215">[ **スパム検出] レポートには** 、EOP によってブロックされたスパム メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="cb79f-216">メッセージは受信者ごとにではなく、個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="cb79f-217">たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、そのメッセージは 1 つのメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="cb79f-218">集計ビューでは 90 日間のフィルター処理が可能で、詳細テーブルでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="cb79f-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="cb79f-219">レポートを表示するには、コンプライアンス センターでセキュリティ &[を](https://protection.office.com)開き、[レポート **ダッシュボード]** に移動し、[スパム検出] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="cb79f-220">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="cb79f-222">スパム対策保護の詳細については [、「EOP のスパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="cb79f-223">スパム検出レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="cb79f-224">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="cb79f-225">**ブレークダウン: アクション**: 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="cb79f-226">**フィルター処理されたスパム コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="cb79f-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="cb79f-227">**スパム IP ブロック**</span><span class="sxs-lookup"><span data-stu-id="cb79f-227">**Spam IP block**</span></span>
  - <span data-ttu-id="cb79f-228">**スパム エンベロープ ブロック**</span><span class="sxs-lookup"><span data-stu-id="cb79f-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="cb79f-229">**スパム DBEB フィルター**: ディレクトリ ベースのエッジ ブロック (DBEB)</span><span class="sxs-lookup"><span data-stu-id="cb79f-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="cb79f-230">グラフで 1 日 (データ ポイント) をポイントすると、その日にブロックされたアイテムの数と、それらのアイテムの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![[スパム検出] レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="cb79f-232">**[ブレークダウン]: [方向**] : 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="cb79f-233">**受信**</span><span class="sxs-lookup"><span data-stu-id="cb79f-233">**Inbound**</span></span>
  - <span data-ttu-id="cb79f-234">**送信**</span><span class="sxs-lookup"><span data-stu-id="cb79f-234">**Outbound**</span></span>

  ![[スパム検出] レポートの方向表示](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="cb79f-236">レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb79f-237">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb79f-238">方向の値</span><span class="sxs-lookup"><span data-stu-id="cb79f-238">Direction values</span></span>
- <span data-ttu-id="cb79f-239">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="cb79f-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="cb79f-240">[スパム検出] レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="cb79f-241">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="cb79f-242">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-242">**Date**</span></span>
- <span data-ttu-id="cb79f-243">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="cb79f-243">**Sender address**</span></span>
- <span data-ttu-id="cb79f-244">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="cb79f-244">**Recipient address**</span></span>
- <span data-ttu-id="cb79f-245">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="cb79f-245">**Event type**</span></span>
- <span data-ttu-id="cb79f-246">**操作**</span><span class="sxs-lookup"><span data-stu-id="cb79f-246">**Action**</span></span>
- <span data-ttu-id="cb79f-247">**件名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-247">**Subject**</span></span>

<span data-ttu-id="cb79f-248">詳細テーブルで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="cb79f-249">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="cb79f-250">方向の値</span><span class="sxs-lookup"><span data-stu-id="cb79f-250">Direction values</span></span>
- <span data-ttu-id="cb79f-251">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="cb79f-251">Event type values</span></span>

<span data-ttu-id="cb79f-252">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="cb79f-253">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-253">Spoof detections report</span></span>

<span data-ttu-id="cb79f-254">ス **プーフィング検出** レポートには、スプーフィング メール メッセージが検出された数と、それらのスプーフィング メッセージの数が示されます。そのうちの 1 つは "良い" と見なされました (正当なビジネス上の理由で行われたスプーフィング メール)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="cb79f-255">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="cb79f-256">レポートの集計ビューでは 90 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="cb79f-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="cb79f-257">レポートを表示するには、セキュリティ コンプライアンス センターを開 [&[](https://protection.office.com)レポート **ダッシュボード]** に移動し、[スプーフィングの検出 \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="cb79f-258">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="cb79f-260">グラフで 1 日 (データ ポイント) をポイントすると、スプーフィング メール メッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="cb79f-261">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="cb79f-262">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="cb79f-263">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="cb79f-263">**Good mail**</span></span>

- <span data-ttu-id="cb79f-264">**スパムとしてキャッチされる**</span><span class="sxs-lookup"><span data-stu-id="cb79f-264">**Caught as spam**</span></span>

![スプーフィング検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="cb79f-266">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cb79f-267">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-267">**Date**</span></span>
- <span data-ttu-id="cb79f-268">**スプーフィングされた送信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-268">**Spoofed sender**</span></span>
- <span data-ttu-id="cb79f-269">**True の送信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-269">**True sender**</span></span>
- <span data-ttu-id="cb79f-270">[**Sender IP (送信者の IP)**]</span><span class="sxs-lookup"><span data-stu-id="cb79f-270">**Sender IP**</span></span>
- <span data-ttu-id="cb79f-271">**操作**</span><span class="sxs-lookup"><span data-stu-id="cb79f-271">**Action**</span></span>
- <span data-ttu-id="cb79f-272">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="cb79f-272">**Message count**</span></span>

<span data-ttu-id="cb79f-273">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cb79f-274">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-274">Threat protection status report</span></span>

<span data-ttu-id="cb79f-275">脅威 **保護の状態レポート** は、EOP と Microsoft Defender の両方Office 365 です。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="cb79f-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="cb79f-276">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが [、SharePoint、OneDrive、および Microsoft Teams](mdo-for-spo-odb-and-teams.md)の安全な添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="cb79f-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="cb79f-277">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト のアドレス (URL)、ゼロ時間自動削除[(ZAP)、](zero-hour-auto-purge.md)および Defender for Office 365 機能 (セーフ リンク、安全な添付ファイル、[](safe-attachments.md)フィッシング対策など)[](set-up-anti-phishing-policies.md)などの悪意のあるコンテンツを含む電子メール メッセージの数が提供されます。 [](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="cb79f-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="cb79f-278">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="cb79f-279">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="cb79f-280">レポートを表示するには、コンプライアンス センターでセキュリティ &[を](https://protection.office.com)開き、[レポート **ダッシュボード]** に移動し、[脅威保護の状態 \> ]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="cb79f-281">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="cb79f-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="cb79f-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="cb79f-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="cb79f-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="cb79f-285">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="cb79f-286">[フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="cb79f-287">詳細テーブル ビューでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="cb79f-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cb79f-288">脅威保護状態レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="cb79f-289">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-289">The following views are available:</span></span>

- <span data-ttu-id="cb79f-290">**データの表示方法: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="cb79f-291">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="cb79f-291">**Email malware**</span></span>
  - <span data-ttu-id="cb79f-292">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="cb79f-292">**Email phish**</span></span>
  - <span data-ttu-id="cb79f-293">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="cb79f-293">**Content malware**</span></span>

  ![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="cb79f-295">**データの表示方法: コンテンツ \> マルウェア**<sup>1</sup>: 365 組織の Microsoft Defender にOffice示されています。</span><span class="sxs-lookup"><span data-stu-id="cb79f-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="cb79f-296">**マルウェア対策エンジン**: [Microsoft 365](virus-detection-in-spo.md)で組み込みのウイルス検出によって Sharepoint、OneDrive、および Microsoft Teams で検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="cb79f-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="cb79f-297">**ファイルの削除**: [SharePoint、OneDrive、および Microsoft Teams](mdo-for-spo-odb-and-teams.md)の安全な添付ファイルによって検出された悪意のあるファイル。</span><span class="sxs-lookup"><span data-stu-id="cb79f-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="cb79f-299">**データの表示: メッセージの上書き**: 次のオーバーライド理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="cb79f-300">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="cb79f-300">**On-premises skip**</span></span>
  - <span data-ttu-id="cb79f-301">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="cb79f-301">**IP Allow**</span></span>
  - <span data-ttu-id="cb79f-302">**メール フロー ルール**</span><span class="sxs-lookup"><span data-stu-id="cb79f-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="cb79f-303">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="cb79f-303">**Sender allow**</span></span>
  - <span data-ttu-id="cb79f-304">**ドメイン許可**</span><span class="sxs-lookup"><span data-stu-id="cb79f-304">**Domain allow**</span></span>
  - <span data-ttu-id="cb79f-305">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="cb79f-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="cb79f-306">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="cb79f-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="cb79f-307">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="cb79f-308">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-308">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="cb79f-310">**[検出テクノロジ] と [\*\*\*\*データの表示方法: メール \> フィッシング:** 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="cb79f-311">**ATP で生成された URL 評価**<sup>1</sup>: 他の Microsoft 365 のお客様の 365 回のOfficeに対して Defender から生成された悪意のある URL レピュテーション。</span><span class="sxs-lookup"><span data-stu-id="cb79f-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="cb79f-312">**高度なフィッシング フィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="cb79f-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="cb79f-313">**スプーフィング対策 - DMARC エラー**: メッセージに対する DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="cb79f-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="cb79f-314">**スプーフィング対策 - 組織内**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="cb79f-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="cb79f-315">**スプーフィング対策 - 外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="cb79f-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="cb79f-316">**ブランド偽装**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="cb79f-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="cb79f-317">**ドメイン偽装**<sup>1:</sup>顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="cb79f-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="cb79f-318">**EOP URL レピュテーション**: 悪意のある URL レピュテーション。</span><span class="sxs-lookup"><span data-stu-id="cb79f-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="cb79f-319">**一般的なフィッシング フィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="cb79f-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="cb79f-320">**Others**</span><span class="sxs-lookup"><span data-stu-id="cb79f-320">**Others**</span></span>
  - <span data-ttu-id="cb79f-321">**フィッシング ZAP**<sup>2</sup>: フィッシング メッセージのゼロ時間自動削除。</span><span class="sxs-lookup"><span data-stu-id="cb79f-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="cb79f-322">**URL のデトナレーション**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="cb79f-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="cb79f-323">**ユーザー偽装**<sup>1</sup>: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="cb79f-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="cb79f-325">**[検出テクノロジ] と [\*\*\*\*データの表示方法: メール \> マルウェア]**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cb79f-326">**ATP で生成されたファイル評価**<sup>1</sup>: 365 回のOfficeが Defender によって生成されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="cb79f-327">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="cb79f-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="cb79f-328">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="cb79f-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="cb79f-329">**ファイルの削除**<sup>1</sup>: 安全な添付ファイルによる検出。</span><span class="sxs-lookup"><span data-stu-id="cb79f-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="cb79f-330">**悪意のあるファイル評価**</span><span class="sxs-lookup"><span data-stu-id="cb79f-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="cb79f-331">**マルウェア ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="cb79f-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="cb79f-332">**Others**</span><span class="sxs-lookup"><span data-stu-id="cb79f-332">**Others**</span></span>

  ![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="cb79f-334">**[ポリシーの種類] と** [データの表示方法 **]: \>** [メールフィッシング] または [データの表示 **方法: メール \> マルウェア**] : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cb79f-335">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="cb79f-335">**Anti-malware**</span></span>
  - <span data-ttu-id="cb79f-336">**安全な添付**<sup>ファイル 1</sup></span><span class="sxs-lookup"><span data-stu-id="cb79f-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="cb79f-337">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="cb79f-337">**Anti-phish**</span></span>
  - <span data-ttu-id="cb79f-338">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="cb79f-338">**Anti-spam**</span></span>
  - <span data-ttu-id="cb79f-339">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="cb79f-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="cb79f-340">**Others**</span><span class="sxs-lookup"><span data-stu-id="cb79f-340">**Others**</span></span>

  ![脅威保護状態レポートのフィッシング メールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="cb79f-342">**[配信の状態]** と [データの表示方法]: [メール フィッシング] または [データの表示 **方法: メール \>** マルウェア] : 次の情報が表示されます。 **\>**</span><span class="sxs-lookup"><span data-stu-id="cb79f-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="cb79f-343">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="cb79f-343">**Delivery failed**</span></span>
  - <span data-ttu-id="cb79f-344">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="cb79f-344">**Dropped**</span></span>
  - <span data-ttu-id="cb79f-345">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="cb79f-345">**Forwarded**</span></span>
  - <span data-ttu-id="cb79f-346">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="cb79f-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="cb79f-347">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="cb79f-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="cb79f-348">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="cb79f-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="cb79f-349">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="cb79f-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="cb79f-350">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="cb79f-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="cb79f-351">**検疫**</span><span class="sxs-lookup"><span data-stu-id="cb79f-351">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシングメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="cb79f-353"><sup>1</sup> Defender for Office 365 のみ</span><span class="sxs-lookup"><span data-stu-id="cb79f-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="cb79f-354"><sup>2</sup> ゼロ時間自動削除 (ZAP) はスタンドアロン EOP では使用できません (Exchange Online メールボックスでのみ機能します)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="cb79f-355">[フィルター] **をクリック** すると、使用可能なフィルターは、表示していたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb79f-356">[**データの表示方法: コンテンツ \> マルウェア**] では、開始日と終了日、および検出値によってレポート **を変更** できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cb79f-357">[ **データの表示方法: メッセージの上書き**] では、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cb79f-358">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-359">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="cb79f-359">**Override Reason**</span></span>
  - <span data-ttu-id="cb79f-360">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cb79f-361">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cb79f-362">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-362">**Domain**</span></span>

- <span data-ttu-id="cb79f-363">他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cb79f-364">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-365">**検出**</span><span class="sxs-lookup"><span data-stu-id="cb79f-365">**Detection**</span></span>
  - <span data-ttu-id="cb79f-366">**で保護:** **ATP** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="cb79f-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="cb79f-367">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cb79f-368">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cb79f-369">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="cb79f-370">脅威保護状態レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="cb79f-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="cb79f-371">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cb79f-372">**[データの表示方法]: [概要]**: [ **詳細の表示] テーブル ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb79f-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="cb79f-373">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="cb79f-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="cb79f-374">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-374">**Date**</span></span>
  - <span data-ttu-id="cb79f-375">**Location**</span><span class="sxs-lookup"><span data-stu-id="cb79f-375">**Location**</span></span>
  - <span data-ttu-id="cb79f-376">**監督者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-376">**Directed by**</span></span>
  - <span data-ttu-id="cb79f-377">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-377">**Malware name**</span></span>

  <span data-ttu-id="cb79f-378">このビューで **[フィルター]** をクリックすると、開始日と終了日、および検出値によってレポートを **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="cb79f-379">**データの表示方法: メッセージの上書き**:</span><span class="sxs-lookup"><span data-stu-id="cb79f-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="cb79f-380">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-380">**Date**</span></span>
  - <span data-ttu-id="cb79f-381">**件名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-381">**Subject**</span></span>
  - <span data-ttu-id="cb79f-382">**送信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-382">**Sender**</span></span>
  - <span data-ttu-id="cb79f-383">**受信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-383">**Recipients**</span></span>
  - <span data-ttu-id="cb79f-384">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="cb79f-384">**Detected by**</span></span>
  - <span data-ttu-id="cb79f-385">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="cb79f-385">**Override Reason**</span></span>
  - <span data-ttu-id="cb79f-386">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="cb79f-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="cb79f-387">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cb79f-387">**Tags**</span></span>

  <span data-ttu-id="cb79f-388">このビューで [ **フィルター]** をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cb79f-389">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-390">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="cb79f-390">**Override Reason**</span></span>
  - <span data-ttu-id="cb79f-391">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cb79f-392">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cb79f-393">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-393">**Domain**</span></span>
  - <span data-ttu-id="cb79f-394">**受信者** (このフィルター可能なプロパティは、詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="cb79f-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="cb79f-395">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="cb79f-395">All other charts:</span></span>

  - <span data-ttu-id="cb79f-396">**日付**</span><span class="sxs-lookup"><span data-stu-id="cb79f-396">**Date**</span></span>
  - <span data-ttu-id="cb79f-397">**件名**</span><span class="sxs-lookup"><span data-stu-id="cb79f-397">**Subject**</span></span>
  - <span data-ttu-id="cb79f-398">**送信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-398">**Sender**</span></span>
  - <span data-ttu-id="cb79f-399">**受信者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-399">**Recipients**</span></span>
  - <span data-ttu-id="cb79f-400">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="cb79f-400">**Detected by**</span></span>
  - <span data-ttu-id="cb79f-401">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="cb79f-401">**Delivery Status**</span></span>
  - <span data-ttu-id="cb79f-402">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="cb79f-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="cb79f-403">**Tags**</span><span class="sxs-lookup"><span data-stu-id="cb79f-403">**Tags**</span></span>

  <span data-ttu-id="cb79f-404">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cb79f-405">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cb79f-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cb79f-406">**検出**</span><span class="sxs-lookup"><span data-stu-id="cb79f-406">**Detection**</span></span>
  - <span data-ttu-id="cb79f-407">**Protected by**: **Defender for Office 365** or **EOP**</span><span class="sxs-lookup"><span data-stu-id="cb79f-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="cb79f-408">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="cb79f-409">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="cb79f-410">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="cb79f-410">**Domain**</span></span>
  - <span data-ttu-id="cb79f-411">**受信者** (このフィルター可能なプロパティは、詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="cb79f-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="cb79f-412">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-412">Top malware report</span></span>

<span data-ttu-id="cb79f-413">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="cb79f-414">レポートを表示するには、コンプライアンス センターでセキュリティ &[を](https://protection.office.com)開き、[レポート **ダッシュボード]** に移動し、[ \> 上位マルウェア]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="cb79f-415">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="cb79f-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![レポート ダッシュボードの上位マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="cb79f-417">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="cb79f-419">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="cb79f-420">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="cb79f-420">**Top malware**</span></span>
- <span data-ttu-id="cb79f-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="cb79f-421">**Count**</span></span>

<span data-ttu-id="cb79f-422">レポート ビューまたは **詳細テーブル ビュー** で [フィルター] をクリックすると、[開始日] と [終了日] で日付 **範囲を\*\*\*\*指定できます**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="cb79f-423">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-423">URL threat protection report</span></span>

<span data-ttu-id="cb79f-424">URL **の脅威保護レポートは** 、Microsoft Defender で 365 Officeできます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cb79f-425">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-425">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="cb79f-426">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="cb79f-426">User-reported messages report</span></span>

<span data-ttu-id="cb79f-427">ユーザー **が報告した** メッセージ レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した電子メール [](enable-the-report-message-add-in.md)メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して [表示](enable-the-report-phish-add-in.md)されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="cb79f-428">詳細は、配信理由など、組織に対して構成されたスパム ポリシーの例外やメール フロー ルールなど、各メッセージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="cb79f-429">詳細を表示するには、ユーザー レポート の一覧でアイテムを選択し、[概要] タブと [詳細] タブ **で情報を\*\*\*\*表示** します。</span><span class="sxs-lookup"><span data-stu-id="cb79f-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![[User-Reportedメッセージ] レポートには、迷惑メールではなく迷惑メールとしてラベル付けされたメッセージ、またはフィッシング詐欺の試行が表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="cb79f-431">このレポートを表示するには、セキュリティ & [コンプライアンス センターで](https://protection.office.com)、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cb79f-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="cb79f-432">[脅威管理 **ダッシュボード]** \> **[** \> **ユーザーが報告したメッセージ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="cb79f-433">[脅威の管理 **] [** \> **ユーザーが報告** \> **したメッセージの確認] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cb79f-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![コンプライアンス センターのセキュリティ &で、[脅威の管理] \> [ユーザーが報告 \> したメッセージの確認] を選択します。](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="cb79f-435">ユーザーが報告したメッセージ レポートが正しく機能するには、365 環境で監査ログOffice必要があります。 </span><span class="sxs-lookup"><span data-stu-id="cb79f-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="cb79f-436">これは通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="cb79f-437">詳細については [、「Turn Microsoft 365 audit log search on or off」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="cb79f-438">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="cb79f-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="cb79f-439">この記事で説明するレポートを表示および使用するには、セキュリティ コンプライアンス センターで次のいずれかの役割グループの&必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb79f-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="cb79f-440">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="cb79f-440">**Organization Management**</span></span>
- <span data-ttu-id="cb79f-441">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="cb79f-441">**Security Administrator**</span></span>
- <span data-ttu-id="cb79f-442">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="cb79f-442">**Security Reader**</span></span>
- <span data-ttu-id="cb79f-443">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="cb79f-443">**Global Reader**</span></span>

<span data-ttu-id="cb79f-444">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb79f-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="cb79f-445">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、セキュリティ & コンプライアンスセンターで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="cb79f-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cb79f-446">詳細については、「[管理者ロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb79f-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cb79f-447">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="cb79f-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cb79f-448">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb79f-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cb79f-449">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="cb79f-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb79f-450">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb79f-450">Related topics</span></span>

[<span data-ttu-id="cb79f-451">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="cb79f-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="cb79f-452">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="cb79f-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cb79f-453">セキュリティ コンプライアンス センターでメール フロー レポート&表示する</span><span class="sxs-lookup"><span data-stu-id="cb79f-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="cb79f-454">Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="cb79f-454">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
