---
title: Microsoft Defender for Microsoft Defender for Microsoft Defender for Threat Explorer での脅威Office 365
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
description: セキュリティ コンプライアンス センターで脅威エクスプローラーまたはリアルタイム検出を使用して、脅威を効率的に &amp; 調査して対応します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295271"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="ce506-103">Microsoft Defender for Microsoft Defender for Microsoft Defender for Threat Explorer での脅威Office 365</span><span class="sxs-lookup"><span data-stu-id="ce506-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ce506-104">この記事の内容:</span><span class="sxs-lookup"><span data-stu-id="ce506-104">In this article:</span></span>

- [<span data-ttu-id="ce506-105">脅威エクスプローラーのウォークスルー</span><span class="sxs-lookup"><span data-stu-id="ce506-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="ce506-106">メールの調査</span><span class="sxs-lookup"><span data-stu-id="ce506-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="ce506-107">電子メールの修復</span><span class="sxs-lookup"><span data-stu-id="ce506-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="ce506-108">脅威の検出エクスペリエンスの改善</span><span class="sxs-lookup"><span data-stu-id="ce506-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="ce506-109">これは、Threat **Explorer (Explorer)** 、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) に関する **3** 記事シリーズの一部です。</span><span class="sxs-lookup"><span data-stu-id="ce506-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="ce506-110">このシリーズの他の 2 つの記事は、 [脅威](email-security-in-microsoft-defender.md) エクスプローラーと脅威エクスプローラーとリアルタイム検出の基本を備えたメール [セキュリティです](real-time-detections.md)。</span><span class="sxs-lookup"><span data-stu-id="ce506-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="ce506-111">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ce506-111">**Applies to**</span></span>
- [<span data-ttu-id="ce506-112">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ce506-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ce506-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ce506-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ce506-114">組織に[Microsoft Defender](defender-for-office-365.md)for Office 365権限がある場合は、エクスプローラー[](#required-licenses-and-permissions)またはリアルタイム検出を使用して脅威を検出および修復できます。 </span><span class="sxs-lookup"><span data-stu-id="ce506-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="ce506-115">[セキュリティ **& コンプライアンス** センター] で、[脅威の管理] に移動し、[**エクスプローラー**  ] または [リアルタイム検出]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ce506-115">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="ce506-116">Microsoft Defender for Office 365プラン 2 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="ce506-117">Microsoft Defender for Office 365プラン 1 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="ce506-120">これらのツールで以下のことができます。</span><span class="sxs-lookup"><span data-stu-id="ce506-120">With these tools, you can:</span></span>

- <span data-ttu-id="ce506-121">セキュリティ機能によって検出されたマルウェアMicrosoft 365表示する</span><span class="sxs-lookup"><span data-stu-id="ce506-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="ce506-122">フィッシング URL を表示し、[評決データ] をクリックする</span><span class="sxs-lookup"><span data-stu-id="ce506-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="ce506-123">エクスプローラーでビューから自動調査と応答プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="ce506-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="ce506-124">悪意のあるメールの調査など</span><span class="sxs-lookup"><span data-stu-id="ce506-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="ce506-125">詳細については、「Threat [Explorer を使用したメール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="ce506-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="ce506-126">脅威エクスプローラーのウォークスルー</span><span class="sxs-lookup"><span data-stu-id="ce506-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="ce506-127">Microsoft Defender for Office 365、プラン 1 とプラン 2 の 2 つのサブスクリプション プランがあります。</span><span class="sxs-lookup"><span data-stu-id="ce506-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="ce506-128">手動で操作された脅威の検出ツールは、両方のプラン、異なる名前、および異なる機能の両方に存在します。</span><span class="sxs-lookup"><span data-stu-id="ce506-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="ce506-129">Defender for Office 365プラン 1では、プラン 2 の脅威エクスプローラー *(エクスプローラー\*\*とも呼* ばれる) ハンティング ツールのサブセットであるリアルタイム検出が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="ce506-130">この一連の記事では、ほとんどの例は完全な Threat Explorer を使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="ce506-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="ce506-131">管理者は、リアルタイム検出で手順をテストして、適用場所を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce506-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="ce506-132">エクスプローラー ツールを開くには、[セキュリティ &**コンプライアンス** センターの脅威  >  **管理**  >  **エクスプローラー** (またはリアルタイムの検出 **) に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ce506-132">To open the Explorer tool, go to **Security & Compliance Center** > **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="ce506-133">既定では、[マルウェア] ページに移動しますが、[表示]ドロップダウンを使用してオプションを理解します。</span><span class="sxs-lookup"><span data-stu-id="ce506-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="ce506-134">フィッシングを探している場合、または脅威キャンペーンを掘り下ろしている場合は、それらのビューを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce506-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-135">![脅威エクスプローラーの [表示] ドロップダウン](../../media/threat-explorer-view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-135">![View drop down in Threat Explorer](../../media/threat-explorer-view-drop-down.png)</span></span>

<span data-ttu-id="ce506-136">セキュリティ操作 (Sec Ops) のユーザーが表示するデータを選択すると、スコープがユーザー申請のような狭いビューか、すべての電子メールのようなより広いビューかを選択すると、[送信者]ボタンを使用してさらにフィルター処理できます。 </span><span class="sxs-lookup"><span data-stu-id="ce506-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="ce506-137">フィルター処理を完了するには、[更新] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="ce506-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-138">![脅威エクスプローラーの [送信者] ボタン](../../media/threat-explorer-sender-button.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-138">![Sender button in Threat Explorer](../../media/threat-explorer-sender-button.png)</span></span>

<span data-ttu-id="ce506-139">エクスプローラーまたはリアルタイム検出でのフォーカスの絞り込みは、レイヤー内で考え得る。</span><span class="sxs-lookup"><span data-stu-id="ce506-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="ce506-140">1 つ目は **View です**。</span><span class="sxs-lookup"><span data-stu-id="ce506-140">The first is **View**.</span></span> <span data-ttu-id="ce506-141">2 つ目は、フィルター処理された *フォーカスと見なされます*。</span><span class="sxs-lookup"><span data-stu-id="ce506-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="ce506-142">たとえば、次のような決定を記録することで、脅威を見つける手順を追跡できます。エクスプローラーで問題を見つけるには、受信者フィルター フォーカスを持つマルウェア ビューを **選択** しました。</span><span class="sxs-lookup"><span data-stu-id="ce506-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="ce506-143">これにより、手順の再トレースが容易になります。</span><span class="sxs-lookup"><span data-stu-id="ce506-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="ce506-144">Sec Opsがタグを使用して、価値の高いターゲットと見なすアカウントにマークを付け、Tags フィルター フォーカスを持つフィッシング ビューなどの選択を行えます (使用する場合は日付範囲を含めます *)。*</span><span class="sxs-lookup"><span data-stu-id="ce506-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="ce506-145">これにより、時間範囲 (特定のフィッシング攻撃が業界で多く発生している日付など) の間に、高価値のユーザー ターゲットに向けられたフィッシングの試みが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="ce506-146">絞り込みは、日付範囲コントロールを使用して日付範囲に対して行えます。</span><span class="sxs-lookup"><span data-stu-id="ce506-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="ce506-147">ここでは、検出テクノロジ フィルターフォーカス **を使用** して、[マルウェア] ビュー **にエクスプローラーを** 表示できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="ce506-148">ただし、Sec Ops チーム **が** 深く掘り下げる高度なフィルター ボタンです。</span><span class="sxs-lookup"><span data-stu-id="ce506-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-149">![脅威エクスプローラーの高度なフィルター](../../media/threat-explorer-advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-149">![Advanced filter in Threat Explorer](../../media/threat-explorer-advanced-filter.png)</span></span>

<span data-ttu-id="ce506-150">[ **詳細設定]** フィルターをクリックすると、Sec Ops のハンターが自分でクエリを作成できるパネルが表示されます。表示する必要がある情報を含めるか除外することができます。</span><span class="sxs-lookup"><span data-stu-id="ce506-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="ce506-151">[エクスプローラー] ページのグラフとテーブルの両方に結果が反映されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-152">![クエリの結果](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="ce506-153">[列の **オプション] ボタン** を使用して、最も役に立つテーブルの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ce506-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-154">![[列のオプション] ボタンが強調表示されている](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-155">![列で使用可能なオプション](../../media/threat-explorer-column-options-details.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-155">![Available options in Columns](../../media/threat-explorer-column-options-details.png)</span></span>

<span data-ttu-id="ce506-156">同じ mien で、表示オプションをテストしてください。</span><span class="sxs-lookup"><span data-stu-id="ce506-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="ce506-157">異なる対象ユーザーは、同じデータの異なるプレゼンテーションにうまく反応します。</span><span class="sxs-lookup"><span data-stu-id="ce506-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="ce506-158">一部の閲覧者の場合、**メール** 配信元マップでは、脅威の横にある [キャンペーンの表示] オプションよりも迅速に脅威が広がっている、または目立たないと表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce506-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="ce506-159">Sec Ops は、これらのディスプレイを利用して、セキュリティと保護の必要性を強調するポイントを作成したり、後で比較したりして、アクションの有効性を実証することができます。</span><span class="sxs-lookup"><span data-stu-id="ce506-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-160">![メールの配信元マップ](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-161">![キャンペーンの表示オプション](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="ce506-162">メールの調査</span><span class="sxs-lookup"><span data-stu-id="ce506-162">Email investigation</span></span>

<span data-ttu-id="ce506-163">疑わしいメールが表示された場合は、名前をクリックして右側のフライアウトを展開します。</span><span class="sxs-lookup"><span data-stu-id="ce506-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="ce506-164">ここでは、Sec Ops に電子メール エンティティ ページを [表示できるバナーが](mdo-email-entity-page.md) 用意されています。</span><span class="sxs-lookup"><span data-stu-id="ce506-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="ce506-165">電子メール エンティティ ページは、[詳細] 、 [添付ファイル] 、[デバイス] の下にあるコンテンツをまとめて取得しますが、より整理されたデータが含まれています。 </span><span class="sxs-lookup"><span data-stu-id="ce506-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="ce506-166">これには、DMARC 結果、コピー オプション付きメール ヘッダーのプレーン テキスト表示、安全に起訴された添付ファイルに関する評決情報、削除された起訴ファイル (連絡先の IP アドレス、ページまたはファイルのスクリーンショットを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce506-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="ce506-167">URL とその評決も、同様の詳細が報告された一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="ce506-168">この段階に達すると、電子メール エンティティ ページは最終的な手順である修復に不可欠 *です*。</span><span class="sxs-lookup"><span data-stu-id="ce506-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-169">![[電子メール エンティティ] ページ](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="ce506-170">削除された添付ファイルの結果、含まれる URL の結果、安全なメール プレビューなど、リッチ メール エンティティ ページ ([分析] タブで以下に示す) の詳細については、こちらをクリック[してください](mdo-email-entity-page.md)。</span><span class="sxs-lookup"><span data-stu-id="ce506-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-171">![電子メール エンティティ ページの [分析] タブ](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="ce506-172">電子メールの修復</span><span class="sxs-lookup"><span data-stu-id="ce506-172">Email remediation</span></span>

<span data-ttu-id="ce506-173">Sec Ops のユーザーが電子メールが脅威と判断すると、次のエクスプローラーまたはリアルタイム検出手順は、脅威を処理して修復します。</span><span class="sxs-lookup"><span data-stu-id="ce506-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="ce506-174">これは、Threat Explorer に戻り、問題の電子メールのチェック ボックスをオンにして、[アクション] ボタンを使用することで **実行** できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-175">![脅威エクスプローラーの [アクション] ボタン](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="ce506-176">ここでは、アナリストは、メールをスパム、フィッシング、マルウェアとして報告したり、受信者に連絡したり、自動調査と応答 (または AIR) プレイブック (プラン 2 がある場合) のトリガーを含む詳細な調査などのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="ce506-177">または、メールをクリーンとして報告できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-178">![[アクション] ドロップダウン](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="ce506-179">脅威の検出エクスペリエンスの改善</span><span class="sxs-lookup"><span data-stu-id="ce506-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="ce506-180">アラート ID</span><span class="sxs-lookup"><span data-stu-id="ce506-180">Alert ID</span></span>

<span data-ttu-id="ce506-181">アラートから脅威エクスプローラーに移動すると、 **警告 ID** によってビューが **フィルター処理されます**。</span><span class="sxs-lookup"><span data-stu-id="ce506-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="ce506-182">これは、リアルタイム検出にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="ce506-183">特定のアラートに関連するメッセージ、および電子メールの合計 (カウント) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="ce506-184">メッセージがアラートの一部だったか確認できるだけでなく、そのメッセージから関連するアラートに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce506-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="ce506-185">最後に、次に示すアラート ID が URL に含まれます。 `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="ce506-185">Finally, alert ID is included in the URL, for example: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-186">![アラート ID のフィルター処理](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-187">![詳細フライアウトのアラート ID](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="ce506-188">試用版テナントのエクスプローラー (およびリアルタイム検出) のデータ保持と検索制限の拡張</span><span class="sxs-lookup"><span data-stu-id="ce506-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="ce506-189">この変更の一環として、アナリストは脅威エクスプローラーで 30 日間 (7 日間から増加) のメール データを検索し、フィルター処理し、Office P1 と P2 の両方の試用版テナントの Defender のリアルタイム検出を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="ce506-190">これは、保持の既定値が既に 30 日である P1 と P2 E5 の両方の顧客の実稼働テナントには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="ce506-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="ce506-191">更新されたエクスポートの制限</span><span class="sxs-lookup"><span data-stu-id="ce506-191">Updated Export limit</span></span> 

<span data-ttu-id="ce506-192">Threat Explorer からエクスポートできるメール レコードの数は、現在 200,000 件 (9990 件) です。</span><span class="sxs-lookup"><span data-stu-id="ce506-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="ce506-193">エクスポートできる列のセットは変更されません。</span><span class="sxs-lookup"><span data-stu-id="ce506-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="ce506-194">脅威エクスプローラーのタグ</span><span class="sxs-lookup"><span data-stu-id="ce506-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="ce506-195">ユーザー タグ機能はプレビュー機能であり、すべてのユーザーが利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce506-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="ce506-196">また、プレビューは変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce506-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="ce506-197">リリース スケジュールの詳細については、次のロードマップMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="ce506-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="ce506-198">ユーザー タグは、Microsoft Defender のユーザーの特定のグループを特定Office 365。</span><span class="sxs-lookup"><span data-stu-id="ce506-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ce506-199">ライセンスや構成などのタグの詳細については、「User tags」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="ce506-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="ce506-200">Threat Explorer では、次のエクスペリエンスでユーザー タグに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="ce506-201">メール グリッド ビュー</span><span class="sxs-lookup"><span data-stu-id="ce506-201">Email grid view</span></span>

<span data-ttu-id="ce506-202">アナリストがメール グリッドの **[タグ] 列** を見ていると、送信者または受信者のメールボックスに適用されたタグが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="ce506-203">既定では、優先アカウントのような *システム タグが* 最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-204">![メール グリッド ビューでタグをフィルター処理する](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="ce506-205">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="ce506-205">Filtering</span></span>

<span data-ttu-id="ce506-206">タグはフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-206">Tags can be used as filters.</span></span> <span data-ttu-id="ce506-207">優先度アカウント間でのみハントするか、特定のユーザー タグシナリオをこの方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="ce506-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="ce506-208">特定のタグを持つ結果を除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce506-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="ce506-209">タグを他のフィルターや日付範囲と組み合わせて調査範囲を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="ce506-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="ce506-210">[![フィルター タグ](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ce506-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-211">![タグをフィルター処理しない](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="ce506-212">電子メールの詳細の飛び出し</span><span class="sxs-lookup"><span data-stu-id="ce506-212">Email detail flyout</span></span>

<span data-ttu-id="ce506-213">送信者と受信者の個々のタグを表示するには、電子メールを選択してメッセージの詳細フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce506-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="ce506-214">[概要 **] タブ** では、送信者と受信者のタグが個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="ce506-215">送信者と受信者の個々のタグに関する情報は、CSV データとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ce506-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-216">![メールの詳細タグ](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="ce506-217">タグ情報は、URL クリック のフライアウトにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="ce506-218">表示するには、[フィッシング] または [すべてのメール] ビューに移動し、[URL > **URL** **クリック] タブをクリック** します。個々の URL フライアウトを選択すると、その URL のクリックに関する詳細 (そのクリックに関連付けられたタグを含む) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="ce506-219">更新されたタイムライン ビュー</span><span class="sxs-lookup"><span data-stu-id="ce506-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-220">![URL タグ](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="ce506-221">[このビデオ](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)を見て詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="ce506-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="ce506-222">拡張機能</span><span class="sxs-lookup"><span data-stu-id="ce506-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="ce506-223">上位の対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="ce506-223">Top targeted users</span></span>

<span data-ttu-id="ce506-224">[上位マルウェア ファミリ] には、[ **マルウェア] セクションの上位の** 対象ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="ce506-225">上位の対象ユーザーは、フィッシングビューとすべてのメール ビューを通じて拡張されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="ce506-226">アナリストは、上位 5 人の対象ユーザーと、各ビューの各ユーザーの試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="ce506-227">セキュリティ操作では、ユーザーは、各電子メール ビューのオフライン分析のために、最大 3,000 の制限を対象ユーザーのリストと試行回数でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ce506-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="ce506-228">また、試行回数 (下の図では 13 回など) を選択すると、脅威エクスプローラーでフィルター処理されたビューが開き、そのユーザーのメールや脅威の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-229">![上位の対象ユーザー](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="ce506-230">Exchangeトランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="ce506-230">Exchange transport rules</span></span>

<span data-ttu-id="ce506-231">セキュリティ運用チームは、メッセージに適用Exchangeトランスポート ルール (またはメール フロー ルール) を [電子メール] グリッド ビューに表示できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="ce506-232">グリッド **で [列のオプション**] を選択し、列Exchange **から [** トランスポート ルールの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ce506-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="ce506-233">[Exchangeルール] オプションは、メールの **[詳細**] フライアウトにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="ce506-234">メッセージに適用されるトランスポート ルールの名前と GUID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="ce506-235">アナリストは、トランスポート ルールの名前を使用してメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="ce506-236">これは CONTAINS 検索で、部分的な検索も実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ce506-237">Exchangeルールの検索と名前の可用性は、割り当てられた特定の役割によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="ce506-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="ce506-238">トランスポート ルール名と検索を表示するには、次のいずれかの役割またはアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce506-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="ce506-239">ただし、以下の役割やアクセス許可がなくても、アナリストはメールの詳細にトランスポート ルールのラベルと GUID 情報を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ce506-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="ce506-240">メール グリッド、電子メール フライアウト、フィルター、およびエクスポートの他のレコード表示エクスペリエンスは影響を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ce506-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="ce506-241">Exchange Onlineのみ - データ損失防止: すべて</span><span class="sxs-lookup"><span data-stu-id="ce506-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="ce506-242">Exchange OnlineOnly - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="ce506-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="ce506-243">Microsoft Azure Active DirectoryまたはExchange Online - セキュリティ管理者: すべて</span><span class="sxs-lookup"><span data-stu-id="ce506-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="ce506-244">Azure Active DirectoryまたはExchange Online - セキュリティ リーダー: All</span><span class="sxs-lookup"><span data-stu-id="ce506-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="ce506-245">Exchange OnlineOnly - トランスポート ルール: All</span><span class="sxs-lookup"><span data-stu-id="ce506-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="ce506-246">Exchange Onlineのみ - View-Only構成: すべて</span><span class="sxs-lookup"><span data-stu-id="ce506-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="ce506-247">電子メール グリッド、詳細フライアウト、およびエクスポート CSV 内で、ETRs には、次に示すように名前/GUID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="ce506-248">![Exchangeトランスポート ルール](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="ce506-249">受信コネクタ</span><span class="sxs-lookup"><span data-stu-id="ce506-249">Inbound connectors</span></span>

<span data-ttu-id="ce506-250">コネクタは、電子メールが組織または組織との間でどのように流れるMicrosoft 365のOffice 365です。</span><span class="sxs-lookup"><span data-stu-id="ce506-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="ce506-251">この機能を使用すると、セキュリティ制限またはコントロールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="ce506-252">Threat Explorer では、電子メールに関連するコネクタを表示し、コネクタ名を使用して電子メールを検索できます。</span><span class="sxs-lookup"><span data-stu-id="ce506-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="ce506-253">コネクタの検索は CONTAINS クエリで、部分的なキーワード検索が機能します。</span><span class="sxs-lookup"><span data-stu-id="ce506-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce506-254">![コネクタの詳細](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="ce506-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ce506-255">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce506-255">Required licenses and permissions</span></span>

<span data-ttu-id="ce506-256">エクスプローラーまたは[リアルタイム検出を使用するにはOffice 365](defender-for-office-365.md) Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce506-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="ce506-257">エクスプローラーは、Defender for Office 365プラン 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce506-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ce506-258">リアルタイム検出レポートは、Defender for Office 365プラン 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="ce506-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="ce506-259">Defender によって保護される必要があるすべてのユーザーにライセンスを割り当てる計画をOffice 365。</span><span class="sxs-lookup"><span data-stu-id="ce506-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="ce506-260">エクスプローラーとリアルタイム検出では、ライセンスを取得したユーザーの検出データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce506-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="ce506-261">エクスプローラーまたはリアルタイムの検出を表示および使用するには、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce506-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="ce506-262">セキュリティ コンプライアンス センター&:</span><span class="sxs-lookup"><span data-stu-id="ce506-262">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="ce506-263">組織の管理</span><span class="sxs-lookup"><span data-stu-id="ce506-263">Organization Management</span></span>
  - <span data-ttu-id="ce506-264">セキュリティ管理者 (この管理者は、管理者センター Azure Active Directory割り当てることができます ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="ce506-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="ce506-265">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="ce506-265">Security Reader</span></span>

- <span data-ttu-id="ce506-266">次Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="ce506-266">For Exchange Online:</span></span>

  - <span data-ttu-id="ce506-267">組織の管理</span><span class="sxs-lookup"><span data-stu-id="ce506-267">Organization Management</span></span>
  - <span data-ttu-id="ce506-268">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="ce506-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="ce506-269">"View-Only Recipients/表示専用受信者"</span><span class="sxs-lookup"><span data-stu-id="ce506-269">View-Only Recipients</span></span>
  - <span data-ttu-id="ce506-270">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="ce506-270">Compliance Management</span></span>

<span data-ttu-id="ce506-271">役割とアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce506-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="ce506-272">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce506-272">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="ce506-273">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ce506-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="ce506-274">Exchange Online の PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce506-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="ce506-275">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ce506-275">More information</span></span>

- [<span data-ttu-id="ce506-276">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="ce506-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="ce506-277">オンライン、オンライン、SharePoint、およびOneDriveで検出された悪意のあるMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce506-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="ce506-278">脅威エクスプローラー (およびリアルタイム検出) のビューの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="ce506-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="ce506-279">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ce506-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="ce506-280">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="ce506-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- <span data-ttu-id="ce506-281">[[電子メール エンティティ] ページでメールを調査する](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="ce506-281">[Investigate emails with the Email Entity Page](mdo-email-entity-page.md)</span></span>