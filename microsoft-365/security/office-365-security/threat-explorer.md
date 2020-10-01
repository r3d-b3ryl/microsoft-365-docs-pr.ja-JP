---
title: 脅威エクスプローラーとリアルタイム検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティコンプライアンスセンターでエクスプローラおよびリアルタイム検出を使用して、 &amp; 効果的かつ効率的に脅威を調査して対応する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32ff9f2c8d009b4c9b05c12ba4e785e59cb182e7
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328085"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="11bf8-103">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="11bf8-103">Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="11bf8-104">組織で [office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) を使用しており、 [必要なアクセス許可](#required-licenses-and-permissions)がある場合は、 **Explorer** または **リアルタイムの検出** (以前の *リアルタイムのレポート* - [新機能を参照](#new-features-in-threat-explorer-and-real-time-detections)) があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="11bf8-105">[セキュリティ & コンプライアンスセンター] で、[ **脅威の管理**] に移動してから、[ **エクスプローラー** ] _または_[ **リアルタイムの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="11bf8-106">ATP プラン2を使用すると、次のように表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-106">With ATP Plan 2, you see:</span></span>|<span data-ttu-id="11bf8-107">ATP プラン1では、次のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-107">With ATP Plan 1, you see:</span></span>|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="11bf8-110">エクスプローラー (リアルタイム検出) を使用すると、強力なレポートが得られます。これにより、セキュリティ運用チームは脅威を調査して効果的かつ効率的に対処することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="11bf8-111">このレポートは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-111">The report resembles the following image:</span></span>

