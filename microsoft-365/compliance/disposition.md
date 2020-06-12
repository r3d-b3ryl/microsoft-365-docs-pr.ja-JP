---
title: コンテンツの廃棄
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
description: 構成した設定に従って、廃棄レビューを使用するか、コンテンツを自動的に削除するかにかかわらず、コンテンツの廃棄を監視および管理します。
ms.openlocfilehash: 56eed956e4488932b7bf0f29eb3810964b8cb425
ms.sourcegitcommit: 3274b65a3932288721541d2b3fa5ecbf4c51e1ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702561"
---
# <a name="disposition-of-content"></a><span data-ttu-id="f4c38-103">コンテンツの廃棄</span><span class="sxs-lookup"><span data-stu-id="f4c38-103">Disposition of content</span></span>

><span data-ttu-id="f4c38-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f4c38-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f4c38-105">Microsoft 365 コンプライアンスセンターの**レコード管理**の [**廃棄**] タブを使用して、廃棄レビューを管理し、保持期間の最後に自動的に削除された[レコード](records.md)を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="f4c38-106">コンテンツの廃棄を表示するための前提条件</span><span class="sxs-lookup"><span data-stu-id="f4c38-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="f4c38-107">廃棄レビューを管理し、レコードが削除されたことを確認するには、十分な権限と監査を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="f4c38-108">廃棄のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4c38-108">Permissions for disposition</span></span>

<span data-ttu-id="f4c38-109">Microsoft 365 コンプライアンスセンターの [**廃棄**] タブに正常にアクセスするには、ユーザーは**廃棄管理**役割と**表示専用の監査ログ**の役割を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="f4c38-110">既定の役割グループにユーザーを追加することを標準としていますが、この場合は、次の2つの役割を持つ**廃棄レビュー担当者**という新しい役割グループを作成し、必要に応じてこのグループにユーザーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f4c38-110">Although the standard advice is to add users to the default role groups, in this case, we recommend you create a new role group called **Disposition Reviewers** that has these two roles and add users to this group as needed.</span></span> <span data-ttu-id="f4c38-111">廃棄に対して単一の役割グループを使用すると、管理のオーバーヘッドが減少し、ユーザーが必要とするアクセス許可をより簡単に管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-111">A single role group for disposition reduces administration overheads and makes it easier for users have the combined permissions that they need.</span></span>

> [!NOTE]
> <span data-ttu-id="f4c38-112">グローバル管理者であっても、**廃棄管理**役割を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> <span data-ttu-id="f4c38-113">したがって、全体管理者が [廃棄] タブにアクセスする必要がある場合は、**廃棄レビュー担当者**の役割グループのメンバーとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-113">So if global admins need to access the disposition tab, them as members of the **Disposition Reviewers** role group.</span></span> 

<span data-ttu-id="f4c38-114">**表示のみの監査ログ**の役割に固有です。</span><span class="sxs-lookup"><span data-stu-id="f4c38-114">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="f4c38-115">監査ログの検索に使用される基礎となるコマンドレットは Exchange Online コマンドレットなので、セキュリティ & コンプライアンスセンターの [**アクセス許可**] ページではなく、exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)を使用してユーザーを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-115">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="f4c38-116">手順については、「 [Manage role groups In Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4c38-116">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="f4c38-117">この役割では、Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f4c38-117">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="f4c38-118">代わりに、ユーザーメールボックス、メールユーザー、またはメールが有効なセキュリティグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-118">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="f4c38-119">**廃棄管理**役割をユーザーに付与し、新しい**廃棄レビュー担当者**の役割を作成する手順については、「 [Office 365 セキュリティ &amp; コンプライアンスセンターへのアクセス権をユーザーに](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)付与する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4c38-119">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="f4c38-120">監査を有効にする</span><span class="sxs-lookup"><span data-stu-id="f4c38-120">Enable auditing</span></span>

<span data-ttu-id="f4c38-121">最初の廃棄アクションの1日以上前に監査が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-121">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="f4c38-122">詳細については、「 [Office 365 セキュリティ &amp; コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4c38-122">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="f4c38-123">廃棄確認</span><span class="sxs-lookup"><span data-stu-id="f4c38-123">Disposition reviews</span></span>

<span data-ttu-id="f4c38-124">コンテンツが保存期間の最後に達すると、いくつかの理由から、そのコンテンツを確認して、安全に削除できるかどうかを判断する必要があります (「廃棄済み」)。</span><span class="sxs-lookup"><span data-stu-id="f4c38-124">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="f4c38-125">たとえば、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-125">For example, you might need to:</span></span>
  
