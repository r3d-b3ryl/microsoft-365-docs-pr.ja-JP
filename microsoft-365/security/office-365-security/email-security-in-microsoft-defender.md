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
ms.openlocfilehash: a2a6d3d10cfa21c0ad2da948bff130cb9336ebd8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297629"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c692b-103">Microsoft Defender の脅威エクスプローラーを使用した電子メール Office 365</span><span class="sxs-lookup"><span data-stu-id="c692b-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="c692b-104">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="c692b-104">In this article:</span></span>

- [<span data-ttu-id="c692b-105">メールで検出されたマルウェアを表示する</span><span class="sxs-lookup"><span data-stu-id="c692b-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- <span data-ttu-id="c692b-106">[フィッシング URL を表示し、[評決データ] をクリックする](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="c692b-106">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- [<span data-ttu-id="c692b-107">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="c692b-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="c692b-108">これは、Threat **Explorer (Explorer)** 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) に関する **3** 記事シリーズの一部です。</span><span class="sxs-lookup"><span data-stu-id="c692b-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="c692b-109">このシリーズの他の 2 つの記事は、Threat Explorer と Threat [Explorer](threat-hunting-in-threat-explorer.md) での脅威の検出とリアルタイム検出 [の基本です](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="c692b-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="c692b-110">この記事では、セキュリティ機能によって電子メールで検出されたマルウェアやフィッシングの試みを表示および調査するMicrosoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="c692b-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="c692b-111">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c692b-111">**Applies to**</span></span>

