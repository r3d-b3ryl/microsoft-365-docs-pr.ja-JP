---
title: クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ
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
description: '管理者の場合: Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除します (法的情報保留に設定されている場合も含む)。 これは、Microsoft 365 に誤ってこぼれたデータを削除する効果的な方法です。'
ms.openlocfilehash: 4cf568c06fc3b6ee886ff1823d8771a64c0286d8
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022087"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="64b6e-104">クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="64b6e-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="64b6e-105">Exchange Online メールボックスの回復可能なアイテムフォルダーは、偶発的または悪意のある削除から保護するために存在します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-105">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="64b6e-106">また、保留や電子情報開示の検索など、コンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-106">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="64b6e-107">ただし、状況によっては、削除する必要のある回復可能なアイテムフォルダーに誤って保持されていたデータが組織に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-107">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="64b6e-108">たとえば、ユーザーが気付かないうちに機密情報や情報が含まれる電子メールメッセージを知らずに送信または転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-108">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="64b6e-109">メッセージが完全に削除された場合でも、メールボックスに法的情報保持が設定されているため、無期限に保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-109">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="64b6e-110">このシナリオは、データが Office 365 に誤って含まれていたため、データ流出と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-110">This scenario is known as data spillage because data has been unintentionally spilled into Office 365.</span></span> <span data-ttu-id="64b6e-111">このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除することができます。これは、Office 365 のさまざまな保留機能のいずれかを使用して、そのメールボックスが保持されている場合でも削除できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-111">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="64b6e-112">これらの種類には、訴訟ホールド、インプレースホールド、電子情報開示の保持、および Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成されたアイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-112">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="64b6e-113">この記事では、保留中のクラウドベースのメールボックスの [回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-113">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="64b6e-114">この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダーアシスタントがメールボックスの処理を無効にし、保持を一時的に削除し、回復可能なアイテムフォルダーからアイテムを削除した後、メールボックスを以前の構成に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-114">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="64b6e-115">プロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64b6e-115">Here's the process:</span></span> 
  
[<span data-ttu-id="64b6e-116">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="64b6e-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="64b6e-117">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="64b6e-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="64b6e-118">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="64b6e-119">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="64b6e-120">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="64b6e-121">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="64b6e-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="64b6e-122">この記事に記載されている手順により、Exchange Online メールボックスからデータが完全に削除 (パージ) されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-122">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="64b6e-123">これは、回復可能なアイテムフォルダーから削除されたメッセージを回復できず、法的証拠開示やその他の法令遵守のために利用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-123">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="64b6e-124">セキュリティ/コンプライアンスセンターで作成された訴訟ホールド、インプレースホールド、電子情報開示の保持、またはアイテム保持ポリシーの一部として保留になっているメールボックスからメッセージを削除する場合は、保留リストを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-124">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="64b6e-125">組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-125">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="64b6e-126">はじめに</span><span class="sxs-lookup"><span data-stu-id="64b6e-126">Before you begin</span></span>

- <span data-ttu-id="64b6e-127">コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-127">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="64b6e-128">メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-128">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="64b6e-129">ユーザーを役割グループに追加する方法の詳細については、「[セキュリティ/コンプライアンス センターの電子情報開示のアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-129">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>

- <span data-ttu-id="64b6e-130">この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="64b6e-130">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="64b6e-131">これは、削除した後、非アクティブなメールボックスに保持 (またはアイテム保持ポリシー) を再適用できないためです。</span><span class="sxs-lookup"><span data-stu-id="64b6e-131">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="64b6e-132">非アクティブなメールボックスからホールドを削除すると、その保留中のメールボックスは通常の回復可能な削除によって削除され、管理フォルダーアシスタントによる処理後は組織から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-132">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="64b6e-133">保持ロックでロックされているアイテム保持ポリシーに割り当てられているメールボックスに対してこの手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="64b6e-133">You can't perform this procedure for a mailbox that has been assigned to a retention policy that's been locked with a Preservation Lock.</span></span> <span data-ttu-id="64b6e-134">これは、保持ロックによって、アイテム保持ポリシーからメールボックスを削除または除外したり、メールボックス上の管理フォルダーアシスタントを無効にしたりできないためです。</span><span class="sxs-lookup"><span data-stu-id="64b6e-134">That's because a Preservation Lock prevents you from removing or excluding the mailbox from the retention policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="64b6e-135">保持ポリシーのロックの詳細については、「[アイテム保持ポリシーのロック](retention-policies.md#locking-a-retention-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-135">For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>

- <span data-ttu-id="64b6e-136">メールボックスが保留になっていない (または単一アイテムの回復が有効になっていない) 場合は、回復可能なアイテムフォルダーからアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-136">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="64b6e-137">これを行う方法の詳細については、「[組織内での電子メールメッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-137">For more information about how to do this, see [Search for and delete email messages in your organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="64b6e-138">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="64b6e-138">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="64b6e-139">最初の手順では、この手順に影響する、ターゲットメールボックスから選択したプロパティを収集します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-139">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="64b6e-140">これらのプロパティの一部を変更し、[回復可能なアイテム] フォルダーからアイテムを削除した後に、手順6で元の値に戻すことができるように、これらの設定を書き留めておくか、テキストファイルに保存してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-140">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="64b6e-141">収集する必要があるメールボックスのプロパティの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-141">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="64b6e-142">*Singleitemrecoveryenabled*および*RetainDeletedItemsFor*。</span><span class="sxs-lookup"><span data-stu-id="64b6e-142">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="64b6e-143">必要に応じて、1回の回復を無効にして、手順3で削除済みアイテムの保存期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-143">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 

- <span data-ttu-id="64b6e-144">*LitigationHoldEnabled*および*InPlaceHolds*。</span><span class="sxs-lookup"><span data-stu-id="64b6e-144">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="64b6e-145">手順3で一時的に削除できるように、メールボックスに配置されているすべての保留リストを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-145">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="64b6e-146">メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-146">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 

<span data-ttu-id="64b6e-147">また、この手順の実行中に所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックスクライアントアクセスの設定を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-147">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="64b6e-148">最後に、[回復可能なアイテム] フォルダー内のアイテムの現在のサイズと数を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-148">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="64b6e-149">手順5で [回復可能なアイテム] フォルダーのアイテムを削除した後、この情報を使用してアイテムが削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-149">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="64b6e-150">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="64b6e-150">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="64b6e-151">Exchange Online で適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-151">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="64b6e-152">単一アイテムの回復と削除済みアイテムの保存期間に関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-152">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="64b6e-153">単一アイテムの回復が有効になっている場合は、手順2で無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-153">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="64b6e-154">削除済みアイテムの保存期間が30日間 (Exchange Online の最大値) に設定されていない場合は、手順2で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-154">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="64b6e-155">次のコマンドを実行して、メールボックスのメールボックスアクセス設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-155">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="64b6e-156">手順2では、これらのアクセス方法をすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-156">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="64b6e-157">次のコマンドを実行して、メールボックスに適用されている保留および保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-157">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>
    
    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="64b6e-158">*InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-158">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="64b6e-159">組織全体のアイテム保持ポリシーに関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-159">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   
   <span data-ttu-id="64b6e-160">組織全体のアイテム保持ポリシーを使用している場合は、手順3でこれらのポリシーからメールボックスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-160">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="64b6e-161">*InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-161">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="64b6e-162">次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-162">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="64b6e-163">ユーザーのアーカイブメールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブメールボックス内の [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-163">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="64b6e-164">手順5でアイテムを削除する場合、ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除するか、削除するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-164">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="64b6e-165">メールボックスの自動拡張アーカイブが有効になっている場合、補助アーカイブメールボックス内のアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="64b6e-165">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="64b6e-166">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="64b6e-166">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="64b6e-167">メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-167">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="64b6e-168">メールボックス**へのクライアントアクセスを無効**にして、メールボックスの所有者がメールボックスにアクセスできないようにして、この手順の実行中にメールボックスデータを変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-168">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="64b6e-169">**削除済みアイテムの保存期間**を30日間 (Exchange Online の最大値) に増やして、手順5でアイテムを回復可能なアイテムフォルダーから削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-169">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="64b6e-170">手順5で [回復可能なアイテム] フォルダーからアイテムを削除した後に、アイテムが保持されないように、**単一アイテムの回復を無効**にします (削除済みアイテムの保存期間中)。</span><span class="sxs-lookup"><span data-stu-id="64b6e-170">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="64b6e-171">**管理フォルダーアシスタントを無効**にして、メールボックスが処理されず、手順5で削除されたアイテムを保持するようにします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-171">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="64b6e-172">Exchange Online PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-172">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="64b6e-173">次のコマンドを実行して、メールボックスへのすべてのクライアントアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-173">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="64b6e-174">コマンド構文では、すべてのクライアントアクセスメソッドがメールボックスで有効になっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-174">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="64b6e-175">メールボックスへのすべてのクライアントアクセス方法を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-175">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="64b6e-176">これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者が切断されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-176">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="64b6e-177">所有者がサインインしていない場合、これらのアクセス方法を無効にした後はメールボックスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-177">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="64b6e-178">次のコマンドを実行して、削除済みアイテムの保存期間を最大で30日に増やします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-178">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="64b6e-179">これは、現在の設定が30日未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-179">This assumes that the current setting is less than 30 days.</span></span> 

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="64b6e-180">次のコマンドを実行して、単一アイテムの回復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-180">Run the following command to disable single item recovery.</span></span>
    
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="64b6e-181">単一アイテムの回復を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-181">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="64b6e-182">この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-182">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="64b6e-183">管理フォルダーアシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-183">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="64b6e-184">前述したように、保持ロックが設定されたアイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダーアシスタントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-184">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="64b6e-185">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-185">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="64b6e-186">回復可能なアイテムフォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべてのホールド (手順1で特定した) を削除することです。</span><span class="sxs-lookup"><span data-stu-id="64b6e-186">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="64b6e-187">[回復可能なアイテム] フォルダーからアイテムを削除した後は、アイテムが保持されないように、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-187">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="64b6e-188">次のセクションでは、メールボックスにさまざまな種類の保留リストを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-188">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="64b6e-189">メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-189">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="64b6e-190">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-190">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="64b6e-191">前述したように、メールボックスから保留リストを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-191">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="64b6e-192">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="64b6e-192">Litigation Hold</span></span>
  
<span data-ttu-id="64b6e-193">Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-193">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="64b6e-194">クライアントアクセス方法と単一アイテムの回復を無効にする場合と同様に、訴訟ホールドを削除するには最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-194">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="64b6e-195">この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-195">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="64b6e-196">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="64b6e-196">In-Place Hold</span></span>
  
<span data-ttu-id="64b6e-197">Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されているインプレースホールドを識別します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-197">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="64b6e-198">手順1で特定したインプレースホールドの GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-198">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="64b6e-199">インプレースホールドを識別した後、Exchange 管理センター (EAC) または Exchange Online PowerShell を使用して、保留リストからメールボックスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-199">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="64b6e-200">詳細については、「[インプレース保持を作成または削除する](https://go.microsoft.com/fwlink/?linkid=852668)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-200">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="64b6e-201">特定のメールボックスに適用されるアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="64b6e-201">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="64b6e-202">[セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用されているアイテム保持ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-202">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="64b6e-203">手順1で特定したアイテム`mbx`保持`skp`ポリシーの GUID (またはプレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-203">Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="64b6e-204">アイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、前の手順で確認したアイテム保持ポリシーを編集して、アイテム保持ポリシーに含まれる受信者のリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-204">After you identify the retention policy, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-retention-policies"></a><span data-ttu-id="64b6e-205">組織全体に対するアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="64b6e-205">Organization-wide retention policies</span></span>
  
<span data-ttu-id="64b6e-206">組織全体および Exchange 全体のアイテム保持ポリシーは、組織内のすべてのメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-206">Organization-wide and Exchange-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="64b6e-207">これらは、(メールボックスレベルではなく) 組織レベルで適用され、手順1で取得した組織レベルの**config**コマンドレットを実行したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-207">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="64b6e-208">[セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、組織全体のアイテム保持ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-208">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="64b6e-209">手順1で特定した組織`mbx`全体のアイテム保持ポリシーの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-209">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="64b6e-210">組織全体のアイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、前の手順で特定した組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストにメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-210">After you identify the organization-wide retention policies, go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="64b6e-211">この操作を行うと、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-211">Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="retention-labels"></a><span data-ttu-id="64b6e-212">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="64b6e-212">Retention labels</span></span>

<span data-ttu-id="64b6e-213">ユーザーがコンテンツを保持するように設定されているラベルを適用するか、メールボックス内のフォルダーまたはアイテムを保持した後にコンテンツを削除すると、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-213">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="64b6e-214">このような場合、メールボックスは、訴訟ホールドの対象となっているか、アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-214">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="64b6e-215">*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-215">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="64b6e-216">フォルダーまたはアイテムに保持ラベルが適用されているためにメールボックスが保留になっていることを確認したら、セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、ComplianceTag の検索条件を使用してラベル付きアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-216">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="64b6e-217">詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-217">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="64b6e-218">ラベルの詳細については、「[ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-218">For more information about labels, see [Overview of labels](labels.md).</span></span>

 ### <a name="ediscovery-holds"></a><span data-ttu-id="64b6e-219">電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="64b6e-219">eDiscovery holds</span></span>
  
<span data-ttu-id="64b6e-220">[セキュリティ & コンプライアンスセンターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース (*電子情報*開示の保留と呼ばれます) に関連付けられている保留リストを識別します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-220">Run the following commands in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds*) that's applied to the mailbox.</span></span> <span data-ttu-id="64b6e-221">手順1で特定した電子`UniH`情報開示ホールドの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-221">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="64b6e-222">2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。3番目のコマンドは、保留の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-222">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="64b6e-223">電子情報開示のケースとホールドの名前を特定したら、コンプライアンスセンターの [**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開き、保留リストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-223">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="64b6e-224">電子情報開示の保持の識別の詳細については、「How to the Exchange Online mailbox」に記載されている[保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)」の「電子情報開示の保持」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-224">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="64b6e-225">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-225">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="64b6e-226">メールボックスから何らかの種類の保留を解除した後、 *DelayHoldApplied*または*DelayReleaseHoldApplied* mailbox プロパティの値は**True**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-226">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="64b6e-227">これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-227">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="64b6e-228">これは*遅延ホールド*と呼ばれ、データがメールボックスから完全に削除されないようにするために、保留リストの実際の削除が30日間延期されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-228">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="64b6e-229">(遅延保持の目的は、保留が解除された後に削除されるメールボックスアイテムを、管理者が検索または復旧する機会を管理者に提供することです)。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-229">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="64b6e-230">30日後、遅延保持が有効期限切れになり、Microsoft 365 は遅延ホールド ( *DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティを**False**に設定して) を自動的に削除して、ホールドが解除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-230">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False**) so that the hold is removed.</span></span> <span data-ttu-id="64b6e-231">遅延ホールドの詳細については、「 [Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)」の「遅延保持のメールボックスを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-231">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="64b6e-232">手順5でアイテムを削除する前に、メールボックスから遅延ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-232">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="64b6e-233">最初に、Exchange Online PowerShell で次のコマンドを実行して、遅延保持がメールボックスに適用されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-233">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="64b6e-234">*DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティの値が**False**に設定されている場合、遅延保持はメールボックスに配置されていません。</span><span class="sxs-lookup"><span data-stu-id="64b6e-234">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="64b6e-235">[回復可能なアイテム] フォルダー内のアイテムを削除するには、手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-235">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="64b6e-236">*DelayHoldApplied*または*DelayReleaseHoldApplied*プロパティの値が**True**に設定されている場合は、次のいずれかのコマンドを実行して遅延保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-236">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True**, run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="64b6e-237">または</span><span class="sxs-lookup"><span data-stu-id="64b6e-237">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="64b6e-238">*RemoveDelayHoldApplied*または*RemoveDelayReleaseHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-238">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="64b6e-239">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="64b6e-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="64b6e-240">これで、セキュリティ & コンプライアンスセンターで[new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)および new-compliancesearchaction コマンドレットを使用して、回復可能[な](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)アイテムフォルダーのアイテムを実際に削除する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="64b6e-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction) cmdlets in the Security & Compliance Center.</span></span> 

<span data-ttu-id="64b6e-241">これを行うには、「[メールメッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-241">To do this, see [Search for and delete email messages](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="64b6e-242">アイテムが削除されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="64b6e-242">Verify that items were deleted</span></span>

<span data-ttu-id="64b6e-243">メールボックスの [回復可能なアイテム] フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell で**get-mailboxfolderstatistics**コマンドレットを使用して、回復可能なアイテムフォルダー内のアイテムのサイズと数を確認します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-243">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="64b6e-244">これらの統計情報は、手順1で収集したものと比較できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-244">You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="64b6e-245">で次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-245">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="64b6e-246">次のコマンドを実行して、ユーザーのアーカイブメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-246">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="64b6e-247">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="64b6e-247">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="64b6e-248">最後の手順では、メールボックスを以前の構成に戻します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-248">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="64b6e-249">これは、手順2で変更したプロパティをリセットし、手順3で削除した保留リストを再適用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-249">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="64b6e-250">これには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-250">This includes:</span></span>
  
- <span data-ttu-id="64b6e-251">削除済みアイテムの保存期間を以前の値に戻します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-251">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="64b6e-252">または、Exchange Online の最大値の30日間に設定しておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-252">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="64b6e-253">単一アイテムの回復を再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-253">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="64b6e-254">所有者が自分のメールボックスにアクセスできるように、クライアントアクセス方法を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-254">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="64b6e-255">削除した保留リストとアイテム保持ポリシーを再適用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-255">Reapplying the holds and retention policies that you removed.</span></span>
    
- <span data-ttu-id="64b6e-256">管理フォルダーアシスタントを再度有効にして、メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-256">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="64b6e-257">管理フォルダーアシスタントを再度有効にしてからメールボックスを処理できるようにするには、保持ポリシーまたはアイテム保持ポリシーを再適用した後24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-257">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="64b6e-258">Exchange Online PowerShell で次の手順を実行します (指定された順序で)。</span><span class="sxs-lookup"><span data-stu-id="64b6e-258">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="64b6e-259">削除済みアイテムの保存期間を元の値に戻すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-259">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="64b6e-260">これは、前の設定が30日未満であることを前提としています。たとえば、14日になります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-260">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span> 
    
    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="64b6e-261">単一アイテムの回復を再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-261">Run the following command to re-enable single item recovery.</span></span>
   
    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="64b6e-262">次のコマンドを実行して、すべてのクライアントアクセス方法をメールボックスに再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-262">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="64b6e-263">手順3で削除したホールドを再適用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-263">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="64b6e-264">保留の種類に応じて、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-264">Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="64b6e-265">**訴訟ホールド**</span><span class="sxs-lookup"><span data-stu-id="64b6e-265">**Litigation Hold**</span></span>
    
    <span data-ttu-id="64b6e-266">メールボックスの訴訟ホールドを再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-266">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="64b6e-267">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="64b6e-267">**In-Place Hold**</span></span>
    
    <span data-ttu-id="64b6e-268">EAC (または Exchange Online PowerShell) を使用して、メールボックスをインプレース保持に戻します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-268">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="64b6e-269">**特定のメールボックスに適用されるアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="64b6e-269">**Retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="64b6e-270">セキュリティ & コンプライアンスセンターを使用して、メールボックスをアイテム保持ポリシーに追加し直します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-270">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="64b6e-271">セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、アイテム保持ポリシーを編集して、アイテム保持ポリシーが適用されている受信者のリストにメールボックスを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-271">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="64b6e-272">**組織全体のアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="64b6e-272">**Organization-wide Retention policies**</span></span>
    
    <span data-ttu-id="64b6e-273">組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、セキュリティ & コンプライアンスセンターを使用して、除外するユーザーのリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-273">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="64b6e-274">セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** \>の**保持**] ページに移動し、組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-274">Go to the **Information governance** \> **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="64b6e-275">これを行うと、ユーザーのメールボックスにアイテム保持ポリシーが再適用されます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-275">Doing this will reapply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="64b6e-276">**電子情報開示ケースの保持**</span><span class="sxs-lookup"><span data-stu-id="64b6e-276">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="64b6e-277">セキュリティ & コンプライアンスセンターを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-277">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="64b6e-278">[**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開いて、メールボックスを保持に戻します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-278">Go to the **eDiscovery** \> **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="64b6e-279">管理フォルダーアシスタントがメールボックスを再度処理できるようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-279">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="64b6e-280">前述したように、管理フォルダーアシスタントを再度有効にする前に、保持ポリシーまたはアイテム保持ポリシーを再適用して24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64b6e-280">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="64b6e-281">メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、設定を手順1で収集したものと比較します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-281">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="64b6e-282">詳細情報</span><span class="sxs-lookup"><span data-stu-id="64b6e-282">More information</span></span>

<span data-ttu-id="64b6e-283">次の表は、 *InPlaceHolds*プロパティの値に基づいて、**メールボックスの取得**または取得、または**取得-組織の構成**のコマンドレットを実行した場合に、さまざまな種類の保留を識別する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-283">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="64b6e-284">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-284">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="64b6e-285">前述のように、[回復可能なアイテム] フォルダー内のアイテムを正常に削除する前に、保留リストとアイテム保持ポリシーをすべて削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-285">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="64b6e-286">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="64b6e-286">**Hold type**</span></span>|<span data-ttu-id="64b6e-287">**値の例**</span><span class="sxs-lookup"><span data-stu-id="64b6e-287">**Example value**</span></span>|<span data-ttu-id="64b6e-288">**保留リストを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="64b6e-288">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64b6e-289">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="64b6e-289">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="64b6e-290">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-290">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="64b6e-291">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="64b6e-291">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="64b6e-292">*InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-292">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="64b6e-293">GUID はプレフィックスで始まっていないため、これはインプレースホールドであることを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-293">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="64b6e-294">Exchange Online の PowerShell `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`でコマンドを使用して、メールボックスのインプレース保持に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-294">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="64b6e-295">セキュリティ & コンプライアンスセンターで特定のメールボックスに適用されるアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="64b6e-295">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="64b6e-296">または</span><span class="sxs-lookup"><span data-stu-id="64b6e-296">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="64b6e-297">**メールボックスの取得**コマンドレットを実行すると、 *InPlaceHolds*プロパティには、メールボックスに適用されているアイテム保持ポリシーの guid も含まれます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-297">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="64b6e-298">GUID が`mbx`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-298">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="64b6e-299">アイテム保持ポリシーの GUID が`skp`プレフィックスで始まっている場合は、アイテム保持ポリシーが Skype for business の会話に適用されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-299">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="64b6e-300">メールボックスに適用されているアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-300">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="64b6e-301">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-301">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="64b6e-302">セキュリティ & コンプライアンスセンターの組織全体のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="64b6e-302">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="64b6e-303">値なし</span><span class="sxs-lookup"><span data-stu-id="64b6e-303">No value</span></span>  <br/> <span data-ttu-id="64b6e-304">または</span><span class="sxs-lookup"><span data-stu-id="64b6e-304">or</span></span>  <br/>  <span data-ttu-id="64b6e-305">`-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体のポリシーから除外されていることを示します)</span><span class="sxs-lookup"><span data-stu-id="64b6e-305">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="64b6e-306">*InPlaceHolds*コマンドレットの実行時にプロパティが空の場合でも、**メールボックスに**適用されている1つ以上の組織全体のアイテム保持ポリシーが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-306">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="64b6e-307">これを確認するには、Exchange `Get-OrganizationConfig | FL InPlaceHolds` Online PowerShell でコマンドを実行して、組織全体のアイテム保持ポリシーの guid の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-307">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="64b6e-308">Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID `mbx`は、先頭にプレフィックスが付いています。たとえば、 `mbxa3056bb15562480fadb46ce523ff7b02`のようになります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-308">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="64b6e-309">メールボックスに適用されている組織全体のアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-309">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="64b6e-310">メールボックスが組織全体のアイテム保持ポリシーから除外されている場合、**メールボックス取得**コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの*InPlaceHolds*プロパティに表示されます。プレフィックス`-mbx`によって識別されます。例えば`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="64b6e-310">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="64b6e-311">セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド</span><span class="sxs-lookup"><span data-stu-id="64b6e-311">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="64b6e-312">*InPlaceHolds*プロパティには、メールボックスに配置される可能性のあるセキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留の GUID も含まれています。</span><span class="sxs-lookup"><span data-stu-id="64b6e-312">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="64b6e-313">GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="64b6e-313">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="64b6e-314">セキュリティ & コンプライアンスセンター `Get-CaseHoldPolicy`の PowerShell でコマンドレットを使用して、メールボックスの保留リストに関連付けられている電子情報開示ケースに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-314">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="64b6e-315">たとえば、コマンド`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`を実行して、メールボックスにあるケースホールドの名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="64b6e-315">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="64b6e-316">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="64b6e-316">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="64b6e-317">メールボックスの保留リストが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64b6e-317">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


