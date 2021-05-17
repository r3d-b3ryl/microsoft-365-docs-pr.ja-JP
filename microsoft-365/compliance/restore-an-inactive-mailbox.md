---
title: 非アクティブなメールボックスを復元する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) する方法についてOffice 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917301"
---
# <a name="restore-an-inactive-mailbox"></a><span data-ttu-id="95c9a-103">非アクティブなメールボックスを復元する</span><span class="sxs-lookup"><span data-stu-id="95c9a-103">Restore an inactive mailbox</span></span>

<span data-ttu-id="95c9a-p101">非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p101">An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:</span></span>

- <span data-ttu-id="95c9a-p102">**非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。非アクティブなメールボックスからアーカイブを復元することもできます。復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。このトピックでは、非アクティブなメールボックスを復元するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p102">**Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.</span></span>

- <span data-ttu-id="95c9a-110">**非アクティブなメールボックスを回復する** 退職した従業員が組織に復帰した場合や、退職した従業員の職責を引き継ぐために新入社員が採用された場合は、非アクティブなメールボックスのコンテンツを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-110">**Recover an inactive mailbox** If the departed employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox.</span></span> <span data-ttu-id="95c9a-111">このメソッドは、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-111">This method converts the inactive mailbox to a new mailbox that contains the contents of the inactive mailbox.</span></span> <span data-ttu-id="95c9a-112">回復された後、非アクティブなメールボックスは存在しなくなります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-112">After it's recovered, the inactive mailbox no longer exists.</span></span> <span data-ttu-id="95c9a-113">手順については、「アクティブでないメールボックスを回復[する](recover-an-inactive-mailbox.md)」を参照Office 365。</span><span class="sxs-lookup"><span data-stu-id="95c9a-113">For the step-by-step procedures, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

