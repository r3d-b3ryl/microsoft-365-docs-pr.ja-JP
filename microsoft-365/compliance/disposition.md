---
title: コンテンツの処理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 処理確認を利用する場合や、レコードとしてマークされたアイテムが構成した設定に従って自動的に削除される場合、コンテンツの処理を監視および管理します。
ms.openlocfilehash: 577cf25ffc8735be19434496bd16202a8e383761
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878126"
---
# <a name="disposition-of-content"></a><span data-ttu-id="f1432-103">コンテンツの処理</span><span class="sxs-lookup"><span data-stu-id="f1432-103">Disposition of content</span></span>

><span data-ttu-id="f1432-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="f1432-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="f1432-105">Microsoft 365 コンプライアンス センターの **レコード管理** の [**処理**] タブを使用して、処理確認を管理し、保持期間の終了時に自動的に削除された [レコード](records-management.md#records)のメタデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-105">Use the **Disposition** page from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view the metadata of [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span>

> [!NOTE]
> <span data-ttu-id="f1432-106">プレビューで: **マルチステージの処理確認**</span><span class="sxs-lookup"><span data-stu-id="f1432-106">In preview: **multi-stage disposition review**</span></span>
> 
> <span data-ttu-id="f1432-107">管理者は保持ラベルに最大 5 つの連続する処理確認ステージを追加し、確認担当者は他のユーザーを処理確認ステージに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f1432-107">An administrator can now add up to five consecutive stages of disposition review in a retention label, and reviewers can add others users to their disposition review stage.</span></span> <span data-ttu-id="f1432-108">メールの通知とアラームをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-108">You can also customize the email notifications and reminders.</span></span> <span data-ttu-id="f1432-109">次のセクションでは、このプレビューでの変更点を詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f1432-109">The following sections have more information about the changes in this preview.</span></span>
>
> <span data-ttu-id="f1432-110">リリースのお知らせは、ブログ記事「[Microsoft レコード管理でのマルチステージ処理のお知らせ](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-multi-stage-disposition-in-microsoft-records/ba-p/2361849)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1432-110">To read the release announcement, see the blog post [Announcing Multi-Stage Disposition in Microsoft Records Management](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-multi-stage-disposition-in-microsoft-records/ba-p/2361849).</span></span>

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="f1432-111">コンテンツの処理を表示するための前提条件</span><span class="sxs-lookup"><span data-stu-id="f1432-111">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="f1432-112">処理確認を管理し、レコードが削除されたことを確認するには、十分なアクセス許可があり、監査が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1432-112">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span> <span data-ttu-id="f1432-113">また、処理の[制限](retention-limits.md#maximum-number-of-items-for-disposition)にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-113">Also be aware of any [limitations](retention-limits.md#maximum-number-of-items-for-disposition) for disposition.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="f1432-114">処理のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f1432-114">Permissions for disposition</span></span>

<span data-ttu-id="f1432-115">Microsoft 365 コンプライアンス センターの [**処理**] タブに正常にアクセスするには、ユーザーは **処理管理** の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1432-115">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role.</span></span> <span data-ttu-id="f1432-116">2020 年 12 月より、この役割は、**レコード管理** の既定の管理者の役割グループに含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f1432-116">From December 2020, this role is now included in the **Records Management** default role group.</span></span>

> [!NOTE]
> <span data-ttu-id="f1432-117">既定で、グローバル管理者には **処理管理** の役割は付与されません。</span><span class="sxs-lookup"><span data-stu-id="f1432-117">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="f1432-118">ユーザーに、保持およびレコード管理用の他の機能を表示および構成するためのアクセス許可を付与せずに、処理確認に必要なアクセス許可のみを付与するには、カスタムの役割グループ (たとえば、"処理確認" という名前) を作成して、このグループに **処理管理** の役割を付与します。</span><span class="sxs-lookup"><span data-stu-id="f1432-118">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the **Disposition Management** role.</span></span>

<span data-ttu-id="f1432-119">これらのアクセス許可を構成する手順については、「[Office 365 セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1432-119">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f1432-120">さらに:</span><span class="sxs-lookup"><span data-stu-id="f1432-120">Additionally:</span></span>

- <span data-ttu-id="f1432-121">さらに、処理プロセス中にアイテムの内容を表示するには、**コンテンツ エクスプローラーのコンテンツ閲覧者** の役割グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f1432-121">To view the contents of items during the disposition process, add users to the **Content Explorer Content Viewer** role group.</span></span> <span data-ttu-id="f1432-122">ユーザーがこれらの役割グループのアクセス許可を持っていない場合でも、処理確認操作を選択して処理確認を完了することができますが、コンプライアンス センターのプレビュー ウィンドウからアイテムのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1432-122">If users don't have the permissions from this role group, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the mini-preview pane in the compliance center.</span></span>

- <span data-ttu-id="f1432-123">プレビューの場合: 既定では、[**処理]** ページにアクセス する人は、自分に確認が割り当てられているアイテムだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-123">In preview: By default, each person that accesses the **Disposition** page sees only items that they are assigned to review.</span></span> <span data-ttu-id="f1432-124">すべてのユーザーに割り当てられているすべてのアイテムを表示し、処理確認で構成されているすべての保持ラベルを表示できるレコード管理者の場合: **レコード管理設定** > **一般** > **レコード マネージャー向けセキュリティ グループ** に移動し、管理者アカウントを含むメールが有効になっているセキュリティ グループを選択して有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1432-124">For a records management administrator to see all items assigned to all users, and all retention labels that are configured for disposition review: Navigate to **Records management settings** > **General** > **Security group for records manager** to select and then enable a mail-enabled security group that contains the administrator accounts.</span></span>
    
    <span data-ttu-id="f1432-125">メールが有効になっていない Microsoft 365 グループとセキュリティ グループは、この機能をサポートしていないので、選択対象のリストには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1432-125">Microsoft 365 groups and security groups that aren't mail-enabled doesn't support this feature and wouldn't be displayed in the list to select.</span></span> <span data-ttu-id="f1432-126">メールが有効な新しいセキュリティ グループを作成する必要がある場合は、Microsoft 365 管理センターへのリンクを使用して新しいグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1432-126">If you need to create a new mail-enabled security group, use the link to the Microsoft 365 admin center to create the new group.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f1432-127">グループの有効化後は、コンプライアンス センターでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="f1432-127">After you have enabled the group, you can't change it in the compliance center.</span></span> <span data-ttu-id="f1432-128">PowerShell を使用して別のグループを有効にする方法については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-128">See the next section for how to enable a different group by using PowerShell.</span></span>

- <span data-ttu-id="f1432-129">プレビューの場合: [**レコード管理の設定**] オプションは、レコード管理管理者にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-129">In preview: The **Records management settings** option is visible only to record management administrators.</span></span> 

#### <a name="enabling-another-security-group-for-disposition"></a><span data-ttu-id="f1432-130">別のセキュリティ グループの処理を可能にする</span><span class="sxs-lookup"><span data-stu-id="f1432-130">Enabling another security group for disposition</span></span>

<span data-ttu-id="f1432-131">Microsoft 365 コンプライアンス センターの **[レコード管理の設定]** で処理用のセキュリティ グループを有効にした後は、そのグループのこのアクセス許可を無効にしたり、コンプライアンス センターで選択したグループを置き換えたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f1432-131">After you have enabled a security group for disposition from the **Records management settings** in the Microsoft 365 compliance center, you can't disable this permission for the group or replace the selected group in the compliance center.</span></span> <span data-ttu-id="f1432-132">ただし、別のメールが有効なセキュリティ グループを有効にするには、 [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) コマンドレット を使います。</span><span class="sxs-lookup"><span data-stu-id="f1432-132">However, you can enable another mail-enabled security group by using the [Enable-ComplianceTagStorage](/powershell/module/exchange/enable-compliancetagstorage) cmdlet.</span></span>

<span data-ttu-id="f1432-133">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-133">For example:</span></span> 

```PowerShell
Enable-ComplianceTagStorage -RecordsManagementSecurityGroupEmail dispositionreviewers@contosoi.com
````

### <a name="enable-auditing"></a><span data-ttu-id="f1432-134">監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="f1432-134">Enable auditing</span></span>

<span data-ttu-id="f1432-135">最初の処理操作の少なくとも 1 日前に、監査が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-135">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="f1432-136">詳細については、「[Office 365 セキュリティ&amp;コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-136">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="f1432-137">処理確認</span><span class="sxs-lookup"><span data-stu-id="f1432-137">Disposition reviews</span></span>

<span data-ttu-id="f1432-p110">コンテンツがその保存期間の終了に近づいたとき、そのコンテンツを確認して、完全に削除 (「破棄」) できるかどうかを確認する理由はいくつかあります。たとえば、コンテンツを削除する代わりに、次のことを行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1432-p110">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed"). For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="f1432-140">訴訟や監査に備え、関連コンテンツの削除を保留にします。</span><span class="sxs-lookup"><span data-stu-id="f1432-140">Suspend the deletion of relevant content for litigation or an audit.</span></span>

- <span data-ttu-id="f1432-141">元の保持設定が一時的または暫定的な解決策であったためか、コンテンツに異なる保持期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f1432-141">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="f1432-142">たとえば、コンテンツに研究的価値や歴史的価値がある場合は、コンテンツを既存の場所からアーカイブの場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1432-142">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="f1432-143">保持期間の終了時に処理確認がトリガーされた場合:</span><span class="sxs-lookup"><span data-stu-id="f1432-143">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="f1432-144">選択したユーザーの元に、確認するコンテンツを知らせるメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="f1432-144">The reviewers you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="f1432-145">これらの確認担当者は個々のユーザーか、メールが有効なセキュリティ グループです。</span><span class="sxs-lookup"><span data-stu-id="f1432-145">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="f1432-146">プレビューの新機能</span><span class="sxs-lookup"><span data-stu-id="f1432-146">New in preview:</span></span>
   - <span data-ttu-id="f1432-147">確認担当者が受け取るメールは、別の言語の手順も含めてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-147">You can customize the email that they receive, including instructions in different languages.</span></span> <span data-ttu-id="f1432-148">複数言語のサポートを利用するには、翻訳を自分で指定する必要があります。このカスタム テキストは、ロケールに関係なく、すべての確認担当者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-148">For multi-language support, you must specify the translations yourself and this custom text is displayed to all reviewers irrespective of their locale.</span></span>
   - <span data-ttu-id="f1432-149">ユーザーは、アイテムの保持期間の最後に、ラベルごとに最初のメール通知を受け取ります。ラベルごとのリマインダーは、自分に割り当てられているすべての処理確認について、週に 1 回行われます。</span><span class="sxs-lookup"><span data-stu-id="f1432-149">Users receive an initial email notification per label at the end of the item's retention period, with a reminder per label once a week of all disposition reviews that they are assigned.</span></span> <span data-ttu-id="f1432-150">通知メールとリマインダー メール内のリンクをクリックして、Microsoft 365 コンプライアンス センターの [**処理**] ページに移動し、コンテンツを確認して対処します。</span><span class="sxs-lookup"><span data-stu-id="f1432-150">They can click the link in the notification and reminder emails to go to the **Disposition** page in the Microsoft 365 compliance center to review the content and take an action.</span></span> <span data-ttu-id="f1432-151">あるいは、確認担当者はコンプライアンス センターの [**処理**] ページに直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-151">Alternately, the reviewers can go directly to the **Disposition** page in the compliance center.</span></span>
   - <span data-ttu-id="f1432-152">確認担当者には、自分に割り当てられている処理確認だけが表示されます。一方、選択したレコード マネージャー向けのセキュリティ グループに追加された管理者には、すべての処理確認が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-152">Reviewers see only the disposition reviews that are assigned to them, whereas administrators who are added to the selected security group for records manager see all disposition reviews.</span></span>
   - <span data-ttu-id="f1432-153">確認担当者は、同じ処理確認に新しいユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f1432-153">Reviewers can add new users to the same disposition review.</span></span> <span data-ttu-id="f1432-154">現時点では、この操作により、追加されたユーザーにユーザーに、[必要なアクセス許可](#permissions-for-disposition) が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-154">Currently, this action doesn't automatically grant these added users the [required permissions](#permissions-for-disposition).</span></span>
   - <span data-ttu-id="f1432-155">処理確認プロセスでは、各項目のミニ確認ウィンドウに、確認者が表示するアクセス許可のあるコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-155">For the disposition review process, a mini-review pane for each item shows a preview of the content if they have permissions to see it.</span></span> <span data-ttu-id="f1432-156">アクセス許可を持っていない場合は、コンテンツ リンクを選択し、アクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="f1432-156">If they don't have permissions, they can select the content link and request permissions.</span></span> <span data-ttu-id="f1432-157">このミニ確認ウィンドウには、コンテンツに関する追加情報のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="f1432-157">This mini-review pane also has tabs for additional information about the content:</span></span>
       - <span data-ttu-id="f1432-158">インデックス付きプロパティ、場所、作成者、作成日時、最終変更日時を表示する **詳細**。</span><span class="sxs-lookup"><span data-stu-id="f1432-158">**Details** to display indexed properties, where it's located, who created it and when, and who last modified it and when.</span></span>
       - <span data-ttu-id="f1432-159">処理確認操作の現在までを示す履歴と、可能な場合は確認者のコメントを含む **履歴**。</span><span class="sxs-lookup"><span data-stu-id="f1432-159">**History** that shows the history of any disposition review actions to date, with reviewer comments if available.</span></span>

<span data-ttu-id="f1432-160">処理確認には、Exchange メールボックス、SharePoint サイト、OneDrive アカウントを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-160">A disposition review can include content in Exchange mailboxes, SharePoint sites, and OneDrive accounts.</span></span> <span data-ttu-id="f1432-161">以上の場所で処理確認を待っているコンテンツは、処理確認の最終ステージで確認担当者がコンテンツの恒久的な削除を選択しない限り削除されません。</span><span class="sxs-lookup"><span data-stu-id="f1432-161">Content pending a disposition review in those locations is permanently deleted only after a reviewer for the final stage of disposition chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="f1432-162">処理確認をサポートするには、メールボックスに少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1432-162">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="f1432-163">管理者は、[**概要**] タブですべての保留中の処理を表示できます。確認担当者には、処理保留中の項目だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-163">Administrators can see an overview of all pending dispositions in the **Overview** tab. Reviewers see only their items pending disposition.</span></span> <span data-ttu-id="f1432-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-164">For example:</span></span>

![レコード管理の概要で保留中の処理](../media/dispositions-overview.png)

<span data-ttu-id="f1432-166">[**すべての保留中の処理を表示**] を選択すると、[**処理**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-166">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="f1432-167">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-167">For example:</span></span>

![Microsoft365 コンプライアンス センターの [処理] ページ](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="f1432-169">処理確認の流れ</span><span class="sxs-lookup"><span data-stu-id="f1432-169">Workflow for a disposition review</span></span>

<span data-ttu-id="f1432-170">次の図は、保持ラベルが公開され、ユーザーが手動で適用した場合の処理確認の基本的な流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="f1432-170">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="f1432-171">または、処理確認用に構成された保持ラベルをコンテンツに自動適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-171">Alternatively, a retention label configured for a disposition review can be automatically applied to content.</span></span>
  
![処理の流れを示すグラフ](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)

### <a name="how-to-configure-a-retention-label-for-disposition-review"></a><span data-ttu-id="f1432-173">処理レビュー用に保持ラベルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f1432-173">How to configure a retention label for disposition review</span></span>

<span data-ttu-id="f1432-174">保持期間の終了時に処理確認をトリガーすることは、保持ラベルでのみ使用可能な構成オプションです。</span><span class="sxs-lookup"><span data-stu-id="f1432-174">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="f1432-175">このオプションは保持ポリシーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f1432-175">Disposition review is not available for a retention policy.</span></span> <span data-ttu-id="f1432-176">これら 2 つの保持ソリューションの詳細については、「[保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-176">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="f1432-177">保持ラベルの [**保持設定の定義**] ページから:</span><span class="sxs-lookup"><span data-stu-id="f1432-177">From the **Define retention settings** page for a retention label:</span></span>

![ラベルの [保持] 設定ページ](../media/disposition-review-option.png)
 
<span data-ttu-id="f1432-179">この [**処理確認を開始する**] オプションを選択した後、ウィザードの次のページで、必要な連続する処理ステージ数と、各ステージの処理確認担当者を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1432-179">After you select this **Trigger a disposition review** option, on the next page of the wizard, you specify how many consecutive stages of disposition you want and the disposition reviewers for each stage:</span></span>

![処理確認担当者の指定](../media/disposition-reviewers.png) 

<span data-ttu-id="f1432-181">[**ステージの追加**] を選択し、識別用にステージに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="f1432-181">Select **Add a stage**, and name your stage for identification purposes.</span></span> <span data-ttu-id="f1432-182">次に、そのステージのレビュー担当者を指定します。</span><span class="sxs-lookup"><span data-stu-id="f1432-182">Then specify the reviewers for that stage.</span></span>

<span data-ttu-id="f1432-183">確認担当者には、ユーザーまたはメール対応のセキュリティ グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1432-183">For the reviewers, specify a user or a mail-enabled security group.</span></span> <span data-ttu-id="f1432-184">Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) は、このオプションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f1432-184">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are currently not supported for this option.</span></span>

<span data-ttu-id="f1432-185">保持期間の最後に複数のユーザーがアイテムを確認する必要がある場合は、[**ステージの追加**] を再び選択し、必要なステージ数 (最大 5 ステージ) を構成するプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="f1432-185">If you need more than one person to review an item at the end of its retention period, select **Add a stage** again and repeat the configuration process for the number of stages that you need, with a maximum of five stages.</span></span> 

<span data-ttu-id="f1432-p123">個々の処理ステージで、そのステージに指定されたされたユーザーは、保持期間の終わりにアイテムに対して次の操作を行う権限を持っています。これらのユーザーは、処理確認ステージに他のユーザーを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-p123">Within each individual stage of disposition, any of the users you specify for that stage are authorized to take the next action for the item at the end of its retention period. These users can also add other users to their disposition review stage.</span></span>

> [!NOTE]
> <span data-ttu-id="f1432-188">処理確認用に構成された既存の保持ラベルは、ラベルを構成することで、複数ステージの処理確認を使用するようにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="f1432-188">Existing retention labels that are configured for disposition review can be upgraded to use multi-staged disposition review by configuring the label.</span></span> <span data-ttu-id="f1432-189">ラベル ウィザードで、[**ラベルの追加**] を選んで既存の確認担当者を編集するか、新しい確認担当者を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1432-189">In the label wizard, select **Add a stage**, or edit the existing reviewers or add new reviewers.</span></span>

<span data-ttu-id="f1432-190">構成フェーズで指定した各ステージについて、名前の変更、並べ替え、削除を行うことができます。その場合は、[ステージアクション] オプション (**...**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1432-190">During the configuration phase, for each stage specified, you can rename it, reorder it, or remove it by selecting the Stage actions option (**...**):</span></span> 

![処理確認のステージ操作](../media/stage-actions-disposition-review.png)

<span data-ttu-id="f1432-192">ただし、保持ラベルを作成した後で、ステージの並べ替えや削除を行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1432-192">However, you can't reorder or remove a stage after you have created the retention label.</span></span>

<span data-ttu-id="f1432-193">確認担当者を指定したら、**処理管理** 役のアクセス許可を確認担当者に付与することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="f1432-193">After you have specified your reviewers, remember to grant them the **Disposition Management** role permission.</span></span> <span data-ttu-id="f1432-194">詳細については、このページのセクション「[処理のアクセス許可](#permissions-for-disposition)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-194">For more information, see the [Permissions for disposition](#permissions-for-disposition) section on this page.</span></span>

### <a name="how-to-customize-email-messages-for-disposition-review"></a><span data-ttu-id="f1432-195">処理確認のためにメール メッセージをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="f1432-195">How to customize email messages for disposition review</span></span>

<span data-ttu-id="f1432-196">確認担当者に送られる既定のメール通知の例。</span><span class="sxs-lookup"><span data-stu-id="f1432-196">Example default email notification sent to a reviewer:</span></span>

![処理確認の準備ができた場合の既定のテキストによるメール通知例](../media/disposition-review-email.png)

<span data-ttu-id="f1432-198">また、プレビューで、最初の通知とその後のリマインダーのために処理確認者に送るメールをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-198">Also in preview, you can customize the email messages that are sent to disposition reviewers for the initial notification and then reminders.</span></span>

<span data-ttu-id="f1432-199">コンプライアンス センターの[処理]ページから、[**レコード管理の設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f1432-199">From any of the Disposition pages in the compliance center, select **Records management settings**:</span></span>  

![レコード管理の設定](../media/record-management-settings.png)

<span data-ttu-id="f1432-201">次に、[**処理通知**] タブを選択し、既定のメール メッセージを使用するか、既定のメッセージに独自のテキストを追加するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1432-201">Then select the **Disposition notifications** tab, and specify whether you want to use just the default email message, or add your own text to the default message.</span></span> <span data-ttu-id="f1432-202">ユーザー設定のテキストは、メールの指示の、保持ラベルに関する情報の後、および次の手順の指示の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-202">Your custom text is added to the email instructions after the information about the retention label and before the next steps instructions.</span></span>

<span data-ttu-id="f1432-203">すべての言語のテキストを追加できますが、書式設定と画像は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f1432-203">Text for all languages can be added, but formatting and images are currently unsupported.</span></span> <span data-ttu-id="f1432-204">URL とメール アドレスはテキストとして入力できます。また、メール クライアントによっては、カスタマイズしたメールにハイパーリンクまたは書式が設定されていないテキストとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-204">URLs and email addresses can be entered as text and depending on the email client, display as hyperlinks or unformatted text in the customized email.</span></span>

<span data-ttu-id="f1432-205">追加するテキストの例。</span><span class="sxs-lookup"><span data-stu-id="f1432-205">Example text to add:</span></span>

```console
If you need additional information, visit the helpdesk website (https://support.contoso.com) or send them an email (helpdesk@contoso.com).
```

<span data-ttu-id="f1432-206">[**保存**] を選んで変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f1432-206">Select **Save** to save any changes.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="f1432-207">コンテンツの表示と処理</span><span class="sxs-lookup"><span data-stu-id="f1432-207">Viewing and disposing of content</span></span>

<span data-ttu-id="f1432-208">確認担当者は、コンテンツを確認する準備ができたことをメールで通知されると、メールのリンクをクリックして、Microsoft365 コンプライアンス センターの **レコード管理** から [**処理**] に直接アクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-208">When a reviewer is notified by email that content is ready to review, they can click a link in the email that takes them directly to the **Disposition** page from **Records management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f1432-209">そこで、確認担当者は、**Type** で **保留中の処理** を表示して、保持ラベルごとに処理待ちのアイテムの数を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-209">There, the reviewers can see how many items for each retention label are waiting disposition with the **Type** displaying **Pending disposition**.</span></span> <span data-ttu-id="f1432-210">そこで、保持ラベルを選択し、[**新しいウィンドウで開く**] を選んで、そのラベルのコンテンツをすべて表示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-210">They then select a retention label, and **Open in new window** to see all content with that label:</span></span>

![処理確認用の新しいウィンドウで開く](../media/open-in-new-window.png)

<span data-ttu-id="f1432-212">[**保留中の処理**] を選ぶと、そのラベルに関して保留中の処理がすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-212">From the **Pending dispositions** page, they see all pending dispositions for that label.</span></span> <span data-ttu-id="f1432-213">1 つ以上のアイテムを選択すると、ミニ プレビュー ウィンドウおよび [**ソース**]、 [**詳細**]、および [**履歴**] タブを使用して、操作を実行する前にコンテンツを検査できます。</span><span class="sxs-lookup"><span data-stu-id="f1432-213">When one or more items are selected, they can use the mini-preview pane and the **Source**, **Details**, and **History** tab to inspect the content before taking action on it:</span></span>

![処理オプション](../media/retention-disposition-options.png)

<span data-ttu-id="f1432-215">水平スクロール バーを使用するか、ミニ レビュー ウィンドウを閉じると、有効期限と処理確認ステージの名前を含む列が他に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-215">If you use the horizontal scroll bar, or close the min-review pane, you see more columns that include the expiry date and the name of the disposition review stage.</span></span>

<span data-ttu-id="f1432-216">下記の例からわかるように、サポートされている操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1432-216">As you can see from the example shown, the actions supported are:</span></span> 
  
- <span data-ttu-id="f1432-217">**処理の承認**:</span><span class="sxs-lookup"><span data-stu-id="f1432-217">**Approve disposal**:</span></span>
    - <span data-ttu-id="f1432-218">処理確認の中間ステージ (複数のステージを構成した場合) に対してこの操作が選択されている場合: その項目は次の処理ステージに移動します。</span><span class="sxs-lookup"><span data-stu-id="f1432-218">When this action is selected for an interim stage of disposition review (you have configured multiple stages): The item moves to the next disposition stage.</span></span>
    - <span data-ttu-id="f1432-219">処理確認の最終ステージにこの操作が選択された場合、または処理のステージが 1 つだけの場合: そのアイテムは完全削除の対象としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="f1432-219">When this action is selected for the final stage of disposition review, or there is only one stage of disposition: The item is marked as eligible for permanent deletion.</span></span> <span data-ttu-id="f1432-220">削除の正確なタイミングは、ワークロードによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f1432-220">The exact timing for that deletion depends on the workload.</span></span> <span data-ttu-id="f1432-221">詳細情報は、「[保持設定が所定の場所にあるコンテンツに作用するしくみ](retention.md#how-retention-settings-work-with-content-in-place)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f1432-221">For more information, see [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>
- <span data-ttu-id="f1432-222">**ラベルの変更**:</span><span class="sxs-lookup"><span data-stu-id="f1432-222">**Relabel**:</span></span>
    - <span data-ttu-id="f1432-223">この操作を選択すると、アイテムは元のラベルの処理確認プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="f1432-223">When this action is selected, the item exits the disposition review process for the original label.</span></span> <span data-ttu-id="f1432-224">そして、そのアイテムは、新しく選択した保持ラベルの保持設定の対象となります。</span><span class="sxs-lookup"><span data-stu-id="f1432-224">The item is then subject to the retention settings of the newly selected retention label.</span></span>
- <span data-ttu-id="f1432-225">**拡張**</span><span class="sxs-lookup"><span data-stu-id="f1432-225">**Extend**:</span></span>
    - <span data-ttu-id="f1432-226">この操作を選択すると、処理確認は延長期間が終了するまで実質的に中断され、その後、第 1 ステージから処理確認が再度開始されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-226">When this action is selected, disposition review is effectively suspended until the end of the extended period and then disposition review is triggered again from the first stage.</span></span>
- <span data-ttu-id="f1432-227">**確認者の追加**</span><span class="sxs-lookup"><span data-stu-id="f1432-227">**Add reviewers**:</span></span>
    - <span data-ttu-id="f1432-228">この操作を選択すると、他のユーザーを指定して追加するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-228">When this action is selected, the user is prompted to specify and add other users for review.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f1432-229">この操作により、追加されたユーザーにユーザーに、[必要なアクセス許可](#permissions-for-disposition) が自動的に付与されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="f1432-229">This action doesn't automatically grant the [required permissions](#permissions-for-disposition) to the users who are added.</span></span> <span data-ttu-id="f1432-230">これらのアクセス許可を持っていない場合、処理確認には参加できません。</span><span class="sxs-lookup"><span data-stu-id="f1432-230">If they don't have these permissions, they won't be able to participate in the disposition review.</span></span>

<span data-ttu-id="f1432-231">実行されたすべての操作は保存され格納されます。ただし、監査ログでの検索はまだできません。</span><span class="sxs-lookup"><span data-stu-id="f1432-231">Each action taken is saved and stored although you can't yet search for them in the audit log.</span></span>

<span data-ttu-id="f1432-232">処理確認中、コンテンツは元の場所から移動されません。また、最終ステージまたは、処理ステージのみに対して確認者がこの操作を選択するまでは、完全削除のマークは付けられません。</span><span class="sxs-lookup"><span data-stu-id="f1432-232">During a disposition review, the content never moves from its original location, and it's not marked for permanent deletion until this action is selected by a reviewer for the final or only disposition stage.</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="f1432-233">レコードの処理</span><span class="sxs-lookup"><span data-stu-id="f1432-233">Disposition of records</span></span>

<span data-ttu-id="f1432-234">[**レコード管理**] ページの [**処理**] タブを使用して、以下を特定します。</span><span class="sxs-lookup"><span data-stu-id="f1432-234">Use the **Disposition** tab from the **Records management** page to identify:</span></span>

- <span data-ttu-id="f1432-235">処理確認の結果として、削除された項目。</span><span class="sxs-lookup"><span data-stu-id="f1432-235">Items deleted as a result of a disposition review.</span></span>
- <span data-ttu-id="f1432-236">保持期間の終了時に自動的に削除された、レコードまたは規制レコードとしてマークされたアイテム。</span><span class="sxs-lookup"><span data-stu-id="f1432-236">Items marked as a record or regulatory record that were automatically deleted at the end of their retention period.</span></span>

<span data-ttu-id="f1432-237">これらのアイテムは、**種類** 列に **処分されたレコード** を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-237">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="f1432-238">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f1432-238">For example:</span></span>

![処理確認なしで処理されたアイテム](../media/records-disposed2.png)

> [!NOTE]
> <span data-ttu-id="f1432-240">この機能は、[統合監査ログ](search-the-audit-log-in-security-and-compliance.md)からの情報を使用して、対応するイベントがキャプチャされるように、監査を[有効にして検索可能](turn-audit-log-search-on-or-off.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1432-240">This functionality uses information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="f1432-241">レコードまたは規制レコードとしてマークされている削除されたアイテムの監査については、**ファイルとページのアクティビティ** カテゴリで「**レコードとしてマークされたファイルの削除**」を検索してください。</span><span class="sxs-lookup"><span data-stu-id="f1432-241">For auditing of deleted items that were marked as records or regulatory records, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="f1432-242">この監査イベントは、ドキュメントとメールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f1432-242">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="f1432-243">表示をフィルター処理してエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f1432-243">Filter and export the views</span></span>

<span data-ttu-id="f1432-244">[**処理**] ページから保持ラベルを選択すると、[**保留中の処理**] タブ (該当する場合) と [**処理されたアイテム**] タブを使用して、表示をフィルター処理できます。より簡単にアイテムを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-244">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span>

<span data-ttu-id="f1432-245">保留中の処理の場合、期間は有効期限に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f1432-245">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="f1432-246">処理されたアイテムの場合、時間範囲は削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f1432-246">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="f1432-247">どちらの表示のアイテムに関する情報も .csv ファイルとしてエクスポートでき、Excel を使用して並べ替えや管理ができます。</span><span class="sxs-lookup"><span data-stu-id="f1432-247">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel.</span></span>
