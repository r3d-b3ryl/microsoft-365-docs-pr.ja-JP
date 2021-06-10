---
title: Microsoft Defender の脅威エクスプローラーを使用した電子メール Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: マルウェアのフィッシング詐欺の試行を表示および調査します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877898"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1ed73-103">Microsoft Defender の脅威エクスプローラーを使用した電子メール Office 365</span><span class="sxs-lookup"><span data-stu-id="1ed73-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="1ed73-104">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="1ed73-104">In this article:</span></span>

- [<span data-ttu-id="1ed73-105">メールで検出されたマルウェアを表示する</span><span class="sxs-lookup"><span data-stu-id="1ed73-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- <span data-ttu-id="1ed73-106">[フィッシング URL を表示し、[評決データ] をクリックする](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="1ed73-106">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- [<span data-ttu-id="1ed73-107">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="1ed73-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="1ed73-108">これは、Threat **Explorer (Explorer)** 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) に関する **3** 記事シリーズの一部です。</span><span class="sxs-lookup"><span data-stu-id="1ed73-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="1ed73-109">このシリーズの他の 2 つの記事は、Threat Explorer と Threat [Explorer](threat-hunting-in-threat-explorer.md) での脅威の検出とリアルタイム検出 [の基本です](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="1ed73-110">この記事では、セキュリティ機能によって電子メールで検出されたマルウェアやフィッシングの試みを表示および調査するMicrosoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="1ed73-111">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="1ed73-111">**Applies to**</span></span>

