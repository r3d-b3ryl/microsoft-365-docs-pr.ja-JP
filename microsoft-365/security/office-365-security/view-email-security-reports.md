---
title: Defender ポータルで電子メール セキュリティ レポートMicrosoft 365表示する
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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について学習します。 メール セキュリティ レポートは、Defender ポータルMicrosoft 365使用できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930327"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="02106-104">Defender ポータルで電子メール セキュリティ レポートMicrosoft 365表示する</span><span class="sxs-lookup"><span data-stu-id="02106-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02106-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="02106-105">**Applies to**</span></span>
- [<span data-ttu-id="02106-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="02106-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="02106-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="02106-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="02106-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02106-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="02106-109">Microsoft 365 Defender ポータルでは[、Microsoft 365](https://security.microsoft.com)のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能がどのように組織を保護しているかを確認するために、さまざまなレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="02106-110">必要な [アクセス許可を](#what-permissions-are-needed-to-view-these-reports)持っている場合は、Microsoft 365 Defender ポータルでこれらのレポートを表示するには、[レポートの電子メール] & グループ& \>  \> **を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="02106-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="02106-111">レポート ダッシュボードに直接移動するには、を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="02106-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Defender ポータルのダッシュボードMicrosoft 365レポート](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="02106-113">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="02106-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="02106-114">このレポートは、メールボックスを使用Microsoft 365組織Exchange Online使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="02106-115">スタンドアロン 組織 (EOP) 組織ではExchange Online Protection使用できません。</span><span class="sxs-lookup"><span data-stu-id="02106-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="02106-116">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="02106-117">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="02106-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="02106-118">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="02106-119">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![レポート ダッシュボードの侵害されたユーザー ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="02106-121">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="02106-122">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートの電子メール & コラボレーション レポート \>  \> **&]に移動** し、[侵害されたユーザー]の下の [詳細の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02106-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="02106-123">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="02106-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="02106-124">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="02106-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="02106-125">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="02106-126">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="02106-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="02106-127">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="02106-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="02106-129">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="02106-130">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="02106-130">**Creation time**</span></span>
- <span data-ttu-id="02106-131">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="02106-131">**User ID**</span></span>
- <span data-ttu-id="02106-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="02106-132">**Action**</span></span>

<span data-ttu-id="02106-133">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02106-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="02106-134">暗号化レポート</span><span class="sxs-lookup"><span data-stu-id="02106-134">Encryption report</span></span>

<span data-ttu-id="02106-135">暗号化 **レポートは**、EOP で使用できます (サブスクリプションは、Exchange Onlineまたはスタンドアロンの EOP に含Exchange Online使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="02106-136">組織のセキュリティ チームは、このレポートの情報を使用してパターンを特定し、機密性の高い電子メール メッセージのポリシーを積極的に適用または調整できます。</span><span class="sxs-lookup"><span data-stu-id="02106-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="02106-137">例:</span><span class="sxs-lookup"><span data-stu-id="02106-137">For example:</span></span>

- <span data-ttu-id="02106-138">ユーザーによって暗号化された電子メール メッセージの数が多い場合は、暗号化ポリシーを追加して、特定の使用例の暗号化を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="02106-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="02106-139">詳細については、「メール フロー ルールを[定義して](../../compliance/define-mail-flow-rules-to-encrypt-email.md)メール メッセージを暗号化する」を参照Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="02106-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="02106-140">使用可能な暗号化テンプレートが多数あるが、使用しているユーザーがいない場合は、ユーザーが機能トレーニングを必要とするかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="02106-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="02106-141">集計ビューでは過去 90 日間のフィルター処理が可能で、詳細ビューでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="02106-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="02106-142">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートの電子メール & コラボレーション レポート \>  \> **&]に移動** し、[暗号化レポート]の下の [詳細の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02106-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="02106-143">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=EncryptionReport> 。</span><span class="sxs-lookup"><span data-stu-id="02106-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="02106-144">暗号化の詳細については、「メール暗号化」[を参照Microsoft 365。](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="02106-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="02106-145">暗号化レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-145">Report view for the Encryption report</span></span>

<span data-ttu-id="02106-146">グラフで次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="02106-147">**データの表示方法: [メッセージの暗号化レポート** ] と [詳細: 暗号化 **方法]**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="02106-148">**ユーザーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="02106-148">**Encryption by user**</span></span>
  - <span data-ttu-id="02106-149">**ポリシーによる暗号化**</span><span class="sxs-lookup"><span data-stu-id="02106-149">**Encryption by policy**</span></span>

  <span data-ttu-id="02106-150">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="02106-151">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-152">暗号化方法。</span><span class="sxs-lookup"><span data-stu-id="02106-152">Encryption method.</span></span>
  - <span data-ttu-id="02106-153">暗号化テンプレート。</span><span class="sxs-lookup"><span data-stu-id="02106-153">Encryption template.</span></span>

- <span data-ttu-id="02106-154">**データの表示方法: [メッセージの暗号化レポート** ] と [詳細: 暗号化テンプレート **]**: 次の暗号化方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="02106-155">**転送しない**</span><span class="sxs-lookup"><span data-stu-id="02106-155">**Do not forward**</span></span>
  - <span data-ttu-id="02106-156">**暗号化のみ**</span><span class="sxs-lookup"><span data-stu-id="02106-156">**Encrypt only**</span></span>
  - <span data-ttu-id="02106-157">**OME 前**</span><span class="sxs-lookup"><span data-stu-id="02106-157">**OME previous**</span></span>
  - <span data-ttu-id="02106-158">**Custom**</span><span class="sxs-lookup"><span data-stu-id="02106-158">**Custom**</span></span>

  <span data-ttu-id="02106-159">[フィルター] **をクリック** すると、次のフィルターを使用してグラフを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="02106-160">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-161">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="02106-161">Encryption method</span></span>
  - <span data-ttu-id="02106-162">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="02106-162">Encryption template</span></span>

- <span data-ttu-id="02106-163">**データの表示方法: 上位 5** つの受信者ドメイン : このビューには、上位 5 つの受信者ドメインの送信メッセージ数を含む円グラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="02106-164">[フィルター] **をクリックすると**、[開始日] と **[終了日]** **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="02106-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="02106-165">暗号化レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="02106-166">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02106-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="02106-167">**[詳細]: [暗号化方法] または** [ **詳細: 暗号化テンプレート]**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="02106-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-168">**Date**</span></span>
  - <span data-ttu-id="02106-169">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="02106-169">**Sender address**</span></span>
  - <span data-ttu-id="02106-170">**暗号化テンプレート**</span><span class="sxs-lookup"><span data-stu-id="02106-170">**Encryption template**</span></span>
  - <span data-ttu-id="02106-171">**暗号化方法**</span><span class="sxs-lookup"><span data-stu-id="02106-171">**Encryption method**</span></span>
  - <span data-ttu-id="02106-172">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="02106-172">**Recipient address**</span></span>
  - <span data-ttu-id="02106-173">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="02106-173">**Subject**</span></span>

- <span data-ttu-id="02106-174">**データの表示方法: 上位 5 つの受信者ドメイン**:</span><span class="sxs-lookup"><span data-stu-id="02106-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="02106-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-175">**Date**</span></span>
  - <span data-ttu-id="02106-176">**受信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-176">**Recipient domain**</span></span>
  - <span data-ttu-id="02106-177">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="02106-177">**Message count**</span></span>

<span data-ttu-id="02106-178">詳細テーブル ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="02106-179">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="02106-180">暗号化方法</span><span class="sxs-lookup"><span data-stu-id="02106-180">Encryption method</span></span>
- <span data-ttu-id="02106-181">暗号化テンプレート</span><span class="sxs-lookup"><span data-stu-id="02106-181">Encryption template</span></span>

<span data-ttu-id="02106-182">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02106-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="02106-183">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="02106-183">Mailflow status report</span></span>

<span data-ttu-id="02106-184">Mailflow **状態レポートには、** マルウェア、スパム、フィッシング、およびエッジブロックされたメッセージに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02106-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="02106-185">詳細については [、「Mailflow status report」を参照してください](view-mail-flow-reports.md#mailflow-status-report)。</span><span class="sxs-lookup"><span data-stu-id="02106-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="02106-186">電子メール レポートのマルウェア検出</span><span class="sxs-lookup"><span data-stu-id="02106-186">Malware detections in email report</span></span>

<span data-ttu-id="02106-187">電子 **メール レポートのマルウェア検出** には、受信および送信電子メール メッセージ (マルウェアが電子メール または EOP によって検出されたマルウェア) のマルウェア検出に関するExchange Online Protection表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="02106-188">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="02106-189">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="02106-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="02106-190">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートメール& コラボレーション メール & コラボレーション レポート] に移動し、[メールで検出されたマルウェア] の下の [詳細を表示] をクリック \>  \> **します**。</span><span class="sxs-lookup"><span data-stu-id="02106-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="02106-191">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="02106-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![レポート ダッシュボードの電子メール ウィジェットでのマルウェア検出](../../media/malware-detections-widget.png)

<span data-ttu-id="02106-193">[フィルター] をクリックして次の項目を選択すると、グラフと詳細テーブル **の両方** をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="02106-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="02106-194">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="02106-195">**受信**</span><span class="sxs-lookup"><span data-stu-id="02106-195">**Inbound**</span></span>
- <span data-ttu-id="02106-196">**送信**</span><span class="sxs-lookup"><span data-stu-id="02106-196">**Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="02106-198">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="02106-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-199">**Date**</span></span>
- <span data-ttu-id="02106-200">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="02106-200">**Sender address**</span></span>
- <span data-ttu-id="02106-201">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="02106-201">**Recipient address**</span></span>
- <span data-ttu-id="02106-202">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02106-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="02106-203">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="02106-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="02106-204">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="02106-204">**Subject**</span></span>
- <span data-ttu-id="02106-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="02106-205">**Filename**</span></span>
- <span data-ttu-id="02106-206">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="02106-206">**Malware name**</span></span>

<span data-ttu-id="02106-207">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02106-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="02106-208">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="02106-208">Mail latency report</span></span>

<span data-ttu-id="02106-209">[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間に関する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="02106-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="02106-210">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="02106-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="02106-211">送信および受信した電子メール レポート</span><span class="sxs-lookup"><span data-stu-id="02106-211">Sent and received email report</span></span>

<span data-ttu-id="02106-212">送信 **および受信電子** メール レポートには、マルウェア、スパム、メール フロー ルール (トランスポート ルールとも呼ばれる)、およびメールがサービスに入った後の高度なマルウェア検出に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="02106-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="02106-213">詳細については、「送信および受信 [メール レポート」を参照してください](view-mail-flow-reports.md#sent-and-received-email-report)。</span><span class="sxs-lookup"><span data-stu-id="02106-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="02106-214">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="02106-214">Spam detections report</span></span>

<span data-ttu-id="02106-215">[ **スパム検出] レポートには** 、EOP によってブロックされたスパム メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="02106-216">メッセージは受信者ごとにではなく、個別にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="02106-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="02106-217">たとえば、同じスパム メッセージが組織内の 100 人の受信者に送信された場合、そのメッセージは 1 つのメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="02106-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="02106-218">集計ビューでは 90 日間のフィルター処理が可能で、詳細テーブルでは 10 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="02106-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="02106-219">レポートを表示するには [、Microsoft 365 Defender ポータルを開](https://security.microsoft.com)き、[レポートメール& コラボレーション メール \>  \> **&** コラボレーション レポート] に移動し、[スパム検出] の下の [詳細の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02106-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="02106-220">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpamDetections> 。</span><span class="sxs-lookup"><span data-stu-id="02106-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![レポート ダッシュボードのスパム検出ウィジェット](../../media/spam-detections-report-widget.png)

<span data-ttu-id="02106-222">スパム対策保護の詳細については [、「EOP のスパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="02106-223">スパム検出レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="02106-224">レポート ビューでは、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="02106-225">**ブレークダウン: アクション**: 次のイベントの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="02106-226">**フィルター処理されたスパム コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="02106-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="02106-227">**スパム IP ブロック**</span><span class="sxs-lookup"><span data-stu-id="02106-227">**Spam IP block**</span></span>
  - <span data-ttu-id="02106-228">**スパム エンベロープ ブロック**</span><span class="sxs-lookup"><span data-stu-id="02106-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="02106-229">**スパム DBEB フィルター**: ディレクトリ ベースのエッジ ブロック (DBEB)</span><span class="sxs-lookup"><span data-stu-id="02106-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="02106-230">グラフで 1 日 (データ ポイント) をポイントすると、その日にブロックされたアイテムの数と、それらのアイテムの分類方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="02106-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![[スパム検出] レポートのアクション ビュー](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="02106-232">**[ブレークダウン]: [方向**] : 次の方向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="02106-233">**受信**</span><span class="sxs-lookup"><span data-stu-id="02106-233">**Inbound**</span></span>
  - <span data-ttu-id="02106-234">**送信**</span><span class="sxs-lookup"><span data-stu-id="02106-234">**Outbound**</span></span>

  ![[スパム検出] レポートの方向表示](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="02106-236">レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="02106-237">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="02106-238">方向の値</span><span class="sxs-lookup"><span data-stu-id="02106-238">Direction values</span></span>
- <span data-ttu-id="02106-239">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="02106-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="02106-240">[スパム検出] レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="02106-241">レポート ビューで **[詳細テーブルの表示** ] をクリックすると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="02106-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-242">**Date**</span></span>
- <span data-ttu-id="02106-243">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="02106-243">**Sender address**</span></span>
- <span data-ttu-id="02106-244">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="02106-244">**Recipient address**</span></span>
- <span data-ttu-id="02106-245">**イベントの種類**</span><span class="sxs-lookup"><span data-stu-id="02106-245">**Event type**</span></span>
- <span data-ttu-id="02106-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="02106-246">**Action**</span></span>
- <span data-ttu-id="02106-247">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="02106-247">**Subject**</span></span>

<span data-ttu-id="02106-248">詳細テーブルで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="02106-249">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="02106-250">方向の値</span><span class="sxs-lookup"><span data-stu-id="02106-250">Direction values</span></span>
- <span data-ttu-id="02106-251">イベントの種類の値</span><span class="sxs-lookup"><span data-stu-id="02106-251">Event type values</span></span>

<span data-ttu-id="02106-252">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02106-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="02106-253">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="02106-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="02106-254">この記事で説明するように改善されたスプーフィング検出レポートはプレビューで、変更される可能性があります。また、すべての組織で利用できるとは限られません。</span><span class="sxs-lookup"><span data-stu-id="02106-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="02106-255">レポートの以前のバージョンでは、良いメールだけが表示 **され** 、スパム **としてキャッチされました**。</span><span class="sxs-lookup"><span data-stu-id="02106-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="02106-256">ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="02106-257">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="02106-258">レポートの集計ビューでは 45 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター <sup>\*</sup> 処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="02106-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="02106-259"><sup>\*</sup> 最終的には、最大 90 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="02106-260">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートメール& コラボレーション メール &] コラボレーション レポートに移動し、[スプーフィングの検出] の下の [詳細の表示] \>  \> **を** クリック **します**。 </span><span class="sxs-lookup"><span data-stu-id="02106-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="02106-261">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReport> 。</span><span class="sxs-lookup"><span data-stu-id="02106-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![レポート ダッシュボードのスプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="02106-263">グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="02106-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="02106-264">[フィルター] をクリックし、次の値の1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="02106-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="02106-265">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="02106-266">**結果**</span><span class="sxs-lookup"><span data-stu-id="02106-266">**Result**</span></span>
  - <span data-ttu-id="02106-267">**Pass**</span><span class="sxs-lookup"><span data-stu-id="02106-267">**Pass**</span></span>
  - <span data-ttu-id="02106-268">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="02106-268">**Fail**</span></span>
  - <span data-ttu-id="02106-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="02106-269">**SoftPass**</span></span>
  - <span data-ttu-id="02106-270">**なし**</span><span class="sxs-lookup"><span data-stu-id="02106-270">**None**</span></span>
  - <span data-ttu-id="02106-271">**その他**</span><span class="sxs-lookup"><span data-stu-id="02106-271">**Other**</span></span>

- <span data-ttu-id="02106-272">**スプーフィングの** 種類 :**内部と\*\*\*\*外部**</span><span class="sxs-lookup"><span data-stu-id="02106-272">**Spoof type**: **Internal** and **External**</span></span>

![スプーフィング検出レポートのレポート ビュー](../../media/spoof-detections-report-view.png)

<span data-ttu-id="02106-274">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="02106-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-275">**Date**</span></span>
- <span data-ttu-id="02106-276">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="02106-276">**Spoofed user**</span></span>
- <span data-ttu-id="02106-277">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="02106-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="02106-278">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="02106-278">**Spoof type**</span></span>
- <span data-ttu-id="02106-279">**結果**</span><span class="sxs-lookup"><span data-stu-id="02106-279">**Result**</span></span>
- <span data-ttu-id="02106-280">**結果コード**</span><span class="sxs-lookup"><span data-stu-id="02106-280">**Result code**</span></span>
- <span data-ttu-id="02106-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="02106-281">**SPF**</span></span>
- <span data-ttu-id="02106-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="02106-282">**DKIM**</span></span>
- <span data-ttu-id="02106-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="02106-283">**DMARC**</span></span>
- <span data-ttu-id="02106-284">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="02106-284">**Message count**</span></span>

<span data-ttu-id="02106-285">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02106-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="02106-286">複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="02106-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="02106-287">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="02106-287">Threat protection status report</span></span>

<span data-ttu-id="02106-288">脅威 **保護の状態レポート** は、EOP と Microsoft Defender の両方Office 365。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="02106-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="02106-289">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが[、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="02106-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="02106-290">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト のアドレス (URL)、ゼロ時間自動削除[(ZAP)、セーフ](zero-hour-auto-purge.md)[リンク、セーフ](safe-links.md)[添付](safe-attachments.md)ファイル、フィッシング対策などの Office 365 機能の Defender などの悪意のあるコンテンツを含む電子メール[](set-up-anti-phishing-policies.md)メッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="02106-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="02106-291">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="02106-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="02106-292">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="02106-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="02106-293">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートの電子メール & コラボレーション レポート \>  \> **&]** に移動し、[脅威保護の状態]の下の [詳細を表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02106-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="02106-294">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="02106-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="02106-295">Microsoft Defender for Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="02106-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="02106-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="02106-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![レポート ダッシュボードの脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="02106-298">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="02106-299">[フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="02106-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="02106-300">詳細テーブル ビューでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="02106-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="02106-301">脅威保護状態レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="02106-302">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-302">The following views are available:</span></span>

- <span data-ttu-id="02106-303">**データの表示方法: 概要**: 次の検出情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="02106-304">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="02106-304">**Email malware**</span></span>
  - <span data-ttu-id="02106-305">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="02106-305">**Email phish**</span></span>
  - <span data-ttu-id="02106-306">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="02106-306">**Content malware**</span></span>

  ![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="02106-308">**データの表示方法: コンテンツ \>マルウェア**<sup>1:</sup>組織の Microsoft Defender に関する次のOffice 365示されています。</span><span class="sxs-lookup"><span data-stu-id="02106-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="02106-309">**マルウェア対策エンジン**: Sharepoint、OneDrive、および Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365。](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="02106-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="02106-310">**ファイルの削除**: 添付ファイルによって検出された悪意のある [セーフ、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="02106-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="02106-312">**データの表示: メッセージの上書き**: 次のオーバーライド理由情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="02106-313">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="02106-313">**On-premises skip**</span></span>
  - <span data-ttu-id="02106-314">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="02106-314">**IP Allow**</span></span>
  - <span data-ttu-id="02106-315">**メール フロー ルール**</span><span class="sxs-lookup"><span data-stu-id="02106-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="02106-316">**送信者の許可**</span><span class="sxs-lookup"><span data-stu-id="02106-316">**Sender allow**</span></span>
  - <span data-ttu-id="02106-317">**ドメイン許可**</span><span class="sxs-lookup"><span data-stu-id="02106-317">**Domain allow**</span></span>
  - <span data-ttu-id="02106-318">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="02106-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="02106-319">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="02106-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="02106-320">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="02106-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="02106-321">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-321">**User Safe Domain**</span></span>

  ![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="02106-323">**[検出テクノロジ] と [\*\*\*\*データの表示方法: メール \> フィッシング:** 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="02106-324">**ATP で生成された URL 評価**<sup>1</sup>: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザー Microsoft 365です。</span><span class="sxs-lookup"><span data-stu-id="02106-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="02106-325">**高度なフィッシング フィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="02106-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="02106-326">**スプーフィング対策 - DMARC エラー**: メッセージに対する DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="02106-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="02106-327">**スプーフィング対策 - 組織内**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="02106-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="02106-328">**スプーフィング対策 - 外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="02106-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="02106-329">**ブランド偽装**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="02106-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="02106-330">**ドメイン偽装**<sup>1:</sup>顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="02106-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="02106-331">**EOP URL レピュテーション**: 悪意のある URL レピュテーション。</span><span class="sxs-lookup"><span data-stu-id="02106-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="02106-332">**一般的なフィッシング フィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="02106-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="02106-333">**Others**</span><span class="sxs-lookup"><span data-stu-id="02106-333">**Others**</span></span>
  - <span data-ttu-id="02106-334">**フィッシング ZAP**<sup>2</sup>: フィッシング メッセージのゼロ時間自動削除。</span><span class="sxs-lookup"><span data-stu-id="02106-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="02106-335">**URL のデトナレーション**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="02106-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="02106-336">**ユーザー偽装**<sup>1</sup>: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスを通じて学習されたユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="02106-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="02106-338">**[検出テクノロジ] と [\*\*\*\*データの表示方法: メール \> マルウェア]**: 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="02106-339">**ATP で生成されたファイル評価**<sup>1:</sup>Defender によって生成された悪意のあるファイル評価Office 365します。</span><span class="sxs-lookup"><span data-stu-id="02106-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="02106-340">**マルウェア対策エンジン**<sup>1</sup>: マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="02106-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="02106-341">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="02106-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="02106-342">**ファイルの削除**<sup>1</sup>: 添付ファイルセーフ検出。</span><span class="sxs-lookup"><span data-stu-id="02106-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="02106-343">**悪意のあるファイル評価**</span><span class="sxs-lookup"><span data-stu-id="02106-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="02106-344">**マルウェア ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="02106-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="02106-345">**Others**</span><span class="sxs-lookup"><span data-stu-id="02106-345">**Others**</span></span>

  ![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="02106-347">**[ポリシーの種類] と** [データの表示方法 **]: \>** [メールフィッシング] または [データの表示 **方法: メール \> マルウェア**] : 次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="02106-348">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="02106-348">**Anti-malware**</span></span>
  - <span data-ttu-id="02106-349">**セーフ添付ファイル**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="02106-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="02106-350">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="02106-350">**Anti-phish**</span></span>
  - <span data-ttu-id="02106-351">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="02106-351">**Anti-spam**</span></span>
  - <span data-ttu-id="02106-352">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="02106-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="02106-353">**Others**</span><span class="sxs-lookup"><span data-stu-id="02106-353">**Others**</span></span>

  ![脅威保護状態レポートのフィッシング メールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="02106-355">**[配信の状態]** と [データの表示方法]: [メール フィッシング] または [データの表示 **方法: メール \>** マルウェア] : 次の情報が表示されます。 **\>**</span><span class="sxs-lookup"><span data-stu-id="02106-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="02106-356">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="02106-356">**Delivery failed**</span></span>
  - <span data-ttu-id="02106-357">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="02106-357">**Dropped**</span></span>
  - <span data-ttu-id="02106-358">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="02106-358">**Forwarded**</span></span>
  - <span data-ttu-id="02106-359">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="02106-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="02106-360">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="02106-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="02106-361">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="02106-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="02106-362">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="02106-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="02106-363">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="02106-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="02106-364">**検疫**</span><span class="sxs-lookup"><span data-stu-id="02106-364">**Quarantine**</span></span>

  ![脅威保護状態レポートのフィッシングメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="02106-366"><sup>1</sup> Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="02106-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="02106-367"><sup>2</sup>ゼロ時間自動削除 (ZAP) はスタンドアロン EOP では使用できません (これは、既定のメールボックスでのみExchange Onlineします)。</span><span class="sxs-lookup"><span data-stu-id="02106-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="02106-368">[フィルター] **をクリック** すると、使用可能なフィルターは、表示していたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02106-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="02106-369">[**データの表示方法: コンテンツ \> マルウェア**] では、開始日と終了日、および検出値によってレポート **を変更** できます。</span><span class="sxs-lookup"><span data-stu-id="02106-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="02106-370">[ **データの表示方法: メッセージの上書き**] では、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="02106-371">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-372">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="02106-372">**Override Reason**</span></span>
  - <span data-ttu-id="02106-373">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="02106-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="02106-374">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="02106-375">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-375">**Domain**</span></span>

- <span data-ttu-id="02106-376">他のすべてのビューでは、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="02106-377">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-378">**検出**</span><span class="sxs-lookup"><span data-stu-id="02106-378">**Detection**</span></span>
  - <span data-ttu-id="02106-379">**で保護:** **ATP** または **EOP**</span><span class="sxs-lookup"><span data-stu-id="02106-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="02106-380">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="02106-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="02106-381">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="02106-382">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="02106-383">脅威保護状態レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="02106-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="02106-384">[詳細テーブル **の表示]** をクリックすると、表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02106-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="02106-385">**[データの表示方法]: [概要]**: [ **詳細の表示] テーブル ボタン** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="02106-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="02106-386">**データの表示方法: コンテンツ \> マルウェア**:</span><span class="sxs-lookup"><span data-stu-id="02106-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="02106-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-387">**Date**</span></span>
  - <span data-ttu-id="02106-388">**場所**</span><span class="sxs-lookup"><span data-stu-id="02106-388">**Location**</span></span>
  - <span data-ttu-id="02106-389">**監督者**</span><span class="sxs-lookup"><span data-stu-id="02106-389">**Directed by**</span></span>
  - <span data-ttu-id="02106-390">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="02106-390">**Malware name**</span></span>

  <span data-ttu-id="02106-391">このビューで **[フィルター]** をクリックすると、開始日と終了日、および検出値によってレポートを **変更** できます。</span><span class="sxs-lookup"><span data-stu-id="02106-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="02106-392">**データの表示方法: メッセージの上書き**:</span><span class="sxs-lookup"><span data-stu-id="02106-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="02106-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-393">**Date**</span></span>
  - <span data-ttu-id="02106-394">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="02106-394">**Subject**</span></span>
  - <span data-ttu-id="02106-395">**送信者**</span><span class="sxs-lookup"><span data-stu-id="02106-395">**Sender**</span></span>
  - <span data-ttu-id="02106-396">**受信者**</span><span class="sxs-lookup"><span data-stu-id="02106-396">**Recipients**</span></span>
  - <span data-ttu-id="02106-397">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="02106-397">**Detected by**</span></span>
  - <span data-ttu-id="02106-398">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="02106-398">**Override Reason**</span></span>
  - <span data-ttu-id="02106-399">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="02106-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="02106-400">**Tags**</span><span class="sxs-lookup"><span data-stu-id="02106-400">**Tags**</span></span>

  <span data-ttu-id="02106-401">このビューで [ **フィルター]** をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="02106-402">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-403">**オーバーライド理由**</span><span class="sxs-lookup"><span data-stu-id="02106-403">**Override Reason**</span></span>
  - <span data-ttu-id="02106-404">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="02106-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="02106-405">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="02106-406">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-406">**Domain**</span></span>
  - <span data-ttu-id="02106-407">**受信者** (このフィルター可能なプロパティは、詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="02106-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="02106-408">その他のすべてのグラフ:</span><span class="sxs-lookup"><span data-stu-id="02106-408">All other charts:</span></span>

  - <span data-ttu-id="02106-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="02106-409">**Date**</span></span>
  - <span data-ttu-id="02106-410">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="02106-410">**Subject**</span></span>
  - <span data-ttu-id="02106-411">**送信者**</span><span class="sxs-lookup"><span data-stu-id="02106-411">**Sender**</span></span>
  - <span data-ttu-id="02106-412">**受信者**</span><span class="sxs-lookup"><span data-stu-id="02106-412">**Recipients**</span></span>
  - <span data-ttu-id="02106-413">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="02106-413">**Detected by**</span></span>
  - <span data-ttu-id="02106-414">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="02106-414">**Delivery Status**</span></span>
  - <span data-ttu-id="02106-415">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="02106-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="02106-416">**Tags**</span><span class="sxs-lookup"><span data-stu-id="02106-416">**Tags**</span></span>

  <span data-ttu-id="02106-417">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="02106-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="02106-418">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="02106-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="02106-419">**検出**</span><span class="sxs-lookup"><span data-stu-id="02106-419">**Detection**</span></span>
  - <span data-ttu-id="02106-420">**Protected by**: **Defender for Office 365** **EOP**</span><span class="sxs-lookup"><span data-stu-id="02106-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="02106-421">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="02106-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="02106-422">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="02106-423">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="02106-423">**Domain**</span></span>
  - <span data-ttu-id="02106-424">**受信者** (このフィルター可能なプロパティは、詳細テーブル ビューでのみ使用できます)</span><span class="sxs-lookup"><span data-stu-id="02106-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="02106-425">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="02106-425">Top malware report</span></span>

<span data-ttu-id="02106-426">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="02106-427">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[レポートの電子メール & コラボレーション レポート&] に移動し、[トップ マルウェア] の下の [詳細を表示] を \>  \> **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="02106-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="02106-428">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="02106-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![レポート ダッシュボードの上位マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="02106-430">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="02106-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

<span data-ttu-id="02106-432">[詳細テーブルの **表示] をクリック** すると、次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="02106-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="02106-433">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="02106-433">**Top malware**</span></span>
- <span data-ttu-id="02106-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="02106-434">**Count**</span></span>

<span data-ttu-id="02106-435">レポート ビューまたは **詳細テーブル ビュー** で [フィルター] をクリックすると、[開始日] と [終了日] で日付 **範囲を\*\*\*\*指定できます**。</span><span class="sxs-lookup"><span data-stu-id="02106-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="02106-436">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="02106-436">URL threat protection report</span></span>

<span data-ttu-id="02106-437">URL **の脅威保護レポートは**、Microsoft Defender で使用できるOffice 365。</span><span class="sxs-lookup"><span data-stu-id="02106-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="02106-438">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="02106-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="02106-439">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="02106-439">User reported messages report</span></span>

<span data-ttu-id="02106-440">[**ユーザーレポート メッセージ]** レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した [](enable-the-report-message-add-in.md)電子メール メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して [表示されます](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="02106-441">詳細は、配信理由など、組織に対して構成されたスパム ポリシーの例外やメール フロー ルールなど、各メッセージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="02106-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="02106-442">詳細を表示するには、ユーザー レポート の一覧でアイテムを選択し、[概要] タブと [詳細] タブ **で情報を\*\*\*\*表示** します。</span><span class="sxs-lookup"><span data-stu-id="02106-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![[ユーザーが報告したメッセージ] レポートには、迷惑メール、迷惑メール、またはフィッシングの試みとしてラベル付けされたメッセージが表示されます。](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="02106-444">このレポートを表示するには、Defender ポータルの [[Microsoft 365]](https://security.microsoft.com)に移動し、[電子メール のレポート] &グループ&レポート ユーザーが報告したメッセージ \>  \>  \> **を報告します**。</span><span class="sxs-lookup"><span data-stu-id="02106-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="02106-445">[レポート] \> **[電子メール] &[グループ** \> **&] [ユーザーが報告した** メッセージ \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02106-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![[Defender ポータルMicrosoft 365] で、[メールのレポート] を選択& \> グループ& \> レポートユーザーがメッセージ \> を報告します。](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="02106-447">ユーザーが報告したメッセージ レポートが正しく機能するには、ユーザーの環境で監査ログを有効Office 365があります。</span><span class="sxs-lookup"><span data-stu-id="02106-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="02106-448">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="02106-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="02106-449">詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="02106-450">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="02106-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="02106-451">この記事で説明するレポートを表示して使用するには、Defender ポータルの次のいずれかの役割グループのMicrosoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="02106-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="02106-452">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="02106-452">**Organization Management**</span></span>
- <span data-ttu-id="02106-453">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="02106-453">**Security Administrator**</span></span>
- <span data-ttu-id="02106-454">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="02106-454">**Security Reader**</span></span>
- <span data-ttu-id="02106-455">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="02106-455">**Global Reader**</span></span>

<span data-ttu-id="02106-456">詳細については、「Defender ポータル[のアクセス許可」をMicrosoft 365してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="02106-457">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="02106-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="02106-458">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02106-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="02106-459">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="02106-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="02106-460">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="02106-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="02106-461">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="02106-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="02106-462">関連項目</span><span class="sxs-lookup"><span data-stu-id="02106-462">Related topics</span></span>

[<span data-ttu-id="02106-463">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="02106-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="02106-464">Defender ポータルのスマート レポートMicrosoft 365分析情報</span><span class="sxs-lookup"><span data-stu-id="02106-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="02106-465">Defender ポータルでメール フロー レポートをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="02106-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="02106-466">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="02106-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
