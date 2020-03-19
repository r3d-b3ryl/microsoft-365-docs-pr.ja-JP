---
title: Office 365 の管理者として検疫済みメッセージおよびファイルを管理する
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
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857075"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="0e4dd-104">Office 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="0e4dd-105">検疫は、exchange online またはスタンドアロンの exchange online Protection (EOP) 組織内のメールボックスを使用する Office 365 組織で潜在的に危険または不要なメッセージを保持します。 exchange online メールボックスはありません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="0e4dd-106">詳細については、「 [Quarantine In Office 365](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="0e4dd-107">管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="0e4dd-108">マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを管理できるのは、管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="0e4dd-109">管理者は、誤検知を Microsoft に報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="0e4dd-110">Office 365 の管理者は、事前脅威保護 (ATP) を使用して、SharePoint Online、OneDrive for Business、Microsoft Teams の検疫されたファイルを表示、ダウンロード、および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="0e4dd-111">検疫済みメッセージを表示して管理するには、セキュリティ & コンプライアンスセンターまたは PowerShell (Office 365 お客様の場合は Exchange Online PowerShell) を使用します。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0e4dd-112">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0e4dd-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0e4dd-113">Office 365 セキュリティ & コンプライアンスセンターを開くには、に<https://protection.office.com>移動します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="0e4dd-114">[検疫] ページを直接開くには<https://protection.office.com/quarantine>、に移動します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="0e4dd-115">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0e4dd-116">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0e4dd-117">管理者として検疫を管理するには、事前にアクセス許可を割り当てる必要があります。アクセス許可は、セキュリティ & コンプライアンスセンターの**検疫**役割によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="0e4dd-118">既定では、この役割はセキュリティ & コンプライアンスセンターの [**組織の管理**(グローバル管理者)]、[**検疫管理**者]、および [**セキュリティ管理者**] 役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="0e4dd-119">詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0e4dd-120">検疫済みメッセージは、自動的に削除されるまで既定の期間保持されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="0e4dd-121">スパム対策ポリシー (スパム、フィッシング、およびバルクメール) によって検疫されたメッセージ:30 日。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="0e4dd-122">これは既定値で、最大値です。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-122">This is the default and maximum value.</span></span> <span data-ttu-id="0e4dd-123">この値を構成するには、「 [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="0e4dd-124">メールフロールールによって検疫されるメッセージ (ルールの処理は、ホストされた**検疫にメッセージを配信する**):30 日。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="0e4dd-125">この値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-125">You can't change this value.</span></span>

  - <span data-ttu-id="0e4dd-126">マルウェアを含むメッセージ:15 日。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="0e4dd-127">メッセージが検疫の期限切れになると、それを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="0e4dd-128">セキュリティ & コンプライアンスセンターを使用して検疫された電子メールメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="0e4dd-129">検疫済みメールを表示する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-129">View quarantined email</span></span>