- <span data-ttu-id="f4c38-126">訴訟または監査の際に、関連するコンテンツの削除を中断します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-126">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="f4c38-127">コンテンツにリサーチまたは履歴の値がある場合は、廃棄リストからコンテンツを削除してアーカイブに保存します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-127">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="f4c38-128">元の保持設定が一時または暫定ソリューションだったために、コンテンツに異なる保存期間を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-128">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="f4c38-129">クライアントにコンテンツを返すか、または別の組織に転送します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-129">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="f4c38-130">保持期間の終了時に廃棄レビューがトリガーされた場合:</span><span class="sxs-lookup"><span data-stu-id="f4c38-130">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="f4c38-131">選択したユーザーには、閲覧するコンテンツがあることを示す電子メール通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-131">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="f4c38-132">これらのレビュー担当者は、個別のユーザー、配布グループまたはセキュリティグループ、または Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-132">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="f4c38-133">通知は週単位で送信されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f4c38-133">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="f4c38-134">レビュー担当者は、Microsoft 365 コンプライアンスセンターの [**廃棄**] タブに移動してコンテンツを確認し、完全に削除するか、保持期間を延長するか、または別の保持ラベルを適用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-134">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="f4c38-135">廃棄レビューには、Exchange メールボックス、SharePoint サイト、OneDrive アカウント、Microsoft 365 グループのコンテンツを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-135">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="f4c38-136">これらの場所の廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-136">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="f4c38-137">廃棄レビューをサポートするには、メールボックスに 10 MB 以上のデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="f4c38-137">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="f4c38-138">[**概要**] タブに、保留中のすべての実行の概要が表示されます。例えば：</span><span class="sxs-lookup"><span data-stu-id="f4c38-138">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![レコード管理の保留中の廃棄の概要](../media/dispositions-overview.png)

<span data-ttu-id="f4c38-140">[**保留中のすべて**の処理を表示] を選択すると、[**ディスポジション**] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-140">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="f4c38-141">例:</span><span class="sxs-lookup"><span data-stu-id="f4c38-141">For example:</span></span>

