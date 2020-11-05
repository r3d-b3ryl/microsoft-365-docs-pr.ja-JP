---
title: クラウドメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する
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
description: 管理者が Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを、法的情報保留の対象となっている場合でも削除できる方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7a51a78280885a8a7aa7c65a0c04110b46ed7f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919957"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold"></a><span data-ttu-id="5b3fb-103">保留中のクラウド ベースのメールボックスの 回復可能なアイテム フォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-103">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold</span></span>

<span data-ttu-id="5b3fb-104">Exchange Online メールボックスの回復可能なアイテムフォルダーは、偶発的または悪意のある削除から保護するために存在します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-104">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions.</span></span> <span data-ttu-id="5b3fb-105">また、保留や電子情報開示の検索など、コンプライアンス機能によって保持およびアクセスされるアイテムを格納するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-105">It's also used to store items that are retained and accessed by compliance features, such as holds and eDiscovery searches.</span></span> <span data-ttu-id="5b3fb-106">ただし、状況によっては、削除する必要のある回復可能なアイテムフォルダーに誤って保持されていたデータが組織に存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-106">However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete.</span></span> <span data-ttu-id="5b3fb-107">たとえば、ユーザーが気付かないうちに機密情報や情報が含まれる電子メールメッセージを知らずに送信または転送することがあります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-107">For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences.</span></span> <span data-ttu-id="5b3fb-108">メッセージが完全に削除された場合でも、メールボックスに法的情報保持が設定されているため、無期限に保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-108">Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-109">このシナリオは、データが Office 365 *に誤って* 含まれていたため、 *データ流出* と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-109">This scenario is known as *data spillage* because data has been unintentionally *spilled* into Office 365.</span></span> <span data-ttu-id="5b3fb-110">このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除することができます。これは、Office 365 のさまざまな保留機能のいずれかを使用して、そのメールボックスが保持されている場合でも削除できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-110">In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365.</span></span> <span data-ttu-id="5b3fb-111">これらの種類には、訴訟ホールド、In-Place ホールド、電子情報開示の保持、および Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成されたアイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-111">These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and retention policies created in the security and compliance center in Office 365 or Microsoft 365.</span></span>
  
 <span data-ttu-id="5b3fb-112">この記事では、管理者が保留中のクラウドベースのメールボックスの回復可能なアイテムフォルダーからアイテムを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-112">This article explains how admins can delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold.</span></span> <span data-ttu-id="5b3fb-113">この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダーアシスタントがメールボックスの処理を無効にし、保持を一時的に削除し、回復可能なアイテムフォルダーからアイテムを削除した後、メールボックスを以前の構成に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-113">This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration.</span></span> <span data-ttu-id="5b3fb-114">プロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-114">Here's the process:</span></span>
  