1. <span data-ttu-id="0e4dd-130">セキュリティ/コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> ] [**検疫**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="0e4dd-131">検疫済み**ビュー**が既定値の**電子メール**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="0e4dd-132">利用可能な列のヘッダーをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="0e4dd-133">[**列の変更**] をクリックして、最大7つの列を表示します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="0e4dd-134">既定値には、アスタリスク (<sup>\*</sup>) のマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="0e4dd-135">**時**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-136">**者**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-137">**件名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-138">**検疫理由**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-139">**時点?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-140">**ポリシーの種類**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-141">**期限**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-142">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-142">**Recipient**</span></span>

   - <span data-ttu-id="0e4dd-143">**メッセージ ID**   メッセージのヘッダーに「メッセージ ID:」で表示されるインターネット メッセージ ID (クライアント ID とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-143">**Message ID**</span></span>

   - <span data-ttu-id="0e4dd-144">**[ポリシー名]**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-144">**Policy name**</span></span>

   - <span data-ttu-id="0e4dd-145">**Size**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-145">**Size**</span></span>

   - <span data-ttu-id="0e4dd-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-146">**Direction**</span></span>

   <span data-ttu-id="0e4dd-147">完了したら、[**保存**] をクリックするか、[**既定に設定] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="0e4dd-148">結果をフィルター処理するには、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="0e4dd-149">使用可能なフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-149">The available filters are:</span></span>

   - <span data-ttu-id="0e4dd-150">**期限切れ時刻**: 検疫の期限が切れるまでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="0e4dd-151">**本日は**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-151">**Today**</span></span>

     - <span data-ttu-id="0e4dd-152">**次の2日**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-152">**Next 2 days**</span></span>

     - <span data-ttu-id="0e4dd-153">**次の7日間**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-153">**Next 7 days**</span></span>

     - <span data-ttu-id="0e4dd-154">**Custom**:**開始日**と**終了日**を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0e4dd-155">[**受信時刻**]:**開始日**と**終了日**を入力します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="0e4dd-156">**検疫理由**:</span><span class="sxs-lookup"><span data-stu-id="0e4dd-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="0e4dd-157">**ポリシー**: メッセージは、メールフロールール (トランスポートルールとも呼ばれます) の条件に一致しました。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="0e4dd-158">**バルク**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-158">**Bulk**</span></span>

     - <span data-ttu-id="0e4dd-159">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-159">**Phish**</span></span>

     - <span data-ttu-id="0e4dd-160">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-160">**Malware**</span></span>

     - <span data-ttu-id="0e4dd-161">**スパム**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-161">**Spam**</span></span>

     - <span data-ttu-id="0e4dd-162">**精度の高いフィッシング**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="0e4dd-163">**電子メール受信者**: すべてのユーザーまたは自分に送信されたメッセージのみ。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="0e4dd-164">エンドユーザーは、それらに送信された検疫済みメッセージのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="0e4dd-165">フィルターをクリアするには、[**クリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="0e4dd-166">フィルターのポップアップを非表示にするには、[**フィルター** ] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="0e4dd-167">[**結果の並べ替え**] (既定では、[**メッセージ ID** ] ボタン) を使用し、特定のメッセージを検索するための対応する値を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="0e4dd-168">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-168">Wildcards aren't supported.</span></span> <span data-ttu-id="0e4dd-169">次の値で検索できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-169">You can search by the following values:</span></span>

   - <span data-ttu-id="0e4dd-170">**メッセージ ID**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="0e4dd-171">たとえば、[メッセージ追跡](message-trace-scc.md)を使用して、組織内のユーザーに送信されたメッセージを検索したときに、メッセージが配信される代わりに検疫されたことを判断したとします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="0e4dd-172">山かっこ (\<\>) が含まれる可能性がある完全なメッセージ ID 値を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="0e4dd-173">例: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="0e4dd-174">**送信者の電子メールアドレス**: 1 人の送信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="0e4dd-175">**受信者の電子メールアドレス**: 単一の受信者の電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="0e4dd-176">**件名**: メッセージの件名全体を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="0e4dd-177">検索では大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="0e4dd-178">検索条件を入力した後、[ ![更新]](../media/scc-quarantine-refresh.png)ボタンの [**更新**] をクリックして結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="0e4dd-179">特定の検疫済みメッセージを見つけた後、メッセージを選択してそのメッセージに関する詳細を表示し、アクションを実行します (たとえば、メッセージの表示、リリース、ダウンロード、または削除)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="0e4dd-180">メッセージの結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0e4dd-180">Export message results</span></span>

1. <span data-ttu-id="0e4dd-181">目的のメッセージを選択し、[結果の**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="0e4dd-182">ブラウザーウィンドウを開いたままにしておくように警告する確認メッセージで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="0e4dd-183">エクスポートの準備ができたら、.csv ファイルのダウンロード場所を名前を指定して選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="0e4dd-184">検疫済みメッセージの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-184">View quarantined message details</span></span>

<span data-ttu-id="0e4dd-185">一覧で電子メールメッセージを選択すると、**詳細**のポップアップウィンドウに次のメッセージの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0e4dd-186">**メッセージ ID**: メッセージのグローバル一意識別子。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="0e4dd-187">**送信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-187">**Sender address**</span></span>

- <span data-ttu-id="0e4dd-188">**Received**: メッセージが受信された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="0e4dd-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-189">**Subject**</span></span>

- <span data-ttu-id="0e4dd-190">**検疫理由**: メッセージが**スパム**、 **Bulk**、**フィッシング**、またはメールフロールール (**トランスポートルール**) に一致したか、または**マルウェア**が含まれていると識別されたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="0e4dd-191">**受信者**: メッセージに複数の受信者が含まれている場合は、[メッセージの**プレビュー** ] または [**メッセージヘッダーの表示**] をクリックして、受信者の完全な一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="0e4dd-192">[**有効期限**]: メッセージが自動的に削除され、検疫から完全に削除される日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="0e4dd-193">[**解放済み**] メッセージが解放されたすべてのメール アドレス (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="0e4dd-194">まだリリースされて**いない**: メッセージがまだ解放されていないすべての電子メールアドレス (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="0e4dd-195">検疫済みメールに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-195">Take action on quarantined email</span></span>

<span data-ttu-id="0e4dd-196">メッセージを選択した後、**詳細**のポップアップウィンドウのメッセージの処理に関するいくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0e4dd-197">**Release message**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="0e4dd-198">[**分析のために Microsoft にメッセージを報告する**]: これは既定でオンになっており、誤って検疫されたメッセージを誤検知として microsoft に報告します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="0e4dd-199">メッセージがスパム、バルク、フィッシング、またはマルウェアとして検疫された場合は、メッセージも Microsoft スパム分析チームに報告されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="0e4dd-200">分析によっては、サービス全体のスパムフィルタールールが、メッセージを経由して許可されるよう調整される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="0e4dd-201">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="0e4dd-202">**すべての受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="0e4dd-203">**特定の受信者にメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="0e4dd-204">**他のユーザーにメッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-204">**Release messages to other people**</span></span>

  <span data-ttu-id="0e4dd-205">完了したら、[**メッセージの解放**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="0e4dd-206">メッセージの解放に関する注意事項:</span><span class="sxs-lookup"><span data-stu-id="0e4dd-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="0e4dd-207">同じ受信者にメッセージを複数回解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="0e4dd-208">メッセージを受信していない受信者のみが、潜在的な受信者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="0e4dd-209">**メッセージヘッダーを表示**する: メッセージヘッダーのテキストを表示するには、このリンクを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="0e4dd-210">ヘッダーフィールドと値を詳細に分析するには、メッセージヘッダーテキストをクリップボードにコピーしてから、[ **Microsoft メッセージヘッダーアナライザー** ] を選択してリモート接続アナライザーに移動します (このタスクを完了させたく365ない場合は、右クリックして [**新しいタブで開く]** を選択します)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="0e4dd-211">メッセージヘッダーを [メッセージヘッダーアナライザー] セクションのページに貼り付け、[**ヘッダーの分析**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="0e4dd-212">**メッセージのプレビュー**: 表示されるフライアウトウィンドウで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="0e4dd-213">**ソースビュー**: すべてのリンクが無効で、メッセージ本文の HTML バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="0e4dd-214">**テキストビュー**: メッセージ本文をテキスト形式で表示します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="0e4dd-215">**検疫から削除**: 表示される警告で [**はい**] をクリックすると、メッセージは元の受信者に送信されることなく、すぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="0e4dd-216">**メッセージのダウンロード**: 表示されるフライアウトウィンドウで、[このメッセージをダウンロードすることに**よるリスクを理解**する] を選択して、.eml 形式でメッセージのローカルコピーを保存します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="0e4dd-217">**メッセージの送信**: 表示されるフライアウトウィンドウで、次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="0e4dd-218">**オブジェクトの種類**:**電子メール**(既定)、 **URL**、または**添付ファイル**。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="0e4dd-219">**送信形式**:**ネットワークメッセージ id** (既定では、対応する値が [**ネットワークメッセージ id** ] ボックスに表示されます) または**ファイル**(ローカル .eml または .msg ファイルを参照)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="0e4dd-220">[**ファイル**] を選択してから [**ネットワークメッセージ ID**] を選択すると、最初の値は失われていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="0e4dd-221">**受信者**: メッセージの元の受信者1人を入力するか、[**すべて選択**] をクリックしてすべての受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="0e4dd-222">[**すべて選択]** をクリックし、個々の受信者を選択的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="0e4dd-223">**送信の理由**: ブロックされて**いない**か (既定)、または**ブロックさ**れている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="0e4dd-224">完了したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="0e4dd-225">メッセージを解放または削除しない場合は、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="0e4dd-226">複数の検疫済みメールメッセージに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="0e4dd-227">リスト内の複数の検疫済みメッセージを選択すると (最大 100)、次の操作を行うことができる [**一括操作**] ポップアップウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="0e4dd-228">[**メッセージの解放**]: 特定の**受信者にメッセージを解放**することはできませんが、1つのメッセージを解放する場合と同じです。[**すべての受信者にメッセージを解放**する] または [**他のユーザーにメッセージを解放**する] のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="0e4dd-229">**メッセージの削除**: 表示される警告で [**はい**] をクリックすると、メッセージは元の受信者に送信されることなく、すぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="0e4dd-230">完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="0e4dd-231">ATP のみ: セキュリティ & コンプライアンスセンターを使用して検疫されたファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="0e4dd-232">このセクションの検疫ファイルの手順は、ATP Plan 1 および Plan 2 のサブスクライバーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="0e4dd-233">ATP を使用している組織では、管理者は SharePoint Online、OneDrive for Business、Microsoft Teams で検疫されたファイルを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="0e4dd-234">検疫されたファイルの表示</span><span class="sxs-lookup"><span data-stu-id="0e4dd-234">View quarantined files</span></span>

1. <span data-ttu-id="0e4dd-235">セキュリティ/コンプライアンスセンターで、[**脅威管理** \>の**レビュー** \> ] [**検疫**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="0e4dd-236">検疫された**ビュー**を既定値**ファイル**に変更します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="0e4dd-237">利用可能な列見出しをクリックすることで、フィールドに対して並べ替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="0e4dd-238">利用可能な列のヘッダーをクリックすると、結果を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="0e4dd-239">[**列の変更**] をクリックして、最大7つの列を表示します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="0e4dd-240">既定の列には、アスタリスク (<sup>\*</sup>) のマークが付いています。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="0e4dd-241">[**User**<sup>\*</sup>]</span><span class="sxs-lookup"><span data-stu-id="0e4dd-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-242">**位置**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-243">**ファイル名**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-244">**ファイルの URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-245">**ファイルサイズ**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-246">**期限**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-247">**時点?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0e4dd-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="0e4dd-248">**検出者**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-248">**Detected by**</span></span>

   - <span data-ttu-id="0e4dd-249">**時間で変更**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-249">**Modified by time**</span></span>

4. <span data-ttu-id="0e4dd-250">結果をフィルター処理するには、[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="0e4dd-251">使用可能なフィルターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-251">The available filters are:</span></span>

   - <span data-ttu-id="0e4dd-252">**期限切れ時刻**: 検疫の期限が切れるまでメッセージをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="0e4dd-253">**本日は**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-253">**Today**</span></span>

     - <span data-ttu-id="0e4dd-254">**次の2日**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-254">**Next 2 days**</span></span>

     - <span data-ttu-id="0e4dd-255">**次の7日間**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-255">**Next 7 days**</span></span>

     - <span data-ttu-id="0e4dd-256">カスタムの日付/時刻範囲。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-256">A custom date/time range.</span></span>

   - <span data-ttu-id="0e4dd-257">**受信時刻**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-257">**Received time**</span></span>

   - <span data-ttu-id="0e4dd-258">**検疫の理由**: 使用できる値は**マルウェア**のみです。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="0e4dd-259">特定の検疫済みファイルを見つけたら、そのファイルを選択して、そのファイルに関する詳細を表示し、操作を行います (たとえば、メッセージの表示、リリース、ダウンロード、または削除)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="0e4dd-260">ファイルエクスポートの結果</span><span class="sxs-lookup"><span data-stu-id="0e4dd-260">Export file results</span></span>

1. <span data-ttu-id="0e4dd-261">目的のファイルを選択し、[結果の**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="0e4dd-262">ブラウザーウィンドウを開いたままにしておくように警告する確認メッセージで、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="0e4dd-263">エクスポートの準備ができたら、.csv ファイルのダウンロード場所を名前を指定して選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="0e4dd-264">検疫されたファイルの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="0e4dd-264">View quarantined file details</span></span>

<span data-ttu-id="0e4dd-265">一覧でファイルを選択すると、次のファイルの詳細が**詳細**のポップアップウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0e4dd-266">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-266">**File Name**</span></span>

- <span data-ttu-id="0e4dd-267">**ファイルの url**: ファイルの場所を定義する Url (SharePoint Online など)。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="0e4dd-268">**検出された悪意のあるコンテンツ**ファイルが検疫された日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="0e4dd-269">**Expires**: ファイルが検疫から削除される日付。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="0e4dd-270">[**検出者**]: ATP (Advanced Threat Protection) または Microsoft のマルウェア対策エンジン。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="0e4dd-271">**時点?**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-271">**Released?**</span></span>

- <span data-ttu-id="0e4dd-272">**マルウェアの名前**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-272">**Malware Name**</span></span>

- <span data-ttu-id="0e4dd-273">**ドキュメント ID**: ドキュメントの一意識別子。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="0e4dd-274">**ファイルサイズ**: キロバイト (kb) 単位。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="0e4dd-275">**組織**組織の一意の ID。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="0e4dd-276">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-276">**Last modified**</span></span>

- <span data-ttu-id="0e4dd-277">**更新**者: ファイルを最後に変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="0e4dd-278">**Secure Hash Algorithm 256 ビット (SHA-256) 値**: このハッシュ値を使用して、他の評価ストアまたは環境内の他の場所にあるファイルを識別できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="0e4dd-279">検疫されたファイルに対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-279">Take action on quarantined files</span></span>

<span data-ttu-id="0e4dd-280">リスト内のファイルを選択すると、[**詳細**] ポップアップウィンドウでファイルに対して次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="0e4dd-281">[**ファイルの解放**]: 選択 (既定) またはレポートファイルの選択解除を**分析のために Microsoft に**、[ファイルの**解放**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="0e4dd-282">**ファイルをダウンロードする**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-282">**Download file**</span></span>

- <span data-ttu-id="0e4dd-283">**検疫からファイルを削除する**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="0e4dd-284">ファイルを解放または削除しない場合は、既定の検疫保持期間が経過した後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="0e4dd-285">複数の検疫されたファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="0e4dd-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="0e4dd-286">リスト内の複数の検疫済みファイル (最大 100) を選択すると、[**一括操作**のポップアップ] ウィンドウが表示され、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="0e4dd-287">**ファイルを解放する**</span><span class="sxs-lookup"><span data-stu-id="0e4dd-287">**Release files**</span></span>

- <span data-ttu-id="0e4dd-288">**ファイルの削除**: 表示される警告で [**はい**] をクリックすると、ファイルがすぐに削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="0e4dd-289">完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="0e4dd-290">Exchange Online PowerShell またはスタンドアロン Exchange Online Protection PowerShell を使用して、検疫されたメッセージとファイルを表示および管理する</span><span class="sxs-lookup"><span data-stu-id="0e4dd-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="0e4dd-291">検疫内のメッセージおよびファイルを表示および管理するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="0e4dd-292">Get-quarantinemessage を削除します。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="0e4dd-293">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="0e4dd-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="0e4dd-294">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="0e4dd-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="0e4dd-295">[Get-quarantinemessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): このコマンドレットは、メッセージのみを対象としています。このコマンドレットは、SharePoint Online、OneDrive for business、または TEAMS の ATP ファイルではなく、メッセージのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="0e4dd-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="0e4dd-296">Get-quarantinemessage</span><span class="sxs-lookup"><span data-stu-id="0e4dd-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
