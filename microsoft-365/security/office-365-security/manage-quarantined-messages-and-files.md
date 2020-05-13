---
title: 管理者として検疫済みメッセージとファイルを管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: 管理者は、Exchange Online Protection (EOP) のすべてのユーザーの検疫済みメッセージを表示および管理する方法について説明します。 Office 365 Advanced Threat Protection (Office 365 ATP) を使用している組織内の管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫されたファイルを管理することもできます。
ms.openlocfilehash: 472a5258c112db7e8b8017e5d2ff19dc4741e93c
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213330"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="cf9c5-104">EOP で管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-104">Manage quarantined messages and files as an admin in EOP</span></span>

<span data-ttu-id="cf9c5-105">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスがない場合、検疫は潜在的に危険または不要なメッセージを保持します。365</span><span class="sxs-lookup"><span data-stu-id="cf9c5-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="cf9c5-106">詳細については、「EOP での検疫された[電子メールメッセージ](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cf9c5-107">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="cf9c5-108">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="cf9c5-109">管理者は、誤検知を Microsoft に報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="cf9c5-110">Office 365 の高度な脅威保護 (Office 365 ATP) を使用している組織での管理者は、SharePoint Online、OneDrive for Business、Microsoft Teams で検疫されたファイルを表示、ダウンロード、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="cf9c5-111">検疫されたメッセージを表示して管理するには、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスを持つ Microsoft 365 組織の場合は exchange Online PowerShell、Exchange Online メールボックスを使用していない組織の場合はスタンドアロン EOP PowerShell) を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf9c5-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="cf9c5-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf9c5-113">セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="cf9c5-114">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="cf9c5-115">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cf9c5-116">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cf9c5-117">管理者として検疫を管理するには、事前にアクセス許可を割り当てる必要があります。アクセス許可は、セキュリティ & コンプライアンスセンターの**検疫**役割によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="cf9c5-118">既定では、この役割はセキュリティ & コンプライアンスセンターの [**組織の管理**(グローバル管理者)]、[**検疫管理**者]、および [**セキュリティ管理者**] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="cf9c5-119">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="cf9c5-120">検疫済みメッセージは、自動的に削除されるまで既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="cf9c5-121">スパム対策ポリシー (スパム、フィッシング、およびバルクメール) によって検疫されたメッセージ:30 日。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="cf9c5-122">これは既定値で、最大値です。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-122">This is the default and maximum value.</span></span> <span data-ttu-id="cf9c5-123">この値を構成するには、「[スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="cf9c5-124">マルウェアを含むメッセージ:15 日。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="cf9c5-125">メッセージが検疫の期限切れになると、それを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="cf9c5-126">セキュリティ & コンプライアンスセンターを使用して検疫された電子メールメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="cf9c5-127">検疫済みメールを表示する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-127">View quarantined email</span></span>

1. <span data-ttu-id="cf9c5-128">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cf9c5-129">検疫済み**ビュー**が既定値の**電子メール**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="cf9c5-130">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cf9c5-131">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cf9c5-132">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cf9c5-133">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-134">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-135">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-136">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-137">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-138">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-139">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-139">**Recipient**</span></span>

   - <span data-ttu-id="cf9c5-140">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-140">**Message ID**</span></span>

   - <span data-ttu-id="cf9c5-141">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-141">**Policy name**</span></span>

   - <span data-ttu-id="cf9c5-142">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-142">**Size**</span></span>

   - <span data-ttu-id="cf9c5-143">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-143">**Direction**</span></span>

   <span data-ttu-id="cf9c5-144">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="cf9c5-145">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cf9c5-146">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-146">The available filters are:</span></span>

   - <span data-ttu-id="cf9c5-147">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="cf9c5-148">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-148">**Today**</span></span>

     - <span data-ttu-id="cf9c5-149">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-149">**Next 2 days**</span></span>

     - <span data-ttu-id="cf9c5-150">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-150">**Next 7 days**</span></span>

     - <span data-ttu-id="cf9c5-151">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cf9c5-152">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cf9c5-153">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="cf9c5-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="cf9c5-154">**ポリシー**: メッセージは、メールフロールール (トランスポートルールとも呼ばれます) の条件に一致しました。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="cf9c5-155">**バルク**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-155">**Bulk**</span></span>

     - <span data-ttu-id="cf9c5-156">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-156">**Phish**</span></span>

     - <span data-ttu-id="cf9c5-157">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-157">**Malware**</span></span>

     - <span data-ttu-id="cf9c5-158">**スパム**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-158">**Spam**</span></span>

     - <span data-ttu-id="cf9c5-159">**精度の高いフィッシング**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="cf9c5-160">**電子メール受信者**: すべてのユーザーまたは自分に送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="cf9c5-161">エンドユーザーは、それらに送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="cf9c5-162">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="cf9c5-163">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="cf9c5-164">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="cf9c5-165">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-165">Wildcards aren't supported.</span></span> <span data-ttu-id="cf9c5-166">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-166">You can search by the following values:</span></span>

   - <span data-ttu-id="cf9c5-167">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="cf9c5-168">たとえば、[メッセージ追跡](message-trace-scc.md)を使用して、組織内のユーザーに送信されたメッセージを検索したときに、メッセージが配信される代わりに検疫されたことを判断したとします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="cf9c5-169">山かっこ () が含まれる可能性がある完全なメッセージ ID 値を含めるようにしてください \< \> 。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="cf9c5-170">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="cf9c5-171">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="cf9c5-172">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="cf9c5-173">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="cf9c5-174">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="cf9c5-175">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="cf9c5-176">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="cf9c5-177">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="cf9c5-177">Export message results</span></span>

