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
ms.service: O365-seccomp
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
ms.openlocfilehash: 2a8e37dc430af5b3d3c47179c721d83832f01184
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600347"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="857d1-103">EOP のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="857d1-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="857d1-104">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="857d1-105">詳細については、「[EOP での検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d1-105">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="857d1-106">ユーザーは、自分が受信者で、スパムまたはバルク メールとして検疫された検疫済みメッセージを表示、解放、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="857d1-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="857d1-107">2020 年 4 月以降、ユーザーは、自分が受信者である検疫済みフィッシング メッセージ (高確度フィッシング詐欺メッセージを除く) を表示または削除できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="857d1-108">検疫されたメッセージをセキュリティ/コンプライアンス センターで表示および管理するか、(管理者がこの設定を構成している場合) [エンド ユーザーのスパム通知を](use-spam-notifications-to-release-and-report-quarantined-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="857d1-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="857d1-109">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="857d1-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="857d1-110">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="857d1-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="857d1-111">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="857d1-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="857d1-112">管理者は、どれ程の期間メッセージを保持してから完全に削除するかを設定できます (スパム対策ポリシー)。</span><span class="sxs-lookup"><span data-stu-id="857d1-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="857d1-113">検疫期間が切れたメッセージは回復できません。</span><span class="sxs-lookup"><span data-stu-id="857d1-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="857d1-114">詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d1-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="857d1-115">管理者は、スパム対策ポリシーで[ エンドユーザー スパム通知を有効にする](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)こともできます。</span><span class="sxs-lookup"><span data-stu-id="857d1-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="857d1-116">ユーザーは、スパム検疫メッセージをこれらの通知から直接リリースできます。</span><span class="sxs-lookup"><span data-stu-id="857d1-116">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="857d1-117">ユーザーは、フィッシング検疫メッセージ (高精度のフィッシング詐欺メッセージではありません) をこれらの通知から直接確認することができます。</span><span class="sxs-lookup"><span data-stu-id="857d1-117">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="857d1-118">詳細については、「[EOP でのエンドユーザースパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d1-118">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="857d1-119">高確度フィッシング、マルウェアとして検疫されるか、メール フロー ルール (別名: トランスポート ルール) により検疫されたメッセージは、管理者のみが管理でき、ユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="857d1-119">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="857d1-120">詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857d1-120">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="857d1-121">メッセージを移動して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="857d1-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="857d1-122">検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="857d1-122">View your quarantined messages</span></span>

1. <span data-ttu-id="857d1-123">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="857d1-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="857d1-124">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="857d1-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="857d1-125">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="857d1-126">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="857d1-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="857d1-127">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-128">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-129">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-130">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-131">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-132">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-133">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="857d1-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="857d1-134">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="857d1-134">**Recipient**</span></span>

   - <span data-ttu-id="857d1-135">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="857d1-135">**Message ID**</span></span>

   - <span data-ttu-id="857d1-136">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="857d1-136">**Policy name**</span></span>

   - <span data-ttu-id="857d1-137">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="857d1-137">**Size**</span></span>

   - <span data-ttu-id="857d1-138">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="857d1-138">**Direction**</span></span>

   <span data-ttu-id="857d1-139">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="857d1-140">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="857d1-141">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="857d1-141">The available filters are:</span></span>

   - <span data-ttu-id="857d1-142">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="857d1-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="857d1-143">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="857d1-143">**Today**</span></span>

     - <span data-ttu-id="857d1-144">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="857d1-144">**Next 2 days**</span></span>

     - <span data-ttu-id="857d1-145">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="857d1-145">**Next 7 days**</span></span>

     - <span data-ttu-id="857d1-146">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="857d1-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="857d1-147">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="857d1-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="857d1-148">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="857d1-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="857d1-149">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="857d1-149">**Bulk**</span></span>

     - <span data-ttu-id="857d1-150">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="857d1-150">**Spam**</span></span>

     - <span data-ttu-id="857d1-151">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="857d1-151">**Phish**</span></span>
     
   - <span data-ttu-id="857d1-152">**ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="857d1-152">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="857d1-153">**フィッシング対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="857d1-153">**Anti-phish policy**</span></span>
     - <span data-ttu-id="857d1-154">**ホストされているコンテンツ フィルター ポリシー**</span><span class="sxs-lookup"><span data-stu-id="857d1-154">**Hosted content filter policy**</span></span>
     

   <span data-ttu-id="857d1-155">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-155">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="857d1-156">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-156">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="857d1-157">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="857d1-157">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="857d1-158">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="857d1-158">Wildcards aren't supported.</span></span> <span data-ttu-id="857d1-159">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-159">You can search by the following values:</span></span>

   - <span data-ttu-id="857d1-160">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="857d1-160">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="857d1-161">一覧でメッセージを選択すると、表示される **[詳細]** ポップアップ ウィンドウに **[メッセージ ID]** 値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-161">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="857d1-162">管理者は、[メッセージ追跡](message-trace-scc.md)を使用して、メッセージとそれに対応する [メッセージ ID] 値を検索できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-162">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="857d1-163">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="857d1-163">**Sender email address**: A single sender's email address.</span></span>
   
   - <span data-ttu-id="857d1-164">**ポリシー名**: メッセージのポリシー名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="857d1-164">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="857d1-165">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="857d1-165">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="857d1-166">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="857d1-166">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="857d1-167">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="857d1-167">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="857d1-168">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="857d1-168">The search is not case-sensitive.</span></span>

   <span data-ttu-id="857d1-169">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-169">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="857d1-170">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="857d1-170">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="857d1-171">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="857d1-171">Export message results</span></span>

1. <span data-ttu-id="857d1-172">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-172">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="857d1-173">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-173">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="857d1-174">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-174">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="857d1-175">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="857d1-175">View quarantined message details</span></span>

<span data-ttu-id="857d1-176">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-176">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="857d1-177">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="857d1-177">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="857d1-178">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="857d1-178">**Sender address**</span></span>

- <span data-ttu-id="857d1-179">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="857d1-179">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="857d1-180">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="857d1-180">**Subject**</span></span>

- <span data-ttu-id="857d1-181">[**検疫の理由**]: メッセージが [**迷惑メール**]、[**バルク メール**]、または [**フィッシング**] として識別されたかを表示します。</span><span class="sxs-lookup"><span data-stu-id="857d1-181">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="857d1-182">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="857d1-182">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="857d1-183">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="857d1-183">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="857d1-184">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="857d1-184">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="857d1-185">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="857d1-185">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="857d1-186">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="857d1-186">Take action on quarantined email</span></span>

<span data-ttu-id="857d1-187">メッセージを選択すると、**[詳細]** ポップアップ ウィンドウに、そのメッセージに関してどんな操作を実行するかを選択するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-187">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="857d1-188">**[メッセージの解放]**: 表示されるポップアップ ウィンドウで、**[メッセージを分析のために Microsoft に報告する]** かどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="857d1-188">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="857d1-189">これは既定で有効になっており、誤って検疫されたメッセージが誤検知として Microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-189">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="857d1-190">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-190">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="857d1-191">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-191">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="857d1-192">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="857d1-192">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="857d1-193">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="857d1-193">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="857d1-194">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="857d1-194">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="857d1-195">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="857d1-195">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="857d1-196">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="857d1-196">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="857d1-197">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="857d1-197">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="857d1-198">**[検疫から削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-198">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="857d1-199">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-199">When you're finished, click **Close**.</span></span>

<span data-ttu-id="857d1-200">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="857d1-200">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="857d1-201">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="857d1-201">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="857d1-202">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-202">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="857d1-203">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="857d1-203">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="857d1-204">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="857d1-204">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="857d1-205">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857d1-205">When you're finished, click **Close**.</span></span>
