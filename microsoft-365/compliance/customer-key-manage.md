---
title: 顧客キーの管理
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
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可とデータ暗号化ポリシーを管理して、そのキーを管理する方法について説明します。
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394671"
---
# <a name="manage-customer-key"></a><span data-ttu-id="d9a4a-103">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="d9a4a-103">Manage Customer Key</span></span>

<span data-ttu-id="d9a4a-104">365 の顧客キーをOffice、この記事の説明に従ってキーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="d9a4a-105">関連トピックの顧客キーの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="d9a4a-106">Azure Key Vault キーの復元</span><span class="sxs-lookup"><span data-stu-id="d9a4a-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="d9a4a-107">復元を実行する前に、ソフト削除によって提供される回復機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="d9a4a-108">顧客キーと一緒に使用するキーはすべて、ソフト削除を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="d9a4a-109">削除はごみ箱のように機能し、復元する必要なしに最大 90 日間の回復を可能にします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="d9a4a-110">キーまたはキー コンテナーが失われた場合など、極端な状況や異常な状況でのみ復元が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="d9a4a-111">顧客キーで使用するキーを復元する必要がある場合は、Azure PowerShell で、次のように Restore-AzureKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="d9a4a-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="d9a4a-113">キー コンテナーに同じ名前のキーが既に含まれている場合、復元操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="d9a4a-114">Restore-AzKeyVaultKey、すべてのキー バージョンと、キー名を含むキーのすべてのメタデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="d9a4a-115">キー コンテナーのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-115">Manage key vault permissions</span></span>

