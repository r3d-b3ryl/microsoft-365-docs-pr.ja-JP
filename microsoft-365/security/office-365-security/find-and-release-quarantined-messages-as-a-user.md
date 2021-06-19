---
title: ユーザーとして検疫済みメッセージを検索して解放する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: ユーザーは、ユーザーに配信されるべきであった検疫済みメッセージを Exchange Online Protection (EOP) で表示して管理する方法を学ぶことができます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 02119130df847da48f0c25ba13cbb321c83f59dd
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028393"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="4ef30-103">EOP のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="4ef30-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ef30-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4ef30-104">**Applies to**</span></span>
- [<span data-ttu-id="4ef30-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4ef30-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4ef30-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4ef30-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4ef30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ef30-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4ef30-108">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="4ef30-109">詳細については、「[EOP での検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>


<span data-ttu-id="4ef30-110">検疫されたメッセージは、Microsoft 365 Defender ポータルで、または (管理者が設定している場合は) [エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)で表示および管理します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-110">You view and manage your quarantined messages in the Microsoft 365 Defender portal or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4ef30-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4ef30-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4ef30-112">Microsoft 365 Defender ポータルを開くには、<https://security.microsoft.com> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-112">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="4ef30-113">検疫ページを直接開くには、<https://security.microsoft.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-113">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="4ef30-114">管理者は、スパム対策ポリシーでメッセージを完全に削除する前に、メッセージを検疫で保持する期間を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-114">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="4ef30-115">検疫期間が切れたメッセージは回復できません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-115">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="4ef30-116">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="4ef30-117">管理者は、スパム対策ポリシーで[ エンドユーザー スパム通知を有効にする](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)こともできます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-117">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="4ef30-118">ユーザーは、スパム検疫メッセージをこれらの通知から直接リリースできます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-118">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="4ef30-119">ユーザーは、フィッシング検疫メッセージ (高精度のフィッシング詐欺メッセージではありません) をこれらの通知から直接確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-119">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="4ef30-120">詳細については、「[EOP でのエンドユーザースパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-120">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="4ef30-121">高確度フィッシング、マルウェアとして検疫されるか、メール フロー ルール (別名: トランスポート ルール) により検疫されたメッセージは、管理者のみが管理でき、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-121">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="4ef30-122">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-122">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="4ef30-123">メッセージを移動して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="4ef30-123">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="4ef30-124">検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="4ef30-124">View your quarantined messages</span></span>

1. <span data-ttu-id="4ef30-125">Microsoft 365 Defender ポータルで、**[メールと共同作業]** \> **[レビュー]** \> **[検疫]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4ef30-126">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-126">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4ef30-127">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-127">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4ef30-128">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="4ef30-128">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4ef30-129">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-129">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-130">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-130">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-131">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-131">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-132">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-132">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-133">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-133">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-134">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-134">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-135">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4ef30-135">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="4ef30-136">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-136">**Recipient**</span></span>
   - <span data-ttu-id="4ef30-137">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-137">**Message ID**</span></span>
   - <span data-ttu-id="4ef30-138">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-138">**Policy name**</span></span>
   - <span data-ttu-id="4ef30-139">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-139">**Size**</span></span>
   - <span data-ttu-id="4ef30-140">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-140">**Direction**</span></span>

   <span data-ttu-id="4ef30-141">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-141">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="4ef30-142">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-142">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4ef30-143">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ef30-143">The available filters are:</span></span>

   - <span data-ttu-id="4ef30-144">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-144">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4ef30-145">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-145">**Today**</span></span>
     - <span data-ttu-id="4ef30-146">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-146">**Next 2 days**</span></span>
     - <span data-ttu-id="4ef30-147">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-147">**Next 7 days**</span></span>
     - <span data-ttu-id="4ef30-148">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-148">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4ef30-149">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-149">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4ef30-150">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="4ef30-150">**Quarantine reason**:</span></span>
     - <span data-ttu-id="4ef30-151">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-151">**Bulk**</span></span>
     - <span data-ttu-id="4ef30-152">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-152">**Spam**</span></span>
     - <span data-ttu-id="4ef30-153">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="4ef30-153">**Phish**</span></span>

   - <span data-ttu-id="4ef30-154">**ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-154">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="4ef30-155">**マルウェア対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="4ef30-155">**Anti-malware policy**</span></span>
     - <span data-ttu-id="4ef30-156">**安全な添付ファイルのポリシー** (Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="4ef30-156">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="4ef30-157">**フィッシング対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="4ef30-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="4ef30-158">**ホストされているコンテンツ フィルター ポリシー** (スパム対策ポリシー)</span><span class="sxs-lookup"><span data-stu-id="4ef30-158">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="4ef30-159">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="4ef30-159">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="4ef30-160">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-160">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4ef30-161">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-161">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="4ef30-162">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-162">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4ef30-163">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-163">Wildcards aren't supported.</span></span> <span data-ttu-id="4ef30-164">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-164">You can search by the following values:</span></span>

   - <span data-ttu-id="4ef30-165">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4ef30-165">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="4ef30-166">一覧でメッセージを選択すると、表示される **[詳細]** ポップアップ ウィンドウに **[メッセージ ID]** 値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-166">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="4ef30-167">管理者は、[メッセージ追跡](message-trace-scc.md)を使用して、メッセージとそれに対応する [メッセージ ID] 値を検索できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-167">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="4ef30-168">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ef30-168">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="4ef30-169">**ポリシー名**: メッセージのポリシー名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-169">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="4ef30-170">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-170">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="4ef30-171">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="4ef30-171">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="4ef30-172">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-172">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4ef30-173">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-173">The search is not case-sensitive.</span></span>

   <span data-ttu-id="4ef30-174">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-174">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4ef30-175">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="4ef30-175">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="4ef30-176">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4ef30-176">Export message results</span></span>

1. <span data-ttu-id="4ef30-177">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-177">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="4ef30-178">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-178">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="4ef30-179">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-179">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="4ef30-180">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="4ef30-180">View quarantined message details</span></span>

<span data-ttu-id="4ef30-181">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-181">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ef30-182">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4ef30-182">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="4ef30-183">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-183">**Sender address**</span></span>
- <span data-ttu-id="4ef30-184">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="4ef30-184">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="4ef30-185">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4ef30-185">**Subject**</span></span>
- <span data-ttu-id="4ef30-186">[**検疫の理由**]: メッセージが [**迷惑メール**]、[**バルク メール**]、または [**フィッシング**] として識別されたかを表示します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-186">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="4ef30-187">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ef30-187">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="4ef30-188">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="4ef30-188">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="4ef30-189">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="4ef30-189">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="4ef30-190">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="4ef30-190">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4ef30-191">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="4ef30-191">Take action on quarantined email</span></span>

<span data-ttu-id="4ef30-192">メッセージを選択すると、**[詳細]** ポップアップ ウィンドウに、そのメッセージに関してどんな操作を実行するかを選択するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-192">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4ef30-193">**[メッセージの解放]**: 表示されるポップアップ ウィンドウで、**[メッセージを分析のために Microsoft に報告する]** かどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-193">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="4ef30-194">これは既定で有効になっており、誤って検疫されたメッセージが誤検知として Microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-194">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="4ef30-195">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-195">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="4ef30-196">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-196">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4ef30-197">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="4ef30-197">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="4ef30-198">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-198">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4ef30-199">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-199">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="4ef30-200">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-200">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="4ef30-201">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-201">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4ef30-202">**[検疫から削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-202">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="4ef30-203">**送信者のブロック**: メールボックスの [ブロックされた送信者] リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-203">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="4ef30-204">詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-204">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="4ef30-205">メールボックスの [ブロックされた送信者] リストに送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="4ef30-205">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="4ef30-206">詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ef30-206">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="4ef30-207">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-207">When you're finished, click **Close**.</span></span>

<span data-ttu-id="4ef30-208">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-208">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4ef30-209">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="4ef30-209">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4ef30-210">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-210">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4ef30-211">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4ef30-211">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="4ef30-212">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="4ef30-212">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4ef30-213">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ef30-213">When you're finished, click **Close**.</span></span>