1. <span data-ttu-id="cf9c5-178">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="cf9c5-179">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="cf9c5-180">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="cf9c5-181">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-181">View quarantined message details</span></span>

<span data-ttu-id="cf9c5-182">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cf9c5-183">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="cf9c5-184">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-184">**Sender address**</span></span>

- <span data-ttu-id="cf9c5-185">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="cf9c5-186">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-186">**Subject**</span></span>

- <span data-ttu-id="cf9c5-187">**検疫理由**: メッセージが**スパム**、 **Bulk**、**フィッシング**、またはメールフロールール (**トランスポートルール**) に一致したか、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="cf9c5-188">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="cf9c5-189">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="cf9c5-190">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="cf9c5-191">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="cf9c5-192">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-192">Take action on quarantined email</span></span>

<span data-ttu-id="cf9c5-193">メッセージを選択した後、**詳細**のポップアップウィンドウのメッセージの処理に関するいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cf9c5-194">**Release message**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cf9c5-195">[**分析のために Microsoft にメッセージを報告する**]: これは既定でオンになっており、誤って検疫されたメッセージを誤検知として microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="cf9c5-196">メッセージがスパム、バルク、フィッシング、またはマルウェアとして検疫された場合は、メッセージも Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="cf9c5-197">分析によっては、サービス全体のスパムフィルタールールが、メッセージを経由して許可されるよう調整される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="cf9c5-198">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="cf9c5-199">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="cf9c5-200">**特定の受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="cf9c5-201">**他のユーザーにメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-201">**Release messages to other people**</span></span>

  <span data-ttu-id="cf9c5-202">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="cf9c5-203">メッセージの解放に関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="cf9c5-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="cf9c5-204">同じ受信者にメッセージを複数回解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="cf9c5-205">メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="cf9c5-206">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="cf9c5-207">ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="cf9c5-208">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="cf9c5-209">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="cf9c5-210">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="cf9c5-211">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="cf9c5-212">**検疫から削除**: 表示される警告で [**はい**] をクリックすると、メッセージは元の受信者に送信されることなく、すぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="cf9c5-213">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="cf9c5-214">**メッセージの送信**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cf9c5-215">**オブジェクトの種類**:**電子メール**(既定)、 **URL**、または**添付ファイル**。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="cf9c5-216">**送信形式**:**ネットワークメッセージ id** (既定では、対応する値が [**ネットワークメッセージ id** ] ボックスに表示されます) または**ファイル**(ローカル .eml または .msg ファイルを参照)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="cf9c5-217">[**ファイル**] を選択してから [**ネットワークメッセージ ID**] を選択すると、最初の値は失われていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="cf9c5-218">**受信者**: メッセージの元の受信者1人を入力するか、[**すべて選択**] をクリックしてすべての受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="cf9c5-219">[**すべて選択]** をクリックし、個々の受信者を選択的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="cf9c5-220">**送信の理由**: ブロックされて**いない**か (既定)、または**ブロックさ**れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="cf9c5-221">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="cf9c5-222">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="cf9c5-223">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="cf9c5-224">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cf9c5-225">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="cf9c5-226">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-226">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="cf9c5-227">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-227">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="cf9c5-228">ATP のみ: セキュリティ & コンプライアンスセンターを使用して検疫されたファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-228">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="cf9c5-229">このセクションの検疫ファイルの手順は、ATP Plan 1 および Plan 2 のサブスクライバーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-229">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="cf9c5-230">ATP を使用している組織では、管理者は SharePoint Online、OneDrive for Business、Microsoft Teams で検疫されたファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-230">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="cf9c5-231">検疫されたファイルの表示</span><span class="sxs-lookup"><span data-stu-id="cf9c5-231">View quarantined files</span></span>

1. <span data-ttu-id="cf9c5-232">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-232">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cf9c5-233">検疫された**ビュー**を既定値**ファイル**に変更します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-233">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="cf9c5-234">利用可能な列見出しをクリックすることで、フィールドに対して並べ替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-234">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="cf9c5-235">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-235">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cf9c5-236">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-236">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cf9c5-237">既定の列には、アスタリスク () のマークが付いてい <sup>\*</sup> ます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-237">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cf9c5-238">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="cf9c5-238">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-239">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-239">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-240">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-240">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-241">**ファイルの URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-241">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-242">**ファイルサイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-242">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-243">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-243">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-244">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cf9c5-244">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="cf9c5-245">**検出者**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-245">**Detected by**</span></span>

   - <span data-ttu-id="cf9c5-246">**時間で変更**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-246">**Modified by time**</span></span>