![[脅威管理エクスプローラー] に移動します。 \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="11bf8-113">このレポートでは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-113">With this report, you can:</span></span>

- [<span data-ttu-id="11bf8-114">Microsoft 365 セキュリティ機能によって検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="11bf8-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="11bf8-115">[フィッシング Url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)</span><span class="sxs-lookup"><span data-stu-id="11bf8-115">[View data about phishing URLs and click verdict](#view-data-about-phishing-urls-and-click-verdict)</span></span>
- <span data-ttu-id="11bf8-116">[エクスプローラーのビューから自動化された調査と応答プロセスを開始](#start-automated-investigation-and-response) する (ATP プラン2のみ)</span><span class="sxs-lookup"><span data-stu-id="11bf8-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="11bf8-117">...[悪意のある電子メールの調査など](#more-ways-to-use-explorer-or-real-time-detections)</span><span class="sxs-lookup"><span data-stu-id="11bf8-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="11bf8-118">脅威エクスプローラーおよびリアルタイム検出の機能が向上しました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-118">Experience Improvements to Threat Explorer and Real-Time Detections</span></span>

<span data-ttu-id="11bf8-119">探しているプロセスの改善の一環として、脅威エクスプローラーとリアルタイム検出にいくつかの更新プログラムを適用しました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-119">As part of improving the hunting process, we have made a few updates to Threat Explorer and Real-Time Detections.</span></span> <span data-ttu-id="11bf8-120">これらの機能が向上しており、探し方がより一貫しています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-120">These are ‘experience’ improvements, with the focus on making the hunting experience more consistent.</span></span> <span data-ttu-id="11bf8-121">これらの変更について、以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-121">These changes are outlined below:</span></span>

- [<span data-ttu-id="11bf8-122">タイムゾーンの向上</span><span class="sxs-lookup"><span data-stu-id="11bf8-122">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="11bf8-123">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="11bf8-123">Update in the Refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="11bf8-124">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="11bf8-124">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="11bf8-125">製品情報の更新</span><span class="sxs-lookup"><span data-stu-id="11bf8-125">In product information updates</span></span>](#in-product-information-updates)

### <a name="timezone-improvements"></a><span data-ttu-id="11bf8-126">タイムゾーンの向上</span><span class="sxs-lookup"><span data-stu-id="11bf8-126">Timezone improvements</span></span>

<span data-ttu-id="11bf8-127">ポータル内の電子メールレコードのタイムゾーンと、エクスポートされたデータについても説明します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-127">We will show the timezone for the email records within the Portal, as well as for Exported data.</span></span> <span data-ttu-id="11bf8-128">タイムゾーンは、電子メールグリッド、詳細ポップアップ、電子メールのタイムライン、類似の電子メールなどのエクスペリエンス間で表示されるので、結果セットのタイムゾーンはユーザーに対してクリアされます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-128">The timezone will be visible across experiences like Email Grid, Details Flyout, Email Timeline, and Similar Emails, so that the timezone for the result set is clear to the user.</span></span>

![エクスプローラーでのタイムゾーンの表示](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="11bf8-130">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="11bf8-130">Update in the Refresh process</span></span>

<span data-ttu-id="11bf8-131">自動更新 (日付の変更、ページの更新)、手動更新 (他のフィルターの場合) との混同に関するフィードバックをお寄せください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-131">We have heard feedback around confusion with automatic refresh (e.g. for date, as soon as you change the date, the page would refresh) and manual refresh (for other filters).</span></span> <span data-ttu-id="11bf8-132">同様に、フィルターを削除すると自動更新になるため、クエリを変更している間に異なるフィルターを変更すると、検索に一貫性がないことがあります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-132">Similarly, removing filters leads to automatic refresh, this causes situations where changing the different filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="11bf8-133">この問題を解決するには、手動のフィルターメカニズムに移行します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-133">To solve this, we are moving to a manual filtering mechanism.</span></span>
<span data-ttu-id="11bf8-134">経験の観点から見ると、ユーザーはさまざまなフィルター範囲 (フィルタセット、日付) を適用および削除し、[refresh] ボタンを押して、クエリの定義によって結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-134">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set, and date), and press the refresh button to filter the results once they are done with defining the query.</span></span> <span data-ttu-id="11bf8-135">[更新] ボタンも、画面上で明確に呼び出されるように更新されています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-135">The refresh button has also been updated to call it out clearly on the screen.</span></span> <span data-ttu-id="11bf8-136">また、この変更に関するツールヒントと製品内のドキュメントも更新しました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-136">We have also updated tooltips and in-product documentation around this change.</span></span>

![[更新] をクリックして結果をフィルター処理する](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="11bf8-138">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="11bf8-138">Chart drilldown to add to filters</span></span>

<span data-ttu-id="11bf8-139">グラフの凡例値をクリックして、その値をフィルターとして追加できるようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-139">You will now be able to click on the chart legend values to add that value as a filter.</span></span> <span data-ttu-id="11bf8-140">なお、上記で説明した変更の一部として結果をフィルター処理するには、[更新] ボタンをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-140">Note that you will still have to click on the refresh button to filter the results as part of the change described above.</span></span>

![グラフからフィルター処理するドリルダウン](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a><span data-ttu-id="11bf8-142">製品情報の更新</span><span class="sxs-lookup"><span data-stu-id="11bf8-142">In product information updates</span></span>

<span data-ttu-id="11bf8-143">また、製品内の追加の詳細も表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-143">You should also see additional details within the product.</span></span> <span data-ttu-id="11bf8-144">たとえば、グリッド内の検索結果の合計数 (下を参照) に加えて、ラベル、エラーメッセージ、および結果セットについての詳細情報を提供するために、ラベルを中心とした改良が行われました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-144">For example, the total number of search results within grid (see below), as well as improvements around labels, error messages and tooltips, to give more information around filters, search experience, and result set.</span></span>

![製品情報の表示](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="11bf8-146">脅威エクスプローラーの拡張機能</span><span class="sxs-lookup"><span data-stu-id="11bf8-146">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="11bf8-147">上位の対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="11bf8-147">Top targeted users</span></span>

<span data-ttu-id="11bf8-148">今日は、上位の対象ユーザーの一覧を電子メール用のマルウェアビュー ([上位のマルウェアファミリ] セクション内) に公開しています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-148">Today we expose the list of the top targeted users in the Malware View for Emails (within the Top Malware Families section).</span></span> <span data-ttu-id="11bf8-149">フィッシングおよびすべての電子メールビューでこのビューを拡張します。上位5つの対象ユーザーと、対応するビューの各ユーザーの試行回数 (たとえば、フィッシングビューの場合はフィッシング試行回数を表示できます) を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-149">We will be extending this view within Phish and All Email views as well, where you will be able to see the top five targeted users along with the number of attempts for each user for the corresponding view (for example, for Phish view you will be able to see the number of Phish attempts).</span></span>
<span data-ttu-id="11bf8-150">また、対象ユーザーの一覧を、各電子メールビューのオフライン分析の試行回数に合わせて、3000の制限までエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-150">You will also be able to export the list of targeted users up to a limit of 3000 along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="11bf8-151">それに加えて、[いいえ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-151">In addition to that, selecting No.</span></span> <span data-ttu-id="11bf8-152">試行回数 (たとえば、13回以下の場合) では、脅威エクスプローラーでフィルター処理されたビューが開き、電子メールとそのユーザーの脅威の詳細を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-152">of attempts (for example, 13 attempts below) would open a filtered view in Threat Explorer, so that you can look at more details across emails and threats for that user.</span></span>

![上位の対象ユーザー](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a><span data-ttu-id="11bf8-154">Exchange トランスポートルール</span><span class="sxs-lookup"><span data-stu-id="11bf8-154">Exchange transport rules</span></span>
<span data-ttu-id="11bf8-155">データエンリッチメントの一部として、メッセージに適用されたさまざまなトランスポートルールを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-155">As part of data enrichment, you should also be able to see all the different transport rules which were applied to a message.</span></span> <span data-ttu-id="11bf8-156">この情報は、電子メールのグリッドビュー内に表示されます (これを表示するには、グリッドの [列] オプションから [列のオプション] を選択します)、および電子メールの詳細ポップアップを表示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-156">This information will be present within the Email grid view (to view this, select Column options in the grid and add Exchange Transport Rule from the Column options in the grid) as well as Details flyout in the email.</span></span>
<span data-ttu-id="11bf8-157">GUID だけでなく、メッセージに適用されたトランスポートルールの名前も表示できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-157">You would be able to see both the GUID as well as the name of the transport rules which were applied to the message.</span></span> <span data-ttu-id="11bf8-158">また、トランスポートルールの名前を使用してメッセージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-158">Additionally, you would be able to search for the messages using the name of the transport rule.</span></span> <span data-ttu-id="11bf8-159">これは、「Contains」検索であり、部分的な検索を使用して検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-159">This would be a ‘Contains’ search which means you will be able to search using partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="11bf8-160">重要な注意事項:</span><span class="sxs-lookup"><span data-stu-id="11bf8-160">Important Note:</span></span>
<span data-ttu-id="11bf8-161">ETR の検索と名前の可用性は、自分に割り当てられている特定の役割によって異なります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-161">ETR search and name availability would depend on the specific role that has been assigned to you.</span></span> <span data-ttu-id="11bf8-162">ETR の名前と検索を表示するには、次の役割/アクセス許可のいずれかを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-162">You will need to have one of the following roles/permissions in order to view the ETR names and search.</span></span>  <span data-ttu-id="11bf8-163">次の役割が割り当てられていない場合は、トランスポートルールの名前を表示することはできません。また、ETR 名を使用してメッセージを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-163">If you do not have any of the following roles assigned to you, you will not be able to see the names of the transport rules, and search for the messages using the ETR names.</span></span> <span data-ttu-id="11bf8-164">ただし、電子メールの詳細内に ETR ラベルと GUID 情報が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-164">However, you will be able to see the ETR label and GUID information within the Email Details.</span></span> <span data-ttu-id="11bf8-165">電子メールのグリッド、電子メールの flyouts、フィルター、エクスポートには影響しません。</span><span class="sxs-lookup"><span data-stu-id="11bf8-165">Your other experiences around viewing records in Email Grids, Email flyouts, Filters, and Export are not impacted.</span></span>

- <span data-ttu-id="11bf8-166">EXO Only-データ損失防止: すべて</span><span class="sxs-lookup"><span data-stu-id="11bf8-166">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="11bf8-167">EXO Only-O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="11bf8-167">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="11bf8-168">AAD または EXO-Security Admin: All</span><span class="sxs-lookup"><span data-stu-id="11bf8-168">AAD or EXO - Security Admin: All</span></span>
- <span data-ttu-id="11bf8-169">AAD または EXO-Security Reader: All</span><span class="sxs-lookup"><span data-stu-id="11bf8-169">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="11bf8-170">EXO Only-トランスポートルール: すべて</span><span class="sxs-lookup"><span data-stu-id="11bf8-170">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="11bf8-171">EXO Only-表示のみの構成: すべて</span><span class="sxs-lookup"><span data-stu-id="11bf8-171">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="11bf8-172">次に示すように、電子メールグリッド、詳細ポップアップ、およびエクスポートされた CSV 内で、Etr に Name/GUID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-172">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

![Exchange トランスポートルール](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a><span data-ttu-id="11bf8-174">受信コネクタ</span><span class="sxs-lookup"><span data-stu-id="11bf8-174">Inbound connectors</span></span>

<span data-ttu-id="11bf8-175">コネクタは、Microsoft 365 または Office 365 組織からの電子メールの流れをカスタマイズし、任意のセキュリティ制限または制御を適用できるようにする命令の集合です。</span><span class="sxs-lookup"><span data-stu-id="11bf8-175">Connectors are a collection of instructions that customize the way your email flows to and from your Microsoft 365 or Office 365 organization, with the ability to apply any security restriction or controls.</span></span> <span data-ttu-id="11bf8-176">脅威エクスプローラーで、メールに関連付けられているコネクタを表示したり、コネクタ名を使用してメールを検索したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-176">Within Threat Explorer, you will now have the ability to view the connectors which are related to an email as well as search for emails using the connector names.</span></span>
<span data-ttu-id="11bf8-177">コネクタの検索は、部分的なキーワード検索でも同様に機能するという点で、' Contains ' です。</span><span class="sxs-lookup"><span data-stu-id="11bf8-177">The search for connectors is ‘Contains’ in nature which means partial keyword searches should work as well.</span></span>
<span data-ttu-id="11bf8-178">次に示すように、メインのグリッドビュー、詳細のポップアップ、およびエクスポートされた CSV の中で、名前/GUID 形式でコネクタを表示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-178">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown below:</span></span>

![コネクタの詳細](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="11bf8-180">脅威エクスプローラおよびリアルタイム検出の新機能</span><span class="sxs-lookup"><span data-stu-id="11bf8-180">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="11bf8-181">脅威エクスプローラーとリアルタイム検出に追加された3つの新機能:</span><span class="sxs-lookup"><span data-stu-id="11bf8-181">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="11bf8-182">メールヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="11bf8-182">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="11bf8-183">電子メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="11bf8-183">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="11bf8-184">URL のエクスポートクリックデータ</span><span class="sxs-lookup"><span data-stu-id="11bf8-184">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="11bf8-185">これらの新機能について、以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-185">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="11bf8-186">メールヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="11bf8-186">Preview email header and download email body</span></span>

<span data-ttu-id="11bf8-187">電子メールヘッダーをプレビューして電子メール本文をダウンロードする機能は、脅威エクスプローラーで利用できる新機能です。</span><span class="sxs-lookup"><span data-stu-id="11bf8-187">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="11bf8-188">管理者は、ダウンロードしたヘッダーや電子メールメッセージを分析して脅威を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-188">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="11bf8-189">電子メールメッセージをダウンロードすると情報の公開が危険になる可能性があるため、このプロセスは、役割ベースのアクセス制御 (RBAC) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-189">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="11bf8-190">新しい役割である [ *プレビュー*] を別の役割グループ (セキュリティ操作やセキュリティ管理者など) に追加して、すべての電子メールメッセージビューでメールのダウンロードとヘッダーのプレビューを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-190">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="11bf8-191">しかし、エクスプローラー (およびリアルタイム検出) によって新しい新しいフィールドも追加され、電子メールメッセージがどこにいるかをより完全に把握することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-191">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="11bf8-192">この変更の目的の一環として、セキュリティを確保したユーザーを探しやすくしていますが、最終的に問題の電子メールメッセージの場所がひとめでわかることになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-192">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="11bf8-193">実行方法</span><span class="sxs-lookup"><span data-stu-id="11bf8-193">How is this done?</span></span> <span data-ttu-id="11bf8-194">配信状態は、次の2つの列に分けられました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-194">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="11bf8-195">**配信アクション** -この電子メールの状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="11bf8-195">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="11bf8-196">**配信場所** -この電子メールは、結果としてルーティングされましたか?</span><span class="sxs-lookup"><span data-stu-id="11bf8-196">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="11bf8-197">配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="11bf8-197">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="11bf8-198">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11bf8-198">Here are the possible actions an email can take:</span></span>

|<span data-ttu-id="11bf8-199">届け</span><span class="sxs-lookup"><span data-stu-id="11bf8-199">Delivered</span></span>|<span data-ttu-id="11bf8-200">Junked</span><span class="sxs-lookup"><span data-stu-id="11bf8-200">Junked</span></span>|<span data-ttu-id="11bf8-201">Blocked</span><span class="sxs-lookup"><span data-stu-id="11bf8-201">Blocked</span></span>|<span data-ttu-id="11bf8-202">換わり</span><span class="sxs-lookup"><span data-stu-id="11bf8-202">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="11bf8-203">電子メールがユーザーの受信トレイまたはフォルダーに配信され、ユーザーが直接アクセスできる。</span><span class="sxs-lookup"><span data-stu-id="11bf8-203">Email was delivered to Inbox or folder of a user and the user can directly access it.</span></span>|<span data-ttu-id="11bf8-204">電子メールは、ユーザーの迷惑メールフォルダーまたは削除されたフォルダーに送信され、ユーザーはそのフォルダー内のメールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-204">Email was sent to either user’s Junk folder or Deleted folder, and the user has access to emails in those folders.</span></span>|<span data-ttu-id="11bf8-205">検疫済み、失敗した、または削除されたメール。</span><span class="sxs-lookup"><span data-stu-id="11bf8-205">Any emails that are quarantined, that  failed, or were dropped.</span></span> <span data-ttu-id="11bf8-206">ユーザーが完全にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11bf8-206">This is completely inaccessible by the user!</span></span>|<span data-ttu-id="11bf8-207">悪意のある添付ファイルが存在するという悪意のある添付ファイルが .txt ファイルに置き換えられる電子メール。</span><span class="sxs-lookup"><span data-stu-id="11bf8-207">Any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>|

|<span data-ttu-id="11bf8-208">届け</span><span class="sxs-lookup"><span data-stu-id="11bf8-208">Delivered</span></span>|<span data-ttu-id="11bf8-209">Junked</span><span class="sxs-lookup"><span data-stu-id="11bf8-209">Junked</span></span>|<span data-ttu-id="11bf8-210">Blocked</span><span class="sxs-lookup"><span data-stu-id="11bf8-210">Blocked</span></span>|<span data-ttu-id="11bf8-211">換わり</span><span class="sxs-lookup"><span data-stu-id="11bf8-211">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="11bf8-212">電子メールがユーザーの受信トレイまたは別のフォルダーに配信され、ユーザーが直接アクセスできる。</span><span class="sxs-lookup"><span data-stu-id="11bf8-212">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>|<span data-ttu-id="11bf8-213">電子メールは、ユーザーの迷惑メールフォルダーまたは削除されたフォルダーに送信され、ユーザーはそのフォルダー内の電子メールメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-213">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>|<span data-ttu-id="11bf8-214">検疫された、失敗した、または削除された電子メールメッセージで、ユーザーがアクセスできないメッセージ。</span><span class="sxs-lookup"><span data-stu-id="11bf8-214">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>|<span data-ttu-id="11bf8-215">添付ファイルが悪意のある添付ファイルであることを示す、悪意のある添付ファイルが .txt ファイルに置き換えられた電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="11bf8-215">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="11bf8-216">次に、ユーザーが表示できる機能と、それができないことを示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-216">And here is what the user can see, and what they can't:</span></span>

|<span data-ttu-id="11bf8-217">エンドユーザーがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="11bf8-217">Accessible to end users</span></span>|<span data-ttu-id="11bf8-218">エンドユーザーがアクセスできない</span><span class="sxs-lookup"><span data-stu-id="11bf8-218">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="11bf8-219">届け</span><span class="sxs-lookup"><span data-stu-id="11bf8-219">Delivered</span></span>|<span data-ttu-id="11bf8-220">Blocked</span><span class="sxs-lookup"><span data-stu-id="11bf8-220">Blocked</span></span>|
|<span data-ttu-id="11bf8-221">Junked</span><span class="sxs-lookup"><span data-stu-id="11bf8-221">Junked</span></span>|<span data-ttu-id="11bf8-222">換わり</span><span class="sxs-lookup"><span data-stu-id="11bf8-222">Replaced</span></span>|

<span data-ttu-id="11bf8-223">[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-223">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="11bf8-224">配信アクションにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-224">It's linked to a Delivery Action.</span></span> <span data-ttu-id="11bf8-225">このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-225">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="11bf8-226">配信場所の指定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11bf8-226">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="11bf8-227">**受信トレイまたはフォルダー**: 電子メールは、受信トレイまたはフォルダー (メールルールに従って) にあります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-227">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="11bf8-228">**オンプレミスまたは外部**: メールボックスはクラウド上に存在していますが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-228">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="11bf8-229">**迷惑メールフォルダー**: メールはユーザーの [迷惑メール] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-229">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="11bf8-230">**削除済みアイテムフォルダー**: ユーザーの [削除済みアイテム] フォルダー内の電子メール。</span><span class="sxs-lookup"><span data-stu-id="11bf8-230">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="11bf8-231">**検疫**: 検疫内の電子メールは、ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="11bf8-231">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="11bf8-232">**失敗**: メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="11bf8-232">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="11bf8-233">**削除**: メールフロー内の任意の場所に電子メールが失われます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-233">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="11bf8-234">電子メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="11bf8-234">Email timeline</span></span>

<span data-ttu-id="11bf8-235">**電子メールのタイムライン**は、管理者にとって、探しやすさを向上させるための別の新しいエクスプローラー機能です。</span><span class="sxs-lookup"><span data-stu-id="11bf8-235">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="11bf8-236">イベントを理解するためにさまざまな場所をチェックするのにかかる時間が短くなるため、ランダム化が減少します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-236">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="11bf8-237">複数のイベントが電子メールで同時に発生するか、または同じ時刻に終了すると、これらのイベントがタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-237">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="11bf8-238">実際、メールへの配信の後に発生する一部のイベントは、[特殊な操作] 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-238">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="11bf8-239">メールのタイムラインからの情報をメールの送信後の特別なアクションと組み合わせることにより、管理者は、ポリシーがどのように機能するか、メールが最後にルーティングされたか、場合によっては最終的な評価がどのようなものかを把握できるようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-239">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="11bf8-240">悪意のある電子メールメッセージの調査の詳細については、「 [Office 365 で配信された悪意のある電子メールを調査および修復する](investigate-malicious-email-that-was-delivered.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-240">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="11bf8-241">URL のエクスポートクリックデータ</span><span class="sxs-lookup"><span data-stu-id="11bf8-241">Export URL click data</span></span>

<span data-ttu-id="11bf8-242">また、ネットワークメッセージ ID とそのクリック Verdict の両方を表示するために、URL クリックのレポートを Microsoft Excel にエクスポートできるようになりました。これにより、URL のクリック時のトラフィックが簡単になることを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-242">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="11bf8-243">そのしくみは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11bf8-243">Here's how it works.</span></span> <span data-ttu-id="11bf8-244">Office 365 のクイック起動での脅威管理の開始で、次のチェーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-244">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="11bf8-245">**エクスプローラー** \>**フィッシング** \> の表示**クリック** \>**上位の url または url の先頭クリック** \>**任意のレコードをクリックして URL フライアウトを開く**</span><span class="sxs-lookup"><span data-stu-id="11bf8-245">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="11bf8-246">一覧の URL をクリックすると、フライアウトパネルに新しい [エクスポート] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-246">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="11bf8-247">このボタンを使用して、レポートを容易にするために、データを Excel スプレッドシートに移動します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-247">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="11bf8-248">リアルタイムの検出レポートでは、次のように同じ場所にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-248">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="11bf8-249">**エクスプローラー** \>**リアルタイムの検出** \>**フィッシング** \> の表示**Url** \>**トップの url またはクリック** \>**任意のレコードをクリックして URL フライアウト** \> を開く[**クリック] タブに移動します。**</span><span class="sxs-lookup"><span data-stu-id="11bf8-249">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="11bf8-250">ネットワークメッセージ ID エクスプローラーまたは関連するサードパーティ製のツールでネットワークメッセージ ID を使用して検索したときに、[クリック戻る] を特定のメールにマップします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-250">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="11bf8-251">ネットワークのメッセージ ID を検索すると、クリックの結果に関連付けられた特定の電子メールが管理者に付与されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-251">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="11bf8-252">エクスポートが行われると、ネットワークメッセージ ID の相関 id があるため、より迅速かつ強力な分析が可能になります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-252">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![エクスプローラーの [タブ] をクリックします。](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="11bf8-254">テクノロジによる電子メールで検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="11bf8-254">See malware detected in email by technology</span></span>

<span data-ttu-id="11bf8-255">Microsoft 365 テクノロジを使用して、電子メールで検出されたマルウェアを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-255">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="11bf8-256">これを行うには、エクスプローラーの [ [電子メール > マルウェア](threat-explorer-views.md#email--malware) ] ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-256">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="11bf8-257">セキュリティ & コンプライアンスセンター () で [https://protection.office.com](https://protection.office.com) 、[**脅威管理**  >  **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-257">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="11bf8-258">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-258">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="11bf8-259">[**表示**] メニューで、[**電子メール**  >  **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-259">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="11bf8-261">[**送信者**] をクリックし、[**基本**  >  **検出テクノロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-261">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="11bf8-262">これで、検出テクノロジがレポートのフィルターとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-262">Your detection technologies are now available as filters for the report.</span></span>

   ![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="11bf8-264">オプションを選択し、[ **更新** ] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-264">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![選択されている検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="11bf8-266">レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-266">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="11bf8-267">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-267">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="11bf8-268">フィッシング Url に関するデータを表示し、[verdict] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-268">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="11bf8-269">許可された Url の一覧を含む、電子メール内の Url によるフィッシングの試行、禁止、および上書きを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-269">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="11bf8-270">クリックされた Url を識別するには、 [安全なリンク](atp-safe-links.md) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-270">Identifying URLs that were clicked requires [Safe Links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="11bf8-271">[安全なリンクを使用して verdicts] をクリックしたときに、 [安全なリンクポリシー](set-up-atp-safe-links-policies.md) が設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-271">Make sure that you have set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="11bf8-272">メッセージ内のフィッシング Url を確認し、フィッシングメッセージで Url をクリックするには、Explorer の [電子メール > フィッシング](threat-explorer-views.md#email--phish) ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-272">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="11bf8-273">セキュリティ & コンプライアンスセンター () で [https://protection.office.com](https://protection.office.com) 、[**脅威管理**  >  **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-273">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="11bf8-274">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-274">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="11bf8-275">[**表示**] メニューの [**電子メール**フィッシング] をクリックし  >  **Phish**ます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-275">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="11bf8-277">[**送信者**] をクリックし、[ **url**] を選択して、  >  **[verdict] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-277">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="11bf8-278">1つまたは複数のオプション ([ **ブロック** されて **ブロック**する] など) を選択し、[ **更新** ] ボタンをクリックして、そのフィルターを適用するオプションと同じ行にあるものをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-278">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="11bf8-279">(ブラウザーウィンドウを更新しないでください)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-279">(Don't refresh your browser window.)</span></span>

   ![Url および [verdicts] をクリックします。](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="11bf8-281">レポートが更新され、[URL] タブにレポートの下に2つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-281">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="11bf8-282">**トップ url** は、フィルター処理されたメッセージに含まれる url と、各 url の電子メール配信アクション数を示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-282">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="11bf8-283">[フィッシング email] ビューには、通常、正当な Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-283">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="11bf8-284">攻撃者は、適切な Url と正しくない Url をメッセージに混在させて配信を試みることができますが、ユーザーがクリックすると、悪意のあるリンクがより興味深いものになります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-284">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="11bf8-285">Url の表は、電子メールの合計数によって並べ替えられます (ただし、ビューを簡略化するため、この列は非表示になっていることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-285">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="11bf8-286">**トップクリック** は、クリックされた url をラップした安全なリンクです。 [合計] をクリックします (この列はビューを簡略化するためにも表示されません)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-286">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="11bf8-287">列別の合計カウント [セーフリンク] は、クリックされた各 URL の [verdict count] を示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-287">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="11bf8-288">フィッシングの電子メール表示では、多くの場合、疑わしいまたは悪意のある Url になりますが、脅威ではないがフィッシングメッセージ内にある Url を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-288">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="11bf8-289">ラップされていないリンクの URL クリックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="11bf8-289">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="11bf8-290">2つの URL 表は、配信アクションと場所によって、フィッシング電子メールメッセージの上位の Url を示しています。また、ブロックされた (または警告によってアクセスされた) URL クリックが表示されるので、ユーザーがどのような潜在的なリンクを受信し、ユーザーが操作したかを把握できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-290">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="11bf8-291">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-291">From here, you can conduct further analysis.</span></span> <span data-ttu-id="11bf8-292">たとえば、グラフの下に、組織の環境でブロックされた電子メールメッセージ内の上位の Url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-292">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![ブロックされたエクスプローラーの Url](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="11bf8-294">URL を選択して、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-294">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11bf8-295">URL のポップアップダイアログで、電子メールメッセージのフィルター処理が削除され、環境内の URL の公開が完全に表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-295">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="11bf8-296">これにより、関心のあるメールメッセージをエクスプローラーでフィルター処理し、潜在的な脅威である特定の Url を見つけ、URL フィルターをエクスプローラービュー自体に追加することなく、環境内の URL の公開について理解を深めることができます (URL の詳細ダイアログを使用)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-296">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-different-click-verdicts"></a><span data-ttu-id="11bf8-297">さまざまなクリック verdicts の解釈</span><span class="sxs-lookup"><span data-stu-id="11bf8-297">Interpretation of different click verdicts</span></span>

<span data-ttu-id="11bf8-298">電子メールまたは URL flyouts 内でのトップクリックとフィルタリングエクスペリエンスの範囲内で、お探しのエクスペリエンスの一部として異なるクリック値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-298">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you will see different click values as part of your hunting experience.</span></span> <span data-ttu-id="11bf8-299">次に、クリック Verdicts に指定できる値とその解釈を示します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-299">Below are the possible values of Click Verdicts and their interpretation:</span></span>

- <span data-ttu-id="11bf8-300">**None**: URL の verdict をキャプチャできませんでした。</span><span class="sxs-lookup"><span data-stu-id="11bf8-300">**None**: We were unable to capture the verdict for the URL.</span></span> <span data-ttu-id="11bf8-301">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-301">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="11bf8-302">**許可**: ユーザーは URL への移動を許可されました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-302">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="11bf8-303">[**ブロック**済み: ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-303">**Blocked**: The User was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="11bf8-304">**保留中の verdict**: ユーザーに分析保留中ページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-304">**Pending verdict**: The user was presented with the detonation pending page.</span></span>
- <span data-ttu-id="11bf8-305">**ブロック**されたオーバーライド: ユーザーは URL への移動をブロックされました。ただし、ユーザーはオーバーライドをブロックして、URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-305">**Blocked overridden**: The user was blocked from navigating to the URL; however, the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="11bf8-306">**Pending verdict バイパス**: ユーザーが分析ページで表示されました。ただし、ユーザーはページをオーバーライドして URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-306">**Pending verdict bypassed**: The user was presented with the detonation page; however, the user overrode the page to navigate to the URL.</span></span>
- <span data-ttu-id="11bf8-307">**エラー**: ユーザーにエラーページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-307">**Error**: The user was presented with the error page.</span></span> <span data-ttu-id="11bf8-308">これは、verdict のキャプチャでエラーが発生したことも意味します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-308">This can also mean there was an error in capturing the verdict.</span></span>
- <span data-ttu-id="11bf8-309">**失敗**: verdict のキャプチャ中に不明な例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="11bf8-309">**Failure**: There was unknown exception while capturing the verdict.</span></span> <span data-ttu-id="11bf8-310">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-310">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="11bf8-311">ユーザーが報告した電子メールメッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="11bf8-311">Review email messages reported by users</span></span>

<span data-ttu-id="11bf8-312">組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-312">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="11bf8-313">これを行うには、エクスプローラー (またはリアルタイムの検出) の [電子メール > 提出](threat-explorer-views.md#email--submissions) の表示] を使用します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-313">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="11bf8-314">セキュリティ & コンプライアンスセンター () で [https://protection.office.com](https://protection.office.com) 、[**脅威管理**  >  **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-314">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="11bf8-315">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-315">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="11bf8-316">[**表示**] メニューの [**電子メール**の送信] を選択し  >  **Submissions**ます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-316">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="11bf8-318">[**送信者**] をクリックし、[**基本**レポートの種類] を選択し  >  **Report type**ます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-318">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="11bf8-319">オプション ( **フィッシング**など) を選択し、[ **更新** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11bf8-319">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![ユーザーによって報告されるフィッシング](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="11bf8-321">レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-321">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="11bf8-322">この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](configure-atp-anti-phishing-policies.md)を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-322">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="11bf8-323">自動調査と応答の開始</span><span class="sxs-lookup"><span data-stu-id="11bf8-323">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="11bf8-324">自動化された調査および応答機能は、 **office 365 ATP Plan 2** および **office 365 E5**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-324">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="11bf8-325">(新)自動化された [調査と応答](automated-investigation-response-office.md) によって、セキュリティ運用チームの時間と労力を節約し、cyberattacks を調査および軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-325">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="11bf8-326">セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-326">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="11bf8-327">詳細については、「 [例: セキュリティ管理者がエクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-327">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="11bf8-328">エクスプローラーを使用するその他の方法 (またはリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="11bf8-328">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="11bf8-329">この記事で説明されているシナリオに加えて、エクスプローラー (またはリアルタイムの検出) で利用できるレポートオプションが他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-329">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="11bf8-330">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="11bf8-330">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="11bf8-331">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="11bf8-331">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="11bf8-332">脅威エクスプローラーのビューの概要 (およびリアルタイムの検出) を取得する</span><span class="sxs-lookup"><span data-stu-id="11bf8-332">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="11bf8-333">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="11bf8-333">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="11bf8-334">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="11bf8-334">Required licenses and permissions</span></span>

<span data-ttu-id="11bf8-335">エクスプローラーまたはリアルタイムの検出を取得するには、 [Office 365 ATP](office-365-atp.md) が必要です。</span><span class="sxs-lookup"><span data-stu-id="11bf8-335">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="11bf8-336">Explorer は Office 365 ATP Plan 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-336">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="11bf8-337">リアルタイム検出レポートは、Office 365 ATP Plan 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-337">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="11bf8-338">Office 365 ATP で保護する必要があるすべてのユーザーにライセンスを割り当てることを計画します。</span><span class="sxs-lookup"><span data-stu-id="11bf8-338">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="11bf8-339">(エクスプローラーまたはリアルタイムの検出は、ライセンスが付与されたユーザーの検出データを示します)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-339">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="11bf8-340">エクスプローラーまたはリアルタイム検出を表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-340">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="11bf8-341">セキュリティ &amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-341">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="11bf8-342">組織管理</span><span class="sxs-lookup"><span data-stu-id="11bf8-342">Organization Management</span></span>
  - <span data-ttu-id="11bf8-343">セキュリティ管理者 (Azure Active Directory 管理センターで割り当て [https://aad.portal.azure.com](https://aad.portal.azure.com) 可能)</span><span class="sxs-lookup"><span data-stu-id="11bf8-343">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="11bf8-344">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="11bf8-344">Security Reader</span></span>

- <span data-ttu-id="11bf8-345">Exchange Online の場合は、Exchange 管理センター ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) または PowerShell コマンドレット (「 [Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11bf8-345">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="11bf8-346">組織の管理</span><span class="sxs-lookup"><span data-stu-id="11bf8-346">Organization Management</span></span>
  - <span data-ttu-id="11bf8-347">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="11bf8-347">View-only Organization Management</span></span>
  - <span data-ttu-id="11bf8-348">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="11bf8-348">View-Only Recipients role</span></span>
  - <span data-ttu-id="11bf8-349">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="11bf8-349">Compliance Management</span></span>

<span data-ttu-id="11bf8-350">役割とアクセス許可の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-350">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="11bf8-351">セキュリティ/コンプライアンスセンターのアクセス許可 &amp;</span><span class="sxs-lookup"><span data-stu-id="11bf8-351">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="11bf8-352">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="11bf8-352">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="11bf8-353">脅威エクスプローラーとリアルタイム検出の相違点</span><span class="sxs-lookup"><span data-stu-id="11bf8-353">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="11bf8-354">**リアルタイムの検出**レポートは OFFICE 365 atp plan 1 で利用できますが、**脅威エクスプローラー**は office 365 atp plan 2 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-354">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="11bf8-355">**リアルタイムの検出**レポートを使用すると、検出がリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-355">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="11bf8-356">**脅威エクスプローラー** も同様ですが、特定の攻撃に関する追加の詳細を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="11bf8-356">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="11bf8-357">**すべての電子メール**ビューは、**脅威エクスプローラー**で使用できます (**リアルタイムの検出**レポートには含まれません)。</span><span class="sxs-lookup"><span data-stu-id="11bf8-357">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="11bf8-358">他のフィルター処理機能および使用可能なアクションは、 **脅威エクスプローラー**に含まれています。</span><span class="sxs-lookup"><span data-stu-id="11bf8-358">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="11bf8-359">詳細については、「 [Office 365 Atp サービスの説明: Advanced Threat Protection (ATP) プランで利用できる機能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11bf8-359">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
