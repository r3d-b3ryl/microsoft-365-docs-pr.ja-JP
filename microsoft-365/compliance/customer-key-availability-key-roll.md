---
title: 顧客キーまたは可用性キーをロールまたは回転する
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
description: Office 365 の顧客キーで使用される Azure Key Vault に格納されている顧客のルートキーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams の各ファイルが含まれます。
ms.openlocfilehash: 9699960666eaa9aa62bb027d3a4549cb50cd52e3
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804826"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a><span data-ttu-id="eae51-104">顧客キーまたは可用性キーをロールまたは回転する</span><span class="sxs-lookup"><span data-stu-id="eae51-104">Roll or rotate a Customer Key or an availability key</span></span>

> [!CAUTION]
> <span data-ttu-id="eae51-105">セキュリティまたはコンプライアンスの要件によってキーをロールする必要がある場合は、顧客キーと共に使用する暗号化キーのみをロールアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="eae51-105">Only roll an encryption key that you use with Customer Key when your security or compliance requirements dictate that you must roll the key.</span></span> <span data-ttu-id="eae51-106">また、ポリシーに関連付けられている、またはポリシーに関連付けられていたキーは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="eae51-106">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="eae51-107">キーをロールすると、以前のキーを使用してコンテンツが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="eae51-107">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="eae51-108">たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブ、切断済み、および無効になったメールボックスは、以前のキーで暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="eae51-108">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="eae51-109">SharePoint Online は復元と回復のためにコンテンツのバックアップを実行するので、古いキーを使用してアーカイブされたコンテンツが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="eae51-109">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span>

## <a name="about-rolling-the-availability-key"></a><span data-ttu-id="eae51-110">可用性キーのローリングについて</span><span class="sxs-lookup"><span data-stu-id="eae51-110">About rolling the availability key</span></span>

<span data-ttu-id="eae51-111">Microsoft は、お客様に可用性キーの直接制御を公開しません。</span><span class="sxs-lookup"><span data-stu-id="eae51-111">Microsoft does not expose direct control of the availability key to customers.</span></span> <span data-ttu-id="eae51-112">たとえば、Azure Key Vault で所有するキーのみをロール (回転) することができます。</span><span class="sxs-lookup"><span data-stu-id="eae51-112">For example, you can only roll (rotate) the keys that you own in Azure Key Vault.</span></span> <span data-ttu-id="eae51-113">Office 365 は、内部で定義されたスケジュールで可用性キーをロールします。</span><span class="sxs-lookup"><span data-stu-id="eae51-113">Office 365 rolls the availability keys on an internally-defined schedule.</span></span> <span data-ttu-id="eae51-114">これらの主要なロールには、顧客向けのサービスレベル契約 (SLA) はありません。</span><span class="sxs-lookup"><span data-stu-id="eae51-114">There is no customer-facing, service-level agreement (SLA) for these key rolls.</span></span> <span data-ttu-id="eae51-115">Office 365 は、手動ではない自動化されたプロセスで Office 365 サービスコードを使用して、可用性キーを回転させます。</span><span class="sxs-lookup"><span data-stu-id="eae51-115">Office 365 rotates the availability key using Office 365 service code in an automated, non-manual process.</span></span> <span data-ttu-id="eae51-116">Microsoft 管理者がロールプロセスを開始する場合があります。</span><span class="sxs-lookup"><span data-stu-id="eae51-116">Microsoft administrators may initiate the roll process.</span></span> <span data-ttu-id="eae51-117">キーは、キーストアに直接アクセスせずに自動機構を使用してロールされます。</span><span class="sxs-lookup"><span data-stu-id="eae51-117">The key is rolled using automated mechanisms without direct access to the key store.</span></span> <span data-ttu-id="eae51-118">可用性キーシークレットストアへのアクセスは、Microsoft 管理者にはプロビジョニングされません。</span><span class="sxs-lookup"><span data-stu-id="eae51-118">Access to the availability key secret store is not provisioned to Microsoft administrators.</span></span> <span data-ttu-id="eae51-119">可用性キーのローリングは、最初にキーを生成するのと同じメカニズムを利用します。</span><span class="sxs-lookup"><span data-stu-id="eae51-119">Availability key rolling leverages the same mechanism used to initially generate the key.</span></span> <span data-ttu-id="eae51-120">可用性キーの詳細については、「[可用性キーに](customer-key-availability-key-understand.md)ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae51-120">For more information about the availability key, see [Understand the availability key](customer-key-availability-key-understand.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eae51-121">Exchange Online と Skype for Business の可用性キーは、作成する DEP ごとに一意の可用性キーが生成されるため、ユーザーが新しい DEP を作成することによって効果的にロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="eae51-121">Exchange Online and Skype for Business availability keys can be effectively rolled by customers creating a new DEP, since a unique availability key is generated for each DEP you create.</span></span> <span data-ttu-id="eae51-122">SharePoint Online、OneDrive for Business、Teams の各ファイルの可用性キーは、フォレストレベルに存在し、DEPs と顧客間で共有されています。これは、Microsoft 社内で定義されたスケジュールでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="eae51-122">Availability keys for SharePoint Online, OneDrive for Business, and Teams files exist at the forest level and are shared across DEPs and customers, which means rolling only occurs at a Microsoft internally defined schedule.</span></span> <span data-ttu-id="eae51-123">新しい DEP が作成されるたびに可用性キーがロールされないリスクを軽減するために、SharePoint、OneDrive、および Teams は、新しい DEP が作成されるたびに、顧客のルートキーと可用性キーによってラップされるキーであるテナントの中間キー (TIK) をロールします。</span><span class="sxs-lookup"><span data-stu-id="eae51-123">To mitigate the risk of not rolling the availability key each time a new DEP is created, SharePoint, OneDrive, and Teams roll the tenant intermediate key (TIK), the key wrapped by the customer root keys and availability key, each time a new DEP is created.</span></span>

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a><span data-ttu-id="eae51-124">ロールアップする各既存のルートキーの新しいバージョンを要求する</span><span class="sxs-lookup"><span data-stu-id="eae51-124">Request a new version of each existing root key you want to roll</span></span>

