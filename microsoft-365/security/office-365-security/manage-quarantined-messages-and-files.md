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
description: 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、および削除できます。 管理者のみが、マルウェア、信頼度の高いフィッシング、またはメールフロールール (トランスポートルール) の結果として検疫されたメッセージを管理できます。
ms.openlocfilehash: 1ae64b71d29f9e2d973f5a73cc19790fe0736913
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635356"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="747e4-104">管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="747e4-104">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="747e4-105">検疫は、exchange online またはスタンドアロンの exchange online Protection (EOP) 組織内のメールボックスを使用して、Microsoft 365 組織で潜在的に危険または不要なメッセージを保持します。 exchange online のメールボックスはありません。</span><span class="sxs-lookup"><span data-stu-id="747e4-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="747e4-106">詳細については、「[Office 365 での検疫](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="747e4-107">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="747e4-108">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="747e4-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="747e4-109">管理者は、誤検知を Microsoft に報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="747e4-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="747e4-110">Office 365 の管理者は、事前脅威保護 (ATP) を使用して、SharePoint Online、OneDrive for Business、Microsoft Teams の検疫されたファイルを表示、ダウンロード、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="747e4-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="747e4-111">検疫済みメッセージを表示して管理するには、セキュリティ & コンプライアンスセンターまたは PowerShell (Microsoft 365 お客様の場合は Exchange Online PowerShell) を使用します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="747e4-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="747e4-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="747e4-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="747e4-113">セキュリティ & コンプライアンスセンターを開くには、に<https://protection.office.com>移動します。</span><span class="sxs-lookup"><span data-stu-id="747e4-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="747e4-114">検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="747e4-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="747e4-115">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="747e4-116">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="747e4-117">管理者として検疫を管理するには、事前にアクセス許可を割り当てる必要があります。アクセス許可は、セキュリティ & コンプライアンスセンターの**検疫**役割によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="747e4-118">既定では、この役割はセキュリティ & コンプライアンスセンターの [**組織の管理**(グローバル管理者)]、[**検疫管理**者]、および [**セキュリティ管理者**] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="747e4-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="747e4-119">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="747e4-120">検疫済みメッセージは、自動的に削除されるまで既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="747e4-121">スパム対策ポリシー (スパム、フィッシング、およびバルクメール) によって検疫されたメッセージ:30 日。</span><span class="sxs-lookup"><span data-stu-id="747e4-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="747e4-122">これは既定値で、最大値です。</span><span class="sxs-lookup"><span data-stu-id="747e4-122">This is the default and maximum value.</span></span> <span data-ttu-id="747e4-123">この値を構成するには、「[スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="747e4-124">組織内のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、サインインし、[セキュリティ & コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="747e4-124">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="747e4-125">マルウェアを含むメッセージ:15 日。</span><span class="sxs-lookup"><span data-stu-id="747e4-125">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="747e4-126">メッセージが検疫の期限切れになると、それを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="747e4-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="747e4-127">セキュリティ & コンプライアンスセンターを使用して検疫された電子メールメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="747e4-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="747e4-128">検疫済みメールを表示する</span><span class="sxs-lookup"><span data-stu-id="747e4-128">View quarantined email</span></span>

1. <span data-ttu-id="747e4-129">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="747e4-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="747e4-130">検疫済み**ビュー**が既定値の**電子メール**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="747e4-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="747e4-131">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="747e4-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="747e4-132">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="747e4-133">既定値にはアスタリスク (<sup>\*</sup>) が付いています。</span><span class="sxs-lookup"><span data-stu-id="747e4-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="747e4-134">**[受信日時]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-134">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-135">**[送信者]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-135">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-136">**[件名]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-136">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-137">**[検疫の理由]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-137">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-138">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-138">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-139">**[ポリシーの種類]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-139">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="747e4-140">組織内のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、サインインし、[セキュリティ & コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="747e4-140">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="747e4-141">**[受信者]**</span><span class="sxs-lookup"><span data-stu-id="747e4-141">**Recipient**</span></span>

   - <span data-ttu-id="747e4-142">**[メッセージ ID]**</span><span class="sxs-lookup"><span data-stu-id="747e4-142">**Message ID**</span></span>

   - <span data-ttu-id="747e4-143">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="747e4-143">**Policy name**</span></span>

   - <span data-ttu-id="747e4-144">**[サイズ]**</span><span class="sxs-lookup"><span data-stu-id="747e4-144">**Size**</span></span>

   - <span data-ttu-id="747e4-145">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="747e4-145">**Direction**</span></span>

   <span data-ttu-id="747e4-146">完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="747e4-147">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="747e4-148">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="747e4-148">The available filters are:</span></span>

   - <span data-ttu-id="747e4-149">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="747e4-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="747e4-150">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="747e4-150">**Today**</span></span>

     - <span data-ttu-id="747e4-151">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="747e4-151">**Next 2 days**</span></span>

     - <span data-ttu-id="747e4-152">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="747e4-152">**Next 7 days**</span></span>

     - <span data-ttu-id="747e4-153">**[カスタム]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="747e4-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="747e4-154">**[受信日時]**: **[開始日]** と **[終了日]** を入力します。</span><span class="sxs-lookup"><span data-stu-id="747e4-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="747e4-155">**[検疫の理由]**:</span><span class="sxs-lookup"><span data-stu-id="747e4-155">**Quarantine reason**:</span></span>

     - <span data-ttu-id="747e4-156">**ポリシー**: メッセージは、メールフロールール (トランスポートルールとも呼ばれます) の条件に一致しました。</span><span class="sxs-lookup"><span data-stu-id="747e4-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="747e4-157">**[バルク]**</span><span class="sxs-lookup"><span data-stu-id="747e4-157">**Bulk**</span></span>

     - <span data-ttu-id="747e4-158">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="747e4-158">**Phish**</span></span>

     - <span data-ttu-id="747e4-159">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="747e4-159">**Malware**</span></span>

     - <span data-ttu-id="747e4-160">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="747e4-160">**Spam**</span></span>

     - <span data-ttu-id="747e4-161">**精度の高いフィッシング**</span><span class="sxs-lookup"><span data-stu-id="747e4-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="747e4-162">**電子メール受信者**: すべてのユーザーまたは自分に送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="747e4-162">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="747e4-163">エンドユーザーは、それらに送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-163">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="747e4-164">フィルターをクリアするには、**[クリア]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-164">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="747e4-165">フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-165">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="747e4-166">**[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="747e4-166">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="747e4-167">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="747e4-167">Wildcards aren't supported.</span></span> <span data-ttu-id="747e4-168">次の値に基づいて検索できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-168">You can search by the following values:</span></span>

   - <span data-ttu-id="747e4-169">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="747e4-169">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="747e4-170">たとえば、[メッセージ追跡](message-trace-scc.md)を使用して、組織内のユーザーに送信されたメッセージを検索したときに、メッセージが配信される代わりに検疫されたことを判断したとします。</span><span class="sxs-lookup"><span data-stu-id="747e4-170">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="747e4-171">山かっこ (\<\>) が含まれる可能性がある完全なメッセージ ID 値を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="747e4-171">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="747e4-172">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="747e4-172">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="747e4-173">**[送信者のメール アドレス]**: 単一の送信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="747e4-173">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="747e4-174">**[受信者のメール アドレス]**: 単一の受信者のメール アドレス。</span><span class="sxs-lookup"><span data-stu-id="747e4-174">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="747e4-175">**[件名]**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="747e4-175">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="747e4-176">この検索では大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="747e4-176">The search is not case-sensitive.</span></span>

   <span data-ttu-id="747e4-177">検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-177">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="747e4-178">特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。</span><span class="sxs-lookup"><span data-stu-id="747e4-178">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="747e4-179">メッセージ結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="747e4-179">Export message results</span></span>

1. <span data-ttu-id="747e4-180">目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-180">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="747e4-181">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-181">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="747e4-182">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-182">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="747e4-183">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="747e4-183">View quarantined message details</span></span>

<span data-ttu-id="747e4-184">一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-184">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="747e4-185">**[メッセージ ID]**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="747e4-185">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="747e4-186">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="747e4-186">**Sender address**</span></span>

- <span data-ttu-id="747e4-187">**[受信日時]**: メッセージを受信した日時。</span><span class="sxs-lookup"><span data-stu-id="747e4-187">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="747e4-188">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="747e4-188">**Subject**</span></span>

- <span data-ttu-id="747e4-189">**検疫理由**: メッセージが**スパム**、 **Bulk**、**フィッシング**、またはメールフロールール (**トランスポートルール**) に一致したか、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="747e4-189">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="747e4-190">**[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="747e4-190">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="747e4-191">**[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。</span><span class="sxs-lookup"><span data-stu-id="747e4-191">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="747e4-192">**[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="747e4-192">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="747e4-193">**[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="747e4-193">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="747e4-194">検疫済みメールを処理する</span><span class="sxs-lookup"><span data-stu-id="747e4-194">Take action on quarantined email</span></span>

<span data-ttu-id="747e4-195">メッセージを選択した後、**詳細**のポップアップウィンドウのメッセージの処理に関するいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="747e4-195">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="747e4-196">**Release message**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="747e4-196">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="747e4-197">[**分析のために Microsoft にメッセージを報告する**]: これは既定でオンになっており、誤って検疫されたメッセージを誤検知として microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="747e4-197">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="747e4-198">メッセージがスパム、バルク、フィッシング、またはマルウェアとして検疫された場合は、メッセージも Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-198">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="747e4-199">分析によっては、サービス全体のスパムフィルタールールが、メッセージを経由して許可されるよう調整される場合があります。</span><span class="sxs-lookup"><span data-stu-id="747e4-199">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="747e4-200">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="747e4-200">Choose one of the following options:</span></span>

    - <span data-ttu-id="747e4-201">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="747e4-201">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="747e4-202">**特定の受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="747e4-202">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="747e4-203">**他のユーザーにメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="747e4-203">**Release messages to other people**</span></span>

  <span data-ttu-id="747e4-204">完了したら、**[メッセージの解放]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-204">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="747e4-205">メッセージの解放に関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="747e4-205">Notes about releasing messages:</span></span>

  - <span data-ttu-id="747e4-206">同じ受信者にメッセージを複数回解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="747e4-206">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="747e4-207">メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-207">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="747e4-208">**[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-208">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="747e4-209">ヘッダーフィールドと値を詳細に分析するには、メッセージヘッダーテキストをクリップボードにコピーし、[ **Microsoft メッセージヘッダーアナライザー** ] を選択してリモート接続アナライザーに移動します (このタスクを完了し365ない場合は、右クリックして [**新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="747e4-209">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="747e4-210">メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="747e4-210">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="747e4-211">**[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="747e4-211">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="747e4-212">**[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="747e4-212">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="747e4-213">**[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。</span><span class="sxs-lookup"><span data-stu-id="747e4-213">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="747e4-214">**検疫から削除**: 表示される警告で [**はい**] をクリックすると、メッセージは元の受信者に送信されることなく、すぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-214">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="747e4-215">**[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。</span><span class="sxs-lookup"><span data-stu-id="747e4-215">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="747e4-216">**メッセージの送信**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="747e4-216">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="747e4-217">**オブジェクトの種類**:**電子メール**(既定)、 **URL**、または**添付ファイル**。</span><span class="sxs-lookup"><span data-stu-id="747e4-217">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="747e4-218">**送信形式**:**ネットワークメッセージ id** (既定では、対応する値が [**ネットワークメッセージ id** ] ボックスに表示されます) または**ファイル**(ローカル .eml または .msg ファイルを参照)。</span><span class="sxs-lookup"><span data-stu-id="747e4-218">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="747e4-219">[**ファイル**] を選択してから [**ネットワークメッセージ ID**] を選択すると、最初の値は失われていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="747e4-219">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="747e4-220">**受信者**: メッセージの元の受信者1人を入力するか、[**すべて選択**] をクリックしてすべての受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="747e4-220">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="747e4-221">[**すべて選択]** をクリックし、個々の受信者を選択的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="747e4-221">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="747e4-222">**送信の理由**: ブロックされて**いない**か (既定)、または**ブロックさ**れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="747e4-222">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="747e4-223">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-223">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="747e4-224">メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="747e4-225">複数の検疫済みメール メッセージを処理する</span><span class="sxs-lookup"><span data-stu-id="747e4-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="747e4-226">一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="747e4-227">**[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="747e4-228">**[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。</span><span class="sxs-lookup"><span data-stu-id="747e4-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="747e4-229">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-229">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="747e4-230">ATP のみ: セキュリティ & コンプライアンスセンターを使用して検疫されたファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="747e4-230">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="747e4-231">このセクションの検疫ファイルの手順は、ATP Plan 1 および Plan 2 のサブスクライバーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-231">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="747e4-232">ATP を使用している組織では、管理者は SharePoint Online、OneDrive for Business、Microsoft Teams で検疫されたファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-232">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="747e4-233">検疫されたファイルの表示</span><span class="sxs-lookup"><span data-stu-id="747e4-233">View quarantined files</span></span>

1. <span data-ttu-id="747e4-234">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="747e4-234">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="747e4-235">検疫された**ビュー**を既定値**ファイル**に変更します。</span><span class="sxs-lookup"><span data-stu-id="747e4-235">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="747e4-236">利用可能な列見出しをクリックすることで、フィールドに対して並べ替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="747e4-236">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="747e4-237">使用できる列見出しをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="747e4-237">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="747e4-238">**[列の変更]** をクリックして、最大で 7 列まで表示できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-238">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="747e4-239">既定の列には、アスタリスク (<sup>\*</sup>) のマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="747e4-239">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="747e4-240">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="747e4-240">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-241">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-241">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-242">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-242">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-243">**ファイルの URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-243">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-244">**ファイルサイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-244">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-245">**[有効期限]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-245">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-246">**[解放済み?]**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="747e4-246">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="747e4-247">**検出者**</span><span class="sxs-lookup"><span data-stu-id="747e4-247">**Detected by**</span></span>

   - <span data-ttu-id="747e4-248">**時間で変更**</span><span class="sxs-lookup"><span data-stu-id="747e4-248">**Modified by time**</span></span>

4. <span data-ttu-id="747e4-249">結果をフィルター処理するには、**[フィルター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-249">To filter the results, click **Filter**.</span></span> <span data-ttu-id="747e4-250">使用できるフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="747e4-250">The available filters are:</span></span>

   - <span data-ttu-id="747e4-251">**[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="747e4-251">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="747e4-252">**[今日]**</span><span class="sxs-lookup"><span data-stu-id="747e4-252">**Today**</span></span>

     - <span data-ttu-id="747e4-253">**[今後 2 日間]**</span><span class="sxs-lookup"><span data-stu-id="747e4-253">**Next 2 days**</span></span>

     - <span data-ttu-id="747e4-254">**[今後 7 日間]**</span><span class="sxs-lookup"><span data-stu-id="747e4-254">**Next 7 days**</span></span>

     - <span data-ttu-id="747e4-255">カスタムの日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="747e4-255">A custom date/time range.</span></span>

   - <span data-ttu-id="747e4-256">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="747e4-256">**Received time**</span></span>

   - <span data-ttu-id="747e4-257">**検疫の理由**: 使用できる値は**マルウェア**のみです。</span><span class="sxs-lookup"><span data-stu-id="747e4-257">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="747e4-258">特定の検疫済みファイルを見つけたら、そのファイルを選択して、そのファイルに関する詳細を表示し、操作を行います (たとえば、メッセージの表示、リリース、ダウンロード、または削除)。</span><span class="sxs-lookup"><span data-stu-id="747e4-258">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="747e4-259">ファイルエクスポートの結果</span><span class="sxs-lookup"><span data-stu-id="747e4-259">Export file results</span></span>

1. <span data-ttu-id="747e4-260">目的のファイルを選択し、[結果の**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-260">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="747e4-261">ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-261">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="747e4-262">エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-262">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="747e4-263">検疫されたファイルの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="747e4-263">View quarantined file details</span></span>

<span data-ttu-id="747e4-264">一覧でファイルを選択すると、次のファイルの詳細が**詳細**のポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-264">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="747e4-265">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="747e4-265">**File Name**</span></span>

- <span data-ttu-id="747e4-266">**ファイルの url**: ファイルの場所を定義する Url (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="747e4-266">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="747e4-267">**検出された悪意のあるコンテンツ**ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="747e4-267">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="747e4-268">**Expires**: ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="747e4-268">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="747e4-269">[**検出者**]: ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジン。</span><span class="sxs-lookup"><span data-stu-id="747e4-269">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="747e4-270">**[解放済み?]**</span><span class="sxs-lookup"><span data-stu-id="747e4-270">**Released?**</span></span>

- <span data-ttu-id="747e4-271">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="747e4-271">**Malware Name**</span></span>

- <span data-ttu-id="747e4-272">**ドキュメント ID**: ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="747e4-272">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="747e4-273">**ファイルサイズ**: キロバイト (kb) 単位。</span><span class="sxs-lookup"><span data-stu-id="747e4-273">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="747e4-274">**組織**組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="747e4-274">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="747e4-275">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="747e4-275">**Last modified**</span></span>

- <span data-ttu-id="747e4-276">**更新**者: ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="747e4-276">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="747e4-277">**Secure Hash Algorithm 256 ビット (SHA-256) 値**: このハッシュ値を使用して、他の評価ストアまたは環境内の他の場所にあるファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-277">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="747e4-278">検疫されたファイルに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="747e4-278">Take action on quarantined files</span></span>

<span data-ttu-id="747e4-279">リスト内のファイルを選択すると、[**詳細**] ポップアップウィンドウでファイルに対して次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-279">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="747e4-280">[**ファイルの解放**]: 選択 (既定) またはレポートファイルの選択解除を**分析のために Microsoft に**、[ファイルの**解放**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="747e4-280">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="747e4-281">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="747e4-281">**Download file**</span></span>

- <span data-ttu-id="747e4-282">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="747e4-282">**Remove file from quarantine**</span></span>

<span data-ttu-id="747e4-283">ファイルを解放または削除しない場合は、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-283">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="747e4-284">複数の検疫されたファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="747e4-284">Actions on multiple quarantined files</span></span>

<span data-ttu-id="747e4-285">リスト内の複数の検疫済みファイル (最大 100) を選択すると、[**一括操作**のポップアップ] ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="747e4-285">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="747e4-286">**ファイルを解放する**</span><span class="sxs-lookup"><span data-stu-id="747e4-286">**Release files**</span></span>

- <span data-ttu-id="747e4-287">**ファイルの削除**: 表示される警告で [**はい**] をクリックすると、ファイルがすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="747e4-287">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="747e4-288">組織内のグローバル管理者特権 (または適切なセキュリティ & コンプライアンスセンターの役割) を持つ職場または学校のアカウントを使用して、サインインし、[セキュリティ & コンプライアンスセンターに移動](../../compliance/go-to-the-securitycompliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="747e4-288">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="747e4-289">Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell を使用して、検疫されたメッセージとファイルを表示および管理する</span><span class="sxs-lookup"><span data-stu-id="747e4-289">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="747e4-290">検疫内のメッセージおよびファイルを表示および管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="747e4-290">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="747e4-291">Get-quarantinemessage を削除します。</span><span class="sxs-lookup"><span data-stu-id="747e4-291">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="747e4-292">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="747e4-292">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="747e4-293">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="747e4-293">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="747e4-294">[Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): このコマンドレットは、メッセージのみを対象としています。このコマンドレットは、SharePoint Online、OneDrive for business、または TEAMS の ATP ファイルではなく、メッセージのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="747e4-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="747e4-295">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="747e4-295">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