<span data-ttu-id="d9a4a-116">いくつかのコマンドレットを使用して、キー コンテナーのアクセス許可を表示したり、必要に応じて削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="d9a4a-117">従業員がチームを離れる場合など、アクセス許可を削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="d9a4a-118">これらの各タスクについて、Azure PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="d9a4a-119">Azure Powershell の詳細については [、「Azure PowerShell の概要」を参照してください](/powershell/azure/)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="d9a4a-120">キー コンテナーのアクセス許可を表示するには、次のコマンドレットGet-AzKeyVaultします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="d9a4a-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="d9a4a-122">管理者のアクセス許可を削除するには、次のコマンドレットをRemove-AzKeyVaultAccessPolicyします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="d9a4a-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="d9a4a-124">顧客キーを使用してデータ暗号化ポリシー (DEP) を管理する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="d9a4a-125">顧客キーは、異なるサービス間で DEP を異なる方法で処理します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="d9a4a-126">たとえば、異なるサービスに対して異なる数の DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="d9a4a-127">**Exchange Online と Skype for Business:** 最大 50 の DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="d9a4a-128">手順については、「Exchange Online および Skype for Business で使用するデータ暗号化ポリシー [(DEP) の作成」を参照してください](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="d9a4a-129">**SharePoint Online、OneDrive for Business、Teams ファイル:** DEP は、地理的な場所 (geo とも呼ばれる) のデータに適用 _されます_。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="d9a4a-130">365 の複数地域機能を使用Office地域ごとに 1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="d9a4a-131">複数地域を使用していない場合は、1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="d9a4a-132">通常、顧客キーを設定するときに DEP を作成します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="d9a4a-133">手順については [、「SharePoint Online および OneDrive for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)geo ごとにデータ暗号化ポリシー (DEP) を作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d9a4a-134">Exchange Online および Skype for Business 用に作成した DEP を表示する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d9a4a-135">PowerShell コマンドレットを使用して Exchange Online および Skype for Business 用に作成したすべての DEP の一覧を表示するには、Get-DataEncryptionPolicy手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d9a4a-136">組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d9a4a-137">組織内のすべての DEP を返す場合は、パラメーターを指定せずに Get-DataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="d9a4a-138">このコマンドレットの詳細についてはGet-DataEncryptionPolicy [Get-DataEncryptionPolicy を参照してください](/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="d9a4a-139">メールボックスをクラウドに移行する前に DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="d9a4a-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="d9a4a-140">DEP を割り当てると、移行中に割り当てられた DEP を使用してメールボックスの内容が暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="d9a4a-141">このプロセスは、メールボックスの移行、DEP の割り当て、暗号化の実行を待機するよりも効率的です。これには数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="d9a4a-142">メールボックスを 365 に移行する前に DEP をOfficeするには、Exchange Online PowerShell Set-MailUserコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="d9a4a-143">組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d9a4a-144">このコマンドレットをSet-MailUserします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="d9a4a-145">*GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し *、DataEncryptionPolicyIdParameter* は DEP の ID です。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="d9a4a-146">このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="d9a4a-147">メールボックスに割り当てられた DEP を決定する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="d9a4a-148">メールボックスに割り当てられた DEP を確認するには、次のコマンドレットGet-MailboxStatisticsします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="d9a4a-149">コマンドレットは、一意の識別子 (GUID) を返します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="d9a4a-150">組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="d9a4a-151">*GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し、DataEncryptionPolicyID は DEP の GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="d9a4a-152">このコマンドレットの詳細についてはGet-MailboxStatistics [Get-MailboxStatistics を参照してください](/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="d9a4a-153">このコマンドレットGet-DataEncryptionPolicy実行して、メールボックスが割り当てられている DEP の表示名を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="d9a4a-154">ここで *、GUID* は、前の手順の Get-MailboxStatisticsコマンドレットによって返される GUID です。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="d9a4a-155">顧客キーが暗号化を完了したのを確認する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="d9a4a-156">顧客キーをロールしたばかりか、新しい DEP が割り当てられているか、メールボックスを移行したのかは、このセクションの手順を使用して、暗号化が完了します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d9a4a-157">Exchange Online と Skype for Business の暗号化が完了した場合の確認</span><span class="sxs-lookup"><span data-stu-id="d9a4a-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d9a4a-158">メールボックスの暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="d9a4a-159">DEP を変更した後、または初めてメールボックスに DEP を割り当てると、暗号化の検証を試行するまで 72 時間待機することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="d9a4a-160">メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="d9a4a-161">IsEncrypted プロパティは、メールボックスが暗号化されている場合は **true、** メールボックスが暗号化されていない場合は **false** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="d9a4a-162">メールボックスの移動を完了する時間は、メールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="d9a4a-163">新しい DEP の割り当てから 72 時間後に顧客キーがメールボックスを完全に暗号化しない場合は、Microsoft サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="d9a4a-164">このNew-MoveRequestは、ローカル メールボックスの移動に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="d9a4a-165">詳細については [、このお知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) らせを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="d9a4a-166">SharePoint Online、OneDrive for Business、Teams ファイルの暗号化が完了した場合の確認</span><span class="sxs-lookup"><span data-stu-id="d9a4a-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d9a4a-167">次のように、Get-SPODataEncryptionPolicyコマンドレットを実行して、暗号化の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="d9a4a-168">このコマンドレットの出力には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="d9a4a-169">主キーの URI。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-169">The URI of the primary key.</span></span>

- <span data-ttu-id="d9a4a-170">セカンダリ キーの URI。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="d9a4a-171">geo の暗号化状態。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-171">The encryption status for the geo.</span></span> <span data-ttu-id="d9a4a-172">可能な状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-172">Possible states include:</span></span>

  - <span data-ttu-id="d9a4a-173">**未登録:** 顧客キーの暗号化がまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="d9a4a-174">**登録:** 顧客キーの暗号化が適用され、ファイルが暗号化中です。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="d9a4a-175">geo のキーが登録されている場合は、暗号化の進行状況を監視するために、geo 内のサイトが完了した割合に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="d9a4a-176">**登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="d9a4a-177">**ローリング:** キー ロールが進行中です。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="d9a4a-178">geo のキーがローリングされている場合は、キー ロール操作を完了したサイトの割合に関する情報も表示され、進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="d9a4a-179">顧客キーから Microsoft マネージ キーへのロールバック</span><span class="sxs-lookup"><span data-stu-id="d9a4a-179">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="d9a4a-180">テナント レベルの顧客キーの場合は、顧客キーからの "offboarding" の要求を受け取って Microsoft に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-180">For Customer Key at the tenant level, you'll need to reach out to Microsoft with a request for “offboarding” from Customer Key.</span></span> <span data-ttu-id="d9a4a-181">要求は On Call Engineering チームによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-181">The request will be handled by the On Call Engineering team.</span></span>

<span data-ttu-id="d9a4a-182">アプリケーション レベルの顧客キーの場合は、Set-mailbox PowerShell コマンドレットを使用してメールボックスから DEP の割り当てを解除し、にを設定します `DataEncryptionPolicy` `$NULL` 。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-182">For Customer Key at the application level, you do this by unassigning a DEP from mailboxes using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="d9a4a-183">このコマンドレットを実行すると、現在割り当てられている DEP の割り当てを解除し、既定の Microsoft 管理キーに関連付けられた DEP を使用してメールボックスを再暗号化します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-183">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="d9a4a-184">Microsoft マネージ キーで使用される DEP の割り当てを解除できません。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-184">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="d9a4a-185">Microsoft 管理キーを使用しない場合は、別の顧客キー DEP をメールボックスに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-185">If you don't want to use Microsoft managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

<span data-ttu-id="d9a4a-186">PowerShell コマンドレットを使用してメールボックスから DEP の割り当てを解除Set-Mailbox手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-186">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="d9a4a-187">組織内でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-187">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="d9a4a-188">このコマンドレットをSet-Mailboxします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-188">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="d9a4a-189">キーを取り消し、データ削除パス プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="d9a4a-189">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="d9a4a-190">可用性キーを含むすべてのルート キーの失効を制御します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-190">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="d9a4a-191">顧客キーは、規制要件の出口計画の側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-191">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="d9a4a-192">データを削除してサービスを終了するためにキーを取り消す場合、データ削除プロセスが完了すると、サービスは可用性キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-192">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="d9a4a-193">テナント レベルのポリシーに対してデータ削除を実行できません。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-193">You can't perform a data purge for a tenant-level policy.</span></span>

<span data-ttu-id="d9a4a-194">Microsoft 365 は、データ削除パスを監査および検証します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-194">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="d9a4a-195">詳細については、「SSAE 18 SOC 2 Report available on the [Service Trust Portal」を参照してください](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-195">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="d9a4a-196">さらに、Microsoft では次のドキュメントを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-196">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="d9a4a-197">Microsoft Cloud の金融機関のリスク評価とコンプライアンス ガイド</span><span class="sxs-lookup"><span data-stu-id="d9a4a-197">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="d9a4a-198">O365 Exit Planning に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d9a4a-198">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="d9a4a-199">データ削除パスは、サービスによって若干異なります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-199">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="d9a4a-200">Exchange Online と Skype for Business のカスタマー キーと可用性キーを取り消す</span><span class="sxs-lookup"><span data-stu-id="d9a4a-200">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="d9a4a-201">Exchange Online および Skype for Business のデータ削除パスを開始すると、DEP に永続的なデータ削除要求を設定します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-201">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="d9a4a-202">これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-202">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="d9a4a-203">PowerShell コマンドレットは一度に 1 つの DEP に対してしか実行できないので、データ削除パスを開始する前に、1 つの DEP をすべてのメールボックスに再割り当てする方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-203">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="d9a4a-204">データ削除パスを使用して、メールボックスのサブセットを削除しない。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-204">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="d9a4a-205">このプロセスは、サービスを終了する顧客のみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-205">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="d9a4a-206">データ削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-206">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="d9a4a-207">Azure Key Vaults から "O365 Exchange Online" のラップとアンラップのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-207">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="d9a4a-208">組織内でグローバル管理者特権を持つ仕事または学校のアカウントを使用して [、Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-208">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="d9a4a-209">削除するメールボックスを含む DEP ごとに、次のように [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-209">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="d9a4a-210">コマンドが失敗した場合は、このタスクで前に指定したように、Azure Key Vault の両方のキーから Exchange Online のアクセス許可を削除してください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-210">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="d9a4a-211">Set-DataEncryptionPolicy コマンドレットを使用して PermanentDataPurgeRequested スイッチを設定すると、この DEP をメールボックスに割り当てなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-211"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="d9a4a-212">Microsoft のサポートに問い合わせ、データ削除 eDocument を要求します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-212">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="d9a4a-213">Microsoft は、要求に応じて、データの削除を承認および承認する法的文書を送信します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-213">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="d9a4a-214">オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-214">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d9a4a-215">通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-215">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="d9a4a-216">代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-216">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="d9a4a-217">Microsoft が法的文書を受け取った後、Microsoft はコマンドレットを実行してデータ削除をトリガーし、最初にポリシーを削除し、メールボックスに完全な削除のマークを付け、可用性キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-217">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="d9a4a-218">データ削除プロセスが完了すると、データは削除され、Exchange Online にアクセスできなくなり、回復できません。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-218">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="d9a4a-219">SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーと可用性キーを取り消す</span><span class="sxs-lookup"><span data-stu-id="d9a4a-219">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="d9a4a-220">SharePoint Online、OneDrive for Business、Teams ファイルのデータ削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-220">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="d9a4a-221">Azure Key Vault アクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-221">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="d9a4a-222">すべてのキー コンテナー管理者は、アクセスを取り消すことに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-222">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="d9a4a-223">SharePoint Online の Azure Key Vault は削除されません。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-223">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="d9a4a-224">キー コンテナーは、複数の SharePoint Online テナントと DEP 間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-224">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="d9a4a-225">可用性キーを削除するには、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-225">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="d9a4a-226">可用性キーを削除するために Microsoft に連絡すると、法的文書が送信されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-226">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="d9a4a-227">オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-227">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="d9a4a-228">通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-228">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="d9a4a-229">代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-229">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="d9a4a-230">Microsoft が法的文書を受け取った後、コマンドレットを実行して、テナント キー、サイト キー、およびドキュメントごとの個々のキーの暗号化削除を実行するデータ削除をトリガーし、キー階層を取り消し可能に壊します。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-230">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="d9a4a-231">データ削除コマンドレットが完了すると、データは削除されます。</span><span class="sxs-lookup"><span data-stu-id="d9a4a-231">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d9a4a-232">関連記事</span><span class="sxs-lookup"><span data-stu-id="d9a4a-232">Related articles</span></span>

- [<span data-ttu-id="d9a4a-233">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="d9a4a-233">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="d9a4a-234">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="d9a4a-234">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="d9a4a-235">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="d9a4a-235">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="d9a4a-236">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="d9a4a-236">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="d9a4a-237">カスタマー ロックボックス</span><span class="sxs-lookup"><span data-stu-id="d9a4a-237">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="d9a4a-238">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="d9a4a-238">Service Encryption</span></span>](office-365-service-encryption.md)