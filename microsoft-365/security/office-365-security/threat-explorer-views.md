---
title: 脅威エクスプローラーのビューとリアルタイム検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 脅威エクスプローラーとリアルタイム検出レポートを使用して、セキュリティ コンプライアンス センターで脅威を調査して対応する&します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406482"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="f0ab0-103">脅威エクスプローラーのビューとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="f0ab0-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0ab0-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f0ab0-104">**Applies to**</span></span>
- [<span data-ttu-id="f0ab0-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f0ab0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f0ab0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0ab0-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![脅威エクスプローラー](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="f0ab0-108">[Threat Explorer](threat-explorer.md) (およびリアルタイム検出レポート) は、セキュリティ運用チームがセキュリティ & コンプライアンス センターの脅威を調査して対応するのに役立つ、リアルタイムに近い強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="f0ab0-109">エクスプローラー (およびリアルタイム検出レポート) には、Office 365 の電子メールやファイル内のマルウェアやフィッシングの疑い、および組織に対する他のセキュリティ上の脅威やリスクに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="f0ab0-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span><span class="sxs-lookup"><span data-stu-id="f0ab0-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="f0ab0-111">Microsoft Defender for Office 365 プラン 1 の場合は、リアルタイムの検出があります。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="f0ab0-112">エクスプローラー (またはリアルタイム検出レポート) を初めて開いた場合、既定のビューには過去 7 日間のメール マルウェア検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="f0ab0-113">このレポートでは、セーフ リンクによって検出された悪意のある URL や、安全な添付ファイルによって検出された悪意のあるファイル[](atp-safe-links.md)など、365 件の検出に関する Microsoft Office Defender を表示[することもできます。](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="f0ab0-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="f0ab0-114">このレポートは、過去 30 日間のデータを表示Office変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="f0ab0-115">試用版サブスクリプションには、過去 7 日間のデータだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="f0ab0-116">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="f0ab0-116">Subscription</span></span>|<span data-ttu-id="f0ab0-117">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="f0ab0-117">Utility</span></span>|<span data-ttu-id="f0ab0-118">データの日数</span><span class="sxs-lookup"><span data-stu-id="f0ab0-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="f0ab0-119">Microsoft Defender for Office 365 P1 試用版</span><span class="sxs-lookup"><span data-stu-id="f0ab0-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="f0ab0-120">リアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="f0ab0-120">Real-time detections</span></span>|<span data-ttu-id="f0ab0-121">7 </span><span class="sxs-lookup"><span data-stu-id="f0ab0-121">7</span></span>|
|<span data-ttu-id="f0ab0-122">Microsoft Defender for Office 365 P1 有料</span><span class="sxs-lookup"><span data-stu-id="f0ab0-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="f0ab0-123">リアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="f0ab0-123">Real-time detections</span></span>|<span data-ttu-id="f0ab0-124">30</span><span class="sxs-lookup"><span data-stu-id="f0ab0-124">30</span></span>|
|<span data-ttu-id="f0ab0-125">Microsoft Defender for Office 365 P1 有料テスト Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="f0ab0-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="f0ab0-126">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="f0ab0-126">Threat Explorer</span></span>|<span data-ttu-id="f0ab0-127">7 </span><span class="sxs-lookup"><span data-stu-id="f0ab0-127">7</span></span>|
|<span data-ttu-id="f0ab0-128">Microsoft Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="f0ab0-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="f0ab0-129">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="f0ab0-129">Threat Explorer</span></span>|<span data-ttu-id="f0ab0-130">7 </span><span class="sxs-lookup"><span data-stu-id="f0ab0-130">7</span></span>|
|<span data-ttu-id="f0ab0-131">Microsoft Defender for Office 365 P2 paid</span><span class="sxs-lookup"><span data-stu-id="f0ab0-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="f0ab0-132">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="f0ab0-132">Threat Explorer</span></span>|<span data-ttu-id="f0ab0-133">30</span><span class="sxs-lookup"><span data-stu-id="f0ab0-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="f0ab0-134">間もなく、試用版テナントのエクスプローラー (およびリアルタイム検出) のデータ保持と検索の制限を 7 日から 30 日間に延長します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="f0ab0-135">この変更は、ロードマップ 項目 No. 70544 の一部として追跡され、現在ロールアウト段階にあります。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="f0ab0-136">表示する情報 **を** 変更するには、[表示] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="f0ab0-137">ツールヒントは、使用するビューを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-137">Tooltips help you determine which view to use.</span></span>

![[脅威エクスプローラーの表示] メニュー](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="f0ab0-139">ビューを選択したら、フィルターを適用してクエリを設定して、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="f0ab0-140">以下のセクションでは、エクスプローラーで使用できるさまざまなビュー (またはリアルタイム検出) の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="f0ab0-141">メール >マルウェア</span><span class="sxs-lookup"><span data-stu-id="f0ab0-141">Email > Malware</span></span>

<span data-ttu-id="f0ab0-142">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[電子メール マルウェアの表示 **]** \> **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="f0ab0-143">このビューには、マルウェアが含まれていると識別された電子メール メッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-143">This view shows information about email messages that were identified as containing malware.</span></span>

![マルウェアとして識別された電子メールに関するデータを表示する](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="f0ab0-145">[送信者 **] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f0ab0-146">この一覧を使用して、送信者、受信者、送信者ドメイン、件名、検出テクノロジ、保護状態などによってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="f0ab0-147">たとえば、検出された電子メール メッセージに対して実行されたアクションを確認するには、一覧で [ **保護の状態** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="f0ab0-148">オプションを選択し、[更新] ボタンをクリックして、そのフィルターをレポートに適用します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![脅威エクスプローラーの脅威保護の状態オプション](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="f0ab0-150">グラフの下に、特定のメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="f0ab0-151">リストでアイテムを選択すると、フライアウト ウィンドウが開き、選択したアイテムの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![飛び出しが開いた脅威エクスプローラー](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="f0ab0-153">メール >フィッシング</span><span class="sxs-lookup"><span data-stu-id="f0ab0-153">Email > Phish</span></span>

<span data-ttu-id="f0ab0-154">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[メール フィッシング **の表示]** \> **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="f0ab0-155">このビューには、フィッシング詐欺の試みとして識別された電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-155">This view shows email messages identified as phishing attempts.</span></span>

![フィッシング詐欺の試みとして識別された電子メールに関するデータを表示する](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="f0ab0-157">[送信者 **] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f0ab0-158">この一覧を使用して、送信者、受信者、送信者ドメイン、送信者 IP、URL ドメイン、クリックの評決などによってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="f0ab0-159">たとえば、フィッシング詐欺の試みとして識別された URL をクリックしたユーザーが実行したアクションを確認するには、リストで [Click **verdict]** を選択し、1 つ以上のオプションを選択し、[更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![[フィッシング] レポートの [評決オプション] をクリックします。](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="f0ab0-161">グラフの下に、特定のメッセージ、URL クリック、URL、メール配信元の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![電子メール メッセージでフィッシングとして検出された URL](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="f0ab0-163">リスト内のアイテム (検出された URL など) を選択すると、フライアウト ウィンドウが開き、選択したアイテムの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![検出された URL の詳細](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="f0ab0-165">メール>提出</span><span class="sxs-lookup"><span data-stu-id="f0ab0-165">Email > Submissions</span></span>

<span data-ttu-id="f0ab0-166">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[電子メール送信の表示 **]** \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="f0ab0-167">このビューには、ユーザーが迷惑メール、迷惑メール、フィッシングメールとして報告したメールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![ユーザーによって報告された電子メール メッセージ](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="f0ab0-169">[送信者 **] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f0ab0-170">この一覧を使用して、送信者、受信者、レポートの種類 (電子メールが迷惑メール、迷惑メール、フィッシングではないというユーザーの判断) などによって情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="f0ab0-171">たとえば、フィッシング詐欺の試みとして報告された電子メール メッセージに関する情報を表示するには、[送信者レポートの種類] をクリックし、[フィッシング] を選択し、[更新] ボタン \> をクリックします。 </span><span class="sxs-lookup"><span data-stu-id="f0ab0-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![[レポートの種類] フィルターで選択されているフィッシング](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="f0ab0-173">グラフの下に、件名、送信者の IP アドレス、迷惑メール、迷惑メール、フィッシングなど、メッセージを報告したユーザーなど、特定の電子メール メッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![フィッシング詐欺の試みとして報告されたメッセージ](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="f0ab0-175">リスト内のアイテムを選択して、追加の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="f0ab0-176">メール > すべてのメール</span><span class="sxs-lookup"><span data-stu-id="f0ab0-176">Email > All email</span></span>

<span data-ttu-id="f0ab0-177">このレポートを表示するには、エクスプローラーで[メールのすべて表示 \> **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="f0ab0-178">このビューには、フィッシングやマルウェアによる悪意のあると識別されたメールや、悪意のあるメール以外のすべてのメール (通常のメール、スパム、バルク メール) など、電子メールアクティビティのオールアップ ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="f0ab0-179">[表示するデータが多すぎます **]** というエラーが表示された場合は、フィルターを追加し、必要に応じて表示する日付範囲を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="f0ab0-180">フィルターを適用するには、[送信者] **を** 選択し、一覧でアイテムを選択し、[更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="f0ab0-181">この例では、検出テクノロジ **を** フィルターとして使用しました (使用可能なオプションは複数あります)。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="f0ab0-182">送信者、送信者のドメイン、受信者、件名、添付ファイル名、マルウェア ファミリ、保護状態 (Office 365 の脅威保護機能とポリシーによって実行されるアクション)、検出テクノロジ (マルウェアの検出方法)などによって情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![検出テクノロジによって検出された電子メールに関するデータを表示する](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="f0ab0-184">グラフの下には、件名、受信者、送信者、状態など、特定の電子メール メッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="f0ab0-185">コンテンツ >マルウェア</span><span class="sxs-lookup"><span data-stu-id="f0ab0-185">Content > Malware</span></span>

<span data-ttu-id="f0ab0-186">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[コンテンツ マルウェアの表示 **]** \> **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="f0ab0-187">このビューには [、SharePoint Online、OneDrive for Business、および Microsoft Teams](atp-for-spo-odb-and-teams.md)の Office 365 に対して Microsoft Defender によって悪意のあるファイルとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f0ab0-188">マルウェア ファミリ、検出テクノロジ (マルウェアの検出方法)、ワークロード (OneDrive、SharePoint、または Teams) 別に情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![検出されたマルウェアに関するデータを表示する](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="f0ab0-190">グラフの下には、添付ファイルのファイル名、ワークロード、ファイル サイズ、ファイルを最後に変更したユーザーなど、特定のファイルの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="f0ab0-191">クリックからフィルターへの機能</span><span class="sxs-lookup"><span data-stu-id="f0ab0-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="f0ab0-192">エクスプローラー (およびリアルタイム検出) を使用すると、クリックでフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="f0ab0-193">凡例内のアイテムをクリックすると、そのアイテムがレポートのフィルターになります。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="f0ab0-194">たとえば、エクスプローラーでマルウェア ビューを見ているとします。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![[脅威管理エクスプローラー] に \> 移動します。](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="f0ab0-196">このグラフ **で [ATP の削除]** をクリックすると、次のようなビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![エクスプローラーがフィルター処理され、365 デトOfficeの Defender のみを表示する](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="f0ab0-198">このビューでは、安全な添付ファイルによって削除されたファイルのデータを [確認しています](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="f0ab0-199">グラフの下には、安全な添付ファイルによって検出された添付ファイルを含む特定の電子メール メッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![検出された添付ファイルを含む電子メール メッセージに関する具体的な詳細](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="f0ab0-201">1 つ以上のアイテムを選択すると、[アクション] メニューがアクティブ化され、選択したアイテムに対して選択できる複数の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![アイテムを選択すると、[操作] メニューがアクティブ化されます。](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="f0ab0-203">クリックでフィルター処理して特定の詳細に移動する機能によって、脅威の調査に多くの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="f0ab0-204">クエリとフィルター</span><span class="sxs-lookup"><span data-stu-id="f0ab0-204">Queries and filters</span></span>

<span data-ttu-id="f0ab0-205">エクスプローラー (リアルタイム検出レポートと同様に) には、いくつかの強力なフィルターとクエリ機能が備え付け、上位の対象ユーザー、トップ マルウェア ファミリ、検出テクノロジなど、詳細を掘り下ろします。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="f0ab0-206">レポートの種類ごとに、さまざまな方法でデータを表示および探索できます。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0ab0-207">Explorer のクエリ バー (またはリアルタイムの検出) では、アスタリスクや疑問符などのワイルドカード文字を使用しません。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="f0ab0-208">[件名] フィールドで電子メール メッセージを検索すると、エクスプローラー (またはリアルタイム検出) は部分的な照合を実行し、ワイルドカード検索と同様の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="f0ab0-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
