---
title: 顧客キーを管理する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可とデータ暗号化ポリシーを管理することによって、キーを管理する方法について説明します。
ms.openlocfilehash: dbdbd61b4d06e183d8cc5461122e316b2b6b1797
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352204"
---
# <a name="manage-customer-key"></a><span data-ttu-id="be402-103">顧客キーを管理する</span><span class="sxs-lookup"><span data-stu-id="be402-103">Manage Customer Key</span></span>

<span data-ttu-id="be402-104">Office 365 の顧客キーを設定した後、この記事で説明されているようにキーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="be402-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="be402-105">関連するトピックの「顧客キー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="be402-106">Azure Key Vault キーを復元する</span><span class="sxs-lookup"><span data-stu-id="be402-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="be402-107">復元を実行する前に、ソフト削除で提供される回復機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="be402-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="be402-108">ユーザーキーで使用されるすべてのキーは、ソフト削除を有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="be402-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="be402-109">ソフト削除は、ごみ箱と同じように動作し、復元する必要がなくても最大90日の復旧が可能です。</span><span class="sxs-lookup"><span data-stu-id="be402-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="be402-110">復元は、キーまたはキーの保管が失われた場合など、極端または異常な状況でのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="be402-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="be402-111">顧客キーと一緒に使用するためにキーを復元する必要がある場合は、Azure PowerShell で、AzureKeyVaultKey コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="be402-112">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="be402-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="be402-113">キー vault に同じ名前のキーが既に含まれている場合、復元操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="be402-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="be402-114">AzKeyVaultKey は、キーの名前を含むキーのすべてのキーバージョンとすべてのメタデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="be402-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="be402-115">キーコンテナーのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="be402-115">Manage key vault permissions</span></span>