4. <span data-ttu-id="cf9c5-247">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-247">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cf9c5-248">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-248">The available filters are:</span></span>

   - <span data-ttu-id="cf9c5-249">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-249">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="cf9c5-250">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-250">**Today**</span></span>

     - <span data-ttu-id="cf9c5-251">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-251">**Next 2 days**</span></span>

     - <span data-ttu-id="cf9c5-252">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-252">**Next 7 days**</span></span>

     - <span data-ttu-id="cf9c5-253">カスタムの日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-253">A custom date/time range.</span></span>

   - <span data-ttu-id="cf9c5-254">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-254">**Received time**</span></span>

   - <span data-ttu-id="cf9c5-255">**検疫の理由**: 使用できる値は**マルウェア**のみです。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-255">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="cf9c5-256">特定の検疫済みファイルを見つけたら、そのファイルを選択して、そのファイルに関する詳細を表示し、操作を行います (たとえば、メッセージの表示、リリース、ダウンロード、または削除)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-256">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="cf9c5-257">ファイルエクスポートの結果</span><span class="sxs-lookup"><span data-stu-id="cf9c5-257">Export file results</span></span>

1. <span data-ttu-id="cf9c5-258">目的のファイルを選択し、[結果の**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-258">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="cf9c5-259">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-259">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="cf9c5-260">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-260">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="cf9c5-261">検疫されたファイルの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="cf9c5-261">View quarantined file details</span></span>

<span data-ttu-id="cf9c5-262">一覧でファイルを選択すると、次のファイルの詳細が**詳細**のポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-262">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cf9c5-263">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-263">**File Name**</span></span>

- <span data-ttu-id="cf9c5-264">**ファイルの url**: ファイルの場所を定義する Url (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-264">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="cf9c5-265">**検出された悪意のあるコンテンツ**ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-265">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="cf9c5-266">**Expires**: ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-266">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="cf9c5-267">[**検出者**]: ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジン。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-267">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="cf9c5-268">**[解放済み?]**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-268">**Released?**</span></span>

- <span data-ttu-id="cf9c5-269">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-269">**Malware Name**</span></span>

- <span data-ttu-id="cf9c5-270">**ドキュメント ID**: ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-270">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="cf9c5-271">**ファイルサイズ**: キロバイト (kb) 単位。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-271">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="cf9c5-272">**組織**組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-272">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="cf9c5-273">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-273">**Last modified**</span></span>

- <span data-ttu-id="cf9c5-274">**更新**者: ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-274">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="cf9c5-275">**Secure Hash Algorithm 256 ビット (SHA-256) 値**: このハッシュ値を使用して、他の評価ストアまたは環境内の他の場所にあるファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-275">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="cf9c5-276">検疫されたファイルに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-276">Take action on quarantined files</span></span>

<span data-ttu-id="cf9c5-277">リスト内のファイルを選択すると、[**詳細**] ポップアップウィンドウでファイルに対して次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-277">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cf9c5-278">[**ファイルの解放**]: 選択 (既定) またはレポートファイルの選択解除を**分析のために Microsoft に**、[ファイルの**解放**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-278">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="cf9c5-279">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-279">**Download file**</span></span>

- <span data-ttu-id="cf9c5-280">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-280">**Remove file from quarantine**</span></span>

<span data-ttu-id="cf9c5-281">ファイルを解放または削除しない場合は、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-281">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="cf9c5-282">複数の検疫されたファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="cf9c5-282">Actions on multiple quarantined files</span></span>

<span data-ttu-id="cf9c5-283">リスト内の複数の検疫済みファイル (最大 100) を選択すると、[**一括操作**のポップアップ] ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-283">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cf9c5-284">**ファイルを解放する**</span><span class="sxs-lookup"><span data-stu-id="cf9c5-284">**Release files**</span></span>

- <span data-ttu-id="cf9c5-285">**ファイルの削除**: 表示される警告で [**はい**] をクリックすると、ファイルがすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-285">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="cf9c5-286">組織内のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、サインインし、[セキュリティ & コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-286">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="cf9c5-287">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して、検疫済みメッセージおよびファイルを表示および管理する</span><span class="sxs-lookup"><span data-stu-id="cf9c5-287">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="cf9c5-288">検疫内のメッセージおよびファイルを表示および管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-288">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="cf9c5-289">Get-quarantinemessage を削除します。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-289">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="cf9c5-290">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="cf9c5-290">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="cf9c5-291">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="cf9c5-291">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="cf9c5-292">[Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): このコマンドレットは、メッセージのみを対象としています。このコマンドレットは、SharePoint Online、OneDrive for business、または TEAMS の ATP ファイルではなく、メッセージのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="cf9c5-292">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="cf9c5-293">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="cf9c5-293">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
