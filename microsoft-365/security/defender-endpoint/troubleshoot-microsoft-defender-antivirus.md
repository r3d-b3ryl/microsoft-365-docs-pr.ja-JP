---
title: Microsoft Defender AV イベントの ID とエラー コード
description: イベントの原因と解決策を調Microsoft Defender ウイルス対策エラーの原因と解決策
keywords: イベント、エラー コード、siem、ログ、トラブルシューティング、wef、Windows イベント転送
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cba7a9d6ed23ac1dc72ef6cbcecfdfc7a0f4c60b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926285"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="103b5-104">Microsoft Defender ウイルス対策ソフトウェアの問題をトラブルシューティングするため、イベント ログとエラー コードをレビューする</span><span class="sxs-lookup"><span data-stu-id="103b5-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="103b5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="103b5-105">**Applies to:**</span></span>

- [<span data-ttu-id="103b5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="103b5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="103b5-107">問題が発生した場合Microsoft Defender ウイルス対策、このトピックの表を検索して、一致する問題と潜在的な解決策を見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="103b5-108">テーブルの一覧:</span><span class="sxs-lookup"><span data-stu-id="103b5-108">The tables list:</span></span>

- <span data-ttu-id="103b5-109">[Microsoft Defender ウイルス対策イベントの ID (](#windows-defender-av-ids)これらは、イベントの両方にWindows 10適用Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="103b5-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="103b5-110">Microsoft Defender ウイルス対策エラー コード</span><span class="sxs-lookup"><span data-stu-id="103b5-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="103b5-111">内部Microsoft Defender ウイルス対策クライアント エラー コード (開発およびテスト中に Microsoft が使用)</span><span class="sxs-lookup"><span data-stu-id="103b5-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="103b5-112">Microsoft Defender for Endpoint のデモ Web サイトにアクセス [して、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能が動作しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="103b5-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="103b5-113">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="103b5-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="103b5-114">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="103b5-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="103b5-115">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="103b5-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="103b5-116">Microsoft Defender ウイルス対策イベントの ID</span><span class="sxs-lookup"><span data-stu-id="103b5-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="103b5-117">Microsoft Defender ウイルス対策ログにイベントのWINDOWSを記録します。</span><span class="sxs-lookup"><span data-stu-id="103b5-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="103b5-118">イベント ログを直接表示するか、サードパーティのセキュリティ情報とイベント管理 (SIEM) ツールがある場合は[、Microsoft Defender ウイルス対策](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids)クライアント イベント ID を使用してエンドポイントから特定のイベントやエラーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="103b5-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="103b5-119">このセクションの表に、メイン イベント MICROSOFT DEFENDER ウイルス対策の一覧を示し、可能な場合は、エラーを修正または解決するための推奨される解決策を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="103b5-120">イベントをMicrosoft Defender ウイルス対策するには</span><span class="sxs-lookup"><span data-stu-id="103b5-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="103b5-121">イベント **ビューアーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="103b5-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="103b5-122">コンソール ツリーで、[アプリケーションとサービス ログ] **、[Microsoft]** の順に展開し、[Windows] を **Windows Defender。**</span><span class="sxs-lookup"><span data-stu-id="103b5-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="103b5-123">[操作] を **ダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="103b5-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="103b5-124">詳細ウィンドウで、個々のイベントの一覧を表示して、イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="103b5-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="103b5-125">イベントをクリックすると、[全般] タブと [詳細] タブの下の下部ウィンドウにイベントに関する特定の **詳細が\*\*\*\*表示** されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="103b5-126">イベント ID: 1000</span><span class="sxs-lookup"><span data-stu-id="103b5-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-127">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="103b5-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-129">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-129">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-130">
<b>マルウェア対策スキャンが開始されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="103b5-131">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-132">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-133">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-133">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-134">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-134">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-135">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-135">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-136">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-137">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-137">Full scan</span></span></li>
<li><span data-ttu-id="103b5-138">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-138">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-139">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-139">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-140">
</dt>
<dt>スキャン リソース: &lt;スキャンされたリソース (ファイル/ディレクトリ/BHO など)。 &gt; </dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-141">イベント ID: 1001</span><span class="sxs-lookup"><span data-stu-id="103b5-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-142">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-144">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-144">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-145">
<b>マルウェア対策スキャンが完了しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-146">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-147">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-148">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-148">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-149">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-149">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-150">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-150">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-151">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-152">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-152">Full scan</span></span></li>
<li><span data-ttu-id="103b5-153">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-153">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-154">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-154">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-155">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>スキャン時間: &lt; スキャンの期間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-156">イベント ID: 1002</span><span class="sxs-lookup"><span data-stu-id="103b5-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-157">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-159">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-159">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-160">
<b>マルウェア対策スキャンは終了する前に停止しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-161">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-162">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-163">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-163">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-164">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-164">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-165">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-165">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-166">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-167">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-167">Full scan</span></span></li>
<li><span data-ttu-id="103b5-168">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-168">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-169">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-169">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-170">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; &amp; lt;ユーザー &gt; </dt>
<dt>スキャン時間: &lt; スキャンの期間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-171">イベント ID: 1003</span><span class="sxs-lookup"><span data-stu-id="103b5-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-172">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-174">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-174">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-175">
<b>マルウェア対策スキャンが一時停止されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-176">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-177">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-178">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-178">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-179">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-179">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-180">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-180">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-181">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-182">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-182">Full scan</span></span></li>
<li><span data-ttu-id="103b5-183">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-183">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-184">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-184">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-185">
</dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-186">イベント ID: 1004</span><span class="sxs-lookup"><span data-stu-id="103b5-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-187">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-189">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-189">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-190">
<b>マルウェア対策スキャンが再開されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-191">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-192">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-193">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-193">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-194">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-194">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-195">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-195">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-196">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-197">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-197">Full scan</span></span></li>
<li><span data-ttu-id="103b5-198">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-198">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-199">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-199">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-200">
</dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-201">イベント ID: 1005</span><span class="sxs-lookup"><span data-stu-id="103b5-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-202">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-204">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-204">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-205">
<b>マルウェア対策スキャンに失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-206">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="103b5-207">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-208">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-208">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-209">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-209">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-210">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-210">Antimalware</span></span></li>
</ul><span data-ttu-id="103b5-211">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-212">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-212">Full scan</span></span></li>
<li><span data-ttu-id="103b5-213">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-213">Quick scan</span></span></li>
<li><span data-ttu-id="103b5-214">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="103b5-214">Customer scan</span></span></li>
</ul><span data-ttu-id="103b5-215">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-216">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-217">ウイルス対策クライアントでエラーが発生し、現在のスキャンが停止しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="103b5-218">クライアント側の問題が原因でスキャンが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="103b5-219">このイベント レコードには、スキャン ID、スキャンの種類 (Microsoft Defender ウイルス対策、スパイウェア対策、マルウェア対策)、スキャン パラメーター、スキャンを開始したユーザー、エラー コード、エラーの説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="103b5-220">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="103b5-221">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="103b5-222">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="103b5-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="103b5-223"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-224">イベント ID: 1006</span><span class="sxs-lookup"><span data-stu-id="103b5-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-225">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-227">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-227">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-228">
<b>マルウェア対策エンジンは、マルウェアや望ましくない可能性のある他のソフトウェアを検出しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-229">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-230">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-231">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-232">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-232">Low</span></span></li>
<li><span data-ttu-id="103b5-233">中</span><span class="sxs-lookup"><span data-stu-id="103b5-233">Moderate</span></span></li>
<li><span data-ttu-id="103b5-234">高</span><span class="sxs-lookup"><span data-stu-id="103b5-234">High</span></span></li>
<li><span data-ttu-id="103b5-235">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-235">Severe</span></span></li>
</ul><span data-ttu-id="103b5-236">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-237">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-237">Unknown</span></span></li>
<li><span data-ttu-id="103b5-238">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-238">Local computer</span></span></li>
<li><span data-ttu-id="103b5-239">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-239">Network share</span></span></li>
<li><span data-ttu-id="103b5-240">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-240">Internet</span></span></li>
<li><span data-ttu-id="103b5-241">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-242">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-243">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-244">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-244">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-245">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-245">Generic</span></span></li>
<li><span data-ttu-id="103b5-246">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-246">Concrete</span></span></li>
<li><span data-ttu-id="103b5-247">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-248">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-249">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-249">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-250">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-250">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-251">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-252">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-253">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-254">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-255">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-256">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-257">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-258">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-259">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-260">UAC </dt> 
<dt>状態: &lt; 状態 &gt; </dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>署名バージョンの
<dt>プロセス: &lt; 定義バージョン &gt; </dt>エンジンのバージョン: マルウェア対策エンジン
<dt> &lt; バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-261">イベント ID : 1007</span><span class="sxs-lookup"><span data-stu-id="103b5-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-262">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-264">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-264">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-265">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションを実行しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-266">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-267">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性のあるソフトウェアからこのコンピューターを保護するための措置を取っています。</span><span class="sxs-lookup"><span data-stu-id="103b5-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="103b5-268">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-269">
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>名: &lt; 脅威 &gt; 名</dt>
<dt>ID: &lt; Threat ID &gt; </dt> 
<dt> Severity: &lt; Severity (次 &gt; に示す場合)</span><span class="sxs-lookup"><span data-stu-id="103b5-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-270">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-270">Low</span></span></li>
<li><span data-ttu-id="103b5-271">中</span><span class="sxs-lookup"><span data-stu-id="103b5-271">Moderate</span></span></li>
<li><span data-ttu-id="103b5-272">高</span><span class="sxs-lookup"><span data-stu-id="103b5-272">High</span></span></li>
<li><span data-ttu-id="103b5-273">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-273">Severe</span></span></li>
</ul><span data-ttu-id="103b5-274">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt> 
<dt>Action: &lt; Action &gt; (アクション): たとえば、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-275">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="103b5-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="103b5-276">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="103b5-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="103b5-277">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="103b5-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="103b5-278">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="103b5-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="103b5-279">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="103b5-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="103b5-280">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="103b5-280">No action: No action</span></span></li>
<li><span data-ttu-id="103b5-281">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="103b5-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="103b5-282">
</dt>
<dt>状態: &lt;Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: マルウェア対策エンジン &lt; バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-283">イベント ID : 1008</span><span class="sxs-lookup"><span data-stu-id="103b5-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-284">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-286">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-286">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-287">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性があるソフトウェアからシステムを保護するためのアクションを実行しようとしたが、アクションは失敗した。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-288">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-289">Microsoft Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="103b5-290">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-291">
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>名: &lt; 脅威 &gt; 名</dt>
<dt>ID: &lt; Threat ID &gt; </dt> 
<dt> Severity: &lt; Severity (次 &gt; に示す場合)</span><span class="sxs-lookup"><span data-stu-id="103b5-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-292">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-292">Low</span></span></li>
<li><span data-ttu-id="103b5-293">中</span><span class="sxs-lookup"><span data-stu-id="103b5-293">Moderate</span></span></li>
<li><span data-ttu-id="103b5-294">高</span><span class="sxs-lookup"><span data-stu-id="103b5-294">High</span></span></li>
<li><span data-ttu-id="103b5-295">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-295">Severe</span></span></li>
</ul><span data-ttu-id="103b5-296">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt> 
<dt> アクション: &lt; アクション &gt; (たとえば、次の操作)</span><span class="sxs-lookup"><span data-stu-id="103b5-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-297">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="103b5-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="103b5-298">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="103b5-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="103b5-299">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="103b5-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="103b5-300">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="103b5-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="103b5-301">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="103b5-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="103b5-302">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="103b5-302">No action: No action</span></span></li>
<li><span data-ttu-id="103b5-303">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="103b5-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="103b5-304">
</dt>
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>状態: &lt;Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: マルウェア対策エンジン &lt; バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-305">イベント ID : 1009</span><span class="sxs-lookup"><span data-stu-id="103b5-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-306">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-308">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-308">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-309">
<b>マルウェア対策プラットフォームは、検疫からアイテムを復元しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-310">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-311">Microsoft Defender ウイルス対策アイテムを検疫から復元しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="103b5-312">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-313">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-314">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-314">Low</span></span></li>
<li><span data-ttu-id="103b5-315">中</span><span class="sxs-lookup"><span data-stu-id="103b5-315">Moderate</span></span></li>
<li><span data-ttu-id="103b5-316">高</span><span class="sxs-lookup"><span data-stu-id="103b5-316">High</span></span></li>
<li><span data-ttu-id="103b5-317">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-317">Severe</span></span></li>
</ul><span data-ttu-id="103b5-318">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>署名のバージョン: &lt; &gt; 定義バージョン</dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-319">イベント ID : 1010</span><span class="sxs-lookup"><span data-stu-id="103b5-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-320">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-322">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-322">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-323">
<b>マルウェア対策プラットフォームでは、検疫からアイテムを復元する必要があります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-324">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-325">Microsoft Defender ウイルス対策アイテムを検疫から復元しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="103b5-326">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-327">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-328">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-328">Low</span></span></li>
<li><span data-ttu-id="103b5-329">中</span><span class="sxs-lookup"><span data-stu-id="103b5-329">Moderate</span></span></li>
<li><span data-ttu-id="103b5-330">高</span><span class="sxs-lookup"><span data-stu-id="103b5-330">High</span></span></li>
<li><span data-ttu-id="103b5-331">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-331">Severe</span></span></li>
</ul><span data-ttu-id="103b5-332">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン &gt; バージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-333">イベント ID: 1011</span><span class="sxs-lookup"><span data-stu-id="103b5-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-334">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-336">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-336">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-337">
<b>マルウェア対策プラットフォームが検疫からアイテムを削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-338">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-339">Microsoft Defender ウイルス対策アイテムを検疫から削除しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="103b5-340">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-341">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-342">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-342">Low</span></span></li>
<li><span data-ttu-id="103b5-343">中</span><span class="sxs-lookup"><span data-stu-id="103b5-343">Moderate</span></span></li>
<li><span data-ttu-id="103b5-344">高</span><span class="sxs-lookup"><span data-stu-id="103b5-344">High</span></span></li>
<li><span data-ttu-id="103b5-345">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-345">Severe</span></span></li>
</ul><span data-ttu-id="103b5-346">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>署名のバージョン: &lt; &gt; 定義バージョン</dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-347">イベント ID : 1012</span><span class="sxs-lookup"><span data-stu-id="103b5-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-348">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-350">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-350">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-351">
<b>マルウェア対策プラットフォームは、検疫からアイテムを削除する必要があります。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-352">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-353">Microsoft Defender ウイルス対策アイテムを検疫から削除しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="103b5-354">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-355">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-356">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-356">Low</span></span></li>
<li><span data-ttu-id="103b5-357">中</span><span class="sxs-lookup"><span data-stu-id="103b5-357">Moderate</span></span></li>
<li><span data-ttu-id="103b5-358">高</span><span class="sxs-lookup"><span data-stu-id="103b5-358">High</span></span></li>
<li><span data-ttu-id="103b5-359">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-359">Severe</span></span></li>
</ul><span data-ttu-id="103b5-360">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン &gt; バージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-361">イベント ID: 1013</span><span class="sxs-lookup"><span data-stu-id="103b5-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-362">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-364">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-364">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-365">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアの履歴を削除しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-366">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-367">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性のあるソフトウェアの履歴が削除されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="103b5-368">
<dt>時間: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-369">イベント ID: 1014</span><span class="sxs-lookup"><span data-stu-id="103b5-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-370">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-372">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="103b5-373">マルウェア対策プラットフォームでは、マルウェアなどの望ましくない可能性があるソフトウェアの履歴を削除する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="103b5-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-374">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-375">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性のあるソフトウェアの履歴を削除しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="103b5-376">
<dt>時間: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-377">イベント ID: 1015</span><span class="sxs-lookup"><span data-stu-id="103b5-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-378">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-380">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-380">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-381">
<b>マルウェア対策プラットフォームが疑わしい動作を検出しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-382">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-383">Microsoft Defender ウイルス対策疑わしい動作が検出されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="103b5-384">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-385">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-386">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-386">Low</span></span></li>
<li><span data-ttu-id="103b5-387">中</span><span class="sxs-lookup"><span data-stu-id="103b5-387">Moderate</span></span></li>
<li><span data-ttu-id="103b5-388">高</span><span class="sxs-lookup"><span data-stu-id="103b5-388">High</span></span></li>
<li><span data-ttu-id="103b5-389">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-389">Severe</span></span></li>
</ul><span data-ttu-id="103b5-390">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-391">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-391">Unknown</span></span></li>
<li><span data-ttu-id="103b5-392">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-392">Local computer</span></span></li>
<li><span data-ttu-id="103b5-393">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-393">Network share</span></span></li>
<li><span data-ttu-id="103b5-394">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-394">Internet</span></span></li>
<li><span data-ttu-id="103b5-395">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-396">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-397">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-398">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-398">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-399">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-399">Generic</span></span></li>
<li><span data-ttu-id="103b5-400">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-400">Concrete</span></span></li>
<li><span data-ttu-id="103b5-401">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-402">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-403">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-403">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-404">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-404">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-405">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-406">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-407">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-408">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-409">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-410">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-411">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-412">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-413">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-414">UAC </dt> 
<dt>状態: &lt; 状態 &gt; </dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>署名
<dt>ID のプロセス: 重大度に一致する列挙。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン &gt; </dt>
<dt>バージョンの [フィ</dt>デリティ ラベル: ターゲット ファイル名
<dt>: ファイル名] &lt; &gt; ファイルの名前。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-415">イベント ID: 1116</span><span class="sxs-lookup"><span data-stu-id="103b5-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-416">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-418">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-418">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-419">
<b>マルウェア対策プラットフォームがマルウェアなどの望ましくない可能性のあるソフトウェアを検出しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-420">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-421">Microsoft Defender ウイルス対策または他の望ましくない可能性のあるソフトウェアが検出されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="103b5-422">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-423">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-424">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-424">Low</span></span></li>
<li><span data-ttu-id="103b5-425">中</span><span class="sxs-lookup"><span data-stu-id="103b5-425">Moderate</span></span></li>
<li><span data-ttu-id="103b5-426">高</span><span class="sxs-lookup"><span data-stu-id="103b5-426">High</span></span></li>
<li><span data-ttu-id="103b5-427">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-427">Severe</span></span></li>
</ul><span data-ttu-id="103b5-428">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-429">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-429">Unknown</span></span></li>
<li><span data-ttu-id="103b5-430">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-430">Local computer</span></span></li>
<li><span data-ttu-id="103b5-431">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-431">Network share</span></span></li>
<li><span data-ttu-id="103b5-432">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-432">Internet</span></span></li>
<li><span data-ttu-id="103b5-433">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-434">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-435">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-436">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-436">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-437">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-437">Generic</span></span></li>
<li><span data-ttu-id="103b5-438">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-438">Concrete</span></span></li>
<li><span data-ttu-id="103b5-439">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-440">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-441">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-441">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-442">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-442">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-443">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-444">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-445">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-446">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-447">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-448">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-449">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-450">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-451">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-452">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>署名バージョンの
<dt>プロセス: &lt; 定義バージョン &gt; </dt>エンジンのバージョン: マルウェア対策エンジン
<dt> &lt; バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-453">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-454">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-454">No action is required.</span></span> <span data-ttu-id="103b5-455">Microsoft Defender ウイルス対策、この脅威に対して定期的なアクションを中断して実行できます。</span><span class="sxs-lookup"><span data-stu-id="103b5-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="103b5-456">脅威を手動で削除する場合は、Microsoft Defender ウイルス対策をクリック<b>します</b>。</span><span class="sxs-lookup"><span data-stu-id="103b5-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-457">イベント ID: 1117</span><span class="sxs-lookup"><span data-stu-id="103b5-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-458">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-460">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-460">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-461">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションを実行しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-462">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-463">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性のあるソフトウェアからこのコンピューターを保護するための措置を取っています。</span><span class="sxs-lookup"><span data-stu-id="103b5-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="103b5-464">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-465">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-466">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-466">Low</span></span></li>
<li><span data-ttu-id="103b5-467">中</span><span class="sxs-lookup"><span data-stu-id="103b5-467">Moderate</span></span></li>
<li><span data-ttu-id="103b5-468">高</span><span class="sxs-lookup"><span data-stu-id="103b5-468">High</span></span></li>
<li><span data-ttu-id="103b5-469">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-469">Severe</span></span></li>
</ul><span data-ttu-id="103b5-470">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-471">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-471">Unknown</span></span></li>
<li><span data-ttu-id="103b5-472">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-472">Local computer</span></span></li>
<li><span data-ttu-id="103b5-473">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-473">Network share</span></span></li>
<li><span data-ttu-id="103b5-474">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-474">Internet</span></span></li>
<li><span data-ttu-id="103b5-475">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-476">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-477">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-478">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-478">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-479">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-479">Generic</span></span></li>
<li><span data-ttu-id="103b5-480">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-480">Concrete</span></span></li>
<li><span data-ttu-id="103b5-481">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-482">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-483">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-483">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-484">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-484">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-485">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-486">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-487">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-488">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-489">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-490">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-491">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-492">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-493">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-494">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="103b5-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-495">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="103b5-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="103b5-496">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="103b5-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="103b5-497">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="103b5-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="103b5-498">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="103b5-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="103b5-499">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="103b5-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="103b5-500">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="103b5-500">No action: No action</span></span></li>
<li><span data-ttu-id="103b5-501">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="103b5-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="103b5-502">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義 &gt; </dt>バージョン エンジンのバージョン
<dt>: &lt; マルウェア対策エンジン &gt; </dt>バージョン NOTE: Microsoft Defender ウイルス対策、Microsoft Security Essentials、悪意のあるソフトウェアの削除ツール、または System Center Endpoint Protection がマルウェアを検出すると、マルウェアが変更された可能性のある次のシステム設定とサービスが復元されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="103b5-503">既定Internet ExplorerまたはMicrosoft Edge設定</span><span class="sxs-lookup"><span data-stu-id="103b5-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="103b5-504">ユーザー アクセス制御の設定</span><span class="sxs-lookup"><span data-stu-id="103b5-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="103b5-505">Chrome の設定</span><span class="sxs-lookup"><span data-stu-id="103b5-505">Chrome settings</span></span></li>
<li><span data-ttu-id="103b5-506">ブート コントロール データ</span><span class="sxs-lookup"><span data-stu-id="103b5-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="103b5-507">Regedit と Task Manager のレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="103b5-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="103b5-508">Windows更新、バックグラウンド インテリジェント転送サービス、およびリモート プロシージャ 通話サービス</span><span class="sxs-lookup"><span data-stu-id="103b5-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="103b5-509">Windowsオペレーティング システム ファイル</span><span class="sxs-lookup"><span data-stu-id="103b5-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="103b5-510">上記のコンテキストは、次のクライアントとサーバーのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="103b5-511">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="103b5-511">Operating system</span></span></th>
<th><span data-ttu-id="103b5-512">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-513">クライアント オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="103b5-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="103b5-514">WindowsVista (Service Pack 1、または Service Pack 2) Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="103b5-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-515">サーバー オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="103b5-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="103b5-516">WindowsServer 2008、Windows Server 2008 R2、Windows Server 2012、およびWindows Server 2016</span><span class="sxs-lookup"><span data-stu-id="103b5-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-517">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-518">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-518">No action is necessary.</span></span> <span data-ttu-id="103b5-519">Microsoft Defender ウイルス対策を削除または検疫した場合。</span><span class="sxs-lookup"><span data-stu-id="103b5-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-520">イベント ID: 1118</span><span class="sxs-lookup"><span data-stu-id="103b5-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-521">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-523">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-523">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-524">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性があるソフトウェアからシステムを保護するためのアクションを実行しようとしたが、アクションは失敗した。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-525">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-526">Microsoft Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときに重大でないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="103b5-527">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-528">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-529">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-529">Low</span></span></li>
<li><span data-ttu-id="103b5-530">中</span><span class="sxs-lookup"><span data-stu-id="103b5-530">Moderate</span></span></li>
<li><span data-ttu-id="103b5-531">高</span><span class="sxs-lookup"><span data-stu-id="103b5-531">High</span></span></li>
<li><span data-ttu-id="103b5-532">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-532">Severe</span></span></li>
</ul><span data-ttu-id="103b5-533">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-534">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-534">Unknown</span></span></li>
<li><span data-ttu-id="103b5-535">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-535">Local computer</span></span></li>
<li><span data-ttu-id="103b5-536">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-536">Network share</span></span></li>
<li><span data-ttu-id="103b5-537">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-537">Internet</span></span></li>
<li><span data-ttu-id="103b5-538">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-539">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-540">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-541">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-541">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-542">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-542">Generic</span></span></li>
<li><span data-ttu-id="103b5-543">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-543">Concrete</span></span></li>
<li><span data-ttu-id="103b5-544">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-545">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-546">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-546">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-547">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-547">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-548">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-549">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-550">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-551">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-552">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-553">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-554">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-555">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-556">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-557">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="103b5-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-558">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="103b5-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="103b5-559">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="103b5-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="103b5-560">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="103b5-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="103b5-561">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="103b5-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="103b5-562">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="103b5-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="103b5-563">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="103b5-563">No action: No action</span></span></li>
<li><span data-ttu-id="103b5-564">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="103b5-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="103b5-565">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン &gt; バージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-566">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-567">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-567">No action is necessary.</span></span> <span data-ttu-id="103b5-568">Microsoft Defender ウイルス対策修復に関連するタスクを完了できなかった場合。</span><span class="sxs-lookup"><span data-stu-id="103b5-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="103b5-569">これは重大なエラーではありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-570">イベント ID: 1119</span><span class="sxs-lookup"><span data-stu-id="103b5-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-571">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-573">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-573">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-574">
<b>マルウェア対策プラットフォームでは、マルウェアなどの望ましくない可能性のあるソフトウェアに対してアクションを実行しようとするときに重大なエラーが発生しました。イベント メッセージには詳細があります。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-575">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-576">Microsoft Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアに対してアクションを実行するときに重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="103b5-577">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="103b5-578">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-579">低い</span><span class="sxs-lookup"><span data-stu-id="103b5-579">Low</span></span></li>
<li><span data-ttu-id="103b5-580">中</span><span class="sxs-lookup"><span data-stu-id="103b5-580">Moderate</span></span></li>
<li><span data-ttu-id="103b5-581">高</span><span class="sxs-lookup"><span data-stu-id="103b5-581">High</span></span></li>
<li><span data-ttu-id="103b5-582">重大</span><span class="sxs-lookup"><span data-stu-id="103b5-582">Severe</span></span></li>
</ul><span data-ttu-id="103b5-583">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-584">不明</span><span class="sxs-lookup"><span data-stu-id="103b5-584">Unknown</span></span></li>
<li><span data-ttu-id="103b5-585">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="103b5-585">Local computer</span></span></li>
<li><span data-ttu-id="103b5-586">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="103b5-586">Network share</span></span></li>
<li><span data-ttu-id="103b5-587">インターネット</span><span class="sxs-lookup"><span data-stu-id="103b5-587">Internet</span></span></li>
<li><span data-ttu-id="103b5-588">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="103b5-589">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="103b5-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="103b5-590">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-591">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="103b5-591">Heuristics</span></span></li>
<li><span data-ttu-id="103b5-592">Generic</span><span class="sxs-lookup"><span data-stu-id="103b5-592">Generic</span></span></li>
<li><span data-ttu-id="103b5-593">コンクリート</span><span class="sxs-lookup"><span data-stu-id="103b5-593">Concrete</span></span></li>
<li><span data-ttu-id="103b5-594">動的署名</span><span class="sxs-lookup"><span data-stu-id="103b5-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="103b5-595">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="103b5-596">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="103b5-596">User: user initiated</span></span></li>
<li><span data-ttu-id="103b5-597">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-597">System: system initiated</span></span></li>
<li><span data-ttu-id="103b5-598">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="103b5-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="103b5-599">IOAV: IE の高速添付ファイルのOutlookと設定が開始されました</span><span class="sxs-lookup"><span data-stu-id="103b5-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="103b5-600">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="103b5-601">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="103b5-602">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="103b5-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="103b5-603">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="103b5-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="103b5-604">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="103b5-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="103b5-605">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="103b5-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="103b5-606">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="103b5-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="103b5-607">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="103b5-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="103b5-608">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="103b5-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="103b5-609">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="103b5-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="103b5-610">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="103b5-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="103b5-611">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="103b5-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="103b5-612">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="103b5-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="103b5-613">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="103b5-613">No action: No action</span></span></li>
<li><span data-ttu-id="103b5-614">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="103b5-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="103b5-615">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン &gt; バージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-616">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-617">クライアントMicrosoft Defender ウイルス対策、重大な問題が原因でこのエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="103b5-618">エンドポイントが保護されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-618">The endpoint might not be protected.</span></span> <span data-ttu-id="103b5-619">エラーの説明を確認し、以下の関連する <b>ユーザー アクションの手順に</b> 従います。</span><span class="sxs-lookup"><span data-stu-id="103b5-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="103b5-620">アクション</span><span class="sxs-lookup"><span data-stu-id="103b5-620">Action</span></span></th>
<th><span data-ttu-id="103b5-621">ユーザー操作</span><span class="sxs-lookup"><span data-stu-id="103b5-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="103b5-622">
<b>削除</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="103b5-623">定義を更新し、削除が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="103b5-624">
<b>クリーン</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="103b5-625">定義を更新し、修復が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="103b5-626">
<b>検疫</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="103b5-627">定義を更新し、ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="103b5-628">
<b>許可する</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="103b5-629">ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="103b5-630">このイベントが続く場合は、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="103b5-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="103b5-631">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="103b5-632">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="103b5-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="103b5-633"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-634">イベント ID: 1120</span><span class="sxs-lookup"><span data-stu-id="103b5-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-635">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-637">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-637">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-638">
<b>Microsoft Defender ウイルス対策リソースのハッシュを誘導しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-639">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-640">Microsoft Defender ウイルス対策は正常な状態で稼働しています。</span><span class="sxs-lookup"><span data-stu-id="103b5-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="103b5-641">
<dt>現在のプラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>の脅威リソース パス: &lt; パス &gt; </dt>
<dt>ハッシュ: &lt; ハッシュ &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="103b5-642"><b>注: このイベントは、次のポリシーが設定されている場合にのみログに <b>記録されます。ThreatFileHashLogging は署名なしです</b>。</span><span class="sxs-lookup"><span data-stu-id="103b5-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-643">イベント ID: 1150</span><span class="sxs-lookup"><span data-stu-id="103b5-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-644">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-646">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-646">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-647">
<b>マルウェア対策プラットフォームが監視プラットフォームに状態を報告する場合、このイベントは、マルウェア対策プラットフォームが実行され、正常な状態にあるかどうかを示します。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-648">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-649">Microsoft Defender ウイルス対策は正常な状態で稼働しています。</span><span class="sxs-lookup"><span data-stu-id="103b5-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="103b5-650">
<dt>プラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>の署名バージョン: &lt; 定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジン バージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-651">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-652">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-652">No action is necessary.</span></span> <span data-ttu-id="103b5-653">クライアントMicrosoft Defender ウイルス対策正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="103b5-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="103b5-654">このイベントは、1 時間単位で報告されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="103b5-655">イベント ID: 1151</span><span class="sxs-lookup"><span data-stu-id="103b5-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-656">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-658">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-658">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-659">
<b>Endpoint Protection正常性レポート (UTC の時刻)</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-660">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-661">ウイルス対策クライアントの正常性レポート。</span><span class="sxs-lookup"><span data-stu-id="103b5-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="103b5-662">
<dt>プラットフォームのバージョン: &lt;&gt;</dt>現在
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>
<dt> &lt; のプラットフォームバージョン エンジンバージョン: マルウェア対策エンジン バージョン ネットワークリアルタイム検査エンジンバージョン: ネットワークリアルタイム検査エンジンバージョン ウイルス対策署名バージョン: ウイルス対策署名バージョン: スパイウェア対策署名バージョン ネットワークリアルタイム検査署名バージョン: ネットワークリアルタイム検査署名バージョン RTP 状態: リアルタイム 保護状態 (有効または無効) OA 状態: On Access 状態 (有効または無効) IOAV 状態: IE ダウンロードと Outlook Express Attachments 状態 (有効または無効) BM 状態: 動作監視状態 (有効または無効) ウイルス対策署名の &gt; </dt>年齢: ウイルス対策署名の年齢 (日)
<dt>&lt; &gt; スパイウェア</dt>対策署名の年齢: スパイウェア対策署名の年齢 (日) 最後のクイック スキャンの時間: 最後のクイック スキャンの年齢
<dt>(日 &lt; &gt; )</dt>最後のフル スキャンの年齢: 最後のフル スキャンの年齢
<dt>(日 &lt; &gt; )</dt>ウイルス対策署名の作成時間
<dt>: ? &lt;ウイルス対策署名の &gt; 作成時間</dt>
<dt>Antispyware 署名の作成時間: ? &lt;スパイウェア対策署名の作成時間 &gt; 最後</dt>
<dt>のクイック スキャンの開始時刻: ? &lt;最後のクイック スキャン &gt; の開始時刻</dt>
<dt>最後のクイック スキャンの終了時刻: ? &lt;最後のクイック &gt; </dt>スキャン終了時刻 最後のクイック スキャン ソース: 最後のクイック スキャン ソース (0 = スキャンは&#39;t が実行され、1 = ユーザーが開始し
<dt> &lt; &gt; 、2 =</dt>システムが開始されました) 最後のフル スキャン開始
<dt>時刻: &lt;最後のフル スキャン &gt; の開始時刻</dt>
<dt>最後のフル スキャンの終了時刻: ? &lt;最後のフル &gt; </dt>スキャン終了時刻 最後のフル スキャン ソース: 最後のフル スキャン ソース (0 = スキャンは&#39;t が実行されました、1 = ユーザーが開始
<dt> &lt; &gt; 、2 =</dt>システムが開始) 製品の状態: 内部トラブルシューティングの 
<dt> 場合</span><span class="sxs-lookup"><span data-stu-id="103b5-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="103b5-663">
<th colspan="2">イベント ID: 2000</span><span class="sxs-lookup"><span data-stu-id="103b5-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-664">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-666">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-666">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-667">
<b>マルウェア対策の定義が正常に更新されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-668">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-669">ウイルス対策署名のバージョンが更新されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="103b5-670">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>以前の署名バージョン: &lt; &gt; 以前の</dt>署名バージョン 
<dt> の署名の種類: &lt; 署名の &gt; 種類 、たとえば、</span><span class="sxs-lookup"><span data-stu-id="103b5-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="103b5-671">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-671">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-672">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-672">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-673">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-673">Antimalware</span></span></li>
<li><span data-ttu-id="103b5-674">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-675">
</dt>
<dt>更新プログラムの種類: &lt;更新の種類 &gt; (Full または Delta)。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>現在のエンジンのバージョン: &lt; 現在のエンジンバージョン &gt; </dt>
<dt>以前のエンジンバージョン: &lt; 以前のエンジンバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-676">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-677">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-677">No action is necessary.</span></span> <span data-ttu-id="103b5-678">クライアントMicrosoft Defender ウイルス対策正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="103b5-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="103b5-679">このイベントは、署名が正常に更新されると報告されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-680">イベント ID: 2001</span><span class="sxs-lookup"><span data-stu-id="103b5-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-681">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-683">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-683">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-684">
<b>セキュリティ インテリジェンスの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-685">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-686">Microsoft Defender ウイルス対策更新中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="103b5-687">
<dt>新しいセキュリティ インテリジェンスのバージョン: &lt;新しいバージョン &gt; 番号</dt>
<dt>以前のセキュリティ インテリジェンス のバージョン: &lt; 以前のバージョン &gt; </dt>の更新元: 
<dt> &lt; 更新プログラム &gt; のソースは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-688">セキュリティ インテリジェンス更新フォルダー</span><span class="sxs-lookup"><span data-stu-id="103b5-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="103b5-689">内部セキュリティ インテリジェンス更新サーバー</span><span class="sxs-lookup"><span data-stu-id="103b5-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="103b5-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="103b5-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="103b5-691">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="103b5-691">File share</span></span></li>
<li><span data-ttu-id="103b5-692">Microsoft マルウェア プロテクション センター (MMPC)</span><span class="sxs-lookup"><span data-stu-id="103b5-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="103b5-693">
</dt>
<dt>更新ステージ: &lt; 更新ステージ &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="103b5-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-694">検索</span><span class="sxs-lookup"><span data-stu-id="103b5-694">Search</span></span></li>
<li><span data-ttu-id="103b5-695">ダウンロード</span><span class="sxs-lookup"><span data-stu-id="103b5-695">Download</span></span></li>
<li><span data-ttu-id="103b5-696">インストール</span><span class="sxs-lookup"><span data-stu-id="103b5-696">Install</span></span></li>
</ul><span data-ttu-id="103b5-697">
</dt>ソース パス: ユニバーサル名前付け規則 (UNC) のファイル共有名、Windows Server Update Services 
<dt>(WSUS)/Microsoft Update/ADL のサーバー名。</dt> 
<dt>署名の種類: &lt; 次に示す &gt; 署名の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="103b5-698">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-698">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-699">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-699">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-700">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-700">Antimalware</span></span></li>
<li><span data-ttu-id="103b5-701">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-702">
</dt>
<dt>更新プログラムの種類: &lt;更新の種類 &gt; (Full または Delta)。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>現在のエンジンのバージョン: &lt; &gt; 現在</dt>のエンジンバージョン 以前のエンジンバージョン
<dt> &lt; &gt; :</dt>以前のエンジンバージョン エラー コード: エラー コード 脅威の状態
<dt> &lt; &gt; に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-703">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-704">このエラーは、定義の更新に問題がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="103b5-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="103b5-705">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="103b5-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a> 、エンドポイントで直接再スキャンを強制します。</span><span class="sxs-lookup"><span data-stu-id="103b5-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="103b5-707">このエラーの詳細については、%Windir%\WindowsUpdate.log ファイルのエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="103b5-708"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-709">イベント ID: 2002</span><span class="sxs-lookup"><span data-stu-id="103b5-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-710">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-712">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-712">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-713">
<b>マルウェア対策エンジンが正常に更新されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-714">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-715">Microsoft Defender ウイルス対策エンジンのバージョンが更新されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="103b5-716">
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt>
<dt>以前の &lt; &gt; エンジン バージョン:</dt>以前のエンジン バージョン エンジンの種類: エンジンの種類 、マルウェア対策
<dt>エンジンまたはネットワーク検査システム &lt; &gt; エンジンのいずれか。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-717">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-718">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-718">No action is necessary.</span></span> <span data-ttu-id="103b5-719">クライアントMicrosoft Defender ウイルス対策正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="103b5-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="103b5-720">このイベントは、マルウェア対策エンジンが正常に更新されると報告されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-721">イベント ID: 2003</span><span class="sxs-lookup"><span data-stu-id="103b5-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-722">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-724">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-724">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-725">
<b>マルウェア対策エンジンの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-726">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-727">Microsoft Defender ウイルス対策更新中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="103b5-728">
<dt>新しいエンジンバージョン:</dt>
<dt>以前のエンジン バージョン: &lt; &gt; </dt>以前のエンジン バージョン エンジンの種類: エンジンの種類 、マルウェア対策
<dt>エンジンまたはネットワーク検査システム &lt; &gt; エンジンのいずれか。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-729">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-730">クライアントMicrosoft Defender ウイルス対策が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="103b5-731">このイベントは、クライアントが更新自体に失敗した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="103b5-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="103b5-732">このイベントは、通常、更新中にネットワーク接続が中断された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="103b5-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="103b5-733">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="103b5-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a> 、エンドポイントで直接再スキャンを強制します。</span><span class="sxs-lookup"><span data-stu-id="103b5-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="103b5-735"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-736">イベント ID: 2004</span><span class="sxs-lookup"><span data-stu-id="103b5-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-737">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-739">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-739">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-740">
<b>マルウェア対策定義の読み込み中に問題が発生しました。マルウェア対策エンジンは、最後に知られている一連の定義の読み込みを試みます。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-741">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-742">Microsoft Defender ウイルス対策を読み込もうとするとエラーが発生し、既知の良い一連の署名に戻そうとします。</span><span class="sxs-lookup"><span data-stu-id="103b5-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="103b5-743">
<dt>署名の試行: エラー</dt>
<dt>コード: エラー コード &lt; &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-744">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-745">クライアントMicrosoft Defender ウイルス対策最新の定義ファイルのダウンロードとインストールを試み、失敗しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="103b5-746">このエラーは、定義の読み込み中にクライアントがエラーを検出した場合、またはファイルが破損している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="103b5-747">Microsoft Defender ウイルス対策は、既知の良い定義セットに戻す試みです。</span><span class="sxs-lookup"><span data-stu-id="103b5-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="103b5-748">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="103b5-749">コンピューターを再起動し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="103b5-750">サイトから最新の定義<a href="https://aka.ms/wdsi">をMicrosoft セキュリティ インテリジェンスします</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="103b5-751">注: サイトからダウンロードされる定義ファイルのサイズは 60 MB を超える場合があります。定義を更新するための長期的なソリューションとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="103b5-752"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-753">イベント ID: 2005</span><span class="sxs-lookup"><span data-stu-id="103b5-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-754">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-756">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-756">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-757">
<b>マルウェア対策プラットフォームが最新ではないので、マルウェア対策エンジンの読み込みに失敗しました。マルウェア対策プラットフォームは、最後に知られている優れたマルウェア対策エンジンを読み込み、更新を試みる。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-758">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-759">Microsoft Defender ウイルス対策プラットフォームのバージョンがサポートされていないため、マルウェア対策エンジンを読み込めない場合があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="103b5-760">Microsoft Defender ウイルス対策既知のエンジンに戻り、プラットフォームの更新が試行されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="103b5-761">
<dt>現在のプラットフォームのバージョン: &lt; 現在のプラットフォームのバージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-762">イベント ID: 2006</span><span class="sxs-lookup"><span data-stu-id="103b5-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-763">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-765">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-765">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-766">
<b>プラットフォームの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-767">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-768">Microsoft Defender ウイルス対策を更新しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="103b5-769">
<dt>現在のプラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>のエラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-770">イベント ID: 2007</span><span class="sxs-lookup"><span data-stu-id="103b5-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-771">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-773">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-773">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-774">
<b>プラットフォームは間もなく更新されます。最新の保護を維持するために最新のプラットフォームをダウンロードします。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-775">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-776">Microsoft Defender ウイルス対策、マルウェア対策エンジンの将来のバージョンをサポートするために、新しいプラットフォーム バージョンがすぐに必要になります。</span><span class="sxs-lookup"><span data-stu-id="103b5-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="103b5-777">最新のセキュリティ Microsoft Defender ウイルス対策をダウンロードして、利用可能な最高レベルの保護を維持します。</span><span class="sxs-lookup"><span data-stu-id="103b5-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="103b5-778">
<dt>現在のプラットフォームのバージョン: &lt; 現在のプラットフォームのバージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-779">イベント ID: 2010</span><span class="sxs-lookup"><span data-stu-id="103b5-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-780">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-782">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-782">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-783">
<b>マルウェア対策エンジンは、動的署名サービスを使用して追加の定義を取得しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-784">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-785">Microsoft Defender ウイルス対策動的<i>署名サービスを使用して</i>、コンピューターの保護に役立つ追加の署名を取得しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="103b5-786">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="103b5-787">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-787">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-788">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-788">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-789">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-789">Antimalware</span></span></li>
<li><span data-ttu-id="103b5-790">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-791">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt> 
<dt> の動的署名の種類: &lt; 動的署名の &gt; 種類は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-792">バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-792">Version</span></span></li>
<li><span data-ttu-id="103b5-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-793">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-794">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-794">No limit</span></span></li>
<li><span data-ttu-id="103b5-795">期間</span><span class="sxs-lookup"><span data-stu-id="103b5-795">Duration</span></span></li>
</ul><span data-ttu-id="103b5-796">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="103b5-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-797">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-797">VDM version</span></span></li>
<li><span data-ttu-id="103b5-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-798">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-799">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-799">No limit</span></span></li>
</ul><span data-ttu-id="103b5-800">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-801">イベント ID : 2011</span><span class="sxs-lookup"><span data-stu-id="103b5-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-802">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-804">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-804">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-805">
<b>動的署名サービスは、古い動的定義を削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-806">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-807">Microsoft Defender ウイルス対策使用<i>して、古い</i>署名を破棄しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="103b5-808">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="103b5-809">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-809">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-810">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-810">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-811">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-811">Antimalware</span></span></li>
<li><span data-ttu-id="103b5-812">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-813">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt> 
<dt> の動的署名の種類: &lt; 動的署名の &gt; 種類は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-814">バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-814">Version</span></span></li>
<li><span data-ttu-id="103b5-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-815">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-816">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-816">No limit</span></span></li>
<li><span data-ttu-id="103b5-817">期間</span><span class="sxs-lookup"><span data-stu-id="103b5-817">Duration</span></span></li>
</ul><span data-ttu-id="103b5-818">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>
<dt> &lt; &gt; Dynamic Signature Compilation Timestamp:</dt>Timestamp Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="103b5-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-819">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-819">VDM version</span></span></li>
<li><span data-ttu-id="103b5-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-820">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-821">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-821">No limit</span></span></li>
</ul><span data-ttu-id="103b5-822">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-823">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-824">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-824">No action is necessary.</span></span> <span data-ttu-id="103b5-825">クライアントMicrosoft Defender ウイルス対策正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="103b5-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="103b5-826">このイベントは、動的署名サービスが古い動的定義を正常に削除すると報告されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-827">イベント ID: 2012</span><span class="sxs-lookup"><span data-stu-id="103b5-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-828">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-830">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-830">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-831">
<b>動的署名サービスを使用しようとするときに、マルウェア対策エンジンでエラーが発生しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-832">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-833">Microsoft Defender ウイルス対策署名サービスを使用しようとしてエラー<i>が発生しました</i>。</span><span class="sxs-lookup"><span data-stu-id="103b5-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="103b5-834">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="103b5-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="103b5-835">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="103b5-835">Antivirus</span></span></li>
<li><span data-ttu-id="103b5-836">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-836">Antispyware</span></span></li>
<li><span data-ttu-id="103b5-837">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="103b5-837">Antimalware</span></span></li>
<li><span data-ttu-id="103b5-838">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-839">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt>
<dt>のエラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt> 
<dt>動的署名の種類: &lt; 動的署名の種類 &gt; は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-840">バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-840">Version</span></span></li>
<li><span data-ttu-id="103b5-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-841">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-842">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-842">No limit</span></span></li>
<li><span data-ttu-id="103b5-843">期間</span><span class="sxs-lookup"><span data-stu-id="103b5-843">Duration</span></span></li>
</ul><span data-ttu-id="103b5-844">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="103b5-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-845">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="103b5-845">VDM version</span></span></li>
<li><span data-ttu-id="103b5-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="103b5-846">Timestamp</span></span></li>
<li><span data-ttu-id="103b5-847">制限なし</span><span class="sxs-lookup"><span data-stu-id="103b5-847">No limit</span></span></li>
</ul><span data-ttu-id="103b5-848">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-849">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-850">インターネット接続の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-851">イベント ID: 2013</span><span class="sxs-lookup"><span data-stu-id="103b5-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-852">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-854">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-854">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-855">
<b>動的署名サービスは、すべての動的定義を削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-856">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-857">Microsoft Defender ウイルス対策、<i>すべての動的署名サービスの署名を</i>破棄しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="103b5-858">
<dt>現在の署名バージョン: &lt; 現在の署名バージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-859">イベント ID: 2020</span><span class="sxs-lookup"><span data-stu-id="103b5-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-860">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-862">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-862">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-863">
<b>マルウェア対策エンジンがクリーン ファイルをダウンロードしました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-864">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-865">Microsoft Defender ウイルス対策ファイルをダウンロードしました。</span><span class="sxs-lookup"><span data-stu-id="103b5-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="103b5-866">
<dt>ファイル名: &lt;ファイル名 &gt; ファイルの名前。</dt>
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>現在のエンジンのバージョン: &lt; 現在のエンジンのバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-867">イベント ID: 2021</span><span class="sxs-lookup"><span data-stu-id="103b5-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-868">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-870">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-870">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-871">
<b>マルウェア対策エンジンがクリーン ファイルのダウンロードに失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-872">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-873">Microsoft Defender ウイルス対策ファイルをダウンロードしようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="103b5-874">
<dt>ファイル名: &lt;ファイル名 &gt; ファイルの名前。</dt>
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>現在のエンジンバージョン: 現在の &lt; エンジンバージョン &gt; </dt>エラー コード: エラー コード 脅威の状態
<dt> &lt; &gt; に関連付けられている結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-875">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-876">インターネット接続の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="103b5-877">動的Microsoft Defender ウイルス対策サービスを使用して特定の脅威に最新の定義をダウンロードするときに、クライアントでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="103b5-878">このエラーは、ネットワーク接続の問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-879">イベント ID: 2030</span><span class="sxs-lookup"><span data-stu-id="103b5-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-880">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-882">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-882">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-883">
<b>マルウェア対策エンジンがダウンロードされ、次のシステム再起動時にオフラインで実行するように構成されています。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-884">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-885">Microsoft Defender ウイルス対策再起動時に実行するようにオフライン ウイルス対策をダウンロードして構成します。</span><span class="sxs-lookup"><span data-stu-id="103b5-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-886">イベント ID: 2031</span><span class="sxs-lookup"><span data-stu-id="103b5-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-887">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-889">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-889">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-890">
<b>マルウェア対策エンジンがオフライン スキャンをダウンロードして構成できなかった。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-891">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-892">Microsoft Defender ウイルス対策ウイルス対策をダウンロードして構成しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="103b5-893">
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-894">イベント ID: 2040</span><span class="sxs-lookup"><span data-stu-id="103b5-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-895">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-897">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-897">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-898">
<b>このオペレーティング システムバージョンのマルウェア対策のサポートは間もなく終了します。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-899">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-900">オペレーティング システムのサポートはまもなく期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="103b5-901">サポートMicrosoft Defender ウイルス対策を実行する方法は、脅威から保護するための適切なソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-902">イベント ID : 2041</span><span class="sxs-lookup"><span data-stu-id="103b5-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-903">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-905">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-905">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-906">
<b>このオペレーティング システムのマルウェア対策のサポートは終了しました。継続的なサポートのためにオペレーティング システムをアップグレードする必要があります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-907">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-908">オペレーティング システムのサポートが期限切れです。</span><span class="sxs-lookup"><span data-stu-id="103b5-908">The support for your operating system has expired.</span></span> <span data-ttu-id="103b5-909">サポートMicrosoft Defender ウイルス対策を実行する方法は、脅威から保護するための適切なソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="103b5-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-910">イベント ID: 2042</span><span class="sxs-lookup"><span data-stu-id="103b5-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-911">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-913">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-913">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-914">
<b>マルウェア対策エンジンは、このオペレーティング システムをサポートしなくなったので、システムをマルウェアから保護しなくなりました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-915">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-916">オペレーティング システムのサポートが期限切れです。</span><span class="sxs-lookup"><span data-stu-id="103b5-916">The support for your operating system has expired.</span></span> <span data-ttu-id="103b5-917">Microsoft Defender ウイルス対策システムではサポートされなくなったり、機能が停止し、マルウェアの脅威から保護されていません。</span><span class="sxs-lookup"><span data-stu-id="103b5-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-918">イベント ID: 3002</span><span class="sxs-lookup"><span data-stu-id="103b5-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-919">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-921">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-921">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-922">
<b>リアルタイム保護でエラーが発生し、失敗しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-923">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-924">Microsoft Defender ウイルス対策 Real-Time保護機能でエラーが発生し、失敗しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="103b5-925">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="103b5-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-926">On Access</span><span class="sxs-lookup"><span data-stu-id="103b5-926">On Access</span></span></li>
<li><span data-ttu-id="103b5-927">Internet Explorerダウンロードと Microsoft Outlook Express 添付ファイル</span><span class="sxs-lookup"><span data-stu-id="103b5-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="103b5-928">動作の監視</span><span class="sxs-lookup"><span data-stu-id="103b5-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="103b5-929">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-930">
</dt>
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>理由: リアルタイムMicrosoft Defender ウイルス対策機能が再起動された理由。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-931">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-932">システムが一時保護されていない可能性&#39;、システムを再起動してからフル スキャンを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="103b5-933">クライアントMicrosoft Defender ウイルス対策の&#39;、サービスの 1 つが開始できなかったため、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="103b5-934">その後に 3007 イベント ID が続く場合、エラーは一時的なもので、マルウェア対策クライアントはエラーから回復しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-935">イベント ID: 3007</span><span class="sxs-lookup"><span data-stu-id="103b5-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-936">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-938">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-938">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-939">
<b>障害から回復されたリアルタイム保護。このエラーが表示された場合は、完全なシステム スキャンを実行することをお勧めします。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-940">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-941">Microsoft Defender ウイルス対策リアルタイム保護が機能を再起動しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="103b5-942">完全なシステム スキャンを実行して、このエージェントがダウンしている間に見つからない可能性があるアイテムを検出してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="103b5-943">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="103b5-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-944">On Access</span><span class="sxs-lookup"><span data-stu-id="103b5-944">On Access</span></span></li>
<li><span data-ttu-id="103b5-945">IE のダウンロードとOutlook Express の添付ファイル</span><span class="sxs-lookup"><span data-stu-id="103b5-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="103b5-946">動作の監視</span><span class="sxs-lookup"><span data-stu-id="103b5-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="103b5-947">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-948">
</dt>
<dt>理由: リアルタイムMicrosoft Defender ウイルス対策機能が再起動された理由。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-949">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-950">リアルタイム保護機能が再起動されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="103b5-951">このイベントが再度発生した場合は <a href="https://go.microsoft.com/fwlink/?LinkId=215491">、Microsoft テクニカル サポートにお問い合わせください</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-952">イベント ID: 5000</span><span class="sxs-lookup"><span data-stu-id="103b5-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-953">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-955">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-955">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-956">
<b>リアルタイム保護が有効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-957">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-958">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性のあるソフトウェアのリアルタイム保護スキャンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="103b5-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-959">イベント ID: 5001</span><span class="sxs-lookup"><span data-stu-id="103b5-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-960">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-962">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-962">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-963">
<b>リアルタイム保護は無効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-964">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-965">Microsoft Defender ウイルス対策、マルウェアなどの望ましくない可能性があるソフトウェアのリアルタイム保護スキャンが無効になりました。</span><span class="sxs-lookup"><span data-stu-id="103b5-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-966">イベント ID: 5004</span><span class="sxs-lookup"><span data-stu-id="103b5-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-967">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-969">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-969">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-970">
<b>リアルタイムの保護構成が変更されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-971">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-972">Microsoft Defender ウイルス対策保護機能の構成が変更されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="103b5-973">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="103b5-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="103b5-974">On Access</span><span class="sxs-lookup"><span data-stu-id="103b5-974">On Access</span></span></li>
<li><span data-ttu-id="103b5-975">IE のダウンロードとOutlook Express の添付ファイル</span><span class="sxs-lookup"><span data-stu-id="103b5-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="103b5-976">動作の監視</span><span class="sxs-lookup"><span data-stu-id="103b5-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="103b5-977">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="103b5-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="103b5-978">
</dt>
<dt>構成: </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-979">イベント ID: 5007</span><span class="sxs-lookup"><span data-stu-id="103b5-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-980">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-982">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-982">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-983">
<b>マルウェア対策プラットフォームの構成が変更されました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-984">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-985">Microsoft Defender ウイルス対策が変更されました。</span><span class="sxs-lookup"><span data-stu-id="103b5-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="103b5-986">予期しないイベントの場合は、マルウェアの結果である可能性がある設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="103b5-987">
<dt>古い値: &lt;古い値番号 &gt; 古いウイルス対策構成の値。</dt>
<dt>新しい値: &lt;新しい値の番号 &gt; 新しいウイルス対策構成の値。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-988">イベント ID: 5008</span><span class="sxs-lookup"><span data-stu-id="103b5-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-989">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-991">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-991">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-992">
<b>マルウェア対策エンジンでエラーが発生し、失敗しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-993">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-994">Microsoft Defender ウイルス対策エラーが原因でエンジンが終了しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="103b5-995">
<dt>エラーの種類: &lt;エラーの &gt; 種類 、たとえば:クラッシュまたは</dt>ハング例外
<dt>コード: &lt; エラー コード &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-996">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-997">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="103b5-998">サービスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="103b5-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="103b5-999">マルウェア対策、ウイルス対策、スパイウェアの場合は、管理者特権でコマンド プロンプトに <b>「net stop msmpsvc」</b>と入力し <b>、「net start msmpsvc」</b> と入力してマルウェア対策エンジンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="103b5-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="103b5-1000">ネットワーク検査<i></i>システムの場合は、管理者特権でコマンド プロンプトに<b>「net start nissrv」</b>と入力し、「net start <i></i> <b>nissrv」</b>と入力して、NiSSRV.exe ファイルを使用してネットワーク検査システム エンジンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="103b5-1001">同じ方法でエラーが発生した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft</a>サポート サイトにアクセスし、[検索] ボックスにエラー番号<b></b>を入力してエラー コードを検索し、Microsoft テクニカル サポートにお<a href="https://go.microsoft.com/fwlink/?LinkId=215491">問い合わせください</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1002">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="103b5-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1003">予期Microsoft Defender ウイルス対策により、クライアント エンジンが停止しました。</span><span class="sxs-lookup"><span data-stu-id="103b5-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="103b5-1004">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="103b5-1005">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="103b5-1006">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="103b5-1007"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="103b5-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1008">イベント ID: 5009</span><span class="sxs-lookup"><span data-stu-id="103b5-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1009">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1011">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1012">
<b>マルウェアなどの望ましくない可能性があるソフトウェアのスキャンが有効になります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1013">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1014">Microsoft Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアのスキャンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="103b5-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1015">イベント ID: 5010</span><span class="sxs-lookup"><span data-stu-id="103b5-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1016">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1018">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1019">
<b>マルウェアなどの望ましくない可能性があるソフトウェアのスキャンが無効になります。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1020">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1021">Microsoft Defender ウイルス対策その他の望ましくない可能性のあるソフトウェアのスキャンが無効になります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1022">イベント ID: 5011</span><span class="sxs-lookup"><span data-stu-id="103b5-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1023">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1025">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1026">
<b>ウイルスのスキャンが有効になっています。</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1027">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1028">Microsoft Defender ウイルス対策スキャンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="103b5-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1029">イベント ID: 5012</span><span class="sxs-lookup"><span data-stu-id="103b5-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1030">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1032">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1033">
<b>ウイルスのスキャンは無効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1034">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1035">Microsoft Defender ウイルス対策スキャンが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="103b5-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1036">イベント ID: 5100</span><span class="sxs-lookup"><span data-stu-id="103b5-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1037">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1039">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1040">
<b>マルウェア対策プラットフォームは間もなく期限切れになります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1041">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1042">Microsoft Defender ウイルス対策猶予期間に入り、間もなく期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="103b5-1043">有効期限が切れ、このプログラムはウイルス、スパイウェア、その他の望ましくない可能性のあるソフトウェアに対する保護を無効にします。</span><span class="sxs-lookup"><span data-stu-id="103b5-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="103b5-1044">
<dt>有効期限の理由: 有効期限が切れるMicrosoft Defender ウイルス対策理由。</dt>
<dt>有効期限: 有効期限が切れるMicrosoft Defender ウイルス対策日付。</dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1045">イベント ID: 5101</span><span class="sxs-lookup"><span data-stu-id="103b5-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="103b5-1046">記号名:</span><span class="sxs-lookup"><span data-stu-id="103b5-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="103b5-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1048">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="103b5-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="103b5-1049">
<b>マルウェア対策プラットフォームの有効期限が切れています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1050">説明:</span><span class="sxs-lookup"><span data-stu-id="103b5-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="103b5-1051">Microsoft Defender ウイルス対策期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="103b5-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="103b5-1052">ウイルス、スパイウェア、その他の望ましくない可能性のあるソフトウェアに対する保護が無効になります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="103b5-1053">
<dt>有効期限の理由:</dt>
<dt>有効期限: </dt>
<dt>エラー コード: エラー コード &lt; &gt; 脅威の状態に関連付けられている結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="103b5-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender ウイルス対策 クライアント エラー コード Microsoft Defender ウイルス対策問題が発生した場合は、通常、問題のトラブルシューティングに役立つエラー コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="103b5-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="103b5-1055">ほとんどの場合、エラーは更新プログラムのインストールに問題が発生したという意味です。</span><span class="sxs-lookup"><span data-stu-id="103b5-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="103b5-1056">このセクションでは、クライアント エラーに関する以下Microsoft Defender ウイルス対策説明します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="103b5-1057">-   エラー コード -   エラーの考えられる理由 -   今すぐ実行する操作に関するアドバイス</span><span class="sxs-lookup"><span data-stu-id="103b5-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="103b5-1058">これらの表の情報を使用して、エラー コードのトラブルシューティングMicrosoft Defender ウイルス対策役立ちます。</span><span class="sxs-lookup"><span data-stu-id="103b5-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="103b5-1059">エラー コード: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="103b5-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="103b5-1060">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1060">Message</span></span></td>
<td><span data-ttu-id="103b5-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1062">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="103b5-1063">このエラーは、メモリが使い切れている可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="103b5-1064">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="103b5-1065">デバイスで使用可能なメモリを確認します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="103b5-1066">実行中の未使用のアプリケーションを閉じて、デバイス上のメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="103b5-1067">デバイスを再起動し、スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1068">エラー コード: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="103b5-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="103b5-1069">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1069">Message</span></span></td>
<td><span data-ttu-id="103b5-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1071">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1072">このエラーは、セキュリティ製品に問題がある可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="103b5-1073">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="103b5-1074">定義を更新します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1074">Update the definitions.</span></span> <span data-ttu-id="103b5-1075">いずれも：</span><span class="sxs-lookup"><span data-stu-id="103b5-1075">Either:</span></span><ol>
<li><span data-ttu-id="103b5-1076">[更新]<b>タブの</b>[定義の更新]<b>ボタンをクリック</b>Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="103b5-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="103b5-1077">または、</span><span class="sxs-lookup"><span data-stu-id="103b5-1077">Or,</span></span>
</li>
<li><span data-ttu-id="103b5-1078">サイトから最新の定義<a href="https://aka.ms/wdsi">をMicrosoft セキュリティ インテリジェンスします</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="103b5-1079">注: サイトからダウンロードされる定義ファイルのサイズは 60 MB を超える場合があります。定義を更新するための長期的なソリューションとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="103b5-1080">フル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="103b5-1081">デバイスを再起動し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1082">エラー コード: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="103b5-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="103b5-1083">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1083">Message</span></span></td>
<td><span data-ttu-id="103b5-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1085">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1086">このエラーは、エンジン構成エラーが発生している可能性を示します。一般に、これはエンジンが正しく機能しない入力データに関連しています。</span><span class="sxs-lookup"><span data-stu-id="103b5-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1087">エラー コード: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="103b5-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1088">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1088">Message</span></span></td>
<td><span data-ttu-id="103b5-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1090">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1091">このエラーは、脅威Microsoft Defender ウイルス対策検疫に失敗した可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1092">エラー コード: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="103b5-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1093">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1093">Message</span></span></td>
<td><span data-ttu-id="103b5-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1095">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1096">このエラーは、脅威の削除を完了するために再起動が必要な場合を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="103b5-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="103b5-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1098">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1098">Message</span></span></td>
<td><span data-ttu-id="103b5-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1100">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1101">このエラーは、脅威がメディアに存在しなくなったか、マルウェアがデバイスのスキャンを停止している可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="103b5-1102">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="103b5-1103">セキュリティ ソフトウェアを<a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a>し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1104">エラー コード: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="103b5-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="103b5-1105">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1105">Message</span></span></td>
<td><span data-ttu-id="103b5-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1107">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1108">このエラーは、システム全体のスキャンが必要な可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="103b5-1109">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1109">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1110">完全なシステム スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1111">エラー コード: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="103b5-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1112">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1112">Message</span></span></td>
<td><span data-ttu-id="103b5-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1114">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1115">このエラーは、脅威の削除を完了するために手動の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="103b5-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1116">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1116">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1117">Microsoft マルウェア保護百科事典で説明されている手動 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">修復手順に従います</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="103b5-1118">イベント履歴には、脅威固有のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1119">エラー コード: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="103b5-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1120">Message</span></span></td>
<td><span data-ttu-id="103b5-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1122">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1123">このエラーは、コンテナーの種類内の削除がサポートされていない可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1124">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1124">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1125">Microsoft Defender ウイルス対策内で検出された脅威を修復できない場合。</span><span class="sxs-lookup"><span data-stu-id="103b5-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="103b5-1126">検出されたリソースを手動で削除する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="103b5-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1127">エラー コード: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="103b5-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1128">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1128">Message</span></span></td>
<td><span data-ttu-id="103b5-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1130">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1131">このエラーは、低および中規模の脅威の削除が無効になる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1132">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1132">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1133">検出された脅威を確認し、必要に応じて解決します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1134">エラー コード: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="103b5-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1135">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1135">Message</span></span></td>
<td><span data-ttu-id="103b5-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1137">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1138">このエラーは、脅威が必要な再スキャンを示します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1139">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1139">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1140">完全なシステム スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1141">エラー コード: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="103b5-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1142">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1142">Message</span></span></td>
<td><span data-ttu-id="103b5-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="103b5-1144">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1145">このエラーは、オフライン スキャンが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1146">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1146">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1147">オフライン で実行Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="103b5-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="103b5-1148">これを行う方法については、オフラインの記事Microsoft Defender ウイルス対策<a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">できます</a>。</span><span class="sxs-lookup"><span data-stu-id="103b5-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="103b5-1149">エラー コード: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="103b5-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="103b5-1150">メッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1150">Message</span></span></td>
<td><span data-ttu-id="103b5-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="103b5-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="103b5-1152">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="103b5-1153">このエラーは、Microsoft Defender ウイルス対策が現在のバージョンのプラットフォームをサポートしていないので、新しいバージョンのプラットフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="103b5-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="103b5-1154">解決方法</span><span class="sxs-lookup"><span data-stu-id="103b5-1154">Resolution</span></span></td><td>
<span data-ttu-id="103b5-1155">このコマンドは、Microsoft Defender ウイルス対策でのみWindows 10。</span><span class="sxs-lookup"><span data-stu-id="103b5-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="103b5-1156">Vista Windows 8、Windows 7、Windows Vista の場合は、 を使用<a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection。</a></span><span class="sxs-lookup"><span data-stu-id="103b5-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="103b5-1157">

<a id="internal-error-codes"></a>次のエラー コードは、内部テストのテスト中に使用Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="103b5-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="103b5-1158">これらのエラーが表示された場合は、定義を[](manage-updates-baselines-microsoft-defender-antivirus.md)更新し、エンドポイントで直接再スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="103b5-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="103b5-1159">内部エラー コード</span><span class="sxs-lookup"><span data-stu-id="103b5-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="103b5-1160"><b>エラー コード</b></span><span class="sxs-lookup"><span data-stu-id="103b5-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="103b5-1161">表示されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="103b5-1161">Message displayed</span></span></th>
<th><span data-ttu-id="103b5-1162">エラーと解決の考えられる理由</span><span class="sxs-lookup"><span data-stu-id="103b5-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="103b5-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="103b5-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="103b5-1165">インターネット接続を確認してから、もう一度スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="103b5-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="103b5-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="103b5-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span><span class="sxs-lookup"><span data-stu-id="103b5-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="103b5-1168">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="103b5-1168">This is an internal error.</span></span> <span data-ttu-id="103b5-1169">原因が明確に定義されていません。</span><span class="sxs-lookup"><span data-stu-id="103b5-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="103b5-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="103b5-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="103b5-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="103b5-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="103b5-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="103b5-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="103b5-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="103b5-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="103b5-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="103b5-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="103b5-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="103b5-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="103b5-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="103b5-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="103b5-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="103b5-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="103b5-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="103b5-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="103b5-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="103b5-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="103b5-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="103b5-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="103b5-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="103b5-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="103b5-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="103b5-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="103b5-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="103b5-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="103b5-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="103b5-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="103b5-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="103b5-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="103b5-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="103b5-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="103b5-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="103b5-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="103b5-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="103b5-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="103b5-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="103b5-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="103b5-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="103b5-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="103b5-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="103b5-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="103b5-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="103b5-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="103b5-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="103b5-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="103b5-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="103b5-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="103b5-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="103b5-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="103b5-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="103b5-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="103b5-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="103b5-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="103b5-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="103b5-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="103b5-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="103b5-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="103b5-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="103b5-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="103b5-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="103b5-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="103b5-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="103b5-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="103b5-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="103b5-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="103b5-1238">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="103b5-1238">This is an internal error.</span></span> <span data-ttu-id="103b5-1239">マルウェアの削除が成功しなかった場合にトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="103b5-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="103b5-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="103b5-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="103b5-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="103b5-1242">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="103b5-1242">This is an internal error.</span></span> <span data-ttu-id="103b5-1243">スキャンが完了しないときにトリガーされた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="103b5-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="103b5-1244">関連項目</span><span class="sxs-lookup"><span data-stu-id="103b5-1244">Related topics</span></span>

- [<span data-ttu-id="103b5-1245">保護に関するMicrosoft Defender ウイルス対策レポート</span><span class="sxs-lookup"><span data-stu-id="103b5-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="103b5-1246">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="103b5-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)