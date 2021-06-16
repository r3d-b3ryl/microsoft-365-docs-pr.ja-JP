---
title: '[レポート] ダッシュボードでOffice 365レポートの Defender を表示する'
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender のレポートを検索して、Office 365 Defender ポータルMicrosoft 365使用します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5c45f58ee83de11712b198c85a8e423314289bf
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930234"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f64ab-103">Defender ポータルの [Office 365] ダッシュボードで[Defender for Microsoft 365レポートを表示する]</span><span class="sxs-lookup"><span data-stu-id="f64ab-103">View Defender for Office 365 reports in the Reports dashboard in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f64ab-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f64ab-104">**Applies to**</span></span>
- [<span data-ttu-id="f64ab-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f64ab-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f64ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f64ab-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f64ab-107">Office 365 組織向け Microsoft Defender (Microsoft 365 E5 サブスクリプション、Office 365 プラン 1 の Microsoft Defender、Office 365 プラン 2 アドオンの Microsoft Defender など) には、さまざまなセキュリティ関連レポートが含まれる。</span><span class="sxs-lookup"><span data-stu-id="f64ab-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="f64ab-108">必要な [アクセス許可がある](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)場合は、[電子メールの共同作業レポート] にアクセスして、Microsoft 365 Defender ポータルでこれらのレポート \>  \> **を表示できます**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email collaboration** \> **Email collaboration reports**.</span></span> <span data-ttu-id="f64ab-109">レポート ダッシュボードに直接移動するには、を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-109">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Defender ポータルの [レポート] Microsoft 365ダッシュボード](../../media/user-reported-messages.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="f64ab-111">Defender for Office 365 のファイル型レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="f64ab-112">[**ファイルの種類Office 365の** Defender レポートには、添付ファイルによって悪意のあるファイルとして検出されたファイルセーフ [表示されます](safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](safe-attachments.md).</span></span>

 <span data-ttu-id="f64ab-113">レポートの集計ビューでは 90 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="f64ab-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="f64ab-114">レポートを表示するには、Defender ポータルの Microsoft 365 [開き、[](https://security.microsoft.com)レポートダッシュボード] に移動し、[Defender] を選択してファイルの種類 \> **Office 365します**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-114">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="f64ab-115">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ATPFileReport> 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![レポート ダッシュボードOffice 365ファイルの種類ウィジェットの Defender](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f64ab-117">このレポートの情報は、メッセージ廃棄レポートの[Defender でもOffice 365使用できます](#defender-for-office-365-message-disposition-report)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="f64ab-118">[ファイルの種類] レポートの Defender Office 365ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="f64ab-119">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-119">The following views are available:</span></span>

- <span data-ttu-id="f64ab-120">**データの表示方法: ファイル**: グラフには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f64ab-121">**悪意のあるExcel添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="f64ab-122">**悪意のあるフラッシュの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="f64ab-123">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="f64ab-124">**悪意のあるPowerPoint添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="f64ab-125">**悪意のある URL**</span><span class="sxs-lookup"><span data-stu-id="f64ab-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="f64ab-126">**悪意のある Word の添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="f64ab-127">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="f64ab-128">**Others**</span><span class="sxs-lookup"><span data-stu-id="f64ab-128">**Others**</span></span>

  <span data-ttu-id="f64ab-129">特定の日 (データ ポイント) にカーソルを合わせると[、EOP](safe-attachments.md)の セーフ 添付ファイルとマルウェア対策保護によって検出された悪意のあるファイルの種類の内訳を[確認できます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![[ファイルの種類] レポートの [Defender Office 365ビュー]](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="f64ab-131">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-132">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-133">グラフに表示されるのと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="f64ab-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="f64ab-134">**データの表示: メッセージ**: グラフには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f64ab-135">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="f64ab-135">**Block access**</span></span>
  - <span data-ttu-id="f64ab-136">**置き換えられたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f64ab-136">**Messages replaced**</span></span>
  - <span data-ttu-id="f64ab-137">**監視対象のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f64ab-137">**Messages monitored**</span></span>
  - <span data-ttu-id="f64ab-138">**動的メール配信に置き換えられる**: 詳細については、「添付ファイル ポリシーの [動的配信セーフを参照してください](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![[ファイルの種類] レポートの Defender Office 365表示](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="f64ab-140">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-141">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-142">グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="f64ab-143">[ファイルの種類] レポートの Defender Office 365ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="f64ab-144">[詳細テーブル **の表示]** をクリックすると、過去 10 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="f64ab-145">表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f64ab-146">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="f64ab-146">**View data by: File**:</span></span>

  - <span data-ttu-id="f64ab-147">**Date**</span><span class="sxs-lookup"><span data-stu-id="f64ab-147">**Date**</span></span>
  - <span data-ttu-id="f64ab-148">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f64ab-148">**Recipient address**</span></span>
  - <span data-ttu-id="f64ab-149">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-149">**Sender address**</span></span>
  - <span data-ttu-id="f64ab-150">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="f64ab-151">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="f64ab-152">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-152">**File**</span></span>

  <span data-ttu-id="f64ab-153">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-154">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-155">グラフに表示されるのと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="f64ab-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="f64ab-156">**データの表示方法: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="f64ab-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="f64ab-157">**Date**</span><span class="sxs-lookup"><span data-stu-id="f64ab-157">**Date**</span></span>
  - <span data-ttu-id="f64ab-158">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f64ab-158">**Recipient address**</span></span>
  - <span data-ttu-id="f64ab-159">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-159">**Sender address**</span></span>
  - <span data-ttu-id="f64ab-160">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-160">**Message ID**</span></span>
  - <span data-ttu-id="f64ab-161">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-161">**File**</span></span>
  - <span data-ttu-id="f64ab-162">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-162">**Subject**</span></span>

  <span data-ttu-id="f64ab-163">[フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="f64ab-164">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-165">グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="f64ab-166">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f64ab-167">Defender for Office 365 のメッセージ処理レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f64ab-168">**ATP メッセージ廃棄レポート** には、悪意のあるコンテンツが検出された電子メール メッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="f64ab-169">レポートを表示するには [、Microsoft 365 Defender ポータルを開](https://security.microsoft.com)き、[レポート電子メール & コラボレーション の電子メール & コラボレーション レポート] に移動し、[Defender] を選択してメッセージの廃棄Office 365 \>  \> **します**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-169">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="f64ab-170">レポートに直接移動するには、を開きます <https://protection.office.com/reportv2?id=ATPMessageReport> 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![レポート ダッシュボードOffice 365メッセージ廃棄ウィジェットの Defender](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f64ab-172">このレポートの情報は、ファイルの種類レポートの[Defender でもOffice 365参照できます](#defender-for-office-365-file-types-report)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f64ab-173">メッセージ廃棄レポートの Defender Office 365ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f64ab-174">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-174">The following views are available:</span></span>

- <span data-ttu-id="f64ab-175">**データの表示: メッセージ**: グラフには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f64ab-176">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="f64ab-176">**Block access**</span></span>
  - <span data-ttu-id="f64ab-177">**置き換えられたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f64ab-177">**Messages replaced**</span></span>
  - <span data-ttu-id="f64ab-178">**監視対象のメッセージ**</span><span class="sxs-lookup"><span data-stu-id="f64ab-178">**Messages monitored**</span></span>
  - <span data-ttu-id="f64ab-179">**動的メール配信に置き換えられる**: 詳細については、「添付ファイル ポリシーの [動的配信セーフを参照してください](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![[ファイルの種類] レポートの Defender Office 365表示](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="f64ab-181">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-182">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-183">グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="f64ab-184">**データの表示方法: ファイル**: グラフには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="f64ab-185">**悪意のあるExcel添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="f64ab-186">**悪意のあるフラッシュの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="f64ab-187">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="f64ab-188">**悪意のあるPowerPoint添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="f64ab-189">**悪意のある URL**</span><span class="sxs-lookup"><span data-stu-id="f64ab-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="f64ab-190">**悪意のある Word の添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="f64ab-191">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="f64ab-192">**Others**</span><span class="sxs-lookup"><span data-stu-id="f64ab-192">**Others**</span></span>

  <span data-ttu-id="f64ab-193">特定の日 (データ ポイント) にカーソルを合わせると[、EOP](safe-attachments.md)の セーフ 添付ファイルとマルウェア対策保護によって検出された悪意のあるファイルの種類の内訳を[確認できます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![[ファイルの種類] レポートの [Defender Office 365ビュー]](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="f64ab-195">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-196">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-197">グラフに表示されるのと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="f64ab-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="f64ab-198">メッセージ廃棄レポートの Defender の詳細Office 365ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="f64ab-199">[詳細テーブル **の表示]** をクリックすると、過去 10 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="f64ab-200">表示される情報は、表示されているグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="f64ab-201">**データの表示方法: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="f64ab-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="f64ab-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="f64ab-202">**Date**</span></span>
  - <span data-ttu-id="f64ab-203">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f64ab-203">**Recipient address**</span></span>
  - <span data-ttu-id="f64ab-204">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-204">**Sender address**</span></span>
  - <span data-ttu-id="f64ab-205">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-205">**Message ID**</span></span>
  - <span data-ttu-id="f64ab-206">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-206">**File**</span></span>
  - <span data-ttu-id="f64ab-207">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-207">**Subject**</span></span>

  <span data-ttu-id="f64ab-208">[フィルター] **をクリック** すると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="f64ab-209">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-210">グラフで使用できるのと同じメッセージ廃棄値と、その他の **メッセージ渡し値** 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="f64ab-211">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="f64ab-211">**View data by: File**:</span></span>

  - <span data-ttu-id="f64ab-212">**Date**</span><span class="sxs-lookup"><span data-stu-id="f64ab-212">**Date**</span></span>
  - <span data-ttu-id="f64ab-213">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="f64ab-213">**Recipient address**</span></span>
  - <span data-ttu-id="f64ab-214">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-214">**Sender address**</span></span>
  - <span data-ttu-id="f64ab-215">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="f64ab-215">**Message ID**</span></span>
  - <span data-ttu-id="f64ab-216">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="f64ab-216">**File**</span></span>

  <span data-ttu-id="f64ab-217">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-218">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-219">グラフに表示されるのと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="f64ab-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="f64ab-220">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f64ab-221">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-221">Mail latency report</span></span>

<span data-ttu-id="f64ab-222">[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間の集計ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f64ab-223">サービス内のメール配信時間は、多くの要因によって影響を受け、絶対配信時間 (秒) は成功または問題を示す良い指標ではない場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="f64ab-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="f64ab-224">ある日の配信時間が遅い場合は、別の日の平均配信時間、またはその逆と見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="f64ab-225">メール **遅延レポートは、** 他のメッセージの観測された配信時間に関する統計データに基づいて、メッセージ配信を修飾します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="f64ab-226">**50 パーセント :** これは、メッセージの配信時間の中央です。</span><span class="sxs-lookup"><span data-stu-id="f64ab-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="f64ab-227">この値は、平均配信時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="f64ab-228">**90 パーセント :** これは、メッセージ配信の待機時間が長いを示します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="f64ab-229">配信にこの値を超える時間がかかったメッセージはわずか 10% です。</span><span class="sxs-lookup"><span data-stu-id="f64ab-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="f64ab-230">**99 パーセント :** メッセージ配信の最大待機時間を示します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="f64ab-231">クライアント側とネットワークの待機時間は含まれません。</span><span class="sxs-lookup"><span data-stu-id="f64ab-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="f64ab-232">レポートを表示するには [、Microsoft 365 Defender](https://security.microsoft.com)ポータルを開き、[メール& コラボレーション レポート] & [メールの遅延レポート] の下にある [詳細の表示] \>  \> **を** クリック **します**。 </span><span class="sxs-lookup"><span data-stu-id="f64ab-232">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Mail latency report**.</span></span> <span data-ttu-id="f64ab-233">レポートに直接移動するには、を開きます <https://security.microsoft.com/mailLatencyReport> 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-233">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![レポート ダッシュボードのメール待機時間レポート ウィジェット](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="f64ab-235">メール待機時間レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="f64ab-236">レポートを開いた場合、既定では **[50 番目** のパーセント] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="f64ab-237">既定では、このビューには、次のフィルターで構成されたグラフが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="f64ab-238">**日付**: 過去 7 日間</span><span class="sxs-lookup"><span data-stu-id="f64ab-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="f64ab-239">**メッセージ ビュー**:</span><span class="sxs-lookup"><span data-stu-id="f64ab-239">**Message View**:</span></span>
  - <span data-ttu-id="f64ab-240">削除されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="f64ab-240">Detonated messages</span></span>

<span data-ttu-id="f64ab-241">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f64ab-242">**メール配信の待機時間**</span><span class="sxs-lookup"><span data-stu-id="f64ab-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="f64ab-243">**デトナレーションの待機時間**</span><span class="sxs-lookup"><span data-stu-id="f64ab-243">**Detonation latency**</span></span>

<span data-ttu-id="f64ab-244">グラフのカテゴリにカーソルを合わせると、各カテゴリの待機時間の内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![メール遅延レポート](../../media/mail-latency-report.png)

<span data-ttu-id="f64ab-246">レポート ビューで **[フィルター]** をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="f64ab-247">すべてのメッセージ</span><span class="sxs-lookup"><span data-stu-id="f64ab-247">All messages</span></span>
- <span data-ttu-id="f64ab-248">添付ファイルまたは URL を含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="f64ab-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="f64ab-249">**[90** 番目のパーセント] タブまたは **[99** 番目のパーセント] タブをクリックすると **、50** 番目のパーセントビューの既定のフィルターと同じフィルターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="f64ab-250">メール待機時間レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="f64ab-251">詳細テーブル ビューには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="f64ab-252">**Date**</span><span class="sxs-lookup"><span data-stu-id="f64ab-252">**Date**</span></span>
- <span data-ttu-id="f64ab-253">**パーセント**</span><span class="sxs-lookup"><span data-stu-id="f64ab-253">**Percentiles**</span></span>
- <span data-ttu-id="f64ab-254">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="f64ab-254">**Message count**</span></span>
- <span data-ttu-id="f64ab-255">**全体的な待機時間**</span><span class="sxs-lookup"><span data-stu-id="f64ab-255">**Overall latency**</span></span>

![メール遅延レポートの詳細](../../media/mail-latency-report-details.png)

<span data-ttu-id="f64ab-257">上記の結果、11 月 14 日に配信および削除されたメッセージの平均待機時間は **108.033** 秒でした。</span><span class="sxs-lookup"><span data-stu-id="f64ab-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="f64ab-258">詳細テーブルには、各タブに同じ情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="f64ab-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f64ab-259">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-259">Threat protection status report</span></span>

<span data-ttu-id="f64ab-260">脅威 **保護の状態** レポートは [、Exchange Online Protection](exchange-online-protection-overview.md) (EOP) と Microsoft Defender for Office 365 によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめる単一のビューです。</span><span class="sxs-lookup"><span data-stu-id="f64ab-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f64ab-261">詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="f64ab-262">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-262">URL threat protection report</span></span>

<span data-ttu-id="f64ab-263">**URL 脅威保護レポートには、** 検出された脅威の概要と傾向ビュー、および URL クリックに対するアクションが[リンク] リンクの一部としてセーフ [されます](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="f64ab-264">このレポートには、[リンク] ポリシーが適用されているユーザーセーフクリックデータが含まれる場合は、[ユーザーのクリックを追跡しない]**オプションが** 選択されています。</span><span class="sxs-lookup"><span data-stu-id="f64ab-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="f64ab-265">レポートを表示するには [、Microsoft 365 Defender ポータルを開](https://security.microsoft.com)き、[レポートの電子メール & コラボレーション レポート \>  \> **&]** に移動し **、[URL** 保護レポートの詳細を表示する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f64ab-265">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **URL protection report**.</span></span> <span data-ttu-id="f64ab-266">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="f64ab-266">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![レポート ダッシュボードの URL 保護レポート ウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="f64ab-268">これは保護傾向 *レポートで、* データは大きなデータセットの傾向を表します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="f64ab-269">その結果、集計ビューのデータはここではリアルタイムで使用できませんが、詳細テーブル ビューのデータは使用できないので、2 つのビューの間に若干の不一致が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="f64ab-270">URL 脅威保護レポートのレポート ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="f64ab-271">**URL 脅威保護レポートには**、過去 90 日間のデータを示す 4 時間に 1 回更新される 2 つの集計ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="f64ab-272">**URL クリック保護アクション**: 組織内のユーザーによる URL クリックの数と、クリックの結果を示します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="f64ab-273">**ブロック (** ユーザーが URL への移動をブロックされました)</span><span class="sxs-lookup"><span data-stu-id="f64ab-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="f64ab-274">**ブロックおよびクリックスルー (** ユーザーが URL への引き続き移動を選択しました)</span><span class="sxs-lookup"><span data-stu-id="f64ab-274">**Blocked and clicked through** (the user has chosen to continue navigating to the URL)</span></span>
  - <span data-ttu-id="f64ab-275">**スキャン中にクリックスルー** (ユーザーがスキャンが完了する前にリンクをクリックしました)</span><span class="sxs-lookup"><span data-stu-id="f64ab-275">**Clicked through during scan** (the user has clicked on the link before the scan was complete)</span></span>

  <span data-ttu-id="f64ab-276">クリックすると、ユーザーがブロック ページをクリックして悪意のある Web サイトに移動した (管理者は、[リンク] ポリシーでクリックセーフ無効にできます)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="f64ab-277">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-278">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-279">使用可能なクリック保護アクションと、値 **Allowed** (ユーザーが URL への移動を許可された) を追加します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL 脅威保護レポートの URL クリック保護アクション ビュー](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="f64ab-281">**アプリケーション別 URL クリック**: リンクをサポートするアプリケーション別の URL クリック数セーフします。</span><span class="sxs-lookup"><span data-stu-id="f64ab-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="f64ab-282">**電子メール クライアント**</span><span class="sxs-lookup"><span data-stu-id="f64ab-282">**Email client**</span></span>
  - <span data-ttu-id="f64ab-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="f64ab-283">**PowerPoint**</span></span>
  - <span data-ttu-id="f64ab-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="f64ab-284">**Word**</span></span>
  - <span data-ttu-id="f64ab-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="f64ab-285">**Excel**</span></span>
  - <span data-ttu-id="f64ab-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="f64ab-286">**OneNote**</span></span>
  - <span data-ttu-id="f64ab-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="f64ab-287">**Visio**</span></span>
  - <span data-ttu-id="f64ab-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="f64ab-288">**Teams**</span></span>
  - <span data-ttu-id="f64ab-289">**その他**</span><span class="sxs-lookup"><span data-stu-id="f64ab-289">**Other**</span></span>

  <span data-ttu-id="f64ab-290">[フィルター] **をクリック** すると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="f64ab-291">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="f64ab-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="f64ab-292">使用可能なアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="f64ab-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="f64ab-293">URL 脅威保護レポートの詳細テーブル ビュー</span><span class="sxs-lookup"><span data-stu-id="f64ab-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="f64ab-294">[詳細テーブル **の表示]** をクリックすると、過去 7 日間組織内で発生したすべてのクリックのほぼリアルタイム ビューがレポートに表示されます。詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f64ab-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="f64ab-295">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="f64ab-295">**Click time**</span></span>
- <span data-ttu-id="f64ab-296">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="f64ab-296">**User**</span></span>
- <span data-ttu-id="f64ab-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="f64ab-297">**URL**</span></span>
- <span data-ttu-id="f64ab-298">**Action**</span><span class="sxs-lookup"><span data-stu-id="f64ab-298">**Action**</span></span>
- <span data-ttu-id="f64ab-299">**アプリ**</span><span class="sxs-lookup"><span data-stu-id="f64ab-299">**App**</span></span>

<span data-ttu-id="f64ab-300">詳細テーブル ビュー **で [フィルター** ] をクリックすると、レポート ビューと同じ条件でフィルター処理したり、ドメインまたは受信者をコンマで区切ってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="f64ab-301">[ **ドメイン] フィルター** は、レポートの結果に一覧表示されている URL ドメインを参照します。</span><span class="sxs-lookup"><span data-stu-id="f64ab-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="f64ab-302">レポート ビューに戻る場合は、[レポートの表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f64ab-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="f64ab-303">表示するその他のレポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-303">Additional reports to view</span></span>

<span data-ttu-id="f64ab-304">この記事で説明するレポートに加えて、次の表で説明するように、いくつかの他のレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="f64ab-305">レポート</span><span class="sxs-lookup"><span data-stu-id="f64ab-305">Report</span></span>|<span data-ttu-id="f64ab-306">トピック</span><span class="sxs-lookup"><span data-stu-id="f64ab-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="f64ab-307">**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム検出 **(Microsoft** Defender for Office 365 プラン 1)</span><span class="sxs-lookup"><span data-stu-id="f64ab-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="f64ab-308">脅威エクスプローラー (およびリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="f64ab-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="f64ab-309">**[上位の送信者** と受信者] レポート、スプーフィング メール レポート、スパム検出レポートなどの電子メール セキュリティ レポート。</span><span class="sxs-lookup"><span data-stu-id="f64ab-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="f64ab-310">Defender ポータルで電子メール セキュリティ レポートMicrosoft 365表示する</span><span class="sxs-lookup"><span data-stu-id="f64ab-310">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="f64ab-311">**転送レポート、** メールフロー状態レポート、上位送信者と受信者レポートなどのメール フロー レポート。</span><span class="sxs-lookup"><span data-stu-id="f64ab-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="f64ab-312">Defender ポータルでメール フロー レポートをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="f64ab-312">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="f64ab-313">**[リンク] リンクセーフ URL トレース**(PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="f64ab-314">このコマンドレットの出力には、過去 7 日間セーフリンク アクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="f64ab-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="f64ab-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="f64ab-316">**EOP および Microsoft Defender for Office 365** トラフィックの結果 (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="f64ab-317">このコマンドレットの出力には、ドメイン、日付、イベントの種類、方向、アクション、およびメッセージ数に関する情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="f64ab-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="f64ab-318">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="f64ab-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="f64ab-319">**EOP と Defender のメール詳細レポート (powerShell Office 365)**</span><span class="sxs-lookup"><span data-stu-id="f64ab-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="f64ab-320">このコマンドレットの出力には、悪意のあるファイルまたは URL、フィッシングの試み、偽装、電子メールまたはファイル内のその他の潜在的な脅威に関する詳細が含まれる。</span><span class="sxs-lookup"><span data-stu-id="f64ab-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="f64ab-321">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="f64ab-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="f64ab-322">レポートの Defender を表示するために必要なアクセス許可Office 365ですか?</span><span class="sxs-lookup"><span data-stu-id="f64ab-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="f64ab-323">この記事で説明するレポートを表示して使用するには、Defender ポータルの次のいずれかの役割グループのMicrosoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f64ab-324">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="f64ab-324">**Organization Management**</span></span>
- <span data-ttu-id="f64ab-325">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="f64ab-325">**Security Administrator**</span></span>
- <span data-ttu-id="f64ab-326">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="f64ab-326">**Security Reader**</span></span>
- <span data-ttu-id="f64ab-327">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="f64ab-327">**Global Reader**</span></span>

<span data-ttu-id="f64ab-328">詳細については、「Defender ポータル[のアクセス許可」をMicrosoft 365してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-328">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f64ab-329">**注**: Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="f64ab-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f64ab-330">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f64ab-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f64ab-331">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="f64ab-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f64ab-332">レポートのデータが Defender に表示されない場合Office 365ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f64ab-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f64ab-333">Defender for セーフ[保護](set-up-safe-links-policies.md)を有効セーフするために、[](set-up-safe-attachments-policies.md)組織にリンク ポリシーと添付ファイル Office 365が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f64ab-333">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="f64ab-334">「スパム [対策とマルウェア対策の保護」も参照してください](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f64ab-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f64ab-335">関連項目</span><span class="sxs-lookup"><span data-stu-id="f64ab-335">Related topics</span></span>

[<span data-ttu-id="f64ab-336">Defender ポータルのスマート レポートMicrosoft 365分析情報</span><span class="sxs-lookup"><span data-stu-id="f64ab-336">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f64ab-337">役割のアクセス許可 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f64ab-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