<span data-ttu-id="be402-116">いくつかのコマンドレットを使用して、重要な資格情報のアクセス許可を表示および削除できます。</span><span class="sxs-lookup"><span data-stu-id="be402-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="be402-117">たとえば、従業員がチームを離れるときにアクセス許可を削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="be402-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="be402-118">これらの各タスクでは、Azure PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="be402-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="be402-119">Azure Powershell の詳細については、「 [Azure powershell の概要](https://docs.microsoft.com/powershell/azure/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="be402-120">重要な資格情報コンテナーのアクセス許可を表示するには、-AzKeyVault コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="be402-121">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="be402-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="be402-122">管理者のアクセス許可を削除するには、AzKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="be402-123">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="be402-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="be402-124">顧客キーを使用してデータ暗号化ポリシー (DEPs) を管理する</span><span class="sxs-lookup"><span data-stu-id="be402-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="be402-125">顧客キーは、異なるサービス間で異なる方法で Ps を処理します。</span><span class="sxs-lookup"><span data-stu-id="be402-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="be402-126">たとえば、異なるサービスに対して異なる数の DEPs を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="be402-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="be402-127">**Exchange Online と Skype For business:** 最大 50 DEPs を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be402-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="be402-128">手順については、「 [Exchange Online および Skype For business で使用するデータ暗号化ポリシー (DEP) を作成する](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="be402-129">**SharePoint Online、OneDrive For business、Teams の各ファイル:** DEP は、1つの地理的位置 ( _geo_とも呼ばれる) のデータに適用されます。</span><span class="sxs-lookup"><span data-stu-id="be402-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="be402-130">Office 365 の複数地域機能を使用する場合は、geo ごとに1つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be402-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="be402-131">複数地域を使用していない場合は、1つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be402-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="be402-132">通常は、顧客キーを設定するときに DEP を作成します。</span><span class="sxs-lookup"><span data-stu-id="be402-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="be402-133">手順については、「 [SharePoint Online および OneDrive For business geo のデータ暗号化ポリシー (DEP) を作成する](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="be402-134">Exchange Online と Skype for Business 用に作成した DEPs を表示する</span><span class="sxs-lookup"><span data-stu-id="be402-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="be402-135">Exchange Online と Skype for Business 用に作成したすべての DEPs の一覧を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="be402-136">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="be402-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="be402-137">組織内のすべての DEPs を戻すには、パラメーターを指定せずに、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="be402-138">Get-DataEncryptionPolicy コマンドレットの詳細については、「 [get-dataencryptionpolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="be402-139">メールボックスをクラウドに移行する前に DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="be402-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="be402-140">DEP 365 を割り当てると、移行時に、割り当てられた DEP を使用してメールボックスのコンテンツが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="be402-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="be402-141">このプロセスは、メールボックスを移行して DEP を割り当ててから、暗号化の実行を待機するよりも効率的です。これには、数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="be402-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="be402-142">Office 365 に移行する前に、メールボックスに DEP を割り当てるには、Exchange Online PowerShell で Set-MailUser コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="be402-143">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="be402-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="be402-144">Set-MailUser コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="be402-145">*GeneralMailboxOrMailUserIdParameter*にはメールボックスを指定し、 *Dataencryptionpolicyidparameter*は DEP の ID です。</span><span class="sxs-lookup"><span data-stu-id="be402-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="be402-146">Set-mailuser コマンドレットの詳細については、「 [set-mailuser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="be402-147">メールボックスに割り当てられた DEP を決定する</span><span class="sxs-lookup"><span data-stu-id="be402-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="be402-148">メールボックスに割り当てられている DEP を特定するには、Get-mailboxstatistics コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="be402-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="be402-149">コマンドレットは、一意の識別子 (GUID) を返します。</span><span class="sxs-lookup"><span data-stu-id="be402-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="be402-150">組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="be402-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="be402-151">ここで、 *GeneralMailboxOrMailUserIdParameter*はメールボックスと DataEncryptionPolicyID を指定し、DEP の GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="be402-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="be402-152">Get-mailboxstatistics コマンドレットの詳細については、「 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="be402-153">Get-DataEncryptionPolicy コマンドレットを実行して、メールボックスが割り当てられている DEP のフレンドリ名を検索します。</span><span class="sxs-lookup"><span data-stu-id="be402-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="be402-154">ここで、 *guid*は、前の手順で get-mailboxstatistics コマンドレットによって返される guid です。</span><span class="sxs-lookup"><span data-stu-id="be402-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="be402-155">顧客キーが暗号化を完了したことを確認する</span><span class="sxs-lookup"><span data-stu-id="be402-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="be402-156">顧客キーをロールアウトし、新しい DEP を割り当てたか、メールボックスを移行したばかりの場合は、このセクションの手順を使用して暗号化が完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="be402-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="be402-157">Exchange Online と Skype for Business の暗号化が完了していることを確認する</span><span class="sxs-lookup"><span data-stu-id="be402-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="be402-158">メールボックスを暗号化するには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="be402-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="be402-159">DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="be402-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="be402-160">メールボックスが暗号化されているかどうかを確認するには、Get-mailboxstatistics コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="be402-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="be402-161">IsEncrypted プロパティは、メールボックスが暗号化されている場合は**true**の値を返し、メールボックスが暗号化されていない場合は**false**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="be402-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="be402-162">メールボックスの移動が完了するまでの時間は、メールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="be402-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="be402-163">新しい DEP を割り当てた時点から72時間後にメールボックスが完全に暗号化されていない場合は、メールボックスの移動を開始します。</span><span class="sxs-lookup"><span data-stu-id="be402-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, initiate a mailbox move.</span></span> <span data-ttu-id="be402-164">これを行うには、New-moverequest コマンドレットを使用して、メールボックスのエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="be402-164">To do this, use the New-MoveRequest cmdlet and provide the alias of the mailbox.</span></span> <span data-ttu-id="be402-165">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="be402-165">For example:</span></span>
  
```powershell
New-MoveRequest <alias>
```

<span data-ttu-id="be402-166">このコマンドレットの詳細については、「 [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/new-moverequest?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-166">For more information about this cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/new-moverequest?view=exchange-ps).</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="be402-167">SharePoint Online、OneDrive for Business、および Teams ファイルの暗号化が完了していることを確認する</span><span class="sxs-lookup"><span data-stu-id="be402-167">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="be402-168">Get-spodataencryptionpolicy コマンドレットを次のように実行して、暗号化の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="be402-168">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="be402-169">このコマンドレットの出力には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be402-169">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="be402-170">主キーの URI。</span><span class="sxs-lookup"><span data-stu-id="be402-170">The URI of the primary key.</span></span>

- <span data-ttu-id="be402-171">セカンダリキーの URI。</span><span class="sxs-lookup"><span data-stu-id="be402-171">The URI of the secondary key.</span></span>

- <span data-ttu-id="be402-172">Geo の暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="be402-172">The encryption status for the geo.</span></span> <span data-ttu-id="be402-173">次の状態が考えられます。</span><span class="sxs-lookup"><span data-stu-id="be402-173">Possible states include:</span></span>

  - <span data-ttu-id="be402-174">**未登録:** 顧客キーの暗号化はまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="be402-174">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="be402-175">**登録:** 顧客キーの暗号化が適用され、ファイルが暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="be402-175">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="be402-176">Geo のキーが登録されている場合は、暗号化の進行状況を監視できるように、地域内のサイトの割合に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="be402-176">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="be402-177">**登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されました。</span><span class="sxs-lookup"><span data-stu-id="be402-177">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="be402-178">**ローリング:** キーロールが進行中です。</span><span class="sxs-lookup"><span data-stu-id="be402-178">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="be402-179">Geo のキーがローリングの場合は、進行状況を監視できるように、キーロール操作を完了したサイトの割合に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="be402-179">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="be402-180">キーを無効にし、データ削除パスプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="be402-180">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="be402-181">可用性キーを含むすべてのルートキーの取り消しを制御します。</span><span class="sxs-lookup"><span data-stu-id="be402-181">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="be402-182">顧客キーは、規制要件の終了計画についての制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="be402-182">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="be402-183">データを削除してサービスを終了するためのキーを失効させる場合、データの削除プロセスが完了すると、サービスによって可用性キーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="be402-183">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="be402-184">Microsoft 365 は、データ削除パスを監査して検証します。</span><span class="sxs-lookup"><span data-stu-id="be402-184">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="be402-185">詳細については、 [Service Trust Portal](https://servicetrust.microsoft.com/)で利用できる SSAE 18 SOC 2 レポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be402-185">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="be402-186">さらに、Microsoft は次のドキュメントをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="be402-186">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="be402-187">Microsoft クラウドでの金融機関のリスク評価およびコンプライアンスガイド</span><span class="sxs-lookup"><span data-stu-id="be402-187">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="be402-188">O365 終了計画に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="be402-188">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="be402-189">データ削除パスは、さまざまなサービス間で少し異なります。</span><span class="sxs-lookup"><span data-stu-id="be402-189">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="be402-190">Exchange Online と Skype for Business の顧客キーと可用性キーを無効にする</span><span class="sxs-lookup"><span data-stu-id="be402-190">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="be402-191">Exchange Online と Skype for Business のデータ削除パスを開始するときは、DEP で永続的なデータ削除要求を設定します。</span><span class="sxs-lookup"><span data-stu-id="be402-191">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="be402-192">これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="be402-192">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="be402-193">一度に1つの DEP に対してのみ PowerShell コマンドレットを実行できるため、データの削除パスを開始する前に、すべてのメールボックスに対して単一の DEP を再割り当てすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="be402-193">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="be402-194">メールボックスのサブセットを削除するのには、データ削除パスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="be402-194">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="be402-195">このプロセスは、サービスを終了しているお客様のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="be402-195">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="be402-196">データの削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-196">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="be402-197">Azure Key コンテナーから、"O365 Exchange Online" のラップとラップ解除のアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="be402-197">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="be402-198">組織のグローバル管理者特権を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="be402-198">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="be402-199">削除するメールボックスを含む DEP ごとに、次のように[Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-199">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="be402-200">コマンドが失敗した場合は、このタスクで前述したように、Azure Key Vault の両方のキーから Exchange Online アクセス許可が削除されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="be402-200">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="be402-201">PermanentDataPurgeRequested スイッチを設定して、このコマンドレットを使用すると、この DEP をメールボックスに割り当てることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="be402-201"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="be402-202">Microsoft サポートに連絡し、データ削除 eDocument を要求します。</span><span class="sxs-lookup"><span data-stu-id="be402-202">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="be402-203">要求に応じて、Microsoft から法的文書が送信され、データの削除を確認して承認します。</span><span class="sxs-lookup"><span data-stu-id="be402-203">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="be402-204">このドキュメントに署名する必要があるのは、オンボード時に FastTrack オファーで承認者としてサインアップした組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="be402-204">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="be402-205">通常、これは、組織の代わりに書類に署名することを正当に承認されている社内のエグゼクティブまたはその他の指定者です。</span><span class="sxs-lookup"><span data-stu-id="be402-205">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="be402-206">担当者が法的文書に署名したら、Microsoft に返信します (通常は eDoc 署名を使用)。</span><span class="sxs-lookup"><span data-stu-id="be402-206">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="be402-207">Microsoft が法的文書を受け取ると、Microsoft はコマンドレットを実行して、最初にポリシーを削除し、メールボックスの完全削除をマークし、可用性キーを削除する、データの削除をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="be402-207">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="be402-208">データ削除プロセスが完了すると、データは削除され、Exchange Online からはアクセスできなくなります。復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="be402-208">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="be402-209">SharePoint Online、OneDrive for Business、および Teams ファイルのお客様キーと可用性キーを無効にする</span><span class="sxs-lookup"><span data-stu-id="be402-209">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="be402-210">SharePoint Online、OneDrive for Business、および Teams ファイルのデータ削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be402-210">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="be402-211">Azure Key Vault アクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="be402-211">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="be402-212">すべてのキーコンテナー管理者がアクセスを取り消すことに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be402-212">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="be402-213">SharePoint Online の Azure キーコンテナーは削除しません。</span><span class="sxs-lookup"><span data-stu-id="be402-213">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="be402-214">キーコンテナーは、いくつかの SharePoint Online テナントと DEPs 間で共有される場合があります。</span><span class="sxs-lookup"><span data-stu-id="be402-214">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="be402-215">Microsoft に連絡して、空き時間情報キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="be402-215">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="be402-216">Microsoft に連絡して可用性キーを削除すると、法的文書が送信されます。</span><span class="sxs-lookup"><span data-stu-id="be402-216">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="be402-217">このドキュメントに署名する必要があるのは、オンボード時に FastTrack オファーで承認者としてサインアップした組織内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="be402-217">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="be402-218">通常、これは、組織の代わりに書類に署名する法的な権限を持つ、社内のエグゼクティブまたはその他の指定者です。</span><span class="sxs-lookup"><span data-stu-id="be402-218">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="be402-219">代表者が法的文書に署名したら、マイクロソフトに返送します (通常は eDoc 署名を使用)。</span><span class="sxs-lookup"><span data-stu-id="be402-219">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="be402-220">Microsoft が法的文書を受け取ったら、コマンドレットを実行して、テナントキー、サイトキー、および各ドキュメントの各キーの暗号化削除を実行するデータ削除をトリガーします。キー階層を irrevocably します。</span><span class="sxs-lookup"><span data-stu-id="be402-220">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="be402-221">データ削除コマンドレットが完了すると、データが削除されています。</span><span class="sxs-lookup"><span data-stu-id="be402-221">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="be402-222">関連記事</span><span class="sxs-lookup"><span data-stu-id="be402-222">Related articles</span></span>

- [<span data-ttu-id="be402-223">顧客キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="be402-223">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="be402-224">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="be402-224">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="be402-225">顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="be402-225">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="be402-226">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="be402-226">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="be402-227">カスタマー ロックボックス</span><span class="sxs-lookup"><span data-stu-id="be402-227">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="be402-228">サービス暗号化</span><span class="sxs-lookup"><span data-stu-id="be402-228">Service Encryption</span></span>](office-365-service-encryption.md)
