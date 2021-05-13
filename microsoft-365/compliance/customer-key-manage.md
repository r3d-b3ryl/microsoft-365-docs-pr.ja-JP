---
title: 顧客キーの管理
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーを設定した後、AKV キーを復元し、アクセス許可を管理し、データ暗号化ポリシーを作成および割り当て、管理する方法について説明します。
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345060"
---
# <a name="manage-customer-key"></a><span data-ttu-id="f59ee-103">顧客キーの管理</span><span class="sxs-lookup"><span data-stu-id="f59ee-103">Manage Customer Key</span></span>

<span data-ttu-id="f59ee-104">顧客キーの設定がOffice 365、1 つ以上のデータ暗号化ポリシー (DEP) を作成して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="f59ee-105">DEP を割り当てしたら、この記事の説明に従ってキーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="f59ee-106">関連トピックの顧客キーの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="f59ee-107">すべてのテナント ユーザーに対して複数のワークロードで使用する DEP を作成する</span><span class="sxs-lookup"><span data-stu-id="f59ee-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="f59ee-108">開始する前に、顧客のセットアップに必要なタスクが完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="f59ee-109">詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="f59ee-110">DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="f59ee-111">詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="f59ee-112">複数ワークロード DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="f59ee-113">ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。</span><span class="sxs-lookup"><span data-stu-id="f59ee-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="f59ee-114">DEP を作成するには、次のコマンドレットNew-M365DataAtRestEncryptionPolicyします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="f59ee-115">ここで、</span><span class="sxs-lookup"><span data-stu-id="f59ee-115">Where:</span></span>

   - <span data-ttu-id="f59ee-116">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="f59ee-117">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-117">Names can't contain spaces.</span></span> <span data-ttu-id="f59ee-118">たとえば、Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="f59ee-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="f59ee-119">*KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="f59ee-120">たとえば、「 <https://contosoWestUSvault1.vault.azure.net/keys/Key_01> 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="f59ee-121">*KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="f59ee-122">たとえば、「 <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02> 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="f59ee-123">2 つの URI をコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="f59ee-124">*ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="f59ee-125">説明にスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-125">You can include spaces in the description.</span></span> <span data-ttu-id="f59ee-126">たとえば、「テナント内のすべてのユーザーに対する複数のワークロードのルート ポリシー」です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="f59ee-127">例:</span><span class="sxs-lookup"><span data-stu-id="f59ee-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="f59ee-128">複数ワークロード ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="f59ee-128">Assign multi-workload policy</span></span>

