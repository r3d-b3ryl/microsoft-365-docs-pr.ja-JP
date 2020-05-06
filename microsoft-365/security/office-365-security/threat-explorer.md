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
description: セキュリティ&amp;コンプライアンスセンターでエクスプローラおよびリアルタイム検出を使用して、効果的かつ効率的に脅威を調査して対応する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d540b52a403e43be06fc731590d183d5edfa7f9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036754"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="19bfc-103">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="19bfc-103">Threat Explorer and real-time detections</span></span>

<span data-ttu-id="19bfc-104">組織で[office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) を使用しており、[必要なアクセス許可](#required-licenses-and-permissions)がある場合は、 **Explorer**または**リアルタイムの検出**(以前の*リアルタイムのレポート*-[新機能を参照](#new-features-in-threat-explorer-and-real-time-detections)) があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-threat-explorer-and-real-time-detections)!).</span></span> <span data-ttu-id="19bfc-105">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**] に移動してから、[**エクスプローラー** ]_または_[**リアルタイムの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

|||
|---|---|
|<span data-ttu-id="19bfc-106">**ATP プラン2を使用すると、次のように表示されることになります。**</span><span class="sxs-lookup"><span data-stu-id="19bfc-106">**With ATP Plan 2, you see:**</span></span>|<span data-ttu-id="19bfc-107">**ATP プラン1では、次のように表示されることがあります。**</span><span class="sxs-lookup"><span data-stu-id="19bfc-107">**With ATP Plan 1, you see:**</span></span>|
|![脅威エクスプローラー](../../media/threatmgmt-explorer.png)|![リアルタイムの検出](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="19bfc-110">エクスプローラー (リアルタイム検出) を使用すると、強力なレポートが得られます。これにより、セキュリティ運用チームは脅威を調査して効果的かつ効率的に対処することができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently.</span></span> <span data-ttu-id="19bfc-111">このレポートは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-111">The report resembles the following image:</span></span>

![[脅威管理\>エクスプローラー] に移動します。](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="19bfc-113">このレポートでは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-113">With this report, you can:</span></span>

- [<span data-ttu-id="19bfc-114">Microsoft 365 セキュリティ機能によって検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="19bfc-114">See malware detected by Microsoft 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="19bfc-115">[フィッシング Url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)</span><span class="sxs-lookup"><span data-stu-id="19bfc-115">[View data about phishing URLs and click verdict](#view-data-about-phishing-urls-and-click-verdict)</span></span>
- <span data-ttu-id="19bfc-116">[エクスプローラーのビューから自動化された調査と応答プロセスを開始](#start-automated-investigation-and-response)する (ATP プラン2のみ)</span><span class="sxs-lookup"><span data-stu-id="19bfc-116">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="19bfc-117">...[悪意のある電子メールの調査など](#more-ways-to-use-explorer-or-real-time-detections)</span><span class="sxs-lookup"><span data-stu-id="19bfc-117">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="19bfc-118">脅威エクスプローラおよびリアルタイム検出の新機能</span><span class="sxs-lookup"><span data-stu-id="19bfc-118">New features in Threat Explorer and real-time detections</span></span>

<span data-ttu-id="19bfc-119">脅威エクスプローラーとリアルタイム検出に追加された3つの新機能:</span><span class="sxs-lookup"><span data-stu-id="19bfc-119">Three new features added into Threat Explorer and real-time detections:</span></span>

- [<span data-ttu-id="19bfc-120">メールヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="19bfc-120">Preview email header and download email body</span></span>](#preview-email-header-and-download-email-body)
- [<span data-ttu-id="19bfc-121">電子メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="19bfc-121">Email timeline</span></span>](#email-timeline)
- [<span data-ttu-id="19bfc-122">URL のエクスポートクリックデータ</span><span class="sxs-lookup"><span data-stu-id="19bfc-122">Export URL click data</span></span>](#export-url-click-data)

<span data-ttu-id="19bfc-123">これらの新機能について、以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-123">These new features are outlined below.</span></span>

### <a name="preview-email-header-and-download-email-body"></a><span data-ttu-id="19bfc-124">メールヘッダーのプレビューとメール本文のダウンロード</span><span class="sxs-lookup"><span data-stu-id="19bfc-124">Preview email header and download email body</span></span>

<span data-ttu-id="19bfc-125">電子メールヘッダーをプレビューして電子メール本文をダウンロードする機能は、脅威エクスプローラーで利用できる新機能です。</span><span class="sxs-lookup"><span data-stu-id="19bfc-125">The ability to preview an email header and download the email body are new features available in Threat Explorer.</span></span> <span data-ttu-id="19bfc-126">管理者は、ダウンロードしたヘッダーや電子メールメッセージを分析して脅威を調べることができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-126">Admins will be able to analyze downloaded headers/email messages for threats.</span></span> <span data-ttu-id="19bfc-127">電子メールメッセージをダウンロードすると情報の公開が危険になる可能性があるため、このプロセスは、役割ベースのアクセス制御 (RBAC) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-127">Because downloading email messages can risk the exposure of information, this process is controlled by roles-based access control (RBAC).</span></span> <span data-ttu-id="19bfc-128">新しい役割である [*プレビュー*] を別の役割グループ (セキュリティ操作やセキュリティ管理者など) に追加して、すべての電子メールメッセージビューでメールのダウンロードとヘッダーのプレビューを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-128">A new role, *Preview*, must be added to another role group (such as Security Operations or Security Administrator) to grant the ability to download mails and preview headers in all-email messages view.</span></span>

<span data-ttu-id="19bfc-129">しかし、エクスプローラー (およびリアルタイム検出) によって新しい新しいフィールドも追加され、電子メールメッセージがどこにいるかをより完全に把握することができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-129">But Explorer (and real-time detections) also adds fresh new fields designed to give you a more complete picture of where your email messages land.</span></span> <span data-ttu-id="19bfc-130">この変更の目的の一環として、セキュリティを確保したユーザーを探しやすくしていますが、最終的に問題の電子メールメッセージの場所がひとめでわかることになります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-130">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="19bfc-131">実行方法</span><span class="sxs-lookup"><span data-stu-id="19bfc-131">How is this done?</span></span> <span data-ttu-id="19bfc-132">配信状態は、次の2つの列に分けられました。</span><span class="sxs-lookup"><span data-stu-id="19bfc-132">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="19bfc-133">**配信アクション**-この電子メールの状態は何ですか。</span><span class="sxs-lookup"><span data-stu-id="19bfc-133">**Delivery Action** - What is the status of this email?</span></span>
- <span data-ttu-id="19bfc-134">**配信場所**-この電子メールは、結果としてルーティングされましたか?</span><span class="sxs-lookup"><span data-stu-id="19bfc-134">**Delivery Location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="19bfc-135">配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。</span><span class="sxs-lookup"><span data-stu-id="19bfc-135">Delivery Action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="19bfc-136">電子メールで実行可能なアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19bfc-136">Here are the possible actions an email can take:</span></span>

|||||
|---|---|---|---|
|<span data-ttu-id="19bfc-137">**届け**</span><span class="sxs-lookup"><span data-stu-id="19bfc-137">**Delivered**</span></span>|<span data-ttu-id="19bfc-138">**Junked**</span><span class="sxs-lookup"><span data-stu-id="19bfc-138">**Junked**</span></span>|<span data-ttu-id="19bfc-139">**Blocked**</span><span class="sxs-lookup"><span data-stu-id="19bfc-139">**Blocked**</span></span>|<span data-ttu-id="19bfc-140">**換わり**</span><span class="sxs-lookup"><span data-stu-id="19bfc-140">**Replaced**</span></span>|
|<span data-ttu-id="19bfc-141">電子メールがユーザーの受信トレイまたは別のフォルダーに配信され、ユーザーが直接アクセスできる。</span><span class="sxs-lookup"><span data-stu-id="19bfc-141">Email was delivered to the user's inbox or another folder, and the user can directly access it.</span></span>| <span data-ttu-id="19bfc-142">電子メールは、ユーザーの迷惑メールフォルダーまたは削除されたフォルダーに送信され、ユーザーはそのフォルダー内の電子メールメッセージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-142">Email was sent to either user's Junk folder or Deleted folder, and the user has access to email messages in those folders.</span></span>| <span data-ttu-id="19bfc-143">検疫された、失敗した、または削除された電子メールメッセージで、ユーザーがアクセスできないメッセージ。</span><span class="sxs-lookup"><span data-stu-id="19bfc-143">Any email messages that are quarantined, that failed, or were dropped, and are not accessible by the user.</span></span>| <span data-ttu-id="19bfc-144">添付ファイルが悪意のある添付ファイルであることを示す、悪意のある添付ファイルが .txt ファイルに置き換えられた電子メールメッセージ。</span><span class="sxs-lookup"><span data-stu-id="19bfc-144">Any email messages where malicious attachments were replaced by .txt files that state the attachments were malicious.</span></span>|
|

<span data-ttu-id="19bfc-145">次に、ユーザーが表示できる機能と、それができないことを示します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-145">And here is what the user can see, and what they can't:</span></span>

|||
|---|---|
|<span data-ttu-id="19bfc-146">**エンドユーザーがアクセス可能**</span><span class="sxs-lookup"><span data-stu-id="19bfc-146">**Accessible to end users**</span></span>|<span data-ttu-id="19bfc-147">**エンドユーザーがアクセスできない**</span><span class="sxs-lookup"><span data-stu-id="19bfc-147">**Inaccessible to end users**</span></span>|
|<span data-ttu-id="19bfc-148">届け</span><span class="sxs-lookup"><span data-stu-id="19bfc-148">Delivered</span></span>|<span data-ttu-id="19bfc-149">Blocked</span><span class="sxs-lookup"><span data-stu-id="19bfc-149">Blocked</span></span>|
|<span data-ttu-id="19bfc-150">Junked</span><span class="sxs-lookup"><span data-stu-id="19bfc-150">Junked</span></span>|<span data-ttu-id="19bfc-151">換わり</span><span class="sxs-lookup"><span data-stu-id="19bfc-151">Replaced</span></span>|
|

<span data-ttu-id="19bfc-152">[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-152">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="19bfc-153">配信アクションにリンクされています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-153">It's linked to a Delivery Action.</span></span> <span data-ttu-id="19bfc-154">このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。</span><span class="sxs-lookup"><span data-stu-id="19bfc-154">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="19bfc-155">配信場所の指定可能な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19bfc-155">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="19bfc-156">**受信トレイまたはフォルダー**: 電子メールは、受信トレイまたはフォルダー (メールルールに従って) にあります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-156">**Inbox or folder**: The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="19bfc-157">**オンプレミスまたは外部**: メールボックスはクラウド上に存在していますが、オンプレミスになっています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-157">**On-prem or external**: The mailbox doesn't exist on cloud but is on-premises.</span></span>
- <span data-ttu-id="19bfc-158">**迷惑メールフォルダー**: メールはユーザーの [迷惑メール] フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-158">**Junk folder**: The email is in the Junk folder of a user.</span></span>
- <span data-ttu-id="19bfc-159">**削除済みアイテムフォルダー**: ユーザーの [削除済みアイテム] フォルダー内の電子メール。</span><span class="sxs-lookup"><span data-stu-id="19bfc-159">**Deleted items folder**: The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="19bfc-160">**検疫**: 検疫内の電子メールは、ユーザーのメールボックスには含まれません。</span><span class="sxs-lookup"><span data-stu-id="19bfc-160">**Quarantine**: The email in quarantine, and is not in a user's mailbox.</span></span>
- <span data-ttu-id="19bfc-161">**失敗**: メールがメールボックスに到達できませんでした。</span><span class="sxs-lookup"><span data-stu-id="19bfc-161">**Failed**: The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="19bfc-162">**削除**: メールフロー内の任意の場所に電子メールが失われます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-162">**Dropped**: The email gets lost somewhere in the mail flow.</span></span>

### <a name="email-timeline"></a><span data-ttu-id="19bfc-163">電子メールのタイムライン</span><span class="sxs-lookup"><span data-stu-id="19bfc-163">Email timeline</span></span>

<span data-ttu-id="19bfc-164">**電子メールのタイムライン**は、管理者にとって、探しやすさを向上させるための別の新しいエクスプローラー機能です。</span><span class="sxs-lookup"><span data-stu-id="19bfc-164">The **Email Timeline** is another new Explorer feature aimed at making the hunting experience better for admins.</span></span> <span data-ttu-id="19bfc-165">イベントを理解するためにさまざまな場所をチェックするのにかかる時間が短くなるため、ランダム化が減少します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-165">It cuts down on randomization because there is less time spent checking different locations to try to understand the event.</span></span> <span data-ttu-id="19bfc-166">複数のイベントが電子メールで同時に発生するか、または同じ時刻に終了すると、これらのイベントがタイムラインビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-166">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="19bfc-167">実際、メールへの配信の後に発生する一部のイベントは、[特殊な操作] 列に記録されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-167">In fact, some events that happen post-delivery to your mail will be captured in the 'Special action' column.</span></span> <span data-ttu-id="19bfc-168">メールのタイムラインからの情報をメールの送信後の特別なアクションと組み合わせることにより、管理者は、ポリシーがどのように機能するか、メールが最後にルーティングされたか、場合によっては最終的な評価がどのようなものかを把握できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-168">Combining the information from the timeline of that mail with the special action taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span>

<span data-ttu-id="19bfc-169">悪意のある電子メールメッセージの調査の詳細については、「 [Office 365 で配信された悪意のある電子メールを調査および修復する](investigate-malicious-email-that-was-delivered.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19bfc-169">For more discussion about investigating malicious email messages, see [Investigate and remediate malicious email that was delivered in Office 365](investigate-malicious-email-that-was-delivered.md).</span></span>

### <a name="export-url-click-data"></a><span data-ttu-id="19bfc-170">URL のエクスポートクリックデータ</span><span class="sxs-lookup"><span data-stu-id="19bfc-170">Export URL click data</span></span>

<span data-ttu-id="19bfc-171">また、ネットワークメッセージ ID とそのクリック Verdict の両方を表示するために、URL クリックのレポートを Microsoft Excel にエクスポートできるようになりました。これにより、URL のクリック時のトラフィックが簡単になることを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-171">Also, you will now be able to export reports for URL clicks to Microsoft Excel in order to view both their Network Message ID, and their Click Verdict, making the task of understanding where your URL click traffic originated easier.</span></span> <span data-ttu-id="19bfc-172">そのしくみは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="19bfc-172">Here's how it works.</span></span> <span data-ttu-id="19bfc-173">Office 365 のクイック起動での脅威管理の開始で、次のチェーンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-173">Starting in Threat Management on the Office 365 quick-launch, click through this chain:</span></span>

<span data-ttu-id="19bfc-174">**エクスプローラー** \> **ビュー** \>フィッシング\> [**トップの url または url** \> **] をクリックします。いずれかのレコードをクリックして url のポップアップを開く** **Clicks**</span><span class="sxs-lookup"><span data-stu-id="19bfc-174">**Explorer** \> **View Phish** \> **Clicks** \> **Top URLs or URL Top Clicks** \> **Click on any record to open URL flyout**</span></span>

<span data-ttu-id="19bfc-175">一覧の URL をクリックすると、フライアウトパネルに新しい [エクスポート] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-175">When you click on a URL in the list, you'll see a new Export button on the fly-out panel.</span></span> <span data-ttu-id="19bfc-176">このボタンを使用して、レポートを容易にするために、データを Excel スプレッドシートに移動します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-176">Use this button to move data to an Excel spreadsheet for easier reporting.</span></span>

<span data-ttu-id="19bfc-177">リアルタイムの検出レポートでは、次のように同じ場所にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-177">You can get to the same location in the real-time detections report as follows:</span></span>

<span data-ttu-id="19bfc-178">**エクスプローラー** \> **のリアルタイム検出** \> **ビューフィッシング** \> **URLs** \>のトップの url**または上部** \> **のクリック [url] ポップアップ** \>を開くには、[**クリック] タブに移動します。**</span><span class="sxs-lookup"><span data-stu-id="19bfc-178">**Explorer** \> **Real-time Detections** \> **View Phish** \> **URLs** \> **Top URLs or Top Clicks** \> **Click on any record to open URL flyout** \> **Navigate to the Clicks Tab.**</span></span>

> [!TIP]
> <span data-ttu-id="19bfc-179">ネットワークメッセージ ID エクスプローラーまたは関連するサードパーティ製のツールでネットワークメッセージ ID を使用して検索したときに、[クリック戻る] を特定のメールにマップします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-179">Network Message ID maps the click back to specific mails when you search through Explorer or associated 3rd party tools via Network Message ID.</span></span> <span data-ttu-id="19bfc-180">ネットワークのメッセージ ID を検索すると、クリックの結果に関連付けられた特定の電子メールが管理者に付与されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-180">Searching through the Network Message ID will give admins the specific email associated with a click result.</span></span> <span data-ttu-id="19bfc-181">エクスポートが行われると、ネットワークメッセージ ID の相関 id があるため、より迅速かつ強力な分析が可能になります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-181">On export having, the correlating identification of Network Message ID makes for quicker and more powerful analysis.</span></span>

![tp_ExportClickResultAndNetworkID .png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="19bfc-183">テクノロジによる電子メールで検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="19bfc-183">See malware detected in email by technology</span></span>

<span data-ttu-id="19bfc-184">Microsoft 365 テクノロジを使用して、電子メールで検出されたマルウェアを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-184">Suppose you want to see malware detected in email, by Microsoft 365 technology.</span></span> <span data-ttu-id="19bfc-185">これを行うには、エクスプローラーの [[電子メール > マルウェア](threat-explorer-views.md#email--malware)] ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-185">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="19bfc-186">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-186">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="19bfc-187">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-187">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="19bfc-188">[**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-188">In the **View** menu, choose **Email** > **Malware**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailMalwareMenu.png)

3. <span data-ttu-id="19bfc-190">[**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-190">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span>

   <span data-ttu-id="19bfc-191">これで、検出テクノロジがレポートのフィルターとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-191">Your detection technologies are now available as filters for the report.</span></span>

   ![マルウェア検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTech.png)

4. <span data-ttu-id="19bfc-193">オプションを選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-193">Select an option, and then click the **Refresh** button to apply that filter.</span></span>

   ![選択されている検出テクノロジ](../../media/ExplorerEmailMalwareDetectionTechATP.png)

<span data-ttu-id="19bfc-195">レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-195">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="19bfc-196">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-196">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="19bfc-197">フィッシング Url に関するデータを表示し、[verdict] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-197">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="19bfc-198">許可された Url の一覧を含む、電子メール内の Url によるフィッシングの試行、禁止、および上書きを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-198">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="19bfc-199">クリックされた Url を識別するには、 [ATP の安全なリンク](atp-safe-links.md)を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-199">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="19bfc-200">[クリック時の保護とログ記録のための、 [atp の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を設定していることを確認してください] verdicts の [安全なリンク] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-200">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span>

<span data-ttu-id="19bfc-201">メッセージ内のフィッシング Url を確認し、フィッシングメッセージで Url をクリックするには、Explorer の[電子メール > フィッシング](threat-explorer-views.md#email--phish)ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-201">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="19bfc-202">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-202">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="19bfc-203">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-203">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="19bfc-204">[**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-204">In the **View** menu, choose **Email** > **Phish**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/ExplorerViewEmailPhishMenu.png)

3. <span data-ttu-id="19bfc-206">[**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-206">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="19bfc-207">1つまたは複数のオプション ([**ブロック**されて**ブロック**する] など) を選択し、[**更新**] ボタンをクリックして、そのフィルターを適用するオプションと同じ行にあるものをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-207">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="19bfc-208">(ブラウザーウィンドウを更新しないでください)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-208">(Don't refresh your browser window.)</span></span>

   ![Url および [verdicts] をクリックします。](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    <span data-ttu-id="19bfc-210">レポートが更新され、[URL] タブにレポートの下に2つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-210">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="19bfc-211">**トップ url**は、フィルター処理されたメッセージに含まれる url と、各 url の電子メール配信アクション数を示します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-211">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="19bfc-212">[フィッシング email] ビューには、通常、正当な Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-212">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="19bfc-213">攻撃者は、適切な Url と正しくない Url をメッセージに混在させて配信を試みることができますが、ユーザーがクリックすると、悪意のあるリンクがより興味深いものになります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-213">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="19bfc-214">Url の表は、電子メールの合計数によって並べ替えられます (ただし、ビューを簡略化するため、この列は非表示になっていることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-214">The table of URLs is sorted by total email count (but note that this column is hidden to simplify the view).</span></span>

   - <span data-ttu-id="19bfc-215">**トップクリック**は、クリックされた url をラップした安全なリンクです。 [合計] をクリックします (この列はビューを簡略化するためにも表示されません)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-215">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="19bfc-216">列別の合計カウント [セーフリンク] は、クリックされた各 URL の [verdict count] を示します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-216">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="19bfc-217">フィッシングの電子メール表示では、多くの場合、疑わしいまたは悪意のある Url になりますが、脅威ではないがフィッシングメッセージ内にある Url を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-217">In the phish email view, these are more often suspicious or malicious URLs, but could include URLs that are not threats but are in phish messages.</span></span> <span data-ttu-id="19bfc-218">ラップされていないリンクの URL クリックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="19bfc-218">URL clicks on unwrapped links will not show up here.</span></span>

   <span data-ttu-id="19bfc-219">2つの URL 表は、配信アクションと場所によって、フィッシング電子メールメッセージの上位の Url を示しています。また、ブロックされた (または警告によってアクセスされた) URL クリックが表示されるので、ユーザーがどのような潜在的なリンクを受信し、ユーザーが操作したかを把握できます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-219">The two URL tables show top URLs in phishing email messages by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="19bfc-220">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-220">From here, you can conduct further analysis.</span></span> <span data-ttu-id="19bfc-221">たとえば、グラフの下に、組織の環境でブロックされた電子メールメッセージ内の上位の Url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-221">For example, below the chart, you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   ![ブロックされたエクスプローラーの Url](../../media/ExplorerPhishClickVerdictURLs.png)

   <span data-ttu-id="19bfc-223">URL を選択して、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-223">Select a URL to view more detailed information.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="19bfc-224">URL のポップアップダイアログで、電子メールメッセージのフィルター処理が削除され、環境内の URL の公開が完全に表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-224">In the URL flyout dialog, the filtering on email messages is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="19bfc-225">これにより、関心のあるメールメッセージをエクスプローラーでフィルター処理し、潜在的な脅威である特定の Url を見つけ、URL フィルターをエクスプローラービュー自体に追加することなく、環境内の URL の公開について理解を深めることができます (URL の詳細ダイアログを使用)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-225">This lets you filter down email messages in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="19bfc-226">ユーザーが報告した電子メールメッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="19bfc-226">Review email messages reported by users</span></span>

<span data-ttu-id="19bfc-227">組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-227">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="19bfc-228">これを行うには、エクスプローラー (またはリアルタイムの検出) の[電子メール > 提出](threat-explorer-views.md#email--submissions)の表示] を使用します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-228">To do this, use the [Email > Submissions](threat-explorer-views.md#email--submissions) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="19bfc-229">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-229">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="19bfc-230">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-230">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="19bfc-231">[**表示**] メニューの [**電子メール** > の**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-231">In the **View** menu, choose **Email** > **Submissions**.</span></span>

   ![エクスプローラーの [表示] メニュー](../../media/explorer-view-menu-email-user-reported.png)

3. <span data-ttu-id="19bfc-233">[**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-233">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="19bfc-234">オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="19bfc-234">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span>

   ![ユーザーによって報告されるフィッシング](../../media/EmailUserReportedReportType.png)

<span data-ttu-id="19bfc-236">レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-236">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="19bfc-237">この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](configure-atp-anti-phishing-policies.md)を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-237">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="19bfc-238">自動調査と応答の開始</span><span class="sxs-lookup"><span data-stu-id="19bfc-238">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="19bfc-239">自動化された調査および応答機能は、 **office 365 ATP Plan 2**および**office 365 E5**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-239">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="19bfc-240">(新)自動化された[調査と応答](automated-investigation-response-office.md)によって、セキュリティ運用チームの時間と労力を節約し、cyberattacks を調査および軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-240">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="19bfc-241">セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-241">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span>

<span data-ttu-id="19bfc-242">詳細については、「[例: セキュリティ管理者がエクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19bfc-242">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="19bfc-243">エクスプローラーを使用するその他の方法 (またはリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="19bfc-243">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="19bfc-244">この記事で説明されているシナリオに加えて、エクスプローラー (またはリアルタイムの検出) で利用できるレポートオプションが他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-244">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span>

- [<span data-ttu-id="19bfc-245">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="19bfc-245">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="19bfc-246">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="19bfc-246">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="19bfc-247">脅威エクスプローラーのビューの概要 (およびリアルタイムの検出) を取得する</span><span class="sxs-lookup"><span data-stu-id="19bfc-247">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="19bfc-248">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="19bfc-248">Required licenses and permissions</span></span>

<span data-ttu-id="19bfc-249">エクスプローラーまたはリアルタイムの検出を取得するには、 [Office 365 ATP](office-365-atp.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="19bfc-249">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>

- <span data-ttu-id="19bfc-250">Explorer は Office 365 ATP Plan 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-250">Explorer is included in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="19bfc-251">リアルタイム検出レポートは、Office 365 ATP Plan 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-251">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>
- <span data-ttu-id="19bfc-252">Office 365 ATP で保護する必要があるすべてのユーザーにライセンスを割り当てることを計画します。</span><span class="sxs-lookup"><span data-stu-id="19bfc-252">Plan to assign licenses for all users who should be protected by Office 365 ATP.</span></span> <span data-ttu-id="19bfc-253">(エクスプローラーまたはリアルタイムの検出は、ライセンスが付与されたユーザーの検出データを示します)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-253">(Explorer or real-time detections shows detection data for licensed users.)</span></span>

<span data-ttu-id="19bfc-254">エクスプローラーまたはリアルタイム検出を表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-254">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span>

- <span data-ttu-id="19bfc-255">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-255">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="19bfc-256">組織の管理</span><span class="sxs-lookup"><span data-stu-id="19bfc-256">Organization Management</span></span>
  - <span data-ttu-id="19bfc-257">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="19bfc-257">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="19bfc-258">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="19bfc-258">Security Reader</span></span>

- <span data-ttu-id="19bfc-259">Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="19bfc-259">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="19bfc-260">組織の管理</span><span class="sxs-lookup"><span data-stu-id="19bfc-260">Organization Management</span></span>
  - <span data-ttu-id="19bfc-261">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="19bfc-261">View-only Organization Management</span></span>
  - <span data-ttu-id="19bfc-262">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="19bfc-262">View-Only Recipients role</span></span>
  - <span data-ttu-id="19bfc-263">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="19bfc-263">Compliance Management</span></span>

<span data-ttu-id="19bfc-264">役割とアクセス許可の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="19bfc-264">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="19bfc-265">セキュリティ&amp; /コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="19bfc-265">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="19bfc-266">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="19bfc-266">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="19bfc-267">脅威エクスプローラーとリアルタイム検出の相違点</span><span class="sxs-lookup"><span data-stu-id="19bfc-267">Some differences between Threat Explorer and real-time detections</span></span>

- <span data-ttu-id="19bfc-268">**リアルタイムの検出**レポートは OFFICE 365 atp plan 1 で利用できますが、**脅威エクスプローラー**は office 365 atp plan 2 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-268">The **real-time detections** report is available in Office 365 ATP Plan 1, whereas **Threat Explorer** is available in Office 365 ATP Plan 2.</span></span>
- <span data-ttu-id="19bfc-269">**リアルタイムの検出**レポートを使用すると、検出がリアルタイムで表示されます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-269">The **real-time detections** report allows you to view detections in real-time.</span></span> <span data-ttu-id="19bfc-270">**脅威エクスプローラー**も同様ですが、特定の攻撃に関する追加の詳細を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="19bfc-270">**Threat Explorer** does this as well, but also allows you to view additional details for a given attack.</span></span>
- <span data-ttu-id="19bfc-271">**すべての電子メール**ビューは、**脅威エクスプローラー**で使用できます (**リアルタイムの検出**レポートには含まれません)。</span><span class="sxs-lookup"><span data-stu-id="19bfc-271">An **All email** view is available in **Threat Explorer** (and is not in the **real-time detections** report).</span></span>
- <span data-ttu-id="19bfc-272">他のフィルター処理機能および使用可能なアクションは、**脅威エクスプローラー**に含まれています。</span><span class="sxs-lookup"><span data-stu-id="19bfc-272">More filtering capabilities and available actions are included in **Threat Explorer**.</span></span>

<span data-ttu-id="19bfc-273">詳細については、「 [Office 365 Atp サービスの説明: Advanced Threat Protection (ATP) プランで利用できる機能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19bfc-273">For more details, see [Office 365 ATP Service Description: Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>
