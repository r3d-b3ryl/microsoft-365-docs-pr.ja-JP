---
title: 高度な脅威保護のレポートを表示する
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
description: セキュリティ/コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用し &amp; ます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4f871432f29138acb8bee3a14b9bb161d87193e3
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2020
ms.locfileid: "48351037"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="339a6-103">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="339a6-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="339a6-104">Office 365 Advanced Threat Protection (ATP) 組織 (たとえば、Microsoft 365 E5 サブスクリプションまたは atp プラン1または ATP プラン2アドオン) には、さまざまなセキュリティ関連のレポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="339a6-105">[必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、**レポート**ダッシュボードにアクセスすることによって、セキュリティ & コンプライアンスセンターでこれらのレポートを表示でき \> **Dashboard**ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="339a6-106">レポートダッシュボードに直接移動するには、を開き <https://protection.office.com/insightdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![セキュリティ & コンプライアンスセンターのレポートダッシュボード](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="339a6-108">Advanced Threat Protection ファイルの種類レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="339a6-109">**Advanced Threat Protection のファイルの種類レポート**レポートには、[安全な添付](atp-safe-attachments.md)ファイルによって悪意のあるファイルとして検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="339a6-110">レポートの集計ビューでは90日間のフィルター処理が可能になりますが、詳細ビューでは10日間のフィルター処理のみが可能です。</span><span class="sxs-lookup"><span data-stu-id="339a6-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="339a6-111">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **Office ATP ファイルの種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="339a6-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="339a6-112">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPFileReport> ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![レポートダッシュボードの Office ATP ファイルの種類ウィジェット](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="339a6-114">このレポートの情報は、 [Advanced Threat Protection メッセージの廃棄レポート](#advanced-threat-protection-message-disposition-report)でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="339a6-115">高度な脅威保護のファイルの種類レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="339a6-116">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-116">The following views are available:</span></span>

