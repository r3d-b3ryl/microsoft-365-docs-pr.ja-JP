---
title: 廃棄レビューの概要
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 のコンテンツを保持する保持ラベルを作成する場合、保持期間の終了時に廃棄のレビューを開始することを選択できます。
ms.openlocfilehash: ee9ea34ee8527558af4d249364b539d3fa1f2fdd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634975"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="fcfc2-103">廃棄レビューの概要</span><span class="sxs-lookup"><span data-stu-id="fcfc2-103">Overview of disposition reviews</span></span>

<span data-ttu-id="fcfc2-104">コンテンツが保存期間の最後に達すると、いくつかの理由から、そのコンテンツを確認して、安全に削除できるかどうかを判断する必要があります (「廃棄済み」)。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-104">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="fcfc2-105">たとえば、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-105">For example, you might need to:</span></span>
  
- <span data-ttu-id="fcfc2-106">訴訟や監査の際に、関連するコンテンツの削除 ("廃棄") を中断します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="fcfc2-107">コンテンツにリサーチまたは履歴の値がある場合は、廃棄リストからコンテンツを削除してアーカイブに保存します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="fcfc2-108">元のポリシーが一時的または暫定ソリューションだった場合は、コンテンツに異なる保存期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="fcfc2-109">クライアントにコンテンツを返すか、または別の組織に転送します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="fcfc2-110">Microsoft 365 コンプライアンスセンター、Microsoft 365 セキュリティセンター、または Office 365 セキュリティ & コンプライアンスセンターで保持ラベルを作成する場合、保持期間の終了時に廃棄レビューを開始することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-110">When you create a retention label in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center, you can choose to trigger a disposition review at the end of the retention period.</span></span> <span data-ttu-id="fcfc2-111">廃棄レビューの場合:</span><span class="sxs-lookup"><span data-stu-id="fcfc2-111">In a disposition review:</span></span>
  
- <span data-ttu-id="fcfc2-112">選択したユーザーには、閲覧するコンテンツがあることを示す電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-112">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="fcfc2-113">通知は週単位で送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-113">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="fcfc2-114">レビュー担当者は、 **Disposition**セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動して、コンテンツを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-114">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> <span data-ttu-id="fcfc2-115">レビュー担当者は、廃棄を待機している各保持ラベルのアイテム数を確認し、そのラベルを持つすべてのコンテンツを表示する保持ラベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-115">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>
    
- <span data-ttu-id="fcfc2-116">レビュー担当者は、ドキュメントまたは電子メールごとに次のことを行えます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-116">For each document or email, the reviewer can:</span></span>
    
  - <span data-ttu-id="fcfc2-117">別の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-117">Apply a different retention label.</span></span>
    
  - <span data-ttu-id="fcfc2-118">その保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="fcfc2-119">完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="fcfc2-120">レビュー担当者は、保留中または完了した処理のいずれかを表示し、その一覧を .csv ファイルとしてエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-120">Reviewers can view either pending or completed dispositions, and export that list as a .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="fcfc2-121">廃棄レビューには、Office 365 Enterprise E5 サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-121">Disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="fcfc2-122">廃棄レビューには、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、および Office 365 グループのコンテンツを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-122">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups.</span></span> <span data-ttu-id="fcfc2-123">これらの場所の廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-123">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![セキュリティ/コンプライアンスセンターの [配置] ページ](../media/Retention-Dispositions-v2-page.png)


## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a><span data-ttu-id="fcfc2-125">保持ラベルを作成して廃棄レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="fcfc2-125">Setting up the disposition review by creating a retention label</span></span>

<span data-ttu-id="fcfc2-126">これは、廃棄レビューを設定するための基本的なワークフローです。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-126">This is the basic workflow for setting up a disposition review.</span></span> <span data-ttu-id="fcfc2-127">このフローには、公開されている保持ラベルと、ユーザーによって手動で適用されるものが示されることに注意してください。または、廃棄レビューをトリガーする保持ラベルをコンテンツに自動適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-127">Note that this flow shows a retention label being published and then manually applied by a user; alternatively, a retention label that triggers a disposition review can be auto-applied to content.</span></span>
  
