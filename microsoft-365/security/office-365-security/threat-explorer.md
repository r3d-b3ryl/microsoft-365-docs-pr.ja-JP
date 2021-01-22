---
title: 脅威エクスプローラーとリアルタイムの検出
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: セキュリティ コンプライアンス センターでエクスプローラーとリアルタイムの検出を使用して、脅威を効率的に &amp; 調査して対応します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: caf795b421ac8e1e6785abff2fc49f0e49c391ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931712"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="731cc-103">脅威エクスプローラーとリアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="731cc-103">Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="731cc-104">組織が [Office 365](office-365-atp.md)用の Microsoft Defender を持ち、必要なアクセス許可を持っている場合は、エクスプローラーまたはリアルタイムの検出 (以前のリアルタイム レポート) に *アクセスできます*。 [](#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="731cc-104">If your organization has [Microsoft Defender for Office 365](office-365-atp.md) and you have the [necessary permissions](#required-licenses-and-permissions), you have access to *Explorer* or *Real-time detections*, which were formerly *Real-time reports*.</span></span> <span data-ttu-id="731cc-105">([新機能を参照してください](#new-features-in-threat-explorer-and-real-time-detections)。セキュリティ/コンプライアンス センター&、脅威の管理に移動し、[**エクスプローラー**  ] または [リアルタイムの検出 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-105">([See what's new.](#new-features-in-threat-explorer-and-real-time-detections)) In the Security & Compliance Center, go to **Threat management**, and then select **Explorer** _or_ **Real-time detections**.</span></span>

|<span data-ttu-id="731cc-106">Microsoft Defender for Office 365 プラン 2 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-106">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="731cc-107">Microsoft Defender for Office 365 プラン 1 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-107">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="731cc-110">エクスプローラーまたはリアルタイムの検出は、セキュリティ運用チームが脅威を効率的に調査して対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="731cc-110">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="731cc-111">レポートは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="731cc-111">The report resembles the following image:</span></span>

![脅威管理エクスプローラーに移動 \> する](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="731cc-113">このレポートでは、次の方法を実行できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-113">With this report, you can:</span></span>

- [<span data-ttu-id="731cc-114">Microsoft 365 のセキュリティ機能によって検出されたマルウェアを確認する</span><span class="sxs-lookup"><span data-stu-id="731cc-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="731cc-115">フィッシング URL を表示し、確認データをクリックする</span><span class="sxs-lookup"><span data-stu-id="731cc-115">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- <span data-ttu-id="731cc-116">[エクスプローラーのビューから](#start-automated-investigation-and-response) 自動調査と対応プロセスを開始する (Defender for Office 365 プラン 2 のみ)</span><span class="sxs-lookup"><span data-stu-id="731cc-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="731cc-117">悪意のあるメールの調査など</span><span class="sxs-lookup"><span data-stu-id="731cc-117">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a><span data-ttu-id="731cc-118">脅威エクスプローラーとリアルタイム検出の機能強化</span><span class="sxs-lookup"><span data-stu-id="731cc-118">Improvements to Threat Explorer and Real-time detections</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="731cc-119">脅威エクスプローラーのタグ</span><span class="sxs-lookup"><span data-stu-id="731cc-119">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="731cc-120">ユーザー タグ機能はプレビュー *中* であり、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-120">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="731cc-121">リリース スケジュールの詳細については、Microsoft 365 ロードマップを参照してください。</span><span class="sxs-lookup"><span data-stu-id="731cc-121">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="731cc-122">ユーザー タグは、Microsoft Defender で 365 用の特定のユーザー Office識別します。</span><span class="sxs-lookup"><span data-stu-id="731cc-122">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="731cc-123">ライセンスや構成など、タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="731cc-123">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="731cc-124">脅威エクスプローラーでは、次のエクスペリエンスでユーザー タグに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-124">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="731cc-125">メール グリッド ビュー</span><span class="sxs-lookup"><span data-stu-id="731cc-125">Email grid view</span></span>

<span data-ttu-id="731cc-126">電子 **メール** グリッドの [タグ] 列には、送信者または受信者のメールボックスに適用されたタグすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="731cc-126">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="731cc-127">既定では、優先度アカウントのようなシステム タグが最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-127">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-128">![メール グリッド ビューでタグをフィルター処理する](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-128">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="731cc-129">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="731cc-129">Filtering</span></span>

<span data-ttu-id="731cc-130">タグはフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-130">You can use tags as a filter.</span></span> <span data-ttu-id="731cc-131">優先順位の高いアカウントまたは特定のユーザー タグのシナリオをまたがってハントします。</span><span class="sxs-lookup"><span data-stu-id="731cc-131">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="731cc-132">特定のタグを持つ結果を除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="731cc-132">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="731cc-133">この機能を他のフィルターと組み合わせて調査範囲を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="731cc-133">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="731cc-134">[![フィルター タグ](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="731cc-134">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-135">![タグをフィルター処理しない](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-135">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="731cc-136">電子メール詳細のフライアウト</span><span class="sxs-lookup"><span data-stu-id="731cc-136">Email detail flyout</span></span>
<span data-ttu-id="731cc-137">送信者と受信者の個々のタグを表示するには、件名を選択してメッセージの詳細のフライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="731cc-137">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="731cc-138">[概要 **] タブ** では、送信者タグと受信者タグが電子メール用に存在する場合は、個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-138">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="731cc-139">送信者と受信者の個々のタグに関する情報は、エクスポートされた CSV データにも適用され、これらの詳細は 2 つの列に分いて表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-139">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-140">![メールの詳細タグ](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-140">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="731cc-141">タグ情報は、URL クリック のフライアウトにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-141">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="731cc-142">表示するには、[フィッシング] ビューまたは [すべてのメール] ビューに移動し **、[URL]** タブまたは **[URL クリック] タブに移動** します。個々の URL フライアウトを選択して、その URL のクリックに関する詳細 (そのクリックに関連付けられているタグを含む) を表示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-142">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-143">![URL タグ](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-143">![URL tags](../../media/tags-urls.png)</span></span>

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="731cc-144">脅威の検出エクスペリエンスの改善 (今後)</span><span class="sxs-lookup"><span data-stu-id="731cc-144">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="731cc-145">メールの脅威情報の更新</span><span class="sxs-lookup"><span data-stu-id="731cc-145">Updated threat information for emails</span></span>

<span data-ttu-id="731cc-146">電子メール レコードのデータ精度と一貫性を高めるプラットフォームとデータ品質の向上に重点を置いて取り組み、</span><span class="sxs-lookup"><span data-stu-id="731cc-146">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="731cc-147">ZAP プロセスの一部として電子メールで実行されるアクションなど、配信前および配信後の情報を 1 つのレコードに統合する機能が改善されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-147">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="731cc-148">スパムの特定、エンティティ レベルの脅威 (悪意のある URL など)、最新の配信場所などの詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="731cc-148">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="731cc-149">これらの更新後、メッセージに影響を与える配信後イベントに関係なく、メッセージごとに 1 つのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-149">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="731cc-150">アクションには、ZAP、手動による修復 (管理者の操作を意味する)、動的配信などがあります。</span><span class="sxs-lookup"><span data-stu-id="731cc-150">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="731cc-151">マルウェアとフィッシングの脅威の表示に加えて、メールに関連付けられているスパムの検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-151">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="731cc-152">メール内で、電子メールに関連付けられているすべての脅威と、対応する検出テクノロジを確認します。</span><span class="sxs-lookup"><span data-stu-id="731cc-152">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="731cc-153">電子メールには、0、1、または複数の脅威があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-153">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="731cc-154">メール のフライアウトの [詳細] セクションに **、現在の** 脅威が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-154">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="731cc-155">複数の脅威 (マルウェアやフィッシングなど) の検出技術フィールドには、脅威を特定した検出テクノロジである脅威検出マッピングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-155">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="731cc-156">一連の検出テクノロジには、新しい検出方法とスパム検出テクノロジが含まれています。</span><span class="sxs-lookup"><span data-stu-id="731cc-156">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="731cc-157">同じ一連の検出テクノロジを使用して、さまざまな電子メール ビュー (マルウェア、フィッシング、すべての電子メール) で結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-157">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="731cc-158">Verdict 分析は、必ずしもエンティティに関連付けられているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="731cc-158">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="731cc-159">たとえば、メールはフィッシングまたはスパムとして分類されますが、フィッシング/スパムの確認がスタンプされた URL はありません。</span><span class="sxs-lookup"><span data-stu-id="731cc-159">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="731cc-160">これは、フィルターは、決まった内容を割り当てる前にメールのコンテンツなどの詳細も評価するからです。</span><span class="sxs-lookup"><span data-stu-id="731cc-160">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="731cc-161">URL 内の脅威</span><span class="sxs-lookup"><span data-stu-id="731cc-161">Threats in URLs</span></span>

<span data-ttu-id="731cc-162">メール の [詳細] タブで、URL に対する特定の脅威を **確認** できます。脅威には、*マルウェア、\*\*フィッシング*、*スパム、* またはなしがあります。</span><span class="sxs-lookup"><span data-stu-id="731cc-162">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-163">![URL の脅威](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-163">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="731cc-164">更新されたタイムライン ビュー (今後)</span><span class="sxs-lookup"><span data-stu-id="731cc-164">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-165">![更新されたタイムライン ビュー](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-165">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="731cc-166">タイムライン ビューは、すべての配信イベントと配信後イベントを識別します。</span><span class="sxs-lookup"><span data-stu-id="731cc-166">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="731cc-167">この情報には、これらのイベントのサブセットについて、その時点で特定された脅威に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="731cc-167">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="731cc-168">タイムライン ビューには、実行された追加のアクション (ZAP や手動修復など) に関する情報と、そのアクションの結果も表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-168">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="731cc-169">タイムライン ビューの情報には、次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="731cc-169">Timeline view information includes:</span></span>

- <span data-ttu-id="731cc-170">**ソース:** イベントのソース。</span><span class="sxs-lookup"><span data-stu-id="731cc-170">**Source:** Source of the event.</span></span> <span data-ttu-id="731cc-171">管理者/システム/ユーザーの場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-171">It can be admin/system/user.</span></span>
- <span data-ttu-id="731cc-172">**イベント:** 元の配信、手動修復、ZAP、提出、動的配信などのトップ レベルのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="731cc-172">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="731cc-173">**アクション:** ZAP または管理者アクションの一部として実行された特定のアクション (削除済み (回復可能) など)。</span><span class="sxs-lookup"><span data-stu-id="731cc-173">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="731cc-174">**脅威:** その時点で特定された脅威 (マルウェア、フィッシング、スパム) について説明します。</span><span class="sxs-lookup"><span data-stu-id="731cc-174">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="731cc-175">**結果/詳細:** ZAP/管理者アクションの一部として実行されたかどうかなど、アクションの結果に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="731cc-175">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="731cc-176">元の配信場所と最新の配信場所</span><span class="sxs-lookup"><span data-stu-id="731cc-176">Original and latest delivery location</span></span>

<span data-ttu-id="731cc-177">現在、メール グリッドと電子メール のフライアウトに配信場所が表示されています。</span><span class="sxs-lookup"><span data-stu-id="731cc-177">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="731cc-178">[ **配信場所]** フィールドの名前が変更されました \**_元の配信場所_* _.</span><span class="sxs-lookup"><span data-stu-id="731cc-178">The **Delivery location** field is getting renamed \**_Original delivery location_* _.</span></span> <span data-ttu-id="731cc-179">また、別のフィールドである最新の配信 _\*_場所を導入しています_\*_。</span><span class="sxs-lookup"><span data-stu-id="731cc-179">And we're introducing another field, _*_Latest delivery location_*_.</span></span>

<span data-ttu-id="731cc-180">_ *元の配信場所*\* は、メールが最初に配信された場所に関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="731cc-180">_ *Original delivery location*\* will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="731cc-181">**最新の配信場所** には *、ZAP* のようなシステム操作や削除済みアイテムへの移動のような管理者アクションの後に電子メールが届いた *場所が表示されます*。</span><span class="sxs-lookup"><span data-stu-id="731cc-181">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="731cc-182">最新の配信場所は、配信後のメッセージの最後の既知の場所、またはシステム/管理者の操作を管理者に伝えるのが目的です。</span><span class="sxs-lookup"><span data-stu-id="731cc-182">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="731cc-183">電子メールにエンド ユーザーの操作は含まれます。</span><span class="sxs-lookup"><span data-stu-id="731cc-183">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="731cc-184">たとえば、ユーザーがメッセージを削除した場合や、メッセージをアーカイブ/pst に移動した場合、"配信" の場所は更新されません。</span><span class="sxs-lookup"><span data-stu-id="731cc-184">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="731cc-185">ただし、システム アクションによって場所が更新された場合 (たとえば、ZAP によってメールが検疫に移動した場合)、最新の配信場所は "検疫" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-185">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-186">![配信場所の更新](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-186">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="731cc-187">配信場所と配信アクションが "**不明**"と表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-187">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="731cc-188">メッセージが配信された場合、配信場所が"配信済み" として表示され、配信場所が "不明" と表示される場合がありますが、受信トレイ ルールによって、メッセージは受信トレイまたは迷惑メール フォルダーではなく、既定のフォルダー (下書きやアーカイブなど) に移動されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-188">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="731cc-189">**管理者/システム** の操作 (ZAP など) が試行されたが、メッセージが見つからなかった場合、最新の配信場所は不明になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-189">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="731cc-190">通常、アクションは、ユーザーがメッセージを移動または削除した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-190">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="731cc-191">このような場合は、タイムライン ビューの **[結果/詳細]** 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="731cc-191">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="731cc-192">「ユーザーがメッセージを移動または削除しました」というステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="731cc-192">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-193">![タイムラインの配信場所](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-193">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="731cc-194">追加のアクション</span><span class="sxs-lookup"><span data-stu-id="731cc-194">Additional actions</span></span>

<span data-ttu-id="731cc-195">*メールの配信* 後に追加のアクションが適用された。</span><span class="sxs-lookup"><span data-stu-id="731cc-195">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="731cc-196">*ZAP、* 手動修復 *(回復* 可能な削除などの管理者が実行したアクション)、動的配信、再処理 *(時間* 的に良好と検出されたメールの場合) を含む場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-196">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="731cc-197">保留中の変更の一環として、配信アクション フィルターに現在表示されている "Removed by ZAP" 値は削除されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-197">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="731cc-198">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span><span class="sxs-lookup"><span data-stu-id="731cc-198">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="731cc-199">検出テクノロジと追加アクション (特に ZAP シナリオ用) の新しいフィールドと値があります。 </span><span class="sxs-lookup"><span data-stu-id="731cc-199">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="731cc-200">既存の保存されたクエリと追跡されたクエリを評価して、新しい値で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-200">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]

> ![エクスプローラーでの追加アクション](../../media/Additional_Actions.png)

### <a name="system-overrides"></a><span data-ttu-id="731cc-202">システム オーバーライド</span><span class="sxs-lookup"><span data-stu-id="731cc-202">System overrides</span></span>

<span data-ttu-id="731cc-203">*システム オーバーライドを使用* すると、メッセージの配信場所に対して例外を設定できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-203">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="731cc-204">フィルタリング スタックによって識別される脅威および他の検出に基づいて、システムによって提供される配信場所を上書きします。</span><span class="sxs-lookup"><span data-stu-id="731cc-204">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="731cc-205">システム オーバーライドは、テナントポリシーまたはユーザー ポリシーを使用して設定し、ポリシーによって提案されたメッセージを配信できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-205">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="731cc-206">上書きでは、ユーザーが設定した過剰に広範な差出人セーフ リスト ポリシーなど、構成のギャップが原因で悪意のあるメッセージが意図せずに配信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-206">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="731cc-207">これらのオーバーライド値は次の場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-207">These override values can be:</span></span>

- <span data-ttu-id="731cc-208">ユーザー ポリシーで許可: ユーザーがメールボックス レベルでポリシーを作成し、ドメインまたは送信者を許可します。</span><span class="sxs-lookup"><span data-stu-id="731cc-208">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>
- <span data-ttu-id="731cc-209">ユーザー ポリシーによってブロック: ユーザーがメール ボックス レベルでポリシーを作成し、ドメインまたは送信者をブロックします。</span><span class="sxs-lookup"><span data-stu-id="731cc-209">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>
- <span data-ttu-id="731cc-210">組織ポリシーで許可: 組織のセキュリティ チームは、組織内のユーザーに対して送信者とドメインを許可するポリシーまたは Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を設定します。</span><span class="sxs-lookup"><span data-stu-id="731cc-210">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="731cc-211">これは、一連のユーザーまたは組織全体に対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-211">This can be for a set of users or the entire organization.</span></span>
- <span data-ttu-id="731cc-212">組織ポリシーによってブロック: 組織のセキュリティ チームは、組織内のユーザーの送信者、ドメイン、メッセージ言語、またはソース IP をブロックするポリシーまたはメール フロー ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="731cc-212">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="731cc-213">これは、一連のユーザーまたは組織全体に適用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-213">This can be applied to a set of users or the entire organization.</span></span>
- <span data-ttu-id="731cc-214">組織ポリシーによってブロックされるファイル拡張子: 組織のセキュリティ チームは、マルウェア対策ポリシー設定を通じてファイル名の拡張子をブロックします。</span><span class="sxs-lookup"><span data-stu-id="731cc-214">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="731cc-215">これらの値は、調査に役立つメールの詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-215">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="731cc-216">Secops チームは、リッチ フィルタリング機能を使用して、ブロックされたファイル拡張子をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="731cc-216">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="731cc-217">[![エクスプローラーでのシステム オーバーライド](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="731cc-217">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-218">![エクスプローラーのシステム オーバーライド グリッド](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-218">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="731cc-219">URL とクリック エクスペリエンスの改善</span><span class="sxs-lookup"><span data-stu-id="731cc-219">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="731cc-220">改善点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="731cc-220">The improvements include:</span></span>

- <span data-ttu-id="731cc-221">URL フライアウトの [クリック] セクションに、完全にクリックされた URL  (URL の一部であるクエリ パラメーターを含む) を表示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-221">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="731cc-222">現時点では、URL ドメインとパスはタイトル バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-222">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="731cc-223">この情報を拡張して、完全な URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-223">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="731cc-224">URL フィルター全体の修正 (*URL* と *URL* ドメイン、URL ドメイン、パス): 更新は、URL/クリックの可否を含むメッセージの検索に影響します。</span><span class="sxs-lookup"><span data-stu-id="731cc-224">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="731cc-225">プロトコルに依存しない検索のサポートが有効になっているので、使用せずに URL を検索できます `http` 。</span><span class="sxs-lookup"><span data-stu-id="731cc-225">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="731cc-226">既定では、別の値が明示的に指定されていない限り、URL 検索は http にマップされます。</span><span class="sxs-lookup"><span data-stu-id="731cc-226">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="731cc-227">例:</span><span class="sxs-lookup"><span data-stu-id="731cc-227">For example:</span></span>

   -  <span data-ttu-id="731cc-228">URL、URL ドメイン、および URL ドメインおよびパス フィルター フィールドで、プレフィックスの付いていなくても `http://` 検索します。   </span><span class="sxs-lookup"><span data-stu-id="731cc-228">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="731cc-229">検索は同じ結果を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-229">The searches should show the same results.</span></span>

   -  <span data-ttu-id="731cc-230">URL でプレフィックス `https://` を検索 **します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-230">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="731cc-231">値を指定しない場合、プレフィックス `http://` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-231">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="731cc-232">`/` は **、URL パス、URL** ドメイン **、URL** ドメイン、およびパス フィールドの先頭と末尾 **では無視** されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-232">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="731cc-233">`/` URL フィールドの末尾 **は** 無視されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-233">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="731cc-234">フィッシングの信頼度</span><span class="sxs-lookup"><span data-stu-id="731cc-234">Phish confidence level</span></span>

<span data-ttu-id="731cc-235">フィッシングの信頼度は、メールが 「フィッシング」として分類された信頼度を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="731cc-235">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="731cc-236">使用できる値は *、High* と *Normal の 2 つです*。</span><span class="sxs-lookup"><span data-stu-id="731cc-236">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="731cc-237">初期段階では、このフィルターは脅威エクスプローラーの [フィッシング] ビューでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-237">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="731cc-238">[![エクスプローラーの Phish Confidence Level](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="731cc-238">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="731cc-239">ZAP URL シグナル</span><span class="sxs-lookup"><span data-stu-id="731cc-239">ZAP URL signal</span></span>

<span data-ttu-id="731cc-240">ZAP URL シグナルは、通常、電子メールがフィッシングとして識別され、配信後に削除された ZAP フィッシングアラート シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-240">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="731cc-241">このシグナルは、アラートをエクスプローラーの対応する結果に接続します。</span><span class="sxs-lookup"><span data-stu-id="731cc-241">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="731cc-242">これは、アラートの IIC の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="731cc-242">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="731cc-243">検出プロセスを改善するために、脅威エクスプローラーとリアルタイム検出を更新して、ハンティング エクスペリエンスの一貫性を高めていました。</span><span class="sxs-lookup"><span data-stu-id="731cc-243">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="731cc-244">変更点の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-244">The changes are outlined here:</span></span>

- [<span data-ttu-id="731cc-245">タイムゾーンの改善</span><span class="sxs-lookup"><span data-stu-id="731cc-245">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="731cc-246">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="731cc-246">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="731cc-247">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="731cc-247">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="731cc-248">製品情報の更新で</span><span class="sxs-lookup"><span data-stu-id="731cc-248">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="731cc-249">ユーザー タグでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="731cc-249">Filter by user tags</span></span>

<span data-ttu-id="731cc-250">システム タグまたはカスタム ユーザー タグで並べ替えとフィルター処理を行い、脅威の範囲をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-250">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="731cc-251">詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="731cc-251">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="731cc-252">ユーザー タグによるフィルター処理と並べ替えは、現在パブリック プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="731cc-252">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="731cc-253">この機能は、商用リリース前に大幅に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-253">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="731cc-254">Microsoft は、その情報に関して明示または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="731cc-254">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

![エクスプローラーの [タグ] 列](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a><span data-ttu-id="731cc-256">タイムゾーンの改善</span><span class="sxs-lookup"><span data-stu-id="731cc-256">Timezone improvements</span></span>

<span data-ttu-id="731cc-257">ポータルとエクスポートされたデータのメール レコードのタイム ゾーンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-257">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="731cc-258">メール グリッド、詳細のフライアウト、メール タイムライン、類似のメールなど、複数のエクスペリエンスで表示されます。そのため、結果セットのタイム ゾーンは明確です。</span><span class="sxs-lookup"><span data-stu-id="731cc-258">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-259">![エクスプローラーでタイム ゾーンを表示する](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-259">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="731cc-260">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="731cc-260">Update in the refresh process</span></span>

<span data-ttu-id="731cc-261">一部のユーザーは、自動更新 (たとえば、日付を変更するとすぐにページが更新されます)、および手動更新 (その他のフィルターの場合) との混乱についてコメントしています。</span><span class="sxs-lookup"><span data-stu-id="731cc-261">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="731cc-262">同様に、フィルターを削除すると自動更新が行います。</span><span class="sxs-lookup"><span data-stu-id="731cc-262">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="731cc-263">クエリの変更中にフィルターを変更すると、一貫性のない検索エクスペリエンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-263">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="731cc-264">これらの問題を解決するために、手動フィルターメカニズムに移行します。</span><span class="sxs-lookup"><span data-stu-id="731cc-264">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="731cc-265">ユーザーは、エクスペリエンスの観点から、(フィルター セットと日付から) さまざまなフィルターの範囲を適用および削除し、更新ボタンを選択して、クエリを定義した後に結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-265">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="731cc-266">[更新] ボタンも画面で強調されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-266">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="731cc-267">関連するヒントと製品内のドキュメントも更新されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-267">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-268">![[更新] を選択して結果をフィルター処理する](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-268">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="731cc-269">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="731cc-269">Chart drilldown to add to filters</span></span>

<span data-ttu-id="731cc-270">凡例値をグラフに追加して、フィルターとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-270">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="731cc-271">[更新] **ボタンを** 選択して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="731cc-271">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-272">![グラフをドリルダウンしてフィルター処理する](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-272">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="731cc-273">製品内情報の更新</span><span class="sxs-lookup"><span data-stu-id="731cc-273">In-product information updates</span></span>

<span data-ttu-id="731cc-274">グリッド内の検索結果の総数など、製品内で追加の詳細が利用可能になります (下記を参照)。</span><span class="sxs-lookup"><span data-stu-id="731cc-274">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="731cc-275">ラベル、エラー メッセージ、ヒントが改善され、フィルター、検索エクスペリエンス、および結果セットに関する詳細な情報が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="731cc-275">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-276">![製品内情報の表示](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-276">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="731cc-277">脅威エクスプローラーの拡張機能</span><span class="sxs-lookup"><span data-stu-id="731cc-277">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="731cc-278">上位の対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="731cc-278">Top targeted users</span></span>

<span data-ttu-id="731cc-279">現在では、メールの [マルウェア] ビューの [上位マルウェア ファミリ] セクションで、上位の対象ユーザー **の一覧を公開** しています。</span><span class="sxs-lookup"><span data-stu-id="731cc-279">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="731cc-280">このビューは、[フィッシング] ビューと [すべてのメール] ビューでも拡張されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-280">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="731cc-281">上位 5 人の対象ユーザーと、対応するビューの各ユーザーの試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-281">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="731cc-282">たとえば、[フィッシング] ビューには、フィッシングの試行回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-282">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="731cc-283">各電子メール ビューのオフライン分析の試行回数と共に、最大 3,000 の制限を持つ対象ユーザーの一覧をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="731cc-283">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="731cc-284">さらに、試行回数を選択すると (次の図では 13 回など)、脅威エクスプローラーでフィルター処理されたビューが開くので、そのユーザーのメールと脅威の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-284">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-285">![上位の対象ユーザー](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-285">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="731cc-286">Exchange トランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="731cc-286">Exchange transport rules</span></span>

<span data-ttu-id="731cc-287">データ エンリッチメントの一環として、メッセージに適用されたさまざまな Exchange トランスポート ルール (ETR) を表示できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-287">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="731cc-288">この情報は、[電子メール] グリッド ビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-288">This information will be available in the Email grid view.</span></span> <span data-ttu-id="731cc-289">表示するには、グリッドで **[列] オプション** を選択し、列オプションから **Exchange トランスポート ルール** を追加します。</span><span class="sxs-lookup"><span data-stu-id="731cc-289">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="731cc-290">また、メールの [詳細] **フライアウト** にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-290">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="731cc-291">メッセージに適用されたトランスポート ルールの GUID と名前の両方を表示できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-291">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="731cc-292">トランスポート ルールの名前を使用してメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-292">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="731cc-293">これは"含まれている" 検索です。つまり、部分的な検索も実行できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-293">This is a "Contains" search, which means you can do partial searches as well.</span></span>

#### <a name="important-note"></a><span data-ttu-id="731cc-294">重要な注意点:</span><span class="sxs-lookup"><span data-stu-id="731cc-294">Important note:</span></span>

<span data-ttu-id="731cc-295">ETR 検索と名前の可用性は、自分に割り当てられている特定の役割によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="731cc-295">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="731cc-296">ETR 名と検索を表示するには、次のいずれかのロール/アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="731cc-296">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="731cc-297">これらの役割が割り当てられていない場合は、トランスポート ルールの名前を表示したり、ETR 名を使用してメッセージを検索したりできない。</span><span class="sxs-lookup"><span data-stu-id="731cc-297">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="731cc-298">ただし、[電子メールの詳細] に ETR ラベルと GUID 情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-298">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="731cc-299">電子メール グリッド、電子メール のフライアウト、フィルター、およびエクスポートのその他の記録表示エクスペリエンスは影響を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="731cc-299">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>

- <span data-ttu-id="731cc-300">EXO のみ - データ損失防止: すべて</span><span class="sxs-lookup"><span data-stu-id="731cc-300">EXO Only - Data Loss Prevention: All</span></span>
- <span data-ttu-id="731cc-301">EXO のみ - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="731cc-301">EXO Only - O365SupportViewConfig: All</span></span>
- <span data-ttu-id="731cc-302">Microsoft Azure Active Directory または EXO - セキュリティ管理者: すべて</span><span class="sxs-lookup"><span data-stu-id="731cc-302">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
- <span data-ttu-id="731cc-303">AAD または EXO - セキュリティ リーダー: すべて</span><span class="sxs-lookup"><span data-stu-id="731cc-303">AAD or EXO - Security Reader: All</span></span>
- <span data-ttu-id="731cc-304">EXO のみ - トランスポート ルール: すべて</span><span class="sxs-lookup"><span data-stu-id="731cc-304">EXO Only - Transport Rules: All</span></span>
- <span data-ttu-id="731cc-305">EXO のみ - View-Only構成: すべて</span><span class="sxs-lookup"><span data-stu-id="731cc-305">EXO Only - View-Only Configuration: All</span></span>

<span data-ttu-id="731cc-306">電子メール グリッド、詳細のフライアウト、エクスポートされた CSV では、以下に示すように、EET には名前/GUID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-306">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-307">![Exchange トランスポート ルール](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-307">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="731cc-308">受信コネクタ</span><span class="sxs-lookup"><span data-stu-id="731cc-308">Inbound connectors</span></span>

<span data-ttu-id="731cc-309">コネクタは、Microsoft 365 または Office 365 組織との間で電子メールを流す方法をカスタマイズする手順のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="731cc-309">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="731cc-310">この機能を使用すると、セキュリティの制限や制御を適用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-310">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="731cc-311">脅威エクスプローラーで、メールに関連するコネクタを表示し、コネクタ名を使用してメールを検索できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-311">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="731cc-312">コネクタの検索は、実際には "含まれている" ので、部分的なキーワード検索も機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-312">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="731cc-313">メイン グリッド ビュー、詳細フライアウト、およびエクスポートされた CSV では、コネクタは次のように名前/GUID 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-313">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-314">![コネクタの詳細](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-314">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="731cc-315">脅威エクスプローラーとリアルタイム検出の新機能</span><span class="sxs-lookup"><span data-stu-id="731cc-315">New features in Threat Explorer and Real-time detections</span></span>

<span data-ttu-id="731cc-316">脅威エクスプローラーとリアルタイム検出では、次の 3 つの新機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-316">Three new features are available in Threat Explorer and Real-time detections:</span></span>

- [<span data-ttu-id="731cc-317">メール ヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="731cc-317">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="731cc-318">メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="731cc-318">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="731cc-319">URL クリック データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="731cc-319">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="731cc-320">これらの新機能の概要を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-320">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="731cc-321">メール ヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="731cc-321">Preview email header and download email body</span></span>

<span data-ttu-id="731cc-322">これで、メール ヘッダーをプレビューし、脅威エクスプローラーでメール本文をダウンロードできます。管理者は、ダウンロードしたヘッダー/電子メール メッセージに脅威を分析できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-322">You can now preview an email header and download the email body in Threat Explorer Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="731cc-323">電子メール メッセージをダウンロードすると情報が危険にさらされる可能性があるから、このプロセスは役割ベースのアクセス制御 (RBAC) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-323">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="731cc-324">すべての電子メールメッセージ ビューでメールとプレビュー ヘッダーをダウンロードする機能を付与するには、新しい役割 Preview を別の役割グループ (セキュリティ操作やセキュリティ管理者など) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-324">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="731cc-325">エクスプローラーとリアルタイムの検出では、電子メール メッセージの配信場所のより完全な画像を提供する新しいフィールドも取得します。</span><span class="sxs-lookup"><span data-stu-id="731cc-325">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="731cc-326">これらの変更により、Security Ops のハンティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="731cc-326">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="731cc-327">しかし、主な結果は、問題のある電子メール メッセージの場所を一目で把握できるという結果です。</span><span class="sxs-lookup"><span data-stu-id="731cc-327">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="731cc-328">これを行う方法</span><span class="sxs-lookup"><span data-stu-id="731cc-328">How is this done?</span></span> <span data-ttu-id="731cc-329">配信状態は、次の 2 つの列に分かれました。</span><span class="sxs-lookup"><span data-stu-id="731cc-329">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="731cc-330">**配信アクション** - メールの状態。</span><span class="sxs-lookup"><span data-stu-id="731cc-330">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="731cc-331">**配信場所** - 電子メールがルーティングされた場所。</span><span class="sxs-lookup"><span data-stu-id="731cc-331">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="731cc-332">*配信アクション* は、既存のポリシーまたは検出のために電子メールに対して実行されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="731cc-332">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="731cc-333">電子メールに対して実行できるアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-333">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="731cc-334">配信</span><span class="sxs-lookup"><span data-stu-id="731cc-334">Delivered</span></span>|<span data-ttu-id="731cc-335">Junked</span><span class="sxs-lookup"><span data-stu-id="731cc-335">Junked</span></span>|<span data-ttu-id="731cc-336">Blocked</span><span class="sxs-lookup"><span data-stu-id="731cc-336">Blocked</span></span>|<span data-ttu-id="731cc-337">置き換え</span><span class="sxs-lookup"><span data-stu-id="731cc-337">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="731cc-338">メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーはアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="731cc-338">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="731cc-339">メールがユーザーの [迷惑メール] フォルダーまたは [削除済み] フォルダーに送信され、ユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="731cc-339">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="731cc-340">検疫された、失敗した、またはドロップされたメール。</span><span class="sxs-lookup"><span data-stu-id="731cc-340">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="731cc-341">これらのメールにはユーザーがアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="731cc-341">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="731cc-342">電子メールには、悪意のある添付ファイルが .txt ファイルに置き換え、添付ファイルが悪意のある添付ファイルであるという状態でした。</span><span class="sxs-lookup"><span data-stu-id="731cc-342">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="731cc-343">ユーザーが表示できる機能と表示できない機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-343">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="731cc-344">エンド ユーザーがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="731cc-344">Accessible to end users</span></span>|<span data-ttu-id="731cc-345">エンド ユーザーがアクセスできない</span><span class="sxs-lookup"><span data-stu-id="731cc-345">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="731cc-346">配信</span><span class="sxs-lookup"><span data-stu-id="731cc-346">Delivered</span></span>|<span data-ttu-id="731cc-347">Blocked</span><span class="sxs-lookup"><span data-stu-id="731cc-347">Blocked</span></span>|
|<span data-ttu-id="731cc-348">Junked</span><span class="sxs-lookup"><span data-stu-id="731cc-348">Junked</span></span>|<span data-ttu-id="731cc-349">置き換え</span><span class="sxs-lookup"><span data-stu-id="731cc-349">Replaced</span></span>|

<span data-ttu-id="731cc-350">**配信場所** には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-350">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="731cc-351">これは、 \* 配信アクション _. に \*_リンク_\* されています。</span><span class="sxs-lookup"><span data-stu-id="731cc-351">It's linked to \**_Delivery action_* _.</span></span> <span data-ttu-id="731cc-352">次の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-352">These are the possible values:</span></span>

- <span data-ttu-id="731cc-353">_Inboxまたはフォルダー\*: メールは受信トレイまたはフォルダー内にあります (メール ルールに従います)。</span><span class="sxs-lookup"><span data-stu-id="731cc-353">_Inbox or folder\*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="731cc-354">*オンプレミスまたは外部*: メールボックスはクラウド上に存在しませんが、オンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="731cc-354">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="731cc-355">*迷惑メール* フォルダー : メールはユーザーの [迷惑メール] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="731cc-355">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="731cc-356">*削除済みアイテム フォルダー*: ユーザーの [削除済みアイテム] フォルダー内のメール。</span><span class="sxs-lookup"><span data-stu-id="731cc-356">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="731cc-357">*検疫*: メールは検疫中であり、ユーザーのメールボックスには含めではありません。</span><span class="sxs-lookup"><span data-stu-id="731cc-357">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="731cc-358">*Failed*: 電子メールがメールボックスに到達できなかった。</span><span class="sxs-lookup"><span data-stu-id="731cc-358">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="731cc-359">*破棄*: メール フローのどこかでメールが失われました。</span><span class="sxs-lookup"><span data-stu-id="731cc-359">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="731cc-360">メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="731cc-360">Email timeline</span></span>

<span data-ttu-id="731cc-361">電子 **メールのタイムライン** は、管理者の検索エクスペリエンスを向上させる新しいエクスプローラー機能です。</span><span class="sxs-lookup"><span data-stu-id="731cc-361">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="731cc-362">イベントを理解するためにさまざまな場所を確認するために費やされる時間が削減されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-362">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="731cc-363">電子メールが届いた時点または近くで複数のイベントが発生すると、それらのイベントはタイムライン ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-363">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="731cc-364">メールの配信後に発生する一部のイベントは、[特別な操作] **列にキャプチャ** されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-364">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="731cc-365">管理者は、タイムラインの情報とメールの配信後に実行される特別なアクションを組み合わせて、ポリシーの動作、メールが最終的にルーティングされた場所、場合によっては最終的な評価の結果に関する洞察を得られます。</span><span class="sxs-lookup"><span data-stu-id="731cc-365">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="731cc-366">詳細については [、「365](investigate-malicious-email-that-was-delivered.md)で配信された悪意のあるメールの調査と修復Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="731cc-366">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="731cc-367">URL クリック データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="731cc-367">Export URL click data</span></span>

<span data-ttu-id="731cc-368">URL クリックのレポートを Microsoft Excel にエクスポートして、ネットワーク メッセージ **ID** を表示し **、[Verdict]** をクリックして URL クリックトラフィックの発信元を説明できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-368">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="731cc-369">動作のしくみは次のとおりです。Office 365 クイック起動バーの脅威管理では、次のチェーンに従います。</span><span class="sxs-lookup"><span data-stu-id="731cc-369">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="731cc-370">**エクスプローラー** \>**フィッシングの表示** \>**クリック数** \>**上位 URL または** **URL トップ クリックは** \> 、任意のレコードを選択して URL フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="731cc-370">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="731cc-371">一覧で URL を選択すると、新しい [エクスポート] ボタンがフライアウト パネルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-371">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="731cc-372">レポートを簡単にするために、このボタンを使用して Excel スプレッドシートにデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="731cc-372">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="731cc-373">リアルタイム検出レポートで同じ場所に移動するには、次のパスに従います。</span><span class="sxs-lookup"><span data-stu-id="731cc-373">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="731cc-374">**エクスプローラー** \>**リアルタイム検出** \>**フィッシングの表示** \>**URL** \>**トップ URL または** **[トップ クリック**] 任意のレコードを選択して URL フライアウトを開き、[ \> \> クリック] タブ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="731cc-374">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="731cc-375">ネットワーク メッセージ ID は、エクスプローラーまたは関連付けられているサード パーティ製ツールを使って ID を検索すると、クリックを特定のメールにマップします。</span><span class="sxs-lookup"><span data-stu-id="731cc-375">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="731cc-376">このような検索では、クリック結果に関連付けられている電子メールが識別されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-376">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="731cc-377">関連付けされたネットワーク メッセージ ID を使用すると、より迅速かつ強力な分析が可能になります。</span><span class="sxs-lookup"><span data-stu-id="731cc-377">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="731cc-378">![エクスプローラーの [クリック] タブ](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-378">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="731cc-379">電子メールで検出されたマルウェアをテクノロジ別に確認する</span><span class="sxs-lookup"><span data-stu-id="731cc-379">See malware detected in email by technology</span></span>

<span data-ttu-id="731cc-380">メールで検出されたマルウェアを Microsoft 365 テクノロジで並べ替えたとします。</span><span class="sxs-lookup"><span data-stu-id="731cc-380">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="731cc-381">これを行うには、エクスプローラーの [[>]](threat-explorer-views.md#email--malware) ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="731cc-381">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="731cc-382">セキュリティ センター コンプライアンス & () で、脅威 <https://protection.office.com> **管理** \> **エクスプローラー** (または **リアルタイムの検出) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-382">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="731cc-383">(この例では、Explorer を使用します)。</span><span class="sxs-lookup"><span data-stu-id="731cc-383">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="731cc-384">[表示] **メニューで** 、[メール マルウェア] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-384">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-385">![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-385">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="731cc-386">[ **送信者] を** クリックし、[基本検出 **テクノロジ** \> **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-386">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="731cc-387">これで、検出テクノロジがレポートのフィルターとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-387">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-388">![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-388">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="731cc-389">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="731cc-389">Choose an option.</span></span> <span data-ttu-id="731cc-390">次に、[更新 **] ボタン** を選択して、そのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="731cc-390">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-391">![選択した検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-391">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="731cc-392">レポートが更新され、選択したテクノロジ オプションを使用して、マルウェアが電子メールで検出した結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-392">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="731cc-393">ここから、詳細な分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-393">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="731cc-394">フィッシング URL を表示し、確認データをクリックする</span><span class="sxs-lookup"><span data-stu-id="731cc-394">View phishing URL and click verdict data</span></span>

<span data-ttu-id="731cc-395">許可、ブロック、上書きされた URL の一覧を含む、電子メール内の URL を介したフィッシング詐欺の試行を確認するとします。</span><span class="sxs-lookup"><span data-stu-id="731cc-395">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="731cc-396">クリックされた URL を識別するには、安全なリンク [を構成する](atp-safe-links.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-396">To identify URLs that were clicked, [Safe Links](atp-safe-links.md) must be configured.</span></span> <span data-ttu-id="731cc-397">クリック時の保護と、[](set-up-atp-safe-links-policies.md)安全なリンクによるクリックの確認のログ記録に対して、安全なリンク ポリシーを設定してください。</span><span class="sxs-lookup"><span data-stu-id="731cc-397">Make sure that you set up [Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="731cc-398">メッセージ内のフィッシング URL を確認し、フィッシング メッセージ内の URL[  >  ](threat-explorer-views.md#email--phish)をクリックするには、エクスプローラーの [電子メール フィッシング] ビューまたはリアルタイム検出を使用します。</span><span class="sxs-lookup"><span data-stu-id="731cc-398">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="731cc-399">セキュリティ センター コンプライアンス & () で、脅威 <https://protection.office.com> **管理** \> **エクスプローラー** (または **リアルタイムの検出) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-399">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="731cc-400">(この例では、Explorer を使用します)。</span><span class="sxs-lookup"><span data-stu-id="731cc-400">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="731cc-401">[表示] **メニューで** 、[メール フィッシング] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-401">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-402">![フィッシング コンテキストでのエクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-402">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="731cc-403">[ **送信者] を** クリックし **、[URL] を選択して** \> **[Click verdict] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="731cc-403">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="731cc-404">ブロック、上書きブロックなどの 1 つ以上のオプションを選択し、そのフィルターを適用するオプションと同じ行の [更新] ボタンを選択します。 </span><span class="sxs-lookup"><span data-stu-id="731cc-404">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="731cc-405">(ブラウザー ウィンドウを更新しない)。</span><span class="sxs-lookup"><span data-stu-id="731cc-405">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-406">![URL とクリックの Verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-406">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="731cc-407">レポートが更新され、レポートの下の [URL] タブに次の 2 つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-407">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="731cc-408">**上位 URL は** 、フィルター処理したメッセージ内の URL と、各 URL の電子メール配信アクションのカウントです。</span><span class="sxs-lookup"><span data-stu-id="731cc-408">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="731cc-409">フィッシング メール ビューでは、通常、この一覧には正当な URL が含まれる。</span><span class="sxs-lookup"><span data-stu-id="731cc-409">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="731cc-410">攻撃者は、メッセージ内に良い URL と悪い URL を組み合わせ、配信を試みているが、悪意のあるリンクをより興味深く見せている。</span><span class="sxs-lookup"><span data-stu-id="731cc-410">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="731cc-411">URL のテーブルは合計メール数で並べ替わりますが、この列は非表示でビューを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="731cc-411">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="731cc-412">**トップ クリックは** 、クリックされた安全なリンクでラップされた URL で、合計クリック数で並べ替えされています。</span><span class="sxs-lookup"><span data-stu-id="731cc-412">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="731cc-413">ビューを簡略化するために、この列も表示されません。</span><span class="sxs-lookup"><span data-stu-id="731cc-413">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="731cc-414">列別の総数は、クリックされた各 URL の 「安全なリンク」クリックの否認カウントを示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-414">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="731cc-415">フィッシング メール ビューでは、通常、これらは疑わしい URL または悪意のある URL です。</span><span class="sxs-lookup"><span data-stu-id="731cc-415">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="731cc-416">ただし、ビューには、脅威ではないがフィッシング メッセージに含まれる URL が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-416">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="731cc-417">ラップされていないリンクの URL クリックは、ここには表示されません。</span><span class="sxs-lookup"><span data-stu-id="731cc-417">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="731cc-418">2 つの URL の表には、配信アクションと場所別のフィッシング メール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-418">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="731cc-419">表には、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されます。そのため、ユーザーに対して表示された可能性のある不良リンクと、ユーザーがクリックした可能性のあるリンクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-419">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="731cc-420">ここから、詳細な分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-420">From here, you can conduct further analysis.</span></span> <span data-ttu-id="731cc-421">たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-421">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-422">![ブロックされたエクスプローラー URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-422">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="731cc-423">URL を選択して詳細な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="731cc-423">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="731cc-424">[URL] フライアウト ダイアログ ボックスでは、環境内の URL の露出の完全なビューを表示するために、電子メール メッセージのフィルター処理が削除されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-424">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="731cc-425">これにより、エクスプローラーで懸念している電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を見つけ、エクスプローラー ビュー自体に URL フィルターを追加することなく、([URL の詳細] ダイアログ ボックスを使用して) 環境内の URL の露出に関する理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="731cc-425">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="731cc-426">クリックの Verdicts の解釈</span><span class="sxs-lookup"><span data-stu-id="731cc-426">Interpretation of click verdicts</span></span>

<span data-ttu-id="731cc-427">メールまたは URL のフライアウト、トップ クリック、およびフィルター処理エクスペリエンス内には、異なるクリックの確認値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-427">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="731cc-428">**なし:** URL の条件を取得できません。</span><span class="sxs-lookup"><span data-stu-id="731cc-428">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="731cc-429">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-429">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="731cc-430">**許可:** ユーザーは URL への移動を許可されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-430">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="731cc-431">**ブロック:** ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="731cc-431">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="731cc-432">**保留中の否決:** ユーザーに、デトレーション保留中のページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-432">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="731cc-433">**ブロックされた上書き:** ユーザーが URL に直接移動できません。</span><span class="sxs-lookup"><span data-stu-id="731cc-433">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="731cc-434">ただし、ユーザーはブロックをオーバーロードして URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="731cc-434">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="731cc-435">**保留中の否決はバイパスされます。** ユーザーにデトレーション ページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-435">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="731cc-436">ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="731cc-436">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="731cc-437">**エラー:** ユーザーにエラー ページが表示された場合、または、エラーが発生して、そのエラーが検出されました。</span><span class="sxs-lookup"><span data-stu-id="731cc-437">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="731cc-438">**エラー:** Verdict のキャプチャ中に不明な例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="731cc-438">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="731cc-439">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-439">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="731cc-440">ユーザーによって報告された電子メール メッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="731cc-440">Review email messages reported by users</span></span>

<span data-ttu-id="731cc-441">組織内のユーザーが迷惑メール、迷惑メールではない、またはフィッシングとして報告した電子メール メッセージを、レポート メッセージ[](enable-the-report-message-add-in.md)アドインまたは Report [Phishing](enable-the-report-phish-add-in.md)アドインを介して表示するとします。 </span><span class="sxs-lookup"><span data-stu-id="731cc-441">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="731cc-442">それらを表示するには、エクスプローラーの [[**メール**  >  **の送信]**](threat-explorer-views.md#email--submissions)ビュー (またはリアルタイムの検出) を使います。</span><span class="sxs-lookup"><span data-stu-id="731cc-442">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="731cc-443">セキュリティ センター コンプライアンス & () で、脅威 <https://protection.office.com> **管理** \> **エクスプローラー** (または **リアルタイムの検出) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-443">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="731cc-444">(この例では、Explorer を使用します)。</span><span class="sxs-lookup"><span data-stu-id="731cc-444">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="731cc-445">[表示] **メニューで** 、[メールの送信 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-445">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-446">![メールのエクスプローラーの [表示] メニュー](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-446">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="731cc-447">[送信者 **] を** クリックし、[基本レポート **の** \> **種類] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="731cc-447">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="731cc-448">フィッシングなどのオプションを選択 **し、[** 更新] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="731cc-448">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="731cc-449">![ユーザーから報告されたフィッシング](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="731cc-449">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="731cc-450">レポートが更新され、組織内のユーザーがフィッシング詐欺の試みとして報告した電子メール メッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-450">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="731cc-451">この情報を使用して詳細な分析を行い、必要に応じて、Microsoft Defender でフィッシング対策ポリシーを Office [365](configure-atp-anti-phishing-policies.md)に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-451">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="731cc-452">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="731cc-452">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="731cc-453">自動調査および対応機能は *、Microsoft Defender で Office 365 プラン 2* および Office *365 E5 で利用できます*。</span><span class="sxs-lookup"><span data-stu-id="731cc-453">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="731cc-454">[自動調査と対応により](automated-investigation-response-office.md) 、セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-454">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="731cc-455">セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査および対応プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-455">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="731cc-456">詳細については、「例: セキュリティ管理者がエクスプローラーから [調査をトリガーする」を参照してください](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="731cc-456">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="731cc-457">エクスプローラーとリアルタイムの検出を使用するその他の方法</span><span class="sxs-lookup"><span data-stu-id="731cc-457">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="731cc-458">この記事で説明するシナリオに加えて、エクスプローラー (またはリアルタイムの検出) で使用できるレポート オプションも多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="731cc-458">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="731cc-459">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="731cc-459">See the following articles:</span></span>

- [<span data-ttu-id="731cc-460">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="731cc-460">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="731cc-461">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="731cc-461">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="731cc-462">脅威エクスプローラーのビューの概要 (およびリアルタイムの検出) を取得する</span><span class="sxs-lookup"><span data-stu-id="731cc-462">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="731cc-463">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="731cc-463">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="731cc-464">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="731cc-464">Automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="731cc-465">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="731cc-465">Required licenses and permissions</span></span>

<span data-ttu-id="731cc-466">エクスプローラーまたは [リアルタイムの検出を使用するには、Office 365](office-365-atp.md) 用の Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="731cc-466">You must have [Microsoft Defender for Office 365](office-365-atp.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="731cc-467">エクスプローラーは Defender for Office 365 プラン 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="731cc-467">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="731cc-468">リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="731cc-468">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="731cc-469">365 用に Defender で保護する必要があるすべてのユーザーにライセンスを割り当Officeします。</span><span class="sxs-lookup"><span data-stu-id="731cc-469">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="731cc-470">エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="731cc-470">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="731cc-471">エクスプローラーまたはリアルタイムの検出を表示して使用するには、セキュリティ管理者やセキュリティ閲覧者に付与されているアクセス許可など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="731cc-471">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="731cc-472">セキュリティ/コンプライアンス センター&、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="731cc-472">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="731cc-473">組織管理</span><span class="sxs-lookup"><span data-stu-id="731cc-473">Organization Management</span></span>
  - <span data-ttu-id="731cc-474">セキュリティ管理者 (これは Azure Active Directory 管理センター ( ) で割り当てることができます <https://aad.portal.azure.com> 。</span><span class="sxs-lookup"><span data-stu-id="731cc-474">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="731cc-475">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="731cc-475">Security Reader</span></span>

- <span data-ttu-id="731cc-476">Exchange Online では、Exchange 管理センター ( ) または Exchange Online PowerShell で次のいずれかの役割が割り当 <https://admin.protection.outlook.com/ecp/> [てられている必要があります](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="731cc-476">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="731cc-477">組織の管理</span><span class="sxs-lookup"><span data-stu-id="731cc-477">Organization Management</span></span>
  - <span data-ttu-id="731cc-478">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="731cc-478">View-Only Organization Management</span></span>
  - <span data-ttu-id="731cc-479">"View-Only Recipients/表示専用受信者"</span><span class="sxs-lookup"><span data-stu-id="731cc-479">View-Only Recipients</span></span>
  - <span data-ttu-id="731cc-480">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="731cc-480">Compliance Management</span></span>

<span data-ttu-id="731cc-481">役割とアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="731cc-481">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="731cc-482">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="731cc-482">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="731cc-483">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="731cc-483">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="731cc-484">脅威エクスプローラーとリアルタイム検出の違い</span><span class="sxs-lookup"><span data-stu-id="731cc-484">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="731cc-485">リアルタイム *検出レポートは、Defender で* Office 365 プラン 1 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-485">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="731cc-486">*脅威エクスプローラー* は、Defender for Office 365 プラン 2 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-486">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="731cc-487">リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。</span><span class="sxs-lookup"><span data-stu-id="731cc-487">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="731cc-488">脅威エクスプローラーも同様に実行しますが、特定の攻撃に関する追加の詳細も提供します。</span><span class="sxs-lookup"><span data-stu-id="731cc-488">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="731cc-489">[ *すべてのメール]* ビューは脅威エクスプローラーで使用できますが、リアルタイム検出レポートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="731cc-489">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="731cc-490">脅威エクスプローラーには、その他のフィルタリング機能と使用可能なアクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="731cc-490">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="731cc-491">詳細については [、「Microsoft Defender for Office 365 サービスの説明: Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)プランに対する Defender 全体での機能の可用性」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="731cc-491">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