- [<span data-ttu-id="1ed73-112">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="1ed73-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1ed73-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ed73-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="1ed73-114">メールで検出されたマルウェアを表示する</span><span class="sxs-lookup"><span data-stu-id="1ed73-114">View malware detected in email</span></span>

<span data-ttu-id="1ed73-115">Microsoft 365 テクノロジによって並べ替えた電子メールで検出されたマルウェアを確認するには、[](threat-explorer-views.md#email--malware)エクスプローラーの [電子メール > マルウェア] ビュー (またはリアルタイム検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="1ed73-116">マルウェアは既定のビューなので、エクスプローラーを開いたとすぐに選択される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ed73-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="1ed73-117">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="1ed73-118">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-118">(This example uses Explorer.)</span></span>

   <span data-ttu-id="1ed73-119">統合された Defender ポータル ( ) を使用している場合Microsoft 365コラボレーション エクスプローラーの [電子メール] <https://security.microsoft.com> **&スクロール**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-119">If you're in the converged Microsoft 365 Defender portal (<https://security.microsoft.com>) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="1ed73-120">ここから、ビューから開始し、調査する特定のフレーム (必要な場合) を選択し、エクスプローラーのウォークスルーに応じてフィルターを [フォーカスします](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-120">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="1ed73-121">[表示] **メニューの** [メール マルウェア] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-121">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-122">![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-122">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="1ed73-123">[送信者 **] を** クリックし、[基本検出 **テクノロジ]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-123">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="1ed73-124">検出テクノロジは、レポートのフィルターとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-124">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-125">![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-125">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="1ed73-126">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-126">Choose an option.</span></span> <span data-ttu-id="1ed73-127">次に、[更新] **ボタンを** 選択して、そのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-127">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-128">![選択された検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-128">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="1ed73-129">レポートが更新され、選択したテクノロジ オプションを使用して、電子メールでマルウェアが検出された結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-129">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="1ed73-130">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-130">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="1ed73-131">フィッシング URL を表示し、[評決データ] をクリックする</span><span class="sxs-lookup"><span data-stu-id="1ed73-131">View phishing URL and click verdict data</span></span>

<span data-ttu-id="1ed73-132">許可、ブロック、および上書きされた URL の一覧を含む、メール内の URL を介してフィッシング詐欺の試みを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-132">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="1ed73-133">クリックされた URL を識別するには、セーフ[リンクを](safe-links.md)構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed73-133">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="1ed73-134">[リンク] でクリック[セーフの](set-up-safe-links-policies.md)保護とログ記録を行う場合は、必ずリンク ポリシーをセーフしてください。</span><span class="sxs-lookup"><span data-stu-id="1ed73-134">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="1ed73-135">メッセージ内のフィッシング URL を確認し、フィッシング メッセージ内の URL[  >  ](threat-explorer-views.md#email--phish)をクリックするには、エクスプローラーまたはリアルタイム検出の [メール フィッシング] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-135">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="1ed73-136">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-136">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="1ed73-137">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-137">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="1ed73-138">[表示] **メニューの** [メール フィッシング] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-138">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-139">![フィッシング コンテキストでのエクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-139">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="1ed73-140">[送信者 **] を** クリックし **、[URL]** \> **[評決のクリック] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1ed73-140">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="1ed73-141">[ブロック] や [上書きブロック]などの 1 つ以上のオプションを選択し、そのフィルターを適用するオプションと同じ行の [更新] ボタンを選択します。 </span><span class="sxs-lookup"><span data-stu-id="1ed73-141">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="1ed73-142">(ブラウザー ウィンドウを更新しない)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-142">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-143">![URL とクリックの評決](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-143">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="1ed73-144">レポートが更新され、レポートの下の [URL] タブに 2 つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-144">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="1ed73-145">**上位 URL は** 、フィルター処理したメッセージ内の URL であり、メール配信アクションは URL ごとにカウントされます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-145">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="1ed73-146">[フィッシング メール] ビューでは、通常、この一覧には正当な URL が含まれる。</span><span class="sxs-lookup"><span data-stu-id="1ed73-146">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="1ed73-147">攻撃者は、メッセージに良い URL と悪い URL を組み合わせ、配信を試みているが、悪意のあるリンクをより面白く見せている。</span><span class="sxs-lookup"><span data-stu-id="1ed73-147">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="1ed73-148">URL のテーブルはメールの総数で並べ替えされますが、この列は非表示に設定され、ビューが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-148">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="1ed73-149">**トップ クリックは**、クリックセーフクリック数で並べ替えたリンクでラップされた URL の一覧です。</span><span class="sxs-lookup"><span data-stu-id="1ed73-149">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="1ed73-150">ビューを簡略化するために、この列も表示されません。</span><span class="sxs-lookup"><span data-stu-id="1ed73-150">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="1ed73-151">列別の合計カウントは、クリックセーフ URL の [リンク] クリックの評決カウントを示します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-151">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="1ed73-152">[フィッシング メール] ビューでは、通常、疑わしい URL または悪意のある URL です。</span><span class="sxs-lookup"><span data-stu-id="1ed73-152">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="1ed73-153">ただし、このビューには、脅威ではないがフィッシング メッセージに含まれる URL が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed73-153">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="1ed73-154">ラップされていないリンクの URL クリックはここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="1ed73-154">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="1ed73-155">2 つの URL テーブルには、配信アクションと場所別のフィッシングメール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-155">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="1ed73-156">この表には、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されます。そのため、ユーザーに表示された潜在的な不良リンクと、ユーザーがクリックした可能性のあるリンクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-156">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="1ed73-157">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-157">From here, you can conduct further analysis.</span></span> <span data-ttu-id="1ed73-158">たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-158">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ed73-159">![ブロックされたエクスプローラー URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="1ed73-159">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="1ed73-160">URL を選択して、詳細な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-160">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1ed73-161">[URL の飛び出し] ダイアログ ボックスで、電子メール メッセージのフィルター処理が削除され、環境内での URL の露出の完全なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-161">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="1ed73-162">これにより、エクスプローラーで懸念される電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を見つけ、エクスプローラー ビュー自体に URL フィルターを追加することなく、([URL の詳細] ダイアログ ボックスを使用して) 環境内の URL 露出に関する理解を広げます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-162">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="1ed73-163">クリックの評決の解釈</span><span class="sxs-lookup"><span data-stu-id="1ed73-163">Interpretation of click verdicts</span></span>

<span data-ttu-id="1ed73-164">メールまたは URL のフライアウト、トップ クリック、およびフィルター 処理では、さまざまなクリックの評決値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-164">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="1ed73-165">**なし:** URL の評決をキャプチャできません。</span><span class="sxs-lookup"><span data-stu-id="1ed73-165">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="1ed73-166">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed73-166">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="1ed73-167">**許可:** ユーザーは URL への移動を許可されました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-167">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="1ed73-168">**ブロック:** ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-168">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="1ed73-169">**保留中の評決:** ユーザーに、削除保留中のページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-169">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="1ed73-170">**ブロックされたオーバーライド:** ユーザーが URL への直接移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-170">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="1ed73-171">ただし、ユーザーはブロックをオーバーロードして URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="1ed73-171">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="1ed73-172">**保留中の評決はバイパスされます。** ユーザーには、削除ページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-172">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="1ed73-173">ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1ed73-173">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="1ed73-174">**エラー:** ユーザーにエラー ページが表示されたか、または評決のキャプチャでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-174">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="1ed73-175">**失敗:** 評決のキャプチャ中に不明な例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="1ed73-175">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="1ed73-176">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed73-176">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="1ed73-177">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="1ed73-177">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="1ed73-178">自動調査と対応機能は *、Microsoft Defender* でプラン 2 および *E5* Office 365でOffice 365できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-178">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="1ed73-179">[自動調査と対応により](automated-investigation-response-office.md) 、セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-179">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="1ed73-180">セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査と応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="1ed73-180">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="1ed73-181">詳細については、「例 [: セキュリティ管理者がエクスプローラーから調査をトリガーする」を参照してください](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1ed73-181">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="1ed73-182">その他の記事</span><span class="sxs-lookup"><span data-stu-id="1ed73-182">Other articles</span></span>

<span data-ttu-id="1ed73-183">[[電子メール エンティティ] ページでメールを調査する](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="1ed73-183">[Investigate emails with the Email Entity Page](mdo-email-entity-page.md)</span></span>