<span data-ttu-id="95c9a-114">非アクティブ [なメールボックスの](#more-information) 復元と回復の違いの詳細については、この記事の「詳細情報」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c9a-114">See the [More information](#more-information) section in this article for more details about the differences between restoring and recovering an inactive mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="95c9a-115">自動拡張アーカイブで構成されている非アクティブなメールボックスを回復または復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="95c9a-115">You can't recover or restore an inactive mailbox that's configured with an auto-expanding archive.</span></span> <span data-ttu-id="95c9a-116">自動拡張アーカイブを使用して非アクティブなメールボックスからデータを回復する必要がある場合は、コンテンツ検索を使用してメールボックスからデータをエクスポートし、別のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="95c9a-116">If you need to recover data from an inactive mailbox with an auto-expanding archive, use content search to export the data from the mailbox and then import to another mailbox.</span></span> <span data-ttu-id="95c9a-117">手順については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c9a-117">For instructions, see following topics:</span></span>
>
> - [<span data-ttu-id="95c9a-118">コンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="95c9a-118">Content search</span></span>](content-search.md)
> - [<span data-ttu-id="95c9a-119">コンテンツ検索結果のエクスポート</span><span class="sxs-lookup"><span data-stu-id="95c9a-119">Export content search results</span></span>](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a><span data-ttu-id="95c9a-120">非アクティブなメールボックスを復元する要件</span><span class="sxs-lookup"><span data-stu-id="95c9a-120">Requirements to restore an inactive mailbox</span></span>

- <span data-ttu-id="95c9a-121">非アクティブなメールボックスを復元するには、Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-121">You have to use Exchange Online PowerShell to restore an inactive mailbox.</span></span> <span data-ttu-id="95c9a-122">Exchange 管理センター (EAC) を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="95c9a-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="95c9a-123">詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c9a-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="95c9a-124">PowerShell で次のコマンドをExchange Online、組織内の非アクティブなメールボックスの ID 情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-124">Run the following command in Exchange Online PowerShell to get identity information for the inactive mailboxes in your organization.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  <span data-ttu-id="95c9a-125">このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-125">Use the information returned by this command to restore a specific inactive mailbox.</span></span>

- <span data-ttu-id="95c9a-126">非アクティブなメールボックスの詳細については、「非アクティブなメールボックス」[を参照Office 365。](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="95c9a-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="restore-inactive-mailboxes"></a><span data-ttu-id="95c9a-127">非アクティブなメールボックスの復元</span><span class="sxs-lookup"><span data-stu-id="95c9a-127">Restore inactive mailboxes</span></span>

<span data-ttu-id="95c9a-p106">**New-MailboxRestoreRequest** コマンドレットを  _SourceMailbox_ と  _TargetMailbox_ パラメーターと共に使用して、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。このコマンドレットの使用方法について詳しくは、「 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p106">Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest).</span></span>

1. <span data-ttu-id="95c9a-130">非アクティブなメールボックスのプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-130">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="95c9a-p107">上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="95c9a-p108">非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。非アクティブなメールボックス (ソース メールボックス) のコンテンツは、既存のメールボックス (ターゲット メールボックス) の対応するフォルダーにマージされます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p108">Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   <span data-ttu-id="95c9a-p109">または、非アクティブなメールボックスのコンテンツの復元先として、ターゲット メールボックス内の最上位フォルダーを指定することもできます。指定したターゲット フォルダーまたはターゲット フォルダー構造がターゲット メールボックス内に存在しない場合は、復元処理中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p109">Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process.</span></span>

   <span data-ttu-id="95c9a-137">次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="95c9a-137">This example copies mailbox items and subfolders from an inactive mailbox to a folder named "Inactive Mailbox" in the top-level folder structure of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a><span data-ttu-id="95c9a-138">非アクティブなメールボックスからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="95c9a-138">Restore the archive from an inactive mailbox</span></span>

<span data-ttu-id="95c9a-139">非アクティブなメールボックスにアーカイブ メールボックスがある場合も、それを既存のメールボックスのアーカイブ メールボックスに復元できます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-139">If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox.</span></span> <span data-ttu-id="95c9a-140">非アクティブなメールボックスからアーカイブを復元するには、非アクティブなメールボックスの復元に使用するコマンドに _SourceIsArchive_ スイッチと _TargetIsArchive_ スイッチを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-140">To restore the archive from an inactive mailbox, you have to add the _SourceIsArchive_ and _TargetIsArchive_ switches to the command used to restore an inactive mailbox.</span></span>

1. <span data-ttu-id="95c9a-141">非アクティブなメールボックスのプロパティを含む変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="95c9a-141">Create a variable that contains the properties of the inactive mailbox.</span></span>

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > <span data-ttu-id="95c9a-p111">上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p111">In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.</span></span>

2. <span data-ttu-id="95c9a-p112">アーカイブのコンテンツを、非アクティブなメールボックス (ソース アーカイブ) から既存のメールボックスのアーカイブ (ターゲット アーカイブ) に復元します。この例では、ソース アーカイブのコンテンツが、ターゲット メールボックスのアーカイブ内の「Inactive Mailbox Archive」という名前のフォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p112">Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.</span></span>

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a><span data-ttu-id="95c9a-146">詳細情報</span><span class="sxs-lookup"><span data-stu-id="95c9a-146">More information</span></span>

- <span data-ttu-id="95c9a-147">**非アクティブなメールボックスを回復することと復元することとの主な違い。**</span><span class="sxs-lookup"><span data-stu-id="95c9a-147">**What's the main difference between recovering and restoring an inactive mailbox?**</span></span> <span data-ttu-id="95c9a-148">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span><span class="sxs-lookup"><span data-stu-id="95c9a-148">When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account.</span></span> <span data-ttu-id="95c9a-149">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="95c9a-149">After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox.</span></span> <span data-ttu-id="95c9a-150">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span><span class="sxs-lookup"><span data-stu-id="95c9a-150">Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox.</span></span> <span data-ttu-id="95c9a-151">The inactive mailbox is preserved and remains an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="95c9a-151">The inactive mailbox is preserved and remains an inactive mailbox.</span></span> <span data-ttu-id="95c9a-152">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="95c9a-152">Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox.</span></span> <span data-ttu-id="95c9a-153">非アクティブなメールボックスは、コンテンツ検索ツールを使用[](content-search.md)して検索したり、その内容を別のメールボックスに復元したり、後で回復または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-153">The inactive mailbox can still be searched by using the [Content Search tool](content-search.md), its contents can be restored to another mailbox, or it can be recovered or deleted at a later date.</span></span>

- <span data-ttu-id="95c9a-p114">**非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p114">**How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.</span></span>

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- <span data-ttu-id="95c9a-156">**非アクティブなメールボックス コンテンツを保持するにはMicrosoft 365保持ポリシーを使用します。**</span><span class="sxs-lookup"><span data-stu-id="95c9a-156">**Use a Litigation Hold or Microsoft 365 retention policy to retain inactive mailbox content.**</span></span> <span data-ttu-id="95c9a-157">非アクティブなメールボックスの復元後に状態を保持する場合は、非アクティブなメールボックスを復元する前に、[](create-a-litigation-hold.md)ターゲット メールボックスを訴訟ホールドに配置するか[、Microsoft 365](retention.md)アイテム保持ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-157">If you want to retain the state of an inactive mailbox after it's restored, you can place the target mailbox on [Litigation Hold](create-a-litigation-hold.md) or apply an [Microsoft 365 retention policy](retention.md) before you restore the inactive mailbox.</span></span> <span data-ttu-id="95c9a-158">これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-158">This will prevent the permanent deletion of any items from the inactive mailbox after they're restored to the target mailbox.</span></span>

- <span data-ttu-id="95c9a-159">**非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にする。**</span><span class="sxs-lookup"><span data-stu-id="95c9a-159">**Enable retention hold on the target mailbox before you restore an inactive mailbox.**</span></span> <span data-ttu-id="95c9a-160">非アクティブなメールボックスのメールボックス アイテムは古くなっている可能性があるため、非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にすることを検討できます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-160">Because mailbox items from an inactive mailbox could be old, you might consider enabling retention hold on the target mailbox before you restore an inactive mailbox.</span></span> <span data-ttu-id="95c9a-161">メールボックスでの保存機能を有効にすると、保存機能が削除されるかまたは保存期間が期限切れになるまで、それに割り当てられた保持ポリシーは処理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-161">When you put a mailbox on retention hold, the retention policy that's assigned to it won't be processed until the retention hold is removed or until the retention hold period expires.</span></span> <span data-ttu-id="95c9a-162">これにより、ターゲット メールボックスの所有者が非アクティブなメールボックスからの古いメッセージを処理するための時間ができます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-162">This gives the owner of the target mailbox time to manage old messages from the inactive mailbox.</span></span> <span data-ttu-id="95c9a-163">そうしないと、ターゲット メールボックスに構成された保存期間の設定に基づいて、期限切れになっている古いアイテムが保持ポリシーによって削除される (またはアーカイブ メールボックスが使用可能な場合にはアイテムがそこに移動される) 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-163">Otherwise, the retention policy might delete old items (or move items to the archive mailbox, if it's enabled) that have expired based on the retention settings configured for the target mailbox.</span></span> <span data-ttu-id="95c9a-164">詳細については、「メールボックスを保持[の保持に保持する」を参照](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95c9a-164">For more information, see [Place a mailbox on retention hold in Exchange Online](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).</span></span>

- <span data-ttu-id="95c9a-p117">**AllowLegacyDNMismatch スイッチの機能。** 非アクティブなメールボックスを復元する前述の例では、 **AllowLegacyDNMismatch** スイッチの使用によって、非アクティブなメールボックスを別のターゲット メールボックスに復元できるようになります。一般的な復元シナリオでは、ソース メールボックスとターゲット メールボックスが同じメールボックスのときに、コンテンツを復元することが目標となります。そのため既定では、 **New-MailboxRestoreRequest** コマンドレットにより、ソース メールボックスとターゲット メールボックスの **LegacyExchangeDN** プロパティの値が同じであることが確認されます。これにより、ソース メールボックスが誤って正しくないターゲット メールボックスに復元されることを防止します。 **AllowLegacyDNMismatch** スイッチを使用しないで非アクティブなメールボックスの復元を試行すると、ソース メールボックスとターゲット メールボックスで **LegacyExchangeDN** プロパティの値が異なる場合に、コマンドは失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p117">**What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.</span></span>

- <span data-ttu-id="95c9a-p118">**New-MailboxRestoreRequest コマンドレットと共に他のパラメーターを使用して、非アクティブなメールボックスのさまざまな復元シナリオを実装できます。** たとえば、次のコマンドを実行して、非アクティブなメールボックスからターゲット メールボックスのプライマリ メールボックスにアーカイブを復元できます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p118">**You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  <span data-ttu-id="95c9a-173">また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="95c9a-173">You can also restore the inactive primary mailbox into the archive of the target mailbox by running this command.</span></span>

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- <span data-ttu-id="95c9a-p119">**TargetRootFolder パラメーターの機能。** 前述のように、 **TargetRootFolder** パラメーターを使用して、非アクティブなメールボックスのコンテンツを復元するためにターゲット メールボックス内のフォルダー構造の最上位フォルダー ( ルートとも呼ばれる) を指定できます。このパラメーターを使用しない場合、非アクティブなメールボックスのメールボックス アイテムはターゲット メールボックスの対応する既定のフォルダーにマージされ、カスタム フォルダーがターゲット メールボックスのルートに再作成されます。次の図は、 **TargetRootFolder** パラメーターを使用しない場合と使用する場合の、これらの相違点を強調しています。</span><span class="sxs-lookup"><span data-stu-id="95c9a-p119">**What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.</span></span>

  <span data-ttu-id="95c9a-178">**TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**</span><span class="sxs-lookup"><span data-stu-id="95c9a-178">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter isn't used**</span></span>

  ![TargetRootFolder パラメーターを使用していないときのスクリーン ショット](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  <span data-ttu-id="95c9a-180">**TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**</span><span class="sxs-lookup"><span data-stu-id="95c9a-180">**Folder hierarchy in the target mailbox when the TargetRootFolder parameter is used**</span></span>

  ![TargetRootFolder パラメーターが使用されているときのスクリーン ショット](../media/300da592-7323-48db-b8a4-07012259d113.png)