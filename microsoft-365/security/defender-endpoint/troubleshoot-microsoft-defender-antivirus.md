---
title: Microsoft Defender AV イベントの ID とエラー コード
description: Microsoft Defender ウイルス対策イベントの ID とエラーの原因と解決策を調べている
keywords: イベント、エラー コード、siem、ログ、トラブルシューティング、wef、Windows イベント転送
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d78728ae6b79914e5e9bac46e000d633793ae991
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691600"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="6a5ef-104">イベント ログとエラー コードを確認して、Microsoft Defender Antivirus の問題をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="6a5ef-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6a5ef-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6a5ef-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a5ef-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a5ef-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6a5ef-107">Microsoft Defender Antivirus で問題が発生した場合は、このトピックの表を検索して、一致する問題と潜在的な解決策を見つける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="6a5ef-108">テーブルの一覧:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-108">The tables list:</span></span>

- <span data-ttu-id="6a5ef-109">[Microsoft Defender ウイルス対策イベントの ID (](#windows-defender-av-ids) これらは Windows 10 と Windows Server 2016 の両方に適用されます)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="6a5ef-110">Microsoft Defender ウイルス対策クライアントのエラー コード</span><span class="sxs-lookup"><span data-stu-id="6a5ef-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="6a5ef-111">Microsoft Defender ウイルス対策クライアントの内部エラー コード (開発およびテスト中に Microsoft が使用)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="6a5ef-112">Microsoft Defender for Endpoint のデモ Web サイトにアクセス [して、demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能が動作しているのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="6a5ef-113">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="6a5ef-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="6a5ef-114">高速学習 (一目でブロックを含む)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="6a5ef-115">望ましくない可能性があるアプリケーションのブロック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="6a5ef-116">Microsoft Defender ウイルス対策イベントの IDs</span><span class="sxs-lookup"><span data-stu-id="6a5ef-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="6a5ef-117">Microsoft Defender ウイルス対策は、Windows イベント ログにイベントの ID を記録します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="6a5ef-118">イベント ログを直接表示するか、サードパーティのセキュリティ情報とイベント管理 (SIEM) ツールがある場合は [、Microsoft Defender Antivirus](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) クライアント イベント ID を使用して、エンドポイントから特定のイベントやエラーを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="6a5ef-119">このセクションの表に、Microsoft Defender Antivirus のメイン イベントの ID を示し、可能な場合は、エラーを修正または解決するための推奨ソリューションを示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="6a5ef-120">Microsoft Defender ウイルス対策イベントを表示するには</span><span class="sxs-lookup"><span data-stu-id="6a5ef-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="6a5ef-121">イベント **ビューアーを開きます**。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="6a5ef-122">コンソール ツリーで、[アプリケーションとサービス ログ] **、[Microsoft]** **、[Windows]** の順に展開し、[Windows Defender]**をWindows Defender。**</span><span class="sxs-lookup"><span data-stu-id="6a5ef-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="6a5ef-123">[操作] を **ダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="6a5ef-124">詳細ウィンドウで、個々のイベントの一覧を表示して、イベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="6a5ef-125">イベントをクリックすると、[全般] タブと [詳細] タブの下の下部ウィンドウにイベントに関する特定の **詳細が\*\*\*\*表示** されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="6a5ef-126">イベント ID: 1000</span><span class="sxs-lookup"><span data-stu-id="6a5ef-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-127">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="6a5ef-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-129">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-129">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-130">
<b>マルウェア対策スキャンが開始されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="6a5ef-131">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-132">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-133">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-133">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-134">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-134">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-135">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-135">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-136">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-137">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-137">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-138">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-138">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-139">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-139">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-140">
</dt>
<dt>スキャン リソース: &lt;スキャンされたリソース (ファイル/ディレクトリ/BHO など)。 &gt; </dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-141">イベント ID: 1001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-142">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-144">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-144">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-145">
<b>マルウェア対策スキャンが完了しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-146">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-147">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-148">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-148">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-149">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-149">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-150">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-150">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-151">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-152">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-152">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-153">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-153">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-154">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-154">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-155">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>スキャン時間: &lt; スキャンの期間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-156">イベント ID: 1002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-157">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-159">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-159">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-160">
<b>マルウェア対策スキャンは終了する前に停止しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-161">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-162">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-163">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-163">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-164">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-164">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-165">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-165">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-166">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-167">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-167">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-168">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-168">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-169">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-169">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-170">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; &amp; lt;ユーザー &gt; </dt>
<dt>スキャン時間: &lt; スキャンの期間。 &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-171">イベント ID: 1003</span><span class="sxs-lookup"><span data-stu-id="6a5ef-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-172">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-174">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-174">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-175">
<b>マルウェア対策スキャンが一時停止されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-176">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-177">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-178">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-178">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-179">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-179">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-180">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-180">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-181">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-182">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-182">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-183">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-183">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-184">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-184">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-185">
</dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-186">イベント ID: 1004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-187">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-189">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-189">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-190">
<b>マルウェア対策スキャンが再開されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-191">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-192">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-193">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-193">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-194">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-194">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-195">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-195">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-196">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-197">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-197">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-198">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-198">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-199">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-199">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-200">
</dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-201">イベント ID: 1005</span><span class="sxs-lookup"><span data-stu-id="6a5ef-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-202">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-204">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-204">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-205">
<b>マルウェア対策スキャンに失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-206">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="6a5ef-207">
<dt>スキャン ID: &lt;関連するスキャンの ID &gt; 番号。</dt> 
<dt>スキャンの種類: &lt; スキャンの種類 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-208">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-208">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-209">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-209">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-210">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-210">Antimalware</span></span></li>
</ul><span data-ttu-id="6a5ef-211">
</dt>
<dt>スキャン パラメーター: &lt; スキャン パラメーター &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-212">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-212">Full scan</span></span></li>
<li><span data-ttu-id="6a5ef-213">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-213">Quick scan</span></span></li>
<li><span data-ttu-id="6a5ef-214">顧客スキャン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-214">Customer scan</span></span></li>
</ul><span data-ttu-id="6a5ef-215">
</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-216">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-217">ウイルス対策クライアントでエラーが発生し、現在のスキャンが停止しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="6a5ef-218">クライアント側の問題が原因でスキャンが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="6a5ef-219">このイベント レコードには、スキャン ID、スキャンの種類 (Microsoft Defender Antivirus、スパイウェア対策、マルウェア対策)、スキャン パラメーター、スキャンを開始したユーザー、エラー コード、エラーの説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="6a5ef-220">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6a5ef-221">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="6a5ef-222">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6a5ef-223"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-224">イベント ID: 1006</span><span class="sxs-lookup"><span data-stu-id="6a5ef-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-225">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-227">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-227">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-228">
<b>マルウェア対策エンジンは、マルウェアや望ましくない可能性のある他のソフトウェアを検出しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-229">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-230">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-231">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-232">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-232">Low</span></span></li>
<li><span data-ttu-id="6a5ef-233">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-233">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-234">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-234">High</span></span></li>
<li><span data-ttu-id="6a5ef-235">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-235">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-236">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-237">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-237">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-238">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-238">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-239">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-239">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-240">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-240">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-241">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-242">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-243">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-244">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-244">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-245">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-245">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-246">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-246">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-247">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-248">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-249">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-249">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-250">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-250">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-251">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-252">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-253">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-254">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-255">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-256">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-257">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-258">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-259">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-260">UAC </dt> 
<dt>状態: &lt; 状態 &gt; </dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>
<dt>署名バージョンのプロセス: &lt; 定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジンのバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-261">イベント ID : 1007</span><span class="sxs-lookup"><span data-stu-id="6a5ef-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-262">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-264">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-264">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-265">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションを実行しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-266">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-267">Microsoft Defender Antivirus は、マルウェアや望ましくない可能性のある他のソフトウェアからこのコンピューターを保護するための措置を取っています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="6a5ef-268">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-269">
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>名: &lt; 脅威 &gt; 名</dt>
<dt>ID: &lt; Threat ID &gt; </dt> 
<dt> Severity: &lt; Severity (次 &gt; に示す場合)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-270">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-270">Low</span></span></li>
<li><span data-ttu-id="6a5ef-271">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-271">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-272">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-272">High</span></span></li>
<li><span data-ttu-id="6a5ef-273">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-273">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-274">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt> 
<dt>Action: &lt; Action &gt; (アクション): たとえば、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-275">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6a5ef-276">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6a5ef-277">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6a5ef-278">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6a5ef-279">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="6a5ef-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6a5ef-280">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-280">No action: No action</span></span></li>
<li><span data-ttu-id="6a5ef-281">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6a5ef-282">
</dt>
<dt>状態: &lt;Status &gt; </dt>
<dt>Signature Version: &lt; Definition &gt; version</dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-283">イベント ID : 1008</span><span class="sxs-lookup"><span data-stu-id="6a5ef-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-284">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-286">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-286">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-287">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性があるソフトウェアからシステムを保護するためのアクションを実行しようとしたが、アクションは失敗した。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-288">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-289">マルウェアなどの望ましくない可能性があるソフトウェアに対してアクションを実行すると、Microsoft Defender Antivirus でエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="6a5ef-290">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-291">
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>名: &lt; 脅威 &gt; 名</dt>
<dt>ID: &lt; Threat ID &gt; </dt> 
<dt> Severity: &lt; Severity (次 &gt; に示す場合)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-292">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-292">Low</span></span></li>
<li><span data-ttu-id="6a5ef-293">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-293">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-294">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-294">High</span></span></li>
<li><span data-ttu-id="6a5ef-295">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-295">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-296">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt> 
<dt> アクション: &lt; アクション &gt; (たとえば、次の操作)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-297">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6a5ef-298">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6a5ef-299">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6a5ef-300">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6a5ef-301">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="6a5ef-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6a5ef-302">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-302">No action: No action</span></span></li>
<li><span data-ttu-id="6a5ef-303">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6a5ef-304">
</dt>
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>状態: &lt;Status &gt; </dt>
<dt>Signature Version: &lt; Definition &gt; version</dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-304">
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
<th colspan="2"><span data-ttu-id="6a5ef-305">イベント ID : 1009</span><span class="sxs-lookup"><span data-stu-id="6a5ef-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-306">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-308">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-308">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-309">
<b>マルウェア対策プラットフォームは、検疫からアイテムを復元しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-310">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-311">Microsoft Defender ウイルス対策は、検疫からアイテムを復元しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="6a5ef-312">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-313">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-314">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-314">Low</span></span></li>
<li><span data-ttu-id="6a5ef-315">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-315">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-316">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-316">High</span></span></li>
<li><span data-ttu-id="6a5ef-317">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-317">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-318">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>署名バージョン: &lt; 定義 &gt; バージョン</dt>
<dt>エンジンのバージョン: &lt; マルウェア &gt; 対策エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-318">
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
<th colspan="2"><span data-ttu-id="6a5ef-319">イベント ID : 1010</span><span class="sxs-lookup"><span data-stu-id="6a5ef-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-320">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-322">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-322">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-323">
<b>マルウェア対策プラットフォームでは、検疫からアイテムを復元する必要があります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-324">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-325">Microsoft Defender ウイルス対策では、検疫からアイテムを復元しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="6a5ef-326">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-327">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-328">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-328">Low</span></span></li>
<li><span data-ttu-id="6a5ef-329">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-329">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-330">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-330">High</span></span></li>
<li><span data-ttu-id="6a5ef-331">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-331">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-332">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-332">
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
<th colspan="2"><span data-ttu-id="6a5ef-333">イベント ID: 1011</span><span class="sxs-lookup"><span data-stu-id="6a5ef-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-334">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-336">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-336">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-337">
<b>マルウェア対策プラットフォームが検疫からアイテムを削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-338">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-339">Microsoft Defender ウイルス対策が検疫からアイテムを削除しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="6a5ef-340">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-341">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-342">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-342">Low</span></span></li>
<li><span data-ttu-id="6a5ef-343">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-343">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-344">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-344">High</span></span></li>
<li><span data-ttu-id="6a5ef-345">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-345">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-346">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>署名バージョン: &lt; 定義 &gt; バージョン</dt>
<dt>エンジンのバージョン: &lt; マルウェア &gt; 対策エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-346">
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
<th colspan="2"><span data-ttu-id="6a5ef-347">イベント ID : 1012</span><span class="sxs-lookup"><span data-stu-id="6a5ef-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-348">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-350">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-350">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-351">
<b>マルウェア対策プラットフォームは、検疫からアイテムを削除する必要があります。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-352">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-353">Microsoft Defender ウイルス対策では、検疫からアイテムを削除しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="6a5ef-354">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-355">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-356">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-356">Low</span></span></li>
<li><span data-ttu-id="6a5ef-357">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-357">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-358">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-358">High</span></span></li>
<li><span data-ttu-id="6a5ef-359">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-359">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-360">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パス</dt>
<dt>User: &lt; Domain &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-360">
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
<th colspan="2"><span data-ttu-id="6a5ef-361">イベント ID: 1013</span><span class="sxs-lookup"><span data-stu-id="6a5ef-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-362">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-364">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-364">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-365">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアの履歴を削除しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-366">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-367">Microsoft Defender Antivirus は、マルウェアなどの望ましくない可能性のあるソフトウェアの履歴を削除しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6a5ef-368">
<dt>時間: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-369">イベント ID: 1014</span><span class="sxs-lookup"><span data-stu-id="6a5ef-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-370">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-372">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-373">マルウェア対策プラットフォームでは、マルウェアなどの望ましくない可能性があるソフトウェアの履歴を削除する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-374">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-375">Microsoft Defender ウイルス対策では、マルウェアなどの望ましくない可能性があるソフトウェアの履歴を削除しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6a5ef-376">
<dt>時間: イベントが発生した時刻 (たとえば、履歴が削除された時刻)。このパラメーターは脅威イベントでは使用されないので、修復時間と感染時間の違いはありません。具体的には、アクション時間または検出時間と呼ぶ必要があります。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt; エラー &gt; の説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-377">イベント ID: 1015</span><span class="sxs-lookup"><span data-stu-id="6a5ef-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-378">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-380">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-380">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-381">
<b>マルウェア対策プラットフォームが疑わしい動作を検出しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-382">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-383">Microsoft Defender ウイルス対策では、疑わしい動作が検出されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="6a5ef-384">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-385">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-386">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-386">Low</span></span></li>
<li><span data-ttu-id="6a5ef-387">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-387">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-388">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-388">High</span></span></li>
<li><span data-ttu-id="6a5ef-389">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-389">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-390">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-391">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-391">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-392">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-392">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-393">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-393">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-394">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-394">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-395">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-396">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-397">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-398">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-398">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-399">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-399">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-400">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-400">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-401">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-402">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-403">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-403">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-404">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-404">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-405">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-406">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-407">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-408">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-409">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-410">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-411">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-412">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-413">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-414">UAC </dt> 
<dt>状態: &lt; 状態 &gt; </dt>
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>署名
<dt>ID のプロセス: 重大度に一致する列挙。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジン</dt>バージョン
<dt>の [忠実度ラベル]:</dt>ターゲット ファイル名: ファイル名
<dt> &lt; &gt; ファイルの名前。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="6a5ef-415">イベント ID: 1116</span><span class="sxs-lookup"><span data-stu-id="6a5ef-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-416">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-418">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-418">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-419">
<b>マルウェア対策プラットフォームがマルウェアなどの望ましくない可能性のあるソフトウェアを検出しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-420">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-421">Microsoft Defender ウイルス対策では、マルウェアなどの望ましくない可能性のあるソフトウェアが検出されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6a5ef-422">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-423">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-424">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-424">Low</span></span></li>
<li><span data-ttu-id="6a5ef-425">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-425">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-426">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-426">High</span></span></li>
<li><span data-ttu-id="6a5ef-427">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-427">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-428">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-429">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-429">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-430">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-430">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-431">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-431">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-432">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-432">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-433">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-434">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-435">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-436">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-436">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-437">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-437">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-438">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-438">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-439">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-440">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-441">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-441">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-442">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-442">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-443">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-444">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-445">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-446">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-447">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-448">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-449">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-450">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-451">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-452">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; </dt>
<dt>署名バージョンのプロセス: &lt; 定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジンのバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-453">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-454">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-454">No action is required.</span></span> <span data-ttu-id="6a5ef-455">Microsoft Defender ウイルス対策は、この脅威に対して定期的なアクションを中断して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="6a5ef-456">脅威を手動で削除する場合は、Microsoft Defender ウイルス対策インターフェイスで、[コンピューターのクリーン] <b>をクリックします</b>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-457">イベント ID: 1117</span><span class="sxs-lookup"><span data-stu-id="6a5ef-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-458">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-460">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-460">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-461">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性のあるソフトウェアからシステムを保護するためのアクションを実行しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-462">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-463">Microsoft Defender Antivirus は、マルウェアや望ましくない可能性のある他のソフトウェアからこのコンピューターを保護するための措置を取っています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6a5ef-464">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-465">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-466">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-466">Low</span></span></li>
<li><span data-ttu-id="6a5ef-467">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-467">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-468">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-468">High</span></span></li>
<li><span data-ttu-id="6a5ef-469">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-469">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-470">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-471">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-471">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-472">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-472">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-473">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-473">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-474">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-474">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-475">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-476">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-477">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-478">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-478">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-479">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-479">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-480">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-480">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-481">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-482">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-483">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-483">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-484">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-484">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-485">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-486">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-487">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-488">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-489">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-490">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-491">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-492">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-493">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-494">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="6a5ef-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-495">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6a5ef-496">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6a5ef-497">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6a5ef-498">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6a5ef-499">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="6a5ef-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6a5ef-500">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-500">No action: No action</span></span></li>
<li><span data-ttu-id="6a5ef-501">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6a5ef-502">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義 &gt; </dt>バージョン エンジンのバージョン
<dt>: &lt; &gt; </dt>マルウェア対策エンジンのバージョン NOTE: Microsoft Defender ウイルス対策、Microsoft Security Essentials、悪意のあるソフトウェアの削除ツール、または System Center Endpoint Protection がマルウェアを検出すると、マルウェアが変更された可能性のある次のシステム設定とサービスが復元されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="6a5ef-503">既定のInternet Explorerまたは Microsoft Edge の設定</span><span class="sxs-lookup"><span data-stu-id="6a5ef-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="6a5ef-504">ユーザー アクセス制御の設定</span><span class="sxs-lookup"><span data-stu-id="6a5ef-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="6a5ef-505">Chrome の設定</span><span class="sxs-lookup"><span data-stu-id="6a5ef-505">Chrome settings</span></span></li>
<li><span data-ttu-id="6a5ef-506">ブート コントロール データ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="6a5ef-507">Regedit と Task Manager のレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="6a5ef-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="6a5ef-508">Windows Update、Background Intelligent Transfer Service、およびリモート プロシージャ コール サービス</span><span class="sxs-lookup"><span data-stu-id="6a5ef-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="6a5ef-509">Windows オペレーティング システム ファイル</span><span class="sxs-lookup"><span data-stu-id="6a5ef-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="6a5ef-510">上記のコンテキストは、次のクライアントとサーバーのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="6a5ef-511">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-511">Operating system</span></span></th>
<th><span data-ttu-id="6a5ef-512">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-513">クライアント オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="6a5ef-514">Windows Vista (Service Pack 1、または Service Pack 2)、Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="6a5ef-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-515">サーバー オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="6a5ef-516">Windows Server 2008、Windows Server 2008 R2、Windows Server 2012、Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6a5ef-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-517">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-518">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-518">No action is necessary.</span></span> <span data-ttu-id="6a5ef-519">Microsoft Defender ウイルス対策は、脅威を削除または検疫しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-520">イベント ID: 1118</span><span class="sxs-lookup"><span data-stu-id="6a5ef-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-521">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-523">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-523">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-524">
<b>マルウェア対策プラットフォームは、マルウェアなどの望ましくない可能性があるソフトウェアからシステムを保護するためのアクションを実行しようとしたが、アクションは失敗した。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-525">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-526">Microsoft Defender ウイルス対策では、マルウェアなどの望ましくない可能性があるソフトウェアに対してアクションを実行するときに重大でないエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6a5ef-527">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-528">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-529">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-529">Low</span></span></li>
<li><span data-ttu-id="6a5ef-530">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-530">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-531">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-531">High</span></span></li>
<li><span data-ttu-id="6a5ef-532">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-532">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-533">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-534">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-534">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-535">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-535">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-536">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-536">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-537">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-537">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-538">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-539">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-540">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-541">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-541">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-542">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-542">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-543">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-543">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-544">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-545">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-546">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-546">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-547">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-547">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-548">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-549">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-550">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-551">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-552">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-553">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-554">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-555">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-556">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-557">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="6a5ef-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-558">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6a5ef-559">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6a5ef-560">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6a5ef-561">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6a5ef-562">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="6a5ef-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6a5ef-563">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-563">No action: No action</span></span></li>
<li><span data-ttu-id="6a5ef-564">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6a5ef-565">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-565">
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
<span data-ttu-id="6a5ef-566">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-567">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-567">No action is necessary.</span></span> <span data-ttu-id="6a5ef-568">Microsoft Defender ウイルス対策は、マルウェア修復に関連するタスクを完了できなかった。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="6a5ef-569">これは重大なエラーではありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-570">イベント ID: 1119</span><span class="sxs-lookup"><span data-stu-id="6a5ef-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-571">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-573">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-573">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-574">
<b>マルウェア対策プラットフォームでは、マルウェアなどの望ましくない可能性のあるソフトウェアに対してアクションを実行しようとするときに重大なエラーが発生しました。イベント メッセージには詳細があります。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-575">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-576">Microsoft Defender ウイルス対策では、マルウェアなどの望ましくない可能性のあるソフトウェアに対してアクションを実行するときに重大なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="6a5ef-577">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="6a5ef-578">
<dt>名前: &lt;脅威名 &gt; </dt>
<dt>ID: &lt; 脅威 ID &gt; </dt> 
<dt> の重大度: &lt; 重大度 &gt; (たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-579">低い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-579">Low</span></span></li>
<li><span data-ttu-id="6a5ef-580">中</span><span class="sxs-lookup"><span data-stu-id="6a5ef-580">Moderate</span></span></li>
<li><span data-ttu-id="6a5ef-581">高い</span><span class="sxs-lookup"><span data-stu-id="6a5ef-581">High</span></span></li>
<li><span data-ttu-id="6a5ef-582">重大</span><span class="sxs-lookup"><span data-stu-id="6a5ef-582">Severe</span></span></li>
</ul><span data-ttu-id="6a5ef-583">
</dt>
<dt>カテゴリ: &lt;カテゴリの &gt; 説明 (脅威やマルウェアの種類など)。</dt>
<dt>パス: &lt;ファイル &gt; パスの</dt> 
<dt> 検出元: &lt; 検出元 &gt; :次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-584">不明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-584">Unknown</span></span></li>
<li><span data-ttu-id="6a5ef-585">ローカル コンピューター</span><span class="sxs-lookup"><span data-stu-id="6a5ef-585">Local computer</span></span></li>
<li><span data-ttu-id="6a5ef-586">ネットワーク共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-586">Network share</span></span></li>
<li><span data-ttu-id="6a5ef-587">インターネット</span><span class="sxs-lookup"><span data-stu-id="6a5ef-587">Internet</span></span></li>
<li><span data-ttu-id="6a5ef-588">受信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="6a5ef-589">送信トラフィック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="6a5ef-590">
</dt>
<dt>検出の種類: &lt; 次に示 &gt; す検出の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-591">ヒューリスティック</span><span class="sxs-lookup"><span data-stu-id="6a5ef-591">Heuristics</span></span></li>
<li><span data-ttu-id="6a5ef-592">Generic</span><span class="sxs-lookup"><span data-stu-id="6a5ef-592">Generic</span></span></li>
<li><span data-ttu-id="6a5ef-593">コンクリート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-593">Concrete</span></span></li>
<li><span data-ttu-id="6a5ef-594">動的署名</span><span class="sxs-lookup"><span data-stu-id="6a5ef-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="6a5ef-595">
</dt>
<dt>検出ソース: &lt; 次に示す &gt; 検出ソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-596">ユーザー: 開始されたユーザー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-596">User: user initiated</span></span></li>
<li><span data-ttu-id="6a5ef-597">システム: システムが開始されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-597">System: system initiated</span></span></li>
<li><span data-ttu-id="6a5ef-598">リアルタイム: リアルタイム コンポーネントの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="6a5ef-599">IOAV: IE のダウンロードと Outlook Express の添付ファイルの開始</span><span class="sxs-lookup"><span data-stu-id="6a5ef-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="6a5ef-600">NIS: ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="6a5ef-601">IEPROTECT: IE - IExtensionValidation;これにより、悪意のある Web ページ コントロールから保護されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="6a5ef-602">早期起動マルウェア対策 (ELAM)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="6a5ef-603">これには、ブート シーケンスによって検出されたマルウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="6a5ef-604">リモート構成証明</span><span class="sxs-lookup"><span data-stu-id="6a5ef-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="6a5ef-605">マルウェア対策スキャン インターフェイス (AMSI)。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="6a5ef-606">主にスクリプト (PS、VBS) を保護するために使用しますが、第三者でも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="6a5ef-607">UAC </dt> 
<dt>ユーザー: &lt; ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>プロセス名: &lt; PID &gt; アクション</dt> 
<dt> のプロセス: &lt; アクション (例 &gt; :</span><span class="sxs-lookup"><span data-stu-id="6a5ef-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="6a5ef-608">クリーン: リソースがクリーンアップされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="6a5ef-609">検疫: リソースが検疫されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="6a5ef-610">削除: リソースが削除されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="6a5ef-611">許可: リソースの実行/存在が許可されました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="6a5ef-612">ユーザー定義: ユーザーが指定したアクションのこのリストから通常 1 つであるユーザー定義のアクション</span><span class="sxs-lookup"><span data-stu-id="6a5ef-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="6a5ef-613">アクションなし: アクションなし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-613">No action: No action</span></span></li>
<li><span data-ttu-id="6a5ef-614">ブロック: リソースの実行がブロックされました</span><span class="sxs-lookup"><span data-stu-id="6a5ef-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="6a5ef-615">
</dt>
<dt>アクションの状態: &lt;追加のアクションの &gt; 説明</dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-615">
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
<span data-ttu-id="6a5ef-616">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-617">重大な問題により、Microsoft Defender ウイルス対策クライアントでこのエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="6a5ef-618">エンドポイントが保護されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-618">The endpoint might not be protected.</span></span> <span data-ttu-id="6a5ef-619">エラーの説明を確認し、以下の関連する <b>ユーザー アクションの手順に</b> 従います。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="6a5ef-620">Action</span><span class="sxs-lookup"><span data-stu-id="6a5ef-620">Action</span></span></th>
<th><span data-ttu-id="6a5ef-621">ユーザー操作</span><span class="sxs-lookup"><span data-stu-id="6a5ef-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-622">
<b>削除</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-623">定義を更新し、削除が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-624">
<b>クリーン</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-625">定義を更新し、修復が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-626">
<b>検疫</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-627">定義を更新し、ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-628">
<b>許可する</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-629">ユーザーが必要なリソースにアクセスするためのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="6a5ef-630">このイベントが続く場合は、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="6a5ef-631">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="6a5ef-632">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6a5ef-633"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-634">イベント ID: 1120</span><span class="sxs-lookup"><span data-stu-id="6a5ef-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-635">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-637">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-637">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-638">
<b>Microsoft Defender ウイルス対策は、脅威リソースのハッシュを誘導しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-639">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-640">Microsoft Defender ウイルス対策クライアントが正常な状態で稼働しています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="6a5ef-641">
<dt>現在のプラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>の脅威リソース パス: &lt; パス &gt; </dt>
<dt>ハッシュ: &lt; ハッシュ &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="6a5ef-642"><b>注: このイベントは、次のポリシーが設定されている場合にのみログに <b>記録されます。ThreatFileHashLogging は署名なしです</b>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-643">イベント ID: 1150</span><span class="sxs-lookup"><span data-stu-id="6a5ef-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-644">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-646">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-646">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-647">
<b>マルウェア対策プラットフォームが監視プラットフォームに状態を報告する場合、このイベントは、マルウェア対策プラットフォームが実行され、正常な状態にあるかどうかを示します。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-648">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-649">Microsoft Defender ウイルス対策クライアントが正常な状態で稼働しています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="6a5ef-650">
<dt>プラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>の署名バージョン: &lt; 定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策エンジンのバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-651">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-652">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-652">No action is necessary.</span></span> <span data-ttu-id="6a5ef-653">Microsoft Defender ウイルス対策クライアントは正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6a5ef-654">このイベントは、1 時間単位で報告されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="6a5ef-655">イベント ID: 1151</span><span class="sxs-lookup"><span data-stu-id="6a5ef-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-656">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-658">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-658">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-659">
<b>エンドポイント保護クライアントの正常性レポート (UTC での時刻) </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-660">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-661">ウイルス対策クライアントの正常性レポート。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="6a5ef-662">
<dt>プラットフォームのバージョン: &lt;&gt;</dt>現在のプラットフォームバージョン エンジンバージョン
<dt>: &lt; &gt; </dt>マルウェア対策エンジンバージョン ネットワークリアルタイム検査エンジンバージョン
<dt> &lt; &gt; :</dt>
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; </dt>ネットワークリアルタイム検査エンジンバージョン ウイルス対策署名バージョン: ウイルス対策署名バージョン: スパイウェア対策署名バージョン ネットワークリアルタイム検査署名バージョン
<dt>: &lt; &gt; </dt>ネットワークリアルタイム検査署名バージョン
<dt>RTP 状態: リアルタイム保護状態 (有効または無効) OA 状態: On Access 状態 (有効または無効 &lt; &gt; </dt>
<dt> &lt; &gt; )</dt>IOAV 状態: IE ダウンロードと Outlook Express 添付ファイルの状態 (有効または無効
<dt> &lt; &gt; )</dt>
<dt>BM 状態: 動作監視状態 (有効または無効 &lt; &gt; )</dt>ウイルス対策署名年齢: ウイルス対策署名年齢 (日
<dt> &lt; &gt; )</dt>スパイウェア対策署名年齢: マルウェア対策署名年齢 (日) 最後のクイック スキャンの年齢: 最後のクイック スキャン年齢 (日
<dt> &lt; &gt; </dt>
<dt> &lt; &gt; )</dt>最後のフル スキャン年齢: 最後のフル スキャン年齢 (日
<dt> &lt; &gt; )</dt>ウイルス対策署名の作成時間:
<dt>? &lt;ウイルス対策署名の &gt; 作成時間</dt>
<dt>Antispyware 署名の作成時間: ? &lt;スパイウェア対策署名の作成時間 &gt; 最後</dt>
<dt>のクイック スキャンの開始時刻: ? &lt;最後のクイック スキャン &gt; の開始時刻</dt>
<dt>最後のクイック スキャンの終了時刻: ? &lt;最後のクイック &gt; </dt>スキャン終了時刻 最後のクイック スキャン ソース: 最後のクイック スキャン ソース (0 = スキャンは&#39;t が実行され、1 = ユーザーが開始し
<dt> &lt; &gt; 、2 =</dt>システムが開始されました) 最後のフル スキャン開始
<dt>時刻: &lt;最後のフル スキャン &gt; の開始時刻</dt>
<dt>最後のフル スキャンの終了時刻: ? &lt;最後のフル &gt; </dt>スキャン終了時刻 最後のフル スキャン ソース: 最後のフル スキャン ソース (0 = スキャンは&#39;t が実行されました、1 = ユーザーが開始
<dt> &lt; &gt; 、2 =</dt>システムが開始) 製品の状態: 内部トラブルシューティングの 
<dt> 場合</span><span class="sxs-lookup"><span data-stu-id="6a5ef-662">
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

<tr><span data-ttu-id="6a5ef-663">
<th colspan="2">イベント ID: 2000</span><span class="sxs-lookup"><span data-stu-id="6a5ef-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-664">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-666">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-666">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-667">
<b>マルウェア対策の定義が正常に更新されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-668">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-669">ウイルス対策署名のバージョンが更新されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="6a5ef-670">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>以前の署名バージョン: &lt; &gt; 以前の</dt>署名バージョン 
<dt> の署名の種類: &lt; 署名の &gt; 種類 、たとえば、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6a5ef-671">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-671">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-672">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-672">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-673">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-673">Antimalware</span></span></li>
<li><span data-ttu-id="6a5ef-674">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-675">
</dt>
<dt>更新プログラムの種類: &lt;更新の種類 &gt; (Full または Delta)。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>現在のエンジンのバージョン: &lt; 現在のエンジンバージョン &gt; </dt>
<dt>以前のエンジンバージョン: &lt; 以前のエンジンバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-675">
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
<span data-ttu-id="6a5ef-676">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-677">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-677">No action is necessary.</span></span> <span data-ttu-id="6a5ef-678">Microsoft Defender ウイルス対策クライアントは正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6a5ef-679">このイベントは、署名が正常に更新されると報告されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-680">イベント ID: 2001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-681">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-683">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-683">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-684">
<b>セキュリティ インテリジェンスの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-685">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-686">Microsoft Defender ウイルス対策では、署名の更新中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="6a5ef-687">
<dt>新しいセキュリティ インテリジェンスのバージョン: &lt;新しいバージョン &gt; 番号</dt>
<dt>以前のセキュリティ インテリジェンス のバージョン: &lt; 以前のバージョン &gt; </dt>の更新元: 
<dt> &lt; 更新プログラム &gt; のソースは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-688">セキュリティ インテリジェンス更新フォルダー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="6a5ef-689">内部セキュリティ インテリジェンス更新サーバー</span><span class="sxs-lookup"><span data-stu-id="6a5ef-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="6a5ef-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="6a5ef-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="6a5ef-691">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="6a5ef-691">File share</span></span></li>
<li><span data-ttu-id="6a5ef-692">マイクロソフト マルウェア プロテクション センター (MMPC)</span><span class="sxs-lookup"><span data-stu-id="6a5ef-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="6a5ef-693">
</dt>
<dt>更新ステージ: &lt; 更新ステージ &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-694">検索</span><span class="sxs-lookup"><span data-stu-id="6a5ef-694">Search</span></span></li>
<li><span data-ttu-id="6a5ef-695">ダウンロード</span><span class="sxs-lookup"><span data-stu-id="6a5ef-695">Download</span></span></li>
<li><span data-ttu-id="6a5ef-696">インストール</span><span class="sxs-lookup"><span data-stu-id="6a5ef-696">Install</span></span></li>
</ul><span data-ttu-id="6a5ef-697">
</dt>
<dt>ソース パス: ユニバーサル名前付け規則 (UNC) のファイル共有名、Windows Server Update Services (WSUS)/Microsoft Update/ADL のサーバー名。</dt> 
<dt>署名の種類: &lt; 次に示す &gt; 署名の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6a5ef-698">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-698">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-699">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-699">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-700">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-700">Antimalware</span></span></li>
<li><span data-ttu-id="6a5ef-701">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-702">
</dt>
<dt>更新プログラムの種類: &lt;更新の種類 &gt; (Full または Delta)。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>現在のエンジンのバージョン: &lt; &gt; 現在</dt>のエンジンバージョン 以前のエンジンバージョン
<dt> &lt; &gt; :</dt>以前のエンジンバージョン エラー コード: エラー コード 脅威の状態
<dt> &lt; &gt; に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-702">
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
<span data-ttu-id="6a5ef-703">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-704">このエラーは、定義の更新に問題がある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="6a5ef-705">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6a5ef-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a> 、エンドポイントで直接再スキャンを強制します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="6a5ef-707">このエラーの詳細については、%Windir%\WindowsUpdate.log ファイルのエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="6a5ef-708"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-709">イベント ID: 2002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-710">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-712">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-712">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-713">
<b>マルウェア対策エンジンが正常に更新されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-714">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-715">Microsoft Defender ウイルス対策エンジンのバージョンが更新されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="6a5ef-716">
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt>
<dt>以前の &lt; &gt; エンジン バージョン:</dt>以前のエンジン バージョン エンジンの種類: エンジンの種類 、マルウェア対策
<dt>エンジンまたはネットワーク検査システム &lt; &gt; エンジンのいずれか。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-717">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-718">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-718">No action is necessary.</span></span> <span data-ttu-id="6a5ef-719">Microsoft Defender ウイルス対策クライアントは正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6a5ef-720">このイベントは、マルウェア対策エンジンが正常に更新されると報告されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-721">イベント ID: 2003</span><span class="sxs-lookup"><span data-stu-id="6a5ef-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-722">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-724">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-724">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-725">
<b>マルウェア対策エンジンの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-726">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-727">Microsoft Defender ウイルス対策では、エンジンを更新しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="6a5ef-728">
<dt>新しいエンジンバージョン:</dt>
<dt>以前のエンジン バージョン: &lt; &gt; </dt>以前のエンジン バージョン エンジンの種類: エンジンの種類 、マルウェア対策
<dt>エンジンまたはネットワーク検査システム &lt; &gt; エンジンのいずれか。</dt>
<dt>ユーザー: &lt;ドメイン &gt; \& lt;ユーザー &gt; </dt>
<dt>エラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-728">
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
<span data-ttu-id="6a5ef-729">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-730">Microsoft Defender ウイルス対策クライアントの更新に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="6a5ef-731">このイベントは、クライアントが更新自体に失敗した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="6a5ef-732">このイベントは、通常、更新中にネットワーク接続が中断された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="6a5ef-733">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6a5ef-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">定義を更新し</a> 、エンドポイントで直接再スキャンを強制します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="6a5ef-735"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-736">イベント ID: 2004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-737">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-739">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-739">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-740">
<b>マルウェア対策定義の読み込み中に問題が発生しました。マルウェア対策エンジンは、最後に知られている一連の定義の読み込みを試みます。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-741">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-742">Microsoft Defender ウイルス対策では、署名の読み込み中にエラーが発生し、既知の良い一連の署名に戻そうとします。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="6a5ef-743">
<dt>署名の試行: エラー</dt>
<dt>コード: エラー コード &lt; &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
<dt>署名バージョン: &lt;定義バージョン &gt; </dt>
<dt>エンジンのバージョン: &lt; マルウェア対策 &gt; エンジンのバージョン</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-743">
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
<span data-ttu-id="6a5ef-744">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-745">Microsoft Defender ウイルス対策クライアントは、最新の定義ファイルのダウンロードとインストールを試み、失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="6a5ef-746">このエラーは、定義の読み込み中にクライアントがエラーを検出した場合、またはファイルが破損している場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="6a5ef-747">Microsoft Defender ウイルス対策は、既知の一連の定義に戻す試みです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="6a5ef-748">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6a5ef-749">コンピューターを再起動し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="6a5ef-750">Microsoft セキュリティ インテリジェンス サイトから最新の定義 <a href="https://aka.ms/wdsi">をダウンロードします</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="6a5ef-751">注: サイトからダウンロードされる定義ファイルのサイズは 60 MB を超える場合があります。定義を更新するための長期的なソリューションとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="6a5ef-752"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-753">イベント ID: 2005</span><span class="sxs-lookup"><span data-stu-id="6a5ef-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-754">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-756">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-756">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-757">
<b>マルウェア対策プラットフォームが最新ではないので、マルウェア対策エンジンの読み込みに失敗しました。マルウェア対策プラットフォームは、最後に知られている優れたマルウェア対策エンジンを読み込み、更新を試みる。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-758">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-759">Microsoft Defender ウイルス対策は、現在のプラットフォームバージョンがサポートされていないため、マルウェア対策エンジンを読み込むためでした。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="6a5ef-760">Microsoft Defender ウイルス対策は、既知の最後のエンジンに戻り、プラットフォームの更新が試行されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="6a5ef-761">
<dt>現在のプラットフォームのバージョン: &lt; 現在のプラットフォームのバージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-762">イベント ID: 2006</span><span class="sxs-lookup"><span data-stu-id="6a5ef-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-763">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-765">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-765">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-766">
<b>プラットフォームの更新に失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-767">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-768">Microsoft Defender ウイルス対策では、プラットフォームを更新しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="6a5ef-769">
<dt>現在のプラットフォームのバージョン: &lt;現在のプラットフォーム &gt; バージョン</dt>
<dt>のエラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-770">イベント ID: 2007</span><span class="sxs-lookup"><span data-stu-id="6a5ef-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-771">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-773">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-773">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-774">
<b>プラットフォームは間もなく更新されます。最新の保護を維持するために最新のプラットフォームをダウンロードします。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-775">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-776">Microsoft Defender Antivirus では、マルウェア対策エンジンの将来のバージョンをサポートするために、新しいプラットフォーム バージョンがすぐに必要になります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="6a5ef-777">最新の Microsoft Defender ウイルス対策プラットフォームをダウンロードして、利用可能な最高レベルの保護を維持します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="6a5ef-778">
<dt>現在のプラットフォームのバージョン: &lt; 現在のプラットフォームのバージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-779">イベント ID: 2010</span><span class="sxs-lookup"><span data-stu-id="6a5ef-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-780">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-782">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-782">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-783">
<b>マルウェア対策エンジンは、動的署名サービスを使用して追加の定義を取得しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-784">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-785">Microsoft Defender ウイルス対策では <i>、動的署名サービスを使用</i> して、コンピューターの保護に役立つ追加の署名を取得しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="6a5ef-786">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6a5ef-787">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-787">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-788">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-788">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-789">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-789">Antimalware</span></span></li>
<li><span data-ttu-id="6a5ef-790">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-791">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt> 
<dt> の動的署名の種類: &lt; 動的署名の &gt; 種類は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-792">バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-792">Version</span></span></li>
<li><span data-ttu-id="6a5ef-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-793">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-794">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-794">No limit</span></span></li>
<li><span data-ttu-id="6a5ef-795">Duration</span><span class="sxs-lookup"><span data-stu-id="6a5ef-795">Duration</span></span></li>
</ul><span data-ttu-id="6a5ef-796">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-797">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-797">VDM version</span></span></li>
<li><span data-ttu-id="6a5ef-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-798">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-799">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-799">No limit</span></span></li>
</ul><span data-ttu-id="6a5ef-800">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-801">イベント ID : 2011</span><span class="sxs-lookup"><span data-stu-id="6a5ef-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-802">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-804">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-804">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-805">
<b>動的署名サービスは、古い動的定義を削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-806">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-807">Microsoft Defender ウイルス対策では、 <i>動的署名サービスを使用して</i> 、古い署名を破棄しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="6a5ef-808">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6a5ef-809">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-809">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-810">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-810">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-811">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-811">Antimalware</span></span></li>
<li><span data-ttu-id="6a5ef-812">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-813">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt> 
<dt> の動的署名の種類: &lt; 動的署名の &gt; 種類は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-814">バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-814">Version</span></span></li>
<li><span data-ttu-id="6a5ef-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-815">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-816">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-816">No limit</span></span></li>
<li><span data-ttu-id="6a5ef-817">Duration</span><span class="sxs-lookup"><span data-stu-id="6a5ef-817">Duration</span></span></li>
</ul><span data-ttu-id="6a5ef-818">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>
<dt> &lt; &gt; Dynamic Signature Compilation Timestamp:</dt>Timestamp Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-819">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-819">VDM version</span></span></li>
<li><span data-ttu-id="6a5ef-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-820">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-821">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-821">No limit</span></span></li>
</ul><span data-ttu-id="6a5ef-822">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-823">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-824">アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-824">No action is necessary.</span></span> <span data-ttu-id="6a5ef-825">Microsoft Defender ウイルス対策クライアントは正常な状態です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="6a5ef-826">このイベントは、動的署名サービスが古い動的定義を正常に削除すると報告されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-827">イベント ID: 2012</span><span class="sxs-lookup"><span data-stu-id="6a5ef-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-828">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-830">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-830">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-831">
<b>動的署名サービスを使用しようとするときに、マルウェア対策エンジンでエラーが発生しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-832">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-833">Microsoft Defender ウイルス対策では、動的署名サービスを使用しようとしてエラー <i>が発生しました</i>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="6a5ef-834">
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt> 
<dt> の署名の種類: &lt; 次に示す署名 &gt; の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="6a5ef-835">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-835">Antivirus</span></span></li>
<li><span data-ttu-id="6a5ef-836">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-836">Antispyware</span></span></li>
<li><span data-ttu-id="6a5ef-837">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-837">Antimalware</span></span></li>
<li><span data-ttu-id="6a5ef-838">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-839">
</dt>
<dt>現在のエンジンのバージョン: &lt;現在のエンジン &gt; バージョン</dt>
<dt>のエラー コード: &lt; エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt> 
<dt>動的署名の種類: &lt; 動的署名の種類 &gt; は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-840">バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-840">Version</span></span></li>
<li><span data-ttu-id="6a5ef-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-841">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-842">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-842">No limit</span></span></li>
<li><span data-ttu-id="6a5ef-843">Duration</span><span class="sxs-lookup"><span data-stu-id="6a5ef-843">Duration</span></span></li>
</ul><span data-ttu-id="6a5ef-844">
</dt>
<dt>永続パス: &lt;Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , &gt; example:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-845">VDM バージョン</span><span class="sxs-lookup"><span data-stu-id="6a5ef-845">VDM version</span></span></li>
<li><span data-ttu-id="6a5ef-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="6a5ef-846">Timestamp</span></span></li>
<li><span data-ttu-id="6a5ef-847">制限なし</span><span class="sxs-lookup"><span data-stu-id="6a5ef-847">No limit</span></span></li>
</ul><span data-ttu-id="6a5ef-848">
</dt>
<dt>永続性の制限: 高速パス署名の永続性の制限。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-849">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-850">インターネット接続の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-851">イベント ID: 2013</span><span class="sxs-lookup"><span data-stu-id="6a5ef-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-852">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-854">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-854">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-855">
<b>動的署名サービスは、すべての動的定義を削除しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-856">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-857">Microsoft Defender ウイルス対策は、すべての <i>動的署名サービス署名を</i> 破棄しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="6a5ef-858">
<dt>現在の署名バージョン: &lt; 現在の署名バージョン&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-859">イベント ID: 2020</span><span class="sxs-lookup"><span data-stu-id="6a5ef-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-860">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-862">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-862">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-863">
<b>マルウェア対策エンジンがクリーン ファイルをダウンロードしました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-864">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-865">Microsoft Defender ウイルス対策がクリーン ファイルをダウンロードしました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="6a5ef-866">
<dt>ファイル名: &lt;ファイル名 &gt; ファイルの名前。</dt>
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>現在のエンジンのバージョン: &lt; 現在のエンジンのバージョン &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-867">イベント ID: 2021</span><span class="sxs-lookup"><span data-stu-id="6a5ef-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-868">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-870">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-870">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-871">
<b>マルウェア対策エンジンがクリーン ファイルのダウンロードに失敗しました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-872">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-873">Microsoft Defender ウイルス対策では、クリーン ファイルのダウンロード中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="6a5ef-874">
<dt>ファイル名: &lt;ファイル名 &gt; ファイルの名前。</dt>
<dt>現在の署名バージョン: &lt;現在の署名 &gt; バージョン</dt>
<dt>現在のエンジンバージョン: 現在の &lt; エンジンバージョン &gt; </dt>エラー コード: エラー コード 脅威の状態
<dt> &lt; &gt; に関連付けられている結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-874">
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
<span data-ttu-id="6a5ef-875">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-876">インターネット接続の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="6a5ef-877">動的署名サービスを使用して最新の定義を特定の脅威にダウンロードすると、Microsoft Defender ウイルス対策クライアントでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="6a5ef-878">このエラーは、ネットワーク接続の問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-879">イベント ID: 2030</span><span class="sxs-lookup"><span data-stu-id="6a5ef-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-880">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-882">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-882">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-883">
<b>マルウェア対策エンジンがダウンロードされ、次のシステム再起動時にオフラインで実行するように構成されています。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-884">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-885">Microsoft Defender ウイルス対策は、次の再起動時に実行するようにオフライン ウイルス対策をダウンロードして構成しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-886">イベント ID: 2031</span><span class="sxs-lookup"><span data-stu-id="6a5ef-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-887">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-889">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-889">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-890">
<b>マルウェア対策エンジンがオフライン スキャンをダウンロードして構成できなかった。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-891">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-892">Microsoft Defender ウイルス対策では、オフライン ウイルス対策をダウンロードして構成しようとしてエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="6a5ef-893">
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-894">イベント ID: 2040</span><span class="sxs-lookup"><span data-stu-id="6a5ef-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-895">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-897">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-897">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-898">
<b>このオペレーティング システムバージョンのマルウェア対策のサポートは間もなく終了します。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-899">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-900">オペレーティング システムのサポートはまもなく期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="6a5ef-901">サポート外のオペレーティング システムで Microsoft Defender Antivirus を実行する方法は、脅威から保護するための適切なソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-902">イベント ID : 2041</span><span class="sxs-lookup"><span data-stu-id="6a5ef-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-903">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-905">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-905">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-906">
<b>このオペレーティング システムのマルウェア対策のサポートは終了しました。継続的なサポートのためにオペレーティング システムをアップグレードする必要があります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-907">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-908">オペレーティング システムのサポートが期限切れです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-908">The support for your operating system has expired.</span></span> <span data-ttu-id="6a5ef-909">サポート外のオペレーティング システムで Microsoft Defender Antivirus を実行する方法は、脅威から保護するための適切なソリューションではありません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-910">イベント ID: 2042</span><span class="sxs-lookup"><span data-stu-id="6a5ef-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-911">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-913">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-913">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-914">
<b>マルウェア対策エンジンは、このオペレーティング システムをサポートしなくなったので、システムをマルウェアから保護しなくなりました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-915">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-916">オペレーティング システムのサポートが期限切れです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-916">The support for your operating system has expired.</span></span> <span data-ttu-id="6a5ef-917">Microsoft Defender Antivirus は、オペレーティング システムでサポートされなくなったり、機能を停止し、マルウェアの脅威から保護されていません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-918">イベント ID: 3002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-919">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-921">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-921">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-922">
<b>リアルタイム保護でエラーが発生し、失敗しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-923">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-924">Microsoft Defender ウイルス対策Real-Time保護機能でエラーが発生し、失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="6a5ef-925">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-926">On Access</span><span class="sxs-lookup"><span data-stu-id="6a5ef-926">On Access</span></span></li>
<li><span data-ttu-id="6a5ef-927">Internet Explorerダウンロードと Microsoft Outlook Express の添付ファイル</span><span class="sxs-lookup"><span data-stu-id="6a5ef-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6a5ef-928">動作の監視</span><span class="sxs-lookup"><span data-stu-id="6a5ef-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6a5ef-929">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-930">
</dt>
<dt>エラー コード: &lt;エラー コード &gt; 脅威の状態に関連付けられた結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。 </dt>
<dt>理由: Microsoft Defender ウイルス対策リアルタイム保護が機能を再起動した理由。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-931">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-932">システムが一時保護されていない可能性&#39;、システムを再起動してからフル スキャンを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="6a5ef-933">Microsoft Defender ウイルス対策クライアント&#39;、サービスの 1 つが開始できなかったため、エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="6a5ef-934">その後に 3007 イベント ID が続く場合、エラーは一時的なもので、マルウェア対策クライアントはエラーから回復しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-935">イベント ID: 3007</span><span class="sxs-lookup"><span data-stu-id="6a5ef-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-936">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-938">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-938">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-939">
<b>障害から回復されたリアルタイム保護。このエラーが表示された場合は、完全なシステム スキャンを実行することをお勧めします。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-940">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-941">Microsoft Defender ウイルス対策リアルタイム保護が機能を再起動しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="6a5ef-942">完全なシステム スキャンを実行して、このエージェントがダウンしている間に見つからない可能性があるアイテムを検出してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="6a5ef-943">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-944">On Access</span><span class="sxs-lookup"><span data-stu-id="6a5ef-944">On Access</span></span></li>
<li><span data-ttu-id="6a5ef-945">IE のダウンロードと Outlook Express の添付ファイル</span><span class="sxs-lookup"><span data-stu-id="6a5ef-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6a5ef-946">動作の監視</span><span class="sxs-lookup"><span data-stu-id="6a5ef-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6a5ef-947">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-948">
</dt>
<dt>理由: Microsoft Defender ウイルス対策リアルタイム保護が機能を再起動した理由。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-949">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-950">リアルタイム保護機能が再起動されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="6a5ef-951">このイベントが再度発生した場合は <a href="https://go.microsoft.com/fwlink/?LinkId=215491">、Microsoft テクニカル サポートにお問い合わせください</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-952">イベント ID: 5000</span><span class="sxs-lookup"><span data-stu-id="6a5ef-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-953">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-955">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-955">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-956">
<b>リアルタイム保護が有効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-957">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-958">マルウェアなどの望ましくない可能性があるソフトウェアに対する Microsoft Defender ウイルス対策のリアルタイム保護スキャンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-959">イベント ID: 5001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-960">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-962">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-962">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-963">
<b>リアルタイム保護は無効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-964">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-965">マルウェアなどの望ましくない可能性があるソフトウェアに対する Microsoft Defender ウイルス対策のリアルタイム保護スキャンが無効になりました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-966">イベント ID: 5004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-967">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-969">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-969">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-970">
<b>リアルタイムの保護構成が変更されました。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-971">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-972">Microsoft Defender ウイルス対策のリアルタイム保護機能の構成が変更されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="6a5ef-973">
<dt>フィーチャー: &lt; フィーチャー &gt; (例:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="6a5ef-974">On Access</span><span class="sxs-lookup"><span data-stu-id="6a5ef-974">On Access</span></span></li>
<li><span data-ttu-id="6a5ef-975">IE のダウンロードと Outlook Express の添付ファイル</span><span class="sxs-lookup"><span data-stu-id="6a5ef-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="6a5ef-976">動作の監視</span><span class="sxs-lookup"><span data-stu-id="6a5ef-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="6a5ef-977">ネットワーク検査システム</span><span class="sxs-lookup"><span data-stu-id="6a5ef-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="6a5ef-978">
</dt>
<dt>構成: </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-979">イベント ID: 5007</span><span class="sxs-lookup"><span data-stu-id="6a5ef-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-980">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-982">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-982">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-983">
<b>マルウェア対策プラットフォームの構成が変更されました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-984">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-985">Microsoft Defender ウイルス対策の構成が変更されました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="6a5ef-986">予期しないイベントの場合は、マルウェアの結果である可能性がある設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="6a5ef-987">
<dt>古い値: &lt;古い値番号 &gt; 古いウイルス対策構成の値。</dt>
<dt>新しい値: &lt;新しい値の番号 &gt; 新しいウイルス対策構成の値。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-988">イベント ID: 5008</span><span class="sxs-lookup"><span data-stu-id="6a5ef-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-989">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-991">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-991">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-992">
<b>マルウェア対策エンジンでエラーが発生し、失敗しました。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-993">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-994">予期しないエラーが原因で Microsoft Defender ウイルス対策エンジンが終了しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="6a5ef-995">
<dt>エラーの種類: &lt;エラーの &gt; 種類 、たとえば:クラッシュまたは</dt>ハング例外
<dt>コード: &lt; エラー コード &gt; </dt>
<dt>Resource: &lt; Resource &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-996">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-997">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="6a5ef-998">サービスを再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="6a5ef-999">マルウェア対策、ウイルス対策、スパイウェアの場合は、管理者特権でコマンド プロンプトに <b>「net stop msmpsvc」</b>と入力し <b>、「net start msmpsvc」</b> と入力してマルウェア対策エンジンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="6a5ef-1000">ネットワーク検査<i></i>システムの場合は、管理者特権でコマンド プロンプトに<b>「net start nissrv」</b>と入力し、「net start <i></i> <b>nissrv」</b>と入力して、NiSSRV.exe ファイルを使用してネットワーク検査システム エンジンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="6a5ef-1001">同じ方法でエラーが発生した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft</a>サポート サイトにアクセスし、[検索] ボックスにエラー番号<b></b>を入力してエラー コードを検索し、Microsoft テクニカル サポートにお<a href="https://go.microsoft.com/fwlink/?LinkId=215491">問い合わせください</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1002">ユーザー アクション:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1003">予期しないエラーが原因で Microsoft Defender ウイルス対策クライアント エンジンが停止しました。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="6a5ef-1004">このイベントをトラブルシューティングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="6a5ef-1005">スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="6a5ef-1006">同じ方法で失敗した場合は<a href="https://go.microsoft.com/fwlink/?LinkId=215163">、Microsoft サポート</a>サイトに移動し、[検索]<b></b>ボックスにエラー番号を入力してエラー コードを探します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="6a5ef-1007"><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft テクニカル サポート</a>にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1008">イベント ID: 5009</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1009">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1011">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1012">
<b>マルウェアなどの望ましくない可能性があるソフトウェアのスキャンが有効になります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1013">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1014">Microsoft Defender ウイルス対策スキャンでマルウェアなどの望ましくない可能性があるソフトウェアが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1015">イベント ID: 5010</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1016">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1018">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1019">
<b>マルウェアなどの望ましくない可能性があるソフトウェアのスキャンが無効になります。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1020">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1021">Microsoft Defender ウイルス対策スキャンでマルウェアなどの望ましくない可能性があるソフトウェアが無効になります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1022">イベント ID: 5011</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1023">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1025">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1026">
<b>ウイルスのスキャンが有効になっています。</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1027">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1028">ウイルスの Microsoft Defender ウイルス対策スキャンが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1029">イベント ID: 5012</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1030">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1032">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1033">
<b>ウイルスのスキャンは無効になっています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1034">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1035">ウイルスの Microsoft Defender ウイルス対策スキャンが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1036">イベント ID: 5100</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1037">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1039">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1040">
<b>マルウェア対策プラットフォームは間もなく期限切れになります。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1041">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1042">Microsoft Defender ウイルス対策は猶予期間に入り、間もなく期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="6a5ef-1043">有効期限が切れ、このプログラムはウイルス、スパイウェア、その他の望ましくない可能性のあるソフトウェアに対する保護を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="6a5ef-1044">
<dt>有効期限の理由: Microsoft Defender ウイルス対策の有効期限が切れる理由。</dt>
<dt>有効期限: Microsoft Defender ウイルス対策の有効期限が切れる日付。</dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1045">イベント ID: 5101</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="6a5ef-1046">記号名:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1048">メッセージ:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="6a5ef-1049">
<b>マルウェア対策プラットフォームの有効期限が切れています。 </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1050">説明:</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="6a5ef-1051">Microsoft Defender ウイルス対策の猶予期間が切れています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="6a5ef-1052">ウイルス、スパイウェア、その他の望ましくない可能性のあるソフトウェアに対する保護が無効になります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="6a5ef-1053">
<dt>有効期限の理由:</dt>
<dt>有効期限: </dt>
<dt>エラー コード: エラー コード &lt; &gt; 脅威の状態に関連付けられている結果コード。標準の HRESULT 値。</dt>
<dt>エラーの説明: &lt;エラーの &gt; 説明 エラーの説明。 </dt>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="6a5ef-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender ウイルス対策クライアントのエラー コード Microsoft Defender ウイルス対策で問題が発生した場合は、通常、問題のトラブルシューティングに役立つエラー コードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="6a5ef-1055">ほとんどの場合、エラーは更新プログラムのインストールに問題が発生したという意味です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="6a5ef-1056">このセクションでは、Microsoft Defender ウイルス対策クライアント エラーに関する次の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="6a5ef-1057">-   エラー コード -   エラーの考えられる理由 -   今すぐ実行する操作に関するアドバイス</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="6a5ef-1058">次の表の情報を使用して、Microsoft Defender ウイルス対策エラー コードのトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1059">エラー コード: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-1060">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1060">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1062">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="6a5ef-1063">このエラーは、メモリが使い切れている可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="6a5ef-1064">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="6a5ef-1065">デバイスで使用可能なメモリを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="6a5ef-1066">実行中の未使用のアプリケーションを閉じて、デバイス上のメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="6a5ef-1067">デバイスを再起動し、スキャンを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1068">エラー コード: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="6a5ef-1069">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1069">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1071">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1072">このエラーは、セキュリティ製品に問題がある可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="6a5ef-1073">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="6a5ef-1074">定義を更新します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1074">Update the definitions.</span></span> <span data-ttu-id="6a5ef-1075">いずれも：</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1075">Either:</span></span><ol>
<li><span data-ttu-id="6a5ef-1076">Microsoft Defender <b>ウイルス対策の [更新]</b> タブにある [ <b>定義の更新</b> ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="6a5ef-1077">または、</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1077">Or,</span></span>
</li>
<li><span data-ttu-id="6a5ef-1078">Microsoft セキュリティ インテリジェンス サイトから最新の定義 <a href="https://aka.ms/wdsi">をダウンロードします</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="6a5ef-1079">注: サイトからダウンロードされる定義ファイルのサイズは 60 MB を超える場合があります。定義を更新するための長期的なソリューションとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="6a5ef-1080">フル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="6a5ef-1081">デバイスを再起動し、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1082">エラー コード: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="6a5ef-1083">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1083">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1085">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1086">このエラーは、エンジン構成エラーが発生している可能性を示します。一般に、これはエンジンが正しく機能しない入力データに関連しています。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1087">エラー コード: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1088">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1088">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1090">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1091">このエラーは、Microsoft Defender ウイルス対策が脅威の検疫に失敗したと示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1092">エラー コード: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1093">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1093">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1095">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1096">このエラーは、脅威の削除を完了するために再起動が必要な場合を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="6a5ef-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1098">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1098">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1100">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1101">このエラーは、脅威がメディアに存在しなくなったか、マルウェアがデバイスのスキャンを停止している可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="6a5ef-1102">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="6a5ef-1103">Microsoft Safety <a href="https://www.microsoft.com/security/scanner/default.aspx">Scanner を実行し</a> 、セキュリティ ソフトウェアを更新し、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1104">エラー コード: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="6a5ef-1105">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1105">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1107">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1108">このエラーは、システム全体のスキャンが必要な可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="6a5ef-1109">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1109">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1110">完全なシステム スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1111">エラー コード: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1112">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1112">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1114">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1115">このエラーは、脅威の削除を完了するために手動の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1116">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1116">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1117">Microsoft マルウェア保護百科事典で説明されている手動 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">修復手順に従います</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="6a5ef-1118">イベント履歴には、脅威固有のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1119">エラー コード: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1120">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1120">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1122">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1123">このエラーは、コンテナーの種類内の削除がサポートされていない可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1124">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1124">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1125">Microsoft Defender ウイルス対策では、アーカイブ内で検出された脅威を修復できない。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="6a5ef-1126">検出されたリソースを手動で削除する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1127">エラー コード: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1128">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1128">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1130">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1131">このエラーは、低および中規模の脅威の削除が無効になる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1132">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1132">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1133">検出された脅威を確認し、必要に応じて解決します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1134">エラー コード: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1135">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1135">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1137">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1138">このエラーは、脅威が必要な再スキャンを示します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1139">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1139">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1140">完全なシステム スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1141">エラー コード: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1142">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1142">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="6a5ef-1144">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1145">このエラーは、オフライン スキャンが必要な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1146">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1146">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1147">オフラインで Microsoft Defender ウイルス対策を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="6a5ef-1148">これを行う方法については、オフラインの <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Microsoft Defender ウイルス対策の記事をご覧ください</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="6a5ef-1149">エラー コード: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="6a5ef-1150">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1150">Message</span></span></td>
<td><span data-ttu-id="6a5ef-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="6a5ef-1152">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="6a5ef-1153">このエラーは、Microsoft Defender Antivirus が現在のバージョンのプラットフォームをサポートしていないので、新しいバージョンのプラットフォームが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="6a5ef-1154">解決方法</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1154">Resolution</span></span></td><td>
<span data-ttu-id="6a5ef-1155">Windows 10 でのみ Microsoft Defender ウイルス対策を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="6a5ef-1156">Windows 7 Windows 8 Windows Vista の場合は <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">、System Center Endpoint Protection を使用できます</a>。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="6a5ef-1157">

<a id="internal-error-codes"></a> Microsoft Defender ウイルス対策の内部テストでは、次のエラー コードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="6a5ef-1158">これらのエラーが表示された場合は、定義を[](manage-updates-baselines-microsoft-defender-antivirus.md)更新し、エンドポイントで直接再スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="6a5ef-1159">内部エラー コード</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="6a5ef-1160"><b>エラー コード</b></span><span class="sxs-lookup"><span data-stu-id="6a5ef-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="6a5ef-1161">表示されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1161">Message displayed</span></span></th>
<th><span data-ttu-id="6a5ef-1162">エラーと解決の考えられる理由</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="6a5ef-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-1165">インターネット接続を確認してから、もう一度スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="6a5ef-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="6a5ef-1168">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1168">This is an internal error.</span></span> <span data-ttu-id="6a5ef-1169">原因が明確に定義されていません。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="6a5ef-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="6a5ef-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="6a5ef-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="6a5ef-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="6a5ef-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="6a5ef-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="6a5ef-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="6a5ef-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="6a5ef-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="6a5ef-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="6a5ef-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="6a5ef-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="6a5ef-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="6a5ef-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="6a5ef-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="6a5ef-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="6a5ef-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="6a5ef-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="6a5ef-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="6a5ef-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="6a5ef-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="6a5ef-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="6a5ef-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="6a5ef-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="6a5ef-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="6a5ef-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="6a5ef-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="6a5ef-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="6a5ef-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="6a5ef-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="6a5ef-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="6a5ef-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="6a5ef-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="6a5ef-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-1238">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1238">This is an internal error.</span></span> <span data-ttu-id="6a5ef-1239">マルウェアの削除が成功しなかった場合にトリガーされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="6a5ef-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="6a5ef-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="6a5ef-1242">これは内部エラーです。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1242">This is an internal error.</span></span> <span data-ttu-id="6a5ef-1243">スキャンが完了しないときにトリガーされた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="6a5ef-1244">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1244">Related topics</span></span>

- [<span data-ttu-id="6a5ef-1245">Microsoft Defender ウイルス対策保護に関するレポート</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6a5ef-1246">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="6a5ef-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)