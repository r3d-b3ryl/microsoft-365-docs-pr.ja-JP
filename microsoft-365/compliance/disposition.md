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
description: 処理確認を使用するか、構成に従ってコンテンツが自動的に削除されるかにかかわらず、コンテンツの処理を監視および管理します。
ms.openlocfilehash: 9900bbc58818a98ad41f4f796184ccf21041bbfe
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409214"
---
# <a name="disposition-of-content"></a><span data-ttu-id="e5790-103">コンテンツの処理</span><span class="sxs-lookup"><span data-stu-id="e5790-103">Disposition of content</span></span>

><span data-ttu-id="e5790-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e5790-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e5790-105">Microsoft 365 コンプライアンス センターの **レコード管理** の [**処理**] タブを使用して、処理確認を管理し、保持期間の終了時に自動的に削除された [レコード](records-management.md#records)を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5790-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="e5790-106">コンテンツの処理を表示するための前提条件</span><span class="sxs-lookup"><span data-stu-id="e5790-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="e5790-107">処理確認を管理し、レコードが削除されたことを確認するには、十分なアクセス許可があり、監査が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5790-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="e5790-108">処理のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e5790-108">Permissions for disposition</span></span>

<span data-ttu-id="e5790-109">Microsoft365 コンプライアンス センターの [**処理**] タブに正常にアクセスするには、ユーザーは **処理管理** の管理者の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5790-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="e5790-110">この役割は、既定の管理者の役割グループである **コンプライアンス管理者** および **コンプライアンス データ管理者** に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5790-110">This role is included in the default admin role groups, **Compliance Administrator** and **Compliance Data Administrator**.</span></span>

<span data-ttu-id="e5790-111">ユーザーにこの必要な処理管理の役割を付与するには、ユーザーをこれらの既定の役割グループの 1 つに追加するか、カスタム役割グループ (たとえば、「処理確認」という名前) を作成して、このグループに処理管理の役割を付与します。</span><span class="sxs-lookup"><span data-stu-id="e5790-111">To grant users this required Disposition Management role, either add them to one of these default role groups, or create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>  

> [!NOTE]
> <span data-ttu-id="e5790-112">全体管理者に対しても、**処理管理** の役割を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5790-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="e5790-113">さらに、処理プロセス中にアイテムの内容を表示するには、**コンテンツ エクスプローラーのコンテンツ閲覧者** と **コンテンツ エクスプローラーのリスト閲覧者** の 2 つの役割グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e5790-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="e5790-114">ユーザーがこれらの役割グループのアクセス許可を持っていない場合でも、処理確認操作を選択して処理確認を完了することができますが、コンプライアンス センターからアイテムのコンテンツを表示することができません。</span><span class="sxs-lookup"><span data-stu-id="e5790-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="e5790-115">手順については、「[ユーザーに Office 365 セキュリティ/センター コンプライアンス センターへのアクセスを許可する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5790-115">For instructions, see [Give users access to the Office 365 Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="e5790-116">監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="e5790-116">Enable auditing</span></span>

<span data-ttu-id="e5790-117">最初の処理操作の少なくとも 1 日前に、監査が有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e5790-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="e5790-118">詳細については、「[Office 365 セキュリティ&amp;コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5790-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="e5790-119">処理確認</span><span class="sxs-lookup"><span data-stu-id="e5790-119">Disposition reviews</span></span>

<span data-ttu-id="e5790-120">コンテンツがその保持期間の終了に近づいたとき、いくつかの理由から、その安全な削除 (「処理」) を決定する目的でコンテンツを見直すことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="e5790-121">たとえば、次の対応が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="e5790-121">For example, you might need to:</span></span>
  
- <span data-ttu-id="e5790-122">訴訟や監査に備え、関連コンテンツの削除を保留にします。</span><span class="sxs-lookup"><span data-stu-id="e5790-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="e5790-123">調査や記録のために残しておく価値がある場合、コンテンツを処理リストから削除し、アーカイブに保存します。</span><span class="sxs-lookup"><span data-stu-id="e5790-123">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="e5790-124">元の保持設定が一時的または暫定的な解決策であったためか、コンテンツに異なる保持期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e5790-124">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="e5790-125">コンテンツを顧客に返すか、別の組織に渡します。</span><span class="sxs-lookup"><span data-stu-id="e5790-125">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="e5790-126">保持期間の終了時に処理確認がトリガーされた場合:</span><span class="sxs-lookup"><span data-stu-id="e5790-126">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="e5790-127">選択したユーザーの元に、確認するコンテンツを知らせるメールが届きます。</span><span class="sxs-lookup"><span data-stu-id="e5790-127">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="e5790-128">これらの確認担当者は個々のユーザーか、メールが有効なセキュリティ グループです。</span><span class="sxs-lookup"><span data-stu-id="e5790-128">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="e5790-129">週単位で通知が送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5790-129">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="e5790-130">確認担当者は、Microsoft365 コンプライアンス センターの [**処理**] タブに移動してコンテンツを確認し、コンテンツを完全に削除するか、保持期間を延長するか、別の保持ラベルを適用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e5790-130">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="e5790-131">処理確認には、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、および Microsoft365 グループのコンテンツを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5790-131">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="e5790-132">以上の場所で処理確認を待っているコンテンツは、確認担当者がコンテンツの完全削除を選択しない限り削除されません。</span><span class="sxs-lookup"><span data-stu-id="e5790-132">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="e5790-133">処理確認をサポートするには、メールボックスに少なくとも 10 MB のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5790-133">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="e5790-134">保留中のすべての処理の概要は、[**概要**] タブで確認できます。例えば:</span><span class="sxs-lookup"><span data-stu-id="e5790-134">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![レコード管理の概要で保留中の処理](../media/dispositions-overview.png)

<span data-ttu-id="e5790-136">[**すべての保留中の処理を表示**] を選択すると、[**処理**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-136">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="e5790-137">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e5790-137">For example:</span></span>

![Microsoft365 コンプライアンス センターの [処理] ページ](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="e5790-139">処理確認の流れ</span><span class="sxs-lookup"><span data-stu-id="e5790-139">Workflow for a disposition review</span></span>

<span data-ttu-id="e5790-140">次の図は、保持ラベルが公開され、ユーザーが手動で適用した場合の処理確認の基本的な流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5790-140">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="e5790-141">または、処理確認用に構成された保持ラベルをコンテンツに自動適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e5790-141">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![処理の流れを示すグラフ](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="e5790-143">保持期間の終了時に処理確認をトリガーすることは、保持ラベルでのみ使用可能な構成オプションです。</span><span class="sxs-lookup"><span data-stu-id="e5790-143">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="e5790-144">このオプションは保持ポリシーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5790-144">This option is not available for a retention policy.</span></span> <span data-ttu-id="e5790-145">これら 2 つの保持ソリューションの詳細については、「[保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5790-145">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="e5790-146">保持ラベルの [**保持設定の定義**] ページから:</span><span class="sxs-lookup"><span data-stu-id="e5790-146">From the **Define retention settings** page for a retention label:</span></span>

![ラベルの [保持] 設定ページ](../media/disposition-review-option.png)
 
<span data-ttu-id="e5790-148">この [**処理確認を開始する**] オプションを選択した後、ウィザードの次のページで処理確認の担当者を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5790-148">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![処理確認の指定](../media/disposition-reviewers.png)

<span data-ttu-id="e5790-150">確認担当者には、ユーザーまたはメール対応のセキュリティ グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5790-150">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="e5790-151">Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) は、このオプションではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e5790-151">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="e5790-152">コンテンツの表示と処理</span><span class="sxs-lookup"><span data-stu-id="e5790-152">Viewing and disposing of content</span></span>

<span data-ttu-id="e5790-153">確認担当者は、コンテンツを確認する準備ができたことをメールで通知されると、Microsoft365 コンプライアンス センターの **レコード管理** から [**処理**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="e5790-153">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e5790-154">確認担当者は、保持ラベルごとに処理を待機しているアイテムの数を確認し、保持ラベルを選択して、そのラベルが付いたすべてのコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e5790-154">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="e5790-155">保持ラベルを選択すると、[**保留中の処理**] タブからそのラベルのすべての保留中の処理が表示されます。操作を選択して妥当性コメントを入力できる 1 つ以上のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5790-155">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![処理オプション](../media/retention-disposition-options.png)

<span data-ttu-id="e5790-157">写真からわかるように、サポートされている操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5790-157">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="e5790-158">アイテムを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="e5790-158">Permanently delete the item</span></span>
- <span data-ttu-id="e5790-159">保持期間を延長する</span><span class="sxs-lookup"><span data-stu-id="e5790-159">Extend the retention period</span></span>
- <span data-ttu-id="e5790-160">別の保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="e5790-160">Apply a different retention label</span></span>

<span data-ttu-id="e5790-161">場所とコンテンツへのアクセス許可があれば、**場所** 列のリンクを使用して、元の場所にあるドキュメントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e5790-161">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="e5790-162">処理確認中、コンテンツが元の場所から移動されることはありません。確認担当者が削除を選択するまで削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="e5790-162">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="e5790-163">メール通知が週単位で確認担当者に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-163">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="e5790-164">このスケジュールされたプロセスは、コンテンツの保持期間が終わるまでに、確認担当者は最大で 7 日、コンテンツが処理を待っているというメール通知を受信する場合があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5790-164">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="e5790-165">すべての処理操作を監査でき、確認担当者が入力した妥当性テキストが保存され、[**処理アイテム**] ページの **コメント** 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-165">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="e5790-166">処理されたコンテンツが完全に削除されるまでの期間</span><span class="sxs-lookup"><span data-stu-id="e5790-166">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="e5790-167">処理確認を待っているコンテンツは、確認担当者がコンテンツの完全削除を選択しない限り削除されません。</span><span class="sxs-lookup"><span data-stu-id="e5790-167">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="e5790-168">確認担当者がこのオプションを選択すると、SharePoint サイトまたは OneDrive アカウントのコンテンツは、「[保持設定が所定の場所にあるコンテンツに作用するしくみ](retention.md#how-retention-settings-work-with-content-in-place)」セクションで説明する標準のクリーンアップ プロセスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="e5790-168">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="e5790-169">レコードの処理</span><span class="sxs-lookup"><span data-stu-id="e5790-169">Disposition of records</span></span>

<span data-ttu-id="e5790-170">[**レコード管理**] ページの [**処理**] タブを使用して、自動的に、または処理確認後に削除されたレコードを特定します。</span><span class="sxs-lookup"><span data-stu-id="e5790-170">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="e5790-171">これらのアイテムは、**種類** 列に **処分されたレコード** を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5790-171">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="e5790-172">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e5790-172">For example:</span></span>

![処理確認なしで処理されたアイテム](../media/records-disposed2.png)

<span data-ttu-id="e5790-174">レコード ラベルの [**処理されたアイテム**] タブに表示されるアイテムは、アイテムが処理されてから最大 7 年間保持され、その期間のレコードあたりのアイテム数は 100 万に制限されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-174">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="e5790-175">**カウント** の数がこの 100 万の制限に近づいていて、レコードの処理の証明が必要な場合は、[Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)に連絡し​​てください。</span><span class="sxs-lookup"><span data-stu-id="e5790-175">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="e5790-176">この機能は、[統合監査ログ](search-the-audit-log-in-security-and-compliance.md)からの情報に基づいているため、対応するイベントがキャプチャされるように、監査を[有効にして検索可能](turn-audit-log-search-on-or-off.md)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5790-176">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="e5790-177">監査では、[**ファイルとページのアクティビティ**] カテゴリで、**レコードとしてマークされている削除されたファイル** を検索 します。</span><span class="sxs-lookup"><span data-stu-id="e5790-177">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="e5790-178">この監査イベントは、ドキュメントとメールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5790-178">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="e5790-179">表示のフィルター処理とエクスポート</span><span class="sxs-lookup"><span data-stu-id="e5790-179">Filter and export the views</span></span>

<span data-ttu-id="e5790-180">[**処理**] ページから保持ラベルを選択すると、[**保留中の処理**] タブ (該当する場合) と [**処理されたアイテム**] タブを使用して、表示をフィルター処理できます。より簡単にアイテムを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e5790-180">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="e5790-181">保留中の処理の場合、期間は有効期限に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e5790-181">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="e5790-182">処理されたアイテムの場合、時間範囲は削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e5790-182">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="e5790-183">どちらの表示のアイテムに関する情報も .csv ファイルとしてエクスポートでき、Excel を使用して並べ替えて管理できます。</span><span class="sxs-lookup"><span data-stu-id="e5790-183">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![処理のためのエクスポート オプション](../media/retention-export-option.png)