- <span data-ttu-id="339a6-117">**データの表示方法: ファイル**: グラフには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="339a6-118">**悪意のある Excel 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="339a6-119">**悪意のあるフラッシュ添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="339a6-120">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="339a6-121">**悪意のある PowerPoint 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="339a6-122">**悪意のある Url**</span><span class="sxs-lookup"><span data-stu-id="339a6-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="339a6-123">**悪意のある Word 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="339a6-124">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="339a6-125">**Others**</span><span class="sxs-lookup"><span data-stu-id="339a6-125">**Others**</span></span>

  <span data-ttu-id="339a6-126">特定の日 (データポイント) にカーソルを移動すると、EOP で [安全な添付](atp-safe-attachments.md) ファイルと [マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="339a6-128">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-129">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-130">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="339a6-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="339a6-131">**データの表示: メッセージ**: グラフには次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="339a6-132">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="339a6-132">**Block access**</span></span>
  - <span data-ttu-id="339a6-133">**置き換えられるメッセージ**</span><span class="sxs-lookup"><span data-stu-id="339a6-133">**Messages replaced**</span></span>
  - <span data-ttu-id="339a6-134">**監視されたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="339a6-134">**Messages monitored**</span></span>
  - <span data-ttu-id="339a6-135">**動的な電子メール配信に置き換え**ます。詳細については、「 [安全な添付ファイルのポリシーでの動的配信](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![ATP ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="339a6-137">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-138">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-139">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="339a6-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="339a6-140">高度な脅威保護のファイルの種類レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="339a6-141">[ **詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="339a6-142">表示される情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="339a6-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="339a6-143">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="339a6-143">**View data by: File**:</span></span>

  - <span data-ttu-id="339a6-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="339a6-144">**Date**</span></span>
  - <span data-ttu-id="339a6-145">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="339a6-145">**Recipient address**</span></span>
  - <span data-ttu-id="339a6-146">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="339a6-146">**Sender address**</span></span>
  - <span data-ttu-id="339a6-147">メッセージ**id**: メッセージヘッダーの**メッセージ id**ヘッダーフィールドで利用可能で、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="339a6-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="339a6-148">値の例を次に示し `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` ます (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="339a6-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="339a6-149">**File**</span><span class="sxs-lookup"><span data-stu-id="339a6-149">**File**</span></span>

  <span data-ttu-id="339a6-150">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-151">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-152">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="339a6-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="339a6-153">**データの表示: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="339a6-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="339a6-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="339a6-154">**Date**</span></span>
  - <span data-ttu-id="339a6-155">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="339a6-155">**Recipient address**</span></span>
  - <span data-ttu-id="339a6-156">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="339a6-156">**Sender address**</span></span>
  - <span data-ttu-id="339a6-157">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="339a6-157">**Message ID**</span></span>
  - <span data-ttu-id="339a6-158">**File**</span><span class="sxs-lookup"><span data-stu-id="339a6-158">**File**</span></span>
  - <span data-ttu-id="339a6-159">**Subject**</span><span class="sxs-lookup"><span data-stu-id="339a6-159">**Subject**</span></span>

  <span data-ttu-id="339a6-160">[ **フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="339a6-161">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-162">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="339a6-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="339a6-163">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="339a6-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="339a6-164">Advanced Threat Protection メッセージの廃棄レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="339a6-165">**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="339a6-166">レポートを表示するには、[セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[**レポート**] ダッシュボードに移動し \> **Dashboard**て、[ **Office ATP メッセージ廃棄**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="339a6-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="339a6-167">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=ATPMessageReport> ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![レポートダッシュボードの Office 365 ATP メッセージ廃棄ウィジェット](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="339a6-169">このレポートの情報は、 [Advanced Threat Protection のファイルの種類レポート](#advanced-threat-protection-file-types-report)でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="339a6-170">Advanced Threat Protection メッセージ廃棄レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="339a6-171">次のビューを利用できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-171">The following views are available:</span></span>

- <span data-ttu-id="339a6-172">**データの表示: メッセージ**: グラフには次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="339a6-173">**アクセスをブロックする**</span><span class="sxs-lookup"><span data-stu-id="339a6-173">**Block access**</span></span>
  - <span data-ttu-id="339a6-174">**置き換えられるメッセージ**</span><span class="sxs-lookup"><span data-stu-id="339a6-174">**Messages replaced**</span></span>
  - <span data-ttu-id="339a6-175">**監視されたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="339a6-175">**Messages monitored**</span></span>
  - <span data-ttu-id="339a6-176">**動的な電子メール配信に置き換え**ます。詳細については、「 [安全な添付ファイルのポリシーでの動的配信](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![ATP ファイルの種類レポートのメッセージビュー](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="339a6-178">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-179">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-180">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="339a6-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="339a6-181">**データの表示方法: ファイル**: グラフには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="339a6-182">**悪意のある Excel 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="339a6-183">**悪意のあるフラッシュ添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="339a6-184">**悪意のある PDF 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="339a6-185">**悪意のある PowerPoint 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="339a6-186">**悪意のある Url**</span><span class="sxs-lookup"><span data-stu-id="339a6-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="339a6-187">**悪意のある Word 添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="339a6-188">**悪意のある実行可能ファイルの添付ファイル**</span><span class="sxs-lookup"><span data-stu-id="339a6-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="339a6-189">**Others**</span><span class="sxs-lookup"><span data-stu-id="339a6-189">**Others**</span></span>

  <span data-ttu-id="339a6-190">特定の日 (データポイント) にカーソルを移動すると、EOP で [安全な添付](atp-safe-attachments.md) ファイルと [マルウェア対策保護](anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![ATP ファイルの種類レポートのファイルビュー](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="339a6-192">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-193">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-194">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="339a6-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="339a6-195">Advanced Threat Protection メッセージ廃棄レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="339a6-196">[ **詳細テーブルの表示**] をクリックすると、過去10日間に組織内で発生したすべてのクリックが、ほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="339a6-197">表示される情報は、表示されていたグラフによって異なります。</span><span class="sxs-lookup"><span data-stu-id="339a6-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="339a6-198">**データの表示: メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="339a6-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="339a6-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="339a6-199">**Date**</span></span>
  - <span data-ttu-id="339a6-200">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="339a6-200">**Recipient address**</span></span>
  - <span data-ttu-id="339a6-201">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="339a6-201">**Sender address**</span></span>
  - <span data-ttu-id="339a6-202">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="339a6-202">**Message ID**</span></span>
  - <span data-ttu-id="339a6-203">**File**</span><span class="sxs-lookup"><span data-stu-id="339a6-203">**File**</span></span>
  - <span data-ttu-id="339a6-204">**Subject**</span><span class="sxs-lookup"><span data-stu-id="339a6-204">**Subject**</span></span>

  <span data-ttu-id="339a6-205">[ **フィルター**] をクリックすると、次のフィルターを使用して結果を変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="339a6-206">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-207">グラフで使用できるものと同じメッセージの廃棄値、および値が **渡さ** れる追加メッセージ。</span><span class="sxs-lookup"><span data-stu-id="339a6-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="339a6-208">**データの表示方法: ファイル**:</span><span class="sxs-lookup"><span data-stu-id="339a6-208">**View data by: File**:</span></span>

  - <span data-ttu-id="339a6-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="339a6-209">**Date**</span></span>
  - <span data-ttu-id="339a6-210">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="339a6-210">**Recipient address**</span></span>
  - <span data-ttu-id="339a6-211">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="339a6-211">**Sender address**</span></span>
  - <span data-ttu-id="339a6-212">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="339a6-212">**Message ID**</span></span>
  - <span data-ttu-id="339a6-213">**File**</span><span class="sxs-lookup"><span data-stu-id="339a6-213">**File**</span></span>

  <span data-ttu-id="339a6-214">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-215">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-216">グラフに表示されているものと同じファイルの種類の値。</span><span class="sxs-lookup"><span data-stu-id="339a6-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="339a6-217">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="339a6-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="339a6-218">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-218">Threat protection status report</span></span>

<span data-ttu-id="339a6-219">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online protection](exchange-online-protection-overview.md) (EOP) および Office 365 ATP によって検出されブロックされます。</span><span class="sxs-lookup"><span data-stu-id="339a6-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="339a6-220">詳細については、「 [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="339a6-221">URL の脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-221">URL threat protection report</span></span>

<span data-ttu-id="339a6-222">**Url 脅威保護レポート**には、検出された脅威の概要と傾向ビュー、および[安全なリンク](atp-safe-links.md)の一部として、URL クリックに対して行われたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="339a6-223">このレポートには、安全なリンクポリシーが適用されているユーザーのクリックデータがありません。 [ユーザーのクリックを **追跡** しない] オプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="339a6-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="339a6-224">レポートを表示するには、 [セキュリティ & コンプライアンスセンター](https://protection.office.com)を開き、[ **レポート** \> **ダッシュボード** ] に移動して、[ **URL 保護レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="339a6-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="339a6-225">レポートに直接移動するには、を開き <https://protection.office.com/reportv2?id=URLProtectionActionReport> ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![レポートダッシュボードの URL 保護レポートウィジェット](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="339a6-227">これは、 *保護傾向レポート*で、データが大きなデータセット内の傾向を表すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="339a6-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="339a6-228">その結果、集計ビュー内のデータはリアルタイムでは使用できませんが、[詳細] テーブルビューのデータは、2つのビューの間に若干の違いがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="339a6-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="339a6-229">URL 脅威保護レポートのレポートビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="339a6-230">**URL 脅威保護**レポートには、過去90日間のデータを表示する4時間ごとに更新される2つの集計ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="339a6-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="339a6-231">**[URL] [保護アクション] をクリック**します。組織内のユーザーによる URL クリック数、およびクリックの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="339a6-232">**ブロック** (ユーザーが URL への移動をブロックされた)</span><span class="sxs-lookup"><span data-stu-id="339a6-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="339a6-233">**ブロックとクリックスルー**</span><span class="sxs-lookup"><span data-stu-id="339a6-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="339a6-234">**スキャン中にクリックでクリック**</span><span class="sxs-lookup"><span data-stu-id="339a6-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="339a6-235">クリックすると、ユーザーが悪意のある web サイトをクリックしたことを示します (管理者は、安全なリンクポリシーでクリックを無効にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="339a6-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="339a6-236">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-237">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-238">利用可能なクリック保護アクションと **許容さ** れる値 (ユーザーが URL への移動を許可されたもの)。</span><span class="sxs-lookup"><span data-stu-id="339a6-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL URL の脅威保護レポートにある [保護アクション表示] をクリックします。](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="339a6-240">**Url [アプリケーション別] をクリック**: 安全なリンクをサポートするアプリケーションによる url クリックの数を表示します。</span><span class="sxs-lookup"><span data-stu-id="339a6-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="339a6-241">**電子メール クライアント**</span><span class="sxs-lookup"><span data-stu-id="339a6-241">**Email client**</span></span>
  - <span data-ttu-id="339a6-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="339a6-242">**PowerPoint**</span></span>
  - <span data-ttu-id="339a6-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="339a6-243">**Word**</span></span>
  - <span data-ttu-id="339a6-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="339a6-244">**Excel**</span></span>
  - <span data-ttu-id="339a6-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="339a6-245">**OneNote**</span></span>
  - <span data-ttu-id="339a6-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="339a6-246">**Visio**</span></span>
  - <span data-ttu-id="339a6-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="339a6-247">**Teams**</span></span>
  - <span data-ttu-id="339a6-248">**その他**</span><span class="sxs-lookup"><span data-stu-id="339a6-248">**Other**</span></span>

  <span data-ttu-id="339a6-249">[ **フィルター**] をクリックすると、次のフィルターを使用してレポートを変更できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="339a6-250">**開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="339a6-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="339a6-251">利用可能なアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="339a6-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="339a6-252">URL 脅威保護レポートの詳細表ビュー</span><span class="sxs-lookup"><span data-stu-id="339a6-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="339a6-253">[ **詳細テーブルの表示**] をクリックすると、このレポートでは、過去7日間の組織内で発生したすべてのクリックが、次のようなほぼリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="339a6-254">**[時刻] をクリック**</span><span class="sxs-lookup"><span data-stu-id="339a6-254">**Click time**</span></span>
- <span data-ttu-id="339a6-255">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="339a6-255">**User**</span></span>
- <span data-ttu-id="339a6-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="339a6-256">**URL**</span></span>
- <span data-ttu-id="339a6-257">**操作**</span><span class="sxs-lookup"><span data-stu-id="339a6-257">**Action**</span></span>
- <span data-ttu-id="339a6-258">**App**</span><span class="sxs-lookup"><span data-stu-id="339a6-258">**App**</span></span>

<span data-ttu-id="339a6-259">詳細テーブルビューで [ **フィルター** ] をクリックすると、レポートビューと同じ条件で、およびコンマで区切られた **ドメイン** または **受信者** によってフィルター処理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="339a6-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="339a6-260">レポートビューに戻るには、[ **レポートの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="339a6-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="339a6-261">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-261">Additional reports to view</span></span>

<span data-ttu-id="339a6-262">このトピックで説明する ATP レポートに加えて、次の表に示すように、他のいくつかのレポートも利用できます。</span><span class="sxs-lookup"><span data-stu-id="339a6-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="339a6-263">レポート</span><span class="sxs-lookup"><span data-stu-id="339a6-263">Report</span></span>|<span data-ttu-id="339a6-264">トピック</span><span class="sxs-lookup"><span data-stu-id="339a6-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="339a6-265">**エクスプローラー** (atp plan 2) または **リアルタイム検出** (atp プラン 1)</span><span class="sxs-lookup"><span data-stu-id="339a6-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="339a6-266">脅威エクスプローラー (およびリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="339a6-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="339a6-267">上位の送信者と受信者レポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="339a6-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="339a6-268">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="339a6-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="339a6-269">転送レポート、メールフロー状態レポート、上位の送信者と受信者レポートなどの**メールフローレポート**。</span><span class="sxs-lookup"><span data-stu-id="339a6-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="339a6-270">セキュリティ & コンプライアンスセンターでメールフローレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="339a6-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="339a6-271">**安全なリンクの URL トレース** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="339a6-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="339a6-272">このコマンドレットの出力では、過去7日間の安全なリンクアクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="339a6-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="339a6-273">取得-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="339a6-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="339a6-274">**EOP および ATP のメールトラフィック結果** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="339a6-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="339a6-275">このコマンドレットの出力には、ドメイン、日付、イベントの種類、方向、アクション、およびメッセージ数に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339a6-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="339a6-276">Get-mailtrafficatpreport</span><span class="sxs-lookup"><span data-stu-id="339a6-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="339a6-277">**EOP および ATP の検出に関するメール詳細レポート** (PowerShell のみ)。</span><span class="sxs-lookup"><span data-stu-id="339a6-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="339a6-278">このコマンドレットの出力には、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="339a6-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="339a6-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="339a6-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="339a6-280">ATP レポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="339a6-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="339a6-281">このトピックで説明されているレポートを表示して使用するには、 **セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="339a6-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="339a6-282">セキュリティ & コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="339a6-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="339a6-283">組織管理</span><span class="sxs-lookup"><span data-stu-id="339a6-283">Organization Management</span></span>
  - <span data-ttu-id="339a6-284">セキュリティ管理者 (Azure Active Directory 管理センターで割り当て [https://aad.portal.azure.com](https://aad.portal.azure.com) 可能)</span><span class="sxs-lookup"><span data-stu-id="339a6-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="339a6-285">Security Operator (Azure Active Directory 管理センター () で割り当てることができます [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="339a6-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="339a6-286">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="339a6-286">Security Reader</span></span>

- <span data-ttu-id="339a6-287">Exchange Online の場合は、Exchange 管理センター ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) または PowerShell コマンドレット (「 [Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="339a6-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="339a6-288">組織の管理</span><span class="sxs-lookup"><span data-stu-id="339a6-288">Organization Management</span></span>
  - <span data-ttu-id="339a6-289">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="339a6-289">View-only Organization Management</span></span>
  - <span data-ttu-id="339a6-290">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="339a6-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="339a6-291">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="339a6-291">Compliance Management</span></span>

<span data-ttu-id="339a6-292">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="339a6-293">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="339a6-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="339a6-294">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="339a6-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="339a6-295">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="339a6-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="339a6-296">ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="339a6-297">組織では、ATP 保護を適用するために、 [安全なリンクポリシー](set-up-atp-safe-links-policies.md) と [安全な添付ファイルポリシー](set-up-atp-safe-attachments-policies.md) が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="339a6-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="339a6-298">また、 [スパム対策とマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)についても参照してください。</span><span class="sxs-lookup"><span data-stu-id="339a6-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="339a6-299">関連項目</span><span class="sxs-lookup"><span data-stu-id="339a6-299">Related topics</span></span>

[<span data-ttu-id="339a6-300">セキュリティ/コンプライアンス センターのスマート レポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="339a6-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="339a6-301">役割のアクセス許可 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="339a6-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
