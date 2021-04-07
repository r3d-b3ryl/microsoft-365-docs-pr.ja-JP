---
title: 脅威エクスプローラーとリアルタイム検出
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
description: セキュリティ コンプライアンス センターでエクスプローラーとリアルタイムの検出を使用して、脅威を効率的に調査 &amp; して対応します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c601169d76fe92ac3038ccb25c5c50aa390f714
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599889"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="087b6-103">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="087b6-103">Threat Explorer and Real-time detections</span></span>


<span data-ttu-id="087b6-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="087b6-104">**Applies to**</span></span>
- [<span data-ttu-id="087b6-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="087b6-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="087b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="087b6-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="087b6-107">組織に microsoft [Defender for Office 365](defender-for-office-365.md)がある場合、必要 [](#required-licenses-and-permissions)なアクセス許可がある場合は、エクスプローラーまたはリアルタイム検出 **(以前** のリアルタイム レポート *-* 新機能 [](#new-features-in-threat-explorer-and-real-time-detections)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="087b6-107">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **Real-time detections** (formerly *Real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="087b6-108">セキュリティ コンプライアンス センター&に移動し、[脅威の管理] に移動し、[**エクスプローラー**  ] または [リアルタイム検出 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-108">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>


|<span data-ttu-id="087b6-109">Microsoft Defender for Office 365 プラン 2 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-109">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="087b6-110">Microsoft Defender for Office 365 プラン 1 では、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-110">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="087b6-113">エクスプローラーまたはリアルタイム検出は、セキュリティ運用チームが脅威を効率的に調査して対応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="087b6-113">Explorer or Real-time detections helps your security operations team investigate and respond to threats efficiently.</span></span> <span data-ttu-id="087b6-114">レポートは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="087b6-114">The report resembles the following image:</span></span>

![[脅威管理エクスプローラー] に \> 移動します。](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="087b6-116">このレポートでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-116">With this report, you can:</span></span>

- [<span data-ttu-id="087b6-117">Microsoft 365 のセキュリティ機能によって検出されたマルウェアを確認する</span><span class="sxs-lookup"><span data-stu-id="087b6-117">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="087b6-118">[フィッシング URL を表示し、[評決データ] をクリックする](#view-phishing-url-and-click-verdict-data)</span><span class="sxs-lookup"><span data-stu-id="087b6-118">[View phishing URL and click verdict data](#view-phishing-url-and-click-verdict-data)</span></span>
- <span data-ttu-id="087b6-119">[エクスプローラーでビューから自動調査と](#start-automated-investigation-and-response) 応答プロセスを開始する (Defender for Office 365 プラン 2 のみ)</span><span class="sxs-lookup"><span data-stu-id="087b6-119">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (Defender for Office 365 Plan 2 only)</span></span>
- [<span data-ttu-id="087b6-120">悪意のあるメールの調査など</span><span class="sxs-lookup"><span data-stu-id="087b6-120">Investigate malicious email, and more</span></span>](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="087b6-121">脅威ハンティング エクスペリエンスの改善</span><span class="sxs-lookup"><span data-stu-id="087b6-121">Improvements to Threat Hunting Experience</span></span>

### <a name="introduction-of-alert-id-for-mdo-alerts-within-explorerreal-time-detections-preview"></a><span data-ttu-id="087b6-122">エクスプローラー/リアルタイム検出内の MDO アラートのアラート ID の概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="087b6-122">Introduction of Alert ID for MDO alerts within Explorer/Real-time detections (Preview)</span></span>
<span data-ttu-id="087b6-123">今日、アラートから脅威エクスプローラーに移動すると、エクスプローラー内でフィルター処理されたビューが開き、そのビューはアラート ポリシー ID (ポリシー ID はアラート ポリシーの一意の識別子) でフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-123">Today, if you navigate from an alert to Threat Explorer, it opens a filtered view within the Explorer, with the view filtered by Alert policy ID (policy ID being a unique identifier for an Alert policy).</span></span>
<span data-ttu-id="087b6-124">脅威エクスプローラーとリアルタイム検出でアラート ID (以下のアラート ID の例を参照) を導入して、特定のアラートに関連するメッセージと電子メールの数を確認することで、この統合の関連性を高めます。</span><span class="sxs-lookup"><span data-stu-id="087b6-124">We are making this integration more relevant by introducing the alert ID (see an example of alert ID below) in Threat Explorer and Real-time detections so that you see messages which are relevant to the specific alert, as well as a count of emails.</span></span> <span data-ttu-id="087b6-125">また、メッセージがアラートの一部だったか、そのメッセージから特定のアラートに移動したのかも確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-125">You will also be able to see if a message was part of an alert, as well as navigate from that message to the specific alert.</span></span>  

<span data-ttu-id="087b6-126">アラート ID は、個々のアラートを表示するときに URL 内で使用できます。の例を示します `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1` 。</span><span class="sxs-lookup"><span data-stu-id="087b6-126">Alert ID is available within the URL when you are viewing an individual alert; an example being `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-127">![アラート ID のフィルター処理](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-127">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-128">![詳細フライアウトのアラート ID](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-128">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

 
### <a name="extending-the-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants-from-7-to-30-days-preview"></a><span data-ttu-id="087b6-129">試用版テナントのエクスプローラー (およびリアルタイム検出) のデータ保持と検索の制限を 7 日から 30 日間に延長する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="087b6-129">Extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days (Preview)</span></span>  
<span data-ttu-id="087b6-130">この変更の一環として、Office P1 および P2 試用版テナントの両方の Defender の脅威エクスプローラー/リアルタイム検出で、30 日間 (前の 7 日間から増加) のメール データを検索およびフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-130">As part of this change, you will be able to search for, and filter email data across 30 days (an increase from the previous 7 days) in Threat Explorer/Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="087b6-131">これは、既に 30 日間のデータ保持および検索機能を備えた P1 および P2/E5 の両方の顧客の実稼働テナントには影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="087b6-131">This does not impact any production tenants for both P1 and P2/E5 customers, which already has the 30 day data retention and search capabilities.</span></span> 

### <a name="updated-limits-for-export-of-records-for-threat-explorer-preview"></a><span data-ttu-id="087b6-132">脅威エクスプローラーのレコードのエクスポートの制限を更新しました (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="087b6-132">Updated limits for Export of records for Threat Explorer (Preview)</span></span> 
<span data-ttu-id="087b6-133">この更新プログラムの一環として、Threat Explorer からエクスポートできる電子メール レコードの行数が 9990 から 200,000 レコードに増加しました。</span><span class="sxs-lookup"><span data-stu-id="087b6-133">As part of this update, the number of rows for Email records that can be exported from Threat Explorer is increased from 9990 to 200,000 records.</span></span> <span data-ttu-id="087b6-134">現在エクスポートできる列のセットは同じままですが、行数は現在の制限値から増加します。</span><span class="sxs-lookup"><span data-stu-id="087b6-134">The set of columns that can be exported currently will remain the same, but the number of rows will increase from the current limit.</span></span>

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="087b6-135">脅威エクスプローラーのタグ</span><span class="sxs-lookup"><span data-stu-id="087b6-135">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="087b6-136">ユーザー タグ機能は [ *プレビュー] で*、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-136">The user tags feature is in *Preview*, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="087b6-137">リリース スケジュールの詳細については、Microsoft 365 ロードマップを参照してください。</span><span class="sxs-lookup"><span data-stu-id="087b6-137">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="087b6-138">ユーザー タグは、Microsoft Defender のユーザーの特定のグループを 365 Officeします。</span><span class="sxs-lookup"><span data-stu-id="087b6-138">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="087b6-139">ライセンスや構成などのタグの詳細については、「User tags」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="087b6-139">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="087b6-140">Threat Explorer では、次のエクスペリエンスでユーザー タグに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-140">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="087b6-141">メール グリッド ビュー</span><span class="sxs-lookup"><span data-stu-id="087b6-141">Email grid view</span></span>

<span data-ttu-id="087b6-142">メール **グリッドの** [タグ] 列には、送信者または受信者のメールボックスに適用されたタグすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="087b6-142">The **Tags** column in the email grid contains all the tags that have been applied to the sender or recipient mailboxes.</span></span> <span data-ttu-id="087b6-143">既定では、優先アカウントのようなシステム タグが最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-143">By default, system tags like priority accounts are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-144">![メール グリッド ビューでタグをフィルター処理する](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-144">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="087b6-145">フィルター処理</span><span class="sxs-lookup"><span data-stu-id="087b6-145">Filtering</span></span>

<span data-ttu-id="087b6-146">タグはフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-146">You can use tags as a filter.</span></span> <span data-ttu-id="087b6-147">優先度の高いアカウントまたは特定のユーザー タグのシナリオ間でハントします。</span><span class="sxs-lookup"><span data-stu-id="087b6-147">Hunt just across priority accounts or specific user tags scenarios.</span></span> <span data-ttu-id="087b6-148">特定のタグを持つ結果を除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-148">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="087b6-149">この機能を他のフィルターと組み合わせて、調査範囲を絞り込む。</span><span class="sxs-lookup"><span data-stu-id="087b6-149">Combine this functionality with other filters to narrow your scope of investigation.</span></span>

<span data-ttu-id="087b6-150">[![フィルター タグ](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="087b6-150">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-151">![タグをフィルター処理しない](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-151">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="087b6-152">電子メールの詳細の飛び出し</span><span class="sxs-lookup"><span data-stu-id="087b6-152">Email detail flyout</span></span>
<span data-ttu-id="087b6-153">送信者と受信者の個々のタグを表示するには、件名を選択してメッセージの詳細のフライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="087b6-153">To view the individual tags for sender and recipient, select the subject to open the message details flyout.</span></span> <span data-ttu-id="087b6-154">[概要 **] タブ** で、送信者と受信者のタグが電子メールに存在する場合は、個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-154">On the **Summary** tab, the sender and recipient tags are shown separately, if they're present for an email.</span></span>
<span data-ttu-id="087b6-155">送信者と受信者の個々のタグに関する情報は、エクスポートされた CSV データにも拡張され、これらの詳細は 2 つの個別の列で確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-155">The information about individual tags for sender and recipient also extends to exported CSV data, where you can see these details in two separate columns.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-156">![メールの詳細タグ](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-156">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="087b6-157">タグ情報は、URL クリック のフライアウトにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-157">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="087b6-158">表示するには、[フィッシング] または [すべてのメール] ビューに移動し **、[URL]** または [URL クリック] **タブに移動** します。個々の URL フライアウトを選択して、その URL のクリックに関する詳細 (そのクリックに関連付けられたタグを含む) を表示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-158">To view it, go to Phish or All Email view and then to the **URLs** or **URL Clicks** tab. Select an individual URL flyout to view additional details about clicks for that URL, including tags associated with that click.</span></span>


### <a name="updated-timeline-view"></a><span data-ttu-id="087b6-159">更新されたタイムライン ビュー</span><span class="sxs-lookup"><span data-stu-id="087b6-159">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-160">![URL タグ](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-160">![URL tags](../../media/tags-urls.png)</span></span>
> 
<span data-ttu-id="087b6-161">[このビデオ](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4)を見て詳細をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="087b6-161">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span> 

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a><span data-ttu-id="087b6-162">脅威の検出エクスペリエンスの改善 (今後)</span><span class="sxs-lookup"><span data-stu-id="087b6-162">Improvements to the threat hunting experience (upcoming)</span></span>

### <a name="updated-threat-information-for-emails"></a><span data-ttu-id="087b6-163">電子メールの更新された脅威情報</span><span class="sxs-lookup"><span data-stu-id="087b6-163">Updated threat information for emails</span></span>

<span data-ttu-id="087b6-164">電子メール レコードのデータの精度と一貫性を高めるプラットフォームとデータ品質の向上に重点を置いて取り組み、</span><span class="sxs-lookup"><span data-stu-id="087b6-164">We've focused on platform and data-quality improvements to increase data accuracy and consistency for email records.</span></span> <span data-ttu-id="087b6-165">ZAP プロセスの一部として電子メールで実行されるアクションなど、配信前および配信後の情報を 1 つのレコードに統合する機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="087b6-165">Improvements include consolidation of pre-delivery and post-delivery information, such as actions executed on an email as part of the ZAP process, into a single record.</span></span> <span data-ttu-id="087b6-166">スパムの評決、エンティティ レベルの脅威 (悪意のある URL など)、最新の配信場所などの詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="087b6-166">Additional details like spam verdict, entity-level threats (for example, which URL was malicious), and latest delivery locations are also included.</span></span>

<span data-ttu-id="087b6-167">これらの更新後、メッセージに影響を与える配信後のイベントに関係なく、メッセージごとに 1 つのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-167">After these updates, you'll see a single entry for each message, regardless of the different post-delivery events that affect the message.</span></span> <span data-ttu-id="087b6-168">アクションには、ZAP、手動修復 (管理者アクションを意味する)、動的配信などがあります。</span><span class="sxs-lookup"><span data-stu-id="087b6-168">Actions can include ZAP, manual remediation (which means admin action), dynamic delivery, and so on.</span></span>

<span data-ttu-id="087b6-169">マルウェアやフィッシングの脅威を表示する以外にも、メールに関連付けられたスパムの評決が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-169">In addition to showing malware and phishing threats, you see the spam verdict associated with an email.</span></span> <span data-ttu-id="087b6-170">電子メール内で、対応する検出テクノロジと共に、電子メールに関連付けられているすべての脅威を確認します。</span><span class="sxs-lookup"><span data-stu-id="087b6-170">Within the email, see all the threats associated with the email along with the corresponding detection technologies.</span></span> <span data-ttu-id="087b6-171">電子メールには、0、1、または複数の脅威を含む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-171">An email can have zero, one, or multiple threats.</span></span> <span data-ttu-id="087b6-172">メール の飛び出しの [ **詳細** ] セクションに現在の脅威が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-172">You'll see the current threats in the **Details** section of the email flyout.</span></span> <span data-ttu-id="087b6-173">複数の脅威 (マルウェアやフィッシングなど) の場合、[検出] 技術フィールドには、脅威を特定した検出テクノロジである脅威検出マッピングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-173">For multiple threats (such as malware and phishing), the **Detection tech** field shows the threat-detection mapping, which is the detection technology that identified the threat.</span></span>

<span data-ttu-id="087b6-174">一連の検出テクノロジには、新しい検出方法とスパム検出テクノロジが含まれています。</span><span class="sxs-lookup"><span data-stu-id="087b6-174">The set of detection technologies now includes new detection methods, as well as spam-detection technologies.</span></span> <span data-ttu-id="087b6-175">同じ一連の検出テクノロジを使用して、さまざまな電子メール ビュー (マルウェア、フィッシング、すべてのメール) で結果をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-175">You can use the same set of detection technologies to filter the results across the different email views (Malware, Phish, All Email).</span></span>

> [!NOTE]
> <span data-ttu-id="087b6-176">評決分析は必ずしもエンティティに関連付けられているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="087b6-176">Verdict analysis might not necessarily be tied to entities.</span></span> <span data-ttu-id="087b6-177">たとえば、電子メールはフィッシングまたはスパムとして分類されますが、フィッシング/スパムの評決でスタンプされた URL はありません。</span><span class="sxs-lookup"><span data-stu-id="087b6-177">As an example, an email might be classified as phish or spam, but there are no URLs that are stamped with a phish/spam verdict.</span></span> <span data-ttu-id="087b6-178">これは、フィルターが、評決を割り当てる前に、メールのコンテンツなどの詳細も評価する理由です。</span><span class="sxs-lookup"><span data-stu-id="087b6-178">This is because the filters also evaluate content and other details for an email before assigning a verdict.</span></span>

#### <a name="threats-in-urls"></a><span data-ttu-id="087b6-179">URL 内の脅威</span><span class="sxs-lookup"><span data-stu-id="087b6-179">Threats in URLs</span></span>

<span data-ttu-id="087b6-180">[メール の飛び出しの詳細] タブで、URL の特定の脅威を **確認** できます。脅威には、マルウェア *、フィッシング*、*スパム、* または *なしがあります*。 </span><span class="sxs-lookup"><span data-stu-id="087b6-180">You can now see the specific threat for a URL on the email flyout **Details** tab. The threat can be *malware*, *phish*, *spam*, or *none*.)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-181">![URL の脅威](../../media/URL_Threats.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-181">![URL threats](../../media/URL_Threats.png)</span></span>

### <a name="updated-timeline-view-upcoming"></a><span data-ttu-id="087b6-182">更新されたタイムライン ビュー (今後)</span><span class="sxs-lookup"><span data-stu-id="087b6-182">Updated timeline view (upcoming)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-183">![更新されたタイムライン ビュー](../../media/Email_Timeline.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-183">![Updated Timeline View](../../media/Email_Timeline.png)</span></span>

<span data-ttu-id="087b6-184">タイムライン ビューは、すべての配信イベントと配信後イベントを識別します。</span><span class="sxs-lookup"><span data-stu-id="087b6-184">Timeline view identifies all delivery and post-delivery events.</span></span> <span data-ttu-id="087b6-185">この情報には、これらのイベントのサブセットについて、その時点で特定された脅威に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="087b6-185">It includes information about the threat identified at that point of time for a subset of these events.</span></span> <span data-ttu-id="087b6-186">タイムライン ビューでは、追加のアクション (ZAP や手動修復など) に関する情報も、そのアクションの結果と共に提供されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-186">Timeline view also provides information about any additional action taken (such as ZAP or manual remediation), along with the result of that action.</span></span> <span data-ttu-id="087b6-187">タイムライン ビューの情報には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="087b6-187">Timeline view information includes:</span></span>

- <span data-ttu-id="087b6-188">**ソース:** イベントのソース。</span><span class="sxs-lookup"><span data-stu-id="087b6-188">**Source:** Source of the event.</span></span> <span data-ttu-id="087b6-189">管理者/システム/ユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-189">It can be admin/system/user.</span></span>
- <span data-ttu-id="087b6-190">**イベント:** 元の配信、手動修復、ZAP、申請、動的配信などのトップ レベルのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="087b6-190">**Event:** Includes top-level events like original delivery, manual remediation, ZAP, submissions, and dynamic delivery.</span></span>
- <span data-ttu-id="087b6-191">**アクション:** ZAP または管理アクションの一部として実行された特定のアクション (たとえば、ソフト削除)。</span><span class="sxs-lookup"><span data-stu-id="087b6-191">**Action:** The specific action that was taken either as part of ZAP or admin action (for example, soft delete).</span></span>
- <span data-ttu-id="087b6-192">**脅威:** その時点で特定された脅威 (マルウェア、フィッシング、スパム) をカバーします。</span><span class="sxs-lookup"><span data-stu-id="087b6-192">**Threats:** Covers the threats (malware, phish, spam) identified at that point of time.</span></span>
- <span data-ttu-id="087b6-193">**結果/詳細:** ZAP/admin アクションの一部として実行されたかどうかなど、アクションの結果に関する詳細。</span><span class="sxs-lookup"><span data-stu-id="087b6-193">**Result/Details:** More information about the result of the action, such as whether it was performed as part of ZAP/admin action.</span></span>

### <a name="original-and-latest-delivery-location"></a><span data-ttu-id="087b6-194">元の配信場所と最新の配信場所</span><span class="sxs-lookup"><span data-stu-id="087b6-194">Original and latest delivery location</span></span>

<span data-ttu-id="087b6-195">現在、メール グリッドと電子メール のフライアウトで配信場所を表示しています。</span><span class="sxs-lookup"><span data-stu-id="087b6-195">Currently, we surface delivery location in the email grid and email flyout.</span></span> <span data-ttu-id="087b6-196">[**配信場所]** フィールドの名前が [元の配信場所 \**_] _に_*変更されています。また、別のフィールド _最新の\* 配信場所 _を導入しています_\*\*。</span><span class="sxs-lookup"><span data-stu-id="087b6-196">The **Delivery location** field is getting renamed **_Original delivery location_*_. And we're introducing another field, _*_Latest delivery location_**.</span></span>

<span data-ttu-id="087b6-197">**元の配信場所** では、メールが最初に配信された場所に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-197">**Original delivery location** will give more information about where an email was delivered initially.</span></span> <span data-ttu-id="087b6-198">**最新の配信場所** には *、ZAP* や削除済みアイテムへの移動のような管理アクションなど、システムアクションの後にメールが届 *いた場所が表示されます*。</span><span class="sxs-lookup"><span data-stu-id="087b6-198">**Latest delivery location** will state where an email landed after system actions like *ZAP* or admin actions like *Move to deleted items*.</span></span> <span data-ttu-id="087b6-199">最新の配信場所は、メッセージの配信後の最後の既知の場所、またはシステム/管理者のアクションを管理者に伝える目的です。</span><span class="sxs-lookup"><span data-stu-id="087b6-199">Latest delivery location is intended to tell admins the message's last-known location post-delivery or any system/admin actions.</span></span> <span data-ttu-id="087b6-200">電子メールにはエンド ユーザーのアクションは含めかねない。</span><span class="sxs-lookup"><span data-stu-id="087b6-200">It doesn't include any end-user actions on the email.</span></span> <span data-ttu-id="087b6-201">たとえば、ユーザーがメッセージを削除した場合、またはメッセージをアーカイブ/pst に移動した場合、メッセージ "配信" の場所は更新されません。</span><span class="sxs-lookup"><span data-stu-id="087b6-201">For example, if a user deleted a message or moved the message to archive/pst, the message "delivery" location won't be updated.</span></span> <span data-ttu-id="087b6-202">ただし、システム アクションによって場所が更新された場合 (たとえば、ZAP が検疫に移動する電子メールなど)、最新の配信場所は "検疫" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-202">But if a system action updated the location (for example, ZAP resulting in an email moving to quarantine), **Latest delivery location** would show as "quarantine."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-203">![更新された配信場所](../../media/Updated_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-203">![Updated delivery locations](../../media/Updated_Delivery_Location.png)</span></span>

> [!NOTE]
> <span data-ttu-id="087b6-204">配信場所と配信アクションが"不明"と表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-204">There are a few cases where **Delivery location** and **Delivery action** may show as "unknown":</span></span>
>
> - <span data-ttu-id="087b6-205">メッセージ **が配信された** 場合、配信場所は"配信済み"、配信場所は "不明" と表示される場合がありますが、受信トレイ ルールはメッセージを受信トレイまたは迷惑メール フォルダーではなく既定のフォルダー (下書きやアーカイブなど) に移動します。</span><span class="sxs-lookup"><span data-stu-id="087b6-205">You might see **Delivery location** as "delivered" and **Delivery location** as "unknown" if the message was delivered, but an Inbox rule moved the message to a default folder (such as Draft or Archive) instead of to the Inbox or Junk Email folder.</span></span>
>
> - <span data-ttu-id="087b6-206">**管理者/システム** アクション (ZAP など) が試行されたが、メッセージが見つからなかった場合、最新の配信場所が不明になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-206">**Latest delivery location** can be unknown if an admin/system action (such as ZAP) was attempted, but the message wasn't found.</span></span> <span data-ttu-id="087b6-207">通常、アクションは、ユーザーがメッセージを移動または削除した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-207">Typically, the action happens after the user  moved or deleted the message.</span></span> <span data-ttu-id="087b6-208">このような場合は、タイムライン ビューの **[結果/詳細]** 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="087b6-208">In such cases, verify the **Result/Details** column in timeline view.</span></span> <span data-ttu-id="087b6-209">"ユーザーが移動または削除したメッセージ" というステートメントを探します。</span><span class="sxs-lookup"><span data-stu-id="087b6-209">Look for the statement "Message moved or deleted by the user."</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-210">![タイムラインの配信場所](../../media/Updated_Timeline_Delivery_Location.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-210">![Delivery locations for timeline](../../media/Updated_Timeline_Delivery_Location.png)</span></span>

### <a name="additional-actions"></a><span data-ttu-id="087b6-211">その他のアクション</span><span class="sxs-lookup"><span data-stu-id="087b6-211">Additional actions</span></span>

<span data-ttu-id="087b6-212">*電子メールの* 配信後に追加のアクションが適用された。</span><span class="sxs-lookup"><span data-stu-id="087b6-212">*Additional actions* were applied after delivery of the email.</span></span> <span data-ttu-id="087b6-213">*ZAP、* 手動修復 *(ソフト* 削除などの管理者が実行したアクション)、動的配信、および再処理 *(さかのぼ* って良好と検出された電子メールの場合) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="087b6-213">They can include *ZAP*, *manual remediation* (action taken by an Admin such as soft delete), *dynamic delivery*, and *reprocessed* (for an email that was retroactively detected as good).</span></span>

> [!NOTE]
> - <span data-ttu-id="087b6-214">保留中の変更の一環として、[配信アクション] フィルターに現在表示されている "削除済み" の値は削除されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-214">As part of the pending changes, the "Removed by ZAP" value currently surfaced in the Delivery Action filter is going away.</span></span> <span data-ttu-id="087b6-215">追加アクションを通じて ZAP の試行ですべてのメールを **検索する方法があります**。</span><span class="sxs-lookup"><span data-stu-id="087b6-215">You'll have a way to search for all email with the ZAP attempt through **Additional actions**.</span></span>
>
> - <span data-ttu-id="087b6-216">検出テクノロジと追加アクション (特に ZAP シナリオの場合) には、新しいフィールドと値が追加されます。 </span><span class="sxs-lookup"><span data-stu-id="087b6-216">There will be new fields and values for **Detection technologies** and **Additional actions** (especially for ZAP scenarios).</span></span> <span data-ttu-id="087b6-217">既存の保存済みクエリと追跡されたクエリを評価して、新しい値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-217">You'll need to evaluate your existing saved queries and tracked queries to make sure they work with the new values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-218">![エクスプローラーのその他のアクション](../../media/Additional_Actions.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-218">![Additional Actions in Explorer](../../media/Additional_Actions.png)</span></span>

### <a name="system-overrides"></a><span data-ttu-id="087b6-219">システムオーバーライド</span><span class="sxs-lookup"><span data-stu-id="087b6-219">System overrides</span></span>

<span data-ttu-id="087b6-220">*システムオーバーライドを使用* すると、メッセージの意図した配信場所に対して例外を作成できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-220">*System overrides* enable you to make exceptions to the intended delivery location of a message.</span></span> <span data-ttu-id="087b6-221">システムによって提供される配信場所は、フィルター スタックによって識別される脅威や他の検出に基づいて上書きします。</span><span class="sxs-lookup"><span data-stu-id="087b6-221">You override the delivery location provided by the system, based on the threats and other detections identified by the filtering stack.</span></span> <span data-ttu-id="087b6-222">システムの上書きは、テナントまたはユーザー ポリシーを使用して設定して、ポリシーによって提案されているメッセージを配信できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-222">System overrides can be set through tenant or user policy to deliver the message as suggested by the policy.</span></span> <span data-ttu-id="087b6-223">オーバーライドは、ユーザーが設定した過剰に広範な差出人セーフ 送信者ポリシーなど、構成のギャップによる悪意のあるメッセージの意図しない配信を識別できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-223">Overrides can identify unintentional delivery of malicious messages due to configurations gaps, such as an overly broad Safe Sender policy set by a user.</span></span> <span data-ttu-id="087b6-224">これらのオーバーライド値には、次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-224">These override values can be:</span></span>

- <span data-ttu-id="087b6-225">ユーザー ポリシーで許可: ユーザーがメールボックス レベルでポリシーを作成し、ドメインまたは送信者を許可します。</span><span class="sxs-lookup"><span data-stu-id="087b6-225">Allowed by user policy: A user creates policies at the mailbox level to allows domains or senders.</span></span>

- <span data-ttu-id="087b6-226">ユーザー ポリシーでブロック: ユーザーがメール ボックス レベルでポリシーを作成して、ドメインまたは送信者をブロックします。</span><span class="sxs-lookup"><span data-stu-id="087b6-226">Blocked by user policy: A user creates policies at the mail box level to block domains or senders.</span></span>

- <span data-ttu-id="087b6-227">組織ポリシーで許可: 組織のセキュリティ チームは、組織内のユーザーに送信者とドメインを許可するポリシーまたは Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を設定します。</span><span class="sxs-lookup"><span data-stu-id="087b6-227">Allowed by org policy: The organization's security teams set policies or Exchange mail flow rules (also known as transport rules) to allow senders and domains for users in their organization.</span></span> <span data-ttu-id="087b6-228">これは、一連のユーザーまたは組織全体に対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-228">This can be for a set of users or the entire organization.</span></span>

- <span data-ttu-id="087b6-229">組織ポリシーでブロック: 組織のセキュリティ チームは、組織内のユーザーの送信者、ドメイン、メッセージ言語、または送信元 IP をブロックするポリシーまたはメール フロー ルールを設定します。</span><span class="sxs-lookup"><span data-stu-id="087b6-229">Blocked by org policy: The organization's security teams set policies or mail flow rules to block senders, domains, message languages, or source IPs for users in their organization.</span></span> <span data-ttu-id="087b6-230">これは、一連のユーザーまたは組織全体に適用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-230">This can be applied to a set of users or the entire organization.</span></span>

- <span data-ttu-id="087b6-231">組織ポリシーによってブロックされるファイル拡張子: 組織のセキュリティ チームは、マルウェア対策ポリシー設定を通じてファイル名の拡張子をブロックします。</span><span class="sxs-lookup"><span data-stu-id="087b6-231">File extension blocked by org policy: An organization's security team blocks a file name extension through the anti-malware policy settings.</span></span> <span data-ttu-id="087b6-232">これらの値は、調査に役立つメールの詳細に表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-232">These values will now be displayed in email details to help with investigations.</span></span> <span data-ttu-id="087b6-233">Secops チームは、リッチ フィルター機能を使用して、ブロックされたファイル拡張子をフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-233">Secops teams can also use the rich-filtering capability to filter on blocked file extensions.</span></span>

<span data-ttu-id="087b6-234">[![エクスプローラーのシステムオーバーライド](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="087b6-234">[![System Overrides in Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-235">![エクスプローラーの System Overrides Grid](../../media/System_Overrides_Grid.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-235">![System Overrides Grid in Explorer](../../media/System_Overrides_Grid.png)</span></span>

### <a name="improvements-for-the-url-and-clicks-experience"></a><span data-ttu-id="087b6-236">URL とクリックエクスペリエンスの改善</span><span class="sxs-lookup"><span data-stu-id="087b6-236">Improvements for the URL and clicks experience</span></span>

<span data-ttu-id="087b6-237">改善点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="087b6-237">The improvements include:</span></span>

- <span data-ttu-id="087b6-238">URL フライアウトの [クリック] セクションに、クリックされた完全な URL  (URL の一部であるクエリ パラメーターを含む) を表示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-238">Show the full clicked URL (including any query parameters that are part of the URL) in the **Clicks** section of the URL flyout.</span></span> <span data-ttu-id="087b6-239">現在、URL ドメインとパスはタイトル バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-239">Currently, the URL domain and path appear in the title bar.</span></span> <span data-ttu-id="087b6-240">その情報を拡張して、完全な URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-240">We're extending that information to show the full URL.</span></span>

- <span data-ttu-id="087b6-241">URL フィルター *(URL* とURL ドメインと URL ドメイン、パスの間の *修正):* 更新プログラムは、URL/クリックの評決を含むメッセージの検索に影響します。</span><span class="sxs-lookup"><span data-stu-id="087b6-241">Fixes across URL filters (*URL* versus *URL domain* versus *URL domain and path*): The updates affect searching for messages that contain a URL/click verdict.</span></span> <span data-ttu-id="087b6-242">プロトコルに依存しない検索のサポートが有効になっているので、使用せずに URL を検索できます `http` 。</span><span class="sxs-lookup"><span data-stu-id="087b6-242">We enabled support for protocol-agnostic searches, so you can search for a URL without using `http`.</span></span> <span data-ttu-id="087b6-243">既定では、別の値が明示的に指定されていない限り、URL 検索は http にマップされます。</span><span class="sxs-lookup"><span data-stu-id="087b6-243">By default, the URL search maps to http, unless another value is explicitly specified.</span></span> <span data-ttu-id="087b6-244">例:</span><span class="sxs-lookup"><span data-stu-id="087b6-244">For example:</span></span>

   -  <span data-ttu-id="087b6-245">URL、URL ドメイン、URL ドメイン、および URL の [ドメイン] および [パス] フィルター フィールドで、プレフィックスの付きまたは指定 `http://` **なしで** 検索します。  </span><span class="sxs-lookup"><span data-stu-id="087b6-245">Search with and without the `http://` prefix in the **URL**, **URL Domain**, and **URL Domain and Path** filter fields.</span></span> <span data-ttu-id="087b6-246">検索は同じ結果を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-246">The searches should show the same results.</span></span>

   -  <span data-ttu-id="087b6-247">URL でプレフィックス `https://` を検索 **します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-247">Search for the `https://` prefix in **URL**.</span></span> <span data-ttu-id="087b6-248">値を指定しない場合、プレフィックス `http://` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-248">When no value is specified, the `http://` prefix is assumed.</span></span>

   - <span data-ttu-id="087b6-249">`/` URL パス **、URL** ドメイン **、URL** ドメイン、およびパス フィールドの先頭と末尾 **で無視** されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-249">`/` is ignored at the beginning and end of the **URL path**, **URL Domain**, **URL domain and path** fields.</span></span> <span data-ttu-id="087b6-250">`/` URL フィールドの末尾 **は無視** されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-250">`/` at the end of the **URL** field is ignored.</span></span>

### <a name="phish-confidence-level"></a><span data-ttu-id="087b6-251">フィッシングの信頼レベル</span><span class="sxs-lookup"><span data-stu-id="087b6-251">Phish confidence level</span></span>

<span data-ttu-id="087b6-252">フィッシングの信頼度は、電子メールが "フィッシング" として分類された信頼度を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="087b6-252">Phish confidence level helps identify the degree of confidence with which an email was categorized as "phish."</span></span> <span data-ttu-id="087b6-253">2 つの可能な値は *、High と Normal* *です*。</span><span class="sxs-lookup"><span data-stu-id="087b6-253">The two possible values are *High* and *Normal*.</span></span> <span data-ttu-id="087b6-254">最初の段階では、このフィルターは、脅威エクスプローラーの [フィッシング] ビューでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-254">In the initial stages, this filter will be available only in the Phish view of Threat Explorer.</span></span>

<span data-ttu-id="087b6-255">[![エクスプローラーのフィッシングの信頼レベル](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="087b6-255">[![Phish Confidence Level in Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)</span></span>

### <a name="zap-url-signal"></a><span data-ttu-id="087b6-256">ZAP URL シグナル</span><span class="sxs-lookup"><span data-stu-id="087b6-256">ZAP URL signal</span></span>

<span data-ttu-id="087b6-257">ZAP URL シグナルは、通常、メールがフィッシングとして識別され、配信後に削除された ZAP フィッシング アラート シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-257">The ZAP URL signal is typically used for ZAP Phish alert scenarios where an email was identified as Phish and removed after delivery.</span></span> <span data-ttu-id="087b6-258">このシグナルは、アラートとエクスプローラーの対応する結果を接続します。</span><span class="sxs-lookup"><span data-stu-id="087b6-258">This signal connects the alert with the corresponding results in Explorer.</span></span> <span data-ttu-id="087b6-259">アラートの IOC の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="087b6-259">It's one of the IOCs for the alert.</span></span>

<span data-ttu-id="087b6-260">狩猟プロセスを改善するために、脅威エクスプローラーとリアルタイム検出を更新して、狩猟のエクスペリエンスをより一貫性のあるものにしました。</span><span class="sxs-lookup"><span data-stu-id="087b6-260">To improve the hunting process, we've updated Threat Explorer and Real-time detections to make the hunting experience more consistent.</span></span> <span data-ttu-id="087b6-261">変更の概要は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="087b6-261">The changes are outlined here:</span></span>

- [<span data-ttu-id="087b6-262">タイムゾーンの改善</span><span class="sxs-lookup"><span data-stu-id="087b6-262">Timezone improvements</span></span>](#timezone-improvements)
- [<span data-ttu-id="087b6-263">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="087b6-263">Update in the refresh process</span></span>](#update-in-the-refresh-process)
- [<span data-ttu-id="087b6-264">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="087b6-264">Chart drilldown to add to filters</span></span>](#chart-drilldown-to-add-to-filters)
- [<span data-ttu-id="087b6-265">製品情報の更新で</span><span class="sxs-lookup"><span data-stu-id="087b6-265">In product information updates</span></span>](#in-product-information-updates)

### <a name="filter-by-user-tags"></a><span data-ttu-id="087b6-266">ユーザー タグによるフィルター</span><span class="sxs-lookup"><span data-stu-id="087b6-266">Filter by user tags</span></span>

<span data-ttu-id="087b6-267">システムまたはカスタム のユーザー タグを並べ替え、フィルター処理して、脅威の範囲をすばやく把握できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-267">You can now sort and filter on system or custom user tags to quickly grasp the scope of threats.</span></span> <span data-ttu-id="087b6-268">詳細については、「ユーザー タグ [」を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="087b6-268">To learn more, see [User tags](user-tags.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="087b6-269">ユーザー タグによるフィルター処理と並べ替えは、現在パブリック プレビューに表示されています。</span><span class="sxs-lookup"><span data-stu-id="087b6-269">Filtering and sorting by user tags is currently in public preview.</span></span> <span data-ttu-id="087b6-270">この機能は、商用リリース前に大幅に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-270">This functionality may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="087b6-271">Microsoft は、明示または黙示を問わず、その情報に関して一切の保証を行いません。</span><span class="sxs-lookup"><span data-stu-id="087b6-271">Microsoft makes no warranties, express or implied, with respect to the information provided about it.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-272">![エクスプローラーの [タグ] 列](../../media/threat-explorer-tags.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-272">![Tags column in Explorer](../../media/threat-explorer-tags.png)</span></span>

### <a name="timezone-improvements"></a><span data-ttu-id="087b6-273">タイムゾーンの改善</span><span class="sxs-lookup"><span data-stu-id="087b6-273">Timezone improvements</span></span>

<span data-ttu-id="087b6-274">ポータルの電子メール レコードのタイム ゾーンとエクスポートされたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-274">You'll see the time zone for the email records in the Portal as well as for Exported data.</span></span> <span data-ttu-id="087b6-275">メール グリッド、詳細フライアウト、メール タイムライン、類似メールなど、エクスペリエンス全体で表示されます。結果セットのタイム ゾーンは明確です。</span><span class="sxs-lookup"><span data-stu-id="087b6-275">It will be visible across experiences like Email Grid, Details flyout, Email Timeline, and Similar Emails, so the time zone for the result set is clear.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-276">![エクスプローラーでタイム ゾーンを表示する](../../media/TimezoneImprovements.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-276">![View time zone in Explorer](../../media/TimezoneImprovements.png)</span></span>

### <a name="update-in-the-refresh-process"></a><span data-ttu-id="087b6-277">更新プロセスでの更新</span><span class="sxs-lookup"><span data-stu-id="087b6-277">Update in the refresh process</span></span>

<span data-ttu-id="087b6-278">一部のユーザーは、自動更新 (たとえば、日付を変更するとすぐにページが更新されます) と手動更新 (他のフィルターの場合) との混同についてコメントしています。</span><span class="sxs-lookup"><span data-stu-id="087b6-278">Some users have commented about confusion with automatic refresh (for example, as soon as you change the date, the page refreshes) and manual refresh (for other filters).</span></span> <span data-ttu-id="087b6-279">同様に、フィルターを削除すると、自動更新が行います。</span><span class="sxs-lookup"><span data-stu-id="087b6-279">Similarly, removing filters leads to automatic refresh.</span></span> <span data-ttu-id="087b6-280">クエリの変更中にフィルターを変更すると、一貫性のない検索エクスペリエンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-280">Changing filters while modifying the query can cause inconsistent search experiences.</span></span> <span data-ttu-id="087b6-281">これらの問題を解決するために、手動フィルターメカニズムに移行します。</span><span class="sxs-lookup"><span data-stu-id="087b6-281">To resolve these issues, we're moving to a manual-filtering mechanism.</span></span>

<span data-ttu-id="087b6-282">ユーザーは、エクスペリエンスの観点から、(フィルター セットと日付から) さまざまな範囲のフィルターを適用および削除し、クエリを定義した後に結果をフィルター処理する更新ボタンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-282">From an experience standpoint, the user can apply and remove the different range of filters (from the filter set and date) and select the refresh button to filter the results after they've defined the query.</span></span> <span data-ttu-id="087b6-283">更新ボタンも画面で強調されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-283">The refresh button is also now emphasized on the screen.</span></span> <span data-ttu-id="087b6-284">関連するツールヒントと製品内ドキュメントも更新しました。</span><span class="sxs-lookup"><span data-stu-id="087b6-284">We've also updated the related tooltips and in-product documentation.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-285">![[更新] を選択して結果をフィルター処理する](../../media/ManualRefresh.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-285">![Select Refresh to filter results](../../media/ManualRefresh.png)</span></span>

### <a name="chart-drilldown-to-add-to-filters"></a><span data-ttu-id="087b6-286">フィルターに追加するグラフのドリルダウン</span><span class="sxs-lookup"><span data-stu-id="087b6-286">Chart drilldown to add to filters</span></span>

<span data-ttu-id="087b6-287">凡例の値をグラフに追加して、フィルターとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-287">You can now chart legend values to add them as filters.</span></span> <span data-ttu-id="087b6-288">[更新] **ボタンを** 選択して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="087b6-288">Select the **Refresh** button to filter the results.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-289">![グラフをドリルダウンしてフィルターに移動する](../../media/ChartDrilldown.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-289">![Drill down through charts to Filter](../../media/ChartDrilldown.png)</span></span>

### <a name="in-product-information-updates"></a><span data-ttu-id="087b6-290">製品内情報の更新</span><span class="sxs-lookup"><span data-stu-id="087b6-290">In-product information updates</span></span>

<span data-ttu-id="087b6-291">グリッド内の検索結果の総数など、製品内で追加の詳細が利用可能になります (以下を参照)。</span><span class="sxs-lookup"><span data-stu-id="087b6-291">Additional details are now available within the product, such as the total number of search results within the grid (see below).</span></span> <span data-ttu-id="087b6-292">フィルター、検索エクスペリエンス、および結果セットに関する詳細を提供するために、ラベル、エラー メッセージ、およびツールヒントが改善されました。</span><span class="sxs-lookup"><span data-stu-id="087b6-292">We've improved labels, error messages, and tooltips to provide more information about the filters, search experience, and result set.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-293">![製品内情報の表示](../../media/ProductInfo.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-293">![View in-product information](../../media/ProductInfo.png)</span></span>

## <a name="extended-capabilities-in-threat-explorer"></a><span data-ttu-id="087b6-294">Threat Explorer の拡張機能</span><span class="sxs-lookup"><span data-stu-id="087b6-294">Extended capabilities in Threat Explorer</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="087b6-295">上位の対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="087b6-295">Top targeted users</span></span>

<span data-ttu-id="087b6-296">今日、メールの [マルウェア] ビューの [トップ マルウェア ファミリ] セクションで、対象ユーザーの上位の一覧 **が公開** されています。</span><span class="sxs-lookup"><span data-stu-id="087b6-296">Today we expose the list of the top targeted users in the Malware view for emails, in the **Top Malware Families** section.</span></span> <span data-ttu-id="087b6-297">このビューは、[フィッシング] ビューと [すべてのメール] ビューでも拡張されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-297">We'll be extending this view in the Phish and All Email views as well.</span></span> <span data-ttu-id="087b6-298">上位 5 人の対象ユーザーと、対応するビューの各ユーザーの試行回数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-298">You'll be able to see the top-five targeted users, along with the number of attempts for each user for the corresponding view.</span></span> <span data-ttu-id="087b6-299">たとえば、[フィッシング] ビューには、フィッシングの試行回数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-299">For example, for Phish view, you'll see the number of Phish attempts.</span></span>

<span data-ttu-id="087b6-300">対象ユーザーのリストを最大 3,000 人までエクスポートし、各電子メール ビューのオフライン分析の試行回数をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-300">You'll be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts for offline analysis for each email view.</span></span> <span data-ttu-id="087b6-301">さらに、試行回数 (下の図では 13 回など) を選択すると、Threat Explorer でフィルター処理されたビューが開き、そのユーザーのメールや脅威の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-301">In addition, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails and threats for that user.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-302">![上位の対象ユーザー](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-302">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="087b6-303">Exchange トランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="087b6-303">Exchange transport rules</span></span>

<span data-ttu-id="087b6-304">データエンリッチメントの一環として、メッセージに適用されたさまざまな Exchange トランスポート ルール (ETR) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-304">As part of data enrichment, you'll be able to see all the different Exchange transport rules (ETR) that were applied to a message.</span></span> <span data-ttu-id="087b6-305">この情報は、[メール] グリッド ビューで使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-305">This information will be available in the Email grid view.</span></span> <span data-ttu-id="087b6-306">表示するには、グリッドで **[列のオプション** ] を選択し、列オプションから **[Exchange トランスポート ルール** の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="087b6-306">To view it,  select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="087b6-307">また、メールの [詳細] **フライ** アウトにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-307">It will also be visible on the **Details** flyout in the email.</span></span>

<span data-ttu-id="087b6-308">GUID と、メッセージに適用されたトランスポート ルールの名前の両方を確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-308">You'll be able to see both the GUID and the name of the transport rules that were applied to the message.</span></span> <span data-ttu-id="087b6-309">トランスポート ルールの名前を使用してメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-309">You'll be able to search for the messages by using the name of the transport rule.</span></span> <span data-ttu-id="087b6-310">これは"Contains" 検索で、部分的な検索も実行できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-310">This is a "Contains" search, which means you can do partial searches as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="087b6-311">ETR 検索と名前の可用性は、割り当てられている特定の役割によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="087b6-311">ETR search and name availability depend on the specific role that's assigned to you.</span></span> <span data-ttu-id="087b6-312">ETR 名と検索を表示するには、次のいずれかの役割/アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="087b6-312">You need to have one of the following roles/permissions to view the ETR names and search.</span></span> <span data-ttu-id="087b6-313">これらの役割が割り当てられていない場合は、トランスポート ルールの名前を表示したり、ETR 名を使用してメッセージを検索したりしません。</span><span class="sxs-lookup"><span data-stu-id="087b6-313">If you don't have any of these roles assigned to you, you can't see the names of the transport rules or search for messages by using ETR names.</span></span> <span data-ttu-id="087b6-314">ただし、[電子メールの詳細] に ETR ラベルと GUID 情報が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-314">However, you could see the ETR label and GUID information in the Email Details.</span></span> <span data-ttu-id="087b6-315">メール グリッド、電子メール フライアウト、フィルター、およびエクスポートの他のレコード表示エクスペリエンスは影響を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="087b6-315">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
> 
> - <span data-ttu-id="087b6-316">EXO のみ - データ損失防止: すべて</span><span class="sxs-lookup"><span data-stu-id="087b6-316">EXO Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="087b6-317">EXO のみ - O365SupportViewConfig: All</span><span class="sxs-lookup"><span data-stu-id="087b6-317">EXO Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="087b6-318">Microsoft Azure Active Directory または EXO - セキュリティ管理者: All</span><span class="sxs-lookup"><span data-stu-id="087b6-318">Microsoft Azure Active Directory or EXO - Security Admin: All</span></span>
> - <span data-ttu-id="087b6-319">AAD または EXO - セキュリティ リーダー: All</span><span class="sxs-lookup"><span data-stu-id="087b6-319">AAD or EXO - Security Reader: All</span></span>
> - <span data-ttu-id="087b6-320">EXO のみ - トランスポート ルール: All</span><span class="sxs-lookup"><span data-stu-id="087b6-320">EXO Only - Transport Rules: All</span></span>
> - <span data-ttu-id="087b6-321">EXO のみ - View-Only構成: すべて</span><span class="sxs-lookup"><span data-stu-id="087b6-321">EXO Only - View-Only Configuration: All</span></span>
> 
> <span data-ttu-id="087b6-322">電子メール グリッド、詳細フライアウト、およびエクスポート CSV 内で、ETRs には、次に示すように名前/GUID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-322">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
> 
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="087b6-323">![Exchange トランスポート ルール](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-323">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="087b6-324">受信コネクタ</span><span class="sxs-lookup"><span data-stu-id="087b6-324">Inbound connectors</span></span>

<span data-ttu-id="087b6-325">コネクタは、Microsoft 365 または 365 組織との間で電子メールが流れる方法をカスタマイズするOfficeです。</span><span class="sxs-lookup"><span data-stu-id="087b6-325">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="087b6-326">この機能を使用すると、セキュリティ制限またはコントロールを適用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-326">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="087b6-327">Threat Explorer 内で、電子メールに関連するコネクタを表示し、コネクタ名を使用して電子メールを検索できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-327">Within Threat Explorer, you can now view the connectors that are related to an email and search for emails by using connector names.</span></span>

<span data-ttu-id="087b6-328">コネクタの検索は、実際には "contains" で、部分的なキーワード検索も機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-328">The search for connectors is "contains" in nature, which means partial keyword searches should work as well.</span></span> <span data-ttu-id="087b6-329">メイン グリッド ビュー、詳細フライアウト、およびエクスポート CSV 内で、コネクタは次のように Name/GUID 形式で表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-329">Within the Main grid view, the Details flyout, and the Exported CSV, the connectors are shown in the Name/GUID format as shown here:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-330">![コネクタの詳細](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-330">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="087b6-331">脅威エクスプローラーとリアルタイム検出の新機能</span><span class="sxs-lookup"><span data-stu-id="087b6-331">New features in Threat Explorer and Real-time detections</span></span>

- [<span data-ttu-id="087b6-332">偽装ユーザーとドメインに送信されたフィッシングメールを表示する</span><span class="sxs-lookup"><span data-stu-id="087b6-332">View phishing emails sent to impersonated users and domains</span></span>](#view-phishing-emails-sent-to-impersonated-users-and-domains)
-  [<span data-ttu-id="087b6-333">メール ヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="087b6-333">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="087b6-334">メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="087b6-334">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="087b6-335">URL クリック データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="087b6-335">Export URL click data</span></span>](#export-url-click-data)

### <a name="view-phishing-emails-sent-to-impersonated-users-and-domains"></a><span data-ttu-id="087b6-336">偽装ユーザーとドメインに送信されたフィッシングメールを表示する</span><span class="sxs-lookup"><span data-stu-id="087b6-336">View phishing emails sent to impersonated users and domains</span></span>

<span data-ttu-id="087b6-337">偽装ユーザーであるユーザーとドメインに対するフィッシング詐欺の試行を識別するには、保護するユーザーの一覧に追加 *する必要があります*。</span><span class="sxs-lookup"><span data-stu-id="087b6-337">To identify phishing attempts against users and domains that are impersonated users must be added to the list of *Users to protect*.</span></span> <span data-ttu-id="087b6-338">ドメインの場合、管理者は組織 *ドメインを有効* にするか、ドメイン名をドメインに追加して保護 *する必要があります*。</span><span class="sxs-lookup"><span data-stu-id="087b6-338">For domains, admins must either enable *Organization domains*, or add a domain name to *Domains to protect*.</span></span> <span data-ttu-id="087b6-339">保護するドメインは、[偽装] セクションの [フィッシング対策ポリシー *]* ページ *に表示* されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-339">The domains to protect are found on the *Anti-Phishing policy page* in the *Impersonation* section.</span></span>

<span data-ttu-id="087b6-340">フィッシング メッセージを確認し、偽装されたユーザーまたはドメインを検索するには、エクスプローラーの [メール > [フィッシング] ビューを](threat-explorer-views.md) 使用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-340">To review phish messages and search for impersonated users or domains, use the [Email > Phish view](threat-explorer-views.md) of Explorer.</span></span>

<span data-ttu-id="087b6-341">この例では、Threat Explorer を使用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-341">This example uses Threat Explorer.</span></span>

1. <span data-ttu-id="087b6-342">[セキュリティ [コンプライアンス センター& (](https://protection.office.com) ) で、[脅威の管理] >エクスプローラー (またはリアルタイムの検出) https://protection.office.com) を選択します。</span><span class="sxs-lookup"><span data-stu-id="087b6-342">In the [Security & Compliance Center](https://protection.office.com) (https://protection.office.com), choose Threat management > Explorer (or Real-time detections).</span></span>

2. <span data-ttu-id="087b6-343">[表示] メニューの [メールとフィッシング>選択します。</span><span class="sxs-lookup"><span data-stu-id="087b6-343">In the View menu, choose Email > Phish.</span></span>

   <span data-ttu-id="087b6-344">ここでは、偽装ドメイン **または偽装\*\*\*\*ユーザーを選択できます**。</span><span class="sxs-lookup"><span data-stu-id="087b6-344">Here you can choose **impersonated domain** or **impersonated user**.</span></span>

3. <span data-ttu-id="087b6-345">**[偽装** された **ドメイン] を** 選択し、テキスト ボックスに保護されたドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="087b6-345">**EITHER** select **Impersonated domain**, and then type a protected domain in the textbox.</span></span>

   <span data-ttu-id="087b6-346">たとえば、contoso、contoso.com、contoso.com.au など、保護された *ドメイン名を検索します*。</span><span class="sxs-lookup"><span data-stu-id="087b6-346">For example, search for protected domain names like *contoso*, *contoso.com*, or *contoso.com.au*.</span></span>

4. <span data-ttu-id="087b6-347">[メール] タブの [メール] タブの [件名] >を選択すると、[偽装ドメイン] や [検出された場所] など、その他の偽装情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-347">Select the Subject of any message under the Email tab > Details tab to see additional impersonation information like Impersonated Domain / Detected location.</span></span>

    <span data-ttu-id="087b6-348">**OR**</span><span class="sxs-lookup"><span data-stu-id="087b6-348">**OR**</span></span> 

    <span data-ttu-id="087b6-349">[ **偽装ユーザー] を** 選択し、保護されたユーザーの電子メール アドレスをテキスト ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="087b6-349">Select **Impersonated user** and type a protected user's email address in the textbox.</span></span>

    > [!TIP]
    > <span data-ttu-id="087b6-350">**最適な結果を得** るためには、完全 *なメール アドレスを使用して* 保護されたユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="087b6-350">**For best results**, use *full email addresses* to search protected users.</span></span> <span data-ttu-id="087b6-351">たとえば、ユーザーの偽装を調査する場合など、保護されたユーザーを検索すると、より迅速 *かつ* firstname.lastname@contoso.com 見つけ出されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-351">You will find your protected user quicker and more successfully if you search for *firstname.lastname@contoso.com*, for example, when investigating user impersonation.</span></span> <span data-ttu-id="087b6-352">保護されたドメインを検索すると、ルート ドメイン (たとえば、contoso.com) とドメイン名 *(contoso)* が取得されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-352">When searching for a protected domain the search will take the root domain (contoso.com, for example), and the domain name (*contoso*).</span></span> <span data-ttu-id="087b6-353">ルート ドメイン を検索すると、contoso.com の偽装とドメイン *名 contoso の contoso.com* 両方が返 *されます*。</span><span class="sxs-lookup"><span data-stu-id="087b6-353">Searching for the root domain *contoso.com* will return both impersonations of *contoso.com* and the domain name *contoso*.</span></span>

5. <span data-ttu-id="087b6-354">[電子メール **] タブの**[**詳細]** タブの [任意のメッセージの件名] を選択して、ユーザーまたはドメインに関する追加の偽装情報と検出された場所  >  *を表示します*。</span><span class="sxs-lookup"><span data-stu-id="087b6-354">Select the **Subject** of any message under **Email tab** > **Details tab** to see additional impersonation information about the user or domain, and the *Detected location*.</span></span>

    :::image type="content" source="../../media/threat-ex-views-impersonated-user-image.png" alt-text="検出場所と検出された脅威 (ここでは、ユーザーのフィッシング偽装) を示す保護されたユーザーの脅威エクスプローラーの詳細ウィンドウ。":::

> [!NOTE]
> <span data-ttu-id="087b6-356">手順 3 または 5 で、[検出テクノロジ]を選択し、[偽装ドメイン] または [偽装ユーザー] をそれぞれ選択すると、[メール] タブの [詳細] タブのユーザーまたはドメインに関する情報が表示され、[検出された場所] は[フィッシング対策ポリシー] ページに表示されるユーザーまたはドメインに関連するメッセージにのみ表示されます。   >    </span><span class="sxs-lookup"><span data-stu-id="087b6-356">In step 3 or 5, if you choose **Detection Technology** and select **Impersonation domain** or **Impersonation user** respectively, the information in the **Email tab** > **Details tab** about the user or domain, and the *Detected location* will be shown only on the messages that are related to the user or domain listed on the *Anti-Phishing policy* page.</span></span> 

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="087b6-357">メール ヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="087b6-357">Preview email header and download email body</span></span>

<span data-ttu-id="087b6-358">これで、メール ヘッダーをプレビューし、脅威エクスプローラーで電子メール本文をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-358">You can now preview an email header and download the email body in Threat Explorer.</span></span> <span data-ttu-id="087b6-359">管理者は、ダウンロードしたヘッダー/電子メール メッセージの脅威を分析できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-359">Admins can analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="087b6-360">電子メール メッセージをダウンロードすると情報が危険にさらされる可能性があるため、このプロセスは役割ベースのアクセス制御 (RBAC) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-360">Because downloading email messages can risk exposure of information, this process is controlled by role-based access control (RBAC).</span></span> <span data-ttu-id="087b6-361">すべての電子メール *メッセージ* ビューでメールをダウンロードする機能を付与するには、新しい役割である Preview を別の役割グループ (セキュリティ操作やセキュリティ管理者など) に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-361">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails in all-email messages view.</span></span> <span data-ttu-id="087b6-362">ただし、電子メール ヘッダーを表示しても、追加の役割は必要ありません (脅威エクスプローラーでメッセージを表示するために必要な役割以外)。</span><span class="sxs-lookup"><span data-stu-id="087b6-362">However, viewing the email header does not require any additional role (other than what is required to view messages in Threat Explorer).</span></span>

<span data-ttu-id="087b6-363">エクスプローラーとリアルタイム検出では、電子メール メッセージの着陸場所の詳細な画像を提供する新しいフィールドも取得します。</span><span class="sxs-lookup"><span data-stu-id="087b6-363">Explorer and Real-time detections will also get new fields that provide a more complete picture of where your email messages land.</span></span> <span data-ttu-id="087b6-364">これらの変更により、Security Ops のハンティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="087b6-364">These changes  make hunting easier for Security Ops.</span></span> <span data-ttu-id="087b6-365">しかし、主な結果は、問題のある電子メール メッセージの場所を一目で知ることができます。</span><span class="sxs-lookup"><span data-stu-id="087b6-365">But the main result is you can know the location of problem email messages at a glance.</span></span>

<span data-ttu-id="087b6-366">これはどのように行われますか?</span><span class="sxs-lookup"><span data-stu-id="087b6-366">How is this done?</span></span> <span data-ttu-id="087b6-367">配信の状態は、次の 2 つの列に分かれました。</span><span class="sxs-lookup"><span data-stu-id="087b6-367">Delivery status is now broken out into two columns:</span></span>

- <span data-ttu-id="087b6-368">**配信アクション** - 電子メールの状態。</span><span class="sxs-lookup"><span data-stu-id="087b6-368">**Delivery action** - Status of the email.</span></span>
- <span data-ttu-id="087b6-369">**配信場所** - 電子メールがルーティングされた場所。</span><span class="sxs-lookup"><span data-stu-id="087b6-369">**Delivery location** - Where the email was routed.</span></span>

<span data-ttu-id="087b6-370">*配信アクション* は、既存のポリシーまたは検出のために電子メールで実行されるアクションです。</span><span class="sxs-lookup"><span data-stu-id="087b6-370">*Delivery action* is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="087b6-371">電子メールに対して実行できる操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-371">Here are the possible actions for an email:</span></span>

|<span data-ttu-id="087b6-372">配信</span><span class="sxs-lookup"><span data-stu-id="087b6-372">Delivered</span></span>|<span data-ttu-id="087b6-373">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="087b6-373">Junked</span></span>|<span data-ttu-id="087b6-374">Blocked</span><span class="sxs-lookup"><span data-stu-id="087b6-374">Blocked</span></span>|<span data-ttu-id="087b6-375">置換</span><span class="sxs-lookup"><span data-stu-id="087b6-375">Replaced</span></span>|
|---|---|---|---|
|<span data-ttu-id="087b6-376">メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーはメールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-376">Email was delivered to the inbox or folder of a user, and the user can access it.</span></span>|<span data-ttu-id="087b6-377">電子メールはユーザーの迷惑メールまたは削除済みフォルダーに送信され、ユーザーはアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-377">Email was sent to the user's Junk  or Deleted folder, and the user can access it.</span></span>|<span data-ttu-id="087b6-378">検疫されたメール、失敗したメール、または削除されたメール。</span><span class="sxs-lookup"><span data-stu-id="087b6-378">Emails that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="087b6-379">これらのメールには、ユーザーがアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="087b6-379">These mails are inaccessible to the user.</span></span>|<span data-ttu-id="087b6-380">メールには、悪意のある添付ファイルが .txt ファイルに置き換え、添付ファイルが悪意のある状態に置き換えられた。</span><span class="sxs-lookup"><span data-stu-id="087b6-380">Email had malicious attachments replaced by .txt files that state the attachment was malicious.</span></span>|

<span data-ttu-id="087b6-381">ユーザーが表示できる機能と表示できない機能を次に示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-381">Here is what the user can and can't see:</span></span>

|<span data-ttu-id="087b6-382">エンド ユーザーがアクセス可能</span><span class="sxs-lookup"><span data-stu-id="087b6-382">Accessible to end users</span></span>|<span data-ttu-id="087b6-383">エンド ユーザーにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="087b6-383">Inaccessible to end users</span></span>|
|---|---|
|<span data-ttu-id="087b6-384">配信</span><span class="sxs-lookup"><span data-stu-id="087b6-384">Delivered</span></span>|<span data-ttu-id="087b6-385">Blocked</span><span class="sxs-lookup"><span data-stu-id="087b6-385">Blocked</span></span>|
|<span data-ttu-id="087b6-386">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="087b6-386">Junked</span></span>|<span data-ttu-id="087b6-387">置換</span><span class="sxs-lookup"><span data-stu-id="087b6-387">Replaced</span></span>|

<span data-ttu-id="087b6-388">**配信場所** は、配信後に実行されるポリシーと検出の結果を示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-388">**Delivery location** shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="087b6-389">[配信] アクション **_にリンクされています_**。</span><span class="sxs-lookup"><span data-stu-id="087b6-389">It's linked to **_Delivery action_**.</span></span> <span data-ttu-id="087b6-390">次の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-390">These are the possible values:</span></span>

- <span data-ttu-id="087b6-391">*受信トレイまたはフォルダー*: 電子メールは受信トレイまたはフォルダー内にあります (メール ルールに従います)。</span><span class="sxs-lookup"><span data-stu-id="087b6-391">*Inbox or folder*: The email is in the inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="087b6-392">*オンプレミスまたは外部*: メールボックスはクラウド上に存在しませんが、オンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="087b6-392">*On-prem or external*: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="087b6-393">*迷惑メール* フォルダー: 電子メールはユーザーの迷惑メール フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="087b6-393">*Junk folder*: The email is in a user's Junk folder.</span></span>
- <span data-ttu-id="087b6-394">*削除済みアイテム フォルダー*: ユーザーの [削除済みアイテム] フォルダー内の電子メール。</span><span class="sxs-lookup"><span data-stu-id="087b6-394">*Deleted items folder*: The email in a user's Deleted items folder.</span></span>
- <span data-ttu-id="087b6-395">*検疫*: 電子メールは検疫中であり、ユーザーのメールボックスには含めではありません。</span><span class="sxs-lookup"><span data-stu-id="087b6-395">*Quarantine*: The email is in quarantine and not in a user's mailbox.</span></span>
- <span data-ttu-id="087b6-396">*Failed*: 電子メールがメールボックスに届きに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="087b6-396">*Failed*: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="087b6-397">*ドロップ*: メール フローのどこかでメールが失われました。</span><span class="sxs-lookup"><span data-stu-id="087b6-397">*Dropped*: The email got lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="087b6-398">メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="087b6-398">Email timeline</span></span>

<span data-ttu-id="087b6-399">メール **タイムラインは、** 管理者の検索エクスペリエンスを向上させる新しいエクスプローラー機能です。</span><span class="sxs-lookup"><span data-stu-id="087b6-399">The **Email timeline** is a new Explorer feature that improves the hunting experience for admins.</span></span> <span data-ttu-id="087b6-400">イベントの理解を試みるさまざまな場所のチェックに費やされる時間を削減します。</span><span class="sxs-lookup"><span data-stu-id="087b6-400">It cuts the time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="087b6-401">電子メールが到着すると同時に複数のイベントが発生または近い場合、それらのイベントはタイムライン ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-401">When multiple events happen at or close to the same time an email arrives, those events are displayed in a timeline view.</span></span> <span data-ttu-id="087b6-402">メールの配信後に発生する一部のイベントは、[特別なアクション] **列にキャプチャ** されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-402">Some events that happen to your email post-delivery are captured in the **Special action** column.</span></span> <span data-ttu-id="087b6-403">管理者は、タイムラインの情報と、配信後のメールに対して実行される特別なアクションを組み合わせて、ポリシーの動作、メールが最終的にルーティングされた場所、場合によっては最終的な評価の結果を把握できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-403">Admins can combine  information from the timeline with the special action taken on the mail post-delivery to get insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="087b6-404">詳細については [、「365](investigate-malicious-email-that-was-delivered.md)で配信された悪意のある電子メールの調査と修復Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="087b6-404">For more information, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="087b6-405">URL クリック データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="087b6-405">Export URL click data</span></span>

<span data-ttu-id="087b6-406">URL クリックのレポートを Microsoft Excel にエクスポートして、ネットワーク メッセージ **ID** を表示し、[評決] をクリックすると、URL クリック トラフィックの発生場所を説明できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-406">You can now export reports for URL clicks to Microsoft Excel to view their **network message ID** and **click verdict**, which helps explain where your URL click traffic originated.</span></span> <span data-ttu-id="087b6-407">動作方法は次のとおりです。 [脅威の管理] Office 365 クイック起動バーで、次のチェーンに従います。</span><span class="sxs-lookup"><span data-stu-id="087b6-407">Here's how it works: In Threat Management on the Office 365 quick-launch bar, follow this chain:</span></span>

<span data-ttu-id="087b6-408">**エクスプローラー** \>**フィッシングの表示** \>**クリック数** \>**トップ URL または** **URL トップ クリックは** \> 、任意のレコードを選択して URL フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="087b6-408">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs** or **URL Top Clicks** \> select any record to open the URL flyout.</span></span>

<span data-ttu-id="087b6-409">リストで URL を選択すると、フライアウト パネルに新しい **[** エクスポート] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-409">When you select a URL in the list, you'll see a new **Export** button on the fly-out panel.</span></span> <span data-ttu-id="087b6-410">レポートを簡単にするために、このボタンを使用して Excel スプレッドシートにデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="087b6-410">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="087b6-411">リアルタイム検出レポートで同じ場所に移動するには、次のパスに従います。</span><span class="sxs-lookup"><span data-stu-id="087b6-411">Follow this path to get to the same location in the Real-time detections report:</span></span>

<span data-ttu-id="087b6-412">**エクスプローラー** \>**リアルタイム検出** \>**フィッシングの表示** \>**URL** \>**[トップ URL]** **または [トップ クリック**] [任意のレコードを選択] をクリックして、[クリック] タブに移動して URL の飛び出 \> \> し **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="087b6-412">**Explorer** \> **Real-time detections** \> **View Phish** \> **URLs** \> **Top URLs** or **Top Clicks** \> Select any record to open the URL flyout \> navigate to the **Clicks** tab.</span></span>

> [!TIP]
> <span data-ttu-id="087b6-413">ネットワーク メッセージ ID は、エクスプローラーまたは関連するサード パーティ製ツールを使用して ID を検索すると、クリックを特定のメールにマップします。</span><span class="sxs-lookup"><span data-stu-id="087b6-413">The Network Message ID maps the click back to specific mails when you search on the ID through Explorer or associated third-party tools.</span></span> <span data-ttu-id="087b6-414">このような検索では、クリック結果に関連付けられた電子メールが識別されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-414">Such searches identify the email associated with a click result.</span></span> <span data-ttu-id="087b6-415">関連付けされたネットワーク メッセージ ID を使用すると、より迅速かつ強力な分析が可能になります。</span><span class="sxs-lookup"><span data-stu-id="087b6-415">Having the correlated Network Message ID makes for quicker and more powerful analysis.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="087b6-416">![エクスプローラーの [クリック] タブ](../../media/tp_ExportClickResultAndNetworkID.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-416">![Clicks tab in Explorer](../../media/tp_ExportClickResultAndNetworkID.png)</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="087b6-417">テクノロジによって電子メールで検出されたマルウェアを確認する</span><span class="sxs-lookup"><span data-stu-id="087b6-417">See malware detected in email by technology</span></span>

<span data-ttu-id="087b6-418">Microsoft 365 テクノロジで並べ替えた電子メールでマルウェアが検出されたとします。</span><span class="sxs-lookup"><span data-stu-id="087b6-418">Suppose you want to see malware detected in email sorted by Microsoft 365 technology.</span></span> <span data-ttu-id="087b6-419">これを行うには、エクスプローラーの [[電子>マルウェア](threat-explorer-views.md#email--malware) ] ビュー (またはリアルタイム検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-419">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="087b6-420">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-420">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="087b6-421">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="087b6-421">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="087b6-422">[表示] **メニューの** [メール マルウェア] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-422">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-423">![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-423">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="087b6-424">[送信者 **] を** クリックし、[基本検出 **テクノロジ]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-424">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="087b6-425">検出テクノロジは、レポートのフィルターとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-425">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-426">![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-426">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="087b6-427">オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="087b6-427">Choose an option.</span></span> <span data-ttu-id="087b6-428">次に、[更新] **ボタンを** 選択して、そのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-428">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-429">![選択された検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-429">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

<span data-ttu-id="087b6-430">レポートが更新され、選択したテクノロジ オプションを使用して、電子メールでマルウェアが検出された結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-430">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="087b6-431">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-431">From here, you can conduct further analysis.</span></span>

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="087b6-432">フィッシング URL を表示し、[評決データ] をクリックする</span><span class="sxs-lookup"><span data-stu-id="087b6-432">View phishing URL and click verdict data</span></span>

<span data-ttu-id="087b6-433">許可、ブロック、およびオーバーライドされた URL の一覧を含む、メール内の URL を介したフィッシング詐欺の試行を確認するとします。</span><span class="sxs-lookup"><span data-stu-id="087b6-433">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="087b6-434">クリックされた URL を識別するには、 [セーフ リンクを構成](safe-links.md) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-434">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="087b6-435">クリック時の保護とセーフ[](set-up-safe-links-policies.md)リンクによるクリックの評決のログ記録に対して、セーフ リンク ポリシーを設定してください。</span><span class="sxs-lookup"><span data-stu-id="087b6-435">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="087b6-436">メッセージ内のフィッシング URL を確認し、フィッシング メッセージ内の URL[  >  ](threat-explorer-views.md#email--phish)をクリックするには、エクスプローラーまたはリアルタイム検出の [メール フィッシング] ビューを使用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-436">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="087b6-437">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-437">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="087b6-438">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="087b6-438">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="087b6-439">[表示] **メニューの** [メール フィッシング] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-439">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-440">![フィッシング コンテキストでのエクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-440">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="087b6-441">[送信者 **] を** クリックし **、[URL]** \> **[評決のクリック] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-441">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="087b6-442">[ブロック] や [上書きブロック]などの 1 つ以上のオプションを選択し、そのフィルターを適用するオプションと同じ行の [更新] ボタンを選択します。 </span><span class="sxs-lookup"><span data-stu-id="087b6-442">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="087b6-443">(ブラウザー ウィンドウを更新しない)。</span><span class="sxs-lookup"><span data-stu-id="087b6-443">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-444">![URL とクリックの評決](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-444">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="087b6-445">レポートが更新され、レポートの下の [URL] タブに 2 つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-445">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="087b6-446">**上位 URL は** 、フィルター処理したメッセージ内の URL であり、メール配信アクションは URL ごとにカウントされます。</span><span class="sxs-lookup"><span data-stu-id="087b6-446">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="087b6-447">[フィッシング メール] ビューでは、通常、この一覧には正当な URL が含まれる。</span><span class="sxs-lookup"><span data-stu-id="087b6-447">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="087b6-448">攻撃者は、メッセージに良い URL と悪い URL を組み合わせ、配信を試みているが、悪意のあるリンクをより面白く見せている。</span><span class="sxs-lookup"><span data-stu-id="087b6-448">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="087b6-449">URL のテーブルはメールの総数で並べ替えされますが、この列は非表示に設定され、ビューが簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-449">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="087b6-450">**トップ クリックは** 、クリックされた安全なリンクでラップされた URL で、クリック総数で並べ替えされます。</span><span class="sxs-lookup"><span data-stu-id="087b6-450">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="087b6-451">ビューを簡略化するために、この列も表示されません。</span><span class="sxs-lookup"><span data-stu-id="087b6-451">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="087b6-452">列別の総数は、クリックされた URL ごとに [安全なリンク] クリックの評決カウントを示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-452">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="087b6-453">[フィッシング メール] ビューでは、通常、疑わしい URL または悪意のある URL です。</span><span class="sxs-lookup"><span data-stu-id="087b6-453">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="087b6-454">ただし、このビューには、脅威ではないがフィッシング メッセージに含まれる URL が含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-454">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="087b6-455">ラップされていないリンクの URL クリックはここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="087b6-455">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="087b6-456">2 つの URL テーブルには、配信アクションと場所別のフィッシングメール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-456">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="087b6-457">この表には、警告にもかかわらずブロックまたはアクセスされた URL クリックが表示されます。そのため、ユーザーに表示された潜在的な不良リンクと、ユーザーがクリックした可能性のあるリンクを確認できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-457">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the user's clicked.</span></span> <span data-ttu-id="087b6-458">ここから、さらに分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-458">From here, you can conduct further analysis.</span></span> <span data-ttu-id="087b6-459">たとえば、グラフの下には、組織の環境でブロックされた電子メール メッセージの上位 URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-459">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-460">![ブロックされたエクスプローラー URL](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-460">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="087b6-461">URL を選択して、詳細な情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="087b6-461">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="087b6-462">[URL の飛び出し] ダイアログ ボックスで、電子メール メッセージのフィルター処理が削除され、環境内での URL の露出の完全なビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-462">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="087b6-463">これにより、エクスプローラーで懸念される電子メール メッセージをフィルター処理し、潜在的な脅威である特定の URL を見つけ、エクスプローラー ビュー自体に URL フィルターを追加することなく、([URL の詳細] ダイアログ ボックスを使用して) 環境内の URL 露出に関する理解を広げます。</span><span class="sxs-lookup"><span data-stu-id="087b6-463">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="087b6-464">クリックの評決の解釈</span><span class="sxs-lookup"><span data-stu-id="087b6-464">Interpretation of click verdicts</span></span>

<span data-ttu-id="087b6-465">[メール] または [URL] フライアウト、トップ クリック数、およびフィルター 処理エクスペリエンス内では、さまざまなクリックの評決値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-465">Within the Email or URL flyouts, Top Clicks as well as within our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="087b6-466">**なし:** URL の評決をキャプチャできません。</span><span class="sxs-lookup"><span data-stu-id="087b6-466">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="087b6-467">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-467">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="087b6-468">**許可:** ユーザーは URL への移動を許可されました。</span><span class="sxs-lookup"><span data-stu-id="087b6-468">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="087b6-469">**ブロック:** ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="087b6-469">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="087b6-470">**保留中の評決:** ユーザーに、削除保留中のページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="087b6-470">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="087b6-471">**ブロックされたオーバーライド:** ユーザーが URL への直接移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="087b6-471">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="087b6-472">ただし、ユーザーはブロックをオーバーロードして URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="087b6-472">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="087b6-473">**保留中の評決はバイパスされます。** ユーザーには、削除ページが表示されました。</span><span class="sxs-lookup"><span data-stu-id="087b6-473">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="087b6-474">ただし、ユーザーはメッセージをオーバーロードして URL にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="087b6-474">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="087b6-475">**エラー:** ユーザーにエラー ページが表示されたか、または評決のキャプチャでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="087b6-475">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="087b6-476">**失敗:** 評決のキャプチャ中に不明な例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="087b6-476">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="087b6-477">ユーザーが URL をクリックした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-477">The user might have clicked through the URL.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="087b6-478">ユーザーが報告した電子メール メッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="087b6-478">Review email messages reported by users</span></span>

<span data-ttu-id="087b6-479">組織内のユーザーが迷惑メール 、迷惑メールではない、またはフィッシングとして報告した電子メール メッセージを、レポート[](enable-the-report-message-add-in.md)メッセージ アドインまたはレポート フィッシング アドインを介して表示すると[します](enable-the-report-phish-add-in.md)。 </span><span class="sxs-lookup"><span data-stu-id="087b6-479">Suppose that you want to see email messages that users in your organization reported as *Junk*, *Not Junk*, or *Phishing* through the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span> <span data-ttu-id="087b6-480">それらを表示するには、エクスプローラーの [**[電子**  >  **メール送信]**](threat-explorer-views.md#email--submissions)ビュー (またはリアルタイム検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="087b6-480">To see them, use the [**Email** > **Submissions**](threat-explorer-views.md#email--submissions) view of Explorer (or Real-time detections).</span></span>

1. <span data-ttu-id="087b6-481">セキュリティ コンプライアンス センター ( &) で <https://protection.office.com> 、[脅威 **管理** \> **エクスプローラー** ] (または [ **リアルタイムの検出] ) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-481">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="087b6-482">(この例では、エクスプローラーを使用します)。</span><span class="sxs-lookup"><span data-stu-id="087b6-482">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="087b6-483">[表示] **メニューの** [メールの提出 **]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-483">In the **View** menu, choose **Email** \> **Submissions**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-484">![電子メールのエクスプローラーの [表示] メニュー](../../media/explorer-view-menu-email-user-reported.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-484">![View menu for Explorer for emails](../../media/explorer-view-menu-email-user-reported.png)</span></span>

3. <span data-ttu-id="087b6-485">[送信者 **] を** クリックし、[基本レポート **の種類]** \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="087b6-485">Click **Sender**, and then choose **Basic** \> **Report type**.</span></span>

4. <span data-ttu-id="087b6-486">フィッシングなどのオプションを選択 **し**、[更新] ボタン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="087b6-486">Select an option, such as **Phish**, and then select the **Refresh** button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="087b6-487">![ユーザーが報告したフィッシング](../../media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="087b6-487">![User-reported phish](../../media/EmailUserReportedReportType.png)</span></span>

<span data-ttu-id="087b6-488">レポートが更新され、組織内のユーザーがフィッシング詐欺の試みとして報告した電子メール メッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-488">The report refreshes to show data about email messages that people in your organization reported as a phishing attempt.</span></span> <span data-ttu-id="087b6-489">この情報を使用して、さらに分析を行い、必要に応じて Microsoft Defender のフィッシング対策ポリシーを [365](configure-atp-anti-phishing-policies.md)用に調整Officeできます。</span><span class="sxs-lookup"><span data-stu-id="087b6-489">You can use this information to conduct further analysis, and, if necessary, adjust your [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="087b6-490">自動調査と対応を開始する</span><span class="sxs-lookup"><span data-stu-id="087b6-490">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="087b6-491">Microsoft Defender では、365 プラン 2 および *365* *E5* のOfficeの自動調査と対応Office利用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-491">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="087b6-492">[自動調査と対応により](automated-investigation-response-office.md) 、セキュリティ運用チームがサイバー攻撃の調査と軽減に費やした時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-492">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="087b6-493">セキュリティ プレイブックをトリガーできるアラートの構成に加えて、エクスプローラーのビューから自動調査と応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-493">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="087b6-494">詳細については、「例 [: セキュリティ管理者がエクスプローラーから調査をトリガーする」を参照してください](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="087b6-494">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a><span data-ttu-id="087b6-495">エクスプローラーとリアルタイム検出を使用するその他の方法</span><span class="sxs-lookup"><span data-stu-id="087b6-495">More ways to use Explorer and Real-time detections</span></span>

<span data-ttu-id="087b6-496">この記事で説明するシナリオに加えて、エクスプローラー (またはリアルタイム検出) で使用できるレポート オプションも多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="087b6-496">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or Real-time detections).</span></span> <span data-ttu-id="087b6-497">次の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="087b6-497">See the following articles:</span></span>

- [<span data-ttu-id="087b6-498">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="087b6-498">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="087b6-499">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="087b6-499">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](./mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="087b6-500">脅威エクスプローラー (およびリアルタイム検出) のビューの概要を取得する</span><span class="sxs-lookup"><span data-stu-id="087b6-500">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md)
- [<span data-ttu-id="087b6-501">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="087b6-501">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="087b6-502">Microsoft Threat Protection での自動調査および対応</span><span class="sxs-lookup"><span data-stu-id="087b6-502">Automated investigation and response in Microsoft Threat Protection</span></span>](../defender/m365d-autoir.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="087b6-503">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="087b6-503">Required licenses and permissions</span></span>

<span data-ttu-id="087b6-504">エクスプローラーまたは [リアルタイム検出を使用するには、Office 365](defender-for-office-365.md) 用の Microsoft Defender が必要です。</span><span class="sxs-lookup"><span data-stu-id="087b6-504">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="087b6-505">Explorer は Defender for Office 365 プラン 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="087b6-505">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="087b6-506">リアルタイム検出レポートは、Defender for Office 365 プラン 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="087b6-506">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="087b6-507">365 用に Defender によって保護される必要があるすべてのユーザーにライセンスを割り当Officeします。</span><span class="sxs-lookup"><span data-stu-id="087b6-507">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="087b6-508">エクスプローラーとリアルタイム検出では、ライセンスを取得したユーザーの検出データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="087b6-508">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="087b6-509">エクスプローラーまたはリアルタイム検出を表示および使用するには、セキュリティ管理者やセキュリティ リーダーに付与されたアクセス許可など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="087b6-509">To view and use Explorer or Real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="087b6-510">セキュリティ コンプライアンス センター&、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="087b6-510">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="087b6-511">組織の管理</span><span class="sxs-lookup"><span data-stu-id="087b6-511">Organization Management</span></span>
  - <span data-ttu-id="087b6-512">セキュリティ管理者 (これは Azure Active Directory 管理センター ( ) で割り当 <https://aad.portal.azure.com> てることができます。</span><span class="sxs-lookup"><span data-stu-id="087b6-512">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="087b6-513">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="087b6-513">Security Reader</span></span>

- <span data-ttu-id="087b6-514">Exchange Online の場合は、Exchange 管理センター ( ) または Exchange Online PowerShell で次のいずれかの役割が割り <https://admin.protection.outlook.com/ecp/> [当てられている必要があります](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="087b6-514">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center (<https://admin.protection.outlook.com/ecp/>) or [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell):</span></span>

  - <span data-ttu-id="087b6-515">組織の管理</span><span class="sxs-lookup"><span data-stu-id="087b6-515">Organization Management</span></span>
  - <span data-ttu-id="087b6-516">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="087b6-516">View-Only Organization Management</span></span>
  - <span data-ttu-id="087b6-517">"View-Only Recipients/表示専用受信者"</span><span class="sxs-lookup"><span data-stu-id="087b6-517">View-Only Recipients</span></span>
  - <span data-ttu-id="087b6-518">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="087b6-518">Compliance Management</span></span>

<span data-ttu-id="087b6-519">役割とアクセス許可の詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="087b6-519">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="087b6-520">セキュリティ/コンプライアンス センターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="087b6-520">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="087b6-521">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="087b6-521">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="087b6-522">脅威エクスプローラーとリアルタイム検出の違い</span><span class="sxs-lookup"><span data-stu-id="087b6-522">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="087b6-523">リアルタイム *検出レポートは* 、Defender で 365 プラン 1 Office使用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-523">The *Real-time detections* report is available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="087b6-524">*脅威エクスプローラー* は、Defender for Office 365 プラン 2 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-524">*Threat Explorer* is available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="087b6-525">リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。</span><span class="sxs-lookup"><span data-stu-id="087b6-525">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="087b6-526">脅威エクスプローラーも同様にこれを実行しますが、特定の攻撃に関する追加の詳細も提供します。</span><span class="sxs-lookup"><span data-stu-id="087b6-526">Threat Explorer does this as well, but it also provides additional details for a given attack.</span></span>
- <span data-ttu-id="087b6-527">すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="087b6-527">An *All email* view is available in Threat Explorer but not in the Real-time detections report.</span></span>
- <span data-ttu-id="087b6-528">脅威エクスプローラーには、より多くのフィルター機能と使用可能なアクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="087b6-528">More filtering capabilities and available actions are included in Threat Explorer.</span></span> <span data-ttu-id="087b6-529">詳細については [、「Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 プラン」を参照してください](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="087b6-529">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="other-articles"></a><span data-ttu-id="087b6-530">その他の記事</span><span class="sxs-lookup"><span data-stu-id="087b6-530">Other articles</span></span>

<span data-ttu-id="087b6-531">[[電子メール エンティティ] ページでメールを調査する](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="087b6-531">[Investigate emails with the Email Entity Page](mdo-email-entity-page.md)</span></span>
