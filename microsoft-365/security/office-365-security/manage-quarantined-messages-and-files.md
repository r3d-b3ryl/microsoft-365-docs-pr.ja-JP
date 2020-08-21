---
title: 管理者として検疫済みメッセージとファイルを管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) のすべてのユーザーの検疫済みメッセージの表示方法と管理方法を学習できます。 Office 365 Advanced Threat Protection (Office 365 ATP) を持つ組織内の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams の検疫ファイルを管理することもできます。
ms.openlocfilehash: 5da67f15a933694c1aef059ff18945122e3ee2e8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827065"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="e6ed3-104">EOP の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="e6ed3-105">Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e6ed3-106">詳細については [、EOP の検疫済み電子メール メッセージを参照してください](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e6ed3-107">管理者は、すべてのユーザーの検疫済みメッセージのすべての種類の検疫済みメッセージを表示、解放、削除できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e6ed3-108">マルウェア、高度フィッシング、メール フロー ルール (別名: トランスポート ルール) の結果として検疫されたメッセージを管理できるのは管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e6ed3-109">管理者は、誤検知を Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e6ed3-110">Office 365 Advance Threat Protection (Office 365 ATP) を持つ組織の管理者は、SharePoint Online、OneDrive for Business、および Microsoft Teams の検疫されたファイルを表示、ダウンロード、削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e6ed3-111">検疫されたメッセージの表示と管理は、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell、Exchange Online メールボックスを持たない組織の場合はスタンドアロン EOP PowerShell)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6ed3-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e6ed3-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6ed3-113">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e6ed3-114">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e6ed3-115">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e6ed3-116">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e6ed3-117">管理者として検疫を管理する前に、アクセス許可を割り当てる必要があります。このアクセス許可は、コンプライアンス センターの **[検** 疫] 役割 &によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="e6ed3-118">既定では、この役割は、セキュリティ/コンプライアンス センター **で組織管理** (グローバル管理者)、 **検疫**管理者、 **およびセキュリティ** 管理者の役割グループに割 &り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e6ed3-119">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e6ed3-120">検疫されたメッセージは、自動的に削除されるまでの既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="e6ed3-121">スパム対策ポリシー (スパム、フィッシング、バルク メール) によって検疫されたメッセージ: 30 日。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="e6ed3-122">これは既定および最大値です。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-122">This is the default and maximum value.</span></span> <span data-ttu-id="e6ed3-123">この値を構成するには、「スパム対策 [ポリシーの構成」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="e6ed3-124">マルウェアを含むメッセージ: 15 日。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="e6ed3-125">検疫の終了後は、メッセージを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e6ed3-126">セキュリティ センター コンプライアンス センター&、検疫済み電子メール メッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e6ed3-127">検疫済みメールを表示する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-127">View quarantined email</span></span>

1. <span data-ttu-id="e6ed3-128">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e6ed3-129">[**検疫済みを表示**] が既定値の [**メール**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e6ed3-130">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e6ed3-131">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e6ed3-132">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e6ed3-133">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-134">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-135">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-136">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-137">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-138">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-139">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-139">**Recipient**</span></span>

   - <span data-ttu-id="e6ed3-140">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-140">**Message ID**</span></span>

   - <span data-ttu-id="e6ed3-141">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-141">**Policy name**</span></span>

   - <span data-ttu-id="e6ed3-142">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-142">**Size**</span></span>

   - <span data-ttu-id="e6ed3-143">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-143">**Direction**</span></span>

   <span data-ttu-id="e6ed3-144">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e6ed3-145">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e6ed3-146">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-146">The available filters are:</span></span>

   - <span data-ttu-id="e6ed3-147">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e6ed3-148">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-148">**Today**</span></span>

     - <span data-ttu-id="e6ed3-149">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-149">**Next 2 days**</span></span>

     - <span data-ttu-id="e6ed3-150">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-150">**Next 7 days**</span></span>

     - <span data-ttu-id="e6ed3-151">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e6ed3-152">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e6ed3-153">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="e6ed3-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="e6ed3-154">**Policy:** メッセージは、メール フロー ルール (トランスポート ルールとも呼ばれる) の条件に一致しました。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="e6ed3-155">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-155">**Bulk**</span></span>

     - <span data-ttu-id="e6ed3-156">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-156">**Phish**</span></span>

     - <span data-ttu-id="e6ed3-157">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-157">**Malware**</span></span>

     - <span data-ttu-id="e6ed3-158">**スパム**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-158">**Spam**</span></span>

     - <span data-ttu-id="e6ed3-159">**精度の高いフィッシング**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e6ed3-160">**メール受信者**: すべてのユーザー、または自分に送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e6ed3-161">エンド ユーザーは、自分に送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e6ed3-162">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e6ed3-163">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e6ed3-164">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e6ed3-165">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-165">Wildcards aren't supported.</span></span> <span data-ttu-id="e6ed3-166">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-166">You can search by the following values:</span></span>

   - <span data-ttu-id="e6ed3-167">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="e6ed3-168">たとえば、組織内の [ユーザーに送信](message-trace-scc.md) されたメッセージをメッセージ追跡で使用し、メッセージは配信の代わりに検疫されたことも確認しました。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e6ed3-169">角かっこ ( ) を含める可能性がある完全なメッセージ ID 値を含める必要があります \<\> 。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e6ed3-170">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e6ed3-171">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e6ed3-172">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e6ed3-173">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e6ed3-174">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="e6ed3-175">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e6ed3-176">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="e6ed3-177">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6ed3-177">Export message results</span></span>

1. <span data-ttu-id="e6ed3-178">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e6ed3-179">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e6ed3-180">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e6ed3-181">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-181">View quarantined message details</span></span>

<span data-ttu-id="e6ed3-182">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e6ed3-183">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e6ed3-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-184">**Sender address**</span></span>

- <span data-ttu-id="e6ed3-185">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e6ed3-186">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-186">**Subject**</span></span>

- <span data-ttu-id="e6ed3-187">**検疫の**理由: メッセージがスパム、一括、**Spam**フィ**Bulk**ッシング**として**識別されたか、メール フロー ルール (**トランスポート**ルール) と一致したか、マルウェアが含まれているとして特定されたかを**示します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e6ed3-188">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e6ed3-189">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e6ed3-190">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e6ed3-191">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e6ed3-192">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-192">Take action on quarantined email</span></span>

<span data-ttu-id="e6ed3-193">メッセージを選択すると、[詳細] ポップアップ ウィンドウのメッセージ処理の処理方法として **、いくつかの** オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e6ed3-194">**メッセージを解**放: 表示されるポップアップ ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e6ed3-195">**分析用に Microsoft に報告してください**。既定では選択され、誤って検疫済みメッセージが誤検知として Microsoft に報告されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e6ed3-196">スパム、バルク、フィッシング、またはマルウェアを含むメッセージが検疫された場合、メッセージは Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e6ed3-197">分析によっては、このメッセージが許可されるサービス全体のスパム フィルター ルールが調整される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e6ed3-198">次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="e6ed3-199">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="e6ed3-200">**メッセージを特定の受信者に解放する**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="e6ed3-201">**他のユーザーへのメッセージの解放**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-201">**Release messages to other people**</span></span>

  <span data-ttu-id="e6ed3-202">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e6ed3-203">メッセージのリリースに関するメモ:</span><span class="sxs-lookup"><span data-stu-id="e6ed3-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e6ed3-204">同じ受信者へのメッセージを 2 回以上解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="e6ed3-205">見出し可能な受信者の一覧に、そのメッセージを受信したのは受信者のみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e6ed3-206">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e6ed3-207">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e6ed3-208">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e6ed3-209">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e6ed3-210">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="e6ed3-211">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e6ed3-212">**検疫から削除**します。表示される警告で **[は** い] をクリックすると、メッセージは直ちに削除されますが、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e6ed3-213">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e6ed3-214">**メッセージの**送信: 表示されるポップアップ ウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e6ed3-215">**オブジェクトの種類**: **電子メール** (既定 **)、URL、** または添付 **ファイル**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e6ed3-216">**提出形式**: **ネットワーク メッセージ ID** (既定。既定。ネットワーク メッセージ **ID** ボックスに対応する値があります) または **ファイル** (ローカルの .eml ファイルまたは .msg ファイルを参照)</span><span class="sxs-lookup"><span data-stu-id="e6ed3-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e6ed3-217">[ファイル] を選 **び** 、ネットワーク メッセージ **ID を選択すると、** 最初の値は無効になります。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="e6ed3-218">**Recipients**/ タイプ: メッセージの 1 人の元の受信者として入力するか、[ **すべてを選択] を** クリックしてすべての受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e6ed3-219">[すべて選択] を **クリックし** 、個々の受信者を選択的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e6ed3-220">**申請の理由**: **ブロックされていない (既定** ) またはブロック **されている必要がある**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e6ed3-221">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e6ed3-222">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e6ed3-223">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e6ed3-224">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e6ed3-225">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e6ed3-226">次のシナリオについて考えます。john@gmail.comをメッセージを送信してユーザーfaith@contoso.com送信john@subsidiary.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="e6ed3-227">Gmail はこのメッセージを、Microsoft のフィッシングとして検疫に両方ともルーティングされる 2 つのコピーに分割します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="e6ed3-228">管理者が、この両方のメッセージをこれらのメッセージからユーザーadmin@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="e6ed3-229">管理者メールボックスに到達する最初のリリース メッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="e6ed3-230">2 番目のリリース メッセージは重複配信として識別され、スキップされます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="e6ed3-231">メッセージは、メッセージ ID が同じで受信時刻が同じ場合は重複として識別されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="e6ed3-232">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e6ed3-233">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e6ed3-234">ATP のみ: セキュリティ、コンプライアンス センター&、検疫済みファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e6ed3-235">このセクションの隔ドされたファイルの手順は、ATP プラン 1 とプラン 2 のサブスクライバーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e6ed3-236">ATP を使用している組織では、管理者は SharePoint Online、OneDrive for Business、および Microsoft Teams の検疫されたファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e6ed3-237">検疫されたファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-237">View quarantined files</span></span>

1. <span data-ttu-id="e6ed3-238">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e6ed3-239">検 **疫されたビューを既定値** ファイルに **変更します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="e6ed3-240">使用できる列見出しをクリックすると、フィールドを並べ替えできます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e6ed3-241">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e6ed3-242">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e6ed3-243">既定の列には、アスタリスク ( ) が付い <sup>\*</sup> ています。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e6ed3-244">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="e6ed3-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-245">**位置情報**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-246">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-247">**ファイル URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-248">**ファイルのサイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-249">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-250">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e6ed3-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e6ed3-251">**検出元のデータ**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-251">**Detected by**</span></span>

   - <span data-ttu-id="e6ed3-252">**Modified by time (時間の変更者)**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-252">**Modified by time**</span></span>

4. <span data-ttu-id="e6ed3-253">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e6ed3-254">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-254">The available filters are:</span></span>

   - <span data-ttu-id="e6ed3-255">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e6ed3-256">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-256">**Today**</span></span>

     - <span data-ttu-id="e6ed3-257">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-257">**Next 2 days**</span></span>

     - <span data-ttu-id="e6ed3-258">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-258">**Next 7 days**</span></span>

     - <span data-ttu-id="e6ed3-259">ユーザー設定の日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-259">A custom date/time range.</span></span>

   - <span data-ttu-id="e6ed3-260">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-260">**Received time**</span></span>

   - <span data-ttu-id="e6ed3-261">**検疫理由**: 使用できる値は、マルウェア **のみです**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="e6ed3-262">特定の検疫済みファイルを見つけたら、そのファイルを選択して詳細を表示し、操作を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="e6ed3-263">ファイルの結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="e6ed3-263">Export file results</span></span>

1. <span data-ttu-id="e6ed3-264">必要なファイルを選択し、[結果のエクスポート] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e6ed3-265">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e6ed3-266">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e6ed3-267">検疫されたファイルの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-267">View quarantined file details</span></span>

<span data-ttu-id="e6ed3-268">一覧でファイルを選択すると、[詳細] ポップアップ ウィンドウに次の **ファイル詳細** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e6ed3-269">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-269">**File Name**</span></span>

- <span data-ttu-id="e6ed3-270">**ファイル URL**: ファイルの場所を定義する URL (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="e6ed3-271">**悪意のあるコンテンツの検出** ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="e6ed3-272">**Expires:** ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="e6ed3-273">**検出されたファイル**: ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジン。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="e6ed3-274">**[解放済み?]**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-274">**Released?**</span></span>

- <span data-ttu-id="e6ed3-275">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-275">**Malware Name**</span></span>

- <span data-ttu-id="e6ed3-276">**ドキュメント ID**: ドキュメントの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="e6ed3-277">**ファイル サイズ**: キロバイト (KB) 単位)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="e6ed3-278">**組織** 組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="e6ed3-279">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-279">**Last modified**</span></span>

- <span data-ttu-id="e6ed3-280">**更新者**: ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="e6ed3-281">**Secure Hash Algorithm 256-bit (SHA-256) 値**: このハッシュ値を使用して、他の評判ストアや、環境内の他の場所でファイルを識別することができます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e6ed3-282">検疫されたファイルを処理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-282">Take action on quarantined files</span></span>

<span data-ttu-id="e6ed3-283">一覧でファイルを選び、詳細ポップアップ ウィンドウで、ファイルに対して次 **の操作** を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e6ed3-284">**ファイルをリリース**: レポート ファイルを選択するか、レポート ファイル **を選択解除して分析を行い**、[ファイルのリリース **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="e6ed3-285">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-285">**Download file**</span></span>

- <span data-ttu-id="e6ed3-286">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="e6ed3-287">ファイルを解放または削除しない場合、既定の検疫保持期間が過ぎた後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e6ed3-288">複数の検疫されたファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="e6ed3-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e6ed3-289">一覧で複数の検疫済みファイル (最大 100 個) を選択すると、 **次の** 操作を実行できる一括操作のポップアップ ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e6ed3-290">**ファイルのリリース**</span><span class="sxs-lookup"><span data-stu-id="e6ed3-290">**Release files**</span></span>

- <span data-ttu-id="e6ed3-291">**[Delete files]**(ファイルの **削除):** 表示される警告で [はい] をクリックすると、ファイルは直ちに削除されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="e6ed3-292">組織でグローバル管理者権限 (または適切なセキュリティ & コンプライアンス センターの役割) を持つ職場または学校のアカウントを使用して、サインインして [セキュリティ & コンプライアンス センターに移動します](../../compliance/go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e6ed3-293">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して検疫済みメッセージとファイルを表示して管理する</span><span class="sxs-lookup"><span data-stu-id="e6ed3-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e6ed3-294">検疫内のメッセージとファイルを表示および管理するコマンドレットは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e6ed3-295">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e6ed3-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="e6ed3-296">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e6ed3-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="e6ed3-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e6ed3-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="e6ed3-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): このコマンドレットはメッセージ専用であり、SharePoint Online、OneDrive for Business、または Teams の ATP からのマルウェアファイルではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e6ed3-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e6ed3-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e6ed3-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
