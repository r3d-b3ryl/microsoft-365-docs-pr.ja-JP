---
title: 高度な脅威保護のレポートを表示する
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
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
ms.openlocfilehash: 857b98c02895f187d8639d991b74ed1fe12622ae
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351875"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="682ba-103">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="682ba-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="682ba-104">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、セキュリティコンプライアンスセンターでいくつかの ATP レポートを使用でき &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="682ba-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="682ba-105">([**レポート** \> ] に移動します。**ダッシュボード**)</span><span class="sxs-lookup"><span data-stu-id="682ba-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![セキュリティ &amp; コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="682ba-107">ATP レポートには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="682ba-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="682ba-108">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="682ba-109">ATP ファイルの種類レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="682ba-110">ATP メッセージの廃棄レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="682ba-111">[リアルタイム検出またはエクスプローラー](threat-explorer.md) (OFFICE 365 ATP プラン1または2を使用しているかどうかによって異なります)</span><span class="sxs-lookup"><span data-stu-id="682ba-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="682ba-112">...その[他](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="682ba-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="682ba-113">ATP レポートの概要とその使用方法については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="682ba-114">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-114">Threat Protection Status report</span></span>

<span data-ttu-id="682ba-115">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。</span><span class="sxs-lookup"><span data-stu-id="682ba-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="682ba-116">このレポートは、時間の経過による検出 (最大90日間) を表示するのに役立ち、セキュリティ管理者が傾向を特定したり、ポリシーが調整を必要とするかどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="682ba-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="682ba-117">このレポートでは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、[ゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)、Atp の[安全](atp-safe-links.md)な添付ファイル、Atp の[安全な添付ファイル](atp-safe-attachments.md)、 [atp のフィッシング対策](set-up-anti-phishing-policies.md)などの atp 機能など、悪意のあるコンテンツを含む一意の電子メールメッセージの集計数を示します。</span><span class="sxs-lookup"><span data-stu-id="682ba-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="682ba-118">情報のフィルターと内訳により、このレポートの情報をより詳細に分類することができます。</span><span class="sxs-lookup"><span data-stu-id="682ba-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="682ba-119">具体的には、[**電子メール**の \> **フィッシング**] および [**電子メール**の \> **マルウェア] ビュー**に含まれている [ブレークダウン] メニューがあります。</span><span class="sxs-lookup"><span data-stu-id="682ba-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="682ba-120">データは次のように分割されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="682ba-121">検出の種類別</span><span class="sxs-lookup"><span data-stu-id="682ba-121">By detection type</span></span>|<span data-ttu-id="682ba-122">これらの脅威をキャッチするために役立つポリシーは何ですか。</span><span class="sxs-lookup"><span data-stu-id="682ba-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="682ba-123">検出テクノロジによる</span><span class="sxs-lookup"><span data-stu-id="682ba-123">By detection technology</span></span>|<span data-ttu-id="682ba-124">脅威をキャッチした Microsoft テクノロジの基礎</span><span class="sxs-lookup"><span data-stu-id="682ba-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="682ba-125">配信状況別</span><span class="sxs-lookup"><span data-stu-id="682ba-125">By delivery status</span></span>|<span data-ttu-id="682ba-126">脅威として検出された電子メールメッセージにはどのような現象がありますか?</span><span class="sxs-lookup"><span data-stu-id="682ba-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="682ba-127">電子メール > フィッシング |マルウェアの表示には、ATP によって*生成さ*れたファイルの評価、*ファイルの分析*、 *URL の分析*、*スプーフィング防止: DMARC failure*などのカテゴリがあるので、表示されている検出テクノロジの詳細な分類があります。たとえば、組織が脅威をキャッチすることを明確にするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="682ba-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![脅威保護の状態レポートのドロップダウンが表示されています。](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="682ba-129">これらのビューでは、ボタンのクリック (**電子メール** \> **フィッシング**、**電子メール**の \> **マルウェア**、および**コンテンツ** \> **マルウェア**の表示) を使用して、エクスポートするオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="682ba-130">コンピューターにエクスポートされた集計データを Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="682ba-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![この図は、マルウェアビューのメニュー、[スケジュールの作成]、および [要求レポート] のオプションとしてのエクスポートを示しています。](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="682ba-132">**注**:**フィッシング**および**マルウェア**に対してエクスポートできるエントリの最大数は、1万の下のみです。</span><span class="sxs-lookup"><span data-stu-id="682ba-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="682ba-133">ビューをエクスポートする場合は、最新の1万エントリのみがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="682ba-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="682ba-134">概要とメールのビューでは、24時間ではなく、処理時間内に情報が表示されます (demand re)。</span><span class="sxs-lookup"><span data-stu-id="682ba-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="682ba-135">ここでは、この速度が向上しています)。</span><span class="sxs-lookup"><span data-stu-id="682ba-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="682ba-136">脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](exchange-online-protection-overview.md)(EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="682ba-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-overview.md)) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="682ba-137">たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="682ba-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="682ba-138">このような情報は ATP に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。</span><span class="sxs-lookup"><span data-stu-id="682ba-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="682ba-139">脅威保護の状態レポートを表示するには、[セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード**の \> **脅威保護の状態**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="682ba-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![ATP の脅威保護状態レポート](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="682ba-141">1日の詳細な状態を取得するには、グラフの上にポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="682ba-141">To get detailed status for a day, hover over the graph.</span></span>

![1日の ATP の脅威保護状態データ](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="682ba-143">既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="682ba-144">ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="682ba-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="682ba-145">(試用版サブスクリプションを使用している場合は、30日間のデータに制限されることがあります)。</span><span class="sxs-lookup"><span data-stu-id="682ba-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![ATP の脅威保護状態フィルター](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="682ba-147">[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="682ba-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![ATP の脅威保護状態レポートの表示オプション](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="682ba-149">URL 保護状態レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-149">URL Protection Status report</span></span>

<span data-ttu-id="682ba-150">このレポートは基礎となるデータを収集し、1回のクリックで検出された脅威です (一方、他のほとんどの電子メール脅威関連のレポートはメッセージデータごと)。</span><span class="sxs-lookup"><span data-stu-id="682ba-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="682ba-151">このレポートは、クリックごとに電子メールメッセージやドキュメント内のハイパーリンクによって発生する脅威を表示するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="682ba-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="682ba-152">2つのビューがあります。</span><span class="sxs-lookup"><span data-stu-id="682ba-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="682ba-153">URL [保護アクション] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="682ba-153">URL click protection action</span></span>|<span data-ttu-id="682ba-154">ブロックされる Url の数、ブロックされているが、ユーザーによるクリックスルーで上書きされ、ユーザーがクリックスルーで上書きしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="682ba-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="682ba-155">[URL] をクリックします (アプリケーション別)</span><span class="sxs-lookup"><span data-stu-id="682ba-155">URL click by application</span></span>|<span data-ttu-id="682ba-156">URL がクリックされたアプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="682ba-157">詳細表には、クリック時間とユーザー情報に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="682ba-158">最後に、URL 保護の状態レポートでは、ATP の安全なリンク機能が保護されているため、ATP の安全なリンクが有効になっているお客様のみが、このレポートに反映されるデータを表示することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="682ba-159">これは、*保護傾向レポート*で、データが大きなデータセット内の傾向を表すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="682ba-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="682ba-160">その結果、集計ビュー内のデータはリアルタイムでは使用できませんが、[詳細] テーブルビューのデータは、2つのビューの間に若干の違いがあることがわかります。</span><span class="sxs-lookup"><span data-stu-id="682ba-160">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="682ba-161">ATP ファイルの種類レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-161">ATP File Types report</span></span>

<span data-ttu-id="682ba-162">**Atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-162">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="682ba-163">このレポートを表示するには、[セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)で、[**レポート**ダッシュボード ATP] [ファイルの種類] に移動 \> **Dashboard** \> **ATP File Types**します。</span><span class="sxs-lookup"><span data-stu-id="682ba-163">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![ATP ファイルの種類レポート](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="682ba-165">特定の日にポインターを置くと、 [ATP の安全な添付](atp-safe-attachments.md)ファイルとスパム対策の[ &amp; マルウェア対策保護](anti-spam-and-anti-malware-protection.md)によって検出された悪意のあるファイルの種類の内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="682ba-165">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1日の ATP ファイルタイプレポートデータ](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="682ba-167">ATP メッセージの廃棄レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-167">ATP Message Disposition report</span></span>

<span data-ttu-id="682ba-168">**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="682ba-169">このレポートを表示するには、[セキュリティ/ &amp; コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="682ba-169">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![ATP メッセージディスポジションレポート](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="682ba-171">グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="682ba-171">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![1日の ATP メッセージディスポジションレポートデータ](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="682ba-173">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="682ba-173">Additional reports to view</span></span>

<span data-ttu-id="682ba-174">この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="682ba-174">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="682ba-175">**レポート (s)**</span><span class="sxs-lookup"><span data-stu-id="682ba-175">**Report(s)**</span></span>|<span data-ttu-id="682ba-176">**詳細**</span><span class="sxs-lookup"><span data-stu-id="682ba-176">**Details**</span></span>|
|<span data-ttu-id="682ba-177">**エクスプローラー**または**リアルタイム検出**: (Office 365 ATP Plan 2 のお客様はエクスプローラーを所有しています。Office 365 ATP Plan 1 お客様はリアルタイムの検出を行っています。</span><span class="sxs-lookup"><span data-stu-id="682ba-177">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="682ba-178">脅威エクスプローラー (およびリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="682ba-178">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="682ba-179">上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="682ba-179">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="682ba-180">セキュリティ/コンプライアンスセンターで電子メールのセキュリティレポートを表示する &amp;</span><span class="sxs-lookup"><span data-stu-id="682ba-180">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="682ba-181">**ATP の安全なリンク URL トレース**: (PowerShell を使用して生成したレポートです。)このレポートには、過去7日間 (7 日間) の ATP の安全なリンクアクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="682ba-181">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="682ba-182">取得-UrlTrace コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="682ba-182">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="682ba-183">**EOP および ATP の結果**: (PowerShell を使用して生成したカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="682ba-183">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="682ba-184">このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="682ba-184">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="682ba-185">Get-mailtrafficatpreport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="682ba-185">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="682ba-186">**EOP および ATP の検出**: (PowerShell を使用して生成したカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="682ba-186">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="682ba-187">このレポートには、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="682ba-187">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="682ba-188">Get-MailDetailATPReport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="682ba-188">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="682ba-189">ATP レポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="682ba-189">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="682ba-190">この記事に記載されているレポートを表示して使用するには、**セキュリティ &amp; コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="682ba-190">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="682ba-191">セキュリティ &amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="682ba-191">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="682ba-192">組織の管理</span><span class="sxs-lookup"><span data-stu-id="682ba-192">Organization Management</span></span>
  - <span data-ttu-id="682ba-193">セキュリティ管理者 (Azure Active Directory 管理センターで割り当て [https://aad.portal.azure.com](https://aad.portal.azure.com) 可能)</span><span class="sxs-lookup"><span data-stu-id="682ba-193">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="682ba-194">Security Operator (Azure Active Directory 管理センター () で割り当てることができます [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="682ba-194">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="682ba-195">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="682ba-195">Security Reader</span></span>

- <span data-ttu-id="682ba-196">Exchange Online の場合は、Exchange 管理センター ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) または PowerShell コマンドレット (「 [Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="682ba-196">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="682ba-197">組織の管理</span><span class="sxs-lookup"><span data-stu-id="682ba-197">Organization Management</span></span>
  - <span data-ttu-id="682ba-198">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="682ba-198">View-only Organization Management</span></span>
  - <span data-ttu-id="682ba-199">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="682ba-199">View-Only Recipients role</span></span>
  - <span data-ttu-id="682ba-200">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="682ba-200">Compliance Management</span></span>

<span data-ttu-id="682ba-201">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-201">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="682ba-202">セキュリティ/コンプライアンスセンターのアクセス許可 &amp;</span><span class="sxs-lookup"><span data-stu-id="682ba-202">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="682ba-203">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="682ba-203">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="682ba-204">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="682ba-204">What if the reports aren't showing data?</span></span>

<span data-ttu-id="682ba-205">ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-205">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="682ba-206">組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。</span><span class="sxs-lookup"><span data-stu-id="682ba-206">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="682ba-207">また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="682ba-207">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="682ba-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="682ba-208">Related topics</span></span>

[<span data-ttu-id="682ba-209">セキュリティ/コンプライアンスセンターのレポートと分析 &amp;</span><span class="sxs-lookup"><span data-stu-id="682ba-209">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="682ba-210">セキュリティ/コンプライアンスセンターでレポートのスケジュールを作成する &amp;</span><span class="sxs-lookup"><span data-stu-id="682ba-210">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="682ba-211">セキュリティ/コンプライアンスセンターでカスタムレポートを設定およびダウンロードする &amp;</span><span class="sxs-lookup"><span data-stu-id="682ba-211">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="682ba-212">役割のアクセス許可 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="682ba-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
