---
title: クラウド メールボックスの保留リストの回復可能なアイテム フォルダー内のアイテムを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 管理者がユーザーの回復可能なアイテム フォルダー内のアイテムを Exchange Online メールボックスに対して削除する方法について説明します(そのメールボックスが法的に保持されている場合でも)。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 776113bcd6141c4f01c2da61f0bd71f99cffd3e2
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326644"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="02f0f-103">保留中のクラウド ベースのメールボックスの 回復可能なアイテム フォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="02f0f-104">偶発的または悪意のある削除から保護Exchange Onlineメールボックスの回復可能なアイテム フォルダーが存在します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="02f0f-105">また、保持機能や電子情報開示検索などのコンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="02f0f-106">ただし、組織によっては、削除する必要がある回復可能なアイテム フォルダーに意図せずに保持されたデータがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="02f0f-107">たとえば、ユーザーが知らないうちに、ビジネスに重大な影響を与える可能性がある機密情報や情報を含む電子メール メッセージを送信または転送する場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="02f0f-108">メッセージが完全に削除された場合でも、メールボックスに法的な保留が設定されたため、メッセージは無期限に保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="02f0f-109">このシナリオは *、データが* 意図せずにデータに流出したため、データ流出と呼Office 365。</span><span class="sxs-lookup"><span data-stu-id="02f0f-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="02f0f-110">このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテム フォルダー内のアイテムを削除できます 。Office 365 で保持機能が異なる場合でも、そのメールボックスを保留にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="02f0f-111">これらの種類の保持には、Office 365 または Microsoft 365 のセキュリティとコンプライアンス センターで作成された訴訟ホールド、In-Place 保持、電子情報開示保持、保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>

<span data-ttu-id="02f0f-112">この記事では、管理者が保留状態のクラウドベースのメールボックスの回復可能なアイテム フォルダーからアイテムを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="02f0f-113">この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダー アシスタントによるメールボックスの処理を無効にし、保留リストを一時的に削除し、回復可能なアイテム フォルダーからアイテムを削除し、メールボックスを以前の構成に戻します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="02f0f-114">このプロセスは次の手順で行います。</span><span class="sxs-lookup"><span data-stu-id="02f0f-114">Here's the process:</span></span>
  
