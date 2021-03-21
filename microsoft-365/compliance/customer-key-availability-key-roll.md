---
title: カスタマー キーまたは可用性キーをローリングまたはローテーションする
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
description: 顧客キーで使用される Azure Key Vault に格納されている顧客ルート キーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルが含まれます。
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923333"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="a45df-104">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="a45df-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="a45df-105">セキュリティ要件またはコンプライアンス要件によってキーをロールする必要がある場合にのみ、顧客キーで使用する暗号化キーをロールします。</span><span class="sxs-lookup"><span data-stu-id="a45df-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="a45df-106">また、ポリシーに関連付けられているキーや関連付けられたキーは削除しない。</span><span class="sxs-lookup"><span data-stu-id="a45df-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="a45df-107">キーをロールすると、前のキーで暗号化されたコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="a45df-108">たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブなメールボックス、切断されたメールボックス、および無効になっているメールボックスは、以前のキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="a45df-109">SharePoint Online は復元および回復の目的でコンテンツのバックアップを実行します。そのため、古いキーを使用してコンテンツがアーカイブされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a45df-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="a45df-110">可用性キーのローリングについて</span><span class="sxs-lookup"><span data-stu-id="a45df-110">About rolling the availability key</span></span>

<span data-ttu-id="a45df-111">Microsoft は、可用性キーの直接制御を顧客に公開しない。</span><span class="sxs-lookup"><span data-stu-id="a45df-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="a45df-112">たとえば、Azure Key Vault で所有しているキーのみをロール (回転) できます。</span><span class="sxs-lookup"><span data-stu-id="a45df-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="a45df-113">Microsoft 365 は、内部で定義されたスケジュールで可用性キーをロールします。</span><span class="sxs-lookup"><span data-stu-id="a45df-113">Microsoft 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="a45df-114">これらの主要なロールには、顧客向けサービス レベル契約 (SLA) はありません。</span><span class="sxs-lookup"><span data-stu-id="a45df-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="a45df-115">Microsoft 365 は、自動化された手動以外のプロセスで Microsoft 365 サービス コードを使用して可用性キーをローテーションします。</span><span class="sxs-lookup"><span data-stu-id="a45df-115">Microsoft 365 rotates the availability key using Microsoft 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="a45df-116">Microsoft 管理者は、ロール プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="a45df-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="a45df-117">キーは、キー ストアに直接アクセスせずに自動化されたメカニズムを使用してロールされます。</span><span class="sxs-lookup"><span data-stu-id="a45df-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="a45df-118">可用性キー シークレット ストアへのアクセスは、Microsoft 管理者にプロビジョニングされません。</span><span class="sxs-lookup"><span data-stu-id="a45df-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="a45df-119">可用性キーのローリングでは、最初にキーを生成するのと同じメカニズムが利用されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="a45df-120">可用性キーの詳細については、「可用性キー [について」を参照してください](customer-key-availability-key-understand.md)。</span><span class="sxs-lookup"><span data-stu-id="a45df-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a45df-121">Exchange Online および Skype for Business 可用性キーは、作成する DEP ごとに一意の可用性キーが生成されるので、新しい DEP を作成する顧客が効果的にロールできます。</span><span class="sxs-lookup"><span data-stu-id="a45df-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="a45df-122">SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーはフォレスト レベルで存在し、DEP と顧客間で共有されます。つまり、ローリングは Microsoft 内部で定義されたスケジュールでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="a45df-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="a45df-123">新しい DEP が作成されるごとに可用性キーを展開しないリスクを軽減するために、SharePoint、OneDrive、Teams は、新しい DEP が作成されるごとに、顧客のルート キーと可用性キーによってラップされたキーであるテナント中間キー (TIK) をロールします。</span><span class="sxs-lookup"><span data-stu-id="a45df-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="a45df-124">ロールする各既存のルート キーの新しいバージョンを要求する</span><span class="sxs-lookup"><span data-stu-id="a45df-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="a45df-125">キーをロールするときに、既存のキーの新しいバージョンを要求します。</span><span class="sxs-lookup"><span data-stu-id="a45df-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="a45df-126">既存のキーの新しいバージョンを要求するには、最初にキーを作成したのと同じ構文で、同じコマンドレット [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a45df-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="a45df-127">データ暗号化ポリシー (DEP) に関連付けられたキーのローリングが完了したら、別のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="a45df-127">After you've finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="a45df-128">各 Azure Key Vault (AKV) でこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="a45df-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a45df-129">For example:</span></span>