![Microsoft 365 コンプライアンスセンターの [配置] ページ](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="f4c38-143">廃棄レビューのワークフロー</span><span class="sxs-lookup"><span data-stu-id="f4c38-143">Workflow for a disposition review</span></span>

<span data-ttu-id="f4c38-144">これは、保持ラベルが公開され、ユーザーによって手動で適用されるときの、廃棄レビューの基本的なワークフローです。</span><span class="sxs-lookup"><span data-stu-id="f4c38-144">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="f4c38-145">または、廃棄レビュー用に構成された保持ラベルをコンテンツに自動的に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-145">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![廃棄のしくみを示す図](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="f4c38-147">保持期間の最後に廃棄レビューをトリガーすることは、[保持ラベル](labels.md)でのみ使用可能な構成オプションです。</span><span class="sxs-lookup"><span data-stu-id="f4c38-147">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="f4c38-148">このオプションは、アイテム保持ポリシーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f4c38-148">This option is not available in a retention policy.</span></span>
  
![ラベルの保持設定](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="f4c38-150">[レビューの準備が**できたアイテムがあるときにこれらのユーザーに通知**する] オプションを選択した場合は、ユーザーまたはメールが有効なセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-150">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="f4c38-151">このオプションでは、Microsoft 365 グループ ([以前の Office 365 グループ](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f4c38-151">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="f4c38-152">コンテンツの表示と破棄</span><span class="sxs-lookup"><span data-stu-id="f4c38-152">Viewing and disposing of content</span></span>

<span data-ttu-id="f4c38-153">コンテンツのレビューの準備ができたことをレビュー担当者に電子メールで通知する場合は、Microsoft 365 コンプライアンスセンターの [**レコード管理**] の [**廃棄**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-153">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f4c38-154">レビュー担当者は、廃棄を待機している各保持ラベルのアイテム数を確認し、そのラベルを持つすべてのコンテンツを表示する保持ラベルを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-154">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="f4c38-155">保持ラベルを選択すると、[**保留中の廃棄**] タブからそのラベルの保留中のすべての実行が表示されます。1つまたは複数のアイテムを選択して、アクションを選択し、ジャスティフィケーションコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-155">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![ディスポジションオプション](../media/retention-disposition-options.png)

<span data-ttu-id="f4c38-157">画像からわかるように、サポートされているアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f4c38-157">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="f4c38-158">アイテムを完全に削除する</span><span class="sxs-lookup"><span data-stu-id="f4c38-158">Permanently delete the item</span></span>
- <span data-ttu-id="f4c38-159">保持期間を延長する</span><span class="sxs-lookup"><span data-stu-id="f4c38-159">Extend the retention period</span></span>
- <span data-ttu-id="f4c38-160">別の保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="f4c38-160">Apply a different retention label</span></span>

<span data-ttu-id="f4c38-161">場所とコンテンツへのアクセス許可が付与されている場合は、[**場所**] 列のリンクを使用して、ドキュメントを元の場所に表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-161">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="f4c38-162">廃棄レビュー中は、コンテンツは元の場所から移動されません。また、レビュー担当者がそのように選択しない限り、削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f4c38-162">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="f4c38-163">電子メール通知は、1週間ごとにレビュー担当者に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-163">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="f4c38-164">このスケジュールされたプロセスは、コンテンツが保持期間の最後に達すると、レビュー担当者がコンテンツが廃棄を待機しているメール通知を受け取るまでに最大7日かかる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-164">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="f4c38-165">すべての廃棄操作を監査することができ、レビュー担当者によって入力された妥当性テキストが保存され、[**廃棄済みアイテム**] ページの [**コメント**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-165">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="f4c38-166">破棄されたコンテンツが完全に削除されるまでの時間</span><span class="sxs-lookup"><span data-stu-id="f4c38-166">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="f4c38-167">廃棄レビューを待機しているコンテンツは、レビュー担当者がコンテンツを完全に削除することを選択した場合にのみ削除されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-167">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="f4c38-168">レビュー担当者がこのオプションを選択すると、SharePoint サイトまたは OneDrive アカウントのコンテンツは、[保持ポリシーがコンテンツをインプレースでどのように動作するか](retention-policies.md#how-a-retention-policy-works-with-content-in-place)について説明されている標準的なクリーンアッププロセスの対象となります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-168">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="f4c38-169">レコードの廃棄</span><span class="sxs-lookup"><span data-stu-id="f4c38-169">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="f4c38-170">廃棄レビューなしで自動的に削除されたレコードを表示する機能は、4月と2020年5月にテナントに段階的にロールアウトされるため、すぐに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4c38-170">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="f4c38-171">[**レコード管理**] ページの [**廃棄**] タブを使用して、自動的に削除されたレコードを識別します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-171">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="f4c38-172">これらのアイテムは、[**種類**] 列に破棄された**レコード**を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4c38-172">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="f4c38-173">例:</span><span class="sxs-lookup"><span data-stu-id="f4c38-173">For example:</span></span>

![廃棄レビューなしで破棄されたアイテム](../media/records-disposed2.png)

<span data-ttu-id="f4c38-175">レコードラベルの [廃棄済み**アイテム**] タブに表示されているアイテムは、アイテムが破棄されてから7年後に保持され、その期間のレコードごとに最大で100万アイテムが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-175">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="f4c38-176">この制限値である100万に近い**カウント**数が表示され、レコードの廃棄の証明が必要な場合は、 [Microsoft サポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f4c38-176">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="f4c38-177">この機能は、[統合監査ログ](search-the-audit-log-in-security-and-compliance.md)からの情報に基づいているため、監査を[有効にして検索](turn-audit-log-search-on-or-off.md)可能にする必要があります。これにより、対応するイベントがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-177">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="f4c38-178">ビューをフィルター処理してエクスポートする</span><span class="sxs-lookup"><span data-stu-id="f4c38-178">Filter and export the views</span></span>

<span data-ttu-id="f4c38-179">**ディスポジション**ページから保持ラベルを選択すると、[**保留中の廃棄**] タブ (該当する場合) および [破棄された**アイテム**] タブを使用して、アイテムを見つけやすくするためのビューをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-179">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="f4c38-180">保留中の処理の場合、時間の範囲は有効期限に基づきます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-180">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="f4c38-181">破棄されたアイテムの場合、時間範囲は、削除日に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f4c38-181">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="f4c38-182">どちらのビューのアイテムに関する情報を .csv ファイルとしてエクスポートすると、Excel を使用して並べ替えや管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f4c38-182">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![廃棄のエクスポートオプション](../media/retention-export-option.png)
  
![Excel でエクスポートされた廃棄データ](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