<span data-ttu-id="eae51-125">キーをロールする場合は、新しいバージョンの既存のキーを要求します。</span><span class="sxs-lookup"><span data-stu-id="eae51-125">When you roll a key, you request a new version of an existing key.</span></span> <span data-ttu-id="eae51-126">既存のキーの新しいバージョンを要求するには、最初にキーを作成したときと同じ構文を使用して、同じコマンドレット[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)を使用します。</span><span class="sxs-lookup"><span data-stu-id="eae51-126">To request a new version of an existing key, you use the same cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), with the same syntax that you used to create the key in the first place.</span></span> <span data-ttu-id="eae51-127">データ暗号化ポリシー (DEP) に関連付けられているキーのローリングを完了した後、別のコマンドレットを実行して、顧客キーが新しいキーの使用を開始するようにします。</span><span class="sxs-lookup"><span data-stu-id="eae51-127">After you’ve finished rolling any key associated with a Data Encryption Policy (DEP), you run another cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="eae51-128">各 Azure Key Vault (AKV) でこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-128">Do this step in each Azure Key Vault (AKV).</span></span>

<span data-ttu-id="eae51-129">例:</span><span class="sxs-lookup"><span data-stu-id="eae51-129">For example:</span></span>

1. <span data-ttu-id="eae51-130">Azure PowerShell を使用して Azure サブスクリプションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="eae51-130">Sign in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="eae51-131">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eae51-131">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="eae51-132">次の例に示されているように、AzKeyVaultKey コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-132">Run the Add-AzKeyVaultKey cmdlet as shown in the following example:</span></span>

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   <span data-ttu-id="eae51-133">この例では、O365EX という名前のキーが**VaultA1-Key001** **vault に**存在するため、このコマンドレットによってキーの新しいバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eae51-133">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** exists in the **Contoso-O365EX-NA-VaultA1** vault, the cmdlet creates a new version of the key.</span></span> <span data-ttu-id="eae51-134">この操作により、キーのバージョン履歴にある以前のキーバージョンが保持されます。</span><span class="sxs-lookup"><span data-stu-id="eae51-134">This operation preserves the previous key versions in the version history for the key.</span></span> <span data-ttu-id="eae51-135">暗号化されたデータを復号化するには、以前のキーバージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="eae51-135">You need the previous key version to decrypt the data that it still encrypts.</span></span> <span data-ttu-id="eae51-136">DEP に関連付けられているキーのロールアウトを完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーの使用を開始していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eae51-136">Once you complete rolling any key associated with a DEP,  run an extra cmdlet to ensure that Customer Key begins using the new key.</span></span> <span data-ttu-id="eae51-137">次のセクションでは、コマンドレットについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="eae51-137">The following sections describe the cmdlets in more detail.</span></span>
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="eae51-138">Exchange Online と Skype for Business の顧客キーを更新する</span><span class="sxs-lookup"><span data-stu-id="eae51-138">Update the Customer Key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="eae51-139">Exchange Online と Skype for Business で使用されている DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、新しいキーをポイントするように DEP を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae51-139">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="eae51-140">これは、可用性キーを回転させません。</span><span class="sxs-lookup"><span data-stu-id="eae51-140">This does not rotate the availability key.</span></span>

