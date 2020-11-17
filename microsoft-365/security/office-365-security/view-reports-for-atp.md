---
title: Defender for Office 365 のレポートの表示
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: セキュリティ/コンプライアンスセンターの Microsoft Defender for Office 365 のレポートを検索して使用し &amp; ます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8885eea2168cc40c497f6fa1066ae020dda7fd7c
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087720"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="1892f-103">Microsoft Defender for Office 365 のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="1892f-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1892f-104">Microsoft Defender for Office 365 組織 (たとえば、Microsoft 365 E5 サブスクリプションまたは microsoft Defender for office 365 Plan 1 または Microsoft Defender for Office 365 Plan 2 アドオン) には、さまざまなセキュリティ関連のレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="1892f-105">[必要なアクセス許可](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)がある場合は、**レポート** ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard** ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="1892f-106">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="1892f-108">Defender for Office 365 のファイル型レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="1892f-109">「 **Defender For Office 365 ファイルの種類レポート** レポート」には、 [安全な添付ファイル](atp-safe-attachments.md)によって悪意のあるファイルとして検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="1892f-110">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="1892f-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="1892f-111">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート** ダッシュボード] に移動して、 \> **Dashboard** [ **Office 365 ファイルの種類] の [Defender**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1892f-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="1892f-112">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPFileReport> ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![レポートダッシュボードでの Office 365 ファイルの種類ウィジェットの Defender](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1892f-114">このレポートの情報は、 [Defender For Office 365 メッセージ廃棄レポート](#defender-for-office-365-message-disposition-report)でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="1892f-115">Office 365 のファイルタイプレポートのためのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="1892f-116">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-116">The following views are available:</span></span>

- <span data-ttu-id="1892f-117">**データの表示方法: ファイル**: グラフには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1892f-118">**悪意のある Excel 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="1892f-119">**悪意のあるフラッシュ添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="1892f-120">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="1892f-121">**悪意のある PowerPoint 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="1892f-122">**悪意のある Url**</span><span class="sxs-lookup"><span data-stu-id="1892f-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="1892f-123">**悪意のある Word 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="1892f-124">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="1892f-125">**Others**</span><span class="sxs-lookup"><span data-stu-id="1892f-125">**Others**</span></span>

  <span data-ttu-id="1892f-126">特定の日 (データポイント) にカーソルを移動すると、EOP で [安全な添付](atp-safe-attachments.md) ファイルと [マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Defender for Office 365 ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="1892f-128">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-129">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-130">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="1892f-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="1892f-131">**データの表示: メッセージ**: グラフには次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1892f-132">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="1892f-132">**Block access**</span></span>
  - <span data-ttu-id="1892f-133">**置き換えられるメッセージ**</span><span class="sxs-lookup"><span data-stu-id="1892f-133">**Messages replaced**</span></span>
  - <span data-ttu-id="1892f-134">**監視されたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="1892f-134">**Messages monitored**</span></span>
  - <span data-ttu-id="1892f-135">**動的な電子メール配信に置き換え** ます。詳細については、「 [安全な添付ファイルのポリシーでの動的配信](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Defender for Office 365 ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="1892f-137">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-138">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-139">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1892f-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="1892f-140">Office 365 のファイルタイプレポートのための詳細テーブルビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="1892f-141">[ **詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="1892f-142">表示される情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1892f-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1892f-143">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="1892f-143">**View data by: File**:</span></span>

  - <span data-ttu-id="1892f-144">**日付**</span><span class="sxs-lookup"><span data-stu-id="1892f-144">**Date**</span></span>
  - <span data-ttu-id="1892f-145">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="1892f-145">**Recipient address**</span></span>
  - <span data-ttu-id="1892f-146">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="1892f-146">**Sender address**</span></span>
  - <span data-ttu-id="1892f-147">メッセージ **id**: メッセージヘッダーの **メッセージ id** ヘッダーフィールドで利用可能で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1892f-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="1892f-148">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="1892f-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="1892f-149">**File**</span><span class="sxs-lookup"><span data-stu-id="1892f-149">**File**</span></span>

  <span data-ttu-id="1892f-150">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-151">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-152">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="1892f-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="1892f-153">**データの表示: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="1892f-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="1892f-154">**日付**</span><span class="sxs-lookup"><span data-stu-id="1892f-154">**Date**</span></span>
  - <span data-ttu-id="1892f-155">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="1892f-155">**Recipient address**</span></span>
  - <span data-ttu-id="1892f-156">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="1892f-156">**Sender address**</span></span>
  - <span data-ttu-id="1892f-157">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="1892f-157">**Message ID**</span></span>
  - <span data-ttu-id="1892f-158">**File**</span><span class="sxs-lookup"><span data-stu-id="1892f-158">**File**</span></span>
  - <span data-ttu-id="1892f-159">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="1892f-159">**Subject**</span></span>

  <span data-ttu-id="1892f-160">[ **フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="1892f-161">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-162">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1892f-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="1892f-163">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1892f-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1892f-164">Defender for Office 365 のメッセージ処理レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1892f-165">**ATP メッセージディスポジション** レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="1892f-166">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **Defender for Office 365 メッセージの廃棄**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1892f-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="1892f-167">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPMessageReport> ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![レポートダッシュボードの Defender for Office 365 メッセージ廃棄ウィジェット](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1892f-169">このレポートの情報は、 [Defender For Office 365 ファイルの種類レポート](#defender-for-office-365-file-types-report)でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1892f-170">Defender for Office 365 メッセージ廃棄レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1892f-171">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-171">The following views are available:</span></span>

- <span data-ttu-id="1892f-172">**データの表示: メッセージ**: グラフには次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1892f-173">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="1892f-173">**Block access**</span></span>
  - <span data-ttu-id="1892f-174">**置き換えられるメッセージ**</span><span class="sxs-lookup"><span data-stu-id="1892f-174">**Messages replaced**</span></span>
  - <span data-ttu-id="1892f-175">**監視されたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="1892f-175">**Messages monitored**</span></span>
  - <span data-ttu-id="1892f-176">**動的な電子メール配信に置き換え** ます。詳細については、「 [安全な添付ファイルのポリシーでの動的配信](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Defender for Office 365 ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="1892f-178">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-179">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-180">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1892f-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="1892f-181">**データの表示方法: ファイル**: グラフには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="1892f-182">**悪意のある Excel 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="1892f-183">**悪意のあるフラッシュ添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="1892f-184">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="1892f-185">**悪意のある PowerPoint 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="1892f-186">**悪意のある Url**</span><span class="sxs-lookup"><span data-stu-id="1892f-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="1892f-187">**悪意のある Word 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="1892f-188">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="1892f-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="1892f-189">**Others**</span><span class="sxs-lookup"><span data-stu-id="1892f-189">**Others**</span></span>

  <span data-ttu-id="1892f-190">特定の日 (データポイント) にカーソルを移動すると、EOP で [安全な添付](atp-safe-attachments.md) ファイルと [マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Defender for Office 365 ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="1892f-192">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-193">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-194">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="1892f-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="1892f-195">Defender for Office 365 メッセージ廃棄レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="1892f-196">[ **詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="1892f-197">表示される情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1892f-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="1892f-198">**データの表示: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="1892f-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="1892f-199">**日付**</span><span class="sxs-lookup"><span data-stu-id="1892f-199">**Date**</span></span>
  - <span data-ttu-id="1892f-200">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="1892f-200">**Recipient address**</span></span>
  - <span data-ttu-id="1892f-201">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="1892f-201">**Sender address**</span></span>
  - <span data-ttu-id="1892f-202">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="1892f-202">**Message ID**</span></span>
  - <span data-ttu-id="1892f-203">**File**</span><span class="sxs-lookup"><span data-stu-id="1892f-203">**File**</span></span>
  - <span data-ttu-id="1892f-204">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="1892f-204">**Subject**</span></span>

  <span data-ttu-id="1892f-205">[ **フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="1892f-206">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-207">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1892f-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="1892f-208">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="1892f-208">**View data by: File**:</span></span>

  - <span data-ttu-id="1892f-209">**日付**</span><span class="sxs-lookup"><span data-stu-id="1892f-209">**Date**</span></span>
  - <span data-ttu-id="1892f-210">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="1892f-210">**Recipient address**</span></span>
  - <span data-ttu-id="1892f-211">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="1892f-211">**Sender address**</span></span>
  - <span data-ttu-id="1892f-212">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="1892f-212">**Message ID**</span></span>
  - <span data-ttu-id="1892f-213">**File**</span><span class="sxs-lookup"><span data-stu-id="1892f-213">**File**</span></span>

  <span data-ttu-id="1892f-214">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-215">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-216">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="1892f-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="1892f-217">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1892f-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="1892f-218">メール待機時間レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-218">Mail latency report</span></span>

<span data-ttu-id="1892f-219">**メール潜在期間レポート** には、組織内で発生したメール配信および分析待機時間の集約されたビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="1892f-220">サービスのメール配信時間はいくつかの要因によって影響を受け、絶対配信時間を秒単位で指定することは、成功または問題の適切な指標ではないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="1892f-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="1892f-221">1日の配信時間が遅い場合は、別の日の平均配信時間として、またはその逆の場合があります。</span><span class="sxs-lookup"><span data-stu-id="1892f-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="1892f-222">**メール待機時間レポート** は、他のメッセージの監視された配信時間に関する統計データに基づいて、メッセージの配信を限定しようとします。</span><span class="sxs-lookup"><span data-stu-id="1892f-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="1892f-223">**50 パー百分位**: これは、メッセージ配信時間の中央です。</span><span class="sxs-lookup"><span data-stu-id="1892f-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="1892f-224">この値は、平均配信時間と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="1892f-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="1892f-225">**90th 百分位**: これは、メッセージ配信の遅延が大きいことを示します。</span><span class="sxs-lookup"><span data-stu-id="1892f-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="1892f-226">この値を超えて配信するようになるのは、メッセージの10% のみです。</span><span class="sxs-lookup"><span data-stu-id="1892f-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="1892f-227">**99th 百分位**: これは、メッセージ配信の最大待機時間を示します。</span><span class="sxs-lookup"><span data-stu-id="1892f-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="1892f-228">クライアント側とネットワークの待機時間は含まれません。</span><span class="sxs-lookup"><span data-stu-id="1892f-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="1892f-229">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **メール待機時間レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1892f-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="1892f-230">レポートに直接移動するには、を開き <https://protection.office.com/mailLatencyReport?viewid=P50> ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![レポートダッシュボードのメール待機時間レポートウィジェット](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="1892f-232">メール待機時間レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="1892f-233">レポートを開くと、既定で [ **50 パー percentiles** ] タブが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="1892f-234">既定では、このビューには次のフィルターを使用して構成されたグラフが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="1892f-235">**日付**: 過去7日間</span><span class="sxs-lookup"><span data-stu-id="1892f-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="1892f-236">**メッセージビュー**:</span><span class="sxs-lookup"><span data-stu-id="1892f-236">**Message View**:</span></span>
  - <span data-ttu-id="1892f-237">分析メッセージ</span><span class="sxs-lookup"><span data-stu-id="1892f-237">Detonated messages</span></span>

<span data-ttu-id="1892f-238">この図は、次のカテゴリに分類されるメッセージを示しています。</span><span class="sxs-lookup"><span data-stu-id="1892f-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="1892f-239">**メール配信の遅延**</span><span class="sxs-lookup"><span data-stu-id="1892f-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="1892f-240">**分析の待機時間**</span><span class="sxs-lookup"><span data-stu-id="1892f-240">**Detonation latency**</span></span>

<span data-ttu-id="1892f-241">グラフのカテゴリの上にマウスカーソルを移動すると、各カテゴリの待機時間の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![メール待機時間レポート](../../media/mail-latency-report.png)

<span data-ttu-id="1892f-243">レポートビューで [ **フィルター** ] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="1892f-244">すべてのメッセージ</span><span class="sxs-lookup"><span data-stu-id="1892f-244">All messages</span></span>
- <span data-ttu-id="1892f-245">添付ファイルまたは Url を含むメッセージ</span><span class="sxs-lookup"><span data-stu-id="1892f-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="1892f-246">[ **90th percentiles** ] タブまたは [ **99 番目の percentiles** ] タブをクリックすると、 **50 パー percentiles** ビューからの同じ既定のフィルターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="1892f-247">メール待機時間レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="1892f-248">詳細テーブルビューには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="1892f-249">**日付**</span><span class="sxs-lookup"><span data-stu-id="1892f-249">**Date**</span></span>
- <span data-ttu-id="1892f-250">**Percentiles**</span><span class="sxs-lookup"><span data-stu-id="1892f-250">**Percentiles**</span></span>
- <span data-ttu-id="1892f-251">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="1892f-251">**Message count**</span></span>
- <span data-ttu-id="1892f-252">**全体的な待機時間**</span><span class="sxs-lookup"><span data-stu-id="1892f-252">**Overall latency**</span></span>

![メール待機時間レポートの詳細](../../media/mail-latency-report-details.png)

<span data-ttu-id="1892f-254">上記は、配信されたすべてのメッセージに対して発生した平均待機時間 (11 月14日)、分析が **108.033** 秒であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="1892f-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="1892f-255">詳細表には、各タブに同じ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1892f-256">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-256">Threat protection status report</span></span>

<span data-ttu-id="1892f-257">**脅威保護の状態** レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューであり、 [Exchange Online protection](exchange-online-protection-overview.md) (EOP) および Microsoft Defender for Office 365 によって検出されブロックされます。</span><span class="sxs-lookup"><span data-stu-id="1892f-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="1892f-258">詳細については、「 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="1892f-259">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-259">URL threat protection report</span></span>

<span data-ttu-id="1892f-260">**Url 脅威保護レポート** には、検出された脅威の概要と傾向ビュー、および [安全なリンク](atp-safe-links.md)の一部として、URL クリックに対して行われたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="1892f-261">このレポートには、安全なリンクポリシーが適用されているユーザーのクリックデータがありません。 [ユーザーのクリックを **追跡** しない] オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="1892f-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="1892f-262">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **URL 保護レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1892f-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="1892f-263">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=URLProtectionActionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![レポートダッシュボードの URL 保護レポートウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="1892f-265">これは、 *保護傾向レポート* で、データが大きなデータセット内の傾向を表すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1892f-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="1892f-266">その結果、集計ビュー内のデータはリアルタイムでは使用できませんが、[詳細] テーブルビューのデータは、2つのビューの間に若干の違いがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="1892f-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="1892f-267">URL 脅威保護レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="1892f-268">**URL 脅威保護** レポートには、過去90日間のデータを表示する4時間ごとに更新される2つの集計ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="1892f-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="1892f-269">**[URL] [保護アクション] をクリック** します。組織内のユーザーによる URL クリック数、およびクリックの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="1892f-270">**ブロック** (ユーザーが URL への移動をブロックされた)</span><span class="sxs-lookup"><span data-stu-id="1892f-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="1892f-271">**ブロックとクリックスルー**</span><span class="sxs-lookup"><span data-stu-id="1892f-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="1892f-272">**スキャン中にクリックでクリック**</span><span class="sxs-lookup"><span data-stu-id="1892f-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="1892f-273">クリックすると、ユーザーが悪意のある web サイトをクリックしたことを示します (管理者は、安全なリンクポリシーでクリックを無効にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="1892f-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="1892f-274">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-275">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-276">利用可能なクリック保護アクションと **許容さ** れる値 (ユーザーが URL への移動を許可されたもの)。</span><span class="sxs-lookup"><span data-stu-id="1892f-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL URL の脅威保護レポートにある [保護アクション表示] をクリックします。](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="1892f-278">**Url [アプリケーション別] をクリック**: 安全なリンクをサポートするアプリケーションによる url クリックの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="1892f-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="1892f-279">**電子メール クライアント**</span><span class="sxs-lookup"><span data-stu-id="1892f-279">**Email client**</span></span>
  - <span data-ttu-id="1892f-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="1892f-280">**PowerPoint**</span></span>
  - <span data-ttu-id="1892f-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="1892f-281">**Word**</span></span>
  - <span data-ttu-id="1892f-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="1892f-282">**Excel**</span></span>
  - <span data-ttu-id="1892f-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="1892f-283">**OneNote**</span></span>
  - <span data-ttu-id="1892f-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="1892f-284">**Visio**</span></span>
  - <span data-ttu-id="1892f-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="1892f-285">**Teams**</span></span>
  - <span data-ttu-id="1892f-286">**その他**</span><span class="sxs-lookup"><span data-stu-id="1892f-286">**Other**</span></span>

  <span data-ttu-id="1892f-287">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="1892f-288">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="1892f-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="1892f-289">利用可能なアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="1892f-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="1892f-290">URL 脅威保護レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="1892f-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="1892f-291">[ **詳細テーブルの表示**] をクリックすると、このレポートでは、過去7日間の組織内で発生したすべてのクリックが、次のようなほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="1892f-292">**[時刻] をクリック**</span><span class="sxs-lookup"><span data-stu-id="1892f-292">**Click time**</span></span>
- <span data-ttu-id="1892f-293">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="1892f-293">**User**</span></span>
- <span data-ttu-id="1892f-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="1892f-294">**URL**</span></span>
- <span data-ttu-id="1892f-295">**操作**</span><span class="sxs-lookup"><span data-stu-id="1892f-295">**Action**</span></span>
- <span data-ttu-id="1892f-296">**App**</span><span class="sxs-lookup"><span data-stu-id="1892f-296">**App**</span></span>

<span data-ttu-id="1892f-297">詳細テーブルビューで [ **フィルター** ] をクリックすると、レポートビューと同じ条件で、およびコンマで区切られた **ドメイン** または **受信者** によってフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1892f-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="1892f-298">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1892f-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="1892f-299">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-299">Additional reports to view</span></span>

<span data-ttu-id="1892f-300">このトピックで説明されているレポートに加えて、次の表に示すように、他にもいくつかのレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1892f-300">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="1892f-301">レポート</span><span class="sxs-lookup"><span data-stu-id="1892f-301">Report</span></span>|<span data-ttu-id="1892f-302">トピック</span><span class="sxs-lookup"><span data-stu-id="1892f-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="1892f-303">**エクスプローラー** (microsoft Defender for Office 365 プラン 2) または **リアルタイム検出** (microsoft Defender for office 365 プラン 1)</span><span class="sxs-lookup"><span data-stu-id="1892f-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="1892f-304">脅威エクスプローラー (およびリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="1892f-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="1892f-305">上位の送信者と受信者レポート、スプーフィングメールレポート、スパム検出レポートなどの **電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="1892f-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="1892f-306">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="1892f-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="1892f-307">転送レポート、メールフロー状態レポート、上位の送信者と受信者レポートなどの **メールフローレポート**。</span><span class="sxs-lookup"><span data-stu-id="1892f-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="1892f-308">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="1892f-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="1892f-309">**安全なリンクの URL トレース** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="1892f-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="1892f-310">このコマンドレットの出力では、過去7日間の安全なリンクアクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1892f-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="1892f-311">取得-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="1892f-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="1892f-312">**EOP のメールトラフィックの結果と Microsoft Defender For Office 365** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="1892f-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="1892f-313">このコマンドレットの出力には、ドメイン、日付、イベントの種類、方向、アクション、およびメッセージ数に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1892f-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="1892f-314">Get-mailtrafficatpreport</span><span class="sxs-lookup"><span data-stu-id="1892f-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="1892f-315">**EOP および Defender For Office 365 の検出に関するメール詳細レポート** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="1892f-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="1892f-316">このコマンドレットの出力には、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="1892f-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="1892f-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="1892f-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="1892f-318">Office 365 レポートの Defender を表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="1892f-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="1892f-319">このトピックで説明されているレポートを表示して使用するには、 **セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="1892f-319">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="1892f-320">セキュリティ & コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1892f-320">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="1892f-321">組織管理</span><span class="sxs-lookup"><span data-stu-id="1892f-321">Organization Management</span></span>
  - <span data-ttu-id="1892f-322">セキュリティ管理者 (Azure Active Directory 管理センターで割り当て [https://aad.portal.azure.com](https://aad.portal.azure.com) 可能)</span><span class="sxs-lookup"><span data-stu-id="1892f-322">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1892f-323">Security Operator (Azure Active Directory 管理センター () で割り当てることができます [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="1892f-323">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1892f-324">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="1892f-324">Security Reader</span></span>

- <span data-ttu-id="1892f-325">Exchange Online の場合は、Exchange 管理センター ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) または PowerShell コマンドレット (「 [Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1892f-325">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="1892f-326">組織の管理</span><span class="sxs-lookup"><span data-stu-id="1892f-326">Organization Management</span></span>
  - <span data-ttu-id="1892f-327">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="1892f-327">View-only Organization Management</span></span>
  - <span data-ttu-id="1892f-328">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="1892f-328">View-Only Recipients role</span></span>
  - <span data-ttu-id="1892f-329">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="1892f-329">Compliance Management</span></span>

<span data-ttu-id="1892f-330">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-330">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="1892f-331">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="1892f-331">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="1892f-332">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="1892f-332">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1892f-333">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="1892f-333">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1892f-334">Office 365 のレポートに関するデータが Defender に表示されない場合は、ポリシーが正しく設定されていることを再度確認してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-334">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1892f-335">組織には、 [安全なリンクポリシー](set-up-atp-safe-links-policies.md) と [安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md) が定義されている必要があります。これには、Defender for Office 365 protection を適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1892f-335">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="1892f-336">また、 [スパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)についても参照してください。</span><span class="sxs-lookup"><span data-stu-id="1892f-336">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1892f-337">関連項目</span><span class="sxs-lookup"><span data-stu-id="1892f-337">Related topics</span></span>

[<span data-ttu-id="1892f-338">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="1892f-338">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="1892f-339">役割のアクセス許可 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1892f-339">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