1. <span data-ttu-id="a45df-130">Azure PowerShell を使用して Azure サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="a45df-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="a45df-131">手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。</span><span class="sxs-lookup"><span data-stu-id="a45df-131">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="a45df-132">次の例Add-AzKeyVaultKey、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="a45df-133">この例では **、Contoso-O365EX-NA-VaultA1-Key001** という名前のキーが **Contoso-O365EX-NA-VaultA1** コンテナーに存在する場合、コマンドレットは新しいバージョンのキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a45df-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="a45df-134">この操作では、キーのバージョン履歴内の以前のキー バージョンが保持されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="a45df-135">暗号化されたデータを復号化するには、以前のキー バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="a45df-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="a45df-136">DEP に関連付けられたキーのローリングが完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="a45df-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="a45df-137">次のセクションでは、コマンドレットの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="a45df-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="a45df-138">Exchange Online および Skype for Business のカスタマー キーを更新する</span><span class="sxs-lookup"><span data-stu-id="a45df-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="a45df-139">Exchange Online および Skype for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーをポイントするように DEP を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a45df-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="a45df-140">これにより、可用性キーはローテーションされない。</span><span class="sxs-lookup"><span data-stu-id="a45df-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="a45df-141">新しいキーを使用してメールボックスを暗号化するように顧客キーに指示するには、次のように Set-DataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-141">To instruct Customer Key to use the new key to encrypt mailboxes, run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="a45df-142">Azure PowerShell でSet-DataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="a45df-143">72 時間以内に、この DEP に関連付けられているアクティブなメールボックスが新しいキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="a45df-144">メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「メールボックスに割り当てられた DEP を決定する」の手順 [を使用します](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="a45df-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="a45df-145">サービスが更新されたキーを適用すると、このプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a45df-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="a45df-146">SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーを更新する</span><span class="sxs-lookup"><span data-stu-id="a45df-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="a45df-147">SharePoint Online では、一度に 1 つのキーのみをロールできます。</span><span class="sxs-lookup"><span data-stu-id="a45df-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="a45df-148">キー コンテナーで両方のキーをロールする場合は、最初の操作が完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a45df-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="a45df-149">Microsoft では、この問題を回避するために操作をずらしてください。</span><span class="sxs-lookup"><span data-stu-id="a45df-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="a45df-150">SharePoint Online および OneDrive for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、DEP を更新して新しいキーをポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a45df-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="a45df-151">これにより、可用性キーはローテーションされない。</span><span class="sxs-lookup"><span data-stu-id="a45df-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="a45df-152">次のようにUpdate-SPODataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="a45df-153">このコマンドレットは、SharePoint Online および OneDrive for Business のキー ロール操作を開始しますが、アクションはすぐには完了されません。</span><span class="sxs-lookup"><span data-stu-id="a45df-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="a45df-154">キー ロール操作の進行状況を確認するには、次のように Get-SPODataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a45df-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="a45df-155">関連記事</span><span class="sxs-lookup"><span data-stu-id="a45df-155">Related articles</span></span>

- [<span data-ttu-id="a45df-156">顧客キーによるサービスの暗号化 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="a45df-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="a45df-157">Office 365 のカスタマー キーを設定する</span><span class="sxs-lookup"><span data-stu-id="a45df-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="a45df-158">Office 365 のカスタマー キーを管理する</span><span class="sxs-lookup"><span data-stu-id="a45df-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="a45df-159">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="a45df-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)