[<span data-ttu-id="02f0f-115">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="02f0f-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="02f0f-116">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="02f0f-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="02f0f-117">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="02f0f-118">手順 4: メールボックスから遅延ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="02f0f-119">手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="02f0f-120">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="02f0f-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="02f0f-121">この記事で説明する手順では、データがメールボックスから完全に削除 (削除) されるExchange Onlineされます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="02f0f-122">つまり、[回復可能なアイテム] フォルダーから削除したメッセージは回復できないので、法的な検出や他のコンプライアンスの目的では使用できません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="02f0f-123">セキュリティとコンプライアンス センターで作成された訴訟ホールド、In-Place ホールド、電子情報開示ホールド、または保持ポリシーの一部として保留にされているメールボックスからメッセージを削除する場合は、保留を削除する前にレコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="02f0f-124">組織には、メールボックスを保留にするか、データ流出インシデントが優先されるのかを定義するポリシーがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="02f0f-125">アイテムを削除する前に</span><span class="sxs-lookup"><span data-stu-id="02f0f-125">Before you delete items</span></span>

- <span data-ttu-id="02f0f-126">コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="02f0f-127">メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="02f0f-128">ユーザーを役割グループに追加する方法の詳細については、「[セキュリティ/コンプライアンス センターの電子情報開示のアクセス許可を割り当てる](./assign-ediscovery-permissions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](./assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="02f0f-129">この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="02f0f-130">これは、非アクティブなメールボックスを削除した後に、保持 (または保持ポリシー) を再適用できないためです。</span><span class="sxs-lookup"><span data-stu-id="02f0f-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="02f0f-131">非アクティブなメールボックスから保留リストを削除すると、そのメールボックスは通常の削除済みメールボックスに変更され、管理フォルダー アシスタントによって処理された後、組織から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="02f0f-132">保持設定が割り当てられているメールボックスに対して、保持ロックを使用してロックされているポリシーでこの手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="02f0f-133">これは、このロックによって、ポリシーからメールボックスを削除または除外したり、メールボックスの管理フォルダー アシスタントを無効にしたりしないのでです。</span><span class="sxs-lookup"><span data-stu-id="02f0f-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="02f0f-134">保持ポリシーのロックの詳細については、「保持ロックを使用してアイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する」 [を参照してください](retention-preservation-lock.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="02f0f-135">メールボックスが保留 (または単一アイテムの回復が有効になっていない) 場合は、[回復可能なアイテム] フォルダーからアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-136">これを行う方法の詳細については、「組織内の電子メール メッセージを検索および削除する」 [を参照してください](./search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-136">For more information about how to do this, see [Search for and delete email messages in your organization](./search-for-and-delete-messages-in-your-organization.md).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="02f0f-137">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="02f0f-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="02f0f-138">この最初の手順は、この手順に影響を与えるターゲット メールボックスから選択したプロパティを収集します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="02f0f-139">これらの設定の一部を変更し、回復可能なアイテム フォルダーからアイテムを削除した後、手順 6 で元の値に戻すので、これらの設定を書き込むか、テキスト ファイルに保存してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-140">収集する必要があるメールボックスのプロパティの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="02f0f-141">*SingleItemRecoveryEnabled および*  *RetainDeletedItemsFor*.</span><span class="sxs-lookup"><span data-stu-id="02f0f-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="02f0f-142">必要に応じて、手順 3 で単一の回復を無効にし、削除済みアイテムの保持期間を長くします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="02f0f-143">*LitigationHoldEnabled および*  *InPlaceHolds*.</span><span class="sxs-lookup"><span data-stu-id="02f0f-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="02f0f-144">手順 3 で一時的にメールボックスを削除するには、メールボックスに配置されている保留リストを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="02f0f-145">メールボックスに [配置される可能性](#more-information) がある種類の保持を特定する方法のヒントについては、「詳細」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="02f0f-146">また、この手順で所有者 (または他のユーザー) がメールボックスにアクセスできない状態で一時的に無効にできるよう、メールボックス クライアント アクセス設定を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="02f0f-147">最後に、回復可能なアイテム フォルダー内のアイテムの現在のサイズと数を取得できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-148">手順 5 の [回復可能なアイテム] フォルダー内のアイテムを削除した後、この情報を使用してアイテムが削除されたのを確認します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="02f0f-149">[Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-149">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="02f0f-150">管理者アカウントで適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="02f0f-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="02f0f-151">次のコマンドを実行して、単一アイテムの回復と削除済みアイテムの保持期間に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="02f0f-152">単一アイテムの回復が有効になっている場合は、手順 2 で無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="02f0f-153">削除されたアイテムの保持期間が 30 日間 (Exchange Online の最大値) に設定されていない場合は、手順 2 で増やします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="02f0f-154">次のコマンドを実行して、メールボックスのメールボックス アクセス設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="02f0f-155">手順 2 で、これらすべてのアクセス方法を無効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="02f0f-156">次のコマンドを実行して、メールボックスに適用される保持ポリシーと保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

    > [!TIP]
    > <span data-ttu-id="02f0f-157">*InPlaceHolds* プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各値を個別の行 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` に表示できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="02f0f-158">次のコマンドを実行して、組織全体の保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="02f0f-159">組織に組織全体の保持ポリシーがある場合は、手順 3 でこれらのポリシーからメールボックスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span> <span data-ttu-id="02f0f-160">変更のレプリケートには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-160">It may take up to 24 hours to replicate the change.</span></span>

    > [!TIP]
    > <span data-ttu-id="02f0f-161">*InPlaceHolds* プロパティに値が多すぎて、すべての値が表示されない場合は、コマンドを実行して各値を個別の行 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` に表示できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-161">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="02f0f-162">次のコマンドを実行して、メールボックスに遅延ホールドが適用されるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-162">Run the following command to determine if a delay hold is applied to the mailbox.</span></span>

   ```powershell
   Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
   ```

   <span data-ttu-id="02f0f-163">*DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、メールボックスに遅延ホールドが適用され、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-163">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, a delay hold is applied to the mailbox and must be removed.</span></span> <span data-ttu-id="02f0f-164">遅延ホールドの詳細については、「手順 [4: メールボックス](#step-4-remove-the-delay-hold-from-the-mailbox)から遅延ホールドを削除する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-164">For more information about delay holds, see [Step 4: Remove the delay hold from the mailbox](#step-4-remove-the-delay-hold-from-the-mailbox).</span></span>

   <span data-ttu-id="02f0f-165">いずれかのプロパティの値が **False** に設定されている場合は、メールボックスに遅延ホールドが適用されないので、手順 4 をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-165">If the value of either properties is set to **False**, a delay hold is not applied to the mailbox, and you can skip Step 4.</span></span>

7. <span data-ttu-id="02f0f-166">次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと総数を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-166">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="02f0f-167">ユーザーのアーカイブ メールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブ メールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと総数を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-167">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="02f0f-168">手順 5 でアイテムを削除すると、ユーザーのプライマリ アーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムを削除するか削除しないか選択できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-168">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="02f0f-169">メールボックスに対して自動拡張アーカイブが有効になっている場合、補助アーカイブ メールボックス内のアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-169">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="02f0f-170">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="02f0f-170">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="02f0f-171">メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-171">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="02f0f-172">**メールボックスへのクライアント アクセスを無効** にして、メールボックスの所有者がメールボックスにアクセスして、この手順の間にメールボックス データに変更を加えきらなけい。</span><span class="sxs-lookup"><span data-stu-id="02f0f-172">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="02f0f-173">削除 **済みアイテム** の保持期間を 30 日 (Exchange Online の最大値) に増やして、手順 5 でアイテムを削除する前に[回復可能なアイテム] フォルダーからアイテムが削除されない。</span><span class="sxs-lookup"><span data-stu-id="02f0f-173">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="02f0f-174">**手順** 5 の [回復可能なアイテム] フォルダーからアイテムを削除した後、アイテムを (削除済みアイテムの保持期間の間) 保持しないので、単一のアイテムの回復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-174">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="02f0f-175">**管理フォルダー アシスタントを無効** にして、メールボックスを処理し、手順 5 で削除したアイテムを保持します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-175">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="02f0f-176">PowerShell の次の手順をExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-176">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="02f0f-177">次のコマンドを実行して、メールボックスへのすべてのクライアント アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-177">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="02f0f-178">コマンド構文では、すべてのクライアント アクセス方法がメールボックスで有効になっていると仮定します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-178">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="02f0f-179">メールボックスへのすべてのクライアント アクセス方法を無効にするには、最大 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-179">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="02f0f-180">これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者は切断されません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-180">Note that disabling these access methods won't disconnect the mailbox owner if they are currently signed in.</span></span> <span data-ttu-id="02f0f-181">所有者がサインインしていない場合、これらのアクセス方法が無効にされた後、所有者は自分のメールボックスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-181">If the owner isn't signed in, they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="02f0f-182">次のコマンドを実行して、削除済みアイテムの保持期間を最大 30 日間増やします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-182">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="02f0f-183">これは、現在の設定が 30 日未満である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-183">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="02f0f-184">次のコマンドを実行して、単一アイテムの回復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-184">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

    > [!NOTE]
    > <span data-ttu-id="02f0f-185">単一アイテムの回復を無効にするには、最大 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-185">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="02f0f-186">この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しない。</span><span class="sxs-lookup"><span data-stu-id="02f0f-186">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="02f0f-187">次のコマンドを実行して、管理フォルダー アシスタントがメールボックスを処理できません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-187">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="02f0f-188">前に説明したように、保持ロックを持つアイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダー アシスタントを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-188">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="02f0f-189">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-189">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="02f0f-190">回復可能なアイテム フォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置された (手順 1 で識別した) すべての保留リストを削除します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-190">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="02f0f-191">アイテムを [回復可能なアイテム] フォルダーから削除した後にアイテムを保持しないので、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-191">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-192">次のセクションでは、メールボックスのさまざまな種類の保留リストを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-192">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="02f0f-193">メールボックスに [配置される可能性](#more-information) がある種類の保持を特定する方法のヒントについては、「詳細」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-193">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="02f0f-194">詳細については、「How to identify of hold of placed on the Exchange Online メールボックス 」[を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-194">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="02f0f-195">前に述べたように、メールボックスから保留リストを削除する前に、レコード管理部門または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-195">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="02f0f-196">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="02f0f-196">Litigation Hold</span></span>
  
<span data-ttu-id="02f0f-197">PowerShell で次のコマンドをExchange Onlineメールボックスから訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-197">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="02f0f-198">クライアント アクセス方法の無効化や単一アイテムの回復と同様に、訴訟ホールドを削除するには最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-198">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="02f0f-199">この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しない。</span><span class="sxs-lookup"><span data-stu-id="02f0f-199">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="02f0f-200">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="02f0f-200">In-Place Hold</span></span>
  
<span data-ttu-id="02f0f-201">PowerShell で次のコマンドExchange Online実行して、メールボックスにIn-Place保持するサーバーを識別します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-201">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="02f0f-202">手順 1 で特定In-Place保持の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-202">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="02f0f-203">保留リストをIn-Placeした後、Exchange 管理センター (EAC) または powerShell Exchange Online を使用して、メールボックスを保留リストから削除できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-203">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="02f0f-204">詳細については、「Create [or remove an In-Place Hold 」を参照してください](/exchange/security-and-compliance/create-or-remove-in-place-holds)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-204">For more information, see [Create or remove an In-Place Hold](/exchange/security-and-compliance/create-or-remove-in-place-holds).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="02f0f-205">特定のメールボックスに適用されるアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="02f0f-205">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="02f0f-206">セキュリティ センター PowerShell で次& [コマンドを](/powershell/exchange/exchange-online-powershell) 実行して、メールボックスに適用されるアイテム保持ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-206">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="02f0f-207">このコマンドは、メールボックスに適用Teams保持ポリシーを返します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-207">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="02f0f-208">手順 1 で識別したアイテム保持ポリシーの GUID (プレフィックスは含めない `mbx` `skp` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-208">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="02f0f-209">アイテム保持ポリシーを特定した後、セキュリティ& コンプライアンス センターの [情報ガバナンス保持] ページに移動し、前の手順で識別したアイテム保持ポリシーを編集し、保持ポリシーに含まれる受信者の一覧からメールボックスを削除します。  >  </span><span class="sxs-lookup"><span data-stu-id="02f0f-209">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="02f0f-210">組織全体に対するアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="02f0f-210">Organization-wide retention policies</span></span>
  
<span data-ttu-id="02f0f-211">組織全体、Exchange、Teams全体の保持ポリシーは、組織内のすべてのメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-211">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="02f0f-212">これらは組織レベル (メールボックス レベルではなく) で適用され、手順 1 で **Get-OrganizationConfig** コマンドレットを実行すると返されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-212">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="02f0f-213">コンプライアンス センター PowerShell のセキュリティ & [コマンドを](/powershell/exchange/exchange-online-powershell) 実行して、組織全体の保持ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-213">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="02f0f-214">手順 1 で特定した組織全体の保持ポリシーの GUID (プレフィックスを含む  `mbx` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-214">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="02f0f-215">組織全体の保持ポリシーを特定した後、セキュリティ  >  & コンプライアンス センターの [情報ガバナンス保持] ページに移動し、前の手順で特定した組織全体の保持ポリシーを編集し、除外された受信者の一覧にメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-215">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="02f0f-216">これにより、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-216">Doing this will remove the user's mailbox from the retention policy.</span></span> <span data-ttu-id="02f0f-217">変更のレプリケートには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-217">It may take up to 24 hours to replicate the change.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="02f0f-218">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="02f0f-218">Retention labels</span></span>

<span data-ttu-id="02f0f-219">ユーザーがコンテンツを保持するか、保持し、メールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように構成されたラベルを適用するたびに *、ComplianceTagHoldApplied* メールボックス プロパティは **True** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-219">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="02f0f-220">この場合、メールボックスは訴訟ホールドに置かれたか、保持ポリシーに割り当てられているかのように、保留と見なされます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-220">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="02f0f-221">*ComplianceTagHoldApplied* プロパティの値を表示するには、PowerShell で次Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-221">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="02f0f-222">保持ラベルがフォルダーまたはアイテムに適用されたため、メールボックスが保留状態であることを確認した後、セキュリティとコンプライアンス センターのコンテンツ検索ツールを使用して、ComplianceTag 検索条件を使用してラベル付きアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-222">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="02f0f-223">詳細については、「コンテンツ検索のキーワード クエリと検索条件」の「 [検索条件」セクションを参照してください](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-223">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="02f0f-224">ラベルの詳細については、「アイテム保持ポリシーと [保持ラベルについて」を参照してください](retention.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-224">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="02f0f-225">電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="02f0f-225">eDiscovery holds</span></span>
  
<span data-ttu-id="02f0f-226">セキュリティ & コンプライアンス センター [PowerShell](/powershell/exchange/connect-to-scc-powershell) で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース (電子情報開示ホールドと呼 *ばれる)* に関連付けられている保留リストを識別します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-226">Run the following commands in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="02f0f-227">手順 1 で識別した電子情報開示ホールドの GUID (プレフィックスを含む  `UniH` ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-227">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="02f0f-228">2 番目のコマンドは、保留リストが関連付けられている電子情報開示ケースの名前を表示します。3 番目のコマンドは、保留リストの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-228">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="02f0f-229">電子情報開示ケースと保留リストの名前を特定した後、コンプライアンス センターの電子情報開示電子情報開示ページに移動し、ケースを開き、メールボックスを保留リストから削除します \> 。</span><span class="sxs-lookup"><span data-stu-id="02f0f-229">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="02f0f-230">電子情報開示の保持を識別する方法の詳細については、「電子情報開示の保持」セクション「電子情報開示メールボックスに配置された保留の種類を識別する方法」[をExchange Onlineしてください](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-230">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="02f0f-231">手順 4: メールボックスから遅延ホールドを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-231">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="02f0f-232">メールボックスから任意の種類の保留リストを削除すると *、DelayHoldApplied* または *DelayReleaseHoldApplied* メールボックス プロパティの値が True に設定 **されます**。</span><span class="sxs-lookup"><span data-stu-id="02f0f-232">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="02f0f-233">これは、次に管理フォルダー アシスタントがメールボックスを処理し、保留リストが削除されたと検出した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-233">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="02f0f-234">これは遅延保留と呼ばれて、メールボックスからデータが完全に削除されるのを防ぐために、実際の保留の削除が 30 日間遅れることを意味します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-234">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="02f0f-235">(遅延ホールドの目的は、管理者に、保留リストが削除された後に削除されるメールボックス アイテムを検索または回復する機会を与える目的です。 メールボックスに遅延ホールドが設定されている場合でも、メールボックスが訴訟ホールドの対象である場合と同様に、メールボックスは無制限の期間保留であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-235">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="02f0f-236">30 日後に遅延保留が期限切れになると、Microsoft 365 は遅延ホールドを自動的に削除します *(DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティを **False** に設定することで) 保留が削除されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-236">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="02f0f-237">遅延ホールドの詳細については、「方法[Exchange Online」](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)の「遅延ホールド時のメールボックスの管理」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-237">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="02f0f-238">*DelayHoldApplied* プロパティまたは *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、次のいずれかのコマンドを実行して遅延ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-238">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="02f0f-239">または</span><span class="sxs-lookup"><span data-stu-id="02f0f-239">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="02f0f-240">*RemoveDelayHoldApplied* または *RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Onlineで法的保持ロールを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-240">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="02f0f-241">手順 5: 回復可能なアイテム フォルダー内のアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="02f0f-241">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="02f0f-242">セキュリティ & コンプライアンス センター PowerShell の [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) コマンドレットと [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムを実際に削除する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="02f0f-242">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="02f0f-243">回復可能なアイテム フォルダーにあるアイテムを検索するには、対象のコレクションを実行することをお *勧めします*。</span><span class="sxs-lookup"><span data-stu-id="02f0f-243">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="02f0f-244">つまり、検索範囲を [回復可能なアイテム] フォルダーにあるアイテムにのみ絞り込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-244">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-245">これを行うには、「対象のコレクションにコンテンツ検索を使用する」の記事 [でスクリプトを実行](use-content-search-for-targeted-collections.md) します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-245">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="02f0f-246">このスクリプトは、ターゲットの回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-246">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-247">次に、検索クエリのフォルダー ID を使用して、そのフォルダー内にあるアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-247">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="02f0f-248">ユーザーの回復可能なアイテム フォルダー内のアイテムを検索および削除するプロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-248">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="02f0f-249">ターゲット ユーザーのメールボックス内のすべてのフォルダーのフォルダー ID を返すターゲット コレクション スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-249">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="02f0f-250">スクリプトは、同じ PowerShell セッションExchange Online PowerShell とセキュリティ &コンプライアンス PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-250">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="02f0f-251">詳細については、「スクリプトを [実行してメールボックスのフォルダーの一覧を取得する」を参照してください](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-251">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="02f0f-252">回復可能なアイテム フォルダー内のすべてのサブフォルダーのフォルダー ID をコピーします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-252">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-253">または、スクリプトの出力をテキスト ファイルにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-253">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="02f0f-254">アイテムを検索および削除できる回復可能なアイテム フォルダー内のサブフォルダーの一覧と説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-254">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="02f0f-255">**削除 :** 削除済みアイテムの保持期間が経過していない、削除済みアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-255">**Deletions**: Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="02f0f-256">ユーザーは、このサブフォルダーの [削除済みアイテムの回復] ツールを使用して、このサブフォルダーから削除済みアイテムを回復Outlook。</span><span class="sxs-lookup"><span data-stu-id="02f0f-256">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="02f0f-257">**削除 :** 削除済みアイテムの保持期間が経過した、ハード削除されたアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-257">**Purges**: Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="02f0f-258">ユーザーは、回復可能なアイテム フォルダーからアイテムを削除することで、アイテムをハード削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-258">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-259">メールボックスが保持されている場合、ハード削除されたアイテムは保持されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-259">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="02f0f-260">このサブフォルダーはエンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="02f0f-261">**DiscoveryHolds**: 電子情報開示ホールドまたはアイテム保持ポリシーによって保持されている、ハード削除されたアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-261">**DiscoveryHolds**: Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="02f0f-262">このサブフォルダーはエンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-262">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="02f0f-263">**SubstrateHolds**: 保持ポリシーまたは他の種類の保留によって保持されている Teams および他のクラウドベースのアプリからのハード削除されたアイテムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-263">**SubstrateHolds**: Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="02f0f-264">このサブフォルダーはエンド ユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="02f0f-264">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="02f0f-265">**New-ComplianceSearch** コマンドレット (セキュリティ & コンプライアンス センター PowerShell) を使用するか、コンプライアンス センターのコンテンツ検索ツールを使用して、ターゲット ユーザーの回復可能なアイテム フォルダーからアイテムを返すコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-265">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-266">これを行うには、検索するサブフォルダーの検索クエリに FolderId を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-266">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="02f0f-267">たとえば、次のクエリは、Purges サブフォルダーと eDiscoveryHolds サブフォルダー内のすべてのメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-267">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="02f0f-268">フォルダー ID プロパティを使用するコンテンツ検索の実行の詳細と例については、「フォルダー ID を使用する」または「対象となるコレクションを実行する」 [を参照してください](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-268">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="02f0f-269">**New-ComplianceSearch** コマンドレットを使用して回復可能なアイテム フォルダーを検索する場合は **、Start-ComplianceSearch** コマンドレットを使用して検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-269">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="02f0f-270">コンテンツ検索を作成し、削除するアイテムが返されたと検証したら、コマンド (セキュリティ & コンプライアンス センター PowerShell) を使用して、前の手順で作成したコンテンツ検索で返されたアイテムを完全に削除します。 `New-ComplianceSearchAction -Purge -PurgeType HardDelete`</span><span class="sxs-lookup"><span data-stu-id="02f0f-270">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="02f0f-271">たとえば、次のようなコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-271">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="02f0f-272">前のコマンドを実行すると、メールボックスごとに最大 10 アイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-272">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="02f0f-273">つまり、[回復可能なアイテム] フォルダーで削除するアイテムを削除するには、コマンドを複数回実行 `New-ComplianceSearchAction -Purge` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-273">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-274">追加のアイテムを削除するには、最初に以前のコンプライアンス検索削除アクションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-274">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="02f0f-275">これを行うには、コマンドレットを実行 `Remove-ComplianceSearchAction` します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-275">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="02f0f-276">たとえば、前の手順で実行した削除アクションを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-276">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="02f0f-277">これを行った後、新しいコンプライアンス検索削除アクションを作成して、より多くのアイテムを削除できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-277">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="02f0f-278">新しい削除アクションを作成する前に、各削除アクションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-278">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="02f0f-279">コンプライアンス検索アクションの一覧を取得するには、コマンドレットを実行 `Get-ComplianceSearchAction` します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-279">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="02f0f-280">削除アクションは、検索名 `_Purge` に追加することで識別されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-280">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="02f0f-281">アイテムが削除されたのを確認する</span><span class="sxs-lookup"><span data-stu-id="02f0f-281">Verify that items were deleted</span></span>

<span data-ttu-id="02f0f-282">メールボックスの回復可能なアイテム フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell の **Get-MailboxFolderStatistics** コマンドレットを使用して、回復可能なアイテム フォルダー内のアイテムのサイズと数を確認します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-282">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="02f0f-283">これらの統計は、手順 1 で収集した統計と比較できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-283">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="02f0f-284">次のコマンドを実行して、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと総数を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-284">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="02f0f-285">次のコマンドを実行して、ユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと総数を取得します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-285">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="02f0f-286">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="02f0f-286">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="02f0f-287">最後の手順では、メールボックスを以前の構成に戻します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-287">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="02f0f-288">つまり、手順 2 で変更したプロパティをリセットし、手順 3 で削除した保留リストを再適用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-288">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="02f0f-289">これには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-289">This includes:</span></span>
  
- <span data-ttu-id="02f0f-290">削除済みアイテムの保持期間を以前の値に戻す。</span><span class="sxs-lookup"><span data-stu-id="02f0f-290">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="02f0f-291">または、この設定を 30 日に設定したままにしておき、Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="02f0f-291">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="02f0f-292">単一アイテムの回復を再び有効にする。</span><span class="sxs-lookup"><span data-stu-id="02f0f-292">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="02f0f-293">所有者が自分のメールボックスにアクセスできるよう、クライアント アクセス方法を再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-293">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="02f0f-294">削除した保持ポリシーと保持ポリシーを再適用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-294">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="02f0f-295">管理フォルダー アシスタントを有効にし、メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-295">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02f0f-296">Managed Folder Assistant を再び有効にしてメールボックスを処理する前に、保持ポリシーまたは保持ポリシーを再適用してから 24 時間待機することをお勧めします 。また、そのポリシーが適用されているのを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-296">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="02f0f-297">PowerShell で次の手順 (指定した順序で) をExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-297">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="02f0f-298">次のコマンドを実行して、削除されたアイテムの保持期間を元の値に戻します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-298">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="02f0f-299">これは、前の設定が 30 日未満である必要があります。たとえば、14 日間です。</span><span class="sxs-lookup"><span data-stu-id="02f0f-299">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="02f0f-300">次のコマンドを実行して、単一アイテムの回復を再び有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-300">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="02f0f-301">次のコマンドを実行して、メールボックスへのすべてのクライアント アクセス方法を再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-301">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="02f0f-302">手順 3 で削除した保留リストを再適用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-302">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="02f0f-303">保留の種類に応じて、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-303">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="02f0f-304">**訴訟ホールド**</span><span class="sxs-lookup"><span data-stu-id="02f0f-304">**Litigation Hold**</span></span>

    <span data-ttu-id="02f0f-305">次のコマンドを実行して、メールボックスの訴訟ホールドを再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-305">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="02f0f-306">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="02f0f-306">**In-Place Hold**</span></span>

    <span data-ttu-id="02f0f-307">EAC (または Exchange Online PowerShell) を使用して、メールボックスを保留リストにIn-Placeします。</span><span class="sxs-lookup"><span data-stu-id="02f0f-307">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="02f0f-308">**特定のメールボックスに適用されるアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="02f0f-308">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="02f0f-309">セキュリティ コンプライアンス センター&使用して、メールボックスをアイテム保持ポリシーに追加し戻します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-309">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="02f0f-310">セキュリティ &コンプライアンス センターの [情報ガバナンス保持] ページに移動し、保持ポリシーを編集し、保持ポリシーが適用されている受信者の一覧にメールボックスを追加し戻  >  します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-310">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="02f0f-311">**組織全体の保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="02f0f-311">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="02f0f-312">組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、セキュリティ & コンプライアンス センターを使用して、除外されたユーザーの一覧からメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-312">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="02f0f-313">セキュリティ &コンプライアンス センターの [情報ガバナンス保持] ページに移動し、組織全体の保持ポリシーを編集し、除外された受信者の一覧からメールボックスを  >  削除します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-313">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="02f0f-314">これにより、アイテム保持ポリシーがユーザーのメールボックスに再適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-314">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="02f0f-315">**電子情報開示ケースホールド**</span><span class="sxs-lookup"><span data-stu-id="02f0f-315">**eDiscovery case holds**</span></span>

    <span data-ttu-id="02f0f-316">セキュリティ コンプライアンス センター&使用して、電子情報開示ケースに関連付けられている保留リストをメールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-316">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="02f0f-317">[電子情報開示 **の電子情報開示**  >  **] ページに** 移動し、ケースを開き、メールボックスを保留リストに戻します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-317">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="02f0f-318">次のコマンドを実行して、管理フォルダー アシスタントがメールボックスを再度処理できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-318">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="02f0f-319">前に述べたように、Managed Folder Assistant を再び有効にする前に、保持ポリシーまたは保持ポリシーを再適用してから 24 時間待機することをお勧めします (また、そのポリシーが適用されているのを確認してください)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-319">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="02f0f-320">メールボックスが以前の構成に戻されたのを確認するには、次のコマンドを実行し、手順 1 で収集した設定と比較します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-320">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="02f0f-321">詳細情報</span><span class="sxs-lookup"><span data-stu-id="02f0f-321">More information</span></span>

<span data-ttu-id="02f0f-322">**Get-Mailbox** コマンドレットまたは **Get-OrganizationConfig** コマンドレットを実行するときに *、InPlaceHolds* プロパティの値に基づいてさまざまな種類の保留リストを識別する方法を示す表を次に示します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-322">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="02f0f-323">詳細については、「Exchange Online メールボックスに配置された保留の種類を識別する方法 [」を参照してください](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="02f0f-323">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="02f0f-324">前に説明したように、回復可能なアイテム フォルダー内のアイテムを正常に削除するには、メールボックスからすべての保持ポリシーと保持ポリシーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-324">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="02f0f-325">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="02f0f-325">Hold type</span></span> | <span data-ttu-id="02f0f-326">値の例</span><span class="sxs-lookup"><span data-stu-id="02f0f-326">Example value</span></span> | <span data-ttu-id="02f0f-327">保留を識別する方法</span><span class="sxs-lookup"><span data-stu-id="02f0f-327">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="02f0f-328">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="02f0f-328">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="02f0f-329">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="02f0f-329">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="02f0f-330">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="02f0f-330">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="02f0f-331">*InPlaceHolds* プロパティには、メールボックスにIn-Place保持の GUID が含まれる。</span><span class="sxs-lookup"><span data-stu-id="02f0f-331">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="02f0f-332">GUID はプレフィックスで始In-Place、これは保留の一部です。</span><span class="sxs-lookup"><span data-stu-id="02f0f-332">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="02f0f-333">Exchange Online PowerShell のコマンドを使用して、メールボックスの保持に関  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` するIn-Placeを取得できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-333">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="02f0f-334">特定のメールボックスに適用されるセキュリティ &コンプライアンス センターのアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="02f0f-334">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="02f0f-335">または</span><span class="sxs-lookup"><span data-stu-id="02f0f-335">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="02f0f-336">**Get-Mailbox コマンドレットを実行** すると *、InPlaceHolds* プロパティには、メールボックスに適用される保持ポリシーの GUID も含まれる。</span><span class="sxs-lookup"><span data-stu-id="02f0f-336">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="02f0f-337">GUID はプレフィックスで始まるため、保持ポリシーを識別  `mbx` できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-337">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="02f0f-338">保持ポリシーの GUID がプレフィックスで始まる場合、保持ポリシーが Skype for Business の会話  `skp` に適用されます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-338">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="02f0f-339">メールボックスに適用されるアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-339">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="02f0f-340">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-340">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="02f0f-341">セキュリティ コンプライアンス センターの組織全体&ポリシー</span><span class="sxs-lookup"><span data-stu-id="02f0f-341">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="02f0f-342">値なし</span><span class="sxs-lookup"><span data-stu-id="02f0f-342">No value</span></span>  <br/> <span data-ttu-id="02f0f-343">または</span><span class="sxs-lookup"><span data-stu-id="02f0f-343">or</span></span>  <br/>  <span data-ttu-id="02f0f-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (メールボックスが組織全体のポリシーから除外される場合を示します)</span><span class="sxs-lookup"><span data-stu-id="02f0f-344">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="02f0f-345">**Get-Mailbox** コマンドレットを実行するときに *InPlaceHolds* プロパティが空の場合でも、メールボックスに適用される組織全体の保持ポリシーが 1 つ以上存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-345">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="02f0f-346">これを確認するには、Exchange Online PowerShell でコマンドを実行して、組織全体の保持ポリシーの GUID の一覧  `Get-OrganizationConfig | FL InPlaceHolds` を取得できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-346">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="02f0f-347">Exchange メールボックスに適用される組織全体の保持ポリシーの GUID は、プレフィックス (たとえば  `mbx` ) で始まります  `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="02f0f-347">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="02f0f-348">メールボックスに適用される組織全体のアイテム保持ポリシーを識別するには、コンプライアンス センター PowerShell のセキュリティ &コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-348">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="02f0f-349">メールボックスが組織全体のアイテム保持ポリシーから除外されている場合 **、Get-Mailbox** コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの *InPlaceHolds* プロパティに表示されます。プレフィックスによって識別されます `-mbx` 。たとえば、`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="02f0f-349">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="02f0f-350">セキュリティ コンプライアンス センターでの電子情報開示&保持</span><span class="sxs-lookup"><span data-stu-id="02f0f-350">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="02f0f-351">*InPlaceHolds* プロパティには、メールボックスに配置される可能性があるセキュリティ & コンプライアンス センターの電子情報開示ケースに関連付けられた任意のホールドの GUID も含まれる。</span><span class="sxs-lookup"><span data-stu-id="02f0f-351">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="02f0f-352">GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="02f0f-352">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="02f0f-353">セキュリティ センター PowerShell のコマンドレット&使用して、メールボックスの保留が関連付けられている電子情報開示ケースに関する  `Get-CaseHoldPolicy` 情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-353">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="02f0f-354">たとえば、このコマンドを実行して、メールボックス上のケースホールドの  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` 名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="02f0f-354">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="02f0f-355">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="02f0f-355">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="02f0f-356">メールボックスの保留が関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02f0f-356">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
