---
title: Office 365 のユーザーとして検疫済みメッセージを検索して解放する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Office 365 のユーザーは、検疫されたメッセージ (本人が受信者で、スパム フィルターによりスパムまたはバルク メールとして検疫されたメッセージ) を表示、解放、削除することができます。 検疫されたメッセージの表示と管理は、セキュリティ/コンプライアンス センターで行います。
ms.openlocfilehash: e74358d57b96c8655fbf6a3f7f0b6eedb5e65ede
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857335"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="4d14a-104">Office 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="4d14a-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="4d14a-105">検疫を実行すると、Exchange Online メールボックスを使用している Office 365 組織や、Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織の危険な可能性のあるメッセージや不要なメッセージが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="4d14a-106">詳細については、「[Office 365 での検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d14a-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="4d14a-107">ユーザーは、本人が受信者で、スパム、バルク メール、または (2020 年 4 月以降) フィッシングとして検疫された検疫済みメッセージを表示、解放、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="4d14a-108">誤検知を Microsoft に報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="4d14a-109">検疫されたメッセージの表示と管理は、セキュリティ/コンプライアンス センターで行います。</span><span class="sxs-lookup"><span data-stu-id="4d14a-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4d14a-110">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="4d14a-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4d14a-111">Office 365 セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="4d14a-112">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="4d14a-113">管理者は、どれ程の期間メッセージを保持してから完全に削除するかを設定できます (スパム対策ポリシー)。</span><span class="sxs-lookup"><span data-stu-id="4d14a-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="4d14a-114">検疫期間が切れたメッセージは回復できません。</span><span class="sxs-lookup"><span data-stu-id="4d14a-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="4d14a-115">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d14a-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="4d14a-116">管理者は、スパム対策ポリシーで[ エンドユーザー スパム通知を有効にする](configure-your-spam-filter-policies.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies.</span></span> <span data-ttu-id="4d14a-117">2019 年 10 月より、検疫されたメッセージをこのような通知から直接開放することはできなくなっています。</span><span class="sxs-lookup"><span data-stu-id="4d14a-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="4d14a-118">通知の **[レビュー]** をクリックすると、セキュリティ/コンプライアンス センターの [検疫] に移動できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="4d14a-119">詳細については、「[Office 365 でのエンドユーザースパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d14a-119">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="4d14a-120">高確度フィッシング、マルウェアとして検疫されるか、メール フロー ルール (別名: トランスポート ルール) により検疫されたメッセージは、管理者のみが管理できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="4d14a-121">詳細については、「[Office 365 の管理者として検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-an-administrator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d14a-121">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

- <span data-ttu-id="4d14a-122">あるメッセージを開放して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="4d14a-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="4d14a-123">検疫済みメッセージを表示する</span><span class="sxs-lookup"><span data-stu-id="4d14a-123">View your quarantined messages</span></span>

1. <span data-ttu-id="4d14a-124">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4d14a-125">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4d14a-126">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4d14a-127">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="4d14a-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4d14a-128">**[Received](受信日時)**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-129">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-130">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-131">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-132">**[開放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-133">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-134">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d14a-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="4d14a-135">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-135">**Recipient**</span></span>

   - <span data-ttu-id="4d14a-136">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-136">**Message ID**</span></span>

   - <span data-ttu-id="4d14a-137">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-137">**Policy name**</span></span>

   - <span data-ttu-id="4d14a-138">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-138">**Size**</span></span>

   - <span data-ttu-id="4d14a-139">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-139">**Direction**</span></span>

   <span data-ttu-id="4d14a-140">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="4d14a-141">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4d14a-142">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4d14a-142">The available filters are:</span></span>

   - <span data-ttu-id="4d14a-143">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="4d14a-144">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-144">**Today**</span></span>

     - <span data-ttu-id="4d14a-145">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-145">**Next 2 days**</span></span>

     - <span data-ttu-id="4d14a-146">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-146">**Next 7 days**</span></span>

     - <span data-ttu-id="4d14a-147">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4d14a-148">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4d14a-149">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="4d14a-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="4d14a-150">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-150">**Bulk**</span></span>

     - <span data-ttu-id="4d14a-151">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-151">**Spam**</span></span>

     - <span data-ttu-id="4d14a-152">**[フィッシング]** (2020 年 4 月以降)</span><span class="sxs-lookup"><span data-stu-id="4d14a-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="4d14a-153">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4d14a-154">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="4d14a-155">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4d14a-156">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4d14a-156">Wildcards aren't supported.</span></span> <span data-ttu-id="4d14a-157">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-157">You can search by the following values:</span></span>

   - <span data-ttu-id="4d14a-158">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4d14a-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="4d14a-159">一覧でメッセージを選択すると、表示される **[詳細]** ポップアップ ウィンドウに **[メッセージ ID]** 値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="4d14a-160">管理者は、[メッセージ追跡](message-trace-scc.md)を使用して、メッセージとそれに対応する [メッセージ ID] 値を検索できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="4d14a-161">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="4d14a-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="4d14a-162">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="4d14a-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="4d14a-163">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4d14a-164">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="4d14a-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="4d14a-165">検索条件を入力したら、![[更新] ボタン](../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4d14a-166">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="4d14a-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="4d14a-167">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4d14a-167">Export message results</span></span>

1. <span data-ttu-id="4d14a-168">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="4d14a-169">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="4d14a-170">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="4d14a-171">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="4d14a-171">View quarantined message details</span></span>

<span data-ttu-id="4d14a-172">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4d14a-173">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="4d14a-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="4d14a-174">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-174">**Sender address**</span></span>

- <span data-ttu-id="4d14a-175">**[Received](受信日時)**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="4d14a-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="4d14a-176">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d14a-176">**Subject**</span></span>

- <span data-ttu-id="4d14a-177">**[検疫の理由]**: メッセージが **[スパム]**、**[バルク]**、**[フィッシング]** (2020 年 4 月以降) のいずれとして識別されたかを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="4d14a-178">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d14a-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="4d14a-179">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="4d14a-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="4d14a-180">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="4d14a-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="4d14a-181">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="4d14a-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4d14a-182">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="4d14a-182">Take action on quarantined email</span></span>

<span data-ttu-id="4d14a-183">メッセージを選択すると、**[詳細]** ポップアップ ウィンドウに、そのメッセージに関してどんな操作を実行するかを選択するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4d14a-184">**[メッセージの解放]**: 表示されるポップアップ ウィンドウで、**[メッセージを分析のために Microsoft に報告する]** かどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="4d14a-185">これは既定で有効になっており、誤って検疫されたメッセージが誤検知として報告されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="4d14a-186">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="4d14a-187">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4d14a-188">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Office 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="4d14a-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="4d14a-189">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4d14a-190">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="4d14a-191">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="4d14a-192">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4d14a-193">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="4d14a-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="4d14a-194">**[検疫から削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="4d14a-195">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="4d14a-196">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4d14a-197">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="4d14a-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4d14a-198">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4d14a-199">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを開放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4d14a-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="4d14a-200">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="4d14a-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4d14a-201">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d14a-201">When you're finished, click **Close**.</span></span>