- [<span data-ttu-id="c692b-112">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c692b-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c692b-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c692b-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="c692b-114">メールで検出されたマルウェアを表示する</span><span class="sxs-lookup"><span data-stu-id="c692b-114">View malware detected in email</span></span>

<span data-ttu-id="c692b-115">Microsoft 365 テクノロジによって並べ替えた電子メールで検出されたマルウェアを確認するには、[](threat-explorer-views.md#email--malware)エクスプローラーの [電子メール > マルウェア] ビュー (またはリアルタイム検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c692b-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="c692b-116">マルウェアは既定のビューなので、エクスプローラーを開いたとすぐに選択される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c692b-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="c692b-117">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="c692b-118">(この例では、エクスプローラーを使用します)。コンバージド セキュリティ センターにMicrosoft 365場合は、[メール] までスクロールし、& https://security.microsoft.com/) **エクスプローラーに**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-118">(This example uses Explorer.) If you're in the converged Microsoft 365 security center (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="c692b-119">ここから、ビューから開始し、調査する特定のフレーム (必要な場合) を選択し、エクスプローラーのウォークスルーに応じてフィルターを [フォーカスします](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)。</span><span class="sxs-lookup"><span data-stu-id="c692b-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="c692b-120">[表示] **メニューの** [メール マルウェア] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-120">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-121">![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-121">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="c692b-122">[送信者 **] を** クリックし、[基本検出 **テクノロジ]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-122">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="c692b-123">検出テクノロジは、レポートのフィルターとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-123">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-124">![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-124">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="c692b-125">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c692b-125">Choose an option.</span></span> <span data-ttu-id="c692b-126">次に、[更新] **ボタンを** 選択して、そのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="c692b-126">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-127">![選択された検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-127">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="c692b-128">レポートが更新され、選択したテクノロジ オプションを使用して、電子メールでマルウェアが検出された結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-128">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="c692b-129">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-129">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="c692b-130">フィッシング URL を表示し、[評決データ] をクリックする</span><span class="sxs-lookup"><span data-stu-id="c692b-130">View phishing URL and click verdict data</span></span>

<span data-ttu-id="c692b-131">許可、ブロック、および上書きされた URL の一覧を含む、メール内の URL を介してフィッシング詐欺の試みを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-131">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="c692b-132">クリックされた URL を識別するには、セーフ[リンクを](safe-links.md)構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c692b-132">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="c692b-133">[リンク] でクリック[セーフの](set-up-safe-links-policies.md)保護とログ記録を行う場合は、必ずリンク ポリシーをセーフしてください。</span><span class="sxs-lookup"><span data-stu-id="c692b-133">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="c692b-134">メッセージ内のフィッシング URL を確認し、フィッシング メッセージ内の URL[  >  ](threat-explorer-views.md#email--phish)をクリックするには、エクスプローラーまたはリアルタイム検出の [メール フィッシング] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="c692b-134">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="c692b-135">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-135">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="c692b-136">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="c692b-136">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="c692b-137">[表示] **メニューの** [メール フィッシング] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-137">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-138">![フィッシング コンテキストでのエクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-138">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="c692b-139">[送信者 **] を** クリックし **、[URL]** \> **[評決のクリック] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c692b-139">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="c692b-140">[ブロック] や [上書きブロック]などの 1 つ以上のオプションを選択し、そのフィルターを適用するオプションと同じ行の [更新] ボタンを選択します。 </span><span class="sxs-lookup"><span data-stu-id="c692b-140">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="c692b-141">(ブラウザー ウィンドウを更新しない)。</span><span class="sxs-lookup"><span data-stu-id="c692b-141">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-142">![URL とクリックの評決](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-142">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="c692b-143">レポートが更新され、レポートの下の [URL] タブに 2 つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-143">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="c692b-144">**上位 URL は** 、フィルター処理したメッセージ内の URL であり、メール配信アクションは URL ごとにカウントされます。</span><span class="sxs-lookup"><span data-stu-id="c692b-144">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="c692b-145">[フィッシング メール] ビューでは、通常、この一覧には正当な URL が含まれる。</span><span class="sxs-lookup"><span data-stu-id="c692b-145">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="c692b-146">攻撃者は、メッセージに良い URL と悪い URL を組み合わせ、配信を試みているが、悪意のあるリンクをより面白く見せている。</span><span class="sxs-lookup"><span data-stu-id="c692b-146">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="c692b-147">URL のテーブルはメールの総数で並べ替えされますが、この列は非表示に設定され、ビューが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-147">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="c692b-148">**トップ クリックは**、クリックセーフクリック数で並べ替えたリンクでラップされた URL の一覧です。</span><span class="sxs-lookup"><span data-stu-id="c692b-148">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="c692b-149">ビューを簡略化するために、この列も表示されません。</span><span class="sxs-lookup"><span data-stu-id="c692b-149">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="c692b-150">列別の合計カウントは、クリックセーフ URL の [リンク] クリックの評決カウントを示します。</span><span class="sxs-lookup"><span data-stu-id="c692b-150">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="c692b-151">[フィッシング メール] ビューでは、通常、疑わしい URL または悪意のある URL です。</span><span class="sxs-lookup"><span data-stu-id="c692b-151">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="c692b-152">ただし、このビューには、脅威ではないがフィッシング メッセージに含まれる URL が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c692b-152">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="c692b-153">ラップされていないリンクの URL クリックはここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="c692b-153">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="c692b-154">2 つの URL テーブルには、配信アクションと場所別のフィッシングメール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-154">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="c692b-155">この表には、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されます。そのため、ユーザーに表示された潜在的な不良リンクと、ユーザーがクリックした可能性のあるリンクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-155">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="c692b-156">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-156">From here, you can conduct further analysis.</span></span> <span data-ttu-id="c692b-157">たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-157">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c692b-158">![ブロックされたエクスプローラー URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="c692b-158">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="c692b-159">URL を選択して、詳細な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c692b-159">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c692b-160">[URL の飛び出し] ダイアログ ボックスで、電子メール メッセージのフィルター処理が削除され、環境内での URL の露出の完全なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-160">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="c692b-161">これにより、エクスプローラーで懸念される電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を見つけ、エクスプローラー ビュー自体に URL フィルターを追加することなく、([URL の詳細] ダイアログ ボックスを使用して) 環境内の URL 露出に関する理解を広げます。</span><span class="sxs-lookup"><span data-stu-id="c692b-161">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="c692b-162">クリックの評決の解釈</span><span class="sxs-lookup"><span data-stu-id="c692b-162">Interpretation of click verdicts</span></span>

<span data-ttu-id="c692b-163">メールまたは URL のフライアウト、トップ クリック、およびフィルター 処理では、さまざまなクリックの評決値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c692b-163">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="c692b-164">**なし:** URL の評決をキャプチャできません。</span><span class="sxs-lookup"><span data-stu-id="c692b-164">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="c692b-165">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c692b-165">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="c692b-166">**許可:** ユーザーは URL への移動を許可されました。</span><span class="sxs-lookup"><span data-stu-id="c692b-166">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="c692b-167">**ブロック:** ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c692b-167">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="c692b-168">**保留中の評決:** ユーザーに、削除保留中のページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="c692b-168">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="c692b-169">**ブロックされたオーバーライド:** ユーザーが URL への直接移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="c692b-169">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="c692b-170">ただし、ユーザーはブロックをオーバーロードして URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="c692b-170">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="c692b-171">**保留中の評決はバイパスされます。** ユーザーには、削除ページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="c692b-171">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="c692b-172">ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c692b-172">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="c692b-173">**エラー:** ユーザーにエラー ページが表示されたか、または評決のキャプチャでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="c692b-173">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="c692b-174">**失敗:** 評決のキャプチャ中に不明な例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c692b-174">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="c692b-175">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c692b-175">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="c692b-176">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="c692b-176">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="c692b-177">自動調査と対応機能は *、Microsoft Defender* でプラン 2 および *E5* Office 365でOffice 365できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-177">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="c692b-178">[自動調査と対応により](automated-investigation-response-office.md) 、セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-178">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="c692b-179">セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査と応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="c692b-179">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="c692b-180">詳細については、「例 [: セキュリティ管理者がエクスプローラーから調査をトリガーする」を参照してください](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="c692b-180">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="c692b-181">その他の記事</span><span class="sxs-lookup"><span data-stu-id="c692b-181">Other articles</span></span>

<span data-ttu-id="c692b-182">[[電子メール エンティティ] ページでメールを調査する](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="c692b-182">[Investigate emails with the Email Entity Page](mdo-email-entity-page.md)</span></span>