![廃棄のしくみを示す図](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="fcfc2-129">廃棄のレビューは、Office 365 で保持ラベルを作成する場合のオプションです。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-129">A disposition review is an option when you create a retention label in Office 365.</span></span> <span data-ttu-id="fcfc2-130">このオプションは、アイテム保持ポリシーでは使用できませんが、コンテンツを保持するように構成された保持ラベルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-130">This option is not available in a retention policy but only in a retention label that's configured to retain content.</span></span>
  
<span data-ttu-id="fcfc2-131">保持ラベルの詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-131">For more information about retention labels, see [Overview of retention labels](labels.md).</span></span>
  
![ラベルの保持設定](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="fcfc2-133">[レビューの準備が**できたアイテムがあるときに、これらのユーザーに通知**する] オプションを指定する場合は、ユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-133">When you specify the option **Notify these people when there are items ready to review**, specify a user.</span></span> <span data-ttu-id="fcfc2-134">このオプションでは、Office 365 グループはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-134">Office 365 groups are not supported for this option.</span></span>

## <a name="disposing-content"></a><span data-ttu-id="fcfc2-135">コンテンツを破棄する</span><span class="sxs-lookup"><span data-stu-id="fcfc2-135">Disposing content</span></span>

<span data-ttu-id="fcfc2-136">コンテンツがレビューできる状態であることをレビュー担当者に電子メールで通知する場合**Disposition**は、セキュリティ&amp;コンプライアンスセンターの [廃棄] ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-136">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="fcfc2-137">レビュー担当者は、廃棄を待機している各保持ラベルのアイテム数を確認し、そのラベルを持つすべてのコンテンツを表示する保持ラベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-137">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="fcfc2-138">保持ラベルを選択すると、次のページにそのラベルの保留中のすべての実行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-138">After you select a retention label, the next page shows all pending dispositions for that label.</span></span>

![ディスポジションオプション](../media/Retention-Disposition-options-v2.png)

<span data-ttu-id="fcfc2-140">レビュー担当者は次のことができます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-140">The reviewer can then:</span></span> 
  
- <span data-ttu-id="fcfc2-141">別の保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-141">Apply a different retention label.</span></span>
    
- <span data-ttu-id="fcfc2-142">保持期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-142">Extend the retention period.</span></span>
    
- <span data-ttu-id="fcfc2-143">アイテムを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-143">Permanently delete the item.</span></span>

<span data-ttu-id="fcfc2-144">レビューアーは複数のアイテムを選択し、それらを同時に破棄することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-144">Note that a reviewer can select multiple items and dispose them at the same time.</span></span>
    
<span data-ttu-id="fcfc2-145">レビュー担当者は、このリンクを使用して、その場所へのアクセス許可がある場合に、元の場所にドキュメントを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-145">A reviewer can also use the link to view the document in its original location, if the reviewer has permissions for that location.</span></span> <span data-ttu-id="fcfc2-146">廃棄レビュー中は、コンテンツは元の場所から移動されません。また、レビュー担当者がそのように選択しない限り、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-146">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="fcfc2-147">電子メール通知は、1週間ごとにレビュー担当者に自動的に送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-147">Note that the email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="fcfc2-148">そのため、コンテンツが保持期間の最後に達すると、コンテンツが廃棄を待機しているというメール通知をレビューアーが受け取るまでに最大7日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-148">Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="fcfc2-149">また、すべての廃棄アクションが監査されることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-149">Also note that all disposition actions are audited.</span></span> <span data-ttu-id="fcfc2-150">このことを確認するには、最初の廃棄アクションの前に少なくとも1日前に監査を有効にする必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-150">To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="fcfc2-151">廃棄のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fcfc2-151">Permissions for disposition</span></span>

<span data-ttu-id="fcfc2-152">[**廃棄**] ページにアクセスするには、[**廃棄管理**] 役割と [**表示のみ] の監査ログ**の役割がレビュー担当者に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-152">To access the **Disposition** page, reviewers must be assigned the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="fcfc2-153">役割の割り当ての[手順を表示](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-153">[View instructions](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) for assigning roles.</span></span>

<span data-ttu-id="fcfc2-154">**表示のみの監査ログ**の役割に固有です。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-154">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="fcfc2-155">監査ログの検索に使用される基礎となるコマンドレットは Exchange Online コマンドレットなので、セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページではなく、exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)を使用してユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-155">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="fcfc2-156">手順については、「 [Manage role groups In Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-156">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="fcfc2-157">Office 365 グループはこの役割ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-157">Office 365 Groups aren't supported for this role.</span></span> <span data-ttu-id="fcfc2-158">代わりに、ユーザーメールボックスまたはメールユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-158">Instead, assign user mailboxes or mail users.</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="fcfc2-159">破棄されたコンテンツが完全に削除されるまでの時間</span><span class="sxs-lookup"><span data-stu-id="fcfc2-159">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="fcfc2-160">廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-160">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="fcfc2-161">レビュー担当者がこのオプションを選択すると、SharePoint サイトまたは OneDrive アカウントのコンテンツは、このセクションで説明されている標準的なクリーンアッププロセスの対象となります。[アイテム保持ポリシーがコンテンツをインプレースでどのように動作するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-161">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="fcfc2-162">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-162">This means that:</span></span>
  
- <span data-ttu-id="fcfc2-163">ドキュメントライブラリ内のコンテンツは、廃棄の**7 日以内**に第1段階のごみ箱に移動され、その後は**93 日**後に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-163">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that.</span></span> <span data-ttu-id="fcfc2-164">ごみ箱には検索によってインデックスが作成されないため、電子情報開示ホールドでそのコンテンツを使用できません。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-164">The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span>

- <span data-ttu-id="fcfc2-165">保持保持ライブラリのコンテンツは、廃棄から**7 日以内**に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-165">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span>

- <span data-ttu-id="fcfc2-166">Exchange メールボックス内のアイテムは、廃棄から**14 日以内**に完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-166">Items in an Exchange mailbox will be permanently deleted **within 14 days** of disposition.</span></span> <span data-ttu-id="fcfc2-167">(既定の設定は14日であることに注意してくださいが、最大30日間構成できます)。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-167">(Note that 14 days is the default setting but it can be configured up to 30 days.)</span></span>
    
## <a name="view-pending-dispositions-and-disposed-items"></a><span data-ttu-id="fcfc2-168">保留中の廃棄と破棄されたアイテムを表示する</span><span class="sxs-lookup"><span data-stu-id="fcfc2-168">View pending dispositions and disposed items</span></span>

<span data-ttu-id="fcfc2-169">[**保留中の廃棄**] ページでは、特定の保持ラベルについて、保留中および完了済みの両方の処理を表示できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-169">On the **Pending disposition** page, you can view both pending and completed dispositions for a specific retention label:</span></span> 
  
- <span data-ttu-id="fcfc2-170">**保留中の廃棄**は、保持期間の最後に達し、廃棄レビューを必要とするアイテムを示します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-170">The **Pending disposition** shows items that have reached the end of their retention period and require a disposition review.</span></span> <span data-ttu-id="fcfc2-171">各項目を確認した後、別の保持ラベルを適用するか、その保持期間を延長するか、または完全に削除するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-171">After reviewing each item, decide if you want to apply a different retention label to it, extend its retention period, or permanently delete it.</span></span> <span data-ttu-id="fcfc2-172">複数のアイテムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-172">You can select multiple items.</span></span>
    
- <span data-ttu-id="fcfc2-173">[**破棄**されたアイテム] タブには、廃棄レビューで既に実行されている完全に削除されたアイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-173">The **Disposed items** tab shows permanently-deleted items that have already been through a disposition review.</span></span> <span data-ttu-id="fcfc2-174">この記事では、上記のセクションで説明したように、永続的な削除処理に数日かかる場合があるため、ここで説明します。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-174">They show here because the permanent deletion process can take several days, as noted in the section above.</span></span> <span data-ttu-id="fcfc2-175">別の保持ラベルが適用されているアイテム、またはレビューの一部として保持期間を延長したアイテムは、ここには表示されません。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-175">Items that had a different retention label applied, or had their retention period extended as part of a review, won't appear here.</span></span>

![ディスポジションタブ](../media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="fcfc2-177">廃棄ビューをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fcfc2-177">Filter the disposition views</span></span>

<span data-ttu-id="fcfc2-178">これらのビューは、保持ラベルまたは時間範囲によってフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-178">You can filter these views by retention label or time range.</span></span> <span data-ttu-id="fcfc2-179">保留中の処理の場合、時間の範囲は有効期限に基づきます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-179">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="fcfc2-180">破棄されたアイテムの場合、時間範囲は、削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-180">For disposed items, the time range is based on the deletion date.</span></span>
  
![廃棄フィルターオプション](../media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a><span data-ttu-id="fcfc2-182">廃棄アイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="fcfc2-182">Export the disposition items</span></span>

<span data-ttu-id="fcfc2-183">また、いずれかのビューのアイテムを .csv ファイルとしてエクスポートして、Excel で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fcfc2-183">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Excel でエクスポートされた廃棄データ](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