<span data-ttu-id="f59ee-129">このコマンドレットを使用して DEP をSet-M365DataAtRestEncryptionPolicyAssignmentします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="f59ee-130">ポリシーを割り当てるとMicrosoft 365 DEP で識別されたキーを使用してデータが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="f59ee-131">PolicyName *は* ポリシーの名前です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="f59ee-132">たとえば、Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="f59ee-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="f59ee-133">例:</span><span class="sxs-lookup"><span data-stu-id="f59ee-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="f59ee-134">メールボックスで使用する DEP をExchange Onlineする</span><span class="sxs-lookup"><span data-stu-id="f59ee-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="f59ee-135">開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="f59ee-136">詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="f59ee-137">これらの手順は、リモートでユーザーに接続し、Exchange OnlineをWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f59ee-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="f59ee-138">DEP は、Azure Key Vault に格納されている一連のキーに関連付けられる。</span><span class="sxs-lookup"><span data-stu-id="f59ee-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="f59ee-139">DEP をメールボックスに割り当てるには、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f59ee-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="f59ee-140">Microsoft 365ポリシーで識別されたキーを使用してメールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="f59ee-141">DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="f59ee-142">詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="f59ee-143">覚えておいてください!</span><span class="sxs-lookup"><span data-stu-id="f59ee-143">Remember!</span></span> <span data-ttu-id="f59ee-144">DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="f59ee-145">地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="f59ee-146">メールボックスで使用する DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="f59ee-147">ローカル コンピューターで、組織内にグローバル管理者または Exchange Online 管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f59ee-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="f59ee-148">DEP を作成するには、次のコマンドNew-DataEncryptionPolicyコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="f59ee-149">ここで、</span><span class="sxs-lookup"><span data-stu-id="f59ee-149">Where:</span></span>

   - <span data-ttu-id="f59ee-150">*PolicyName* は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="f59ee-151">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-151">Names can't contain spaces.</span></span> <span data-ttu-id="f59ee-152">たとえば、USA_mailboxes。</span><span class="sxs-lookup"><span data-stu-id="f59ee-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="f59ee-153">*ポリシーの* 説明は、ポリシーの内容を思い出すのに役立つ、ユーザーフレンドリーなポリシーの説明です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="f59ee-154">説明にスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-154">You can include spaces in the description.</span></span> <span data-ttu-id="f59ee-155">たとえば、「米国とその地域のメールボックスのルート キー」です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="f59ee-156">*KeyVaultURI1 は* 、ポリシーの最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="f59ee-157">たとえば、「 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01> 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="f59ee-158">*KeyVaultURI2* は、ポリシー内の 2 番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="f59ee-159">たとえば、「 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02> 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="f59ee-160">2 つの URI をコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="f59ee-161">例:</span><span class="sxs-lookup"><span data-stu-id="f59ee-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="f59ee-162">構文とパラメーターの詳細については [、「New-DataEncryptionPolicy」を参照してください](/powershell/module/exchange/new-data-encryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="f59ee-163">メールボックスへの DEP の割り当て</span><span class="sxs-lookup"><span data-stu-id="f59ee-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="f59ee-164">DEP をメールボックスに割り当てるには、このコマンドレットSet-Mailboxします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="f59ee-165">ポリシーを割り当てるとMicrosoft 365 DEP で識別されたキーを使用してメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="f59ee-166">*MailboxIdParameter はユーザー* メールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="f59ee-167">このコマンドレットの詳細についてはSet-Mailbox [Set-Mailbox を参照してください](/powershell/module/exchange/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="f59ee-168">ハイブリッド環境では、DEP をオンプレミスのメールボックス データに割り当て、そのデータをテナントにExchange Onlineできます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="f59ee-169">この同期されたメールボックス データに DEP を割り当てるには、次のコマンドレットSet-MailUserします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="f59ee-170">ハイブリッド環境のメールボックス データの詳細については、「ハイブリッドモダン認証を使用した iOS および Android 用 Outlookを使用するオンプレミスのメールボックス」[を参照してください](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="f59ee-171">*MailUserIdParameter はメール* ユーザー (メールが有効なユーザーとも呼ばれる) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="f59ee-172">このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="f59ee-173">オンライン、オンライン、SharePoint、およびOneDrive for Businessで使用Teamsする</span><span class="sxs-lookup"><span data-stu-id="f59ee-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="f59ee-174">開始する前に、Azure Key Vault のセットアップに必要なタスクが完了している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="f59ee-175">詳細については、「 [顧客キーの設定」を参照してください](customer-key-set-up.md)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="f59ee-176">SharePoint Online、OneDrive for Business、および Teams ファイルのカスタマー キーを設定するには、SharePoint Online と Windows PowerShell でリモート接続して、これらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="f59ee-177">DEP を Azure Key Vault に格納されている一連のキーに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="f59ee-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="f59ee-178">DEP は、地理と呼ばれる 1 つの地理的な場所のすべてのデータに適用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="f59ee-179">Office 365 の複数地域機能を使用する場合は、geo ごとに異なるキーを使用する機能を使用して、地域ごとに 1 つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="f59ee-180">複数地域を使用していない場合は、SharePoint Online、OneDrive for Business、および Teams ファイルで使用するために、組織内に 1 つの DEP をTeamsできます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="f59ee-181">Microsoft 365 DEP で識別されたキーを使用して、その地域のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="f59ee-182">DEP を作成するには、セットアップ時に取得した Key Vault URI が必要です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="f59ee-183">詳細については、「Azure [Key Vault キーごとに URI を取得する」を参照してください](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="f59ee-184">覚えておいてください!</span><span class="sxs-lookup"><span data-stu-id="f59ee-184">Remember!</span></span> <span data-ttu-id="f59ee-185">DEP を作成する場合は、2 つの異なる Azure キー コンテナーに 2 つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="f59ee-186">地理的冗長性を確保するために、これらのキーを 2 つの別個の Azure リージョンに作成します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="f59ee-187">DEP を作成するには、サーバーを使用してオンラインSharePointリモート接続するWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f59ee-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="f59ee-188">ローカル コンピューターで、組織内にグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、オンライン[PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)ConnectをSharePointします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="f59ee-189">[管理シェルMicrosoft Office SharePoint Onlineで、次のようにRegister-SPODataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="f59ee-190">例:</span><span class="sxs-lookup"><span data-stu-id="f59ee-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="f59ee-191">DEP を登録すると、geo のデータで暗号化が開始されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="f59ee-192">暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-192">Encryption can take some time.</span></span> <span data-ttu-id="f59ee-193">このパラメーターの使用の詳細については [、「Register-SPODataEncryptionPolicy」を参照してください](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="f59ee-194">メールボックス用に作成した DEP をExchange Onlineする</span><span class="sxs-lookup"><span data-stu-id="f59ee-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="f59ee-195">メールボックス用に作成したすべての DEP の一覧を表示するには、PowerShell コマンドレットGet-DataEncryptionPolicy使用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="f59ee-196">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f59ee-197">組織内のすべての DEP を返す場合は、パラメーターを指定せずに Get-DataEncryptionPolicyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="f59ee-198">このコマンドレットの詳細についてはGet-DataEncryptionPolicy [Get-DataEncryptionPolicy を参照してください](/powershell/module/exchange/get-dataencryptionpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="f59ee-199">メールボックスをクラウドに移行する前に DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="f59ee-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="f59ee-200">DEP を割り当てるMicrosoft 365、移行中に割り当てられた DEP を使用してメールボックスの内容を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="f59ee-201">このプロセスは、メールボックスの移行、DEP の割り当て、暗号化の実行を待機するよりも効率的です。これには数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="f59ee-202">DEP をメールボックスに移行する前にメールボックスに割り当てるにはOffice 365 PowerShell で Set-MailUser コマンドレットExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="f59ee-203">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f59ee-204">このコマンドレットをSet-MailUserします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="f59ee-205">*GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し *、DataEncryptionPolicyIdParameter* は DEP の ID です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="f59ee-206">このコマンドレットの詳細についてはSet-MailUser [Set-MailUser を参照してください](/powershell/module/exchange/set-mailuser)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="f59ee-207">メールボックスに割り当てられた DEP を決定する</span><span class="sxs-lookup"><span data-stu-id="f59ee-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="f59ee-208">メールボックスに割り当てられた DEP を確認するには、次のコマンドレットGet-MailboxStatisticsします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="f59ee-209">コマンドレットは、一意の識別子 (GUID) を返します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="f59ee-210">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="f59ee-211">*GeneralMailboxOrMailUserIdParameter は* メールボックスを指定し、DataEncryptionPolicyID は DEP の GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="f59ee-212">このコマンドレットの詳細についてはGet-MailboxStatistics [Get-MailboxStatistics を参照してください](/powershell/module/exchange/get-mailboxstatistics)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="f59ee-213">このコマンドレットGet-DataEncryptionPolicy実行して、メールボックスが割り当てられている DEP の表示名を確認します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="f59ee-214">ここで *、GUID* は、前の手順の Get-MailboxStatisticsコマンドレットによって返される GUID です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="f59ee-215">顧客キーが暗号化を完了したのを確認する</span><span class="sxs-lookup"><span data-stu-id="f59ee-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="f59ee-216">顧客キーをロールしたかどうか、新しい DEP を割り当てたか、メールボックスを移行した場合でも、このセクションの手順を使用して、暗号化が完了します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="f59ee-217">メールボックスの暗号化が完了Exchange Onlineする</span><span class="sxs-lookup"><span data-stu-id="f59ee-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="f59ee-218">メールボックスの暗号化には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="f59ee-219">初めて暗号化を行う場合は、サービスがメールボックスを暗号化する前に、メールボックスをあるデータベースから別のデータベースに完全に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="f59ee-220">メールボックスが暗号化Get-MailboxStatisticsを判断するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="f59ee-221">IsEncrypted プロパティは、メールボックスが暗号化されている場合は true、メールボックスが暗号化されていない場合は **false** の値を返します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="f59ee-222">メールボックスの移動を完了する時間は、初めて DEP を割り当てるメールボックスの数と、メールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="f59ee-223">DEP を割り当てた時刻から 1 週間後にメールボックスが暗号化されていない場合は、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="f59ee-224">このNew-MoveRequestは、ローカル メールボックスの移動に使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f59ee-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="f59ee-225">詳細については [、このお知](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) らせを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="f59ee-226">オンライン、SharePoint、OneDrive for BusinessファイルTeams確認する</span><span class="sxs-lookup"><span data-stu-id="f59ee-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="f59ee-227">次のように、Get-SPODataEncryptionPolicyコマンドレットを実行して、暗号化の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="f59ee-228">このコマンドレットの出力には、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="f59ee-229">主キーの URI。</span><span class="sxs-lookup"><span data-stu-id="f59ee-229">The URI of the primary key.</span></span>

- <span data-ttu-id="f59ee-230">セカンダリ キーの URI。</span><span class="sxs-lookup"><span data-stu-id="f59ee-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="f59ee-231">geo の暗号化状態。</span><span class="sxs-lookup"><span data-stu-id="f59ee-231">The encryption status for the geo.</span></span> <span data-ttu-id="f59ee-232">可能な状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f59ee-232">Possible states include:</span></span>

  - <span data-ttu-id="f59ee-233">**未登録:** 顧客キーの暗号化がまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="f59ee-234">**登録:** 顧客キーの暗号化が適用され、ファイルが暗号化中です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="f59ee-235">geo のキーが登録されている場合は、暗号化の進行状況を監視するために、geo 内のサイトが完了した割合に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="f59ee-236">**登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="f59ee-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="f59ee-237">**ローリング:** キー ロールが進行中です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="f59ee-238">geo のキーがローリングされている場合は、キー ロール操作を完了したサイトの割合に関する情報も表示され、進行状況を監視できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="f59ee-239">複数のワークロードで使用する DEP の詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="f59ee-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="f59ee-240">複数のワークロードで使用するために作成した DEP の詳細を取得するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="f59ee-241">ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。</span><span class="sxs-lookup"><span data-stu-id="f59ee-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="f59ee-242">組織内のすべての複数ワークロード DEP の一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="f59ee-243">特定の DEP に関する詳細を返す場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="f59ee-244">この例では、"Contoso_Global" という名前の DEP の詳細情報を返Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="f59ee-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="f59ee-245">複数ワークロードの DEP 割り当て情報を取得する</span><span class="sxs-lookup"><span data-stu-id="f59ee-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="f59ee-246">現在テナントに割り当てられている DEP を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="f59ee-247">ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。</span><span class="sxs-lookup"><span data-stu-id="f59ee-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="f59ee-248">このコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="f59ee-249">複数ワークロード DEP を無効にする</span><span class="sxs-lookup"><span data-stu-id="f59ee-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="f59ee-250">マルチワークロード DEP を無効にする前に、テナント内のワークロードから DEP の割り当てを解除します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="f59ee-251">複数のワークロードで使用される DEP を無効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="f59ee-252">ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。</span><span class="sxs-lookup"><span data-stu-id="f59ee-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="f59ee-253">このコマンドレットをSet-M365DataAtRestEncryptionPolicyします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="f59ee-254">PolicyName *は* 、ポリシーの名前または一意の ID です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="f59ee-255">たとえば、Contoso_Global。</span><span class="sxs-lookup"><span data-stu-id="f59ee-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="f59ee-256">例:</span><span class="sxs-lookup"><span data-stu-id="f59ee-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="f59ee-257">Azure Key Vault キーの復元</span><span class="sxs-lookup"><span data-stu-id="f59ee-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="f59ee-258">復元を実行する前に、ソフト削除によって提供される回復機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="f59ee-259">顧客キーと一緒に使用するキーはすべて、ソフト削除を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="f59ee-260">削除はごみ箱のように機能し、復元する必要なしに最大 90 日間の回復を可能にします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="f59ee-261">キーまたはキー コンテナーが失われた場合など、極端な状況や異常な状況でのみ復元が必要です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="f59ee-262">顧客キーで使用するキーを復元する必要がある場合は、次Azure PowerShell、Restore-AzureKeyVaultKeyコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="f59ee-263">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="f59ee-264">キー コンテナーに同じ名前のキーが既に含まれている場合、復元操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="f59ee-265">Restore-AzKeyVaultKey、すべてのキー バージョンと、キー名を含むキーのすべてのメタデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="f59ee-266">キー コンテナーのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="f59ee-266">Manage key vault permissions</span></span>

<span data-ttu-id="f59ee-267">いくつかのコマンドレットを使用して、キー コンテナーのアクセス許可を表示したり、必要に応じて削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="f59ee-268">従業員がチームを離れる場合など、アクセス許可を削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="f59ee-269">これらの各タスクに対して、このタスクを使用Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f59ee-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="f59ee-270">詳細については、「Azure PowerShellの[概要」を参照Azure PowerShell。](/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="f59ee-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="f59ee-271">キー コンテナーのアクセス許可を表示するには、次のコマンドレットGet-AzKeyVaultします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="f59ee-272">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="f59ee-273">管理者のアクセス許可を削除するには、次のコマンドレットをRemove-AzKeyVaultAccessPolicyします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="f59ee-274">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="f59ee-275">顧客キーから Microsoft マネージ キーへのロールバック</span><span class="sxs-lookup"><span data-stu-id="f59ee-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="f59ee-276">Microsoft で管理されているキーに戻す必要がある場合は、可能です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="f59ee-277">オフボードの場合、データは、個々のワークロードでサポートされる既定の暗号化を使用して再暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="f59ee-278">たとえば、Microsoft Exchange Onlineキーを使用した既定の暗号化がサポートされている場合です。</span><span class="sxs-lookup"><span data-stu-id="f59ee-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f59ee-279">オフボードは、データ削除と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="f59ee-280">データの削除は、組織のデータを完全に暗号化削除し、Microsoft 365オフボードから削除します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="f59ee-281">複数のワークロード ポリシーに対してデータ削除を実行できない。</span><span class="sxs-lookup"><span data-stu-id="f59ee-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="f59ee-282">マルチワークロード DEP の割り当てに顧客キーを使用しない場合は、顧客キーから "offboard" への要求を受け取って Microsoft サポートに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="f59ee-283">サポート チームに、顧客キー チームに対してサービス要求Microsoft 365依頼します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="f59ee-284">質問がある場合 m365-ck@service.microsoft.com に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="f59ee-285">メールボックス レベルの DEP を使用して個々のメールボックスを暗号化しない場合は、すべてのメールボックスからメールボックス レベルの DEP の割り当てを解除できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="f59ee-286">メールボックス DEP の割り当てを解除するには、PowerShell コマンドレットSet-Mailbox使用します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="f59ee-287">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して[、PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)にExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f59ee-288">このコマンドレットをSet-Mailboxします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="f59ee-289">このコマンドレットを実行すると、現在割り当てられている DEP の割り当てを解除し、既定の Microsoft 管理キーに関連付けられた DEP を使用してメールボックスを再暗号化します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="f59ee-290">Microsoft マネージ キーで使用される DEP の割り当てを解除できません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="f59ee-291">Microsoft で管理されているキーを使用しない場合は、別の顧客キー DEP をメールボックスに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="f59ee-292">キーを取り消し、データ削除パス プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="f59ee-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="f59ee-293">可用性キーを含むすべてのルート キーの失効を制御します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="f59ee-294">顧客キーは、規制要件の出口計画の側面を制御します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="f59ee-295">データを削除してサービスを終了するためにキーを取り消す場合、データ削除プロセスが完了すると、サービスは可用性キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="f59ee-296">これは、個々のメールボックスに割り当てられている顧客キー DEP でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="f59ee-297">Microsoft 365削除パスを監査および検証します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="f59ee-298">詳細については、「SSAE 18 SOC 2 Report available on the [Service Trust Portal」を参照してください](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="f59ee-299">さらに、Microsoft では次のドキュメントを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="f59ee-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="f59ee-300">Microsoft Cloud の金融機関のリスク評価とコンプライアンス ガイド</span><span class="sxs-lookup"><span data-stu-id="f59ee-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="f59ee-301">O365 Exit Planning に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f59ee-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="f59ee-302">複数ワークロード DEP の削除は、顧客キーのMicrosoft 365サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="f59ee-303">マルチワークロード DEP は、すべてのテナント ユーザーで複数のワークロード間でデータを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="f59ee-304">このような DEP を削除すると、複数のワークロード間のデータにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="f59ee-305">サービスを完全に終了Microsoft 365場合は、文書化されたプロセスごとにテナントの削除のパスを追求できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="f59ee-306">[Azure Active Directoy でテナントを削除する方法を参照してください](/azure/active-directory/enterprise-users/directory-delete-howto)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="f59ee-307">顧客キーとユーザーキーの可用性キーをExchange Online Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f59ee-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="f59ee-308">データ の削除パスを開始Exchange Online、Skype for Business DEP に永続的なデータ削除要求を設定します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="f59ee-309">これにより、DEP が割り当てられているメールボックス内の暗号化されたデータが完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="f59ee-310">PowerShell コマンドレットは一度に 1 つの DEP に対してしか実行できないので、データ削除パスを開始する前に、1 つの DEP をすべてのメールボックスに再割り当てする方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="f59ee-311">データ削除パスを使用して、メールボックスのサブセットを削除しない。</span><span class="sxs-lookup"><span data-stu-id="f59ee-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="f59ee-312">このプロセスは、サービスを終了する顧客のみを対象とします。</span><span class="sxs-lookup"><span data-stu-id="f59ee-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="f59ee-313">データ削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="f59ee-314">Azure Key Vaults から "O365 Exchange Online" のラップとアンラップのアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="f59ee-315">組織でグローバル管理者特権を持つ仕事または学校のアカウントを使用して[、PowerShell Exchange Online接続します](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="f59ee-316">削除するメールボックスを含む DEP ごとに、次のように [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="f59ee-317">コマンドが失敗した場合は、このタスクで前に指定したように、Azure Key Vault のExchange Onlineのアクセス許可を削除してください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="f59ee-318">Set-DataEncryptionPolicy コマンドレットを使用して PermanentDataPurgeRequested スイッチを設定すると、この DEP をメールボックスに割り当てなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f59ee-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="f59ee-319">Microsoft のサポートに問い合わせ、データ削除 eDocument を要求します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="f59ee-320">Microsoft は、要求に応じて、データの削除を承認および承認する法的文書を送信します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="f59ee-321">オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="f59ee-322">通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="f59ee-323">代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="f59ee-324">Microsoft が法的文書を受け取った後、Microsoft はコマンドレットを実行してデータ削除をトリガーし、最初にポリシーを削除し、メールボックスに完全な削除のマークを付け、可用性キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="f59ee-325">データの削除プロセスが完了すると、データは削除され、Exchange Onlineにアクセスできなくなり、回復できません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="f59ee-326">お客様の顧客キーとオンライン、SharePoint、OneDrive for BusinessファイルTeams取り消す</span><span class="sxs-lookup"><span data-stu-id="f59ee-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="f59ee-327">Online、SharePoint、および OneDrive for BusinessファイルTeams削除パスを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="f59ee-328">Azure Key Vault アクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="f59ee-329">すべてのキー コンテナー管理者は、アクセスを取り消すことに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="f59ee-330">オンラインの Azure Key Vault はSharePointされません。</span><span class="sxs-lookup"><span data-stu-id="f59ee-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="f59ee-331">キー コンテナーは、複数のオンライン テナントSharePoint DEP 間で共有できます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="f59ee-332">可用性キーを削除するには、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f59ee-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="f59ee-333">可用性キーを削除するために Microsoft に連絡すると、法的文書が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="f59ee-334">オンボーディング中に FastTrack オファーで承認者としてサインアップした組織内のユーザーは、このドキュメントに署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f59ee-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="f59ee-335">通常、これは会社の役員または他の指定された人物で、組織に代わって書類に署名する法的権限を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="f59ee-336">代理人が法的文書に署名したら、それを Microsoft に返します (通常は eDoc 署名を通じて)。</span><span class="sxs-lookup"><span data-stu-id="f59ee-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="f59ee-337">Microsoft が法的文書を受け取った後、コマンドレットを実行して、テナント キー、サイト キー、およびドキュメントごとの個々のキーの暗号化削除を実行するデータ削除をトリガーし、キー階層を取り消し可能に壊します。</span><span class="sxs-lookup"><span data-stu-id="f59ee-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="f59ee-338">データ削除コマンドレットが完了すると、データは削除されます。</span><span class="sxs-lookup"><span data-stu-id="f59ee-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f59ee-339">関連記事</span><span class="sxs-lookup"><span data-stu-id="f59ee-339">Related articles</span></span>

- [<span data-ttu-id="f59ee-340">カスタマー キーによるサービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="f59ee-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="f59ee-341">可用性キーの詳細</span><span class="sxs-lookup"><span data-stu-id="f59ee-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="f59ee-342">顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="f59ee-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="f59ee-343">カスタマー キーまたは可用性キーをローリングまたはローテーションする</span><span class="sxs-lookup"><span data-stu-id="f59ee-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="f59ee-344">カスタマー ロックボックス</span><span class="sxs-lookup"><span data-stu-id="f59ee-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="f59ee-345">サービスの暗号化</span><span class="sxs-lookup"><span data-stu-id="f59ee-345">Service Encryption</span></span>](office-365-service-encryption.md)