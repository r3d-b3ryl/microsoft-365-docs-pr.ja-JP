---
title: 脅威エクスプローラーのビューとリアルタイムの検出
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
description: 脅威エクスプローラーとリアルタイム検出レポートを使用して、セキュリティ/コンプライアンス センターで脅威を調査して対応する方法&します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290287"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="44f7f-103">脅威エクスプローラーのビューとリアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="44f7f-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="44f7f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="44f7f-104">**Applies to**</span></span>
- [<span data-ttu-id="44f7f-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="44f7f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="44f7f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44f7f-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![脅威エクスプローラー](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="44f7f-108">[脅威エクスプローラー](threat-explorer.md) (およびリアルタイム検出レポート) は、セキュリティ運用チームがセキュリティ & コンプライアンス センターの脅威を調査して対応するのに役立つ、ほぼリアルタイムの強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="44f7f-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="44f7f-109">エクスプローラー (およびリアルタイム検出レポート) には、Office 365 のメールやファイル内のマルウェアとフィッシングの疑いがある情報、および組織に対するその他のセキュリティの脅威とリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="44f7f-110">[Microsoft Defender for Office 365](office-365-atp.md)プラン 2 をお持ちのお客様は、エクスプローラーをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="44f7f-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="44f7f-111">Microsoft Defender for Office 365 プラン 1 を使用している場合は、リアルタイムで検出されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="44f7f-112">エクスプローラー (またはリアルタイム検出レポート) を初めて開いた場合、既定のビューには過去 7 日間のメール マルウェア検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="44f7f-113">このレポートでは、安全なリンクによって検出された悪意のある URL や、安全な添付ファイルによって検出された悪意のあるファイル[](atp-safe-links.md)など、Office 365 の検出に関する Microsoft Defender を[表示](atp-safe-attachments.md)することもできます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="44f7f-114">このレポートは、過去 30 日間のデータを表示するために変更できます (Microsoft Defender Office 365 P2 有料サブスクリプションを使用)。</span><span class="sxs-lookup"><span data-stu-id="44f7f-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="44f7f-115">試用版サブスクリプションには、過去 7 日間のデータだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="44f7f-116">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="44f7f-116">Subscription</span></span>|<span data-ttu-id="44f7f-117">ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="44f7f-117">Utility</span></span>|<span data-ttu-id="44f7f-118">データの日数</span><span class="sxs-lookup"><span data-stu-id="44f7f-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="44f7f-119">Microsoft Defender for Office 365 P1 試用版</span><span class="sxs-lookup"><span data-stu-id="44f7f-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="44f7f-120">リアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="44f7f-120">Real-time detections</span></span>|<span data-ttu-id="44f7f-121">7 </span><span class="sxs-lookup"><span data-stu-id="44f7f-121">7</span></span>|
|<span data-ttu-id="44f7f-122">Microsoft Defender for Office 365 P1 (有料)</span><span class="sxs-lookup"><span data-stu-id="44f7f-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="44f7f-123">リアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="44f7f-123">Real-time detections</span></span>|<span data-ttu-id="44f7f-124">30</span><span class="sxs-lookup"><span data-stu-id="44f7f-124">30</span></span>|
|<span data-ttu-id="44f7f-125">Microsoft Defender for Office 365 P1 有料テスト Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="44f7f-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="44f7f-126">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="44f7f-126">Threat Explorer</span></span>|<span data-ttu-id="44f7f-127">7 </span><span class="sxs-lookup"><span data-stu-id="44f7f-127">7</span></span>|
|<span data-ttu-id="44f7f-128">Microsoft Defender for Office 365 P2 試用版</span><span class="sxs-lookup"><span data-stu-id="44f7f-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="44f7f-129">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="44f7f-129">Threat Explorer</span></span>|<span data-ttu-id="44f7f-130">7 </span><span class="sxs-lookup"><span data-stu-id="44f7f-130">7</span></span>|
|<span data-ttu-id="44f7f-131">Microsoft Defender for Office 365 P2 (有料)</span><span class="sxs-lookup"><span data-stu-id="44f7f-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="44f7f-132">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="44f7f-132">Threat Explorer</span></span>|<span data-ttu-id="44f7f-133">30</span><span class="sxs-lookup"><span data-stu-id="44f7f-133">30</span></span>|
|

<span data-ttu-id="44f7f-134">表示される情報 **を変更** するには、[表示] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-134">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="44f7f-135">ツールヒントは、使用するビューを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-135">Tooltips help you determine which view to use.</span></span>

![脅威エクスプローラーの [表示] メニュー](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="44f7f-137">ビューを選択したら、フィルターを適用し、クエリを設定して詳細な分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-137">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="44f7f-138">以下のセクションでは、エクスプローラーで使用できるさまざまなビュー (またはリアルタイムの検出) の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-138">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="44f7f-139">電子メール>マルウェア</span><span class="sxs-lookup"><span data-stu-id="44f7f-139">Email > Malware</span></span>

<span data-ttu-id="44f7f-140">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[ **メール** マルウェアの表示] \> **を選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="44f7f-140">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="44f7f-141">このビューには、マルウェアが含まれていると識別された電子メール メッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-141">This view shows information about email messages that were identified as containing malware.</span></span>

![マルウェアとして識別されたメールに関するデータを表示する](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="44f7f-143">[ **送信者] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="44f7f-144">この一覧を使用して、送信者、受信者、送信者ドメイン、件名、検出テクノロジ、保護状態などによってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-144">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="44f7f-145">たとえば、検出された電子メール メッセージに対して実行されたアクションを確認するには、一覧で **[保護の状態** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-145">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="44f7f-146">オプションを選択し、[最新の情報に更新] ボタンをクリックして、そのフィルターをレポートに適用します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-146">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![脅威エクスプローラーの脅威保護状態オプション](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="44f7f-148">グラフの下に、特定のメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-148">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="44f7f-149">一覧で項目を選択すると、選択した項目の詳細を確認できるフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-149">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![フライアウトが開いた脅威エクスプローラー](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="44f7f-151">メール>フィッシング</span><span class="sxs-lookup"><span data-stu-id="44f7f-151">Email > Phish</span></span>

<span data-ttu-id="44f7f-152">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[ **メール** フィッシングの表示] \> **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f7f-152">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="44f7f-153">このビューには、フィッシングの試行として識別された電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-153">This view shows email messages identified as phishing attempts.</span></span>

![フィッシングの試行として識別されたメールに関するデータを表示する](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="44f7f-155">[ **送信者] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-155">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="44f7f-156">この一覧を使用して、送信者、受信者、送信者ドメイン、送信者 IP、URL ドメイン、クリックの確認などによってデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-156">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="44f7f-157">たとえば、フィッシングの試行として識別された URL をユーザーがクリックした場合に実行されたアクションを確認するには、一覧で [クリックの確認] を選択し、1 つ以上のオプションを選択して、[最新の情報に更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="44f7f-157">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![フィッシング レポートの [確認オプション] をクリックする](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="44f7f-159">グラフの下に、特定のメッセージ、URL のクリック、URL、メールの配信元に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-159">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![メール メッセージでフィッシングとして検出された URL](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="44f7f-161">検出された URL など、リスト内の項目を選択すると、選択した項目の詳細を確認できるフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-161">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![検出された URL の詳細](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="44f7f-163">メール>提出</span><span class="sxs-lookup"><span data-stu-id="44f7f-163">Email > Submissions</span></span>

<span data-ttu-id="44f7f-164">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[メール送信の表示] \>  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f7f-164">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="44f7f-165">このビューには、ユーザーが迷惑メール、迷惑メール、フィッシングメールとして報告したメールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-165">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![ユーザーによって報告された電子メール メッセージ](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="44f7f-167">[ **送信者] を** クリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-167">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="44f7f-168">この一覧を使用して、送信者、受信者、レポートの種類 (メールが迷惑メール、迷惑メール、フィッシングメールではないというユーザーの判断) 別に情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-168">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="44f7f-169">たとえば、フィッシング詐欺として報告されたメール メッセージに関する情報を表示するには、[**送信者** レポートの種類] をクリックし、[フィッシング] を選択して、[更新] ボタンを \> クリックします。 </span><span class="sxs-lookup"><span data-stu-id="44f7f-169">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![[レポートの種類] フィルターで選択されたフィッシング](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="44f7f-171">グラフの下に、件名、送信者の IP アドレス、迷惑メール、迷惑メールではないメッセージ、フィッシングなどのメッセージを報告したユーザーなど、特定の電子メール メッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-171">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![フィッシングの試行として報告されたメッセージ](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="44f7f-173">リスト内の項目を選択して、追加の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-173">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="44f7f-174">メール >すべてのメール</span><span class="sxs-lookup"><span data-stu-id="44f7f-174">Email > All email</span></span>

<span data-ttu-id="44f7f-175">このレポートを表示するには、エクスプローラーで[メールすべて表示 \> **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f7f-175">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="44f7f-176">このビューには、フィッシングやマルウェアによる悪意のあるメールと識別されたメールや、悪意のあるメール以外のすべてのメール (通常のメール、スパム、バルク メール) など、メール アクティビティの全ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-176">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="44f7f-177">表示するデータが多すぎるというエラーが発生した場合は、フィルターを追加し、必要に応じて表示する日付範囲を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-177">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="44f7f-178">フィルターを適用するには、[ **送信者**] を選択し、一覧からアイテムを選択して、[更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="44f7f-178">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="44f7f-179">この例では、検出テクノロジ **を** フィルターとして使用しました (使用可能なオプションは複数あります)。</span><span class="sxs-lookup"><span data-stu-id="44f7f-179">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="44f7f-180">送信者、送信者のドメイン、受信者、件名、添付ファイル名、マルウェア ファミリ、保護の状態 (Office 365 の脅威保護機能とポリシーによって実行されるアクション)、検出テクノロジ (マルウェアの検出方法)、その他別に情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-180">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![検出された電子メールに関するデータを検出テクノロジで表示する](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="44f7f-182">グラフの下に、件名、受信者、送信者、状態など、特定の電子メール メッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-182">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="44f7f-183">コンテンツ >マルウェア</span><span class="sxs-lookup"><span data-stu-id="44f7f-183">Content > Malware</span></span>

<span data-ttu-id="44f7f-184">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[コンテンツ **マルウェアの** 表示] \> **を選択** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="44f7f-184">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="44f7f-185">このビューには [、SharePoint Online、OneDrive for Business、Microsoft Teams で Office 365](atp-for-spo-odb-and-teams.md)の Microsoft Defender によって悪意のあるファイルとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-185">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="44f7f-186">マルウェア ファミリ、検出テクノロジ (マルウェアの検出方法)、ワークロード (OneDrive、SharePoint、または Teams) で情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-186">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![検出されたマルウェアに関するデータを表示する](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="44f7f-188">グラフの下に、添付ファイルのファイル名、ワークロード、ファイル サイズ、ファイルを最後に変更したユーザーなど、特定のファイルに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-188">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="44f7f-189">クリックしてフィルター処理を行う機能</span><span class="sxs-lookup"><span data-stu-id="44f7f-189">Click-to-filter capabilities</span></span>

<span data-ttu-id="44f7f-190">エクスプローラー (およびリアルタイムの検出) を使用すると、クリックでフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-190">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="44f7f-191">凡例内の項目をクリックすると、その項目がレポートのフィルターになります。</span><span class="sxs-lookup"><span data-stu-id="44f7f-191">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="44f7f-192">たとえば、エクスプローラーの [マルウェア] ビューを見ているとします。</span><span class="sxs-lookup"><span data-stu-id="44f7f-192">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![脅威管理エクスプローラーに移動 \> する](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="44f7f-194">このグラフ **で ATP 分析** をクリックすると、次のようなビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-194">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![365 分析結果に対して Defender Office表示するためにフィルター処理されたエクスプローラー](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="44f7f-196">このビューでは、安全な添付ファイルによって分析されたファイルのデータ [を確認しています](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="44f7f-196">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="44f7f-197">グラフの下に、安全な添付ファイルで検出された添付ファイルを含む特定の電子メール メッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-197">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![検出された添付ファイルを含む電子メール メッセージに関する具体的な詳細](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="44f7f-199">1 つ以上の項目を選択すると、[操作] メニューがアクティブ化され、選択した項目に対して選択できる複数の選択肢が表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-199">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![項目を選択すると 、[操作] メニューがアクティブ化されます。](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="44f7f-201">クリックでフィルター処理し、特定の詳細に移動する機能によって、脅威の調査に多くの時間を節約できます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-201">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="44f7f-202">クエリとフィルター</span><span class="sxs-lookup"><span data-stu-id="44f7f-202">Queries and filters</span></span>

<span data-ttu-id="44f7f-203">エクスプローラー (リアルタイム検出レポートと同様に) には、いくつかの強力なフィルター機能とクエリ機能があります。この機能を使用すると、上位の対象ユーザー、上位マルウェア ファミリ、検出テクノロジなど、詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="44f7f-203">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="44f7f-204">レポートの種類ごとに、データを表示および探索するさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="44f7f-204">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44f7f-205">エクスプローラーのクエリ バーでは、アスタリスクや疑問符などのワイルドカード文字を使用しません (またはリアルタイム検出)。</span><span class="sxs-lookup"><span data-stu-id="44f7f-205">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="44f7f-206">電子メール メッセージの **[件名** ] フィールドを検索すると、エクスプローラー (またはリアルタイムの検出) は部分的な一致を実行し、ワイルドカード検索のような結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="44f7f-206">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