<span data-ttu-id="eae51-141">Office 365 でメールボックスを暗号化するために新しいキーを使用するよう顧客キーに指示するには、次のように、Set-DataEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-141">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>

1. <span data-ttu-id="eae51-142">Azure PowerShell で Set-DataEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-142">Run the Set-DataEncryptionPolicy cmdlet in Azure PowerShell:</span></span>
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   <span data-ttu-id="eae51-143">72時間以内に、この DEP に関連付けられているアクティブなメールボックスは新しいキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="eae51-143">Within 72 hours, the active mailboxes associated with this DEP become encrypted with the new key.</span></span>

2. <span data-ttu-id="eae51-144">メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「[メールボックスに DEP が割り当てられているかどうかを判断](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)する」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="eae51-144">To check the value for the DataEncryptionPolicyID property for the mailbox, use the steps in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox).</span></span> <span data-ttu-id="eae51-145">このプロパティの値は、更新されたキーがサービスによって適用されると変更されます。</span><span class="sxs-lookup"><span data-stu-id="eae51-145">The value for this property changes once the service applies the updated key.</span></span>
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="eae51-146">SharePoint Online、OneDrive for Business、および Teams ファイルの顧客キーを更新する</span><span class="sxs-lookup"><span data-stu-id="eae51-146">Update the Customer Key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="eae51-147">SharePoint Online では、一度に1つのキーのみをロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="eae51-147">SharePoint Online only allows you to roll one key at a time.</span></span> <span data-ttu-id="eae51-148">キーコンテナーで両方のキーをロールする場合は、最初の操作が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="eae51-148">If you want to roll both keys in a key vault, wait for the first operation to complete.</span></span> <span data-ttu-id="eae51-149">Microsoft では、この問題を回避するために運用をずらすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eae51-149">Microsoft recommends that you stagger your operations to avoid this issue.</span></span> <span data-ttu-id="eae51-150">SharePoint Online と OneDrive for business で使用されている DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、新しいキーをポイントするように DEP を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eae51-150">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must update the DEP to point to the new key.</span></span> <span data-ttu-id="eae51-151">これは、可用性キーを回転させません。</span><span class="sxs-lookup"><span data-stu-id="eae51-151">This does not rotate the availability key.</span></span>

1. <span data-ttu-id="eae51-152">Get-spodataencryptionpolicy コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-152">Run the Update-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   <span data-ttu-id="eae51-153">このコマンドレットは、SharePoint Online と OneDrive for business のキーロール操作を開始しますが、アクションはすぐには完了しません。</span><span class="sxs-lookup"><span data-stu-id="eae51-153">While this cmdlet starts the key roll operation for SharePoint Online and OneDrive for Business, the action doesn't complete immediately.</span></span>

2. <span data-ttu-id="eae51-154">キーロール操作の進行状況を確認するには、次のように Get-spodataencryptionpolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="eae51-154">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a><span data-ttu-id="eae51-155">関連記事</span><span class="sxs-lookup"><span data-stu-id="eae51-155">Related articles</span></span>

- [<span data-ttu-id="eae51-156">Office 365 の顧客キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="eae51-156">Service encryption with Customer Key for Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="eae51-157">Office 365 の顧客キーを設定する</span><span class="sxs-lookup"><span data-stu-id="eae51-157">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="eae51-158">Office 用の顧客キーの管理365</span><span class="sxs-lookup"><span data-stu-id="eae51-158">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="eae51-159">可用性キーについて</span><span class="sxs-lookup"><span data-stu-id="eae51-159">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)