[<span data-ttu-id="5b3fb-115">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-115">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="5b3fb-116">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-116">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="5b3fb-117">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-117">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="5b3fb-118">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-118">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="5b3fb-119">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-119">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="5b3fb-120">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="5b3fb-120">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="5b3fb-121">この記事に記載されている手順により、Exchange Online メールボックスからデータが完全に削除 (パージ) されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-121">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox.</span></span> <span data-ttu-id="5b3fb-122">これは、回復可能なアイテムフォルダーから削除されたメッセージを回復できず、法的証拠開示やその他の法令遵守のために利用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-122">That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes.</span></span> <span data-ttu-id="5b3fb-123">セキュリティ/コンプライアンスセンターで作成された訴訟ホールド、In-Place ホールド、電子情報開示の保留、またはアイテム保持ポリシーの一部として保留になっているメールボックスからメッセージを削除する場合は、保留リストを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-123">If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or retention policy created in the security and compliance center, check with your records management or legal departments before removing the hold.</span></span> <span data-ttu-id="5b3fb-124">組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-124">Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span>
  
## <a name="before-you-delete-items"></a><span data-ttu-id="5b3fb-125">アイテムを削除する前に</span><span class="sxs-lookup"><span data-stu-id="5b3fb-125">Before you delete items</span></span>

- <span data-ttu-id="5b3fb-126">コンテンツ検索を作成して実行するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-126">To create and run a Content Search, you have to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role.</span></span> <span data-ttu-id="5b3fb-127">メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-127">To delete messages, you have to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="5b3fb-128">ユーザーを役割グループに追加する方法の詳細については、「[セキュリティ/コンプライアンス センターの電子情報開示のアクセス許可を割り当てる](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-128">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions).</span></span>

- <span data-ttu-id="5b3fb-129">この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-129">The procedure described in this article isn't supported for inactive mailboxes.</span></span> <span data-ttu-id="5b3fb-130">これは、削除した後、非アクティブなメールボックスに保持 (またはアイテム保持ポリシー) を再適用できないためです。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-130">That's because you can't reapply a hold (or retention policy) to an inactive mailbox after you remove it.</span></span> <span data-ttu-id="5b3fb-131">非アクティブなメールボックスからホールドを削除すると、その保留中のメールボックスは通常の回復可能な削除によって削除され、管理フォルダーアシスタントによる処理後は組織から完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-131">When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>

- <span data-ttu-id="5b3fb-132">保持ロックを使用してロックされているポリシーを使用して、保持設定が割り当てられているメールボックスに対してこの手順を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-132">You can't perform this procedure for a mailbox that has been assigned retention settings with a policy that's locked by using Preservation Lock.</span></span> <span data-ttu-id="5b3fb-133">これは、このロックによって、ポリシーからメールボックスを削除または除外したり、メールボックス上の管理フォルダーアシスタントを無効にしたりできないためです。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-133">That's because this lock prevents you from removing or excluding the mailbox from the policy and from disabling the Managed Folder Assistant on the mailbox.</span></span> <span data-ttu-id="5b3fb-134">保持のためのロックポリシーの詳細については、「保持 [ロックを使用してアイテム保持ポリシーおよび保持ラベルポリシーへの変更を制限する](retention-preservation-lock.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-134">For more information about locking policies for retention,see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

- <span data-ttu-id="5b3fb-135">メールボックスが保留になっていない (または単一アイテムの回復が有効になっていない) 場合は、回復可能なアイテムフォルダーからアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-135">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can delete the items from the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-136">これを行う方法の詳細については、「 [組織内での電子メールメッセージの検索と削除](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-136">For more information about how to do this, see [Search for and delete email messages in your organization](https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="5b3fb-137">手順 1: メールボックスに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-137">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="5b3fb-138">最初の手順では、この手順に影響する、ターゲットメールボックスから選択したプロパティを収集します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-138">This first step is to collect selected properties from the target mailbox that will affect this procedure.</span></span> <span data-ttu-id="5b3fb-139">これらのプロパティの一部を変更し、[回復可能なアイテム] フォルダーからアイテムを削除した後に、手順6で元の値に戻すことができるように、これらの設定を書き留めておくか、テキストファイルに保存してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-139">Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-140">収集する必要があるメールボックスのプロパティの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-140">Here's a list of the mailbox properties you need to collect.</span></span>
  
- <span data-ttu-id="5b3fb-141">*Singleitemrecoveryenabled*  および  *RetainDeletedItemsFor* 。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-141">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*.</span></span> <span data-ttu-id="5b3fb-142">必要に応じて、1回の回復を無効にして、手順3で削除済みアイテムの保存期間を延長します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-142">If necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span>

- <span data-ttu-id="5b3fb-143">*LitigationHoldEnabled*  および  *InPlaceHolds* 。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-143">*LitigationHoldEnabled*  and  *InPlaceHolds*.</span></span> <span data-ttu-id="5b3fb-144">手順3で一時的に削除できるように、メールボックスに配置されているすべての保留リストを識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-144">You need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3.</span></span> <span data-ttu-id="5b3fb-145">メールボックスに配置される可能性のある型保持を特定する方法については、「 [詳細情報](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-145">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span>

<span data-ttu-id="5b3fb-146">また、この手順の実行中に所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックスクライアントアクセスの設定を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-146">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure.</span></span> <span data-ttu-id="5b3fb-147">最後に、[回復可能なアイテム] フォルダー内のアイテムの現在のサイズと数を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-147">Finally, you can get the current size and number of items in the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-148">手順5で [回復可能なアイテム] フォルダーのアイテムを削除した後、この情報を使用してアイテムが削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-148">After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were removed.</span></span>
  
1. <span data-ttu-id="5b3fb-149">[Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-149">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="5b3fb-150">Exchange Online で適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-150">Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span>

2. <span data-ttu-id="5b3fb-151">単一アイテムの回復と削除済みアイテムの保存期間に関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-151">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```powershell
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="5b3fb-152">単一アイテムの回復が有効になっている場合は、手順2で無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-152">If single item recovery is enabled, you'll have to disable it in Step 2.</span></span> <span data-ttu-id="5b3fb-153">削除済みアイテムの保存期間が30日間 (Exchange Online の最大値) に設定されていない場合は、手順2で増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-153">If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span>

3. <span data-ttu-id="5b3fb-154">次のコマンドを実行して、メールボックスのメールボックスアクセス設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-154">Run the following command to get the mailbox access settings for the mailbox.</span></span>

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="5b3fb-155">手順2では、これらのアクセス方法をすべて無効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-155">You'll disable all of these access methods in Step 2.</span></span>

4. <span data-ttu-id="5b3fb-156">次のコマンドを実行して、メールボックスに適用されている保留および保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-156">Run the following command to get information about the holds and retention policies applied to the mailbox.</span></span>

    ```powershell
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```

   > [!TIP]
    > <span data-ttu-id="5b3fb-157">*InPlaceHolds* プロパティに含まれる値が多すぎて、一部が表示されていない場合は、コマンドを実行してそれぞれの値を別々の行に表示することができ `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` ます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-157">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span>
  
5. <span data-ttu-id="5b3fb-158">組織全体のアイテム保持ポリシーに関する情報を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-158">Run the following command to get information about any organization-wide retention policies.</span></span> 

    ```powershell
    Get-OrganizationConfig | FL InPlaceHolds
    ```

   <span data-ttu-id="5b3fb-159">組織全体のアイテム保持ポリシーを使用している場合は、手順3でこれらのポリシーからメールボックスを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-159">If your organization has any organization-wide retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="5b3fb-160">*InPlaceHolds* プロパティに含まれる値が多すぎて、一部が表示されていない場合は、コマンドを実行してそれぞれの値を別々の行に表示することができ `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` ます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="5b3fb-161">次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-161">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="5b3fb-162">ユーザーのアーカイブメールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブメールボックス内の [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-162">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```powershell
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="5b3fb-163">手順5でアイテムを削除する場合、ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除するか、削除するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-163">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox.</span></span> <span data-ttu-id="5b3fb-164">メールボックスの自動拡張アーカイブが有効になっている場合、補助アーカイブメールボックス内のアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-164">If auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="5b3fb-165">手順 2: メールボックスを準備する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-165">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="5b3fb-166">メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-166">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span>
  
- <span data-ttu-id="5b3fb-167">メールボックス **へのクライアントアクセスを無効** にして、メールボックスの所有者がメールボックスにアクセスできないようにして、この手順の実行中にメールボックスデータを変更しないようにします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-167">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span>

- <span data-ttu-id="5b3fb-168">**削除済みアイテムの保存期間** を30日間 (Exchange Online の最大値) に増やして、手順5でアイテムを回復可能なアイテムフォルダーから削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-168">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span>

- <span data-ttu-id="5b3fb-169">手順5で [回復可能なアイテム] フォルダーからアイテムを削除した後に、アイテムが保持されないように、 **単一アイテムの回復を無効** にします (削除済みアイテムの保存期間中)。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-169">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span>

- <span data-ttu-id="5b3fb-170">**管理フォルダーアシスタントを無効** にして、メールボックスが処理されず、手順5で削除されたアイテムを保持するようにします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-170">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span>

<span data-ttu-id="5b3fb-171">Exchange Online PowerShell で次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-171">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="5b3fb-172">次のコマンドを実行して、メールボックスへのすべてのクライアントアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-172">Run the following command to disable all client access to the mailbox.</span></span> <span data-ttu-id="5b3fb-173">コマンド構文では、すべてのクライアントアクセスメソッドがメールボックスで有効になっていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-173">The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="5b3fb-174">メールボックスへのすべてのクライアントアクセス方法を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-174">It might take up to 60 minutes to disable all client access methods to the mailbox.</span></span> <span data-ttu-id="5b3fb-175">これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者が切断されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-175">Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in.</span></span> <span data-ttu-id="5b3fb-176">所有者がサインインしていない場合、これらのアクセス方法を無効にした後はメールボックスにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-176">If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span>
  
2. <span data-ttu-id="5b3fb-177">次のコマンドを実行して、削除済みアイテムの保存期間を最大で30日に増やします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-177">Run the following command to increase the deleted item retention period the maximum of 30 days.</span></span> <span data-ttu-id="5b3fb-178">これは、現在の設定が30日未満であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-178">This assumes that the current setting is less than 30 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="5b3fb-179">次のコマンドを実行して、単一アイテムの回復を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-179">Run the following command to disable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="5b3fb-180">単一アイテムの回復を無効にするには、最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-180">It might take up to 60 minutes to disable single item recovery.</span></span> <span data-ttu-id="5b3fb-181">この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-181">Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="5b3fb-182">管理フォルダーアシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-182">Run the following command to prevent the Managed Folder Assistant from processing the mailbox.</span></span> <span data-ttu-id="5b3fb-183">前述したように、保持ロックが設定されたアイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダーアシスタントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-183">As previously explained, you can disable the Managed Folder Assistant only if a retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="5b3fb-184">手順 3: メールボックスからすべての保留リストを削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-184">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="5b3fb-185">回復可能なアイテムフォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべてのホールド (手順1で特定した) を削除することです。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-185">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-186">[回復可能なアイテム] フォルダーからアイテムを削除した後は、アイテムが保持されないように、すべての保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-186">All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-187">次のセクションでは、メールボックスにさまざまな種類の保留リストを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-187">The following sections contain information about removing different types of holds on a mailbox.</span></span> <span data-ttu-id="5b3fb-188">メールボックスに配置される可能性のある型保持を特定する方法については、「 [詳細情報](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-188">See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> <span data-ttu-id="5b3fb-189">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-189">For more information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="5b3fb-190">前述したように、メールボックスから保留リストを削除する前に、レコード管理または法務部門に確認してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-190">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
### <a name="litigation-hold"></a><span data-ttu-id="5b3fb-191">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="5b3fb-191">Litigation Hold</span></span>
  
<span data-ttu-id="5b3fb-192">Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-192">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $false
```

> [!NOTE]
> <span data-ttu-id="5b3fb-193">クライアントアクセス方法と単一アイテムの回復を無効にする場合と同様に、訴訟ホールドを削除するには最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-193">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold.</span></span> <span data-ttu-id="5b3fb-194">この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-194">Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
### <a name="in-place-hold"></a><span data-ttu-id="5b3fb-195">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="5b3fb-195">In-Place Hold</span></span>
  
<span data-ttu-id="5b3fb-196">Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されている In-Place 保持を識別します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-196">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-197">手順1で特定した保留 In-Place の GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-197">Use the GUID for the In-Place Hold that you identified in Step 1.</span></span>

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```

<span data-ttu-id="5b3fb-198">In-Place ホールドを識別した後、Exchange 管理センター (EAC) または Exchange Online PowerShell を使用して、メールボックスを保留リストから削除できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-198">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold.</span></span> <span data-ttu-id="5b3fb-199">詳細については、「 [In-Place ホールドを作成または削除する](https://go.microsoft.com/fwlink/?linkid=852668)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-199">For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
### <a name="retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="5b3fb-200">特定のメールボックスに適用されるアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="5b3fb-200">Retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="5b3fb-201">[セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用されているアイテム保持ポリシーを識別します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-201">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the retention policy that is applied to the mailbox.</span></span> <span data-ttu-id="5b3fb-202">このコマンドは、メールボックスに適用されている Teams の会話保持ポリシーも返します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-202">This command will also return any Teams conversation retention policies applied to a mailbox.</span></span> <span data-ttu-id="5b3fb-203">`mbx` `skp` 手順1で特定したアイテム保持ポリシーの GUID (またはプレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-203">Use the GUID (not including the `mbx` or `skp` prefix) for the retention policy that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="5b3fb-204">アイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** の  >  **保持** ] ページに移動し、前の手順で確認したアイテム保持ポリシーを編集して、アイテム保持ポリシーに含まれる受信者のリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-204">After you identify the retention policy, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span>
  
### <a name="organization-wide-retention-policies"></a><span data-ttu-id="5b3fb-205">組織全体に対するアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="5b3fb-205">Organization-wide retention policies</span></span>
  
<span data-ttu-id="5b3fb-206">組織全体、Exchange 全体、およびチーム全体のアイテム保持ポリシーは、組織内のすべてのメールボックスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-206">Organization-wide, Exchange-wide, and Teams-wide retention policies are applied to every mailbox in the organization.</span></span> <span data-ttu-id="5b3fb-207">これらは、(メールボックスレベルではなく) 組織レベルで適用され、手順1で取得した組織レベルの **config** コマンドレットを実行したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-207">They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1.</span></span> <span data-ttu-id="5b3fb-208">[セキュリティ & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、組織全体のアイテム保持ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-208">Run the following command in [Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide retention policies.</span></span> <span data-ttu-id="5b3fb-209">`mbx`手順1で特定した組織全体のアイテム保持ポリシーの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-209">Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span>

```powershell
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="5b3fb-210">組織全体のアイテム保持ポリシーを特定したら、セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** の  >  **保持** ] ページに移動し、前の手順で特定した組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストにメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-210">After you identify the organization-wide retention policies, go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients.</span></span> <span data-ttu-id="5b3fb-211">この操作を行うと、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-211">Doing this will remove the user's mailbox from the retention policy.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="5b3fb-212">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="5b3fb-212">Retention labels</span></span>

<span data-ttu-id="5b3fb-213">ユーザーがコンテンツを保持するように設定されているラベルを適用するか、メールボックス内のフォルダーまたはアイテムを保持した後にコンテンツを削除すると、 *ComplianceTagHoldApplied* mailbox プロパティが **True** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-213">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="5b3fb-214">このような場合、メールボックスは、訴訟ホールドの対象となっているか、アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-214">When this happens, the mailbox is considered to be on hold, as if it was placed on Litigation Hold or assigned to a retention policy.</span></span>

<span data-ttu-id="5b3fb-215">*ComplianceTagHoldApplied* プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-215">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="5b3fb-216">フォルダーまたはアイテムに保持ラベルが適用されているためにメールボックスが保留になっていることを確認したら、セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、ComplianceTag の検索条件を使用してラベル付きアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-216">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the security and compliance center to search for labeled items by using the ComplianceTag search condition.</span></span> <span data-ttu-id="5b3fb-217">詳細については、「 [コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)」の「検索条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-217">For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="5b3fb-218">ラベルの詳細については、「 [アイテム保持ポリシーと保持ラベルについ](retention.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-218">For more information about labels, see [Learn about retention policies and retention labels](retention.md).</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="5b3fb-219">電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="5b3fb-219">eDiscovery holds</span></span>
  
<span data-ttu-id="5b3fb-220">[セキュリティ & コンプライアンスセンターの PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)で次のコマンドを実行して、メールボックスに適用される電子情報開示ケース ( *電子情報* 開示の保留と呼ばれます) に関連付けられている保留リストを識別します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-220">Run the following commands in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to identify the hold associated with an eDiscovery case (called *eDiscovery holds* ) that's applied to the mailbox.</span></span> <span data-ttu-id="5b3fb-221">`UniH`手順1で特定した電子情報開示ホールドの GUID (プレフィックスを含まない) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-221">Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1.</span></span> <span data-ttu-id="5b3fb-222">2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。3番目のコマンドは、保留の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-222">The second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span>
  
```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold.Name
```

<span data-ttu-id="5b3fb-223">電子情報開示のケースとホールドの名前を特定したら、コンプライアンスセンターの [ **電子情報** \> **開示電子情報開示** ] ページに移動し、ケースを開き、保留リストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-223">After you've identified the name of the eDiscovery case and the hold, go to the **eDiscovery** \> **eDiscovery** page in the compliance center, open the case, and remove the mailbox from the hold.</span></span> <span data-ttu-id="5b3fb-224">電子情報開示の保持の識別の詳細については、「How to the Exchange Online mailbox」に記載されている [保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds)」の「電子情報開示の保持」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-224">For more information about identifying eDiscovery holds, see the "eDiscovery holds" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#ediscovery-holds).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="5b3fb-225">手順 4: メールボックスから遅延保持を削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-225">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="5b3fb-226">メールボックスから何らかの種類の保留を解除した後、 *DelayHoldApplied* または *DelayReleaseHoldApplied* mailbox プロパティの値は **True** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-226">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* mailbox property is set to **True**.</span></span> <span data-ttu-id="5b3fb-227">これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-227">This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed.</span></span> <span data-ttu-id="5b3fb-228">これは *遅延ホールド* と呼ばれ、データがメールボックスから完全に削除されないようにするために、保留リストの実際の削除が30日間延期されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-228">This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox.</span></span> <span data-ttu-id="5b3fb-229">(遅延保持の目的は、保留が解除された後に削除されるメールボックスアイテムを、管理者が検索または復旧する機会を管理者に提供することです)。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-229">(The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold.</span></span> <span data-ttu-id="5b3fb-230">30日後、遅延保持が有効期限切れになり、Microsoft 365 は遅延ホールド ( *DelayHoldApplied* または *DelayReleaseHoldApplied* プロパティを **False** に設定して) を自動的に削除して、ホールドが解除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-230">After 30 days, the delay hold expires, and Microsoft 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* or *DelayReleaseHoldApplied* property to **False** ) so that the hold is removed.</span></span> <span data-ttu-id="5b3fb-231">遅延ホールドの詳細については、「 [Exchange Online メールボックスに配置された保留の種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)」の「遅延保持のメールボックスを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-231">For more information about a delay hold, see the "Managing mailboxes on delay hold" section in [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

<span data-ttu-id="5b3fb-232">手順5でアイテムを削除する前に、メールボックスから遅延ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-232">Before you can delete items in Step 5, you have to remove a delay hold from the mailbox.</span></span> <span data-ttu-id="5b3fb-233">最初に、Exchange Online PowerShell で次のコマンドを実行して、遅延保持がメールボックスに適用されているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-233">First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-Mailbox <username> | FL DelayHoldApplied,DelayReleaseHoldApplied
```

<span data-ttu-id="5b3fb-234">*DelayHoldApplied* または *DelayReleaseHoldApplied* プロパティの値が **False** に設定されている場合、遅延保持はメールボックスに配置されていません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-234">If the value of either the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **False** , a delay hold has not been placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-235">[回復可能なアイテム] フォルダー内のアイテムを削除するには、手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-235">You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="5b3fb-236">*DelayHoldApplied* または *DelayReleaseHoldApplied* プロパティの値が **True** に設定されている場合は、次のいずれかのコマンドを実行して遅延保持を削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-236">If the value of the *DelayHoldApplied* or *DelayReleaseHoldApplied* property is set to **True** , run one of the following commands to remove the delay hold:</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

<span data-ttu-id="5b3fb-237">または</span><span class="sxs-lookup"><span data-stu-id="5b3fb-237">Or</span></span>

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

<span data-ttu-id="5b3fb-238">*RemoveDelayHoldApplied* または *RemoveDelayReleaseHoldApplied* パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-238">You must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* or *RemoveDelayReleaseHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="5b3fb-239">手順 5: 回復可能なアイテムフォルダーのアイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="5b3fb-240">これで、セキュリティ & コンプライアンスセンター PowerShell で [new-compliancesearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) および [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) コマンドレットを使用して、回復可能なアイテムフォルダーのアイテムを実際に削除する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-240">Now you're ready to actually delete items in the Recoverable Items folder by using the [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch) and [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearchaction) cmdlets in Security & Compliance Center PowerShell.</span></span>

<span data-ttu-id="5b3fb-241">回復可能なアイテムフォルダーに格納されているアイテムを検索するには、 *対象となるコレクション* を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-241">To search for items that are located in the Recoverable Items folder, we recommend that you perform a *targeted collection*.</span></span> <span data-ttu-id="5b3fb-242">つまり、[回復可能なアイテム] フォルダーにあるアイテムに対してのみ、検索の範囲を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-242">This means you narrow the scope of your search only to items located in the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-243">この操作を行うには、「 [コンテンツ検索で対象コレクションの検索を使用](use-content-search-for-targeted-collections.md) する」の記事にあるスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-243">You can do this by running the script in the [Use Content Search for targeted collections](use-content-search-for-targeted-collections.md) article.</span></span> <span data-ttu-id="5b3fb-244">このスクリプトは、ターゲットの回復可能なアイテムフォルダー内にあるすべてのサブフォルダーのフォルダー ID プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-244">This script returns the value of the folder ID property for all the subfolders in the target Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-245">次に、検索クエリでフォルダー ID を使用して、そのフォルダーにあるアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-245">Then you use the folder ID in a search query to return items located in that folder.</span></span>

<span data-ttu-id="5b3fb-246">ユーザーの回復可能なアイテムフォルダーのアイテムを検索して削除するプロセスの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-246">Here's an overview of the process to search for and delete items in a user's Recoverable Items folder:</span></span>

1. <span data-ttu-id="5b3fb-247">ターゲットユーザーのメールボックス内のすべてのフォルダーのフォルダー Id を返す対象となるコレクションスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-247">Run the targeted collection script that returns the folder IDs for all folders in the target user's mailbox.</span></span> <span data-ttu-id="5b3fb-248">このスクリプトは、同じ PowerShell セッション内の Exchange Online PowerShell および Security & コンプライアンス PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-248">The script connects to Exchange Online PowerShell and Security & Compliance PowerShell in the same PowerShell session.</span></span> <span data-ttu-id="5b3fb-249">詳細については、「スクリプトを実行して [メールボックスのフォルダーの一覧を取得する](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-249">For more information, see [Run the script to get a list of folders for a mailbox](use-content-search-for-targeted-collections.md#step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site).</span></span>

2. <span data-ttu-id="5b3fb-250">回復可能なアイテムフォルダー内のすべてのサブフォルダーのフォルダー Id をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-250">Copy the folder IDs for all subfolders in the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-251">または、スクリプトの出力をテキストファイルにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-251">Alternatively, you can redirect the output of the script to a text file.</span></span>

   <span data-ttu-id="5b3fb-252">以下に、アイテムを検索して削除できる、回復可能なアイテムフォルダー内のサブフォルダーの一覧と説明を示します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-252">Here's a list and description of the subfolders in the Recoverable Items folder that you can search and delete items from:</span></span>

   - <span data-ttu-id="5b3fb-253">**削除: 削除** 済みアイテムの保存期間が期限切れになっていない回復可能な削除アイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-253">**Deletions** : Contains soft-deleted items whose deleted item retention period has not expired.</span></span> <span data-ttu-id="5b3fb-254">ユーザーは、Outlook の削除済みアイテムの復元ツールを使用して、このサブフォルダーから削除済みのアイテムを回復できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-254">Users can recover soft-deleted items from this subfolder using the Recover Deleted Items tool in Outlook.</span></span>

   - <span data-ttu-id="5b3fb-255">**パージ** : 削除済みアイテムの保存期間が経過した物理的に削除されたアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-255">**Purges** : Contains hard-deleted items whose deleted item retention period has expired.</span></span> <span data-ttu-id="5b3fb-256">ユーザーは、回復可能なアイテムフォルダーからアイテムを削除することによってアイテムを物理的に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-256">Users can also hard-delete items by purging items from their Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-257">メールボックスが保持されている場合は、ハード削除されたアイテムが保持されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-257">If the mailbox is on hold, hard-deleted items are preserved.</span></span> <span data-ttu-id="5b3fb-258">このサブフォルダーは、エンドユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-258">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="5b3fb-259">**Discoveryholds** : 電子情報開示の保持またはアイテム保持ポリシーによって保持された、物理的に削除されたアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-259">**DiscoveryHolds** : Contains hard-deleted items that have been preserved by an eDiscovery hold or a retention policy.</span></span> <span data-ttu-id="5b3fb-260">このサブフォルダーは、エンドユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-260">This subfolder isn't visible to end users.</span></span>

   - <span data-ttu-id="5b3fb-261">**SubstrateHolds** : Teams や、アイテム保持ポリシーまたはその他の保留によって保持されているその他のクラウドベースのアプリから、物理的に削除されたアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-261">**SubstrateHolds** : Contains hard-deleted items from Teams and other cloud-based apps that have been preserved by a retention policy or other type of hold.</span></span> <span data-ttu-id="5b3fb-262">このサブフォルダーは、エンドユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-262">This subfolder isn't visible to end users.</span></span>

3. <span data-ttu-id="5b3fb-263">**New-compliancesearch** コマンドレット (セキュリティ & コンプライアンスセンター PowerShell) を使用するか、コンプライアンスセンターのコンテンツ検索ツールを使用して、対象ユーザーの回復可能なアイテムフォルダーからアイテムを返すコンテンツ検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-263">Use the **New-ComplianceSearch** cmdlet (in Security & Compliance Center PowerShell) or use the Content search tool in the compliance center to create a content search that returns items from the target user's Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-264">検索するすべてのサブフォルダーの検索クエリに FolderId を含めることで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-264">You can do this by including the FolderId in the search query for all subfolders that you want to search.</span></span> <span data-ttu-id="5b3fb-265">たとえば、次のクエリは、削除および eDiscoveryHolds サブフォルダー内のすべてのメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-265">For example, the following query returns all messages in the Purges and eDiscoveryHolds subfolders:</span></span>

   ```text
   folderid:<folder ID of Purges subfolder> OR folderid:<folder ID of DiscoveryHolds subfolder>
   ```

   <span data-ttu-id="5b3fb-266">Folder ID プロパティを使用したコンテンツ検索の実行の詳細と例については、「 [フォルダー id を使用する」または「対象コレクションを実行する」を](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection)参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-266">For more information and examples about running content searches that use the folder ID property, see [Use a folder ID or to perform a targeted collection](use-content-search-for-targeted-collections.md#step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5b3fb-267">**New-compliancesearch** コマンドレットを使用して回復可能なアイテムフォルダーを検索する場合は、必ず **new-compliancesearch** コマンドレットを使用して検索を実行してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-267">If you use the **New-ComplianceSearch** cmdlet to search the Recoverable Items folder, be sure to use **Start-ComplianceSearch** cmdlet to run the search.</span></span>

4. <span data-ttu-id="5b3fb-268">コンテンツ検索を作成して、削除するアイテムが返されることを確認したら、 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 前の手順で作成したコンテンツ検索によって返されたアイテムを完全に削除するためのコマンド (セキュリティ & コンプライアンスセンター PowerShell) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-268">After you've created a content search and validated that it returns the items that you wan to delete, use the `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command (in Security & Compliance Center PowerShell) to permanently delete the items returned by the content search that you created in the previous step.</span></span> <span data-ttu-id="5b3fb-269">たとえば、次のようなコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-269">For example, you can run a command similar to the following command:</span></span>

   ```powershell
   New-ComplianceSearchAction -SearchName "RecoverableItems" -Purge -PurgeType HardDelete
   ```

5. <span data-ttu-id="5b3fb-270">前のコマンドを実行すると、メールボックスごとに最大10個のアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-270">A maximum of 10 items per mailbox are deleted when you run the previous command.</span></span> <span data-ttu-id="5b3fb-271">つまり、 `New-ComplianceSearchAction -Purge` 回復可能なアイテムフォルダーで削除するアイテムをすべて削除するには、コマンドを複数回実行する必要があるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-271">That means you may have to run the `New-ComplianceSearchAction -Purge` command multiple times to delete all the items that you want to delete in the Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-272">その他のアイテムを削除するには、最初に、前のコンプライアンス検索の削除アクションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-272">To delete additional items, you first have to remove the previous compliance search purge action.</span></span> <span data-ttu-id="5b3fb-273">これを行うには、 `Remove-ComplianceSearchAction` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-273">You do this by running the `Remove-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="5b3fb-274">たとえば、前の手順で実行された削除アクションを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-274">For example, to delete the purge action that was run in the previous step, run the following command:</span></span>

   ```powershell
   Remove-ComplianceSearchAction "RecoverableItems_Purge"
   ```

   <span data-ttu-id="5b3fb-275">その後、新しいコンプライアンス検索の削除アクションを作成して、さらにアイテムを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-275">After you do this, you can create a new compliance search purge action to delete more items.</span></span> <span data-ttu-id="5b3fb-276">新しい削除アクションを作成する前に、それぞれの削除アクションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-276">You'll have to delete each purge action before creating a new one.</span></span>

   <span data-ttu-id="5b3fb-277">コンプライアンス検索アクションの一覧を取得するには、コマンドレットを実行し `Get-ComplianceSearchAction` ます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-277">To get a list of the compliance search actions, you can run the `Get-ComplianceSearchAction` cmdlet.</span></span> <span data-ttu-id="5b3fb-278">削除アクションは `_Purge` 、検索名に追加されて識別されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-278">Purge actions are identified by `_Purge` appended to the search name.</span></span>

### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="5b3fb-279">アイテムが削除されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="5b3fb-279">Verify that items were deleted</span></span>

<span data-ttu-id="5b3fb-280">メールボックスの [回復可能なアイテム] フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell で **get-mailboxfolderstatistics** コマンドレットを使用して、回復可能なアイテムフォルダー内のアイテムのサイズと数を確認します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-280">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder.</span></span> <span data-ttu-id="5b3fb-281">これらの統計情報は、手順1で収集したものと比較できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-281">You can compare these statistics with the ones you collected in Step 1.</span></span>
  
<span data-ttu-id="5b3fb-282">で次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-282">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span>
  
```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

<span data-ttu-id="5b3fb-283">次のコマンドを実行して、ユーザーのアーカイブメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-283">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span>

```powershell
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```

## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="5b3fb-284">手順 6: メールボックスを以前の状態に戻す</span><span class="sxs-lookup"><span data-stu-id="5b3fb-284">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="5b3fb-285">最後の手順では、メールボックスを以前の構成に戻します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-285">The final step is to revert the mailbox back to its previous configuration.</span></span> <span data-ttu-id="5b3fb-286">これは、手順2で変更したプロパティをリセットし、手順3で削除した保留リストを再適用することを意味します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-286">This means resetting the properties that you changed in Step 2 and reapplying the holds that you removed in Step 3.</span></span> <span data-ttu-id="5b3fb-287">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-287">This includes:</span></span>
  
- <span data-ttu-id="5b3fb-288">削除済みアイテムの保存期間を以前の値に戻します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-288">Changing the deleted item retention period back to its previous value.</span></span> <span data-ttu-id="5b3fb-289">または、Exchange Online の最大値の30日間に設定しておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-289">Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>

- <span data-ttu-id="5b3fb-290">単一アイテムの回復を再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-290">Re-enabling single Item recovery.</span></span>

- <span data-ttu-id="5b3fb-291">所有者が自分のメールボックスにアクセスできるように、クライアントアクセス方法を再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-291">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>

- <span data-ttu-id="5b3fb-292">削除した保留リストとアイテム保持ポリシーを再適用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-292">Reapplying the holds and retention policies that you removed.</span></span>

- <span data-ttu-id="5b3fb-293">管理フォルダーアシスタントを再度有効にして、メールボックスを処理します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-293">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b3fb-294">管理フォルダーアシスタントを再度有効にしてからメールボックスを処理できるようにするには、保持ポリシーまたはアイテム保持ポリシーを再適用した後24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-294">We recommend that you wait 24 hours after re-applying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span>
  
<span data-ttu-id="5b3fb-295">Exchange Online PowerShell で次の手順を実行します (指定された順序で)。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-295">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="5b3fb-296">削除済みアイテムの保存期間を元の値に戻すには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-296">Run the following command to change the deleted item retention period back to its original value.</span></span> <span data-ttu-id="5b3fb-297">これは、前の設定が30日未満であることを前提としています。たとえば、14日になります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-297">This assumes that the previous setting is less than 30 days; for example, 14 days.</span></span>

    ```powershell
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```

2. <span data-ttu-id="5b3fb-298">単一アイテムの回復を再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-298">Run the following command to re-enable single item recovery.</span></span>

    ```powershell
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="5b3fb-299">次のコマンドを実行して、すべてのクライアントアクセス方法をメールボックスに再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-299">Run the following command to re-enable all client access methods to the mailbox.</span></span>

    ```powershell
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```

4. <span data-ttu-id="5b3fb-300">手順3で削除したホールドを再適用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-300">Reapply the holds that you removed in Step 3.</span></span> <span data-ttu-id="5b3fb-301">保留の種類に応じて、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-301">Depending on the type of hold, use one of the following procedures.</span></span>

    <span data-ttu-id="5b3fb-302">**訴訟ホールド**</span><span class="sxs-lookup"><span data-stu-id="5b3fb-302">**Litigation Hold**</span></span>

    <span data-ttu-id="5b3fb-303">メールボックスの訴訟ホールドを再び有効にするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-303">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>

    ```powershell
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="5b3fb-304">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="5b3fb-304">**In-Place Hold**</span></span>

    <span data-ttu-id="5b3fb-305">EAC (または Exchange Online PowerShell) を使用して、メールボックスを In-Place ホールドに戻します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-305">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span>

    <span data-ttu-id="5b3fb-306">**特定のメールボックスに適用されるアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="5b3fb-306">**Retention policies applied to specific mailboxes**</span></span>

    <span data-ttu-id="5b3fb-307">セキュリティ & コンプライアンスセンターを使用して、メールボックスをアイテム保持ポリシーに追加し直します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-307">Use the Security & Compliance Center to add the mailbox back to the retention policy.</span></span> <span data-ttu-id="5b3fb-308">セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** の  >  **保持** ] ページに移動し、アイテム保持ポリシーを編集して、アイテム保持ポリシーが適用されている受信者のリストにメールボックスを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-308">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span>

    <span data-ttu-id="5b3fb-309">**組織全体のアイテム保持ポリシー**</span><span class="sxs-lookup"><span data-stu-id="5b3fb-309">**Organization-wide Retention policies**</span></span>

    <span data-ttu-id="5b3fb-310">組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、セキュリティ & コンプライアンスセンターを使用して、除外するユーザーのリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-310">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security & Compliance Center to remove the mailbox from the list of excluded users.</span></span> <span data-ttu-id="5b3fb-311">セキュリティ & コンプライアンスセンターの [ **Information ガバナンス** の  >  **保持** ] ページに移動し、組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストからメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-311">Go to the **Information governance** > **Retention** page in the Security & Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients.</span></span> <span data-ttu-id="5b3fb-312">これを行うと、ユーザーのメールボックスにアイテム保持ポリシーが再適用されます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-312">Doing this will reapply the retention policy to the user's mailbox.</span></span>

    <span data-ttu-id="5b3fb-313">**電子情報開示ケースの保持**</span><span class="sxs-lookup"><span data-stu-id="5b3fb-313">**eDiscovery case holds**</span></span>

    <span data-ttu-id="5b3fb-314">セキュリティ & コンプライアンスセンターを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加し直します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-314">Use the Security & Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case.</span></span> <span data-ttu-id="5b3fb-315">[ **電子情報**  >  **開示電子情報開示** ] ページに移動し、ケースを開いて、メールボックスを保持に戻します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-315">Go to the **eDiscovery** > **eDiscovery** page, open the case, and add the mailbox back to the hold.</span></span> 

5. <span data-ttu-id="5b3fb-316">管理フォルダーアシスタントがメールボックスを再度処理できるようにするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-316">Run the following command to allow the Managed Folder Assistant to process the mailbox again.</span></span> <span data-ttu-id="5b3fb-317">前述したように、管理フォルダーアシスタントを再度有効にする前に、保持ポリシーまたはアイテム保持ポリシーを再適用して24時間待ってから、そのポリシーが適切に設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-317">As previously stated, we recommend that you wait 24 hours after reapplying a hold or retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span>

    ```powershell
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```

6. <span data-ttu-id="5b3fb-318">メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、設定を手順1で収集したものと比較します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-318">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```powershell
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```powershell
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

## <a name="more-information"></a><span data-ttu-id="5b3fb-319">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5b3fb-319">More information</span></span>

<span data-ttu-id="5b3fb-320">次の表は、  *InPlaceHolds*  プロパティの値に基づいて、 **メールボックスの取得** または取得、または **取得-組織の構成** のコマンドレットを実行した場合に、さまざまな種類の保留を識別する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-320">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets.</span></span> <span data-ttu-id="5b3fb-321">詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-321">For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="5b3fb-322">前述のように、[回復可能なアイテム] フォルダー内のアイテムを正常に削除する前に、保留リストとアイテム保持ポリシーをすべて削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-322">As previously explained, you have to remove all holds and retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span>
  
| <span data-ttu-id="5b3fb-323">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="5b3fb-323">Hold type</span></span> | <span data-ttu-id="5b3fb-324">値の例</span><span class="sxs-lookup"><span data-stu-id="5b3fb-324">Example value</span></span> | <span data-ttu-id="5b3fb-325">保留リストを識別する方法</span><span class="sxs-lookup"><span data-stu-id="5b3fb-325">How to identify the hold</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="5b3fb-326">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="5b3fb-326">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="5b3fb-327">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-327">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="5b3fb-328">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="5b3fb-328">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="5b3fb-329">*InPlaceHolds* プロパティには、メールボックスに配置された In-Place 保持の GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-329">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-330">GUID がプレフィックスで始まっていないため、これは In-Place ホールドであることを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-330">You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.</span></span>  <br/> <span data-ttu-id="5b3fb-331">`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`Exchange Online の PowerShell でコマンドを使用して、メールボックスの保留 In-Place に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-331">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="5b3fb-332">セキュリティ & コンプライアンスセンターで特定のメールボックスに適用されるアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="5b3fb-332">Retention policies in the Security & Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="5b3fb-333">または</span><span class="sxs-lookup"><span data-stu-id="5b3fb-333">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="5b3fb-334">**メールボックスの取得** コマンドレットを実行すると、 *InPlaceHolds* プロパティには、メールボックスに適用されているアイテム保持ポリシーの guid も含まれます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-334">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of retention policies applied to the mailbox.</span></span> <span data-ttu-id="5b3fb-335">GUID がプレフィックスで始まっているため、アイテム保持ポリシーを識別でき  `mbx` ます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-335">You can identify retention policies because the GUID starts with the  `mbx` prefix.</span></span> <span data-ttu-id="5b3fb-336">アイテム保持ポリシーの GUID がプレフィックスで始まっている場合は  `skp` 、アイテム保持ポリシーが Skype For business の会話に適用されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-336">If the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.</span></span>  <br/> <span data-ttu-id="5b3fb-337">メールボックスに適用されているアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-337">To identity the retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="5b3fb-338">このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-338">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="5b3fb-339">セキュリティ & コンプライアンスセンターの組織全体のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="5b3fb-339">Organization-wide retention policies in the Security & Compliance Center</span></span>  <br/> |<span data-ttu-id="5b3fb-340">値なし</span><span class="sxs-lookup"><span data-stu-id="5b3fb-340">No value</span></span>  <br/> <span data-ttu-id="5b3fb-341">または</span><span class="sxs-lookup"><span data-stu-id="5b3fb-341">or</span></span>  <br/>  <span data-ttu-id="5b3fb-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (メールボックスが組織全体のポリシーから除外されていることを示します)</span><span class="sxs-lookup"><span data-stu-id="5b3fb-342">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="5b3fb-343">*InPlaceHolds* コマンドレットの実行時にプロパティが空の場合でも、 **メールボックスに** 適用されている1つ以上の組織全体のアイテム保持ポリシーが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-343">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="5b3fb-344">これを確認するには、  `Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell でコマンドを実行して、組織全体のアイテム保持ポリシーの guid の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-344">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide retention policies.</span></span> <span data-ttu-id="5b3fb-345">Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID は、というプレフィックスで始まり  `mbx` ます (例:)  `mbxa3056bb15562480fadb46ce523ff7b02` 。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-345">The GUID for organization-wide retention policies applied to Exchange mailboxes starts with the  `mbx` prefix; for example,  `mbxa3056bb15562480fadb46ce523ff7b02`.</span></span>  <br/> <span data-ttu-id="5b3fb-346">メールボックスに適用されている組織全体のアイテム保持ポリシーを識別するには、セキュリティ & コンプライアンスセンターの PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-346">To identity the organization-wide retention policy that's applied to the mailbox, run the following command in Security & Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="5b3fb-347">メールボックスが組織全体のアイテム保持ポリシーから除外されている場合、 **メールボックス取得** コマンドレットを実行すると、アイテム保持ポリシーの GUID がユーザーのメールボックスの *InPlaceHolds* プロパティに表示されます。プレフィックスによって識別され `-mbx` ます。たとえば、`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="5b3fb-347">If a mailbox is excluded from an organization-wide retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="5b3fb-348">セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド</span><span class="sxs-lookup"><span data-stu-id="5b3fb-348">eDiscovery case hold in the Security & Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="5b3fb-349">*InPlaceHolds* プロパティには、メールボックスに配置される可能性のあるセキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留の GUID も含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-349">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center that might be placed on the mailbox.</span></span> <span data-ttu-id="5b3fb-350">GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-350">You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.</span></span>  <br/> <span data-ttu-id="5b3fb-351">`Get-CaseHoldPolicy`セキュリティ & コンプライアンスセンターの PowerShell でコマンドレットを使用して、メールボックスの保留リストに関連付けられている電子情報開示ケースに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-351">You can use the  `Get-CaseHoldPolicy` cmdlet in Security & Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with.</span></span> <span data-ttu-id="5b3fb-352">たとえば、コマンドを実行して、  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` メールボックスにあるケースホールドの名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-352">For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox.</span></span> <span data-ttu-id="5b3fb-353">Be sure to remove the  `UniH` プレフィックスを削除してください。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-353">Be sure to remove the  `UniH` prefix when you run this command.</span></span>  <br/><br/> <span data-ttu-id="5b3fb-354">メールボックスの保留リストが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b3fb-354">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`
